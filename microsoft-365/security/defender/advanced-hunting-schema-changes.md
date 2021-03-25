---
title: Изменения именования в схеме предварительной охоты Microsoft 365 Defender
description: Отслеживание и проверка именования изменений таблиц и столбцов в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, data, naming changes, rename, Microsoft Threat Protection
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
ms.openlocfilehash: acb259088717b2772ec9798027545f2ff6dbc5e0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076709"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="60c11-104">Advanced hunting schema - Naming changes</span><span class="sxs-lookup"><span data-stu-id="60c11-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="60c11-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="60c11-105">**Applies to:**</span></span>
- <span data-ttu-id="60c11-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60c11-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="60c11-107">[Передовая схема охоты](advanced-hunting-schema-tables.md) регулярно обновляется, чтобы добавлять новые таблицы и столбцы.</span><span class="sxs-lookup"><span data-stu-id="60c11-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="60c11-108">В некоторых случаях имена существующих столбцов переименовываются или заменяются для улучшения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="60c11-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="60c11-109">Обратитесь к этой статье, чтобы просмотреть изменения именования, которые могут повлиять на запросы.</span><span class="sxs-lookup"><span data-stu-id="60c11-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="60c11-110">Изменения именования автоматически применяются к запросам, сохраненным в центре безопасности, включая запросы, используемые пользовательскими правилами обнаружения.</span><span class="sxs-lookup"><span data-stu-id="60c11-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="60c11-111">Не нужно обновлять эти запросы вручную.</span><span class="sxs-lookup"><span data-stu-id="60c11-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="60c11-112">Однако необходимо обновить следующие запросы:</span><span class="sxs-lookup"><span data-stu-id="60c11-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="60c11-113">Запросы, которые запускаются с помощью API</span><span class="sxs-lookup"><span data-stu-id="60c11-113">Queries that are run using the API</span></span>
- <span data-ttu-id="60c11-114">Запросы, сохраненные в другом месте за пределами центра безопасности</span><span class="sxs-lookup"><span data-stu-id="60c11-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="60c11-115">Декабрь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="60c11-115">December 2020</span></span>

| <span data-ttu-id="60c11-116">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="60c11-116">Table name</span></span> | <span data-ttu-id="60c11-117">Исходное имя столбца</span><span class="sxs-lookup"><span data-stu-id="60c11-117">Original column name</span></span> | <span data-ttu-id="60c11-118">Новое имя столбца</span><span class="sxs-lookup"><span data-stu-id="60c11-118">New column name</span></span> | <span data-ttu-id="60c11-119">Причина изменений</span><span class="sxs-lookup"><span data-stu-id="60c11-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="60c11-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="60c11-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="60c11-121">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="60c11-121">Customer feedback</span></span> |
| [<span data-ttu-id="60c11-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="60c11-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="60c11-123">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="60c11-123">Customer feedback</span></span> |
| [<span data-ttu-id="60c11-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="60c11-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="60c11-125">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="60c11-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="60c11-126">Январь 2021 г.</span><span class="sxs-lookup"><span data-stu-id="60c11-126">January 2021</span></span>

| <span data-ttu-id="60c11-127">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="60c11-127">Column name</span></span> | <span data-ttu-id="60c11-128">Имя исходного значения</span><span class="sxs-lookup"><span data-stu-id="60c11-128">Original value name</span></span> | <span data-ttu-id="60c11-129">Новое имя значения</span><span class="sxs-lookup"><span data-stu-id="60c11-129">New value name</span></span> | <span data-ttu-id="60c11-130">Причина изменений</span><span class="sxs-lookup"><span data-stu-id="60c11-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="60c11-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="60c11-131">MCAS</span></span> |    <span data-ttu-id="60c11-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="60c11-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="60c11-133">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="60c11-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="60c11-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="60c11-135">EDR</span><span class="sxs-lookup"><span data-stu-id="60c11-135">EDR</span></span>| <span data-ttu-id="60c11-136">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="60c11-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="60c11-137">WindowsDefenderAv</span></span> | <span data-ttu-id="60c11-138">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="60c11-138">Antivirus</span></span> | <span data-ttu-id="60c11-139">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="60c11-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="60c11-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="60c11-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="60c11-141">SmartScreen</span></span> | <span data-ttu-id="60c11-142">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="60c11-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="60c11-143">CustomerTI</span></span> |  <span data-ttu-id="60c11-144">Настраиваемый TI</span><span class="sxs-lookup"><span data-stu-id="60c11-144">Custom TI</span></span> | <span data-ttu-id="60c11-145">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="60c11-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="60c11-146">OfficeATP</span></span> | <span data-ttu-id="60c11-147">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="60c11-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="60c11-148">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="60c11-149">MTP</span><span class="sxs-lookup"><span data-stu-id="60c11-149">MTP</span></span>   | <span data-ttu-id="60c11-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60c11-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="60c11-151">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="60c11-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="60c11-152">AzureATP</span></span> |    <span data-ttu-id="60c11-153">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="60c11-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="60c11-154">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="60c11-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="60c11-155">CustomDetection</span></span>   | <span data-ttu-id="60c11-156">Настраиваемый обнаружение</span><span class="sxs-lookup"><span data-stu-id="60c11-156">Custom detection</span></span> | <span data-ttu-id="60c11-157">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="60c11-158">Автоматическаяинвестигация</span><span class="sxs-lookup"><span data-stu-id="60c11-158">AutomatedInvestigation</span></span> |<span data-ttu-id="60c11-159">Автоматическое расследование</span><span class="sxs-lookup"><span data-stu-id="60c11-159">Automated investigation</span></span> | <span data-ttu-id="60c11-160">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="60c11-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="60c11-161">ThreatExperts</span></span> | <span data-ttu-id="60c11-162">Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="60c11-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="60c11-163">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="60c11-164">TI третьей стороны</span><span class="sxs-lookup"><span data-stu-id="60c11-164">3rd party TI</span></span> | <span data-ttu-id="60c11-165">Датчики 3-й стороны</span><span class="sxs-lookup"><span data-stu-id="60c11-165">3rd Party sensors</span></span> | <span data-ttu-id="60c11-166">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="60c11-167">ATP в Microsoft Defender — это</span><span class="sxs-lookup"><span data-stu-id="60c11-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="60c11-168">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="60c11-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="60c11-169">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="60c11-170">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="60c11-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="60c11-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60c11-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="60c11-172">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="60c11-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="60c11-173">Office 365 ATP</span></span>  |<span data-ttu-id="60c11-174">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="60c11-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="60c11-175">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="60c11-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="60c11-176">Azure ATP</span></span>    |<span data-ttu-id="60c11-177">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="60c11-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="60c11-178">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="60c11-178">Rebranding</span></span> |

<span data-ttu-id="60c11-179">`DetectionSource`доступна в таблице [AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="60c11-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="60c11-180">`ServiceSource`доступно в [таблицах AlertEvidence](advanced-hunting-alertevidence-table.md) и [AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="60c11-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="60c11-181">Февраль 2021 г.</span><span class="sxs-lookup"><span data-stu-id="60c11-181">February 2021</span></span>

1. <span data-ttu-id="60c11-182">В [таблицах EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) и [EmailEvents](advanced-hunting-emailevents-table.md) столбцы и столбцы `MalwareFilterVerdict` `PhishFilterVerdict` заменены `ThreatTypes` столбцом.</span><span class="sxs-lookup"><span data-stu-id="60c11-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="60c11-183">Столбцы `MalwareDetectionMethod` `PhishDetectionMethod` и столбцы также были заменены `DetectionMethods` столбцом.</span><span class="sxs-lookup"><span data-stu-id="60c11-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="60c11-184">Эта оптимизация позволяет нам предоставлять дополнительные сведения в новых столбцах.</span><span class="sxs-lookup"><span data-stu-id="60c11-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="60c11-185">Сопоставление приведено ниже.</span><span class="sxs-lookup"><span data-stu-id="60c11-185">The mapping is provided below.</span></span>

| <span data-ttu-id="60c11-186">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="60c11-186">Table name</span></span> | <span data-ttu-id="60c11-187">Исходное имя столбца</span><span class="sxs-lookup"><span data-stu-id="60c11-187">Original column name</span></span> | <span data-ttu-id="60c11-188">Новое имя столбца</span><span class="sxs-lookup"><span data-stu-id="60c11-188">New column name</span></span> | <span data-ttu-id="60c11-189">Причина изменений</span><span class="sxs-lookup"><span data-stu-id="60c11-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="60c11-190">Включай дополнительные методы обнаружения</span><span class="sxs-lookup"><span data-stu-id="60c11-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="60c11-191">Включаем дополнительные типы угроз</span><span class="sxs-lookup"><span data-stu-id="60c11-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="60c11-192">Включай дополнительные методы обнаружения</span><span class="sxs-lookup"><span data-stu-id="60c11-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="60c11-193">Включаем дополнительные типы угроз</span><span class="sxs-lookup"><span data-stu-id="60c11-193">Include more threat types</span></span> |


2. <span data-ttu-id="60c11-194">В `EmailAttachmentInfo` таблицах `EmailEvents` и таблицах `ThreatNames` столбец был добавлен, чтобы предоставить дополнительные сведения об угрозе электронной почты.</span><span class="sxs-lookup"><span data-stu-id="60c11-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="60c11-195">В этом столбце содержатся такие значения, как спам или фишинг.</span><span class="sxs-lookup"><span data-stu-id="60c11-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="60c11-196">В таблице [DeviceInfo](advanced-hunting-deviceinfo-table.md) столбец был заменен столбцом `DeviceObjectId` на основе `AadDeviceId` отзывов клиентов.</span><span class="sxs-lookup"><span data-stu-id="60c11-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="60c11-197">В таблице [DeviceEvents](advanced-hunting-deviceevents-table.md) несколько имен ActionType были изменены, чтобы лучше отражать описание действия.</span><span class="sxs-lookup"><span data-stu-id="60c11-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="60c11-198">Подробные сведения об изменениях приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="60c11-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="60c11-199">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="60c11-199">Table name</span></span> | <span data-ttu-id="60c11-200">Исходное имя ActionType</span><span class="sxs-lookup"><span data-stu-id="60c11-200">Original ActionType name</span></span> | <span data-ttu-id="60c11-201">Новое имя ActionType</span><span class="sxs-lookup"><span data-stu-id="60c11-201">New ActionType name</span></span> | <span data-ttu-id="60c11-202">Причина изменений</span><span class="sxs-lookup"><span data-stu-id="60c11-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="60c11-203">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="60c11-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="60c11-204">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="60c11-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="60c11-205">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="60c11-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="60c11-206">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="60c11-206">Customer feedback</span></span> |






## <a name="related-topics"></a><span data-ttu-id="60c11-207">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="60c11-207">Related topics</span></span>
- [<span data-ttu-id="60c11-208">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="60c11-208">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="60c11-209">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="60c11-209">Understand the schema</span></span>](advanced-hunting-schema-tables.md)