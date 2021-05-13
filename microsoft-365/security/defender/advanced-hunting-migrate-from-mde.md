---
title: Перенос расширенных запросов на охоту из Microsoft Defender для конечной точки
description: Узнайте, как настроить запросы Microsoft Defender для конечных точек, чтобы использовать их в Microsoft 365 Defender
keywords: продвинутая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, Microsoft Defender для конечной точки, поиск, запрос, телеметрия, настраиваемые обнаружения, схема, кусто, сопоставление
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ba6f84f9f08d0635dab6ac65eaa697b8e0e73df7
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470692"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="056b2-104">Перенос расширенных запросов на охоту из Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="056b2-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="056b2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="056b2-105">**Applies to:**</span></span>
- <span data-ttu-id="056b2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="056b2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="056b2-107">Переместите расширенные процессы охоты из Microsoft Defender для конечной точки, чтобы активно искать угрозы с помощью более широкого набора данных.</span><span class="sxs-lookup"><span data-stu-id="056b2-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="056b2-108">В Microsoft 365 Defender вы получаете доступ к данным из других Microsoft 365 решений безопасности, в том числе:</span><span class="sxs-lookup"><span data-stu-id="056b2-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="056b2-109">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="056b2-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="056b2-110">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="056b2-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="056b2-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="056b2-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="056b2-112">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="056b2-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="056b2-113">Большинство клиентов Microsoft Defender для конечных точек могут [использовать Microsoft 365 Defender без дополнительных лицензий.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="056b2-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="056b2-114">Чтобы начать переход ваших расширенных процессов охоты из Defender для конечной точки, включите [Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="056b2-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="056b2-115">Вы можете перейти, не затрагивая существующие рабочий процессы Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="056b2-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="056b2-116">Сохраненные запросы остаются нетронутыми, а пользовательские правила обнаружения продолжают запускать и создавать оповещения.</span><span class="sxs-lookup"><span data-stu-id="056b2-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="056b2-117">Однако они будут видны в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="056b2-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="056b2-118">Таблицы схемы только Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="056b2-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="056b2-119">Схема [Microsoft 365 Defender предоставляет](advanced-hunting-schema-tables.md) дополнительные таблицы, содержащие данные из различных Microsoft 365 безопасности.</span><span class="sxs-lookup"><span data-stu-id="056b2-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="056b2-120">Следующие таблицы доступны только в Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="056b2-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="056b2-121">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="056b2-121">Table name</span></span> | <span data-ttu-id="056b2-122">Описание</span><span class="sxs-lookup"><span data-stu-id="056b2-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="056b2-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="056b2-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="056b2-124">Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями</span><span class="sxs-lookup"><span data-stu-id="056b2-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="056b2-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="056b2-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="056b2-126">Оповещения от Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender для удостоверений, включая сведения о серьезности и категории угроз</span><span class="sxs-lookup"><span data-stu-id="056b2-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="056b2-127">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="056b2-127">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="056b2-128">Сведения о файлах, присоединенных к электронным письмам</span><span class="sxs-lookup"><span data-stu-id="056b2-128">Information about files attached to emails</span></span> |
| [<span data-ttu-id="056b2-129">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="056b2-129">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="056b2-130">Microsoft 365 событий электронной почты, включая доставку электронной почты и блокирование событий</span><span class="sxs-lookup"><span data-stu-id="056b2-130">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="056b2-131">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="056b2-131">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="056b2-132">События безопасности, которые происходят после доставки, Microsoft 365 после доставки сообщений электронной почты в почтовый ящик получателя</span><span class="sxs-lookup"><span data-stu-id="056b2-132">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="056b2-133">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="056b2-133">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="056b2-134">Сведения об URL-адресах в электронных письмах</span><span class="sxs-lookup"><span data-stu-id="056b2-134">Information about URLs on emails</span></span> |
| [<span data-ttu-id="056b2-135">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="056b2-135">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="056b2-136">События с участием локального контроллера домена под управлением Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="056b2-136">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="056b2-137">В этой таблице описывается ряд событий, связанных с удостоверением, и системных событий на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="056b2-137">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="056b2-138">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="056b2-138">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="056b2-139">Сведения об учетных записях из различных источников, включая Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="056b2-139">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="056b2-140">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="056b2-140">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="056b2-141">События проверки подлинности в службах Active Directory и Microsoft online</span><span class="sxs-lookup"><span data-stu-id="056b2-141">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="056b2-142">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="056b2-142">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="056b2-143">Запросы для объектов Active Directory, таких как пользователи, группы, устройства и домены</span><span class="sxs-lookup"><span data-stu-id="056b2-143">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="056b2-144">Запросы и настраиваемые обнаружения, которые используют таблицы схем, доступные только в Microsoft 365 Defender, можно просмотреть только в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="056b2-144">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="056b2-145">Таблица Map DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="056b2-145">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="056b2-146">Таблицы `AlertInfo` `AlertEvidence` и таблицы `DeviceAlertEvents` заменяют таблицу в схеме Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="056b2-146">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="056b2-147">Помимо данных о оповещениях о устройствах, эти две таблицы включают данные о оповещениях для удостоверений, приложений и электронных писем.</span><span class="sxs-lookup"><span data-stu-id="056b2-147">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="056b2-148">Используйте следующую таблицу, чтобы проверить, как столбцы сое всего мира сое and `DeviceAlertEvents` `AlertInfo` `AlertEvidence` tables.</span><span class="sxs-lookup"><span data-stu-id="056b2-148">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="056b2-149">Помимо столбцов в следующей таблице, в таблице содержится множество других столбцов, которые предоставляют более целостную картину оповещений из `AlertEvidence` различных источников.</span><span class="sxs-lookup"><span data-stu-id="056b2-149">In addition to the columns in the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="056b2-150">См. все столбцы AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="056b2-150">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="056b2-151">Колонка DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="056b2-151">DeviceAlertEvents column</span></span> | <span data-ttu-id="056b2-152">Где найти те же данные в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="056b2-152">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="056b2-153">`AlertInfo` и  `AlertEvidence` таблицы</span><span class="sxs-lookup"><span data-stu-id="056b2-153">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="056b2-154">`AlertInfo` и  `AlertEvidence` таблицы</span><span class="sxs-lookup"><span data-stu-id="056b2-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="056b2-155">`AlertEvidence` таблица</span><span class="sxs-lookup"><span data-stu-id="056b2-155">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="056b2-156">`AlertEvidence` таблица</span><span class="sxs-lookup"><span data-stu-id="056b2-156">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="056b2-157">`AlertInfo` таблица</span><span class="sxs-lookup"><span data-stu-id="056b2-157">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="056b2-158">`AlertInfo` таблица</span><span class="sxs-lookup"><span data-stu-id="056b2-158">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="056b2-159">`AlertInfo` таблица</span><span class="sxs-lookup"><span data-stu-id="056b2-159">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="056b2-160">`AlertEvidence` таблица</span><span class="sxs-lookup"><span data-stu-id="056b2-160">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="056b2-161">`AlertEvidence` таблица</span><span class="sxs-lookup"><span data-stu-id="056b2-161">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="056b2-162">`AlertEvidence` таблица</span><span class="sxs-lookup"><span data-stu-id="056b2-162">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="056b2-163">`AlertEvidence` таблица</span><span class="sxs-lookup"><span data-stu-id="056b2-163">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="056b2-164">`AlertInfo` таблица</span><span class="sxs-lookup"><span data-stu-id="056b2-164">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="056b2-165">Этот столбец обычно используется в Microsoft Defender для конечной точки для поиска связанных записей в других таблицах.</span><span class="sxs-lookup"><span data-stu-id="056b2-165">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="056b2-166">В Microsoft 365 Defender можно получить соответствующие данные непосредственно из `AlertEvidence` таблицы.</span><span class="sxs-lookup"><span data-stu-id="056b2-166">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="056b2-167">Этот столбец обычно используется в Microsoft Defender для конечной точки для получения дополнительных сведений о событиях в других таблицах.</span><span class="sxs-lookup"><span data-stu-id="056b2-167">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="056b2-168">В Microsoft 365 Defender можно получить соответствующие данные непосредственно из `AlertEvidence` таблицы.</span><span class="sxs-lookup"><span data-stu-id="056b2-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="056b2-169">Настройка существующих запросов Microsoft Defender для запросов конечной точки</span><span class="sxs-lookup"><span data-stu-id="056b2-169">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="056b2-170">Запросы Microsoft Defender для конечных точек будут работать как есть, если они не ссылатся на `DeviceAlertEvents` таблицу.</span><span class="sxs-lookup"><span data-stu-id="056b2-170">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="056b2-171">Чтобы использовать эти запросы в Microsoft 365 Defender, внесите эти изменения:</span><span class="sxs-lookup"><span data-stu-id="056b2-171">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="056b2-172">Замените `DeviceAlertEvents` `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="056b2-172">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="056b2-173">Присоединяйтесь `AlertInfo` к `AlertEvidence` таблицам и таблицам, чтобы получить `AlertId` эквивалентные данные.</span><span class="sxs-lookup"><span data-stu-id="056b2-173">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="056b2-174">Исходный запрос</span><span class="sxs-lookup"><span data-stu-id="056b2-174">Original query</span></span>
<span data-ttu-id="056b2-175">Следующий запрос используется `DeviceAlertEvents` в Microsoft Defender для конечной точки для получения оповещений, которые включают _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="056b2-175">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="056b2-176">Измененный запрос</span><span class="sxs-lookup"><span data-stu-id="056b2-176">Modified query</span></span>
<span data-ttu-id="056b2-177">Следующий запрос был скорректирован для использования в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="056b2-177">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="056b2-178">Вместо того, чтобы проверять имя файла непосредственно из, он присоединяется и проверяет имя `DeviceAlertEvents` `AlertEvidence` файла в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="056b2-178">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="056b2-179">Перенос пользовательских правил обнаружения</span><span class="sxs-lookup"><span data-stu-id="056b2-179">Migrate custom detection rules</span></span>

<span data-ttu-id="056b2-180">Когда правила Microsoft Defender для конечных точек редактированы в Microsoft 365 Defender, они продолжают функционировать так же, как и раньше, если в результате запрос смотрит только на таблицы устройств.</span><span class="sxs-lookup"><span data-stu-id="056b2-180">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="056b2-181">Например, оповещения, созданные пользовательскими правилами обнаружения, которые по-прежнему будут доставляться в SIEM только таблицы устройств и создавать уведомления электронной почты, в зависимости от того, как вы настроили их в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="056b2-181">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="056b2-182">Любые существующие правила подавления в Защитнике для конечной точки также будут продолжать применяться.</span><span class="sxs-lookup"><span data-stu-id="056b2-182">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="056b2-183">После изменения правила Defender для конечной точки, чтобы он запрашивал удостоверения и таблицы электронной почты, доступные только в Microsoft 365 Defender, правило автоматически перемещается в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="056b2-183">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="056b2-184">Оповещения, созданные правилом переноса:</span><span class="sxs-lookup"><span data-stu-id="056b2-184">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="056b2-185">Больше не отображается на портале Defender for Endpoint (Центр безопасности в Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="056b2-185">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="056b2-186">Прекратите доставку в SIEM или создание уведомлений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="056b2-186">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="056b2-187">Чтобы обойти это изменение, настройте уведомления Microsoft 365 Defender для получения оповещений.</span><span class="sxs-lookup"><span data-stu-id="056b2-187">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="056b2-188">Вы можете использовать [API Microsoft 365 Defender](api-incident.md) для получения уведомлений о оповещениях об обнаружении клиентов или связанных с ними инцидентах.</span><span class="sxs-lookup"><span data-stu-id="056b2-188">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="056b2-189">Правила подавления конечных точек microsoft Defender не будут подавлены.</span><span class="sxs-lookup"><span data-stu-id="056b2-189">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="056b2-190">Чтобы предотвратить сгенерированию оповещений для определенных пользователей, устройств или почтовых ящиков, измените соответствующие запросы, чтобы исключить эти объекты явно.</span><span class="sxs-lookup"><span data-stu-id="056b2-190">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="056b2-191">Если изменить правило таким образом, вам будет предложено подтверждение до того, как будут применены такие изменения.</span><span class="sxs-lookup"><span data-stu-id="056b2-191">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="056b2-192">На странице оповещений, которая содержит следующую информацию, отображаются новые оповещения, созданные пользовательскими правилами обнаружения Microsoft 365 портала Defender.</span><span class="sxs-lookup"><span data-stu-id="056b2-192">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="056b2-193">Название и описание оповещений</span><span class="sxs-lookup"><span data-stu-id="056b2-193">Alert title and description</span></span> 
- <span data-ttu-id="056b2-194">Влияние активов</span><span class="sxs-lookup"><span data-stu-id="056b2-194">Impacted assets</span></span>
- <span data-ttu-id="056b2-195">Действия, принятые в ответ на предупреждение</span><span class="sxs-lookup"><span data-stu-id="056b2-195">Actions taken in response to the alert</span></span>
- <span data-ttu-id="056b2-196">Результаты запроса, которые вызвали оповещение</span><span class="sxs-lookup"><span data-stu-id="056b2-196">Query results that triggered the alert</span></span> 
- <span data-ttu-id="056b2-197">Сведения о пользовательском правиле обнаружения</span><span class="sxs-lookup"><span data-stu-id="056b2-197">Information on the custom detection rule</span></span> 
 
> [!div class="mx-imgBorder"]
> <span data-ttu-id="056b2-198">![Изображение новой страницы оповещений](../../media/new-alert-page.png)</span><span class="sxs-lookup"><span data-stu-id="056b2-198">![Image of new alert page](../../media/new-alert-page.png)</span></span>

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="056b2-199">Записывай запросы без DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="056b2-199">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="056b2-200">В схеме Microsoft 365 Defender предоставляются таблицы и таблицы для размещения разнообразного набора сведений, сопровождающих оповещения `AlertInfo` `AlertEvidence` из различных источников.</span><span class="sxs-lookup"><span data-stu-id="056b2-200">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="056b2-201">Чтобы получить те же сведения оповещений, которые вы использовали для получения из таблицы в схеме Microsoft Defender для конечной точки, фильтруем таблицу, а затем присоединяем каждый уникальный ID со таблицей, которая предоставляет подробные сведения о событиях и `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` сущности.</span><span class="sxs-lookup"><span data-stu-id="056b2-201">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="056b2-202">Пример запроса см. ниже:</span><span class="sxs-lookup"><span data-stu-id="056b2-202">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="056b2-203">Этот запрос дает гораздо больше столбцов, чем `DeviceAlertEvents` в схеме Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="056b2-203">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="056b2-204">Чтобы сохранить управляемые результаты, используйте для получения только `project` интересуемых столбцов.</span><span class="sxs-lookup"><span data-stu-id="056b2-204">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="056b2-205">В примере ниже проектов столбцов, которые могут быть интересны при обнаружении в ходе расследования активности PowerShell:</span><span class="sxs-lookup"><span data-stu-id="056b2-205">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="056b2-206">Если вы хотите фильтровать для определенных сущностей, участвующих в оповещениях, вы можете это сделать, указав тип объекта и значение, которое вы хотите `EntityType` фильтровать.</span><span class="sxs-lookup"><span data-stu-id="056b2-206">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="056b2-207">В следующем примере ниже приводится пример определенного IP-адреса:</span><span class="sxs-lookup"><span data-stu-id="056b2-207">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="056b2-208">См. также</span><span class="sxs-lookup"><span data-stu-id="056b2-208">See also</span></span>
- [<span data-ttu-id="056b2-209">Включение Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="056b2-209">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="056b2-210">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="056b2-210">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="056b2-211">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="056b2-211">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="056b2-212">Расширенный поиск в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="056b2-212">Advanced hunting in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)