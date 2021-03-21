---
title: Параметры навигации для SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: В этой статье описываются сайты вариантов навигации с поддержкой SharePoint Publishing в SharePoint Online.
ms.openlocfilehash: b5989bf26ebf7bb1452f983af89a6e6739821d53
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923628"
---
# <a name="navigation-options-for-sharepoint-online"></a><span data-ttu-id="8119b-103">Параметры навигации для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8119b-103">Navigation options for SharePoint Online</span></span>

<span data-ttu-id="8119b-104">В этой статье описываются сайты вариантов навигации с поддержкой SharePoint Publishing в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8119b-104">This article describes navigation options sites with SharePoint Publishing enabled in SharePoint Online.</span></span> <span data-ttu-id="8119b-105">Выбор и конфигурация навигации существенно влияют на производительность и масштабируемость сайтов в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8119b-105">The choice and configuration of navigation significantly impacts the performance and scalability of sites in SharePoint Online.</span></span> <span data-ttu-id="8119b-106">Шаблон сайта SharePoint Publishing следует использовать только в том случае, если это необходимо для централизованного портала, а функция публикации должна быть включена только на определенных сайтах и только в том случае, если это абсолютно необходимо, так как это может повлиять на производительность при неправильном использования.</span><span class="sxs-lookup"><span data-stu-id="8119b-106">The SharePoint Publishing site template should only be used if required for a centralized portal and the publishing feature should only be enabled on specific sites and only when absolutely required as it can impact performance when used incorrectly.</span></span>

>[!NOTE]
><span data-ttu-id="8119b-107">Если вы используете современные параметры навигации SharePoint, такие как мега-меню, каскадная навигация или навигация в концентраторах, эта статья не применяется к вашему сайту.</span><span class="sxs-lookup"><span data-stu-id="8119b-107">If you're using modern SharePoint navigation options like mega menu, cascading navigation, or hub navigation, this article does not apply to your site.</span></span> <span data-ttu-id="8119b-108">Современные архитектуры сайтов SharePoint используют более уплощенную иерархию сайтов и модель с использованием концентраторов и спичек.</span><span class="sxs-lookup"><span data-stu-id="8119b-108">Modern SharePoint site architectures leverage a more flattened site hierarchy and a hub-and-spoke model.</span></span> <span data-ttu-id="8119b-109">Это позволяет достичь многих сценариев, не требующих использования функции Публикации SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8119b-109">This allows many scenarios to be achieved that do NOT require use of the SharePoint Publishing feature.</span></span>

## <a name="overview-of-navigation-options"></a><span data-ttu-id="8119b-110">Обзор параметров навигации</span><span class="sxs-lookup"><span data-stu-id="8119b-110">Overview of navigation options</span></span>

<span data-ttu-id="8119b-111">Конфигурация поставщика навигации может существенно повлиять на производительность для всего сайта, и необходимо тщательно рассмотреть выбор поставщика навигации и конфигурации, которая эффективно масштабирования для требований сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8119b-111">Navigation provider configuration can significantly impact performance for the entire site, and careful consideration must be taken to pick a navigation provider and configuration that scales effectively for the requirements of a SharePoint site.</span></span> <span data-ttu-id="8119b-112">Существует два поставщика навигации, а также настраиваемые реализации навигации.</span><span class="sxs-lookup"><span data-stu-id="8119b-112">There are two out-of-the-box navigation providers, as well as custom navigation implementations.</span></span>

<span data-ttu-id="8119b-113">Первый вариант— [**структурная**](#using-structural-navigation-in-sharepoint-online)навигация — это рекомендуемый вариант навигации в SharePoint Online для классических сайтов Sharepoint, если включить структурную навигационную кэшинг **для вашего сайта.**</span><span class="sxs-lookup"><span data-stu-id="8119b-113">The first option, [**Structural navigation**](#using-structural-navigation-in-sharepoint-online), is the recommended navigation option in SharePoint Online for classic Sharepoint sites, **if you turn on structural navigation caching for your site**.</span></span> <span data-ttu-id="8119b-114">Этот поставщик навигации отображает элементы навигации ниже текущего сайта, а также необязательно текущего сайта и его братьев и сестер.</span><span class="sxs-lookup"><span data-stu-id="8119b-114">This navigation provider displays the navigation items below the current site, and optionally the current site and its siblings.</span></span> <span data-ttu-id="8119b-115">Он предоставляет дополнительные возможности, такие как обрезка безопасности и переумежение структуры сайта.</span><span class="sxs-lookup"><span data-stu-id="8119b-115">It provides additional capabilities such as security trimming and site structure enumeration.</span></span> <span data-ttu-id="8119b-116">Если кэширование отключено, это отрицательно скажется на производительности и масштабируемости и может быть подвержено регулирование.</span><span class="sxs-lookup"><span data-stu-id="8119b-116">If caching is disabled, this will negatively impact performance and scalability, and may be subject to throttling.</span></span>

<span data-ttu-id="8119b-117">Второй вариант — [**навигация управляемых (метаданных)**](#using-managed-navigation-and-metadata-in-sharepoint-online)— представляет элементы навигации с помощью набора терминов Управляемые метаданные.</span><span class="sxs-lookup"><span data-stu-id="8119b-117">The second option, [**Managed (Metadata) navigation**](#using-managed-navigation-and-metadata-in-sharepoint-online), represents navigation items using a Managed Metadata term set.</span></span> <span data-ttu-id="8119b-118">Мы рекомендуем отключить обрезку безопасности, если это не требуется.</span><span class="sxs-lookup"><span data-stu-id="8119b-118">We recommend that security trimming be disabled unless required.</span></span> <span data-ttu-id="8119b-119">Обрезка безопасности включена в качестве параметра безопасности по умолчанию для этого поставщика навигации; однако многие сайты не требуют накладных расходов на обрезку безопасности, так как элементы навигации часто являются последовательными для всех пользователей сайта.</span><span class="sxs-lookup"><span data-stu-id="8119b-119">Security trimming is enabled as a secure-by-default setting for this navigation provider; however, many sites do not require the overhead of security trimming since navigation elements often are consistent for all users of the site.</span></span> <span data-ttu-id="8119b-120">При рекомендуемой конфигурации для отключения обрезки безопасности этот поставщик навигации не требует переоформить структуру сайта и имеет высокую масштабируемость с приемлемым влиянием на производительность.</span><span class="sxs-lookup"><span data-stu-id="8119b-120">With the recommended configuration to disable security trimming, this navigation provider does not require enumerating site structure and is highly scalable with acceptable performance impact.</span></span>

<span data-ttu-id="8119b-121">Помимо поставщиков нестандартной навигации многие клиенты успешно реализовали альтернативные пользовательские реализации навигации.</span><span class="sxs-lookup"><span data-stu-id="8119b-121">In addition to the out-of-the-box navigation providers, many customers have successfully implemented alternative custom navigation implementations.</span></span> <span data-ttu-id="8119b-122">В [этой статье см.](#using-search-driven-client-side-scripting) сценарий с клиентской стороной поиска.</span><span class="sxs-lookup"><span data-stu-id="8119b-122">See [Search-driven client-side scripting](#using-search-driven-client-side-scripting) in this article.</span></span>
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a><span data-ttu-id="8119b-123">Плюсы и минусы параметров навигации SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8119b-123">Pros and Cons of SharePoint Online navigation options</span></span>

<span data-ttu-id="8119b-124">В следующей таблице подводятся доводы "за" и "против" каждого варианта.</span><span class="sxs-lookup"><span data-stu-id="8119b-124">The following table summarizes the pros and cons of each option.</span></span>

|<span data-ttu-id="8119b-125">Структурная навигация</span><span class="sxs-lookup"><span data-stu-id="8119b-125">Structural navigation</span></span>  |<span data-ttu-id="8119b-126">Управляемая навигация</span><span class="sxs-lookup"><span data-stu-id="8119b-126">Managed navigation</span></span>  |<span data-ttu-id="8119b-127">Навигация на основе поиска</span><span class="sxs-lookup"><span data-stu-id="8119b-127">Search-driven navigation</span></span>  |<span data-ttu-id="8119b-128">Поставщик настраиваемой навигации</span><span class="sxs-lookup"><span data-stu-id="8119b-128">Custom-navigation provider</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="8119b-129">Плюсы:</span><span class="sxs-lookup"><span data-stu-id="8119b-129">Pros:</span></span><br/><br/><span data-ttu-id="8119b-130">Простой в обслуживании</span><span class="sxs-lookup"><span data-stu-id="8119b-130">Easy to maintain</span></span><br/><span data-ttu-id="8119b-131">Безопасность обрезана</span><span class="sxs-lookup"><span data-stu-id="8119b-131">Security trimmed</span></span><br/><span data-ttu-id="8119b-132">Автоматически обновляется в течение 24 часов после изменения контента</span><span class="sxs-lookup"><span data-stu-id="8119b-132">Automatically updates within 24 hours when content is changed</span></span><br/>     |<span data-ttu-id="8119b-133">Плюсы:</span><span class="sxs-lookup"><span data-stu-id="8119b-133">Pros:</span></span><br/><br/><span data-ttu-id="8119b-134">Простой в обслуживании</span><span class="sxs-lookup"><span data-stu-id="8119b-134">Easy to maintain</span></span><br/>|<span data-ttu-id="8119b-135">Плюсы:</span><span class="sxs-lookup"><span data-stu-id="8119b-135">Pros:</span></span><br/><br/><span data-ttu-id="8119b-136">Безопасность обрезана</span><span class="sxs-lookup"><span data-stu-id="8119b-136">Security trimmed</span></span><br/><span data-ttu-id="8119b-137">Автоматически обновляется при добавлении сайтов</span><span class="sxs-lookup"><span data-stu-id="8119b-137">Automatically updates as sites are added</span></span><br/><span data-ttu-id="8119b-138">Быстрая загрузка времени и локально кэшировать структуру навигации</span><span class="sxs-lookup"><span data-stu-id="8119b-138">Fast loading time and locally cached navigation structure</span></span><br/>|<span data-ttu-id="8119b-139">Плюсы:</span><span class="sxs-lookup"><span data-stu-id="8119b-139">Pros:</span></span><br/><br/><span data-ttu-id="8119b-140">Более широкий выбор доступных вариантов</span><span class="sxs-lookup"><span data-stu-id="8119b-140">Wider choice of options available</span></span><br/><span data-ttu-id="8119b-141">Быстрая загрузка при правильном кэшинге</span><span class="sxs-lookup"><span data-stu-id="8119b-141">Fast loading when caching is used correctly</span></span><br/><span data-ttu-id="8119b-142">Многие параметры хорошо работают с адаптивной конструкцией страницы</span><span class="sxs-lookup"><span data-stu-id="8119b-142">Many options work well with responsive page design</span></span><br/>|
|<span data-ttu-id="8119b-143">Минусы:</span><span class="sxs-lookup"><span data-stu-id="8119b-143">Cons:</span></span><br/><br/><span data-ttu-id="8119b-144">**Влияет на производительность при отключении кэшинга**</span><span class="sxs-lookup"><span data-stu-id="8119b-144">**Impacts performance if caching is disabled**</span></span><br/><span data-ttu-id="8119b-145">При условии регулирования</span><span class="sxs-lookup"><span data-stu-id="8119b-145">Subject to throttling</span></span><br/>|<span data-ttu-id="8119b-146">Минусы:</span><span class="sxs-lookup"><span data-stu-id="8119b-146">Cons:</span></span><br/><br/><span data-ttu-id="8119b-147">Не обновляется автоматически для отражения структуры сайта</span><span class="sxs-lookup"><span data-stu-id="8119b-147">Not automatically updated to reflect site structure</span></span><br/><span data-ttu-id="8119b-148">**Влияет на производительность, если** включена обрезка безопасности или сложная структура навигации</span><span class="sxs-lookup"><span data-stu-id="8119b-148">**Impacts performance if security trimming is enabled** or when navigation structure is complex</span></span><br/>|<span data-ttu-id="8119b-149">Минусы:</span><span class="sxs-lookup"><span data-stu-id="8119b-149">Cons:</span></span><br/><br/><span data-ttu-id="8119b-150">Нет возможности легко заказать сайты</span><span class="sxs-lookup"><span data-stu-id="8119b-150">No ability to easily order sites</span></span><br/><span data-ttu-id="8119b-151">Требуется настройка мастер-страницы (необходимые технические навыки)</span><span class="sxs-lookup"><span data-stu-id="8119b-151">Requires customization of the master page (technical skills required)</span></span><br/>|<span data-ttu-id="8119b-152">Минусы:</span><span class="sxs-lookup"><span data-stu-id="8119b-152">Cons:</span></span><br/><br/><span data-ttu-id="8119b-153">Требуется настраиваемая разработка</span><span class="sxs-lookup"><span data-stu-id="8119b-153">Custom development is required</span></span><br/><span data-ttu-id="8119b-154">Необходимы внешние источники данных и кэш, хранимые, например Azure</span><span class="sxs-lookup"><span data-stu-id="8119b-154">External data source / cache stored is needed e.g. Azure</span></span><br/>|

<span data-ttu-id="8119b-155">Наиболее подходящий вариант для сайта зависит от требований к сайту и от технических возможностей.</span><span class="sxs-lookup"><span data-stu-id="8119b-155">The most appropriate option for your site will depend on your site requirements and on your technical capability.</span></span> <span data-ttu-id="8119b-156">Если вам нужен простой в настройке поставщик навигации, который автоматически обновляется [](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) при смене контента, то структурная навигация с включенной кэшированием — это хороший вариант.</span><span class="sxs-lookup"><span data-stu-id="8119b-156">If you want an easy-to-configure navigation provider that automatically updates when content is changed, then structural navigation [with caching enabled](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) is a good option.</span></span>

>[!NOTE]
><span data-ttu-id="8119b-157">Применение того же принципа, что и современные сайты SharePoint, упрощая общую структуру сайта в более лестную, не иерархическую структуру, повышает производительность и упрощает переход на современные сайты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8119b-157">Applying the same principle as modern SharePoint sites by simplifying the overall site structure to a flatter, non-hierarchical structure improves performance and simplifies moving to modern SharePoint sites.</span></span> <span data-ttu-id="8119b-158">Это означает, что вместо одной коллекции сайтов с сотнями сайтов (subwebs) лучше использовать множество коллекций сайтов с очень немногими подвидами (subwebs).</span><span class="sxs-lookup"><span data-stu-id="8119b-158">What this means is that instead of having a single site collection with hundreds of sites (subwebs), a better approach is to have many site collections with very few subsites (subwebs).</span></span>

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a><span data-ttu-id="8119b-159">Анализ производительности навигации в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8119b-159">Analyzing navigation performance in SharePoint Online</span></span>

<span data-ttu-id="8119b-160">Средство [Page Diagnostics for SharePoint](./page-diagnostics-for-spo.md) — это расширение браузера для браузеров Microsoft Edge и Chrome, которое анализирует современный портал SharePoint Online и классические страницы сайтов публикации.</span><span class="sxs-lookup"><span data-stu-id="8119b-160">The [Page Diagnostics for SharePoint tool](./page-diagnostics-for-spo.md) is a browser extension for Microsoft Edge and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="8119b-161">Этот инструмент работает только для SharePoint Online и не может использоваться на странице системы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8119b-161">This tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="8119b-162">Средство создает отчет для каждой анализируемой страницы с указанием того, как страница выполняется в отношении заранее определенного набора правил, и отображает подробные сведения, когда результаты теста выпадают за пределы базового значения.</span><span class="sxs-lookup"><span data-stu-id="8119b-162">The tool generates a report for each analyzed page showing how the page performs against a pre-defined set of rules and displays detailed information when results for a test fall outside the baseline value.</span></span> <span data-ttu-id="8119b-163">Администраторы и дизайнеры SharePoint Online могут использовать этот инструмент для устранения проблем с производительностью, чтобы обеспечить оптимизацию новых страниц до публикации.</span><span class="sxs-lookup"><span data-stu-id="8119b-163">SharePoint Online administrators and designers can use the tool to troubleshoot performance issues to ensure that new pages are optimized prior to publishing.</span></span>

<span data-ttu-id="8119b-164">**SPRequestDuration** — это время, необходимое SharePoint для обработки страницы.</span><span class="sxs-lookup"><span data-stu-id="8119b-164">**SPRequestDuration** in particular is the time it takes for SharePoint to process the page.</span></span> <span data-ttu-id="8119b-165">Тяжелая навигация (например, в том числе страницы в навигации), сложные иерархии сайтов и другие параметры конфигурации и топологии могут значительно способствовать более длительным срокам.</span><span class="sxs-lookup"><span data-stu-id="8119b-165">Heavy navigation (like including pages in navigation), complex site hierarchies, and other configuration and topology options can all dramatically contribute to longer durations.</span></span>

## <a name="using-structural-navigation-in-sharepoint-online"></a><span data-ttu-id="8119b-166">Использование структурной навигации в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8119b-166">Using structural navigation in SharePoint Online</span></span>

<span data-ttu-id="8119b-167">Это навигация, используемая по умолчанию, и является самым простым решением.</span><span class="sxs-lookup"><span data-stu-id="8119b-167">This is the out-of-the-box navigation used by default and is the most straightforward solution.</span></span> <span data-ttu-id="8119b-168">Она не требует настройки, и не технический пользователь может легко добавлять элементы, скрывать элементы и управлять навигацией со страницы параметров.</span><span class="sxs-lookup"><span data-stu-id="8119b-168">It does not require any customization and a non-technical user can also easily add items, hide items, and manage the navigation from the settings page.</span></span> <span data-ttu-id="8119b-169">Рекомендуется [включить кэшинг,](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)в противном случае существует дорогостоящая компромиссная производительность.</span><span class="sxs-lookup"><span data-stu-id="8119b-169">We recommend [enabling caching](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), otherwise there is an expensive performance trade-off.</span></span>

### <a name="how-to-implement-structural-navigation-caching"></a><span data-ttu-id="8119b-170">Реализация структурного кэшинга навигации</span><span class="sxs-lookup"><span data-stu-id="8119b-170">How to implement structural navigation caching</span></span>

<span data-ttu-id="8119b-171">В **статье Параметры сайта** Look and Feel Navigation можно проверить, выбрана ли структурная навигация для глобальной навигации или текущей  >    >  навигации.</span><span class="sxs-lookup"><span data-stu-id="8119b-171">Under **Site Settings** > **Look and Feel** > **Navigation**, you can validate if structural navigation is selected for either global navigation or current navigation.</span></span> <span data-ttu-id="8119b-172">Выбор страниц **Show отрицательно** скажется на производительности.</span><span class="sxs-lookup"><span data-stu-id="8119b-172">Selecting **Show pages** will have negative impact on performance.</span></span>

![Структурная навигация с выбранными подвидами Show](../media/SPONavOptionsStructuredShowSubsites.png)

<span data-ttu-id="8119b-174">Кэшинг может быть включен или отключен на уровне коллекции сайтов и на уровне сайта, и включен для обоих по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8119b-174">Caching can be enabled or disabled at the site collection level and at the site level, and is enabled for both by default.</span></span> <span data-ttu-id="8119b-175">Чтобы включить на уровне коллекции веб-сайтов, в статье **Параметры** веб-сайтов Администрирование коллекций веб-сайтов навигации, проверьте поле  >    >  для **включить кэшировать**.</span><span class="sxs-lookup"><span data-stu-id="8119b-175">To enable at the site collection level, under **Site Settings** > **Site Collection Administration** > **Site Collection Navigation**, check the box for **Enable caching**.</span></span>

![Включить кэшинг на уровне сайта](../media/structural-nav/structural-nav-caching-site-coll.png)

<span data-ttu-id="8119b-177">Чтобы включить на уровне сайта, в **статье Параметры** сайта  >  **навигации,** проверьте поле для **включить кэшировать**.</span><span class="sxs-lookup"><span data-stu-id="8119b-177">To enable at the site level, under **Site Settings** > **Navigation**, check the box for **Enable caching**.</span></span>

![Включить кэшинг на уровне сайта](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a><span data-ttu-id="8119b-179">Использование управляемой навигации и метаданных в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8119b-179">Using managed navigation and metadata in SharePoint Online</span></span>

<span data-ttu-id="8119b-180">Управление навигацией — это еще один вариант, который можно использовать для воссоздания большей части функций, что и структурная навигация.</span><span class="sxs-lookup"><span data-stu-id="8119b-180">Managed navigation is another out-of-the-box option that you can use to recreate most of the same functionality as structural navigation.</span></span> <span data-ttu-id="8119b-181">Управляемые метаданные можно настроить для включения или отключения обрезки безопасности.</span><span class="sxs-lookup"><span data-stu-id="8119b-181">Managed metadata can be configured to have security trimming enabled or disabled.</span></span> <span data-ttu-id="8119b-182">При настройке с отключенной обрезкой безопасности управление навигацией достаточно эффективно, так как загружает все ссылки навигации с постоянным количеством вызовов сервера.</span><span class="sxs-lookup"><span data-stu-id="8119b-182">When configured with security trimming disabled, managed navigation is fairly efficient as it loads all the navigation links with a constant number of server calls.</span></span> <span data-ttu-id="8119b-183">Включение обрезки безопасности, однако, отменяет некоторые преимущества управляемой навигации.</span><span class="sxs-lookup"><span data-stu-id="8119b-183">Enabling security trimming, however, negates some of the performance advantages of managed navigation.</span></span>

<span data-ttu-id="8119b-184">Если необходимо включить обрезку безопасности, рекомендуем:</span><span class="sxs-lookup"><span data-stu-id="8119b-184">If you need to enable security trimming, we recommend that you:</span></span>

- <span data-ttu-id="8119b-185">Обновление всех дружественных ссылок URL-адресов на простые ссылки</span><span class="sxs-lookup"><span data-stu-id="8119b-185">Update all friendly URL links to simple links</span></span>
- <span data-ttu-id="8119b-186">Добавление необходимых узлов обрезки безопасности в качестве дружественных URL-адресов</span><span class="sxs-lookup"><span data-stu-id="8119b-186">Add required security trimming nodes as friendly URLs</span></span>
- <span data-ttu-id="8119b-187">Ограничение количества элементов навигации не более 100 и не более 3 уровней глубиной</span><span class="sxs-lookup"><span data-stu-id="8119b-187">Limit the number of navigation items to no more than 100 and no more than 3 levels deep</span></span>

<span data-ttu-id="8119b-188">Многие сайты не требуют обрезки безопасности, так как структура навигации часто согласуется для всех пользователей сайта.</span><span class="sxs-lookup"><span data-stu-id="8119b-188">Many sites do not require security trimming, as the navigation structure is often consistent for all users of the site.</span></span> <span data-ttu-id="8119b-189">Если обрезка безопасности отключена и в навигацию добавляется ссылка, доступ к которую имеют не все пользователи, ссылка будет по-прежнему показываться, но приведет к отказу в доступе.</span><span class="sxs-lookup"><span data-stu-id="8119b-189">If security trimming is disabled and a link is added to navigation that not all users have access to, the link will still show but will lead to an access denied message.</span></span> <span data-ttu-id="8119b-190">Нет риска случайного доступа к содержимому.</span><span class="sxs-lookup"><span data-stu-id="8119b-190">There is no risk of inadvertent access to the content.</span></span>

### <a name="how-to-implement-managed-navigation-and-the-results"></a><span data-ttu-id="8119b-191">Реализация управляемой навигации и результатов</span><span class="sxs-lookup"><span data-stu-id="8119b-191">How to implement managed navigation and the results</span></span>

<span data-ttu-id="8119b-192">Существует несколько статей по docs.microsoft.com сведения об управляемой навигации.</span><span class="sxs-lookup"><span data-stu-id="8119b-192">There are several articles on docs.microsoft.com about the details of managed navigation.</span></span> <span data-ttu-id="8119b-193">Например, см. [обзор управляемой навигации в SharePoint Server.](/sharepoint/administration/overview-of-managed-navigation)</span><span class="sxs-lookup"><span data-stu-id="8119b-193">For example, see [Overview of managed navigation in SharePoint Server](/sharepoint/administration/overview-of-managed-navigation).</span></span>

<span data-ttu-id="8119b-194">Для реализации управляемой навигации необходимо настроить термины с URL-адресами, соответствующими структуре навигации сайта.</span><span class="sxs-lookup"><span data-stu-id="8119b-194">In order to implement managed navigation, you set up terms with URLs corresponding to the navigation structure of the site.</span></span> <span data-ttu-id="8119b-195">Управляемые навигации можно даже вручную курировать, чтобы заменить структурную навигацию во многих случаях.</span><span class="sxs-lookup"><span data-stu-id="8119b-195">Managed navigation can even be manually curated to replace structural navigation in many cases.</span></span> <span data-ttu-id="8119b-196">Например:</span><span class="sxs-lookup"><span data-stu-id="8119b-196">For example:</span></span>

![Структура сайта SharePoint Online](../media/SPONavOptionsListOfSites.png)<span data-ttu-id="8119b-198">)</span><span class="sxs-lookup"><span data-stu-id="8119b-198">)</span></span>

## <a name="using-search-driven-client-side-scripting"></a><span data-ttu-id="8119b-199">Использование клиентского сценария на основе поиска</span><span class="sxs-lookup"><span data-stu-id="8119b-199">Using Search-driven client-side scripting</span></span>

<span data-ttu-id="8119b-200">Один распространенный класс пользовательских реализации навигации охватывает клиентские шаблоны проектирования, хранимые локальный кэш узлов навигации.</span><span class="sxs-lookup"><span data-stu-id="8119b-200">One common class of custom navigation implementations embraces client-rendered design patterns that store a local cache of navigation nodes.</span></span>

<span data-ttu-id="8119b-201">Эти поставщики навигации имеют несколько ключевых преимуществ:</span><span class="sxs-lookup"><span data-stu-id="8119b-201">These navigation providers have a couple of key advantages:</span></span>

- <span data-ttu-id="8119b-202">Как правило, они хорошо работают с отзывчивыми проектами страниц.</span><span class="sxs-lookup"><span data-stu-id="8119b-202">They generally work well with responsive page designs.</span></span>
- <span data-ttu-id="8119b-203">Они чрезвычайно масштабируемы и исполняемы, так как они могут отрисовки без затрат ресурсов (и обновления в фоновом режиме после разового времени).</span><span class="sxs-lookup"><span data-stu-id="8119b-203">They are extremely scalable and performant because they can render with no resource cost (and refresh in the background after a timeout).</span></span>
- <span data-ttu-id="8119b-204">Эти поставщики навигации могут получать данные навигации с помощью различных стратегий, от простых статических конфигураций до различных динамических поставщиков данных.</span><span class="sxs-lookup"><span data-stu-id="8119b-204">These navigation providers can retrieve navigation data using various strategies, ranging from simple static configurations to various dynamic data providers.</span></span>

<span data-ttu-id="8119b-205">Примером поставщика данных является использование навигации, управляемой поиском, которая позволяет гибко скомпрометировать узлы навигации и эффективно обрабатывать обрезку безопасности.</span><span class="sxs-lookup"><span data-stu-id="8119b-205">An example of a data provider is to use a **Search-driven navigation**, which allows flexibility for enumerating navigation nodes and handling security trimming efficiently.</span></span>

<span data-ttu-id="8119b-206">Существуют и другие популярные варианты создания **настраиваемого поставщика навигации.**</span><span class="sxs-lookup"><span data-stu-id="8119b-206">There are other popular options to build **Custom navigation providers**.</span></span> <span data-ttu-id="8119b-207">Просмотрите [решения навигации для порталов SharePoint Online,](/sharepoint/dev/solution-guidance/portal-navigation) чтобы получить дополнительные рекомендации по построению пользовательского поставщика навигации.</span><span class="sxs-lookup"><span data-stu-id="8119b-207">Please review [Navigation solutions for SharePoint Online portals](/sharepoint/dev/solution-guidance/portal-navigation) for further guidance on building a Custom navigation provider.</span></span>

<span data-ttu-id="8119b-208">С помощью поиска можно использовать индексы, встроенные в фоновом режиме, с помощью непрерывного обхода.</span><span class="sxs-lookup"><span data-stu-id="8119b-208">Using search you can leverage the indexes that are built up in the background using continuous crawl.</span></span> <span data-ttu-id="8119b-209">Результаты поиска извлекаются из индекса поиска, а результаты подрезаются.</span><span class="sxs-lookup"><span data-stu-id="8119b-209">The search results are pulled from the search index and the results are security-trimmed.</span></span> <span data-ttu-id="8119b-210">Обычно это происходит быстрее, чем у поставщиков навигации из-за необходимости обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="8119b-210">This is generally faster than out-of-the-box navigation providers when security trimming is required.</span></span> <span data-ttu-id="8119b-211">Использование поиска для структурной навигации, особенно если у вас сложная структура сайта, значительно ускорит время загрузки страницы.</span><span class="sxs-lookup"><span data-stu-id="8119b-211">Using search for structural navigation, especially if you have a complex site structure, will speed up page loading time considerably.</span></span> <span data-ttu-id="8119b-212">Основное преимущество этого перед управляемой навигацией заключается в том, что вы извлекаем пользу из обрезки безопасности.</span><span class="sxs-lookup"><span data-stu-id="8119b-212">The main advantage of this over managed navigation is that you benefit from security trimming.</span></span>

<span data-ttu-id="8119b-213">Этот подход предполагает создание настраиваемой мастер-страницы и замену нестандартного кода навигации на пользовательский HTML.</span><span class="sxs-lookup"><span data-stu-id="8119b-213">This approach involves creating a custom master page and replacing the out-of-the-box navigation code with custom HTML.</span></span> <span data-ttu-id="8119b-214">Следуйте этой процедуре, описанной в следующем примере, чтобы заменить код навигации в `seattle.html` файле.</span><span class="sxs-lookup"><span data-stu-id="8119b-214">Follow this procedure outlined in the following example to replace the navigation code in the file `seattle.html`.</span></span> <span data-ttu-id="8119b-215">В этом примере вы откроете файл и замените весь элемент `seattle.html` `id="DeltaTopNavigation"` пользовательским HTML-кодом.</span><span class="sxs-lookup"><span data-stu-id="8119b-215">In this example, you will open the `seattle.html` file and replace the whole element `id="DeltaTopNavigation"` with custom HTML code.</span></span>

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a><span data-ttu-id="8119b-216">Пример: Замена кода навигации из окна на мастер-странице</span><span class="sxs-lookup"><span data-stu-id="8119b-216">Example: Replace the out-of-the-box navigation code in a master page</span></span>

1. <span data-ttu-id="8119b-217">Перейдите на страницу Параметры сайта.</span><span class="sxs-lookup"><span data-stu-id="8119b-217">Navigate to the Site Settings page.</span></span>
2. <span data-ttu-id="8119b-218">Откройте галерею мастер-страниц, нажав **мастер-страницы.**</span><span class="sxs-lookup"><span data-stu-id="8119b-218">Open the master page gallery by clicking **Master Pages**.</span></span>
3. <span data-ttu-id="8119b-219">Здесь вы можете перемещаться по библиотеке и скачивать `seattle.master` файл.</span><span class="sxs-lookup"><span data-stu-id="8119b-219">From here you can navigate through the library and download the file `seattle.master`.</span></span>
4. <span data-ttu-id="8119b-220">Изменить код с помощью текстового редактора и удалить блок кода в следующем снимке экрана.</span><span class="sxs-lookup"><span data-stu-id="8119b-220">Edit the code using a text editor and delete the code block in the following screen shot.</span></span><br/>![Удаление показанного блока кода](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. <span data-ttu-id="8119b-222">Удалите код между тегами и тегами и замените его `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` следующим фрагментом:</span><span class="sxs-lookup"><span data-stu-id="8119b-222">Remove the code between the `<SharePoint:AjaxDelta id="DeltaTopNavigation">` and `<\SharePoint:AjaxDelta>` tags and replace it with the following snippet:</span></span><br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. <span data-ttu-id="8119b-223">Замените URL-адрес в якорной метке загрузки изображения в начале ссылкой на изображение загрузки в коллекции веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="8119b-223">Replace the URL in the loading image anchor tag at the beginning, with a link to a loading image in your site collection.</span></span> <span data-ttu-id="8119b-224">После внесения изменений переименуем файл и загрузите его в галерею страниц.</span><span class="sxs-lookup"><span data-stu-id="8119b-224">After you have made the changes, rename the file and then upload it to the master page gallery.</span></span> <span data-ttu-id="8119b-225">Это создает новый файл .master.</span><span class="sxs-lookup"><span data-stu-id="8119b-225">This generates a new .master file.</span></span><br/>
7. <span data-ttu-id="8119b-226">Этот HTML — это базовая разметка, которая будет заполняться результатами поиска, возвращаемыми из кода JavaScript.</span><span class="sxs-lookup"><span data-stu-id="8119b-226">This HTML is the basic markup that will be populated by the search results returned from JavaScript code.</span></span> <span data-ttu-id="8119b-227">Вам потребуется изменить код, чтобы изменить значение корневого значения var = URL-адрес коллекции сайтов, как показано в следующем фрагменте:</span><span class="sxs-lookup"><span data-stu-id="8119b-227">You will need to edit the code to change the value for var root = "site collection URL" as demonstrated in the following snippet:</span></span><br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. <span data-ttu-id="8119b-228">Результаты назначаются массиву self.nodes, и иерархия строится из объектов с помощью linq.js, назначающих выход в массив self.hierarchy.</span><span class="sxs-lookup"><span data-stu-id="8119b-228">The results are assigned to the self.nodes array and a hierarchy is built out of the objects using linq.js assigning the output to an array self.hierarchy.</span></span> <span data-ttu-id="8119b-229">Этот массив является объектом, привязанным к HTML.</span><span class="sxs-lookup"><span data-stu-id="8119b-229">This array is the object that is bound to the HTML.</span></span> <span data-ttu-id="8119b-230">Это делается в функции toggleView() путем передачи самостоятельного объекта функции ko.applyBinding() .</span><span class="sxs-lookup"><span data-stu-id="8119b-230">This is done in the toggleView() function by passing the self object to the ko.applyBinding() function.</span></span><br/><span data-ttu-id="8119b-231">Это приводит к тому, что массив иерархии должен быть привязан к следующему HTML:</span><span class="sxs-lookup"><span data-stu-id="8119b-231">This then causes the hierarchy array to be bound to the following HTML:</span></span><br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

<span data-ttu-id="8119b-232">Обработчики событий и добавлены в навигацию верхнего уровня для обработки подмышных выпадающих меню, которые делаются `mouseenter` `mouseexit` в `addEventsToElements()` функции.</span><span class="sxs-lookup"><span data-stu-id="8119b-232">The event handlers for `mouseenter` and `mouseexit` are added to the top-level navigation to handle the subsite drop-down menus which is done in the `addEventsToElements()` function.</span></span>

<span data-ttu-id="8119b-233">В нашем сложном примере навигации новая загрузка страницы без локального кэшинга показывает, что время, затраченное на сервере, было сокращено с базовой структурной навигации, чтобы получить такой же результат, как и управляемый подход к навигации.</span><span class="sxs-lookup"><span data-stu-id="8119b-233">In our complex navigation example, a fresh page load without the local caching shows the time spent on the server has been cut down from the benchmark structural navigation to get a similar result as the managed navigation approach.</span></span>

### <a name="about-the-javascript-file"></a><span data-ttu-id="8119b-234">О файле JavaScript...</span><span class="sxs-lookup"><span data-stu-id="8119b-234">About the JavaScript file...</span></span>

>[!NOTE]
><span data-ttu-id="8119b-235">При использовании настраиваемого JavaScript убедитесь, что общедоступный CDN включен и файл находится в расположении CDN.</span><span class="sxs-lookup"><span data-stu-id="8119b-235">If using custom JavaScript, ensure that public CDN is enabled and the file is in a CDN location.</span></span>

<span data-ttu-id="8119b-236">Весь файл JavaScript следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8119b-236">The entire JavaScript file is as follows:</span></span>

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

<span data-ttu-id="8119b-237">Чтобы обобщить код, показанный выше в функции, создается, а затем называется функция на `jQuery $(document).ready` `viewModel object` этом `loadNavigationNodes()` объекте.</span><span class="sxs-lookup"><span data-stu-id="8119b-237">To summarize the code shown above in the `jQuery $(document).ready` function there is a `viewModel object` created and then the `loadNavigationNodes()` function on that object is called.</span></span> <span data-ttu-id="8119b-238">Эта функция либо загружает ранее построенную иерархию навигации, хранимую в локальном хранилище HTML5 клиентского браузера, либо вызывает функцию `queryRemoteInterface()` .</span><span class="sxs-lookup"><span data-stu-id="8119b-238">This function either loads the previously built navigation hierarchy stored in the HTML5 local storage of the client browser or it calls the function `queryRemoteInterface()`.</span></span>

<span data-ttu-id="8119b-239">`QueryRemoteInterface()` создает запрос с помощью функции с параметром запроса, определенным ранее в сценарии, а затем возвращает `getRequest()` данные с сервера.</span><span class="sxs-lookup"><span data-stu-id="8119b-239">`QueryRemoteInterface()` builds a request using the `getRequest()` function with the query parameter defined earlier in the script and then returns data from the server.</span></span> <span data-ttu-id="8119b-240">Эти данные по сути являются массивом всех сайтов в коллекции сайтов, представленных в качестве объектов передачи данных с различными свойствами.</span><span class="sxs-lookup"><span data-stu-id="8119b-240">This data is essentially an array of all the sites in the site collection represented as data transfer objects with various properties.</span></span>

<span data-ttu-id="8119b-241">Затем эти данные анализются в ранее определенные объекты, которые используются для создания наблюдаемых свойств для использования с помощью привязки данных к `SPO.Models.NavigationNode` значениям HTML, которые мы определили `Knockout.js` ранее.</span><span class="sxs-lookup"><span data-stu-id="8119b-241">This data is then parsed into the previously defined `SPO.Models.NavigationNode` objects which use `Knockout.js` to create observable properties for use by data binding the values into the HTML that we defined earlier.</span></span>

<span data-ttu-id="8119b-242">Затем объекты помещаются в массив результатов.</span><span class="sxs-lookup"><span data-stu-id="8119b-242">The objects are then put into a results array.</span></span> <span data-ttu-id="8119b-243">Этот массив разрезан в JSON с помощью knockout и хранится в локальном хранилище браузера для повышения производительности будущих нагрузок страниц.</span><span class="sxs-lookup"><span data-stu-id="8119b-243">This array is parsed into JSON using Knockout and stored in the local browser storage for improved performance on future page loads.</span></span>

### <a name="benefits-of-this-approach"></a><span data-ttu-id="8119b-244">Преимущества этого подхода</span><span class="sxs-lookup"><span data-stu-id="8119b-244">Benefits of this approach</span></span>

<span data-ttu-id="8119b-245">Одно из [](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) основных преимуществ этого подхода заключается в том, что при использовании локального хранилища HTML5 навигация сохраняется локально для пользователя при следующей загрузке страницы.</span><span class="sxs-lookup"><span data-stu-id="8119b-245">One major benefit of [this approach](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is that by using HTML5 local storage, the navigation is stored locally for the user the next time they load the page.</span></span> <span data-ttu-id="8119b-246">Мы получаем основные улучшения производительности с помощью API поиска для структурной навигации; однако для выполнения и настройки этой функции требуется некоторое техническое оснащение.</span><span class="sxs-lookup"><span data-stu-id="8119b-246">We get major performance improvements from using the search API for structural navigation; however, it takes some technical capability to execute and customize this functionality.</span></span>

<span data-ttu-id="8119b-247">В [примере реализации](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)сайты заказываться так же, как и в случае с внеупорядоченной структурной навигацией; алфавитный порядок.</span><span class="sxs-lookup"><span data-stu-id="8119b-247">In the [example implementation](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), the sites are ordered in the same way as the out-of-the-box structural navigation; alphabetical order.</span></span> <span data-ttu-id="8119b-248">Если вы хотите отклоняться от этого порядка, будет сложнее разрабатывать и поддерживать.</span><span class="sxs-lookup"><span data-stu-id="8119b-248">If you wanted to deviate from this order, it would be more complicated to develop and maintain.</span></span> <span data-ttu-id="8119b-249">Кроме того, этот подход требует отклоняться от поддерживаемых мастер-страниц.</span><span class="sxs-lookup"><span data-stu-id="8119b-249">Also, this approach requires you to deviate from the supported master pages.</span></span> <span data-ttu-id="8119b-250">Если настраиваемая мастер-страница не поддерживается, на сайте будут не хватать обновлений и улучшений, которые корпорация Майкрософт вносит на мастер-страницы.</span><span class="sxs-lookup"><span data-stu-id="8119b-250">If the custom master page is not maintained, your site will miss out on updates and improvements that Microsoft makes to the master pages.</span></span>

<span data-ttu-id="8119b-251">В [вышеуказанной](#about-the-javascript-file) коде есть следующие зависимости:</span><span class="sxs-lookup"><span data-stu-id="8119b-251">The [above code](#about-the-javascript-file) has the following dependencies:</span></span>

- <span data-ttu-id="8119b-252">jQuery — https://jquery.com/</span><span class="sxs-lookup"><span data-stu-id="8119b-252">jQuery - https://jquery.com/</span></span>
- <span data-ttu-id="8119b-253">KnockoutJS — https://knockoutjs.com/</span><span class="sxs-lookup"><span data-stu-id="8119b-253">KnockoutJS - https://knockoutjs.com/</span></span>
- <span data-ttu-id="8119b-254">Linq.js - https://linqjs.codeplex.com/ или github.com/neuecc/linq.js</span><span class="sxs-lookup"><span data-stu-id="8119b-254">Linq.js - https://linqjs.codeplex.com/, or github.com/neuecc/linq.js</span></span>

<span data-ttu-id="8119b-255">Текущая версия LinqJS не содержит метода ByHierarchy, используемого в вышеуказанном коде, и будет нарушать код навигации.</span><span class="sxs-lookup"><span data-stu-id="8119b-255">The current version of LinqJS does not contain the ByHierarchy method used in the above code and will break the navigation code.</span></span> <span data-ttu-id="8119b-256">Чтобы исправить это, добавьте следующий метод в файл Linq.js перед `Flatten: function ()` строкой.</span><span class="sxs-lookup"><span data-stu-id="8119b-256">To fix this, add the following method to the Linq.js file before the line `Flatten: function ()`.</span></span>

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a><span data-ttu-id="8119b-257">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="8119b-257">Related topics</span></span>

[<span data-ttu-id="8119b-258">Обзор управляемой навигации в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="8119b-258">Overview of managed navigation in SharePoint Server</span></span>](/sharepoint/administration/overview-of-managed-navigation)

[<span data-ttu-id="8119b-259">Кэшинг и производительность структурной навигации</span><span class="sxs-lookup"><span data-stu-id="8119b-259">Structural navigation caching and performance</span></span>](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)