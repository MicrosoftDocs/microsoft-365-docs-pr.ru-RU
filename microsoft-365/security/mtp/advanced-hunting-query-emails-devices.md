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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 97640c318908b87c211caed780624080508a255f
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847348"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="ed153-104">Поиск угроз для различных устройств, сообщений электронной почты, приложений и удостоверений</span><span class="sxs-lookup"><span data-stu-id="ed153-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ed153-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ed153-105">**Applies to:**</span></span>
- <span data-ttu-id="ed153-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed153-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ed153-107">[Расширенный](advanced-hunting-overview.md) Поиск в защитнике Microsoft 365 позволяет профилактическое слежение за угрозами в:</span><span class="sxs-lookup"><span data-stu-id="ed153-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="ed153-108">Устройства, управляемые защитником Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ed153-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="ed153-109">Сообщения электронной почты, обработанные Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed153-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="ed153-110">Действия облачных приложений, события проверки подлинности и действия контроллера домена, отслеживаемые Microsoft Cloud App Security и защитник Майкрософт для удостоверения</span><span class="sxs-lookup"><span data-stu-id="ed153-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="ed153-111">Благодаря такому уровню видимости вы можете быстро находить угрозы, которые просматривают разделы сети, в том числе сложные проникновения, поступающие на электронную почту или Интернет, повышать права на локальные права, получать учетные данные привилегированного домена и перемещать их позже на все устройства.</span><span class="sxs-lookup"><span data-stu-id="ed153-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="ed153-112">Ниже приведены общие методики и примеры запросов, основанные на различных сценариях, которые могут помочь вам понять, как можно создавать запросы при поиске таких сложных угроз.</span><span class="sxs-lookup"><span data-stu-id="ed153-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="ed153-113">Получение сведений об объекте</span><span class="sxs-lookup"><span data-stu-id="ed153-113">Get entity info</span></span>
<span data-ttu-id="ed153-114">Используйте эти запросы, чтобы узнать, как можно быстро получить сведения об учетных записях пользователей, устройствах и файлах.</span><span class="sxs-lookup"><span data-stu-id="ed153-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="ed153-115">Получение учетных записей пользователей из адресов электронной почты</span><span class="sxs-lookup"><span data-stu-id="ed153-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="ed153-116">При формировании запросов по [таблицам, относящимся к устройствам и сообщениям электронной почты](advanced-hunting-schema-tables.md) может возникать необходимость получить названия учетных записей пользователей из электронных адресов отправителя или получателя.</span><span class="sxs-lookup"><span data-stu-id="ed153-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="ed153-117">Как правило, это можно сделать для адреса получателя или отправителя с помощью *локального узла* и адреса электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ed153-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="ed153-118">В приведенном ниже фрагменте мы используем функцию [ToString ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Кусто, чтобы извлечь право локального узла перед `@` адресами электронной почты получателя в столбце `RecipientEmailAddress` .</span><span class="sxs-lookup"><span data-stu-id="ed153-118">In the snippet below, we use the [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="ed153-119">В запросе ниже показано, как можно использовать этот фрагмент:</span><span class="sxs-lookup"><span data-stu-id="ed153-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="ed153-120">Объединение таблицы Идентитинфо</span><span class="sxs-lookup"><span data-stu-id="ed153-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="ed153-121">Вы можете получить имена учетных записей и другие сведения об учетных записях, объединив или присоединяясь к [таблице идентитинфо](advanced-hunting-identityinfo-table.md).</span><span class="sxs-lookup"><span data-stu-id="ed153-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="ed153-122">В запросе ниже показано, как получить список обнаруженных вредоносных программ и вредоносных программ из [таблицы емаилевентс](advanced-hunting-emailevents-table.md) , а затем присоединяет эти сведения к `IdentityInfo` таблице для получения подробных сведений о каждом получателе.</span><span class="sxs-lookup"><span data-stu-id="ed153-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="ed153-123">Получение сведений об устройстве</span><span class="sxs-lookup"><span data-stu-id="ed153-123">Get device information</span></span>
<span data-ttu-id="ed153-124">[Расширенная схема](advanced-hunting-schema-tables.md) подпоиска предоставляет подробные сведения об устройствах в различных таблицах.</span><span class="sxs-lookup"><span data-stu-id="ed153-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="ed153-125">Например, [Таблица девицеинфо](advanced-hunting-deviceinfo-table.md) предоставляет исчерпывающие сведения об устройствах на основе регулярно собранных данных о событиях.</span><span class="sxs-lookup"><span data-stu-id="ed153-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="ed153-126">В этом запросе используется `DeviceInfo` Таблица для проверки того, что потенциально скомпрометированный пользователь ( `<account-name>` ) выполнил вход на любые устройства, а затем выдает список оповещений, активированных на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="ed153-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="ed153-127">Этот запрос использует `kind=inner` для указания [внутреннего объединения](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), которое предотвращает дедупликацию значений левой стороны для `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="ed153-127">This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="ed153-128">Сценарии выслеживания</span><span class="sxs-lookup"><span data-stu-id="ed153-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="ed153-129">Перечисление действий входа пользователей, которые получали сообщения электронной почты, которые не были успешно заппед</span><span class="sxs-lookup"><span data-stu-id="ed153-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="ed153-130">[Автоматическая очистка (ZAP) с нулевым временем](../office-365-security/zero-hour-auto-purge.md) адресов после их получения.</span><span class="sxs-lookup"><span data-stu-id="ed153-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="ed153-131">В противном случае вредоносный код может запуститься на устройстве и оставить учетные записи скомпрометированными.</span><span class="sxs-lookup"><span data-stu-id="ed153-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="ed153-132">Этот запрос проверяет действия входа в систему, выполняемые получателями сообщений электронной почты, которые не были успешно устранены с помощью ZAP.</span><span class="sxs-lookup"><span data-stu-id="ed153-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="ed153-133">Получение попыток входа для учетных записей домена, нацеленных на хищение учетных данных</span><span class="sxs-lookup"><span data-stu-id="ed153-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="ed153-134">Этот запрос сначала определяет все оповещения о доступе к учетным данным в `AlertInfo` таблице.</span><span class="sxs-lookup"><span data-stu-id="ed153-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="ed153-135">Затем он объединяет или присоединяется к `AlertEvidence` таблице, которая анализирует имена целевых учетных записей и фильтров только для учетных записей, присоединенных к домену.</span><span class="sxs-lookup"><span data-stu-id="ed153-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="ed153-136">Наконец, он проверяет `IdentityLogonEvents` таблицу на получение всех действий входа для целевых учетных записей, присоединенных к домену.</span><span class="sxs-lookup"><span data-stu-id="ed153-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="ed153-137">Расскажем о том, как проверить, есть ли на устройствах файлы от известного злоумышленника.</span><span class="sxs-lookup"><span data-stu-id="ed153-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="ed153-138">Если вы знаете адрес электронной почты, который отправляет вредоносные файлы ( `MaliciousSender@example.com` ), вы можете выполнить этот запрос, чтобы определить, существуют ли файлы этого отправителя на ваших устройствах.</span><span class="sxs-lookup"><span data-stu-id="ed153-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="ed153-139">Этот запрос можно использовать, например, для определения устройств, на которые распространяется кампания по распространению вредоносных программ.</span><span class="sxs-lookup"><span data-stu-id="ed153-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="ed153-140">Проверка попыток входа после получения вредоносных сообщений электронной почты</span><span class="sxs-lookup"><span data-stu-id="ed153-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="ed153-141">Благодаря этому запросу обнаруживается 10 последних случаев входа, выполненных получателями сообщений электронной почты, в течение 30 минут после получения ими известных вредоносных сообщений.</span><span class="sxs-lookup"><span data-stu-id="ed153-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="ed153-142">Этот запрос можно использовать, чтобы проверить, не скомпрометированы ли учетные записи получателей сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="ed153-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="ed153-143">Проверка действий PowerShell после получения сообщений электронной почты от известного злоумышленника</span><span class="sxs-lookup"><span data-stu-id="ed153-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="ed153-144">Вредоносные сообщения часто содержат документы и другие специально изготовленные вложения, которые запускают команды PowerShell для создания дополнительных полезных данных.</span><span class="sxs-lookup"><span data-stu-id="ed153-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="ed153-145">Если вы осведомлены о сообщениях, поступающих от известных вредоносных отправителей ( `MaliciousSender@example.com` ), вы можете использовать этот запрос для просмотра и просмотра действий PowerShell, которые произошли в течение 30 минут после получения сообщения от отправителя.</span><span class="sxs-lookup"><span data-stu-id="ed153-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="ed153-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ed153-146">Related topics</span></span>
- [<span data-ttu-id="ed153-147">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="ed153-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ed153-148">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="ed153-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ed153-149">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="ed153-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="ed153-150">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="ed153-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ed153-151">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="ed153-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ed153-152">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="ed153-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
