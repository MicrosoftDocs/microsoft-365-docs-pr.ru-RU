---
title: Изменение имен в схеме advanced hunting в Microsoft 365 Defender
description: Отслеживание и проверка изменений именования таблиц и столбцов в схеме расширенных поисков
keywords: расширенный поиск, охота на угрозы, поиск киберугроз, защита от угроз (Майкрософт), Microsoft 365, mtp, m365, поиск, запрос, телеметрия, справочник по схеме, kusto, таблица, данные, изменения именования, переименование, Защита от угроз (Майкрософт)
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
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780815"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="ebb43-104">Схема "Расширенный поиск" — изменения именования</span><span class="sxs-lookup"><span data-stu-id="ebb43-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ebb43-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ebb43-105">**Applies to:**</span></span>
- <span data-ttu-id="ebb43-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ebb43-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="ebb43-107">Схема [расширенных поисков регулярно](advanced-hunting-schema-tables.md) обновляется для добавления новых таблиц и столбцов.</span><span class="sxs-lookup"><span data-stu-id="ebb43-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="ebb43-108">В некоторых случаях существующие имена столбцов переименовываются или заменяются для улучшения пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ebb43-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="ebb43-109">В этой статье вы можете просмотреть изменения именования, которые могут повлиять на ваши запросы.</span><span class="sxs-lookup"><span data-stu-id="ebb43-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="ebb43-110">Изменения именования автоматически применяются к запросам, сохраненным в центре безопасности, включая запросы, используемые пользовательскими правилами обнаружения.</span><span class="sxs-lookup"><span data-stu-id="ebb43-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="ebb43-111">Вам не нужно обновлять эти запросы вручную.</span><span class="sxs-lookup"><span data-stu-id="ebb43-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="ebb43-112">Однако вам потребуется обновить следующие запросы:</span><span class="sxs-lookup"><span data-stu-id="ebb43-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="ebb43-113">Запросы, которые запускаются с помощью API</span><span class="sxs-lookup"><span data-stu-id="ebb43-113">Queries that are run using the API</span></span>
- <span data-ttu-id="ebb43-114">Запросы, сохраненные в другом месте за пределами центра безопасности</span><span class="sxs-lookup"><span data-stu-id="ebb43-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="ebb43-115">Декабрь 2020 г.</span><span class="sxs-lookup"><span data-stu-id="ebb43-115">December 2020</span></span>

| <span data-ttu-id="ebb43-116">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="ebb43-116">Table name</span></span> | <span data-ttu-id="ebb43-117">Исходное имя столбца</span><span class="sxs-lookup"><span data-stu-id="ebb43-117">Original column name</span></span> | <span data-ttu-id="ebb43-118">Имя нового столбца</span><span class="sxs-lookup"><span data-stu-id="ebb43-118">New column name</span></span> | <span data-ttu-id="ebb43-119">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="ebb43-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="ebb43-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="ebb43-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="ebb43-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="ebb43-121">FinalEmailAction</span></span> | <span data-ttu-id="ebb43-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="ebb43-122">EmailAction</span></span> | <span data-ttu-id="ebb43-123">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="ebb43-123">Customer feedback</span></span> |
| [<span data-ttu-id="ebb43-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="ebb43-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="ebb43-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="ebb43-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="ebb43-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="ebb43-126">EmailActionPolicy</span></span> | <span data-ttu-id="ebb43-127">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="ebb43-127">Customer feedback</span></span> |
| [<span data-ttu-id="ebb43-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="ebb43-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="ebb43-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="ebb43-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="ebb43-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="ebb43-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="ebb43-131">Отзывы пользователей</span><span class="sxs-lookup"><span data-stu-id="ebb43-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="ebb43-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ebb43-132">Related topics</span></span>
- [<span data-ttu-id="ebb43-133">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="ebb43-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ebb43-134">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="ebb43-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)