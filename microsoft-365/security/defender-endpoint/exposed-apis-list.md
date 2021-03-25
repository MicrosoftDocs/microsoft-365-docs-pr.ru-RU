---
title: Поддерживаемые API-API Microsoft Defender для конечных точек
ms.reviewer: ''
description: Узнайте о конкретных поддерживаемых сущностям Microsoft Defender для конечных точек, куда можно создавать вызовы API.
keywords: apis, поддерживаемые apis, actor, alerts, device, user, domain, ip, file, advanced queries, advanced hunting
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198330"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="18d9e-104">Поддерживаемые API-API Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="18d9e-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="18d9e-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="18d9e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="18d9e-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="18d9e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="18d9e-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="18d9e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="18d9e-108">URI конечной точки и версия</span><span class="sxs-lookup"><span data-stu-id="18d9e-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="18d9e-109">URI конечной точки:            </span><span class="sxs-lookup"><span data-stu-id="18d9e-109">Endpoint URI:</span></span>

> <span data-ttu-id="18d9e-110">База служб URI: https://api.securitycenter.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18d9e-110">The service base URI is: https://api.securitycenter.microsoft.com</span></span>
> 
> <span data-ttu-id="18d9e-111">На основе OData запросов имеется префикс "/api".</span><span class="sxs-lookup"><span data-stu-id="18d9e-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="18d9e-112">Например, для получения оповещений можно отправить запрос GET в https://api.securitycenter.microsoft.com/api/alerts</span><span class="sxs-lookup"><span data-stu-id="18d9e-112">For example, to get Alerts you can send GET request to https://api.securitycenter.microsoft.com/api/alerts</span></span>

### <a name="versioning"></a><span data-ttu-id="18d9e-113">Версия:</span><span class="sxs-lookup"><span data-stu-id="18d9e-113">Versioning:</span></span>

> <span data-ttu-id="18d9e-114">API поддерживает версию.</span><span class="sxs-lookup"><span data-stu-id="18d9e-114">The API supports versioning.</span></span>
> 
> <span data-ttu-id="18d9e-115">Текущая версия **— V1.0.**</span><span class="sxs-lookup"><span data-stu-id="18d9e-115">The current version is **V1.0**.</span></span>
> 
> <span data-ttu-id="18d9e-116">Чтобы использовать определенную версию, используйте этот формат: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="18d9e-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="18d9e-117">Пример: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="18d9e-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
> 
> <span data-ttu-id="18d9e-118">Если вы не указываете версию (например, https://api.securitycenter.microsoft.com/api/alerts ) вы получите последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="18d9e-118">If you don't specify any version (e.g. https://api.securitycenter.microsoft.com/api/alerts ) you will get to the latest version.</span></span>


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="18d9e-119">Дополнительные сведения об отдельных поддерживаемых сущностях, в которых можно запускать вызовы API, а также сведения, такие как значения запросов HTTP, заглавные заголовки запросов и ожидаемые ответы.</span><span class="sxs-lookup"><span data-stu-id="18d9e-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="18d9e-120">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="18d9e-120">In this section</span></span>

<span data-ttu-id="18d9e-121">Статья</span><span class="sxs-lookup"><span data-stu-id="18d9e-121">Topic</span></span> | <span data-ttu-id="18d9e-122">Описание</span><span class="sxs-lookup"><span data-stu-id="18d9e-122">Description</span></span>
:---|:---
<span data-ttu-id="18d9e-123">Расширенный охота</span><span class="sxs-lookup"><span data-stu-id="18d9e-123">Advanced Hunting</span></span> | <span data-ttu-id="18d9e-124">Выполнение запросов из API.</span><span class="sxs-lookup"><span data-stu-id="18d9e-124">Run queries from API.</span></span>
<span data-ttu-id="18d9e-125">Оповещения</span><span class="sxs-lookup"><span data-stu-id="18d9e-125">Alerts</span></span> | <span data-ttu-id="18d9e-126">Запустите вызовы API, такие как получения оповещений, создания оповещений, обновления оповещений и других.</span><span class="sxs-lookup"><span data-stu-id="18d9e-126">Run API calls such as get alerts, create alert, update alert and more.</span></span>
<span data-ttu-id="18d9e-127">Домены</span><span class="sxs-lookup"><span data-stu-id="18d9e-127">Domains</span></span> | <span data-ttu-id="18d9e-128">Запустите вызовы API, такие как получить устройства, связанные с доменом, статистику домена и другие.</span><span class="sxs-lookup"><span data-stu-id="18d9e-128">Run API calls such as get domain-related devices, domain statistics and more.</span></span>
<span data-ttu-id="18d9e-129">Files</span><span class="sxs-lookup"><span data-stu-id="18d9e-129">Files</span></span> | <span data-ttu-id="18d9e-130">Запустите вызовы API, такие как получения данных о файлах, связанных с файлами оповещений, устройств, связанных с файлами, и статистики файлов.</span><span class="sxs-lookup"><span data-stu-id="18d9e-130">Run API calls such as get file information, file related alerts, file related devices, and file statistics.</span></span>
<span data-ttu-id="18d9e-131">IPs</span><span class="sxs-lookup"><span data-stu-id="18d9e-131">IPs</span></span> | <span data-ttu-id="18d9e-132">Запустите вызовы API, такие как получения оповещений, связанных с IP, и получения статистики IP.</span><span class="sxs-lookup"><span data-stu-id="18d9e-132">Run API calls such as get IP-related alerts and get IP statistics.</span></span>
<span data-ttu-id="18d9e-133">Компьютеры</span><span class="sxs-lookup"><span data-stu-id="18d9e-133">Machines</span></span> | <span data-ttu-id="18d9e-134">Запустите вызовы API, такие как получить устройства, получить устройства по ID, сведения о в журнале пользователей, изменить теги и другие.</span><span class="sxs-lookup"><span data-stu-id="18d9e-134">Run API calls such as get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
<span data-ttu-id="18d9e-135">Действия машины</span><span class="sxs-lookup"><span data-stu-id="18d9e-135">Machine Actions</span></span> | <span data-ttu-id="18d9e-136">Запустите вызов API, например Isolation, запустите антивирусное сканирование и другие.</span><span class="sxs-lookup"><span data-stu-id="18d9e-136">Run API call such as Isolation, Run anti-virus scan and more.</span></span>
<span data-ttu-id="18d9e-137">Индикаторы</span><span class="sxs-lookup"><span data-stu-id="18d9e-137">Indicators</span></span> | <span data-ttu-id="18d9e-138">Запустите вызов API, например создать индикатор, получить Индикаторы и удалить Индикаторы.</span><span class="sxs-lookup"><span data-stu-id="18d9e-138">Run API call such as create Indicator, get Indicators and delete Indicators.</span></span>
<span data-ttu-id="18d9e-139">Users</span><span class="sxs-lookup"><span data-stu-id="18d9e-139">Users</span></span> | <span data-ttu-id="18d9e-140">Запуск вызовов API, например получения оповещений, связанных с пользователем, и устройств, связанных с пользователем.</span><span class="sxs-lookup"><span data-stu-id="18d9e-140">Run API calls such as get user-related alerts and user-related devices.</span></span>
<span data-ttu-id="18d9e-141">Оценка</span><span class="sxs-lookup"><span data-stu-id="18d9e-141">Score</span></span> | <span data-ttu-id="18d9e-142">Запустите вызовы API, такие как получить оценку экспозиции или получить безопасную оценку устройства.</span><span class="sxs-lookup"><span data-stu-id="18d9e-142">Run API calls such as get exposure score or get device secure score.</span></span>
<span data-ttu-id="18d9e-143">Программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="18d9e-143">Software</span></span> | <span data-ttu-id="18d9e-144">Запустите вызовы API, такие как уязвимости списка с помощью программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="18d9e-144">Run API calls such as list vulnerabilities by software.</span></span>
<span data-ttu-id="18d9e-145">Уязвимость</span><span class="sxs-lookup"><span data-stu-id="18d9e-145">Vulnerability</span></span> | <span data-ttu-id="18d9e-146">Запустите вызовы API, такие как устройства списка по уязвимости.</span><span class="sxs-lookup"><span data-stu-id="18d9e-146">Run API calls such as list devices by vulnerability.</span></span>
<span data-ttu-id="18d9e-147">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="18d9e-147">Recommendation</span></span> | <span data-ttu-id="18d9e-148">Запустите вызовы API, такие как Get recommendation by ID.</span><span class="sxs-lookup"><span data-stu-id="18d9e-148">Run API calls such as Get recommendation by ID.</span></span>

## <a name="see-also"></a><span data-ttu-id="18d9e-149">См. также</span><span class="sxs-lookup"><span data-stu-id="18d9e-149">See also</span></span>
- [<span data-ttu-id="18d9e-150">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="18d9e-150">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
