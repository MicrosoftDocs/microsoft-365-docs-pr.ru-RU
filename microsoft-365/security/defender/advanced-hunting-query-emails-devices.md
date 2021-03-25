---
title: Охота на угрозы на устройствах, электронных письмах, приложениях и удостоверениях с расширенным поиском
description: Изучите распространенные сценарии охоты и примеры запросов, которые охватывают устройства, электронные почты, приложения и удостоверения.
keywords: расширенный поиск, данные Office365, устройства Windows, электронные почты Office365 нормализуются, электронные почты, приложения, удостоверения, охота на угрозы, поиск, запрос, телеметрия, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e494bfe57c31c1d5044f72a8adb3e2548d531604
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199153"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="f5cd2-104">Охота за угрозами на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="f5cd2-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f5cd2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f5cd2-105">**Applies to:**</span></span>
- <span data-ttu-id="f5cd2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5cd2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f5cd2-107">[Расширенный поиск](advanced-hunting-overview.md) в Microsoft 365 Defender позволяет активно искать угрозы по всему:</span><span class="sxs-lookup"><span data-stu-id="f5cd2-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="f5cd2-108">Устройства, управляемые Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f5cd2-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="f5cd2-109">Сообщения электронной почты, обработанные Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f5cd2-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="f5cd2-110">Действия облачного приложения, события проверки подлинности и действия контроллера домена, отслеживаются службами безопасности облачных приложений Microsoft и Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="f5cd2-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="f5cd2-111">С помощью этого уровня видимости можно быстро искать угрозы, которые пересекают разделы вашей сети, включая сложные вторжения, которые поступают по электронной почте или в Интернете, повысить местные привилегии, получить привилегированные учетные данные домена и перейти на другие устройства.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="f5cd2-112">Вот общие методы и примеры запросов, основанных на различных сценариях охоты, которые помогут вам изучить, как можно создавать запросы при поиске таких сложных угроз.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="f5cd2-113">Получить сведения об объектах</span><span class="sxs-lookup"><span data-stu-id="f5cd2-113">Get entity info</span></span>
<span data-ttu-id="f5cd2-114">Используйте эти запросы, чтобы узнать, как быстро получить сведения о учетных записях пользователей, устройствах и файлах.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="f5cd2-115">Получение учетных записей пользователей из адресов электронной почты</span><span class="sxs-lookup"><span data-stu-id="f5cd2-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="f5cd2-116">При формировании запросов по [таблицам, относящимся к устройствам и сообщениям электронной почты](advanced-hunting-schema-tables.md) может возникать необходимость получить названия учетных записей пользователей из электронных адресов отправителя или получателя.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="f5cd2-117">Обычно это можно сделать для адреса получателя или отправщика с помощью *локального* хоста с адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="f5cd2-118">В приведенной ниже фрагменте мы используем функцию [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto для извлечения локального хоста прямо перед адресами электронной почты получателей в `@` столбце `RecipientEmailAddress` .</span><span class="sxs-lookup"><span data-stu-id="f5cd2-118">In the snippet below, we use the [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="f5cd2-119">В ниже приведеном ниже запросе показано, как можно использовать этот фрагмент:</span><span class="sxs-lookup"><span data-stu-id="f5cd2-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="f5cd2-120">Объединение таблицы IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="f5cd2-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="f5cd2-121">Вы можете получить имена учетных записей и другие сведения об учетной записи путем слияния или присоединения к [таблице IdentityInfo.](advanced-hunting-identityinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="f5cd2-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="f5cd2-122">В приведенной ниже области запрос получает список обнаружения фишинга и вредоносных программ из таблицы [EmailEvents,](advanced-hunting-emailevents-table.md) а затем присоединяется к этой информации со таблицей, чтобы получить подробные сведения о каждом `IdentityInfo` получателе.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="f5cd2-123">Получить сведения об устройстве</span><span class="sxs-lookup"><span data-stu-id="f5cd2-123">Get device information</span></span>
<span data-ttu-id="f5cd2-124">[Передовая схема охоты содержит](advanced-hunting-schema-tables.md) обширные сведения о устройстве в различных таблицах.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="f5cd2-125">Например, [таблица DeviceInfo предоставляет](advanced-hunting-deviceinfo-table.md) всестороннюю информацию об устройстве на основе регулярно агрегированных данных событий.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="f5cd2-126">В этом запросе используется таблица, чтобы проверить, вошел ли потенциально скомпрометированный пользователь на любые устройства, а затем перечислить оповещения, срабатывав на `DeviceInfo` `<account-name>` этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="f5cd2-127">Этот запрос использует для указания внутреннего присоединяния, которое предотвращает `kind=inner` [](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)декупликацию значений левой стороны `DeviceId` для .</span><span class="sxs-lookup"><span data-stu-id="f5cd2-127">This query uses `kind=inner` to specify an [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="f5cd2-128">Сценарии выслеживания</span><span class="sxs-lookup"><span data-stu-id="f5cd2-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="f5cd2-129">Список действий пользователей, которые получили сообщения электронной почты, которые не были успешно заперт</span><span class="sxs-lookup"><span data-stu-id="f5cd2-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="f5cd2-130">[Автоматическая очистка нулевого часа (ZAP)](../office-365-security/zero-hour-auto-purge.md) адреса вредоносных сообщений после их отправки.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="f5cd2-131">Если zaP сбой, вредоносный код может в конечном итоге запуститься на устройстве и оставить учетные записи скомпрометирован.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="f5cd2-132">Этот запрос проверяет действия логотипа, сделанные получателями сообщений электронной почты, которые не были успешно устранены ZAP.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="f5cd2-133">Получить попытки логона учетных записей домена, нацеленных на кражу учетных данных</span><span class="sxs-lookup"><span data-stu-id="f5cd2-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="f5cd2-134">Этот запрос сначала определяет все оповещения о доступе к учетным данным в `AlertInfo` таблице.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="f5cd2-135">Затем он сливается или присоединяется к таблице, которая сравнится с именами целевых учетных записей и фильтрами только для учетных записей, присоединив к `AlertEvidence` домену.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="f5cd2-136">Наконец, он проверяет таблицу, чтобы получить все действия с логотипом с помощью учетных записей, присоединив `IdentityLogonEvents` к домену.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="f5cd2-137">Расскажем о том, как проверить, есть ли на устройствах файлы от известного злоумышленника.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="f5cd2-138">Если вы знаете об электронном адресе, отправляемом вредоносные файлы ( ), вы можете запустить этот запрос, чтобы определить, существуют ли файлы этого отправитель `MaliciousSender@example.com` на ваших устройствах.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="f5cd2-139">Этот запрос можно использовать, например, для определения устройств, затронутых кампанией распространения вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="f5cd2-140">Проверка попыток входа после получения вредоносных сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="f5cd2-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="f5cd2-141">Благодаря этому запросу обнаруживается 10 последних случаев входа, выполненных получателями сообщений электронной почты, в течение 30 минут после получения ими известных вредоносных сообщений.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="f5cd2-142">Этот запрос можно использовать, чтобы проверить, не скомпрометированы ли учетные записи получателей сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="f5cd2-143">Проверка действий PowerShell после получения сообщений электронной почты от известного злоумышленника</span><span class="sxs-lookup"><span data-stu-id="f5cd2-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="f5cd2-144">Вредоносные сообщения часто содержат документы и другие специально изготовленные вложения, которые запускают команды PowerShell для создания дополнительных полезных данных.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="f5cd2-145">Если вам известно о сообщениях электронной почты, полученных от известного вредоносного отправитель (), этот запрос можно использовать для списка и просмотра действий PowerShell, которые произошли в течение 30 минут после того, как сообщение было получено от `MaliciousSender@example.com` отправитель.</span><span class="sxs-lookup"><span data-stu-id="f5cd2-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="f5cd2-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f5cd2-146">Related topics</span></span>
- [<span data-ttu-id="f5cd2-147">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="f5cd2-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f5cd2-148">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="f5cd2-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f5cd2-149">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="f5cd2-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="f5cd2-150">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="f5cd2-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f5cd2-151">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="f5cd2-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f5cd2-152">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="f5cd2-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)