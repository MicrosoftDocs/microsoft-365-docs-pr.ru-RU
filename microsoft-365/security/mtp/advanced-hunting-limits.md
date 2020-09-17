---
title: Расширенные пределы при поиске в Microsoft Threat protection
description: Общие сведения об ограничении служб, которые поддерживают службу расширенного поискового запросы
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, схема, Кусто, ограничение использования ЦП, ограничение числа запросов, ресурсы, максимальные результаты
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e3fbe29076d541df68dc39754960386fe935c7bc
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950953"
---
# <a name="advanced-hunting-service-limits"></a><span data-ttu-id="7119b-104">Расширенные пределы службы поискового значения</span><span class="sxs-lookup"><span data-stu-id="7119b-104">Advanced hunting service limits</span></span>

<span data-ttu-id="7119b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7119b-105">**Applies to:**</span></span>
- <span data-ttu-id="7119b-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="7119b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7119b-107">Чтобы служба не выполнялась и отвечала, расширенный поиск устанавливает различные пределы для запросов, выполняемых вручную и [пользовательскими правилами обнаружения](custom-detection-rules.md).</span><span class="sxs-lookup"><span data-stu-id="7119b-107">To keep the service performant and responsive, advanced hunting sets various limits for queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="7119b-108">Чтобы определить эти пределы, обратитесь к следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7119b-108">Refer to the following table to understand these limits.</span></span>

| <span data-ttu-id="7119b-109">Ограничение</span><span class="sxs-lookup"><span data-stu-id="7119b-109">Limit</span></span> | <span data-ttu-id="7119b-110">Size</span><span class="sxs-lookup"><span data-stu-id="7119b-110">Size</span></span> | <span data-ttu-id="7119b-111">Цикл обновления</span><span class="sxs-lookup"><span data-stu-id="7119b-111">Refresh cycle</span></span> | <span data-ttu-id="7119b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7119b-112">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="7119b-113">Диапазон данных</span><span class="sxs-lookup"><span data-stu-id="7119b-113">Data range</span></span> | <span data-ttu-id="7119b-114">30 дней</span><span class="sxs-lookup"><span data-stu-id="7119b-114">30 days</span></span> | <span data-ttu-id="7119b-115">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="7119b-115">Every query</span></span> | <span data-ttu-id="7119b-116">Каждый запрос может выполнять поиск данных за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="7119b-116">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="7119b-117">Результирующий набор</span><span class="sxs-lookup"><span data-stu-id="7119b-117">Result set</span></span> | <span data-ttu-id="7119b-118">10 000 строк</span><span class="sxs-lookup"><span data-stu-id="7119b-118">10,000 rows</span></span> | <span data-ttu-id="7119b-119">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="7119b-119">Every query</span></span> | <span data-ttu-id="7119b-120">Каждый запрос может возвращать до 10 000 записей.</span><span class="sxs-lookup"><span data-stu-id="7119b-120">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="7119b-121">Timeout</span><span class="sxs-lookup"><span data-stu-id="7119b-121">Timeout</span></span> | <span data-ttu-id="7119b-122">10 минут</span><span class="sxs-lookup"><span data-stu-id="7119b-122">10 minutes</span></span> | <span data-ttu-id="7119b-123">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="7119b-123">Every query</span></span> | <span data-ttu-id="7119b-124">Каждый запрос может выполняться до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="7119b-124">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="7119b-125">Если она не будет завершена в течение 10 минут, служба выведет сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7119b-125">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="7119b-126">Ресурсы ЦП</span><span class="sxs-lookup"><span data-stu-id="7119b-126">CPU resources</span></span> | <span data-ttu-id="7119b-127">На основе размера клиента</span><span class="sxs-lookup"><span data-stu-id="7119b-127">Based on tenant size</span></span> | <span data-ttu-id="7119b-128">— В час, а затем каждые 15 минут.</span><span class="sxs-lookup"><span data-stu-id="7119b-128">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="7119b-129">– Ежедневно в 12 полуночи</span><span class="sxs-lookup"><span data-stu-id="7119b-129">- Daily at 12 midnight</span></span> | <span data-ttu-id="7119b-130">Служба применяет ежедневный и 15 минутный лимит отдельно.</span><span class="sxs-lookup"><span data-stu-id="7119b-130">The service enforces the daily and the 15-minute limit separately.</span></span> <span data-ttu-id="7119b-131">Для каждого ограничения на [портале отображается сообщение об ошибке](advanced-hunting-errors.md) при выполнении запроса, а клиент потребляет 10% выделенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7119b-131">For each limit, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="7119b-132">Запросы блокируются, если клиент достиг 100% до следующего дня или 15 минутного цикла.</span><span class="sxs-lookup"><span data-stu-id="7119b-132">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="7119b-133">Отдельный набор пределов применяется к расширенным запросам на поиск с поиском, выполненным через API.</span><span class="sxs-lookup"><span data-stu-id="7119b-133">A separate set of limits apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="7119b-134">Сведения о расширенных API поискового интерфейса</span><span class="sxs-lookup"><span data-stu-id="7119b-134">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

<span data-ttu-id="7119b-135">Клиенты, которые регулярно запускают несколько запросов, должны отслеживать потребление и применять рекомендации по [оптимизации](advanced-hunting-best-practices.md) для минимизации сбоев, возникших в результате превышения этих пределов.</span><span class="sxs-lookup"><span data-stu-id="7119b-135">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruption resulting from exceeding these limits.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7119b-136">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7119b-136">Related topics</span></span>

- [<span data-ttu-id="7119b-137">Расширенные рекомендации по поиску</span><span class="sxs-lookup"><span data-stu-id="7119b-137">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="7119b-138">Обработка дополнительных ошибок при поиске</span><span class="sxs-lookup"><span data-stu-id="7119b-138">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="7119b-139">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="7119b-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7119b-140">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="7119b-140">Custom detections overview</span></span>](custom-detections-overview.md)
