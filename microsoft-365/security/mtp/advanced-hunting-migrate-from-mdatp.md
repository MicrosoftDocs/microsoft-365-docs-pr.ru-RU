---
title: Перенос расширенных запросов на охоту из Microsoft Defender для конечной точки
description: Узнайте, как настроить запросы Microsoft Defender для конечных точек, чтобы использовать их в Microsoft 365 Defender
keywords: передовая охота, охота на угрозы, охота на киберугрозы, защита от угроз Майкрософт, Microsoft 365, mtp, m365, microsoft defender atp, mdatp, search, query, telemetry, custom detections, schema, kusto, microsoft 365, mapping
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4d29f4f3df3d65ad72a19f059763523d7f7cba31
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597002"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="1bfd4-104">Перенос расширенных запросов на охоту из Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1bfd4-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1bfd4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1bfd4-105">**Applies to:**</span></span>
- <span data-ttu-id="1bfd4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1bfd4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1bfd4-107">Переместите расширенные процессы охоты из Microsoft Defender для конечной точки, чтобы активно искать угрозы с помощью более широкого набора данных.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="1bfd4-108">В Microsoft 365 Defender вы получаете доступ к данным из других решений безопасности Microsoft 365, включая:</span><span class="sxs-lookup"><span data-stu-id="1bfd4-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="1bfd4-109">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1bfd4-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="1bfd4-110">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="1bfd4-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="1bfd4-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1bfd4-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="1bfd4-112">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="1bfd4-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="1bfd4-113">Большинство клиентов Microsoft Defender для конечных точек могут [использовать Microsoft 365 Defender без дополнительных лицензий.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="1bfd4-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="1bfd4-114">Чтобы приступить к переходу передовых процессов охоты из Defender для конечной точки, включите [Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="1bfd4-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="1bfd4-115">Вы можете перейти, не затрагивая существующие рабочий процессы Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="1bfd4-116">Сохраненные запросы остаются нетронутыми, а пользовательские правила обнаружения продолжают запускать и создавать оповещения.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="1bfd4-117">Однако они будут видны в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="1bfd4-118">Таблицы схемы только в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1bfd4-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="1bfd4-119">Продвинутая схема охоты [Microsoft 365 Defender](advanced-hunting-schema-tables.md) содержит дополнительные таблицы, содержащие данные из различных решений безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="1bfd4-120">Следующие таблицы доступны только в Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="1bfd4-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="1bfd4-121">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="1bfd4-121">Table name</span></span> | <span data-ttu-id="1bfd4-122">Описание</span><span class="sxs-lookup"><span data-stu-id="1bfd4-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="1bfd4-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="1bfd4-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="1bfd4-124">Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями</span><span class="sxs-lookup"><span data-stu-id="1bfd4-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="1bfd4-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="1bfd4-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="1bfd4-126">Оповещения от Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender for Identity, включая сведения о серьезности и категориях угроз</span><span class="sxs-lookup"><span data-stu-id="1bfd4-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="1bfd4-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="1bfd4-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="1bfd4-128">Действия, связанные с файлами в облачных приложениях и службах</span><span class="sxs-lookup"><span data-stu-id="1bfd4-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="1bfd4-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="1bfd4-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="1bfd4-130">Сведения о файлах, присоединенных к электронным письмам</span><span class="sxs-lookup"><span data-stu-id="1bfd4-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="1bfd4-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="1bfd4-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="1bfd4-132">События электронной почты Microsoft 365, включая доставку электронной почты и блокировку событий</span><span class="sxs-lookup"><span data-stu-id="1bfd4-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="1bfd4-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="1bfd4-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="1bfd4-134">События безопасности, которые происходят после доставки, после того, как Microsoft 365 доставила сообщения электронной почты в почтовый ящик получателя</span><span class="sxs-lookup"><span data-stu-id="1bfd4-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="1bfd4-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="1bfd4-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="1bfd4-136">Сведения об URL-адресах в электронных письмах</span><span class="sxs-lookup"><span data-stu-id="1bfd4-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="1bfd4-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="1bfd4-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="1bfd4-138">События с участием локального контроллера домена под управлением Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="1bfd4-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="1bfd4-139">В этой таблице описывается ряд событий, связанных с удостоверением, и системных событий на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="1bfd4-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="1bfd4-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="1bfd4-141">Сведения об учетных записях из различных источников, включая Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1bfd4-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="1bfd4-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="1bfd4-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="1bfd4-143">События проверки подлинности в службах Active Directory и Microsoft online</span><span class="sxs-lookup"><span data-stu-id="1bfd4-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="1bfd4-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="1bfd4-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="1bfd4-145">Запросы для объектов Active Directory, таких как пользователи, группы, устройства и домены</span><span class="sxs-lookup"><span data-stu-id="1bfd4-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="1bfd4-146">Запросы и настраиваемые обнаружения, которые используют таблицы схем, доступные только в Microsoft 365 Defender, можно просматривать только в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-146">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="1bfd4-147">Таблица Map DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="1bfd4-147">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="1bfd4-148">Таблицы `AlertInfo` `AlertEvidence` и таблицы `DeviceAlertEvents` заменяют таблицу в схеме Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-148">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="1bfd4-149">Помимо данных о оповещениях о устройствах, эти две таблицы включают данные о оповещениях для удостоверений, приложений и электронных писем.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-149">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="1bfd4-150">Используйте следующую таблицу, чтобы проверить, как столбцы сое всего мира сое and `DeviceAlertEvents` `AlertInfo` `AlertEvidence` tables.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-150">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="1bfd4-151">Помимо столбцов в следующей таблице в таблице содержится множество других столбцов, которые предоставляют более целостную картину оповещений из `AlertEvidence` различных источников.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-151">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="1bfd4-152">См. все столбцы AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="1bfd4-152">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="1bfd4-153">Колонка DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="1bfd4-153">DeviceAlertEvents column</span></span> | <span data-ttu-id="1bfd4-154">Где найти те же данные в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1bfd4-154">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="1bfd4-155">`AlertInfo` и  `AlertEvidence` таблицы</span><span class="sxs-lookup"><span data-stu-id="1bfd4-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="1bfd4-156">`AlertInfo` и  `AlertEvidence` таблицы</span><span class="sxs-lookup"><span data-stu-id="1bfd4-156">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="1bfd4-157">`AlertEvidence` таблица</span><span class="sxs-lookup"><span data-stu-id="1bfd4-157">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="1bfd4-158">`AlertEvidence` таблица</span><span class="sxs-lookup"><span data-stu-id="1bfd4-158">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="1bfd4-159">`AlertInfo` таблица</span><span class="sxs-lookup"><span data-stu-id="1bfd4-159">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="1bfd4-160">`AlertInfo` таблица</span><span class="sxs-lookup"><span data-stu-id="1bfd4-160">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="1bfd4-161">`AlertInfo` таблица</span><span class="sxs-lookup"><span data-stu-id="1bfd4-161">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="1bfd4-162">`AlertEvidence` таблица</span><span class="sxs-lookup"><span data-stu-id="1bfd4-162">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="1bfd4-163">`AlertEvidence` таблица</span><span class="sxs-lookup"><span data-stu-id="1bfd4-163">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="1bfd4-164">`AlertEvidence` таблица</span><span class="sxs-lookup"><span data-stu-id="1bfd4-164">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="1bfd4-165">`AlertEvidence` таблица</span><span class="sxs-lookup"><span data-stu-id="1bfd4-165">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="1bfd4-166">`AlertInfo` таблица</span><span class="sxs-lookup"><span data-stu-id="1bfd4-166">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="1bfd4-167">Этот столбец обычно используется в Microsoft Defender для конечной точки для поиска связанных записей в других таблицах.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-167">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="1bfd4-168">В Microsoft 365 Defender можно получить связанные данные непосредственно из `AlertEvidence` таблицы.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="1bfd4-169">Этот столбец обычно используется в Microsoft Defender для конечной точки для получения дополнительных сведений о событиях в других таблицах.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-169">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="1bfd4-170">В Microsoft 365 Defender можно получить связанные данные непосредственно из `AlertEvidence` таблицы.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-170">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="1bfd4-171">Настройка существующих запросов Microsoft Defender для запросов конечной точки</span><span class="sxs-lookup"><span data-stu-id="1bfd4-171">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="1bfd4-172">Запросы Microsoft Defender для конечных точек будут работать как есть, если они не ссылатся на `DeviceAlertEvents` таблицу.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-172">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="1bfd4-173">Чтобы использовать эти запросы в Microsoft 365 Defender, внесите эти изменения:</span><span class="sxs-lookup"><span data-stu-id="1bfd4-173">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="1bfd4-174">Замените `DeviceAlertEvents` `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="1bfd4-174">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="1bfd4-175">Присоединяйтесь `AlertInfo` к `AlertEvidence` таблицам и таблицам, чтобы получить `AlertId` эквивалентные данные.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-175">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="1bfd4-176">Исходный запрос</span><span class="sxs-lookup"><span data-stu-id="1bfd4-176">Original query</span></span>
<span data-ttu-id="1bfd4-177">Следующий запрос используется `DeviceAlertEvents` в Microsoft Defender для конечной точки для получения оповещений, которые включают _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="1bfd4-177">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="1bfd4-178">Измененный запрос</span><span class="sxs-lookup"><span data-stu-id="1bfd4-178">Modified query</span></span>
<span data-ttu-id="1bfd4-179">Следующий запрос был скорректирован для использования в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-179">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="1bfd4-180">Вместо того, чтобы проверять имя файла непосредственно из, он присоединяется и проверяет имя `DeviceAlertEvents` `AlertEvidence` файла в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-180">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="1bfd4-181">Перенос пользовательских правил обнаружения</span><span class="sxs-lookup"><span data-stu-id="1bfd4-181">Migrate custom detection rules</span></span>

<span data-ttu-id="1bfd4-182">Когда правила Microsoft Defender для конечной точки редактированы в Microsoft 365 Defender, они продолжают функционировать так же, как и раньше, если в результате запрос смотрит только на таблицы устройств.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-182">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="1bfd4-183">Например, оповещения, созданные пользовательскими правилами обнаружения, которые по-прежнему будут доставляться в SIEM только таблицы устройств и создавать уведомления электронной почты, в зависимости от того, как вы настроили их в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-183">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="1bfd4-184">Любые существующие правила подавления в Защитнике для конечной точки также будут продолжать применяться.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-184">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="1bfd4-185">После изменения правила Defender для конечной точки, чтобы он запрашивал удостоверения и таблицы электронной почты, доступные только в Microsoft 365 Defender, правило автоматически перемещается в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-185">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="1bfd4-186">Оповещения, созданные правилом переноса:</span><span class="sxs-lookup"><span data-stu-id="1bfd4-186">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="1bfd4-187">Больше не отображается на портале Защитник для конечной точки (Центр безопасности Защитника Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="1bfd4-187">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="1bfd4-188">Прекратите доставку в SIEM или создание уведомлений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-188">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="1bfd4-189">Чтобы обойти это изменение, настройте уведомления через Microsoft 365 Defender для получения оповещений.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-189">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="1bfd4-190">API [защитника Microsoft 365](api-incident.md) можно использовать для получения уведомлений о оповещениях об обнаружении клиентов или связанных с ними инцидентах.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-190">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="1bfd4-191">Правила подавления конечных точек microsoft Defender не будут подавлены.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-191">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="1bfd4-192">Чтобы предотвратить сгенерированию оповещений для определенных пользователей, устройств или почтовых ящиков, измените соответствующие запросы, чтобы исключить эти объекты явно.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-192">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="1bfd4-193">Если изменить правило таким образом, вам будет предложено подтверждение до того, как будут применены такие изменения.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-193">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="1bfd4-194">Новые оповещения, созданные с помощью настраиваемых правил обнаружения на портале Microsoft 365 Defender, отображаются на странице оповещений, которая содержит следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="1bfd4-194">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="1bfd4-195">Название и описание оповещений</span><span class="sxs-lookup"><span data-stu-id="1bfd4-195">Alert title and description</span></span> 
- <span data-ttu-id="1bfd4-196">Влияние активов</span><span class="sxs-lookup"><span data-stu-id="1bfd4-196">Impacted assets</span></span>
- <span data-ttu-id="1bfd4-197">Действия, принятые в ответ на предупреждение</span><span class="sxs-lookup"><span data-stu-id="1bfd4-197">Actions taken in response to the alert</span></span>
- <span data-ttu-id="1bfd4-198">Результаты запроса, которые вызвали оповещение</span><span class="sxs-lookup"><span data-stu-id="1bfd4-198">Query results that triggered the alert</span></span> 
- <span data-ttu-id="1bfd4-199">Сведения о пользовательском правиле обнаружения</span><span class="sxs-lookup"><span data-stu-id="1bfd4-199">Information on the custom detection rule</span></span> 
 
![Изображение новой страницы оповещений](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="1bfd4-201">Записывай запросы без DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="1bfd4-201">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="1bfd4-202">В схеме защитника Microsoft 365 предоставляются таблицы и таблицы для размещения разнообразного набора сведений, сопровождающих оповещения `AlertInfo` `AlertEvidence` из различных источников.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-202">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="1bfd4-203">Чтобы получить те же сведения оповещений, которые вы использовали для получения из таблицы в схеме Microsoft Defender для конечной точки, фильтруем таблицу, а затем присоединяем каждый уникальный ID со таблицей, которая предоставляет подробные сведения о событиях и `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` сущности.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-203">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="1bfd4-204">Пример запроса см. ниже:</span><span class="sxs-lookup"><span data-stu-id="1bfd4-204">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="1bfd4-205">Этот запрос дает гораздо больше столбцов, чем `DeviceAlertEvents` в схеме Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-205">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="1bfd4-206">Чтобы сохранить управляемые результаты, используйте для получения только `project` интересуемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-206">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="1bfd4-207">В примере ниже проектов столбцов, которые могут быть интересны при обнаружении в ходе расследования активности PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1bfd4-207">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="1bfd4-208">Если вы хотите фильтровать для определенных сущностей, участвующих в оповещениях, вы можете это сделать, указав тип объекта и значение, которое вы хотите `EntityType` фильтровать.</span><span class="sxs-lookup"><span data-stu-id="1bfd4-208">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="1bfd4-209">В следующем примере ниже приводится пример определенного IP-адреса:</span><span class="sxs-lookup"><span data-stu-id="1bfd4-209">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="1bfd4-210">См. также</span><span class="sxs-lookup"><span data-stu-id="1bfd4-210">See also</span></span>
- [<span data-ttu-id="1bfd4-211">Включив защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1bfd4-211">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1bfd4-212">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="1bfd4-212">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1bfd4-213">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="1bfd4-213">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1bfd4-214">Расширенный поиск в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1bfd4-214">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)