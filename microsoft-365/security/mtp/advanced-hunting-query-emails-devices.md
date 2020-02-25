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
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 0bbcef72fa305819c9f8e0813cfcdfd6c2b0fff3
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234728"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a><span data-ttu-id="c6ecd-104">Поиск угроз на устройствах и в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="c6ecd-104">Hunt for threats across devices and emails</span></span>

<span data-ttu-id="c6ecd-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c6ecd-105">**Applies to:**</span></span>
- <span data-ttu-id="c6ecd-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c6ecd-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="c6ecd-107">Благодаря[Расширенному выслеживанию](advanced-hunting-overview.md) в службе Защиты от угроз (Майкрософт) можно на профилактической основе выслеживать угрозы на устройствах c Windows и в сообщениях электронной почты Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6ecd-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across your Windows devices and Office 365 emails.</span></span> <span data-ttu-id="c6ecd-108">Ниже приводится несколько сценариев выслеживания и примеров запросов, позволяющих понять, как создавать запросы, которые будут относиться и к устройствам, и к сообщениям электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c6ecd-108">Here are some hunting scenarios and sample queries that can help you explore how you might construct queries covering both devices and emails.</span></span>

## <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="c6ecd-109">Получение учетных записей пользователей из адресов электронной почты</span><span class="sxs-lookup"><span data-stu-id="c6ecd-109">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="c6ecd-110">При формировании запросов по [таблицам, относящимся к устройствам и сообщениям электронной почты](advanced-hunting-schema-tables.md) может возникать необходимость получить названия учетных записей пользователей из электронных адресов отправителя или получателя.</span><span class="sxs-lookup"><span data-stu-id="c6ecd-110">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="c6ecd-111">Для этого используется *локальный узел* из адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c6ecd-111">To do this use the *local-host* from the email address:</span></span>

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

<span data-ttu-id="c6ecd-112">Этот метод нормализации применяется в последующих сценариях.</span><span class="sxs-lookup"><span data-stu-id="c6ecd-112">This normalization technique is used in the succeeding scenarios.</span></span>

## <a name="hunting-scenarios"></a><span data-ttu-id="c6ecd-113">Сценарии выслеживания</span><span class="sxs-lookup"><span data-stu-id="c6ecd-113">Hunting scenarios</span></span>

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="c6ecd-114">Расскажем о том, как проверить, есть ли на устройствах файлы от известного злоумышленника.</span><span class="sxs-lookup"><span data-stu-id="c6ecd-114">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="c6ecd-115">Если известен адрес электронной почты, с которого рассылаются вредоносные файлы, этот запрос можно выполнить, чтобы определить, есть ли на устройствах файлы от этого отправителя.</span><span class="sxs-lookup"><span data-stu-id="c6ecd-115">Assuming you know of an email address sending malicious files, you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="c6ecd-116">Например, с помощью этого запроса можно определить количество устройств, которые подверглись рассылке вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="c6ecd-116">You can use this query, for example, to determine the number of devices affected by a malware distribution campaign.</span></span>

```kusto
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="c6ecd-117">Проверка попыток входа после получения вредоносных сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="c6ecd-117">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="c6ecd-118">Благодаря этому запросу обнаруживается 10 последних случаев входа, выполненных получателями сообщений электронной почты, в течение 30 минут после получения ими известных вредоносных сообщений.</span><span class="sxs-lookup"><span data-stu-id="c6ecd-118">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="c6ecd-119">Этот запрос можно использовать, чтобы проверить, не скомпрометированы ли учетные записи получателей сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c6ecd-119">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```kusto
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
DeviceLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="c6ecd-120">Проверка действий PowerShell после получения сообщений электронной почты от известного злоумышленника</span><span class="sxs-lookup"><span data-stu-id="c6ecd-120">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="c6ecd-121">Вредоносные сообщения часто содержат документы и другие специально изготовленные вложения, которые запускают команды PowerShell для создания дополнительных полезных данных.</span><span class="sxs-lookup"><span data-stu-id="c6ecd-121">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="c6ecd-122">Если стало известно, что приходят сообщения от известного злоумышленника, этот запрос можно использовать для создания списка действий и проверки действий PowerShell, которые произошли в течение 30 минут после получения сообщения от этого отправителя.</span><span class="sxs-lookup"><span data-stu-id="c6ecd-122">If you are aware of emails coming from a known malicious sender, you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender .</span></span>  

```kusto
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
DeviceProcessEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a><span data-ttu-id="c6ecd-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c6ecd-123">Related topics</span></span>
- [<span data-ttu-id="c6ecd-124">Профилактическое выслеживание угроз</span><span class="sxs-lookup"><span data-stu-id="c6ecd-124">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c6ecd-125">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="c6ecd-125">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c6ecd-126">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="c6ecd-126">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c6ecd-127">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="c6ecd-127">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c6ecd-128">Применение рекомендаций по использованию запросов</span><span class="sxs-lookup"><span data-stu-id="c6ecd-128">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
