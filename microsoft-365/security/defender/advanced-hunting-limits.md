---
title: Расширенные квоты охоты и параметры использования в Microsoft 365 Defender
description: Разграничить различные квоты и параметры использования (ограничения службы), которые будут отвечать на запросы передовой службы охоты.
keywords: продвинутая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, схема, кусто, ограничение ЦП, ограничение запросов, ресурсы, максимальные результаты, квота, параметры, распределение
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
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245604"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="34592-104">Расширенные квоты на охоту и параметры использования</span><span class="sxs-lookup"><span data-stu-id="34592-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="34592-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="34592-105">**Applies to:**</span></span>
- <span data-ttu-id="34592-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34592-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="34592-107">Для поддержания выполнения службы и реагирования на нее расширенный режим охоты задает различные квоты и параметры использования (также известные как "ограничения службы").</span><span class="sxs-lookup"><span data-stu-id="34592-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="34592-108">Эти квоты и параметры применяются отдельно к запросам, которые запускают вручную, а запросы запускают с использованием [пользовательских правил обнаружения.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="34592-108">These quotas and parameters apply separately to queries run manually and to queries run using [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="34592-109">Клиенты, которые регулярно запускают несколько запросов, должны помнить об этих ограничениях и применять оптимальные методы оптимизации, [чтобы](advanced-hunting-best-practices.md) свести к минимуму нарушения.</span><span class="sxs-lookup"><span data-stu-id="34592-109">Customers who run multiple queries regularly should be mindful of these limits and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="34592-110">Обратитесь к следующей таблице, чтобы понять существующие квоты и параметры использования.</span><span class="sxs-lookup"><span data-stu-id="34592-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="34592-111">Квота или параметр</span><span class="sxs-lookup"><span data-stu-id="34592-111">Quota or parameter</span></span> | <span data-ttu-id="34592-112">Size</span><span class="sxs-lookup"><span data-stu-id="34592-112">Size</span></span> | <span data-ttu-id="34592-113">Цикл обновления</span><span class="sxs-lookup"><span data-stu-id="34592-113">Refresh cycle</span></span> | <span data-ttu-id="34592-114">Описание</span><span class="sxs-lookup"><span data-stu-id="34592-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="34592-115">Диапазон данных</span><span class="sxs-lookup"><span data-stu-id="34592-115">Data range</span></span> | <span data-ttu-id="34592-116">30 дней</span><span class="sxs-lookup"><span data-stu-id="34592-116">30 days</span></span> | <span data-ttu-id="34592-117">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="34592-117">Every query</span></span> | <span data-ttu-id="34592-118">Каждый запрос может искать данные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="34592-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="34592-119">Набор результатов</span><span class="sxs-lookup"><span data-stu-id="34592-119">Result set</span></span> | <span data-ttu-id="34592-120">10 000 строк</span><span class="sxs-lookup"><span data-stu-id="34592-120">10,000 rows</span></span> | <span data-ttu-id="34592-121">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="34592-121">Every query</span></span> | <span data-ttu-id="34592-122">Каждый запрос может возвращать до 10 000 записей.</span><span class="sxs-lookup"><span data-stu-id="34592-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="34592-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="34592-123">Timeout</span></span> | <span data-ttu-id="34592-124">10 минут</span><span class="sxs-lookup"><span data-stu-id="34592-124">10 minutes</span></span> | <span data-ttu-id="34592-125">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="34592-125">Every query</span></span> | <span data-ttu-id="34592-126">Каждый запрос может работать до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="34592-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="34592-127">Если он не завершится в течение 10 минут, служба отображает ошибку.</span><span class="sxs-lookup"><span data-stu-id="34592-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="34592-128">Ресурсы ЦП</span><span class="sxs-lookup"><span data-stu-id="34592-128">CPU resources</span></span> | <span data-ttu-id="34592-129">В зависимости от размера клиента</span><span class="sxs-lookup"><span data-stu-id="34592-129">Based on tenant size</span></span> | <span data-ttu-id="34592-130">Каждые 15 минут</span><span class="sxs-lookup"><span data-stu-id="34592-130">Every 15 minutes</span></span> | <span data-ttu-id="34592-131">Портал [отображает ошибку при](advanced-hunting-errors.md) запуске запроса, и клиент потребляет более 10% выделенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="34592-131">The [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="34592-132">Запросы блокируют, если клиент достиг 100% до следующего 15-минутного цикла.</span><span class="sxs-lookup"><span data-stu-id="34592-132">Queries are blocked if the tenant has reached 100% until after the next 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="34592-133">Отдельный набор квот и параметров применяется к расширенным запросам на охоту, выполняемым через API.</span><span class="sxs-lookup"><span data-stu-id="34592-133">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="34592-134">Ознакомьтесь с расширенными API охоты</span><span class="sxs-lookup"><span data-stu-id="34592-134">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="34592-135">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="34592-135">Related topics</span></span>

- [<span data-ttu-id="34592-136">Передовые методы охоты</span><span class="sxs-lookup"><span data-stu-id="34592-136">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="34592-137">Обработка ошибок, совершенных в области охоты</span><span class="sxs-lookup"><span data-stu-id="34592-137">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="34592-138">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="34592-138">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="34592-139">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="34592-139">Custom detections overview</span></span>](custom-detections-overview.md)