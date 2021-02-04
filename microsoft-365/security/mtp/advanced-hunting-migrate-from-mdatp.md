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
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094811"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="4417c-104">Перенос запросов на расширенный поиск из Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4417c-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="4417c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="4417c-105">**Applies to:**</span></span>
- <span data-ttu-id="4417c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4417c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4417c-107">Переместите ваши расширенные процессы выслеки из Microsoft Defender для конечной точки, чтобы заблаговременно искать угрозы с использованием более широкого набора данных.</span><span class="sxs-lookup"><span data-stu-id="4417c-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="4417c-108">В Microsoft 365 Defender вы получаете доступ к данным из других решений для обеспечения безопасности Microsoft 365, в том числе:</span><span class="sxs-lookup"><span data-stu-id="4417c-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="4417c-109">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4417c-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="4417c-110">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="4417c-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="4417c-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4417c-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="4417c-112">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="4417c-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="4417c-113">Большинство пользователей Endpoint в Microsoft Defender могут использовать [Microsoft 365 Defender без дополнительных лицензий.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="4417c-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="4417c-114">Чтобы начать переключение расширенных процессов охоты из Защитника для конечной точки, включите [Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="4417c-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="4417c-115">Переход можно без влияния на существующие процессы Защитника для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="4417c-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="4417c-116">Сохраненные запросы остаются без изменений, а пользовательские правила обнаружения продолжают запускаться и создавать оповещения.</span><span class="sxs-lookup"><span data-stu-id="4417c-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="4417c-117">Однако они будут видны в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4417c-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="4417c-118">Таблицы схемы только в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4417c-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="4417c-119">Схема advanced hunting в [Microsoft 365 Defender](advanced-hunting-schema-tables.md) предоставляет дополнительные таблицы, содержащие данные из различных решений для обеспечения безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4417c-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="4417c-120">Следующие таблицы доступны только в Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="4417c-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="4417c-121">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="4417c-121">Table name</span></span> | <span data-ttu-id="4417c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="4417c-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="4417c-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="4417c-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="4417c-124">Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями</span><span class="sxs-lookup"><span data-stu-id="4417c-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="4417c-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="4417c-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="4417c-126">Оповещения из Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender для удостоверений, включая сведения о серьезности и категории угроз</span><span class="sxs-lookup"><span data-stu-id="4417c-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="4417c-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="4417c-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="4417c-128">Действия, связанные с файлами, в облачных приложениях и службах</span><span class="sxs-lookup"><span data-stu-id="4417c-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="4417c-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="4417c-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="4417c-130">Сведения о файлах, вложенных в сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="4417c-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="4417c-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="4417c-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="4417c-132">События электронной почты Microsoft 365, в том числе события доставки и блокирования электронной почты</span><span class="sxs-lookup"><span data-stu-id="4417c-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="4417c-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="4417c-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="4417c-134">События безопасности, которые происходят после доставки, после того как Microsoft 365 доставляет сообщения электронной почты в почтовый ящик получателя</span><span class="sxs-lookup"><span data-stu-id="4417c-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="4417c-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="4417c-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="4417c-136">Сведения об URL-адресах в электронных письмах</span><span class="sxs-lookup"><span data-stu-id="4417c-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="4417c-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="4417c-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="4417c-138">События, связанные с контроллером локального домена под управлением Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="4417c-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="4417c-139">В этой таблице описывается ряд событий, связанных с удостоверением, и системных событий на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="4417c-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="4417c-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="4417c-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="4417c-141">Сведения об учетной записи из различных источников, включая Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4417c-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="4417c-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="4417c-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="4417c-143">События проверки подлинности в Active Directory и веб-службах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4417c-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="4417c-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="4417c-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="4417c-145">Запросы объектов Active Directory, таких как пользователи, группы, устройства и домены</span><span class="sxs-lookup"><span data-stu-id="4417c-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="4417c-146">Таблица Map DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="4417c-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="4417c-147">Таблицы `AlertInfo` `AlertEvidence` и `DeviceAlertEvents` таблицы заменяют таблицу в схеме Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="4417c-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="4417c-148">Помимо данных об оповещениях устройств эти две таблицы включают данные об оповещениях для удостоверений, приложений и электронных писем.</span><span class="sxs-lookup"><span data-stu-id="4417c-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="4417c-149">Используйте следующую таблицу для проверки того, как `DeviceAlertEvents` столбцы соеблюют столбцы в `AlertInfo` таблицах и `AlertEvidence` столбцах.</span><span class="sxs-lookup"><span data-stu-id="4417c-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="4417c-150">Помимо столбцов в следующей таблице, в таблице содержится множество других столбцов, которые предоставляют более целостную картину оповещений из `AlertEvidence` различных источников.</span><span class="sxs-lookup"><span data-stu-id="4417c-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="4417c-151">См. все столбцы AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="4417c-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="4417c-152">Столбец DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="4417c-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="4417c-153">Где найти те же данные в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4417c-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="4417c-154">`AlertInfo` и  `AlertEvidence` таблицы</span><span class="sxs-lookup"><span data-stu-id="4417c-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="4417c-155">`AlertInfo` и  `AlertEvidence` таблицы</span><span class="sxs-lookup"><span data-stu-id="4417c-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="4417c-156">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="4417c-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="4417c-157">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="4417c-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="4417c-158">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="4417c-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="4417c-159">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="4417c-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="4417c-160">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="4417c-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="4417c-161">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="4417c-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="4417c-162">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="4417c-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="4417c-163">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="4417c-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="4417c-164">`AlertEvidence` table</span><span class="sxs-lookup"><span data-stu-id="4417c-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="4417c-165">`AlertInfo` table</span><span class="sxs-lookup"><span data-stu-id="4417c-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="4417c-166">Этот столбец обычно используется в Microsoft Defender для конечной точки для поиска связанных записей в других таблицах.</span><span class="sxs-lookup"><span data-stu-id="4417c-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="4417c-167">В Microsoft 365 Defender вы можете получить связанные данные непосредственно из `AlertEvidence` таблицы.</span><span class="sxs-lookup"><span data-stu-id="4417c-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="4417c-168">Этот столбец обычно используется в Microsoft Defender для конечной точки для получения дополнительных сведений о событиях в других таблицах.</span><span class="sxs-lookup"><span data-stu-id="4417c-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="4417c-169">В Microsoft 365 Defender вы можете получить связанные данные непосредственно из `AlertEvidence` таблицы.</span><span class="sxs-lookup"><span data-stu-id="4417c-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="4417c-170">Настройка существующего Защитника Майкрософт для запросов конечных точек</span><span class="sxs-lookup"><span data-stu-id="4417c-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="4417c-171">Microsoft Defender для запросов конечных точек будет работать без ссылки на `DeviceAlertEvents` таблицу.</span><span class="sxs-lookup"><span data-stu-id="4417c-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="4417c-172">Чтобы использовать эти запросы в Microsoft 365 Defender, внесите указанные здесь изменения.</span><span class="sxs-lookup"><span data-stu-id="4417c-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="4417c-173">Замените `DeviceAlertEvents` на `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="4417c-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="4417c-174">Присоединитесь `AlertInfo` к `AlertEvidence` таблицам и таблицам, чтобы получить `AlertId` эквивалентные данные.</span><span class="sxs-lookup"><span data-stu-id="4417c-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="4417c-175">Исходный запрос</span><span class="sxs-lookup"><span data-stu-id="4417c-175">Original query</span></span>
<span data-ttu-id="4417c-176">Следующий запрос использует в Microsoft Defender для конечной точки для получения оповещений, `DeviceAlertEvents` в том числеpowershell.exe: __</span><span class="sxs-lookup"><span data-stu-id="4417c-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="4417c-177">Изменен запрос</span><span class="sxs-lookup"><span data-stu-id="4417c-177">Modified query</span></span>
<span data-ttu-id="4417c-178">Следующий запрос был настроен для использования в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4417c-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="4417c-179">Вместо того чтобы проверять имя файла непосредственно из, он присоединяется и проверяет имя `DeviceAlertEvents` `AlertEvidence` файла в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="4417c-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```



## <a name="see-also"></a><span data-ttu-id="4417c-180">См. также</span><span class="sxs-lookup"><span data-stu-id="4417c-180">See also</span></span>
- [<span data-ttu-id="4417c-181">Включить Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4417c-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4417c-182">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="4417c-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4417c-183">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="4417c-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4417c-184">Расширенный поиск в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4417c-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)