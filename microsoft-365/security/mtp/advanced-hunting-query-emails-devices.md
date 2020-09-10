---
title: Поиск угроз для различных устройств, сообщений электронной почты, приложений и удостоверений с помощью расширенного поиска
description: Исследование распространенных сценариев и примеров запросов, посвященных устройствам, сообщениям электронной почты, приложениям и удостоверениям.
keywords: Расширенный поиск, Office365 данные, устройства Windows, Office365ные сообщения, нормализация, электронная почта, приложения, удостоверения, Поиск угроз, Поиск угроз кибератак, поиск, запрос, телеметрии, Microsoft 365, защита от угроз Майкрософт
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: c24f5891573b8541a97a35d228c57642766fe4a0
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419148"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Поиск угроз для различных устройств, сообщений электронной почты, приложений и удостоверений

**Область применения:**
- Защита от угроз (Майкрософт)

[Расширенные](advanced-hunting-overview.md) функции поиска в защите от угроз Майкрософт позволяют выполнять профилактическое слежение за угрозами:
- Устройства, управляемые пакетом анализа "защитник Майкрософт"
- Сообщения электронной почты, обработанные Microsoft 365
- Действия облачных приложений, события проверки подлинности и действия с контроллерами домена, отслеживаемые Microsoft Cloud App Security и Azure ATP

Благодаря такому уровню видимости вы можете быстро находить угрозы, которые просматривают разделы сети, в том числе сложные проникновения, поступающие на электронную почту или Интернет, повышать права на локальные права, получать учетные данные привилегированного домена и перемещать их позже на все устройства. 

Ниже приведены общие методики и примеры запросов, основанные на различных сценариях, которые могут помочь вам понять, как можно создавать запросы при поиске таких сложных угроз.

## <a name="get-entity-info"></a>Получение сведений об объекте
Используйте эти запросы, чтобы узнать, как можно быстро получить сведения об учетных записях пользователей, устройствах и файлах. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Получение учетных записей пользователей из адресов электронной почты
При формировании запросов по [таблицам, относящимся к устройствам и сообщениям электронной почты](advanced-hunting-schema-tables.md) может возникать необходимость получить названия учетных записей пользователей из электронных адресов отправителя или получателя. Как правило, это можно сделать для адреса получателя или отправителя с помощью *локального узла* и адреса электронной почты.

В приведенном ниже фрагменте мы используем функцию [ToString ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Кусто, чтобы извлечь право локального узла перед `@` адресами электронной почты получателя в столбце `RecipientEmailAddress` .

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
В запросе ниже показано, как можно использовать этот фрагмент:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>Объединение таблицы Идентитинфо

Вы можете получить имена учетных записей и другие сведения об учетных записях, объединив или присоединяясь к [таблице идентитинфо](advanced-hunting-identityinfo-table.md). В запросе ниже показано, как получить список обнаруженных вредоносных программ и вредоносных программ из [таблицы емаилевентс](advanced-hunting-emailevents-table.md) , а затем присоединяет эти сведения к `IdentityInfo` таблице для получения подробных сведений о каждом получателе. 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where MalwareFilterVerdict == 'Malware' or PhishFilterVerdict == 'Phish'
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, PhishFilterVerdict, MalwareFilterVerdict,
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>Получение сведений об устройстве
[Расширенная схема](advanced-hunting-schema-tables.md) подпоиска предоставляет подробные сведения об устройствах в различных таблицах. Например, [Таблица девицеинфо](advanced-hunting-deviceinfo-table.md) предоставляет исчерпывающие сведения об устройствах на основе регулярно собранных данных о событиях. В этом запросе используется `DeviceInfo` Таблица для проверки того, что потенциально скомпрометированный пользователь ( `<account-name>` ) выполнил вход на любые устройства, а затем выдает список оповещений, активированных на этих устройствах.

>[!Tip]
> Этот запрос использует `kind=inner` для указания [внутреннего объединения](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), которое предотвращает дедупликацию значений левой стороны для `DeviceId` .

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

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Перечисление действий входа пользователей, которые получали сообщения электронной почты, которые не были успешно заппед
[Автоматическая очистка (ZAP) с нулевым временем](../office-365-security/zero-hour-auto-purge.md) адресов после их получения. В противном случае вредоносный код может запуститься на устройстве и оставить учетные записи скомпрометированными. Этот запрос проверяет действия входа в систему, выполняемые получателями сообщений электронной почты, которые не были успешно устранены с помощью ZAP.

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>Получение попыток входа для учетных записей домена, нацеленных на хищение учетных данных
Этот запрос сначала определяет все оповещения о доступе к учетным данным в `AlertInfo` таблице. Затем он объединяет или присоединяется к `AlertEvidence` таблице, которая анализирует имена целевых учетных записей и фильтров только для учетных записей, присоединенных к домену. Наконец, он проверяет `IdentityLogonEvents` таблицу на получение всех действий входа для целевых учетных записей, присоединенных к домену.

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
Если вы знаете адрес электронной почты, который отправляет вредоносные файлы ( `MaliciousSender@example.com` ), вы можете выполнить этот запрос, чтобы определить, существуют ли файлы этого отправителя на ваших устройствах. Этот запрос можно использовать, например, для определения устройств, на которые распространяется кампания по распространению вредоносных программ.

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
| where MalwareFilterVerdict == "Malware"
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
Вредоносные сообщения часто содержат документы и другие специально изготовленные вложения, которые запускают команды PowerShell для создания дополнительных полезных данных. Если вы осведомлены о сообщениях, поступающих от известных вредоносных отправителей ( `MaliciousSender@example.com` ), вы можете использовать этот запрос для просмотра и просмотра действий PowerShell, которые произошли в течение 30 минут после получения сообщения от отправителя.  

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
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)