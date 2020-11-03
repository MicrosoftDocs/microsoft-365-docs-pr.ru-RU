---
title: Расширенные квоты и параметры использования при поиске в защитнике Microsoft 365
description: Общие сведения о различных квотах и параметрах использования (ограничениях служб), которые не поддерживают службу расширенного поискового запросы
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, схема, Кусто, ограничение использования ЦП, ограничение числа запросов, ресурсы, максимальные результаты, квота, параметры, выделение
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
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847372"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a><span data-ttu-id="15237-104">Расширенные квоты и параметры использования при поиске</span><span class="sxs-lookup"><span data-stu-id="15237-104">Advanced hunting quotas and usage parameters</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="15237-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="15237-105">**Applies to:**</span></span>
- <span data-ttu-id="15237-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="15237-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="15237-107">Для обеспечения работоспособности и скорости обслуживания службы Расширенный поиск устанавливает различные квоты и параметры использования (также называемые ограничениями для служб).</span><span class="sxs-lookup"><span data-stu-id="15237-107">To keep the service performant and responsive, advanced hunting sets various quotas and usage parameters (also known as "service limits").</span></span> <span data-ttu-id="15237-108">Эти квоты и параметры применяются к запросам, выполняемым вручную и [пользовательским правилом обнаружения](custom-detection-rules.md).</span><span class="sxs-lookup"><span data-stu-id="15237-108">These quotas and parameters apply to queries run manually and by [custom detection rules](custom-detection-rules.md).</span></span> <span data-ttu-id="15237-109">Клиенты, которые регулярно запускают несколько запросов, должны отслеживать потребление и [применять рекомендации по оптимизации](advanced-hunting-best-practices.md) для минимизации сбоев.</span><span class="sxs-lookup"><span data-stu-id="15237-109">Customers who run multiple queries regularly should track consumption and [apply optimization best practices](advanced-hunting-best-practices.md) to minimize disruptions.</span></span>

<span data-ttu-id="15237-110">В приведенной ниже таблице содержатся сведения о существующих квотах и параметрах использования.</span><span class="sxs-lookup"><span data-stu-id="15237-110">Refer to the following table to understand existing quotas and usage parameters.</span></span>

| <span data-ttu-id="15237-111">Квота или параметр</span><span class="sxs-lookup"><span data-stu-id="15237-111">Quota or parameter</span></span> | <span data-ttu-id="15237-112">Size</span><span class="sxs-lookup"><span data-stu-id="15237-112">Size</span></span> | <span data-ttu-id="15237-113">Цикл обновления</span><span class="sxs-lookup"><span data-stu-id="15237-113">Refresh cycle</span></span> | <span data-ttu-id="15237-114">Описание</span><span class="sxs-lookup"><span data-stu-id="15237-114">Description</span></span> |
|--|--|--|--|
| <span data-ttu-id="15237-115">Диапазон данных</span><span class="sxs-lookup"><span data-stu-id="15237-115">Data range</span></span> | <span data-ttu-id="15237-116">30 дней</span><span class="sxs-lookup"><span data-stu-id="15237-116">30 days</span></span> | <span data-ttu-id="15237-117">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="15237-117">Every query</span></span> | <span data-ttu-id="15237-118">Каждый запрос может выполнять поиск данных за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="15237-118">Each query can look up data from up to the past 30 days.</span></span> |
| <span data-ttu-id="15237-119">Результирующий набор</span><span class="sxs-lookup"><span data-stu-id="15237-119">Result set</span></span> | <span data-ttu-id="15237-120">10 000 строк</span><span class="sxs-lookup"><span data-stu-id="15237-120">10,000 rows</span></span> | <span data-ttu-id="15237-121">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="15237-121">Every query</span></span> | <span data-ttu-id="15237-122">Каждый запрос может возвращать до 10 000 записей.</span><span class="sxs-lookup"><span data-stu-id="15237-122">Each query can return up to 10,000 records.</span></span> |
| <span data-ttu-id="15237-123">Timeout</span><span class="sxs-lookup"><span data-stu-id="15237-123">Timeout</span></span> | <span data-ttu-id="15237-124">10 минут</span><span class="sxs-lookup"><span data-stu-id="15237-124">10 minutes</span></span> | <span data-ttu-id="15237-125">Каждый запрос</span><span class="sxs-lookup"><span data-stu-id="15237-125">Every query</span></span> | <span data-ttu-id="15237-126">Каждый запрос может выполняться до 10 минут.</span><span class="sxs-lookup"><span data-stu-id="15237-126">Each query can run for up to 10 minutes.</span></span> <span data-ttu-id="15237-127">Если она не будет завершена в течение 10 минут, служба выведет сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="15237-127">If it does not complete within 10 minutes, the service displays an error.</span></span>
| <span data-ttu-id="15237-128">Ресурсы ЦП</span><span class="sxs-lookup"><span data-stu-id="15237-128">CPU resources</span></span> | <span data-ttu-id="15237-129">На основе размера клиента</span><span class="sxs-lookup"><span data-stu-id="15237-129">Based on tenant size</span></span> | <span data-ttu-id="15237-130">— В час, а затем каждые 15 минут.</span><span class="sxs-lookup"><span data-stu-id="15237-130">- On the hour and then every 15 minutes</span></span><br><span data-ttu-id="15237-131">– Ежедневно в 12 полуночи</span><span class="sxs-lookup"><span data-stu-id="15237-131">- Daily at 12 midnight</span></span> | <span data-ttu-id="15237-132">Служба применяет каждую из ежедневных и 15 минутных квот отдельно.</span><span class="sxs-lookup"><span data-stu-id="15237-132">The service enforces the daily and the 15-minute quota separately.</span></span> <span data-ttu-id="15237-133">Для каждой квоты на [портале отображается сообщение об ошибке](advanced-hunting-errors.md) при выполнении запроса, а клиент потребляет 10% выделенных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="15237-133">For each quota, the [portal displays an error](advanced-hunting-errors.md) whenever a query runs and the tenant has consumed over 10% of allocated resources.</span></span> <span data-ttu-id="15237-134">Запросы блокируются, если клиент достиг 100% до следующего дня или 15 минутного цикла.</span><span class="sxs-lookup"><span data-stu-id="15237-134">Queries are blocked if the tenant has reached 100% until after the next daily or 15-minute cycle.</span></span> |

>[!NOTE] 
><span data-ttu-id="15237-135">Отдельный набор квот и параметров применяется к расширенным запросам на поиск с поиском, выполненным через API.</span><span class="sxs-lookup"><span data-stu-id="15237-135">A separate set of quotas and parameters apply to advanced hunting queries performed through the API.</span></span> [<span data-ttu-id="15237-136">Сведения о расширенных API поискового интерфейса</span><span class="sxs-lookup"><span data-stu-id="15237-136">Read about advanced hunting APIs</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a><span data-ttu-id="15237-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="15237-137">Related topics</span></span>

- [<span data-ttu-id="15237-138">Расширенные рекомендации по поиску</span><span class="sxs-lookup"><span data-stu-id="15237-138">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="15237-139">Обработка дополнительных ошибок при поиске</span><span class="sxs-lookup"><span data-stu-id="15237-139">Handle advanced hunting errors</span></span>](advanced-hunting-errors.md)
- [<span data-ttu-id="15237-140">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="15237-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="15237-141">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="15237-141">Custom detections overview</span></span>](custom-detections-overview.md)