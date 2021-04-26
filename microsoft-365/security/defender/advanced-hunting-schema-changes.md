---
title: Изменения именования в схеме предварительной охоты Microsoft 365 Defender
description: Отслеживание и проверка именования изменений таблиц и столбцов в продвинутой схеме охоты
keywords: расширенный поиск, охота на угрозы, поиск киберугроз, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка на схему, кусто, таблица, данные, изменения имен, переименование
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
ms.technology: m365d
ms.openlocfilehash: eb6dfa628488239e3953d19d5e78b338e76f50a2
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023789"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="f3705-104">Advanced hunting schema - Naming changes</span><span class="sxs-lookup"><span data-stu-id="f3705-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f3705-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f3705-105">**Applies to:**</span></span>
- <span data-ttu-id="f3705-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3705-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f3705-107">[Передовая схема охоты](advanced-hunting-schema-tables.md) регулярно обновляется, чтобы добавлять новые таблицы и столбцы.</span><span class="sxs-lookup"><span data-stu-id="f3705-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="f3705-108">В некоторых случаях имена существующих столбцов переименовываются или заменяются для улучшения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f3705-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="f3705-109">Обратитесь к этой статье, чтобы просмотреть изменения именования, которые могут повлиять на запросы.</span><span class="sxs-lookup"><span data-stu-id="f3705-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="f3705-110">Изменения именования автоматически применяются к запросам, сохраненным в центре безопасности, включая запросы, используемые пользовательскими правилами обнаружения.</span><span class="sxs-lookup"><span data-stu-id="f3705-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="f3705-111">Не нужно обновлять эти запросы вручную.</span><span class="sxs-lookup"><span data-stu-id="f3705-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="f3705-112">Однако необходимо обновить следующие запросы:</span><span class="sxs-lookup"><span data-stu-id="f3705-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="f3705-113">Запросы, которые запускаются с помощью API</span><span class="sxs-lookup"><span data-stu-id="f3705-113">Queries that are run using the API</span></span>
- <span data-ttu-id="f3705-114">Запросы, сохраненные в другом месте за пределами центра безопасности</span><span class="sxs-lookup"><span data-stu-id="f3705-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="f3705-115">Декабрь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="f3705-115">December 2020</span></span>

| <span data-ttu-id="f3705-116">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="f3705-116">Table name</span></span> | <span data-ttu-id="f3705-117">Исходное имя столбца</span><span class="sxs-lookup"><span data-stu-id="f3705-117">Original column name</span></span> | <span data-ttu-id="f3705-118">Новое имя столбца</span><span class="sxs-lookup"><span data-stu-id="f3705-118">New column name</span></span> | <span data-ttu-id="f3705-119">Причина изменений</span><span class="sxs-lookup"><span data-stu-id="f3705-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="f3705-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="f3705-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="f3705-121">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="f3705-121">Customer feedback</span></span> |
| [<span data-ttu-id="f3705-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="f3705-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="f3705-123">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="f3705-123">Customer feedback</span></span> |
| [<span data-ttu-id="f3705-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="f3705-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="f3705-125">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="f3705-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="f3705-126">Январь 2021 г.</span><span class="sxs-lookup"><span data-stu-id="f3705-126">January 2021</span></span>

| <span data-ttu-id="f3705-127">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="f3705-127">Column name</span></span> | <span data-ttu-id="f3705-128">Имя исходного значения</span><span class="sxs-lookup"><span data-stu-id="f3705-128">Original value name</span></span> | <span data-ttu-id="f3705-129">Новое имя значения</span><span class="sxs-lookup"><span data-stu-id="f3705-129">New value name</span></span> | <span data-ttu-id="f3705-130">Причина изменений</span><span class="sxs-lookup"><span data-stu-id="f3705-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="f3705-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="f3705-131">MCAS</span></span> |    <span data-ttu-id="f3705-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f3705-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="f3705-133">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="f3705-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="f3705-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="f3705-135">EDR</span><span class="sxs-lookup"><span data-stu-id="f3705-135">EDR</span></span>| <span data-ttu-id="f3705-136">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="f3705-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="f3705-137">WindowsDefenderAv</span></span> | <span data-ttu-id="f3705-138">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="f3705-138">Antivirus</span></span> | <span data-ttu-id="f3705-139">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="f3705-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="f3705-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="f3705-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="f3705-141">SmartScreen</span></span> | <span data-ttu-id="f3705-142">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="f3705-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="f3705-143">CustomerTI</span></span> |  <span data-ttu-id="f3705-144">Настраиваемый TI</span><span class="sxs-lookup"><span data-stu-id="f3705-144">Custom TI</span></span> | <span data-ttu-id="f3705-145">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="f3705-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="f3705-146">OfficeATP</span></span> | <span data-ttu-id="f3705-147">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="f3705-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="f3705-148">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="f3705-149">MTP</span><span class="sxs-lookup"><span data-stu-id="f3705-149">MTP</span></span>   | <span data-ttu-id="f3705-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3705-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="f3705-151">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="f3705-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="f3705-152">AzureATP</span></span> |    <span data-ttu-id="f3705-153">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="f3705-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="f3705-154">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="f3705-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="f3705-155">CustomDetection</span></span>   | <span data-ttu-id="f3705-156">Настраиваемый обнаружение</span><span class="sxs-lookup"><span data-stu-id="f3705-156">Custom detection</span></span> | <span data-ttu-id="f3705-157">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="f3705-158">Автоматическаяинвестигация</span><span class="sxs-lookup"><span data-stu-id="f3705-158">AutomatedInvestigation</span></span> |<span data-ttu-id="f3705-159">Автоматическое расследование</span><span class="sxs-lookup"><span data-stu-id="f3705-159">Automated investigation</span></span> | <span data-ttu-id="f3705-160">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="f3705-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="f3705-161">ThreatExperts</span></span> | <span data-ttu-id="f3705-162">Эксперты Майкрософт по угрозам</span><span class="sxs-lookup"><span data-stu-id="f3705-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="f3705-163">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="f3705-164">TI третьей стороны</span><span class="sxs-lookup"><span data-stu-id="f3705-164">3rd party TI</span></span> | <span data-ttu-id="f3705-165">Датчики 3-й стороны</span><span class="sxs-lookup"><span data-stu-id="f3705-165">3rd Party sensors</span></span> | <span data-ttu-id="f3705-166">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="f3705-167">ATP в Microsoft Defender — это</span><span class="sxs-lookup"><span data-stu-id="f3705-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="f3705-168">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f3705-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="f3705-169">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="f3705-170">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f3705-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="f3705-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3705-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="f3705-172">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="f3705-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="f3705-173">Office 365 ATP</span></span>  |<span data-ttu-id="f3705-174">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="f3705-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="f3705-175">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="f3705-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="f3705-176">Azure ATP</span></span>    |<span data-ttu-id="f3705-177">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="f3705-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="f3705-178">Ребрендинг</span><span class="sxs-lookup"><span data-stu-id="f3705-178">Rebranding</span></span> |

<span data-ttu-id="f3705-179">`DetectionSource`доступна в таблице [AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="f3705-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="f3705-180">`ServiceSource`доступно в [таблицах AlertEvidence](advanced-hunting-alertevidence-table.md) и [AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="f3705-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 

## <a name="february-2021"></a><span data-ttu-id="f3705-181">Февраль 2021 г.</span><span class="sxs-lookup"><span data-stu-id="f3705-181">February 2021</span></span>

1. <span data-ttu-id="f3705-182">В [таблицах EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) и [EmailEvents](advanced-hunting-emailevents-table.md) столбцы и столбцы `MalwareFilterVerdict` `PhishFilterVerdict` заменены `ThreatTypes` столбцом.</span><span class="sxs-lookup"><span data-stu-id="f3705-182">In the [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) and [EmailEvents](advanced-hunting-emailevents-table.md) tables, the `MalwareFilterVerdict`and `PhishFilterVerdict` columns have been replaced by the `ThreatTypes` column.</span></span> <span data-ttu-id="f3705-183">Столбцы `MalwareDetectionMethod` `PhishDetectionMethod` и столбцы также были заменены `DetectionMethods` столбцом.</span><span class="sxs-lookup"><span data-stu-id="f3705-183">The `MalwareDetectionMethod` and `PhishDetectionMethod` columns were also replaced by the `DetectionMethods` column.</span></span> <span data-ttu-id="f3705-184">Эта оптимизация позволяет нам предоставлять дополнительные сведения в новых столбцах.</span><span class="sxs-lookup"><span data-stu-id="f3705-184">This streamlining allows us to provide more information under the new columns.</span></span> <span data-ttu-id="f3705-185">Сопоставление приведено ниже.</span><span class="sxs-lookup"><span data-stu-id="f3705-185">The mapping is provided below.</span></span>

| <span data-ttu-id="f3705-186">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="f3705-186">Table name</span></span> | <span data-ttu-id="f3705-187">Исходное имя столбца</span><span class="sxs-lookup"><span data-stu-id="f3705-187">Original column name</span></span> | <span data-ttu-id="f3705-188">Новое имя столбца</span><span class="sxs-lookup"><span data-stu-id="f3705-188">New column name</span></span> | <span data-ttu-id="f3705-189">Причина изменений</span><span class="sxs-lookup"><span data-stu-id="f3705-189">Reason for change</span></span>
|--|--|--|--|
| `EmailAttachmentInfo` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="f3705-190">Включай дополнительные методы обнаружения</span><span class="sxs-lookup"><span data-stu-id="f3705-190">Include more detection methods</span></span> |
| `EmailAttachmentInfo`  | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="f3705-191">Включаем дополнительные типы угроз</span><span class="sxs-lookup"><span data-stu-id="f3705-191">Include more threat types</span></span> |
| `EmailEvents` | `MalwareDetectionMethod` <br> `PhishDetectionMethod` | `DetectionMethods` | <span data-ttu-id="f3705-192">Включай дополнительные методы обнаружения</span><span class="sxs-lookup"><span data-stu-id="f3705-192">Include more detection methods</span></span> |
| `EmailEvents` | `MalwareFilterVerdict` <br>`PhishFilterVerdict` | `ThreatTypes` | <span data-ttu-id="f3705-193">Включаем дополнительные типы угроз</span><span class="sxs-lookup"><span data-stu-id="f3705-193">Include more threat types</span></span> |


2. <span data-ttu-id="f3705-194">В `EmailAttachmentInfo` таблицах `EmailEvents` и таблицах `ThreatNames` столбец был добавлен, чтобы предоставить дополнительные сведения об угрозе электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f3705-194">In the `EmailAttachmentInfo` and `EmailEvents` tables, the `ThreatNames` column was added to give more information about the email threat.</span></span> <span data-ttu-id="f3705-195">В этом столбце содержатся такие значения, как спам или фишинг.</span><span class="sxs-lookup"><span data-stu-id="f3705-195">This column contains values like Spam or Phish.</span></span>

3. <span data-ttu-id="f3705-196">В таблице [DeviceInfo](advanced-hunting-deviceinfo-table.md) столбец был заменен столбцом `DeviceObjectId` на основе `AadDeviceId` отзывов клиентов.</span><span class="sxs-lookup"><span data-stu-id="f3705-196">In the [DeviceInfo](advanced-hunting-deviceinfo-table.md) table, the `DeviceObjectId` column was replaced by the `AadDeviceId` column based on customer feedback.</span></span>

4. <span data-ttu-id="f3705-197">В таблице [DeviceEvents](advanced-hunting-deviceevents-table.md) несколько имен ActionType были изменены, чтобы лучше отражать описание действия.</span><span class="sxs-lookup"><span data-stu-id="f3705-197">In the [DeviceEvents](advanced-hunting-deviceevents-table.md) table, several ActionType names were modified to better reflect the description of the action.</span></span> <span data-ttu-id="f3705-198">Подробные сведения об изменениях приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="f3705-198">Details of the changes can be found below.</span></span>

| <span data-ttu-id="f3705-199">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="f3705-199">Table name</span></span> | <span data-ttu-id="f3705-200">Исходное имя ActionType</span><span class="sxs-lookup"><span data-stu-id="f3705-200">Original ActionType name</span></span> | <span data-ttu-id="f3705-201">Новое имя ActionType</span><span class="sxs-lookup"><span data-stu-id="f3705-201">New ActionType name</span></span> | <span data-ttu-id="f3705-202">Причина изменений</span><span class="sxs-lookup"><span data-stu-id="f3705-202">Reason for change</span></span>
|--|--|--|--|
| `DeviceEvents` | `DlpPocPrintJob` | `FilePrinted` | <span data-ttu-id="f3705-203">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="f3705-203">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveMount` | `UsbDriveMounted` | <span data-ttu-id="f3705-204">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="f3705-204">Customer feedback</span></span> |
| `DeviceEvents` | `UsbDriveUnmount` | `UsbDriveUnmounted` | <span data-ttu-id="f3705-205">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="f3705-205">Customer feedback</span></span> |
| `DeviceEvents` | `WriteProcessMemoryApiCall` | `WriteToLsassProcessMemory` | <span data-ttu-id="f3705-206">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="f3705-206">Customer feedback</span></span> |

## <a name="march-2021"></a><span data-ttu-id="f3705-207">Март 2021 г.</span><span class="sxs-lookup"><span data-stu-id="f3705-207">March 2021</span></span>

<span data-ttu-id="f3705-208">Таблица `DeviceTvmSoftwareInventoryVulnerabilities` обесценилась.</span><span class="sxs-lookup"><span data-stu-id="f3705-208">The `DeviceTvmSoftwareInventoryVulnerabilities` table has been deprecated.</span></span> <span data-ttu-id="f3705-209">Его заменяют `DeviceTvmSoftwareInventory` таблицы `DeviceTvmSoftwareVulnerabilities` и таблицы.</span><span class="sxs-lookup"><span data-stu-id="f3705-209">Replacing it are the `DeviceTvmSoftwareInventory` and `DeviceTvmSoftwareVulnerabilities` tables.</span></span>



## <a name="related-topics"></a><span data-ttu-id="f3705-210">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f3705-210">Related topics</span></span>
- [<span data-ttu-id="f3705-211">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="f3705-211">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f3705-212">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="f3705-212">Understand the schema</span></span>](advanced-hunting-schema-tables.md)