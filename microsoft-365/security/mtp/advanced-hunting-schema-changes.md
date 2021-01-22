---
title: Изменения именования в схеме advanced hunting в Microsoft 365 Defender
description: Отслеживание и проверка именования таблиц и столбцов в схеме расширенных поисков
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, data, naming changes, rename, Microsoft Threat Protection
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
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932206"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="be90a-104">Схема "Расширенный поиск" — изменения именования</span><span class="sxs-lookup"><span data-stu-id="be90a-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="be90a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="be90a-105">**Applies to:**</span></span>
- <span data-ttu-id="be90a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="be90a-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="be90a-107">Схема [advanced hunting регулярно](advanced-hunting-schema-tables.md) обновляется для добавления новых таблиц и столбцов.</span><span class="sxs-lookup"><span data-stu-id="be90a-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="be90a-108">В некоторых случаях существующие имена столбцов переименовываются или заменяются для улучшения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="be90a-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="be90a-109">В этой статье вы можете просмотреть изменения именования, которые могут повлиять на запросы.</span><span class="sxs-lookup"><span data-stu-id="be90a-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="be90a-110">Изменения именования автоматически применяются к запросам, сохраненным в центре безопасности, включая запросы, используемые пользовательскими правилами обнаружения.</span><span class="sxs-lookup"><span data-stu-id="be90a-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="be90a-111">Вам не нужно обновлять эти запросы вручную.</span><span class="sxs-lookup"><span data-stu-id="be90a-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="be90a-112">Однако вам потребуется обновить следующие запросы:</span><span class="sxs-lookup"><span data-stu-id="be90a-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="be90a-113">Запросы, которые запускаются с помощью API</span><span class="sxs-lookup"><span data-stu-id="be90a-113">Queries that are run using the API</span></span>
- <span data-ttu-id="be90a-114">Запросы, сохраненные в другом месте за пределами центра безопасности</span><span class="sxs-lookup"><span data-stu-id="be90a-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="be90a-115">Декабрь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="be90a-115">December 2020</span></span>

| <span data-ttu-id="be90a-116">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="be90a-116">Table name</span></span> | <span data-ttu-id="be90a-117">Исходное имя столбца</span><span class="sxs-lookup"><span data-stu-id="be90a-117">Original column name</span></span> | <span data-ttu-id="be90a-118">Имя нового столбца</span><span class="sxs-lookup"><span data-stu-id="be90a-118">New column name</span></span> | <span data-ttu-id="be90a-119">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="be90a-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="be90a-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="be90a-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="be90a-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="be90a-121">FinalEmailAction</span></span> | <span data-ttu-id="be90a-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="be90a-122">EmailAction</span></span> | <span data-ttu-id="be90a-123">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="be90a-123">Customer feedback</span></span> |
| [<span data-ttu-id="be90a-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="be90a-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="be90a-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="be90a-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="be90a-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="be90a-126">EmailActionPolicy</span></span> | <span data-ttu-id="be90a-127">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="be90a-127">Customer feedback</span></span> |
| [<span data-ttu-id="be90a-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="be90a-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="be90a-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="be90a-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="be90a-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="be90a-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="be90a-131">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="be90a-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="be90a-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="be90a-132">Related topics</span></span>
- [<span data-ttu-id="be90a-133">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="be90a-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="be90a-134">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="be90a-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)