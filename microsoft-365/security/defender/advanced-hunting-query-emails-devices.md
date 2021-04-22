---
title: Охота на угрозы на устройствах, электронных письмах, приложениях и удостоверениях с расширенным поиском
description: Изучите распространенные сценарии охоты и примеры запросов, которые охватывают устройства, электронные почты, приложения и удостоверения.
keywords: расширенный поиск, данные Office365, устройства Windows, электронные почты Office365 нормализуются, сообщения электронной почты, приложения, удостоверения, охота на угрозы, поиск, запрос, телеметрия, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8a811d60af281bb534776736e77c3eb54ab6a760
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932969"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Охота за угрозами на различных устройствах, в письмах, приложениях и удостоверениях

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[Расширенный поиск](advanced-hunting-overview.md) в Microsoft 365 Defender позволяет активно искать угрозы по всему:
- Устройства, управляемые Microsoft Defender для конечной точки
- Сообщения электронной почты, обработанные Microsoft 365
- Действия облачного приложения, события проверки подлинности и действия контроллера домена, отслеживаются службами безопасности облачных приложений Microsoft и Microsoft Defender for Identity

С помощью этого уровня видимости можно быстро искать угрозы, которые пересекают разделы вашей сети, включая сложные вторжения, которые поступают по электронной почте или в Интернете, повысить местные привилегии, получить привилегированные учетные данные домена и перейти на другие устройства. 

Вот общие методы и примеры запросов, основанных на различных сценариях охоты, которые помогут вам изучить, как можно создавать запросы при поиске таких сложных угроз.

## <a name="get-entity-info"></a>Получить сведения об объектах
Используйте эти запросы, чтобы узнать, как быстро получить сведения о учетных записях пользователей, устройствах и файлах. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Получение учетных записей пользователей из адресов электронной почты
При формировании запросов по [таблицам, относящимся к устройствам и сообщениям электронной почты](advanced-hunting-schema-tables.md) может возникать необходимость получить названия учетных записей пользователей из электронных адресов отправителя или получателя. Обычно это можно сделать для адреса получателя или отправщика с помощью *локального* хоста с адреса электронной почты.

В приведенной ниже фрагменте мы используем функцию [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto для извлечения локального хоста прямо перед адресами электронной почты получателей в `@` столбце `RecipientEmailAddress` .

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
В ниже приведеном ниже запросе показано, как можно использовать этот фрагмент:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>Объединение таблицы IdentityInfo

Вы можете получить имена учетных записей и другие сведения об учетной записи путем слияния или присоединения к [таблице IdentityInfo.](advanced-hunting-identityinfo-table.md) В приведенной ниже области запрос получает список обнаружения фишинга и вредоносных программ из таблицы [EmailEvents,](advanced-hunting-emailevents-table.md) а затем присоединяется к этой информации со таблицей, чтобы получить подробные сведения о каждом `IdentityInfo` получателе. 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where ThreatTypes has "Malware" or ThreatTypes has "Phish"
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, ThreatTypes, 
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>Получить сведения об устройстве
[Передовая схема охоты содержит](advanced-hunting-schema-tables.md) обширные сведения о устройстве в различных таблицах. Например, [таблица DeviceInfo предоставляет](advanced-hunting-deviceinfo-table.md) всестороннюю информацию об устройстве на основе регулярно агрегированных данных событий. В этом запросе используется таблица, чтобы проверить, вошел ли потенциально скомпрометированный пользователь на любые устройства, а затем перечислить оповещения, срабатывав на `DeviceInfo` `<account-name>` этих устройствах.

>[!Tip]
> Этот запрос использует для указания внутреннего присоединяния, которое предотвращает `kind=inner` [](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)декупликацию значений левой стороны `DeviceId` для .

```kusto
DeviceInfo
//Query for devices that the potentially compromised account has logged onto
| where LoggedOnUsers contains '<account-name>'
| distinct DeviceId
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables
| join kind=inner AlertEvidence on DeviceId
| project AlertId
//List all alerts on devices that user has logged on to
| join AlertInfo on AlertId
| project AlertId, Timestamp, Title, Severity, Category 
```

## <a name="hunting-scenarios"></a>Сценарии выслеживания

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Список действий пользователей, которые получили сообщения электронной почты, которые не были успешно заперт
[Автоматическая очистка нулевого часа (ZAP)](../office-365-security/zero-hour-auto-purge.md) адреса вредоносных сообщений после их отправки. Если zaP сбой, вредоносный код может в конечном итоге запуститься на устройстве и оставить учетные записи скомпрометирован. Этот запрос проверяет действия логотипа, сделанные получателями сообщений электронной почты, которые не были успешно устранены ZAP.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfully
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>Получить попытки логона учетных записей домена, нацеленных на кражу учетных данных
Этот запрос сначала определяет все оповещения о доступе к учетным данным в `AlertInfo` таблице. Затем он сливается или присоединяется к таблице, которая сравнится с именами целевых учетных записей и фильтрами только для учетных записей, присоединив к `AlertEvidence` домену. Наконец, он проверяет таблицу, чтобы получить все действия с логотипом с помощью учетных записей, присоединив `IdentityLogonEvents` к домену.

```kusto
AlertInfo
| where Timestamp > ago(30d)
//Get all credential access alerts
| where Category == "CredentialAccess"
//Get more info from AlertEvidence table to get the SID of the target accounts
| join AlertEvidence on AlertId
| extend IsJoined=(parse_json(AdditionalFields).Account.IsDomainJoined)
| extend TargetAccountSid=tostring(parse_json(AdditionalFields).Account.Sid)
//Filter for domain-joined accounts only
| where IsJoined has "true"
//Merge with IdentityLogonEvents to get all logon attempts by the potentially compromised target accounts
| join kind=inner IdentityLogonEvents on $left.TargetAccountSid == $right.AccountSid
//Show only pertinent info, such as account name, the app or service, protocol, the accessed device, and type of logon
| project AccountDisplayName, TargetAccountSid, Application, Protocol, DeviceName, LogonType
```

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Расскажем о том, как проверить, есть ли на устройствах файлы от известного злоумышленника.
Если вы знаете об электронном адресе, отправляемом вредоносные файлы ( ), вы можете запустить этот запрос, чтобы определить, существуют ли файлы этого отправитель `MaliciousSender@example.com` на ваших устройствах. Этот запрос можно использовать, например, для определения устройств, затронутых кампанией распространения вредоносных программ.

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Проверка попыток входа после получения вредоносных сообщений электронной почты
Благодаря этому запросу обнаруживается 10 последних случаев входа, выполненных получателями сообщений электронной почты, в течение 30 минут после получения ими известных вредоносных сообщений. Этот запрос можно использовать, чтобы проверить, не скомпрометированы ли учетные записи получателей сообщений электронной почты.

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where ThreatTypes has "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmails
| join (
//Merge malicious emails with logon events to find logons by recipients
IdentityLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
//Check only logons within 30 minutes of receipt of an email
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Проверка действий PowerShell после получения сообщений электронной почты от известного злоумышленника
Вредоносные сообщения часто содержат документы и другие специально изготовленные вложения, которые запускают команды PowerShell для создания дополнительных полезных данных. Если вам известно о сообщениях электронной почты, полученных от известного вредоносного отправитель (), этот запрос можно использовать для списка и просмотра действий PowerShell, которые произошли в течение 30 минут после того, как сообщение было получено от `MaliciousSender@example.com` отправитель.  

```kusto
//Define new table for emails from specific sender
let EmailsFromBadSender=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
//Merge emails from sender with process-related events on devices
EmailsFromBadSender
| join (
DeviceProcessEvents
//Look for PowerShell activity
| where FileName =~ "powershell.exe"
//Add line below to check only events initiated by Outlook
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
//Check only PowerShell activities within 30 minutes of receipt of an email
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>Похожие темы
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)