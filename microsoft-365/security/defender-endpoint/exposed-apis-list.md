---
title: Поддерживаемые API Microsoft Defender для конечной точки
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
ms.openlocfilehash: 656aa26d80db73bfc52511f9dd94e58e771f3ac6
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073839"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="4b441-104">Поддерживаемые API Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4b441-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4b441-105">**Применяется к:** [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4b441-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4b441-106">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="4b441-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4b441-107">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="4b441-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="4b441-108">URI конечной точки и версия</span><span class="sxs-lookup"><span data-stu-id="4b441-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="4b441-109">URI конечной точки</span><span class="sxs-lookup"><span data-stu-id="4b441-109">Endpoint URI</span></span>

> <span data-ttu-id="4b441-110">База служб URI: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4b441-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="4b441-111">На основе OData запросов имеется префикс "/api".</span><span class="sxs-lookup"><span data-stu-id="4b441-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="4b441-112">Например, для получения оповещений можно отправить запрос GET в [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="4b441-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="4b441-113">Управление версиями</span><span class="sxs-lookup"><span data-stu-id="4b441-113">Versioning</span></span>

> <span data-ttu-id="4b441-114">API поддерживает версию.</span><span class="sxs-lookup"><span data-stu-id="4b441-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="4b441-115">Текущая версия **— V1.0.**</span><span class="sxs-lookup"><span data-stu-id="4b441-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="4b441-116">Чтобы использовать определенную версию, используйте этот формат: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="4b441-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="4b441-117">Пример: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="4b441-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="4b441-118">Если вы не указываете версию (например, `https://api.securitycenter.microsoft.com/api/alerts` ) вы получите последнюю версию.</span><span class="sxs-lookup"><span data-stu-id="4b441-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="4b441-119">Дополнительные сведения об отдельных поддерживаемых сущностях, в которых можно запускать вызовы API, а также сведения, такие как значения запросов HTTP, заглавные заголовки запросов и ожидаемые ответы.</span><span class="sxs-lookup"><span data-stu-id="4b441-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4b441-120">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4b441-120">In this section</span></span>

<span data-ttu-id="4b441-121">Статья</span><span class="sxs-lookup"><span data-stu-id="4b441-121">Topic</span></span> | <span data-ttu-id="4b441-122">Описание</span><span class="sxs-lookup"><span data-stu-id="4b441-122">Description</span></span>
:---|:---
[<span data-ttu-id="4b441-123">Расширенная охота</span><span class="sxs-lookup"><span data-stu-id="4b441-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="4b441-124">Выполнение запросов из API.</span><span class="sxs-lookup"><span data-stu-id="4b441-124">Run queries from API.</span></span>
[<span data-ttu-id="4b441-125">Методы и свойства оповещений</span><span class="sxs-lookup"><span data-stu-id="4b441-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="4b441-126">Запустите вызовы API, такие как \- получения оповещений, создания оповещений, обновления оповещений и других.</span><span class="sxs-lookup"><span data-stu-id="4b441-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="4b441-127">Автоматизированные методы и свойства исследования</span><span class="sxs-lookup"><span data-stu-id="4b441-127">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="4b441-128">Запустите вызовы API, такие \- как сбор данных исследования.</span><span class="sxs-lookup"><span data-stu-id="4b441-128">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="4b441-129">Получать оповещения, связанные с доменом</span><span class="sxs-lookup"><span data-stu-id="4b441-129">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="4b441-130">Запустите вызовы API, такие как получить устройства, связанные с \- доменом, статистику домена и другие.</span><span class="sxs-lookup"><span data-stu-id="4b441-130">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="4b441-131">Методы и свойства файла</span><span class="sxs-lookup"><span data-stu-id="4b441-131">File methods and properties</span></span>](files.md) | <span data-ttu-id="4b441-132">Запустите вызовы API, такие как получения данных о файлах, связанных с файлами оповещений, устройств, связанных с \- файлами, и статистики файлов.</span><span class="sxs-lookup"><span data-stu-id="4b441-132">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="4b441-133">Методы и свойства индикаторов</span><span class="sxs-lookup"><span data-stu-id="4b441-133">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="4b441-134">Запустите вызов API, например \- получить индикаторы, создать индикатор и удалить Индикаторы.</span><span class="sxs-lookup"><span data-stu-id="4b441-134">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="4b441-135">Получать оповещения, связанные с протоколами IP</span><span class="sxs-lookup"><span data-stu-id="4b441-135">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="4b441-136">Запустите вызовы API, такие как получения оповещений, связанных с \- IP, и получения статистики IP.</span><span class="sxs-lookup"><span data-stu-id="4b441-136">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="4b441-137">Методы и свойства компьютера</span><span class="sxs-lookup"><span data-stu-id="4b441-137">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="4b441-138">Запустите вызовы API, такие как получить устройства, получить устройства по ID, сведения о в журнале \- пользователей, изменить теги и другие.</span><span class="sxs-lookup"><span data-stu-id="4b441-138">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="4b441-139">Методы и свойства действия компьютера</span><span class="sxs-lookup"><span data-stu-id="4b441-139">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="4b441-140">Запустите вызов API, например \- Isolation, запустите антивирусное сканирование и другие.</span><span class="sxs-lookup"><span data-stu-id="4b441-140">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="4b441-141">Методы и свойства рекомендаций</span><span class="sxs-lookup"><span data-stu-id="4b441-141">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="4b441-142">Запустите вызовы API, такие \- как получить рекомендации по ID.</span><span class="sxs-lookup"><span data-stu-id="4b441-142">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="4b441-143">Методы и свойства оценки</span><span class="sxs-lookup"><span data-stu-id="4b441-143">Score methods and properties</span></span>](score.md) | <span data-ttu-id="4b441-144">Запустите вызовы API, такие \- как получить оценку экспозиции или получить безопасную оценку устройства.</span><span class="sxs-lookup"><span data-stu-id="4b441-144">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="4b441-145">Методы и свойства программного обеспечения</span><span class="sxs-lookup"><span data-stu-id="4b441-145">Software methods and properties</span></span>](software.md) | <span data-ttu-id="4b441-146">Запустите вызовы API, такие \- как уязвимости списка с помощью программного обеспечения.</span><span class="sxs-lookup"><span data-stu-id="4b441-146">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="4b441-147">Методы пользователя</span><span class="sxs-lookup"><span data-stu-id="4b441-147">User methods</span></span>](user.md) | <span data-ttu-id="4b441-148">Запуск вызовов API, например получения оповещений, связанных с \- пользователем, и устройств, связанных с пользователем.</span><span class="sxs-lookup"><span data-stu-id="4b441-148">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="4b441-149">Методы и свойства уязвимости</span><span class="sxs-lookup"><span data-stu-id="4b441-149">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="4b441-150">Запустите вызовы API, такие как \- устройства списка по уязвимости.</span><span class="sxs-lookup"><span data-stu-id="4b441-150">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b441-151">См. также</span><span class="sxs-lookup"><span data-stu-id="4b441-151">See also</span></span>

- [<span data-ttu-id="4b441-152">Microsoft Defender для API конечных точек</span><span class="sxs-lookup"><span data-stu-id="4b441-152">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="4b441-153">Заметки о выпуске API для Защитника Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="4b441-153">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
