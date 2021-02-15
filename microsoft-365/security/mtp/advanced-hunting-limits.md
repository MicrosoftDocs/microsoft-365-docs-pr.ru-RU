---
title: Квоты advanced hunting и параметры использования в Microsoft 365 Defender
description: Различные квоты и параметры использования (ограничения служб), которые отвечают службе advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema, kusto, CPU limit, query limit, resources, maximum results, quota, parameters, allocation
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
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929794"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="3d48f-104">Квоты и параметры использования для расширенных охот</span><span class="sxs-lookup"><span data-stu-id="3d48f-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3d48f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3d48f-105">**Applies to:**</span></span>
- <span data-ttu-id="3d48f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3d48f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3d48f-107">Для поддержания быстрой работы службы и реагирования расширенный поиск задает различные квоты и параметры использования (также известные как "ограничения службы").</span><span class="sxs-lookup"><span data-stu-id="3d48f-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="3d48f-108">Эти квоты и параметры применяются к запросам, которые запускают вручную и [настраиваемые правила обнаружения.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="3d48f-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="3d48f-109">Клиенты, которые регулярно запускают [](advanced-hunting-best-practices.md) несколько запросов, должны отслеживать потребление и применять лучшие методики оптимизации, чтобы свести к минимуму сбои.</span><span class="sxs-lookup"><span data-stu-id="3d48f-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="3d48f-110">Чтобы понять существующие квоты и параметры использования, обратитесь к следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="3d48f-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="3d48f-111">Квота или параметр</span><span class="sxs-lookup"><span data-stu-id="3d48f-111">Quota or parameter</span></span> | <span data-ttu-id="3d48f-112">Size</span><span class="sxs-lookup"><span data-stu-id="3d48f-112">Size</span></span> | <span data-ttu-id="3d48f-113">Цикл обновления</span><span class="sxs-lookup"><span data-stu-id="3d48f-113">Refresh cycle</span></span> | <span data-ttu-id="3d48f-114">Description</span><span class="sxs-lookup"><span data-stu-id="3d48f-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="3d48f-115">Диапазон данных</span><span class="sxs-lookup"><span data-stu-id="3d48f-115">Data range</span></span> | <span data-ttu-id="3d48f-116">30 дней</span><span class="sxs-lookup"><span data-stu-id="3d48f-116">30 days</span></span> | <span data-ttu-id="3d48f-117">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="3d48f-117">Every query</span></span> | <span data-ttu-id="3d48f-118">Каждый запрос может искать данные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="3d48f-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="3d48f-119">Набор результатов</span><span class="sxs-lookup"><span data-stu-id="3d48f-119">Result set</span></span> | <span data-ttu-id="3d48f-120">10 000 строк</span><span class="sxs-lookup"><span data-stu-id="3d48f-120">10,000 rows</span></span> | <span data-ttu-id="3d48f-121">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="3d48f-121">Every query</span></span> | <span data-ttu-id="3d48f-122">Каждый запрос может возвращать до 10 000 записей.</span><span class="sxs-lookup"><span data-stu-id="3d48f-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="3d48f-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="3d48f-123">Timeout</span></span> | <span data-ttu-id="3d48f-124">10 минут</span><span class="sxs-lookup"><span data-stu-id="3d48f-124">10 minutes</span></span> | <span data-ttu-id="3d48f-125">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="3d48f-125">Every query</span></span> | <span data-ttu-id="3d48f-126">Каждый запрос может работать до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="3d48f-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="3d48f-127">Если оно не завершится в течение 10 минут, служба отобразит ошибку.</span><span class="sxs-lookup"><span data-stu-id="3d48f-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="3d48f-128">Ресурсы ЦП</span><span class="sxs-lookup"><span data-stu-id="3d48f-128">CPU resources</span></span> | <span data-ttu-id="3d48f-129">В зависимости от размера клиента</span><span class="sxs-lookup"><span data-stu-id="3d48f-129">Based on tenant size</span></span> | <span data-ttu-id="3d48f-130">- В час, а затем каждые 15 минут</span><span class="sxs-lookup"><span data-stu-id="3d48f-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="3d48f-131">- Ежедневно в 12 полночь</span><span class="sxs-lookup"><span data-stu-id="3d48f-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="3d48f-132">Служба принудительно применяет суточную и 15-минутную квоты отдельно.</span><span class="sxs-lookup"><span data-stu-id="3d48f-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="3d48f-133">Для каждой квоты портал отображает ошибку при каждом запуске запроса, когда клиент потребляет более 10 % выделенных ресурсов. [](advanced-hunting-errors.md)</span><span class="sxs-lookup"><span data-stu-id="3d48f-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="3d48f-134">Запросы блокируются, если клиент достиг 100 % до следующего ежедневного или 15-минутного цикла.</span><span class="sxs-lookup"><span data-stu-id="3d48f-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="3d48f-135">Отдельный набор квот и параметров применяется к запросам на расширенный поиск, выполняемый с помощью API.</span><span class="sxs-lookup"><span data-stu-id="3d48f-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="3d48f-136">Ознакомьтесь с API расширенных охот</span><span class="sxs-lookup"><span data-stu-id="3d48f-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="3d48f-137">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="3d48f-137">Related topics</span></span>

- [<span data-ttu-id="3d48f-138">Расширенные методы охоты</span><span class="sxs-lookup"><span data-stu-id="3d48f-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="3d48f-139">Обработка ошибок расширенных поисков</span><span class="sxs-lookup"><span data-stu-id="3d48f-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="3d48f-140">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="3d48f-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3d48f-141">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="3d48f-141">Custom detections overview</span></span>](custom-detections-overview.md)