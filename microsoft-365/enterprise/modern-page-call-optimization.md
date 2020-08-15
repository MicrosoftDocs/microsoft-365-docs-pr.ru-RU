---
title: Оптимизация вызовов на современных и классических страницах сайтов публикации SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Узнайте, как оптимизировать современные и классические страницы сайтов публикации в SharePoint Online, ограничив число вызовов конечных точек служб SharePoint Online.
ms.openlocfilehash: b3c41dfe308f1546887f28cf0e8fbe9ab4dc2761
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693545"
---
# <a name="optimize-page-calls-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="bd121-103">Оптимизация вызовов на современных и классических страницах сайтов публикации SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bd121-103">Optimize page calls in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="bd121-104">Современные и классические страницы сайтов публикации SharePoint Online содержат ссылки, загружающие данные (или отправляющие вызовы) из компонентов SharePoint и CDN.</span><span class="sxs-lookup"><span data-stu-id="bd121-104">Both SharePoint Online modern and classic publishing sites contain links that load data from (or make calls to) SharePoint features and CDNs.</span></span> <span data-ttu-id="bd121-105">Чем больше вызовов выполняет страница, тем дольше страница загружается.</span><span class="sxs-lookup"><span data-stu-id="bd121-105">The more calls made by a page, the longer the page takes to load.</span></span> <span data-ttu-id="bd121-106">Это называется **задержкой, распознаваемой конечным пользователем,** или **EUPL**.</span><span class="sxs-lookup"><span data-stu-id="bd121-106">This is known as **end user perceived latency** or **EUPL**.</span></span>

<span data-ttu-id="bd121-107">С помощью этой статьи вы узнаете, как определить число и влияние вызовов на внешние конечные точки с современных и классических страниц сайтов публикации и как ограничить их влияние на задержку, распознаваемую конечным пользователем.</span><span class="sxs-lookup"><span data-stu-id="bd121-107">This article will help you understand how to determine the number and impact of calls to external endpoints from your modern and classic publishing site pages and how to limit their effect on end user perceived latency.</span></span>

>[!NOTE]
><span data-ttu-id="bd121-108">Дополнительные сведения о производительности на современных порталах SharePoint Online см. в статье [Производительность в современном интерфейсе SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="bd121-108">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-calls"></a><span data-ttu-id="bd121-109">Использование средства диагностики страниц SharePoint для анализа вызовов страниц</span><span class="sxs-lookup"><span data-stu-id="bd121-109">Use the Page Diagnostics for SharePoint tool to analyze page calls</span></span>

<span data-ttu-id="bd121-110">Средство "Диагностика страниц SharePoint" — это браузерное расширение для браузеров Chrome и новой версии Microsoft Edge (https://www.microsoft.com/edge), анализирующее страницы современных и классических сайтов публикаций SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bd121-110">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="bd121-111">Это средство предоставляет отчет о каждой проанализированной странице, показывающий, как она работает при заданных критериях производительности.</span><span class="sxs-lookup"><span data-stu-id="bd121-111">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="bd121-112">Чтобы установить и изучить средство диагностики страниц SharePoint, ознакомьтесь со статьей [Использование средства диагностики страниц SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="bd121-112">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="bd121-113">Средство диагностики страниц работает только в SharePoint Online, и его нельзя использовать на системной странице SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bd121-113">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="bd121-114">При анализе страницы сайта SharePoint с помощью средства диагностики страниц SharePoint вы можете просматривать сведения о внешних вызовах в результатах **Запросы к SharePoint** в панели _Диагностические тесты_.</span><span class="sxs-lookup"><span data-stu-id="bd121-114">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about external calls in the **Requests to SharePoint** result in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="bd121-115">Строка будет выделена зеленым цветом, если страница сайта содержит меньше вызовов, чем установленное базовое число, и красным цветом, если количество вызовов превышает базовое число.</span><span class="sxs-lookup"><span data-stu-id="bd121-115">The line will appear in green if the site page contains fewer than the baseline number of calls, and red if the page exceeds the baseline number.</span></span> <span data-ttu-id="bd121-116">Базовое число отличается для современных и классических страниц, так как классические страницы сайтов используют протокол HTTP 1.1, а современные страницы — HTTP 2.0:</span><span class="sxs-lookup"><span data-stu-id="bd121-116">The baseline number is different for modern and classic pages because classic site pages use HTTP1.1 and modern pages use HTTP2.0:</span></span>

- <span data-ttu-id="bd121-117">Современные страницы сайтов не должны содержать более **25** вызовов</span><span class="sxs-lookup"><span data-stu-id="bd121-117">Modern site pages should contain no more than **25** calls</span></span>
- <span data-ttu-id="bd121-118">Классические страницы публикации не должны содержать более **6** вызовов</span><span class="sxs-lookup"><span data-stu-id="bd121-118">Classic publishing pages should contain no more than **6** calls</span></span>

<span data-ttu-id="bd121-119">Возможные результаты:</span><span class="sxs-lookup"><span data-stu-id="bd121-119">Possible results include:</span></span>

- <span data-ttu-id="bd121-120">**Внимание!** (красный цвет). На странице превышено базовое число вызовов</span><span class="sxs-lookup"><span data-stu-id="bd121-120">**Attention required** (red): The page exceeds the baseline number of calls</span></span>
- <span data-ttu-id="bd121-121">**Действия не требуются** (зеленый цвет). Количество вызовов на странице не превышает базовое число</span><span class="sxs-lookup"><span data-stu-id="bd121-121">**No action required** (green): The page contains fewer than the baseline number of calls</span></span>

<span data-ttu-id="bd121-122">Если результат **Запросы к SharePoint** отображается в разделе **Внимание!**, вы можете щелкнуть его, чтобы просмотреть подробные сведения, включая общее число вызовов на странице и список URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="bd121-122">If the **Requests to SharePoint** result appears in the **Attention required** section, you can click the result for details, including the total number of calls on the page and a list of the URLs.</span></span>

![Результаты "Запросы к SharePoint"](../media/modern-portal-optimization/pagediag-requests.png)

## <a name="remediate-performance-issues-related-to-too-many-calls-on-a-page"></a><span data-ttu-id="bd121-124">Исправление проблем с производительностью, связанных со слишком большим числом вызовов на странице</span><span class="sxs-lookup"><span data-stu-id="bd121-124">Remediate performance issues related to too many calls on a page</span></span>

<span data-ttu-id="bd121-125">Если страница содержит слишком много вызовов, можно использовать список URL-адресов в результатах **Запросы к SharePoint**, чтобы определить, являются ли они повторными вызовами, вызовами, требующими пакетной обработки, или вызовами, возвращающими данные, которые следует кэшировать.</span><span class="sxs-lookup"><span data-stu-id="bd121-125">If a page contains too many calls, you can use the list of URLs in the **Requests to Sharepoint** results to determine whether there are any repeated calls, calls that should be batched, or calls that return data that should be cached.</span></span>

<span data-ttu-id="bd121-126">**Пакетная обработка вызовов REST** может снизить нагрузку при работе.</span><span class="sxs-lookup"><span data-stu-id="bd121-126">**Batching REST calls** can help to reduce performance overhead.</span></span> <span data-ttu-id="bd121-127">Дополнительные сведения о пакетной обработке вызовов API см. в статье [Отправка пакетных запросов с использованием REST API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span><span class="sxs-lookup"><span data-stu-id="bd121-127">For more information about API call batching, see [Make batch requests with the REST APIs](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span></span>

<span data-ttu-id="bd121-128">**Использование кэша** для хранения результатов вызова API может повысить производительность подготовленного запроса, разрешая клиенту использовать кэшированные данные вместо создания дополнительного вызова для каждой последующей загрузки страницы.</span><span class="sxs-lookup"><span data-stu-id="bd121-128">**Using a cache** to store the results of an API call can improve the performance of a warm request by allowing the client to use the cached data instead of making an additional call for each subsequent page load.</span></span> <span data-ttu-id="bd121-129">Это решение можно использовать различными способами в зависимости от требований организации.</span><span class="sxs-lookup"><span data-stu-id="bd121-129">There are multiple ways to approach this solution depending on the business requirement.</span></span> <span data-ttu-id="bd121-130">Как правило, если данные одинаковы для всех пользователей, использование службы кэширования среднего уровня, например [кэша _Azure Redis_](https://azure.microsoft.com/services/cache/), является отличным способом значительно сократить трафик API на сайте, так как пользователи будут запрашивать данные из службы кэширования, а не напрямую из SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bd121-130">Typically if the data will be the same for all users, using a middle-tier caching service like [_Azure Redis_ cache](https://azure.microsoft.com/services/cache/) is a great option to significantly reduce API traffic against a site, as the users would request the data from the caching service instead of directly from SPO.</span></span> <span data-ttu-id="bd121-131">Единственными обязательными вызовами SharePoint Online будут обновления кэша среднего уровня.</span><span class="sxs-lookup"><span data-stu-id="bd121-131">The only SPO calls needed would be to refresh the middle-tier's cache.</span></span> <span data-ttu-id="bd121-132">Если данные для отдельных пользователей отличаются, возможно, наилучшим решением будет реализовать кэширование на стороне клиента, например с помощью хранилища LocalStorage или даже файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="bd121-132">If the data will fluctuate on an individual user basis, it may be best to implement a client side cache, like LocalStorage or even a Cookie.</span></span> <span data-ttu-id="bd121-133">Это позволит сократить количество вызовов, устранив последующие запросы, выполняемые одним пользователем, пока существует кэш, но это будет менее эффективно, чем специальная служба кэширования.</span><span class="sxs-lookup"><span data-stu-id="bd121-133">This will still reduce call volumes by eliminating subsequent requests made by the same user for the cache duration, but will be less efficient than a dedicated caching service.</span></span> <span data-ttu-id="bd121-134">Служба PnP позволяет использовать хранилище LocalStorage с небольшой доработкой.</span><span class="sxs-lookup"><span data-stu-id="bd121-134">PnP allows you to use LocalStorage with little additional development required.</span></span>

<span data-ttu-id="bd121-135">Перед внесением изменений в страницы для исправления проблем с производительностью запомните время загрузки страницы в результатах анализа.</span><span class="sxs-lookup"><span data-stu-id="bd121-135">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="bd121-136">Снова запустите средство после внесения изменений, чтобы узнать, соответствует ли новый результат базовому стандарту, и проверить, сократилось ли время загрузки.</span><span class="sxs-lookup"><span data-stu-id="bd121-136">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Анализ времени загрузки страницы](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="bd121-138">Время загрузки страницы зависит от множества факторов, например от загрузки сети, времени суток и других переменных условий.</span><span class="sxs-lookup"><span data-stu-id="bd121-138">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="bd121-139">Следует несколько раз проверить время загрузки страницы до и после внесения изменений, чтобы получить среднестатистические данные.</span><span class="sxs-lookup"><span data-stu-id="bd121-139">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bd121-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bd121-140">Related topics</span></span>

[<span data-ttu-id="bd121-141">Настройка производительности SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bd121-141">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="bd121-142">Настройка производительности Office 365</span><span class="sxs-lookup"><span data-stu-id="bd121-142">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="bd121-143">Производительность в современном интерфейсе SharePoint</span><span class="sxs-lookup"><span data-stu-id="bd121-143">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="bd121-144">Сети доставки содержимого</span><span class="sxs-lookup"><span data-stu-id="bd121-144">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="bd121-145">Использование сети доставки содержимого Office 365 с SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bd121-145">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
