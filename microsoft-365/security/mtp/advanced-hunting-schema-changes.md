---
title: Изменение имен в схеме advanced hunting в Microsoft 365 Defender
description: Отслеживание и проверка именования таблиц и столбцов в схеме расширенных поисков
keywords: расширенный поиск, охота на угрозы, поиск киберугроз, защита от угроз (Майкрософт), Microsoft 365, mtp, m365, поиск, запрос, телеметрия, справочник по схеме, kusto, таблица, данные, изменения именования, переименование, Защита от угроз (Майкрософт)
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
ms.technology: m365d
ms.openlocfilehash: 3f03543b03dca5fe426700ffff4f5c6edb8fa3c7
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066873"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="ba790-104">Схема "Расширенный поиск" — изменения именования</span><span class="sxs-lookup"><span data-stu-id="ba790-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ba790-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ba790-105">**Applies to:**</span></span>
- <span data-ttu-id="ba790-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba790-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="ba790-107">Схема [расширенных поисков регулярно](advanced-hunting-schema-tables.md) обновляется для добавления новых таблиц и столбцов.</span><span class="sxs-lookup"><span data-stu-id="ba790-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="ba790-108">В некоторых случаях существующие имена столбцов переименовываются или заменяются для улучшения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ba790-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="ba790-109">В этой статье вы можете просмотреть изменения именования, которые могут повлиять на ваши запросы.</span><span class="sxs-lookup"><span data-stu-id="ba790-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="ba790-110">Изменения именования автоматически применяются к запросам, сохраненным в центре безопасности, включая запросы, используемые пользовательскими правилами обнаружения.</span><span class="sxs-lookup"><span data-stu-id="ba790-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="ba790-111">Вам не нужно обновлять эти запросы вручную.</span><span class="sxs-lookup"><span data-stu-id="ba790-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="ba790-112">Однако вам потребуется обновить следующие запросы:</span><span class="sxs-lookup"><span data-stu-id="ba790-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="ba790-113">Запросы, которые запускаются с помощью API</span><span class="sxs-lookup"><span data-stu-id="ba790-113">Queries that are run using the API</span></span>
- <span data-ttu-id="ba790-114">Запросы, сохраненные в другом месте за пределами центра безопасности</span><span class="sxs-lookup"><span data-stu-id="ba790-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="ba790-115">Декабрь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="ba790-115">December 2020</span></span>

| <span data-ttu-id="ba790-116">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="ba790-116">Table name</span></span> | <span data-ttu-id="ba790-117">Исходное имя столбца</span><span class="sxs-lookup"><span data-stu-id="ba790-117">Original column name</span></span> | <span data-ttu-id="ba790-118">Имя нового столбца</span><span class="sxs-lookup"><span data-stu-id="ba790-118">New column name</span></span> | <span data-ttu-id="ba790-119">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="ba790-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="ba790-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="ba790-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailAction` | `EmailAction` | <span data-ttu-id="ba790-121">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="ba790-121">Customer feedback</span></span> |
| [<span data-ttu-id="ba790-122">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="ba790-122">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicy` | `EmailActionPolicy` | <span data-ttu-id="ba790-123">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="ba790-123">Customer feedback</span></span> |
| [<span data-ttu-id="ba790-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="ba790-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | `FinalEmailActionPolicyGuid` | `EmailActionPolicyGuid` | <span data-ttu-id="ba790-125">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="ba790-125">Customer feedback</span></span> |

## <a name="january-2021"></a><span data-ttu-id="ba790-126">Январь 2021 г.</span><span class="sxs-lookup"><span data-stu-id="ba790-126">January 2021</span></span>

| <span data-ttu-id="ba790-127">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="ba790-127">Column name</span></span> | <span data-ttu-id="ba790-128">Имя исходного значения</span><span class="sxs-lookup"><span data-stu-id="ba790-128">Original value name</span></span> | <span data-ttu-id="ba790-129">Новое имя значения</span><span class="sxs-lookup"><span data-stu-id="ba790-129">New value name</span></span> | <span data-ttu-id="ba790-130">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="ba790-130">Reason for change</span></span>
|--|--|--|--|
| `DetectionSource` | <span data-ttu-id="ba790-131">MCAS</span><span class="sxs-lookup"><span data-stu-id="ba790-131">MCAS</span></span> |    <span data-ttu-id="ba790-132">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ba790-132">Microsoft Cloud App Security</span></span> | <span data-ttu-id="ba790-133">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-133">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ba790-134">WindowsDefenderAtp</span><span class="sxs-lookup"><span data-stu-id="ba790-134">WindowsDefenderAtp</span></span>|   <span data-ttu-id="ba790-135">EDR</span><span class="sxs-lookup"><span data-stu-id="ba790-135">EDR</span></span>| <span data-ttu-id="ba790-136">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-136">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ba790-137">WindowsDefenderAv</span><span class="sxs-lookup"><span data-stu-id="ba790-137">WindowsDefenderAv</span></span> | <span data-ttu-id="ba790-138">Защита от вирусов</span><span class="sxs-lookup"><span data-stu-id="ba790-138">Antivirus</span></span> | <span data-ttu-id="ba790-139">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-139">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ba790-140">WindowsDefenderSmartScreen</span><span class="sxs-lookup"><span data-stu-id="ba790-140">WindowsDefenderSmartScreen</span></span> |  <span data-ttu-id="ba790-141">SmartScreen</span><span class="sxs-lookup"><span data-stu-id="ba790-141">SmartScreen</span></span> | <span data-ttu-id="ba790-142">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-142">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ba790-143">CustomerTI</span><span class="sxs-lookup"><span data-stu-id="ba790-143">CustomerTI</span></span> |  <span data-ttu-id="ba790-144">Настраиваемая ti</span><span class="sxs-lookup"><span data-stu-id="ba790-144">Custom TI</span></span> | <span data-ttu-id="ba790-145">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-145">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ba790-146">OfficeATP</span><span class="sxs-lookup"><span data-stu-id="ba790-146">OfficeATP</span></span> | <span data-ttu-id="ba790-147">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="ba790-147">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="ba790-148">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-148">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ba790-149">MTP</span><span class="sxs-lookup"><span data-stu-id="ba790-149">MTP</span></span>   | <span data-ttu-id="ba790-150">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba790-150">Microsoft 365 Defender</span></span> | <span data-ttu-id="ba790-151">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-151">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ba790-152">AzureATP</span><span class="sxs-lookup"><span data-stu-id="ba790-152">AzureATP</span></span> |    <span data-ttu-id="ba790-153">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="ba790-153">Microsoft Defender for Identity</span></span> | <span data-ttu-id="ba790-154">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-154">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ba790-155">CustomDetection</span><span class="sxs-lookup"><span data-stu-id="ba790-155">CustomDetection</span></span>   | <span data-ttu-id="ba790-156">Пользовательское обнаружение</span><span class="sxs-lookup"><span data-stu-id="ba790-156">Custom detection</span></span> | <span data-ttu-id="ba790-157">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-157">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ba790-158">AutomatedInvestigation</span><span class="sxs-lookup"><span data-stu-id="ba790-158">AutomatedInvestigation</span></span> |<span data-ttu-id="ba790-159">Автоматическое исследование</span><span class="sxs-lookup"><span data-stu-id="ba790-159">Automated investigation</span></span> | <span data-ttu-id="ba790-160">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-160">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ba790-161">ThreatExperts</span><span class="sxs-lookup"><span data-stu-id="ba790-161">ThreatExperts</span></span> | <span data-ttu-id="ba790-162">Эксперты Майкрософт по угрозам</span><span class="sxs-lookup"><span data-stu-id="ba790-162">Microsoft Threat Experts</span></span> | <span data-ttu-id="ba790-163">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-163">Rebranding</span></span> |
| `DetectionSource` | <span data-ttu-id="ba790-164">Сторонний ti</span><span class="sxs-lookup"><span data-stu-id="ba790-164">3rd party TI</span></span> | <span data-ttu-id="ba790-165">Сторонние датчики</span><span class="sxs-lookup"><span data-stu-id="ba790-165">3rd Party sensors</span></span> | <span data-ttu-id="ba790-166">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-166">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="ba790-167">ATP в Microsoft Defender — это</span><span class="sxs-lookup"><span data-stu-id="ba790-167">Microsoft Defender ATP</span></span>| <span data-ttu-id="ba790-168">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ba790-168">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="ba790-169">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-169">Rebranding</span></span> |
|`ServiceSource` |<span data-ttu-id="ba790-170">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="ba790-170">Microsoft Threat Protection</span></span>   | <span data-ttu-id="ba790-171">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba790-171">Microsoft 365 Defender</span></span> | <span data-ttu-id="ba790-172">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-172">Rebranding</span></span> |
| `ServiceSource` | <span data-ttu-id="ba790-173">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ba790-173">Office 365 ATP</span></span>  |<span data-ttu-id="ba790-174">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="ba790-174">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="ba790-175">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-175">Rebranding</span></span> |
| `ServiceSource` |<span data-ttu-id="ba790-176">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="ba790-176">Azure ATP</span></span>    |<span data-ttu-id="ba790-177">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="ba790-177">Microsoft Defender for Identity</span></span> | <span data-ttu-id="ba790-178">Rebranding</span><span class="sxs-lookup"><span data-stu-id="ba790-178">Rebranding</span></span> |

<span data-ttu-id="ba790-179">`DetectionSource`доступен в таблице [AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="ba790-179">`DetectionSource` is available in the [AlertInfo](advanced-hunting-alertinfo-table.md) table.</span></span> <span data-ttu-id="ba790-180">`ServiceSource`доступен в [таблицах AlertEvidence](advanced-hunting-alertevidence-table.md) и [AlertInfo.](advanced-hunting-alertinfo-table.md)</span><span class="sxs-lookup"><span data-stu-id="ba790-180">`ServiceSource` is available in the [AlertEvidence](advanced-hunting-alertevidence-table.md) and [AlertInfo](advanced-hunting-alertinfo-table.md) tables.</span></span> 
## <a name="related-topics"></a><span data-ttu-id="ba790-181">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="ba790-181">Related topics</span></span>
- [<span data-ttu-id="ba790-182">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="ba790-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ba790-183">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="ba790-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)