---
title: Расширенные квоты охоты и параметры использования в Microsoft 365 Defender
description: Разграничить различные квоты и параметры использования (ограничения службы), которые будут отвечать на запросы передовой службы охоты.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results, quota, parameters, allocation
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
ms.openlocfilehash: c9526363b0430514455db1fbdf12cfb7a18229f1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932993"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="1a074-104">Расширенные квоты на охоту и параметры использования</span><span class="sxs-lookup"><span data-stu-id="1a074-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1a074-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1a074-105">**Applies to:**</span></span>
- <span data-ttu-id="1a074-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a074-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1a074-107">Для поддержания выполнения службы и реагирования на нее расширенный режим охоты задает различные квоты и параметры использования (также известные как "ограничения службы").</span><span class="sxs-lookup"><span data-stu-id="1a074-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="1a074-108">Эти квоты и параметры применяются к запросам, которые запускают вручную и по [пользовательским правилам обнаружения.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="1a074-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="1a074-109">Клиенты, которые регулярно запускают несколько запросов, должны отслеживать потребление и применять оптимальные методы оптимизации, [чтобы](advanced-hunting-best-practices.md) свести к минимуму нарушения.</span><span class="sxs-lookup"><span data-stu-id="1a074-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="1a074-110">Обратитесь к следующей таблице, чтобы понять существующие квоты и параметры использования.</span><span class="sxs-lookup"><span data-stu-id="1a074-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="1a074-111">Квота или параметр</span><span class="sxs-lookup"><span data-stu-id="1a074-111">Quota or parameter</span></span> | <span data-ttu-id="1a074-112">Size</span><span class="sxs-lookup"><span data-stu-id="1a074-112">Size</span></span> | <span data-ttu-id="1a074-113">Цикл обновления</span><span class="sxs-lookup"><span data-stu-id="1a074-113">Refresh cycle</span></span> | <span data-ttu-id="1a074-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1a074-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="1a074-115">Диапазон данных</span><span class="sxs-lookup"><span data-stu-id="1a074-115">Data range</span></span> | <span data-ttu-id="1a074-116">30 дней</span><span class="sxs-lookup"><span data-stu-id="1a074-116">30 days</span></span> | <span data-ttu-id="1a074-117">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="1a074-117">Every query</span></span> | <span data-ttu-id="1a074-118">Каждый запрос может искать данные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="1a074-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="1a074-119">Набор результатов</span><span class="sxs-lookup"><span data-stu-id="1a074-119">Result set</span></span> | <span data-ttu-id="1a074-120">10 000 строк</span><span class="sxs-lookup"><span data-stu-id="1a074-120">10,000 rows</span></span> | <span data-ttu-id="1a074-121">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="1a074-121">Every query</span></span> | <span data-ttu-id="1a074-122">Каждый запрос может возвращать до 10 000 записей.</span><span class="sxs-lookup"><span data-stu-id="1a074-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="1a074-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="1a074-123">Timeout</span></span> | <span data-ttu-id="1a074-124">10 минут</span><span class="sxs-lookup"><span data-stu-id="1a074-124">10 minutes</span></span> | <span data-ttu-id="1a074-125">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="1a074-125">Every query</span></span> | <span data-ttu-id="1a074-126">Каждый запрос может работать до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="1a074-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="1a074-127">Если он не завершится в течение 10 минут, служба отображает ошибку.</span><span class="sxs-lookup"><span data-stu-id="1a074-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="1a074-128">Ресурсы ЦП</span><span class="sxs-lookup"><span data-stu-id="1a074-128">CPU resources</span></span> | <span data-ttu-id="1a074-129">В зависимости от размера клиента</span><span class="sxs-lookup"><span data-stu-id="1a074-129">Based on tenant size</span></span> | <span data-ttu-id="1a074-130">- В час, а затем каждые 15 минут</span><span class="sxs-lookup"><span data-stu-id="1a074-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="1a074-131">- Ежедневно в 12 полночь</span><span class="sxs-lookup"><span data-stu-id="1a074-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="1a074-132">Служба обеспечивает ежедневное и 15-минутное квотирование отдельно.</span><span class="sxs-lookup"><span data-stu-id="1a074-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="1a074-133">Для каждой [квоты](advanced-hunting-errors.md) портал отображает ошибку всякий раз, когда выполняется запрос, и клиент потребляет более 10% выделенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="1a074-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="1a074-134">Запросы блокируют, если клиент достиг 100% до следующего ежедневного или 15-минутного цикла.</span><span class="sxs-lookup"><span data-stu-id="1a074-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="1a074-135">Отдельный набор квот и параметров применяется к расширенным запросам на охоту, выполняемым через API.</span><span class="sxs-lookup"><span data-stu-id="1a074-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="1a074-136">Ознакомьтесь с расширенными API охоты</span><span class="sxs-lookup"><span data-stu-id="1a074-136">Read about advanced hunting APIs</span></span>](./api-advanced-hunting.md)

## <a name="related-topics"></a><span data-ttu-id="1a074-137">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="1a074-137">Related topics</span></span>

- [<span data-ttu-id="1a074-138">Передовые методы охоты</span><span class="sxs-lookup"><span data-stu-id="1a074-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="1a074-139">Обработка ошибок, совершенных в области охоты</span><span class="sxs-lookup"><span data-stu-id="1a074-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="1a074-140">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="1a074-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1a074-141">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="1a074-141">Custom detections overview</span></span>](custom-detections-overview.md)