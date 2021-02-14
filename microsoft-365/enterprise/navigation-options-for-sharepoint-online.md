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
description: В этой статье описываются сайты параметров навигации с включенной публикацией SharePoint в SharePoint Online.
ms.openlocfilehash: 86cefc60a26687835fd6a88de7f249143811de4f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696444"
---
# <a name="navigation-options-for-sharepoint-online"></a><span data-ttu-id="532fd-103">Параметры навигации для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="532fd-103">Navigation options for SharePoint Online</span></span>

<span data-ttu-id="532fd-104">В этой статье описываются сайты параметров навигации с включенной публикацией SharePoint в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="532fd-104">This article describes navigation options sites with SharePoint Publishing enabled in SharePoint Online.</span></span> <span data-ttu-id="532fd-105">Выбор и настройка навигации значительно влияют на производительность и масштабируемость сайтов в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="532fd-105">The choice and configuration of navigation significantly impacts the performance and scalability of sites in SharePoint Online.</span></span> <span data-ttu-id="532fd-106">Шаблон сайта публикации SharePoint следует использовать только в том случае, если это необходимо для централизованного портала, а функция публикации должна быть включена только на определенных сайтах и только тогда, когда это абсолютно необходимо, так как это может повлиять на производительность при неправильном используется.</span><span class="sxs-lookup"><span data-stu-id="532fd-106">The SharePoint Publishing site template should only be used if required for a centralized portal and the publishing feature should only be enabled on specific sites and only when absolutely required as it can impact performance when used incorrectly.</span></span>

>[!NOTE]
><span data-ttu-id="532fd-107">Если вы используете современные параметры навигации SharePoint, такие как мегаменю, каскадная навигация или навигация в центре, эта статья не относится к сайту.</span><span class="sxs-lookup"><span data-stu-id="532fd-107">If you're using modern SharePoint navigation options like mega menu, cascading navigation, or hub navigation, this article does not apply to your site.</span></span> <span data-ttu-id="532fd-108">Современные архитектуры сайтов SharePoint используют более плоскую иерархию сайтов и модель центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="532fd-108">Modern SharePoint site architectures leverage a more flattened site hierarchy and a hub-and-spoke model.</span></span> <span data-ttu-id="532fd-109">Это позволяет достичь многих сценариев, не требующих использования функции публикации SharePoint.</span><span class="sxs-lookup"><span data-stu-id="532fd-109">This allows many scenarios to be achieved that do NOT require use of the SharePoint Publishing feature.</span></span>

## <a name="overview-of-navigation-options"></a><span data-ttu-id="532fd-110">Обзор параметров навигации</span><span class="sxs-lookup"><span data-stu-id="532fd-110">Overview of navigation options</span></span>

<span data-ttu-id="532fd-111">Конфигурация поставщика навигации может значительно повлиять на производительность всего сайта, и следует тщательно пронабделить выбор поставщика навигации и конфигурации, которая эффективно масштабирования соответствует требованиям сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="532fd-111">Navigation provider configuration can significantly impact performance for the entire site, and careful consideration must be taken to pick a navigation provider and configuration that scales effectively for the requirements of a SharePoint site.</span></span> <span data-ttu-id="532fd-112">Существует два готовых поставщика навигации, а также настраиваемые реализации навигации.</span><span class="sxs-lookup"><span data-stu-id="532fd-112">There are two out-of-the-box navigation providers, as well as custom navigation implementations.</span></span>

<span data-ttu-id="532fd-113">Первый [**вариант,**](#using-structural-navigation-in-sharepoint-online)структурная навигация, — это рекомендуемый вариант навигации в SharePoint Online для классических сайтов SharePoint, если вы включите структурную навигацию для своего **сайта.**</span><span class="sxs-lookup"><span data-stu-id="532fd-113">The first option, [**Structural navigation**](#using-structural-navigation-in-sharepoint-online), is the recommended navigation option in SharePoint Online for classic Sharepoint sites, **if you turn on structural navigation caching for your site**.</span></span> <span data-ttu-id="532fd-114">Этот поставщик навигации отображает элементы навигации под текущим сайтом и, при необходимости, текущий сайт и его элементы уровня.</span><span class="sxs-lookup"><span data-stu-id="532fd-114">This navigation provider displays the navigation items below the current site, and optionally the current site and its siblings.</span></span> <span data-ttu-id="532fd-115">Он предоставляет дополнительные возможности, такие как обрезка по ролям безопасности и нумерация структуры сайта.</span><span class="sxs-lookup"><span data-stu-id="532fd-115">It provides additional capabilities such as security trimming and site structure enumeration.</span></span> <span data-ttu-id="532fd-116">Если кэширование отключено, это отрицательно скажется на производительности и масштабируемости и может влиять на регулирование.</span><span class="sxs-lookup"><span data-stu-id="532fd-116">If caching is disabled, this will negatively impact performance and scalability, and may be subject to throttling.</span></span>

<span data-ttu-id="532fd-117">Второй вариант, [**управл. Навигация (метаданные)**](#using-managed-navigation-and-metadata-in-sharepoint-online)представляет элементы навигации с использованием набора терминов управляемых метаданных.</span><span class="sxs-lookup"><span data-stu-id="532fd-117">The second option, [**Managed (Metadata) navigation**](#using-managed-navigation-and-metadata-in-sharepoint-online), represents navigation items using a Managed Metadata term set.</span></span> <span data-ttu-id="532fd-118">Рекомендуется отключить триммер безопасности, если это не требуется.</span><span class="sxs-lookup"><span data-stu-id="532fd-118">We recommend that security trimming be disabled unless required.</span></span> <span data-ttu-id="532fd-119">Триммер безопасности включен в качестве параметра безопасности по умолчанию для этого поставщика навигации; Однако многие сайты не требуют дополнительных расходов на триммер безопасности, так как элементы навигации часто согласуются для всех пользователей сайта.</span><span class="sxs-lookup"><span data-stu-id="532fd-119">Security trimming is enabled as a secure-by-default setting for this navigation provider; however, many sites do not require the overhead of security trimming since navigation elements often are consistent for all users of the site.</span></span> <span data-ttu-id="532fd-120">При рекомендуемой конфигурации для отключения триммеров безопасности этот поставщик навигации не требует нумерации структуры сайта и имеет высокую масштабируемость с приемлемым влиянием на производительность.</span><span class="sxs-lookup"><span data-stu-id="532fd-120">With the recommended configuration to disable security trimming, this navigation provider does not require enumerating site structure and is highly scalable with acceptable performance impact.</span></span>

<span data-ttu-id="532fd-121">В дополнение к внедренным поставщикам навигации, многие клиенты успешно реализовали альтернативные реализации настраиваемой навигации.</span><span class="sxs-lookup"><span data-stu-id="532fd-121">In addition to the out-of-the-box navigation providers, many customers have successfully implemented alternative custom navigation implementations.</span></span> <span data-ttu-id="532fd-122">См. сценарии на [основе поиска на стороне клиента](#using-search-driven-client-side-scripting) в этой статье.</span><span class="sxs-lookup"><span data-stu-id="532fd-122">See [Search-driven client-side scripting](#using-search-driven-client-side-scripting) in this article.</span></span>
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a><span data-ttu-id="532fd-123">Преимущества и недостатки параметров навигации SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="532fd-123">Pros and Cons of SharePoint Online navigation options</span></span>

<span data-ttu-id="532fd-124">В следующей таблице водятся преимущества и недостатки каждого из вариантов.</span><span class="sxs-lookup"><span data-stu-id="532fd-124">The following table summarizes the pros and cons of each option.</span></span>

|<span data-ttu-id="532fd-125">Структурная навигация</span><span class="sxs-lookup"><span data-stu-id="532fd-125">Structural navigation</span></span>  |<span data-ttu-id="532fd-126">Управляемая навигация</span><span class="sxs-lookup"><span data-stu-id="532fd-126">Managed navigation</span></span>  |<span data-ttu-id="532fd-127">Навигация на основе поиска</span><span class="sxs-lookup"><span data-stu-id="532fd-127">Search-driven navigation</span></span>  |<span data-ttu-id="532fd-128">Поставщик настраиваемой навигации</span><span class="sxs-lookup"><span data-stu-id="532fd-128">Custom-navigation provider</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="532fd-129">Плюсы:</span><span class="sxs-lookup"><span data-stu-id="532fd-129">Pros:</span></span><br/><br/><span data-ttu-id="532fd-130">Простое обслуживание</span><span class="sxs-lookup"><span data-stu-id="532fd-130">Easy to maintain</span></span><br/><span data-ttu-id="532fd-131">Триммер безопасности</span><span class="sxs-lookup"><span data-stu-id="532fd-131">Security trimmed</span></span><br/><span data-ttu-id="532fd-132">Автоматическое обновление в течение 24 часов после изменения содержимого</span><span class="sxs-lookup"><span data-stu-id="532fd-132">Automatically updates within 24 hours when content is changed</span></span><br/>     |<span data-ttu-id="532fd-133">Плюсы:</span><span class="sxs-lookup"><span data-stu-id="532fd-133">Pros:</span></span><br/><br/><span data-ttu-id="532fd-134">Простое обслуживание</span><span class="sxs-lookup"><span data-stu-id="532fd-134">Easy to maintain</span></span><br/>|<span data-ttu-id="532fd-135">Плюсы:</span><span class="sxs-lookup"><span data-stu-id="532fd-135">Pros:</span></span><br/><br/><span data-ttu-id="532fd-136">Триммер безопасности</span><span class="sxs-lookup"><span data-stu-id="532fd-136">Security trimmed</span></span><br/><span data-ttu-id="532fd-137">Автоматическое обновление при добавлении сайтов</span><span class="sxs-lookup"><span data-stu-id="532fd-137">Automatically updates as sites are added</span></span><br/><span data-ttu-id="532fd-138">Быстрая загрузка времени и локально кэшировать структуру навигации</span><span class="sxs-lookup"><span data-stu-id="532fd-138">Fast loading time and locally cached navigation structure</span></span><br/>|<span data-ttu-id="532fd-139">Плюсы:</span><span class="sxs-lookup"><span data-stu-id="532fd-139">Pros:</span></span><br/><br/><span data-ttu-id="532fd-140">Более широкий выбор доступных вариантов</span><span class="sxs-lookup"><span data-stu-id="532fd-140">Wider choice of options available</span></span><br/><span data-ttu-id="532fd-141">Быстрая загрузка при правильном кэшинге</span><span class="sxs-lookup"><span data-stu-id="532fd-141">Fast loading when caching is used correctly</span></span><br/><span data-ttu-id="532fd-142">Многие параметры хорошо работают с адаптивной разработкой страницы</span><span class="sxs-lookup"><span data-stu-id="532fd-142">Many options work well with responsive page design</span></span><br/>|
|<span data-ttu-id="532fd-143">Минусы:</span><span class="sxs-lookup"><span data-stu-id="532fd-143">Cons:</span></span><br/><br/><span data-ttu-id="532fd-144">**Влияет на производительность, если кэшинг отключен**</span><span class="sxs-lookup"><span data-stu-id="532fd-144">**Impacts performance if caching is disabled**</span></span><br/><span data-ttu-id="532fd-145">Подавно к регулированием</span><span class="sxs-lookup"><span data-stu-id="532fd-145">Subject to throttling</span></span><br/>|<span data-ttu-id="532fd-146">Минусы:</span><span class="sxs-lookup"><span data-stu-id="532fd-146">Cons:</span></span><br/><br/><span data-ttu-id="532fd-147">Автоматическое обновление для отражения структуры сайта</span><span class="sxs-lookup"><span data-stu-id="532fd-147">Not automatically updated to reflect site structure</span></span><br/><span data-ttu-id="532fd-148">**Влияет на производительность, если** включена триммер безопасности или сложная структура навигации</span><span class="sxs-lookup"><span data-stu-id="532fd-148">**Impacts performance if security trimming is enabled** or when navigation structure is complex</span></span><br/>|<span data-ttu-id="532fd-149">Минусы:</span><span class="sxs-lookup"><span data-stu-id="532fd-149">Cons:</span></span><br/><br/><span data-ttu-id="532fd-150">Нет возможности легко заказать сайты</span><span class="sxs-lookup"><span data-stu-id="532fd-150">No ability to easily order sites</span></span><br/><span data-ttu-id="532fd-151">Требуется настройка этакого страницы (требуются технические навыки)</span><span class="sxs-lookup"><span data-stu-id="532fd-151">Requires customization of the master page (technical skills required)</span></span><br/>|<span data-ttu-id="532fd-152">Минусы:</span><span class="sxs-lookup"><span data-stu-id="532fd-152">Cons:</span></span><br/><br/><span data-ttu-id="532fd-153">Требуется настраиваемая разработка</span><span class="sxs-lookup"><span data-stu-id="532fd-153">Custom development is required</span></span><br/><span data-ttu-id="532fd-154">Требуется внешний источник данных или хранимый кэш, например Azure</span><span class="sxs-lookup"><span data-stu-id="532fd-154">External data source / cache stored is needed e.g. Azure</span></span><br/>|

<span data-ttu-id="532fd-155">Наиболее подходящий вариант для сайта зависит от требований к сайту и технических возможностей.</span><span class="sxs-lookup"><span data-stu-id="532fd-155">The most appropriate option for your site will depend on your site requirements and on your technical capability.</span></span> <span data-ttu-id="532fd-156">Если вам нужен простой в настройке поставщик навигации, который автоматически обновляется [](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) при смене содержимого, то структурная навигация с включенным кэшингом является хорошим вариантом.</span><span class="sxs-lookup"><span data-stu-id="532fd-156">If you want an easy-to-configure navigation provider that automatically updates when content is changed, then structural navigation [with caching enabled](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) is a good option.</span></span>

>[!NOTE]
><span data-ttu-id="532fd-157">Применение того же принципа, что и современные сайты SharePoint, упрощая общую структуру сайтов до плоской, неиехронной структуры, повышает производительность и упрощает переход на современные сайты SharePoint.</span><span class="sxs-lookup"><span data-stu-id="532fd-157">Applying the same principle as modern SharePoint sites by simplifying the overall site structure to a flatter, non-hierarchical structure improves performance and simplifies moving to modern SharePoint sites.</span></span> <span data-ttu-id="532fd-158">Это означает, что вместо одного веб-сайта с сотнями сайтов (подсайтов) лучше использовать большое количество сайтов с очень большим количеством подсайтов ..</span><span class="sxs-lookup"><span data-stu-id="532fd-158">What this means is that instead of having a single site collection with hundreds of sites (subwebs), a better approach is to have many site collections with very few subsites (subwebs).</span></span>

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a><span data-ttu-id="532fd-159">Анализ производительности навигации в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="532fd-159">Analyzing navigation performance in SharePoint Online</span></span>

<span data-ttu-id="532fd-160">Средство диагностики страниц [для SharePoint](https://aka.ms/perftool) — это расширение браузера для браузеров Microsoft Edge и Chrome, которое анализирует как современный портал SharePoint Online, так и страницы классического сайта публикации.</span><span class="sxs-lookup"><span data-stu-id="532fd-160">The [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) is a browser extension for Microsoft Edge and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="532fd-161">Это средство работает только для SharePoint Online и не может использоваться на системной странице SharePoint.</span><span class="sxs-lookup"><span data-stu-id="532fd-161">This tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="532fd-162">Средство создает отчет для каждой проанализированой страницы, в котором показывая, как страница работает с заранее определенным набором правил, и отображает подробные сведения, когда результаты теста не попадают за пределы базового значения.</span><span class="sxs-lookup"><span data-stu-id="532fd-162">The tool generates a report for each analyzed page showing how the page performs against a pre-defined set of rules and displays detailed information when results for a test fall outside the baseline value.</span></span> <span data-ttu-id="532fd-163">Администраторы и дизайнеры SharePoint Online могут использовать это средство для устранения проблем с производительностью, чтобы обеспечить оптимизацию новых страниц перед публикацией.</span><span class="sxs-lookup"><span data-stu-id="532fd-163">SharePoint Online administrators and designers can use the tool to troubleshoot performance issues to ensure that new pages are optimized prior to publishing.</span></span>

<span data-ttu-id="532fd-164">**В частности, SPRequestDuration** — это время, необходимое SharePoint для обработки страницы.</span><span class="sxs-lookup"><span data-stu-id="532fd-164">**SPRequestDuration** in particular is the time it takes for SharePoint to process the page.</span></span> <span data-ttu-id="532fd-165">Интенсивное навигационное управление (например, включит страницы в структуру навигации), сложные иерархии сайтов и другие параметры конфигурации и топологии могут существенно ухудшить продолжительность.</span><span class="sxs-lookup"><span data-stu-id="532fd-165">Heavy navigation (like including pages in navigation), complex site hierarchies, and other configuration and topology options can all dramatically contribute to longer durations.</span></span>

## <a name="using-structural-navigation-in-sharepoint-online"></a><span data-ttu-id="532fd-166">Использование структурной навигации в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="532fd-166">Using structural navigation in SharePoint Online</span></span>

<span data-ttu-id="532fd-167">Это стандартная навигация, используемая по умолчанию, и является самым простым решением.</span><span class="sxs-lookup"><span data-stu-id="532fd-167">This is the out-of-the-box navigation used by default and is the most straightforward solution.</span></span> <span data-ttu-id="532fd-168">Он не требует какой-либо настройки, и не технические пользователи также могут легко добавлять элементы, скрывать элементы и управлять навигацией со страницы параметров.</span><span class="sxs-lookup"><span data-stu-id="532fd-168">It does not require any customization and a non-technical user can also easily add items, hide items, and manage the navigation from the settings page.</span></span> <span data-ttu-id="532fd-169">Рекомендуется [включать кэшинг,](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)в противном случае существует дорогостоящая компромиссная возможность производительности.</span><span class="sxs-lookup"><span data-stu-id="532fd-169">We recommend [enabling caching](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), otherwise there is an expensive performance trade-off.</span></span>

### <a name="how-to-implement-structural-navigation-caching"></a><span data-ttu-id="532fd-170">Реализация структурного кэшинга навигации</span><span class="sxs-lookup"><span data-stu-id="532fd-170">How to implement structural navigation caching</span></span>

<span data-ttu-id="532fd-171">В **области навигации "Параметры** сайта" можно проверить, выбрана ли структурная навигация для глобальной или  >    >  текущей навигации.</span><span class="sxs-lookup"><span data-stu-id="532fd-171">Under **Site Settings** > **Look and Feel** > **Navigation**, you can validate if structural navigation is selected for either global navigation or current navigation.</span></span> <span data-ttu-id="532fd-172">Выбор страницы **"Показать" будет** отрицательно влиять на производительность.</span><span class="sxs-lookup"><span data-stu-id="532fd-172">Selecting **Show pages** will have negative impact on performance.</span></span>

![Структурная навигация с выбранным представлением подсайтов](../media/SPONavOptionsStructuredShowSubsites.png)

<span data-ttu-id="532fd-174">Кэш можно включить или отключить на уровне и на уровне сайта, и включено для обоих этих режимов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="532fd-174">Caching can be enabled or disabled at the site collection level and at the site level, and is enabled for both by default.</span></span> <span data-ttu-id="532fd-175">Чтобы включить на уровне коллекции сайтов, в области **навигации**"Администрирование веб-сайтов для параметров сайта" в поле "Администрирование веб-сайтов" в поле "Включить кэшировать" в поле "Включить  >    >   **кэшинг".**</span><span class="sxs-lookup"><span data-stu-id="532fd-175">To enable at the site collection level, under **Site Settings** > **Site Collection Administration** > **Site Collection Navigation**, check the box for **Enable caching**.</span></span>

![Включить кэш на уровне сайта](../media/structural-nav/structural-nav-caching-site-coll.png)

<span data-ttu-id="532fd-177">Чтобы включить на уровне сайта, в **области** навигации "Параметры сайта" в поле "Включить  >   **кэш".**</span><span class="sxs-lookup"><span data-stu-id="532fd-177">To enable at the site level, under **Site Settings** > **Navigation**, check the box for **Enable caching**.</span></span>

![Включить кэш на уровне сайта](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a><span data-ttu-id="532fd-179">Использование управляемой навигации и метаданных в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="532fd-179">Using managed navigation and metadata in SharePoint Online</span></span>

<span data-ttu-id="532fd-180">У управляемой навигации есть еще один вариант, который можно использовать для воссоздания большинства функций, таких как структурная навигация.</span><span class="sxs-lookup"><span data-stu-id="532fd-180">Managed navigation is another out-of-the-box option that you can use to recreate most of the same functionality as structural navigation.</span></span> <span data-ttu-id="532fd-181">Для управляемых метаданных можно настроить отключение или отключение триммеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="532fd-181">Managed metadata can be configured to have security trimming enabled or disabled.</span></span> <span data-ttu-id="532fd-182">Если отключена триммерация безопасности, управличенная навигация является относительно эффективной, так как загружает все навигационные ссылки с постоянным числом вызовов сервера.</span><span class="sxs-lookup"><span data-stu-id="532fd-182">When configured with security trimming disabled, managed navigation is fairly efficient as it loads all the navigation links with a constant number of server calls.</span></span> <span data-ttu-id="532fd-183">Включение триммеров безопасности, однако, отменяет некоторые преимущества производительности управляемой навигации.</span><span class="sxs-lookup"><span data-stu-id="532fd-183">Enabling security trimming, however, negates some of the performance advantages of managed navigation.</span></span>

<span data-ttu-id="532fd-184">Если необходимо включить триммер безопасности, рекомендуется:</span><span class="sxs-lookup"><span data-stu-id="532fd-184">If you need to enable security trimming, we recommend that you:</span></span>

- <span data-ttu-id="532fd-185">Обновление всех ссылок на простые URL-адреса</span><span class="sxs-lookup"><span data-stu-id="532fd-185">Update all friendly URL links to simple links</span></span>
- <span data-ttu-id="532fd-186">Добавление необходимых узлов триммеров безопасности в качестве url-адресов</span><span class="sxs-lookup"><span data-stu-id="532fd-186">Add required security trimming nodes as friendly URLs</span></span>
- <span data-ttu-id="532fd-187">Ограничение числа элементов навигации не более 100 и не более 3 уровней в глубине</span><span class="sxs-lookup"><span data-stu-id="532fd-187">Limit the number of navigation items to no more than 100 and no more than 3 levels deep</span></span>

<span data-ttu-id="532fd-188">Для многих сайтов не требуется триммер безопасности, так как структура навигации часто согласована для всех пользователей сайта.</span><span class="sxs-lookup"><span data-stu-id="532fd-188">Many sites do not require security trimming, as the navigation structure is often consistent for all users of the site.</span></span> <span data-ttu-id="532fd-189">Если триммер безопасности отключен и в навигацию добавлена ссылка, доступ к которую есть не у всех пользователей, ссылка будет по-прежнему отображена, но при этом будет отказано в доступе.</span><span class="sxs-lookup"><span data-stu-id="532fd-189">If security trimming is disabled and a link is added to navigation that not all users have access to, the link will still show but will lead to an access denied message.</span></span> <span data-ttu-id="532fd-190">Не существует риска случайного доступа к контенту.</span><span class="sxs-lookup"><span data-stu-id="532fd-190">There is no risk of inadvertent access to the content.</span></span>

### <a name="how-to-implement-managed-navigation-and-the-results"></a><span data-ttu-id="532fd-191">Реализация управляемой навигации и результатов</span><span class="sxs-lookup"><span data-stu-id="532fd-191">How to implement managed navigation and the results</span></span>

<span data-ttu-id="532fd-192">Существует несколько статей о docs.microsoft.com о подробностях управляемой навигации.</span><span class="sxs-lookup"><span data-stu-id="532fd-192">There are several articles on docs.microsoft.com about the details of managed navigation.</span></span> <span data-ttu-id="532fd-193">Например, [см. обзор управляемой навигации в SharePoint Server.](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)</span><span class="sxs-lookup"><span data-stu-id="532fd-193">For example, see [Overview of managed navigation in SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).</span></span>

<span data-ttu-id="532fd-194">Для реализации управляемой навигации необходимо настроить термины с URL-адресами, соответствующими структуре навигации сайта.</span><span class="sxs-lookup"><span data-stu-id="532fd-194">In order to implement managed navigation, you set up terms with URLs corresponding to the navigation structure of the site.</span></span> <span data-ttu-id="532fd-195">Управлию навигацию можно даже вручную сменить структурную навигацию во многих случаях.</span><span class="sxs-lookup"><span data-stu-id="532fd-195">Managed navigation can even be manually curated to replace structural navigation in many cases.</span></span> <span data-ttu-id="532fd-196">Пример:</span><span class="sxs-lookup"><span data-stu-id="532fd-196">For example:</span></span>

![Структура сайта SharePoint Online](../media/SPONavOptionsListOfSites.png)<span data-ttu-id="532fd-198">)</span><span class="sxs-lookup"><span data-stu-id="532fd-198">)</span></span>

## <a name="using-search-driven-client-side-scripting"></a><span data-ttu-id="532fd-199">Использование клиентских сценариев на основе поиска</span><span class="sxs-lookup"><span data-stu-id="532fd-199">Using Search-driven client-side scripting</span></span>

<span data-ttu-id="532fd-200">Один распространенный класс реализации настраиваемой навигации охватывает шаблоны проектирования, отрисоваемые клиентом, которые хранят локальный кэш узлов навигации.</span><span class="sxs-lookup"><span data-stu-id="532fd-200">One common class of custom navigation implementations embraces client-rendered design patterns that store a local cache of navigation nodes.</span></span>

<span data-ttu-id="532fd-201">Эти поставщики навигации имеют несколько ключевых преимуществ:</span><span class="sxs-lookup"><span data-stu-id="532fd-201">These navigation providers have a couple of key advantages:</span></span>

- <span data-ttu-id="532fd-202">Как правило, они хорошо работают с адаптивной схемой страниц.</span><span class="sxs-lookup"><span data-stu-id="532fd-202">They generally work well with responsive page designs.</span></span>
- <span data-ttu-id="532fd-203">Они чрезвычайно масштабируемые и высоковыполнимы, так как они могут отрисовки без затрат на ресурсы (и обновления в фоновом режиме после окончания времени.</span><span class="sxs-lookup"><span data-stu-id="532fd-203">They are extremely scalable and performant because they can render with no resource cost (and refresh in the background after a timeout).</span></span>
- <span data-ttu-id="532fd-204">Эти поставщики навигации могут получать данные навигации с помощью различных стратегий, от простых статических конфигураций до различных динамических поставщиков данных.</span><span class="sxs-lookup"><span data-stu-id="532fd-204">These navigation providers can retrieve navigation data using various strategies, ranging from simple static configurations to various dynamic data providers.</span></span>

<span data-ttu-id="532fd-205">Примером поставщика данных является использование навигации на основе **поиска,** которая обеспечивает гибкость для эффективного нумерации узлов навигации и обработки триммеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="532fd-205">An example of a data provider is to use a **Search-driven navigation**, which allows flexibility for enumerating navigation nodes and handling security trimming efficiently.</span></span>

<span data-ttu-id="532fd-206">Существуют другие популярные варианты создания **пользовательских поставщиков навигации.**</span><span class="sxs-lookup"><span data-stu-id="532fd-206">There are other popular options to build **Custom navigation providers**.</span></span> <span data-ttu-id="532fd-207">Дополнительные [рекомендации по построению](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) настраиваемой службы навигации для порталов SharePoint Online можно найти в решениях навигации для SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="532fd-207">Please review [Navigation solutions for SharePoint Online portals](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) for further guidance on building a Custom navigation provider.</span></span>

<span data-ttu-id="532fd-208">С помощью поиска можно использовать индексы, встроенные в фоновом режиме, с помощью непрерывного обхода контента.</span><span class="sxs-lookup"><span data-stu-id="532fd-208">Using search you can leverage the indexes that are built up in the background using continuous crawl.</span></span> <span data-ttu-id="532fd-209">Результаты поиска извлекаются из индекса поиска, а результаты обрезаются по безопасности.</span><span class="sxs-lookup"><span data-stu-id="532fd-209">The search results are pulled from the search index and the results are security-trimmed.</span></span> <span data-ttu-id="532fd-210">Как правило, это быстрее, чем у поставщиков навигации, которые уже есть в комплекте, если требуется обрезка по ролю безопасности.</span><span class="sxs-lookup"><span data-stu-id="532fd-210">This is generally faster than out-of-the-box navigation providers when security trimming is required.</span></span> <span data-ttu-id="532fd-211">Использование поиска для структурной навигации, особенно при использовании сложной структуры сайта, значительно ускоряет загрузку страниц.</span><span class="sxs-lookup"><span data-stu-id="532fd-211">Using search for structural navigation, especially if you have a complex site structure, will speed up page loading time considerably.</span></span> <span data-ttu-id="532fd-212">Основное преимущество этого по сравнению с управляемой навигацией заключается в том, что вы можете воспользоваться триммером безопасности.</span><span class="sxs-lookup"><span data-stu-id="532fd-212">The main advantage of this over managed navigation is that you benefit from security trimming.</span></span>

<span data-ttu-id="532fd-213">Этот подход включает создание настраиваемой эталовой страницы и замену стандартного кода навигации на пользовательский HTML.</span><span class="sxs-lookup"><span data-stu-id="532fd-213">This approach involves creating a custom master page and replacing the out-of-the-box navigation code with custom HTML.</span></span> <span data-ttu-id="532fd-214">Выполните следующую процедуру, описанную в следующем примере, чтобы заменить код навигации в `seattle.html` файле.</span><span class="sxs-lookup"><span data-stu-id="532fd-214">Follow this procedure outlined in the following example to replace the navigation code in the file `seattle.html`.</span></span> <span data-ttu-id="532fd-215">В этом примере мы откроем файл и замените `seattle.html` весь элемент `id="DeltaTopNavigation"` пользовательским HTML-кодом.</span><span class="sxs-lookup"><span data-stu-id="532fd-215">In this example, you will open the `seattle.html` file and replace the whole element `id="DeltaTopNavigation"` with custom HTML code.</span></span>

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a><span data-ttu-id="532fd-216">Пример. Замена замещаемого кода навигации на этакодной странице</span><span class="sxs-lookup"><span data-stu-id="532fd-216">Example: Replace the out-of-the-box navigation code in a master page</span></span>

1. <span data-ttu-id="532fd-217">Перейдите на страницу "Параметры сайта".</span><span class="sxs-lookup"><span data-stu-id="532fd-217">Navigate to the Site Settings page.</span></span>
2. <span data-ttu-id="532fd-218">Откройте галерею этастерных страниц, щелкнув **"Этакое страницы".**</span><span class="sxs-lookup"><span data-stu-id="532fd-218">Open the master page gallery by clicking **Master Pages**.</span></span>
3. <span data-ttu-id="532fd-219">Здесь вы можете перейти по библиотеке и скачать `seattle.master` файл.</span><span class="sxs-lookup"><span data-stu-id="532fd-219">From here you can navigate through the library and download the file `seattle.master`.</span></span>
4. <span data-ttu-id="532fd-220">Отредактировать код с помощью текстового редактора и удалить блок кода на следующем снимке экрана.</span><span class="sxs-lookup"><span data-stu-id="532fd-220">Edit the code using a text editor and delete the code block in the following screen shot.</span></span><br/>![Удаление блока кода, показанного](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. <span data-ttu-id="532fd-222">Удалите код между тегами и `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` тегами и замените его следующим фрагментом кода:</span><span class="sxs-lookup"><span data-stu-id="532fd-222">Remove the code between the `<SharePoint:AjaxDelta id="DeltaTopNavigation">` and `<\SharePoint:AjaxDelta>` tags and replace it with the following snippet:</span></span><br/>

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
6. <span data-ttu-id="532fd-223">Замените URL-адрес в загружаемом теге привязки изображения в начале ссылкой на загружающий образ в вашем коллекции веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="532fd-223">Replace the URL in the loading image anchor tag at the beginning, with a link to a loading image in your site collection.</span></span> <span data-ttu-id="532fd-224">После внесения изменений переименуем файл и загрузите его в галерею этакого страницы.</span><span class="sxs-lookup"><span data-stu-id="532fd-224">After you have made the changes, rename the file and then upload it to the master page gallery.</span></span> <span data-ttu-id="532fd-225">При этом создается новый MASTER-файл.</span><span class="sxs-lookup"><span data-stu-id="532fd-225">This generates a new .master file.</span></span><br/>
7. <span data-ttu-id="532fd-226">Этот HTML-код — это базовая разметка, которая будет заполнена результатами поиска, возвращенными кодом JavaScript.</span><span class="sxs-lookup"><span data-stu-id="532fd-226">This HTML is the basic markup that will be populated by the search results returned from JavaScript code.</span></span> <span data-ttu-id="532fd-227">Вам потребуется изменить код, чтобы изменить значение var root = "URL-адрес коллекции веб-сайтов", как показано в следующем фрагменте кода:</span><span class="sxs-lookup"><span data-stu-id="532fd-227">You will need to edit the code to change the value for var root = "site collection URL" as demonstrated in the following snippet:</span></span><br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. <span data-ttu-id="532fd-228">Результаты назначаются массиву self.nodes, а иерархия строится из объектов с помощью linq.js назначения выходных данных массиву self.hierarchy.</span><span class="sxs-lookup"><span data-stu-id="532fd-228">The results are assigned to the self.nodes array and a hierarchy is built out of the objects using linq.js assigning the output to an array self.hierarchy.</span></span> <span data-ttu-id="532fd-229">Этот массив является объектом, привязанным к HTML.</span><span class="sxs-lookup"><span data-stu-id="532fd-229">This array is the object that is bound to the HTML.</span></span> <span data-ttu-id="532fd-230">Это делается в функции toggleView() путем передачи самостоятельного объекта в функцию ko.applyBinding().</span><span class="sxs-lookup"><span data-stu-id="532fd-230">This is done in the toggleView() function by passing the self object to the ko.applyBinding() function.</span></span><br/><span data-ttu-id="532fd-231">После этого массив иерархии будет привязан к следующему HTML-коду:</span><span class="sxs-lookup"><span data-stu-id="532fd-231">This then causes the hierarchy array to be bound to the following HTML:</span></span><br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

<span data-ttu-id="532fd-232">Обработчики событий для навигации верхнего уровня и добавляются в них для обработки выпадающих меню подсайтов, которые `mouseenter` `mouseexit` делаются в `addEventsToElements()` функции.</span><span class="sxs-lookup"><span data-stu-id="532fd-232">The event handlers for `mouseenter` and `mouseexit` are added to the top-level navigation to handle the subsite drop-down menus which is done in the `addEventsToElements()` function.</span></span>

<span data-ttu-id="532fd-233">В нашем примере сложной навигации новая нагрузка на страницу без локального кэшинга показывает, что время, затраченное на сервере, было сокращено из структурной навигации производительности, чтобы получить такой же результат, как и у управляемой навигации.</span><span class="sxs-lookup"><span data-stu-id="532fd-233">In our complex navigation example, a fresh page load without the local caching shows the time spent on the server has been cut down from the benchmark structural navigation to get a similar result as the managed navigation approach.</span></span>

### <a name="about-the-javascript-file"></a><span data-ttu-id="532fd-234">О файле JavaScript...</span><span class="sxs-lookup"><span data-stu-id="532fd-234">About the JavaScript file...</span></span>

>[!NOTE]
><span data-ttu-id="532fd-235">Если используется пользовательский JavaScript, убедитесь, что общедоступный CDN включен и файл находится в расположении CDN.</span><span class="sxs-lookup"><span data-stu-id="532fd-235">If using custom JavaScript, ensure that public CDN is enabled and the file is in a CDN location.</span></span>

<span data-ttu-id="532fd-236">Весь файл JavaScript будет следующим:</span><span class="sxs-lookup"><span data-stu-id="532fd-236">The entire JavaScript file is as follows:</span></span>

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

<span data-ttu-id="532fd-237">Чтобы обобщить код, показанный выше в функции, создается и затем функция для `jQuery $(document).ready` `viewModel object` этого `loadNavigationNodes()` объекта.</span><span class="sxs-lookup"><span data-stu-id="532fd-237">To summarize the code shown above in the `jQuery $(document).ready` function there is a `viewModel object` created and then the `loadNavigationNodes()` function on that object is called.</span></span> <span data-ttu-id="532fd-238">Эта функция загружает ранее созданную иерархию навигации, храняную в локальном хранилище HTML5 клиентского браузера, или вызывает `queryRemoteInterface()` функцию.</span><span class="sxs-lookup"><span data-stu-id="532fd-238">This function either loads the previously built navigation hierarchy stored in the HTML5 local storage of the client browser or it calls the function `queryRemoteInterface()`.</span></span>

<span data-ttu-id="532fd-239">`QueryRemoteInterface()` создает запрос с помощью функции с параметром запроса, определенным ранее в сценарии, а затем возвращает данные `getRequest()` с сервера.</span><span class="sxs-lookup"><span data-stu-id="532fd-239">`QueryRemoteInterface()` builds a request using the `getRequest()` function with the query parameter defined earlier in the script and then returns data from the server.</span></span> <span data-ttu-id="532fd-240">По сути, эти данные представляют собой массив всех сайтов в коллекции сайтов, представленных в качестве объектов передачи данных с различными свойствами.</span><span class="sxs-lookup"><span data-stu-id="532fd-240">This data is essentially an array of all the sites in the site collection represented as data transfer objects with various properties.</span></span>

<span data-ttu-id="532fd-241">Затем эти данные анализются в ранее определенных объектах, которые используются для создания наблюдаемых свойств для использования при привязке данных значений в HTML-код, определенный `SPO.Models.NavigationNode` `Knockout.js` ранее.</span><span class="sxs-lookup"><span data-stu-id="532fd-241">This data is then parsed into the previously defined `SPO.Models.NavigationNode` objects which use `Knockout.js` to create observable properties for use by data binding the values into the HTML that we defined earlier.</span></span>

<span data-ttu-id="532fd-242">Затем объекты помещаются в массив результатов.</span><span class="sxs-lookup"><span data-stu-id="532fd-242">The objects are then put into a results array.</span></span> <span data-ttu-id="532fd-243">Этот массив разбит на JSON с помощью Knockout и сохраняется в локальном хранилище браузера для повышения производительности при будущих загрузках страниц.</span><span class="sxs-lookup"><span data-stu-id="532fd-243">This array is parsed into JSON using Knockout and stored in the local browser storage for improved performance on future page loads.</span></span>

### <a name="benefits-of-this-approach"></a><span data-ttu-id="532fd-244">Преимущества этого подхода</span><span class="sxs-lookup"><span data-stu-id="532fd-244">Benefits of this approach</span></span>

<span data-ttu-id="532fd-245">Одно из [](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) основных преимуществ этого подхода заключается в том, что при использовании локального хранилища HTML5 навигация сохраняется локально для пользователя при следующей загрузке страницы.</span><span class="sxs-lookup"><span data-stu-id="532fd-245">One major benefit of [this approach](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) is that by using HTML5 local storage, the navigation is stored locally for the user the next time they load the page.</span></span> <span data-ttu-id="532fd-246">Мы получаем основные улучшения производительности благодаря использованию API поиска для структурной навигации; Однако для выполнения и настройки этой функции требуется техническая возможность.</span><span class="sxs-lookup"><span data-stu-id="532fd-246">We get major performance improvements from using the search API for structural navigation; however, it takes some technical capability to execute and customize this functionality.</span></span>

<span data-ttu-id="532fd-247">В [примере реализации](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)сайты упорядочены так же, как и готовые структуры навигации; алфавитный порядок.</span><span class="sxs-lookup"><span data-stu-id="532fd-247">In the [example implementation](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), the sites are ordered in the same way as the out-of-the-box structural navigation; alphabetical order.</span></span> <span data-ttu-id="532fd-248">Если вы хотите отклоняться от этого порядка, будет сложнее разрабатывать и поддерживать.</span><span class="sxs-lookup"><span data-stu-id="532fd-248">If you wanted to deviate from this order, it would be more complicated to develop and maintain.</span></span> <span data-ttu-id="532fd-249">Кроме того, для этого подхода необходимо отклоняться от поддерживаемых этастерных страниц.</span><span class="sxs-lookup"><span data-stu-id="532fd-249">Also, this approach requires you to deviate from the supported master pages.</span></span> <span data-ttu-id="532fd-250">Если настраиваемая этаповая страница не поддерживается, на вашем сайте не будут обновлены и усовершенствования, которые корпорация Майкрософт вносит в этакое страницы.</span><span class="sxs-lookup"><span data-stu-id="532fd-250">If the custom master page is not maintained, your site will miss out on updates and improvements that Microsoft makes to the master pages.</span></span>

<span data-ttu-id="532fd-251">[Вышеперечисленный](#about-the-javascript-file) код имеет следующие зависимости:</span><span class="sxs-lookup"><span data-stu-id="532fd-251">The [above code](#about-the-javascript-file) has the following dependencies:</span></span>

- <span data-ttu-id="532fd-252">jQuery — https://jquery.com/</span><span class="sxs-lookup"><span data-stu-id="532fd-252">jQuery - https://jquery.com/</span></span>
- <span data-ttu-id="532fd-253">KnockoutJS — https://knockoutjs.com/</span><span class="sxs-lookup"><span data-stu-id="532fd-253">KnockoutJS - https://knockoutjs.com/</span></span>
- <span data-ttu-id="532fd-254">Linq.js - https://linqjs.codeplex.com/ или github.com/neuecc/linq.js</span><span class="sxs-lookup"><span data-stu-id="532fd-254">Linq.js - https://linqjs.codeplex.com/, or github.com/neuecc/linq.js</span></span>

<span data-ttu-id="532fd-255">Текущая версия LinqJS не содержит метод ByHierarchy, используемый в коде выше, и разорвет код навигации.</span><span class="sxs-lookup"><span data-stu-id="532fd-255">The current version of LinqJS does not contain the ByHierarchy method used in the above code and will break the navigation code.</span></span> <span data-ttu-id="532fd-256">Чтобы устранить эту проблему, добавьте следующий метод в Linq.js перед `Flatten: function ()` строкой.</span><span class="sxs-lookup"><span data-stu-id="532fd-256">To fix this, add the following method to the Linq.js file before the line `Flatten: function ()`.</span></span>

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
  
## <a name="related-topics"></a><span data-ttu-id="532fd-257">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="532fd-257">Related topics</span></span>

[<span data-ttu-id="532fd-258">Обзор управляемой навигации в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="532fd-258">Overview of managed navigation in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

[<span data-ttu-id="532fd-259">Кэшинг и производительность структурной навигации</span><span class="sxs-lookup"><span data-stu-id="532fd-259">Structural navigation caching and performance</span></span>](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)
