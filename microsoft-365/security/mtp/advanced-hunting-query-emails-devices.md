---
title: Обнаружение угроз на устройствах и сообщениях электронной почты с помощью расширенного выслеживания
description: В этой статье приводятся примеры распространенных сценариев выслеживания и примеры запросов, применяемых для устройств и сообщений электронной почты.
keywords: расширенное выслеживание, данные Office365, устройства с Windows, нормализация сообщений электронной почты Office365, сообщения электронной почты, выслеживание угроз, выслеживание киберугроз, поиск, запрос, телеметрия, Microsoft 365, Защита от угроз (Майкрософт)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b374aac84b309d18a88ee7248021b50a893e120c
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911519"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a>Поиск угроз на устройствах и в сообщениях электронной почты

**Область применения:**
- Защита от угроз (Майкрософт)

[!include[Prerelease information](prerelease.md)]

Благодаря[Расширенному выслеживанию](advanced-hunting-overview.md) в службе Защиты от угроз (Майкрософт) можно на профилактической основе выслеживать угрозы на устройствах c Windows и в сообщениях электронной почты Office 365. Ниже приводится несколько сценариев выслеживания и примеров запросов, позволяющих понять, как создавать запросы, которые будут относиться и к устройствам, и к сообщениям электронной почты.

## <a name="obtain-user-accounts-from-email-addresses"></a>Получение учетных записей пользователей из адресов электронной почты
При формировании запросов по [таблицам, относящимся к устройствам и сообщениям электронной почты](advanced-hunting-schema-tables.md) может возникать необходимость получить названия учетных записей пользователей из электронных адресов отправителя или получателя. Для этого используется *локальный узел* из адреса электронной почты.

```
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

Этот метод нормализации применяется в последующих сценариях.

## <a name="hunting-scenarios"></a>Сценарии выслеживания

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Расскажем о том, как проверить, есть ли на устройствах файлы от известного злоумышленника.
Если известен адрес электронной почты, с которого рассылаются вредоносные файлы, этот запрос можно выполнить, чтобы определить, есть ли на устройствах файлы от этого отправителя. Например, с помощью этого запроса можно определить количество устройств, которые подверглись рассылке вредоносных программ.

```
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
FileCreationEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Проверка попыток входа после получения вредоносных сообщений электронной почты
Благодаря этому запросу обнаруживается 10 последних случаев входа, выполненных получателями сообщений электронной почты, в течение 30 минут после получения ими известных вредоносных сообщений. Этот запрос можно использовать, чтобы проверить, не скомпрометированы ли учетные записи получателей сообщений электронной почты.

```
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = EventTime, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
LogonEvents
| project LogonTime = EventTime, AccountName, ComputerName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Проверка действий PowerShell после получения сообщений электронной почты от известного злоумышленника
Вредоносные сообщения часто содержат документы и другие специально изготовленные вложения, которые запускают команды PowerShell для создания дополнительных полезных данных. Если стало известно, что приходят сообщения от известного злоумышленника, этот запрос можно использовать для создания списка действий и проверки действий PowerShell, которые произошли в течение 30 минут после получения сообщения от этого отправителя.  

```
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = EventTime, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
ProcessCreationEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = EventTime, AccountName, ComputerName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>См. также
- [Профилактическое выслеживание угроз](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)