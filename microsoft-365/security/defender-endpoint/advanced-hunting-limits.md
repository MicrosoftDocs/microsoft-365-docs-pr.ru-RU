---
title: Расширенные ограничения на охоту в ATP Защитника Майкрософт
description: Разграничить различные ограничения службы, которые будут поддерживать отзывчивость передовой службы охоты
keywords: продвинутая охота, охота на угрозы, поиск киберугроз, mdatp, microsoft defender atp, wdatp, поиск, запрос, телеметрия, схема, кусто, ограничение ЦП, ограничение запросов, ресурсы, максимальные результаты
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8a9279d1dd2a6465553b576609bb81cdf4e03fa0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499529"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="d5536-104">Расширенные ограничения службы охоты</span><span class="sxs-lookup"><span data-stu-id="d5536-104">Advanced hunting service limits</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d5536-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d5536-105">**Applies to:**</span></span>
- [<span data-ttu-id="d5536-106">Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d5536-106">Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="d5536-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="d5536-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d5536-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="d5536-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="d5536-109">Чтобы служба выполняла и реагировала, расширенный режим охоты устанавливает различные ограничения для запросов, выполняемых вручную и по пользовательским [правилам обнаружения.](custom-detection-rules.md)</span><span class="sxs-lookup"><span data-stu-id="d5536-109">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="d5536-110">Чтобы понять эти ограничения, обратитесь к следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d5536-110">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="d5536-111">Ограничение</span><span class="sxs-lookup"><span data-stu-id="d5536-111">Limit</span></span> | <span data-ttu-id="d5536-112">Size</span><span class="sxs-lookup"><span data-stu-id="d5536-112">Size</span></span> | <span data-ttu-id="d5536-113">Цикл обновления</span><span class="sxs-lookup"><span data-stu-id="d5536-113">Refresh cycle</span></span> | <span data-ttu-id="d5536-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d5536-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="d5536-115">Диапазон данных</span><span class="sxs-lookup"><span data-stu-id="d5536-115">Data range</span></span> | <span data-ttu-id="d5536-116">30 дней</span><span class="sxs-lookup"><span data-stu-id="d5536-116">30 days</span></span> | <span data-ttu-id="d5536-117">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="d5536-117">Every query</span></span> | <span data-ttu-id="d5536-118">Каждый запрос может искать данные за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="d5536-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="d5536-119">Набор результатов</span><span class="sxs-lookup"><span data-stu-id="d5536-119">Result set</span></span> | <span data-ttu-id="d5536-120">10 000 строк</span><span class="sxs-lookup"><span data-stu-id="d5536-120">10,000 rows</span></span> | <span data-ttu-id="d5536-121">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="d5536-121">Every query</span></span> | <span data-ttu-id="d5536-122">Каждый запрос может возвращать до 10 000 записей.</span><span class="sxs-lookup"><span data-stu-id="d5536-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="d5536-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="d5536-123">Timeout</span></span> | <span data-ttu-id="d5536-124">10 минут</span><span class="sxs-lookup"><span data-stu-id="d5536-124">10 minutes</span></span> | <span data-ttu-id="d5536-125">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="d5536-125">Every query</span></span> | <span data-ttu-id="d5536-126">Каждый запрос может работать до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="d5536-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="d5536-127">Если он не завершится в течение 10 минут, служба отображает ошибку.</span><span class="sxs-lookup"><span data-stu-id="d5536-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="d5536-128">Ресурсы ЦП</span><span class="sxs-lookup"><span data-stu-id="d5536-128">CPU resources</span></span> | <span data-ttu-id="d5536-129">В зависимости от размера клиента</span><span class="sxs-lookup"><span data-stu-id="d5536-129">Based on tenant size</span></span> | <span data-ttu-id="d5536-130">- В час, а затем каждые 15 минут</span><span class="sxs-lookup"><span data-stu-id="d5536-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="d5536-131">- Ежедневно в 12 полночь</span><span class="sxs-lookup"><span data-stu-id="d5536-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="d5536-132">Служба обеспечивает ежедневное и 15-минутное ограничение отдельно.</span><span class="sxs-lookup"><span data-stu-id="d5536-132">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="d5536-133">Для каждого ограничения портал [отображает](advanced-hunting-errors.md) ошибку всякий раз, когда выполняется запрос, и клиент потребляет более 10% выделенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d5536-133">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="d5536-134">Запросы блокируют, если клиент достиг 100% до следующего ежедневного или 15-минутного цикла.</span><span class="sxs-lookup"><span data-stu-id="d5536-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="d5536-135">Отдельный набор ограничений применяется к расширенным запросам на охоту, выполняемым через API.</span><span class="sxs-lookup"><span data-stu-id="d5536-135">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="d5536-136">Ознакомьтесь с расширенными API охоты</span><span class="sxs-lookup"><span data-stu-id="d5536-136">Read about advanced hunting APIs</span></span>](run-advanced-query-api.md)

<span data-ttu-id="d5536-137">Клиенты, которые регулярно запускают [](advanced-hunting-best-practices.md) несколько запросов, должны отслеживать потребление и применять оптимальные методы оптимизации, чтобы свести к минимуму нарушения в результате превышения этих ограничений.</span><span class="sxs-lookup"><span data-stu-id="d5536-137">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d5536-138">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d5536-138">Related topics</span></span>

- [<span data-ttu-id="d5536-139">Передовые методы охоты</span><span class="sxs-lookup"><span data-stu-id="d5536-139">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="d5536-140">Обработка ошибок, совершенных в области охоты</span><span class="sxs-lookup"><span data-stu-id="d5536-140">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="d5536-141">Обзор расширенной охоты</span><span class="sxs-lookup"><span data-stu-id="d5536-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d5536-142">Правила настраиваемой диагностики</span><span class="sxs-lookup"><span data-stu-id="d5536-142">Custom detections rules</span></span>](custom-detection-rules.md)
