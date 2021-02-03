---
title: Перенос запросов на расширенный поиск из Microsoft Defender для конечной точки
description: Узнайте, как настроить Microsoft Defender для запросов конечных точек, чтобы использовать их в Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, microsoft defender atp, mdatp, search, query, telemetry, custom detections, schema, kusto, microsoft 365, mapping
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
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080748"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="9a8d9-104">Перенос запросов на расширенный поиск из Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9a8d9-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9a8d9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="9a8d9-105">**Applies to:**</span></span>
- <span data-ttu-id="9a8d9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a8d9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9a8d9-107">Переместите расширенные процессы охоты из Microsoft Defender для конечной точки, чтобы заблаговременно искать угрозы с использованием более широкого набора данных.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="9a8d9-108">В Microsoft 365 Defender вы получаете доступ к данным из других решений для обеспечения безопасности Microsoft 365, в том числе:</span><span class="sxs-lookup"><span data-stu-id="9a8d9-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="9a8d9-109">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9a8d9-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="9a8d9-110">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="9a8d9-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="9a8d9-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9a8d9-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="9a8d9-112">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="9a8d9-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="9a8d9-113">Большинство пользователей Endpoint в Microsoft Defender могут использовать [Microsoft 365 Defender без дополнительных лицензий.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="9a8d9-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="9a8d9-114">Чтобы начать переключение расширенных процессов охоты из Защитника для конечной точки, включите [Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="9a8d9-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="9a8d9-115">Переход можно без влияния на существующие процессы Защитника для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="9a8d9-116">Сохраненные запросы остаются без изменений, а пользовательские правила обнаружения продолжают запускаться и создавать оповещения.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="9a8d9-117">Однако они будут видны в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="9a8d9-118">Таблицы схемы только в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a8d9-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="9a8d9-119">Схема advanced hunting в [Microsoft 365 Defender](advanced-hunting-schema-tables.md) предоставляет дополнительные таблицы, содержащие данные из различных решений для обеспечения безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="9a8d9-120">Следующие таблицы доступны только в Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="9a8d9-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="9a8d9-121">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="9a8d9-121">Table name</span></span> | <span data-ttu-id="9a8d9-122">Описание</span><span class="sxs-lookup"><span data-stu-id="9a8d9-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="9a8d9-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="9a8d9-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="9a8d9-124">Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями</span><span class="sxs-lookup"><span data-stu-id="9a8d9-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="9a8d9-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="9a8d9-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="9a8d9-126">Оповещения из Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender для удостоверений, включая сведения о серьезности и категории угроз</span><span class="sxs-lookup"><span data-stu-id="9a8d9-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="9a8d9-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="9a8d9-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="9a8d9-128">Действия, связанные с файлами, в облачных приложениях и службах</span><span class="sxs-lookup"><span data-stu-id="9a8d9-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="9a8d9-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="9a8d9-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="9a8d9-130">Сведения о файлах, вложенных в сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="9a8d9-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="9a8d9-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="9a8d9-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="9a8d9-132">События электронной почты Microsoft 365, включая события доставки и блокирования электронной почты</span><span class="sxs-lookup"><span data-stu-id="9a8d9-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="9a8d9-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="9a8d9-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="9a8d9-134">События безопасности, которые происходят после доставки, после того как Microsoft 365 доставляет сообщения электронной почты в почтовый ящик получателя</span><span class="sxs-lookup"><span data-stu-id="9a8d9-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="9a8d9-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="9a8d9-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="9a8d9-136">Сведения об URL-адресах в электронных письмах</span><span class="sxs-lookup"><span data-stu-id="9a8d9-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="9a8d9-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="9a8d9-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="9a8d9-138">События с использованием локального контроллера домена с Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="9a8d9-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="9a8d9-139">В этой таблице описывается ряд событий, связанных с удостоверением, и системных событий на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="9a8d9-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="9a8d9-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="9a8d9-141">Сведения об учетной записи из различных источников, включая Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9a8d9-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="9a8d9-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="9a8d9-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="9a8d9-143">События проверки подлинности в Active Directory и веб-службах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="9a8d9-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="9a8d9-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="9a8d9-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="9a8d9-145">Запросы объектов Active Directory, таких как пользователи, группы, устройства и домены</span><span class="sxs-lookup"><span data-stu-id="9a8d9-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="9a8d9-146">Таблица Map DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="9a8d9-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="9a8d9-147">Таблицы `AlertInfo` `AlertEvidence` и `DeviceAlertEvents` таблицы заменяют таблицу в схеме Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="9a8d9-148">Помимо данных об оповещениях устройств эти две таблицы включают данные об оповещениях для удостоверений, приложений и электронных писем.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="9a8d9-149">Используйте следующую таблицу для проверки того, как `DeviceAlertEvents` столбцы соеблюют столбцы в `AlertInfo` таблицах и `AlertEvidence` столбцах.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="9a8d9-150">Помимо столбцов в следующей таблице, в таблице содержится множество других столбцов, которые предоставляют более целостную картину оповещений из `AlertEvidence` различных источников.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="9a8d9-151">См. все столбцы AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="9a8d9-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="9a8d9-152">Столбец DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="9a8d9-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="9a8d9-153">Где найти те же данные в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a8d9-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="9a8d9-154">`AlertInfo` и  `AlertEvidence` таблицы</span><span class="sxs-lookup"><span data-stu-id="9a8d9-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="9a8d9-155">`AlertInfo` и  `AlertEvidence` таблицы</span><span class="sxs-lookup"><span data-stu-id="9a8d9-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="9a8d9-156">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9a8d9-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="9a8d9-157">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9a8d9-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="9a8d9-158">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="9a8d9-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="9a8d9-159">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="9a8d9-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="9a8d9-160">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="9a8d9-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="9a8d9-161">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9a8d9-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="9a8d9-162">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9a8d9-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="9a8d9-163">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9a8d9-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="9a8d9-164">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="9a8d9-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="9a8d9-165">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="9a8d9-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="9a8d9-166">Этот столбец обычно используется в Microsoft Defender для конечной точки для поиска связанных записей в других таблицах.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="9a8d9-167">В Microsoft 365 Defender вы можете получить связанные данные непосредственно из `AlertEvidence` таблицы.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="9a8d9-168">Этот столбец обычно используется в Microsoft Defender для конечной точки для получения дополнительных сведений о событиях в других таблицах.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="9a8d9-169">В Microsoft 365 Defender вы можете получить связанные данные непосредственно из `AlertEvidence` таблицы.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="9a8d9-170">Настройка существующего Защитника Майкрософт для запросов конечных точек</span><span class="sxs-lookup"><span data-stu-id="9a8d9-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="9a8d9-171">Microsoft Defender для запросов конечных точек будет работать без ссылки на `DeviceAlertEvents` таблицу.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="9a8d9-172">Чтобы использовать эти запросы в Microsoft 365 Defender, внесите указанные здесь изменения.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="9a8d9-173">Замените `DeviceAlertEvents` на `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="9a8d9-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="9a8d9-174">Присоединитесь `AlertInfo` к `AlertEvidence` таблицам и таблицам, чтобы получить `AlertId` эквивалентные данные.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="9a8d9-175">Исходный запрос</span><span class="sxs-lookup"><span data-stu-id="9a8d9-175">Original query</span></span>
<span data-ttu-id="9a8d9-176">Следующий запрос использует в Microsoft Defender для конечной точки для получения оповещений, `DeviceAlertEvents` в том числеpowershell.exe: __</span><span class="sxs-lookup"><span data-stu-id="9a8d9-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="9a8d9-177">Изменен запрос</span><span class="sxs-lookup"><span data-stu-id="9a8d9-177">Modified query</span></span>
<span data-ttu-id="9a8d9-178">Следующий запрос был настроен для использования в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="9a8d9-179">Вместо того чтобы проверять имя файла непосредственно из, он присоединяется и проверяет имя `DeviceAlertEvents` `AlertEvidence` файла в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="9a8d9-180">Перенос пользовательских правил обнаружения</span><span class="sxs-lookup"><span data-stu-id="9a8d9-180">Migrate custom detection rules</span></span>

<span data-ttu-id="9a8d9-181">При редактировании правил Microsoft Defender для конечных точек в Microsoft 365 они продолжают работать так же, как и раньше, если в результате запроса только таблицы устройств.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-181">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> <span data-ttu-id="9a8d9-182">Например, оповещения, созданные пользовательскими правилами обнаружения, которые запрашивают только таблицы устройств, будут по-прежнему доставляться в SIEM и создавать уведомления по электронной почте в зависимости от того, как вы настроили их в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-182">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9a8d9-183">Все существующие правила подавления в Защитнике для конечной точки также будут применяться.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-183">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="9a8d9-184">После изменения правила Защитника для конечной точки, чтобы оно запрашивает таблицы удостоверений и электронной почты, доступные только в Microsoft 365 Defender, правило автоматически перемещается в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-184">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="9a8d9-185">Оповещения, созданные правилом переноса:</span><span class="sxs-lookup"><span data-stu-id="9a8d9-185">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="9a8d9-186">Больше не видны на портале Защитника конечных точек (Центр безопасности Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="9a8d9-186">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="9a8d9-187">Прекратить доставку в SIEM или создавать уведомления по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-187">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="9a8d9-188">Чтобы обойти это изменение, настройте уведомления через Microsoft 365 Defender для получения оповещений.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-188">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="9a8d9-189">Вы можете использовать [API Защитника Microsoft 365](api-incident.md) для получения уведомлений об оповещениях об обнаружении клиентов или связанных инцидентах.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-189">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="9a8d9-190">Microsoft Defender не будет подавлять правила подавления конечных точек.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-190">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="9a8d9-191">Чтобы предотвратить генерирование оповещений для определенных пользователей, устройств или почтовых ящиков, измените соответствующие запросы, чтобы исключить эти сущности явным образом.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-191">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="9a8d9-192">Если вы изменяете правило таким образом, вам будет предложено подтвердить, прежде чем эти изменения будут применены.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-192">If you do edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="9a8d9-193">Новые оповещения, созданные пользовательскими правилами обнаружения на портале Защитника Microsoft 365, отображаются на странице оповещений со следующими сведениями:</span><span class="sxs-lookup"><span data-stu-id="9a8d9-193">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="9a8d9-194">Название и описание оповещения</span><span class="sxs-lookup"><span data-stu-id="9a8d9-194">Alert title and description</span></span> 
- <span data-ttu-id="9a8d9-195">Активы, на которые влияют ресурсы</span><span class="sxs-lookup"><span data-stu-id="9a8d9-195">Impacted assets</span></span>
- <span data-ttu-id="9a8d9-196">Действия, принятые в ответ на оповещение</span><span class="sxs-lookup"><span data-stu-id="9a8d9-196">Actions taken in response to the alert</span></span>
- <span data-ttu-id="9a8d9-197">Результаты запроса, которые инициировали оповещение</span><span class="sxs-lookup"><span data-stu-id="9a8d9-197">Query results that triggered the alert</span></span> 
- <span data-ttu-id="9a8d9-198">Сведения о настраиваемом правиле обнаружения</span><span class="sxs-lookup"><span data-stu-id="9a8d9-198">Information on the custom detection rule</span></span> 
 
![Изображение новой страницы оповещений](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="9a8d9-200">Написание запросов без DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="9a8d9-200">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="9a8d9-201">В схеме Защитника Microsoft 365 предоставляются таблицы и таблицы для размещения разнообразных сведений, сопровождающих оповещения из `AlertInfo` `AlertEvidence` различных источников.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-201">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="9a8d9-202">Чтобы получить те же сведения оповещений, которые использовались для получения из таблицы в схеме Microsoft Defender для конечной точки, отфильтруем таблицу по каждому уникальному ИД с таблицей, которая предоставляет подробные сведения о событиях и `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` объектах.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-202">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="9a8d9-203">См. пример запроса ниже:</span><span class="sxs-lookup"><span data-stu-id="9a8d9-203">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="9a8d9-204">Этот запрос дает намного больше столбцов, чем `DeviceAlertEvents` в схеме Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-204">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="9a8d9-205">Чтобы управлять результатами, используйте для получения только интересуемых `project` столбцов.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-205">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="9a8d9-206">В примере ниже проектов столбцов, которые могут вас заинтересовать, когда исследование обнаружило активность PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9a8d9-206">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="9a8d9-207">Если вы хотите отфильтровать определенные объекты, участвующие в оповещениях, это можно сделать, указав тип сущности и значение, которое вы хотите `EntityType` отфильтровать.</span><span class="sxs-lookup"><span data-stu-id="9a8d9-207">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="9a8d9-208">В следующем примере ищется определенный IP-адрес:</span><span class="sxs-lookup"><span data-stu-id="9a8d9-208">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="9a8d9-209">См. также</span><span class="sxs-lookup"><span data-stu-id="9a8d9-209">See also</span></span>
- [<span data-ttu-id="9a8d9-210">Включить Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9a8d9-210">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9a8d9-211">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="9a8d9-211">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9a8d9-212">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="9a8d9-212">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9a8d9-213">Расширенный поиск в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="9a8d9-213">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)