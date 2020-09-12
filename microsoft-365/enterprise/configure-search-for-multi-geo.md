---
title: Настройка поиска для Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: tlarsen
author: tklarsen
manager: arnek
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-mar2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: Сведения о настройке поиска в среде с поддержкой нескольких регионов. Только некоторые клиенты, например OneDrive для бизнеса, могут возвращать результаты в среде с поддержкой нескольких регионов.
ms.openlocfilehash: e213e93cfbc967a723b4d27f4b36a83fe6687da9
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547156"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a><span data-ttu-id="f1233-104">Настройка поиска для Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="f1233-104">Configure Search for Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="f1233-105">В среде с поддержкой нескольких регионов для каждого географического расположения предусмотрены отдельные индекс и центр поиска.</span><span class="sxs-lookup"><span data-stu-id="f1233-105">In a multi-geo environment, each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="f1233-106">Когда пользователь пытается что-то найти, запрос развертывается для всех индексов, а возвращенные результаты объединяются.</span><span class="sxs-lookup"><span data-stu-id="f1233-106">When a user searches, the query is fanned out to all the indexes, and the returned results are merged.</span></span>

<span data-ttu-id="f1233-107">Например, пользователь, находящийся в одном географическом расположении, может искать контент, хранящийся в другом, а также на сайте SharePoint, доступ к которому ограничен другим географическим расположением.</span><span class="sxs-lookup"><span data-stu-id="f1233-107">For example, a user in one geo location can search for content stored in another geo location, or for content on a SharePoint site that's restricted to a different geo location.</span></span> <span data-ttu-id="f1233-108">Если у пользователя есть доступ к этому контенту, отобразятся результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="f1233-108">If the user has access to this content, search will show the result.</span></span>

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a><span data-ttu-id="f1233-109">Какие клиенты поиска работают в среде с поддержкой нескольких регионов?</span><span class="sxs-lookup"><span data-stu-id="f1233-109">Which search clients work in a multi-geo environment?</span></span>

<span data-ttu-id="f1233-110">Возвращать результаты поиска из всех географических расположений могут такие клиенты:</span><span class="sxs-lookup"><span data-stu-id="f1233-110">These clients can return results from all geo locations:</span></span>

- <span data-ttu-id="f1233-111">OneDrive для бизнеса;</span><span class="sxs-lookup"><span data-stu-id="f1233-111">OneDrive for Business</span></span>
- <span data-ttu-id="f1233-112">Delve;</span><span class="sxs-lookup"><span data-stu-id="f1233-112">Delve</span></span>
- <span data-ttu-id="f1233-113">домашняя страница SharePoint;</span><span class="sxs-lookup"><span data-stu-id="f1233-113">The SharePoint home page</span></span>
- <span data-ttu-id="f1233-114">центр поиска;</span><span class="sxs-lookup"><span data-stu-id="f1233-114">The Search Center</span></span>
- <span data-ttu-id="f1233-115">специальные поисковые приложения, которые используют API поиска SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f1233-115">Custom search applications that use the SharePoint Search API</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="f1233-116">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f1233-116">OneDrive for Business</span></span>

<span data-ttu-id="f1233-117">Как только завершится настройка среды с поддержкой нескольких регионов, пользователи, выполняющие поиск в OneDrive, получат результаты из всех географических расположений.</span><span class="sxs-lookup"><span data-stu-id="f1233-117">As soon as the multi-geo environment has been set up, users that search in OneDrive get results from all geo locations.</span></span>

### <a name="delve"></a><span data-ttu-id="f1233-118">Delve</span><span class="sxs-lookup"><span data-stu-id="f1233-118">Delve</span></span>

<span data-ttu-id="f1233-119">Как только завершится настройка среды с поддержкой нескольких регионов, пользователи, выполняющие поиск в Delve, получат результаты из всех географических расположений.</span><span class="sxs-lookup"><span data-stu-id="f1233-119">As soon as the multi-geo environment has been set up, users that search in Delve get results from all geo locations.</span></span>

<span data-ttu-id="f1233-120">Веб-канал Delve и карточка профиля показывают только краткое содержание файлов, которые хранятся в центральном расположении.</span><span class="sxs-lookup"><span data-stu-id="f1233-120">The Delve feed and the profile card only show previews of files that are stored in the central location.</span></span> <span data-ttu-id="f1233-121">В случае файлов, хранящихся в периферийных расположениях, отображается значок типа файла.</span><span class="sxs-lookup"><span data-stu-id="f1233-121">For files that are stored in satellite locations, the icon for the file type is shown instead.</span></span>

### <a name="the-sharepoint-home-page"></a><span data-ttu-id="f1233-122">Домашняя страница SharePoint</span><span class="sxs-lookup"><span data-stu-id="f1233-122">The SharePoint home page</span></span>

<span data-ttu-id="f1233-p105">Как только завершится настройка среды с поддержкой нескольких регионов, пользователи на своей домашней странице SharePoint увидят новости, недавние и отслеживаемые сайты из нескольких географических расположений. Используя поле поиска на домашней странице SharePoint, пользователи получат объединенные результаты из нескольких географических расположений.</span><span class="sxs-lookup"><span data-stu-id="f1233-p105">As soon as the multi-geo environment has been set up, users will see news, recent and followed sites from multiple geo locations on their SharePoint home page. If they use the search box on the SharePoint home page, they'll get merged results from multiple geo locations.</span></span>

### <a name="the-search-center"></a><span data-ttu-id="f1233-125">центр поиска;</span><span class="sxs-lookup"><span data-stu-id="f1233-125">The Search Center</span></span>

<span data-ttu-id="f1233-p106">Когда завершится настройка среды с поддержкой нескольких регионов, каждый центр поиска будет по-прежнему отображать только результаты из своего географического расположения. Чтобы можно было получать данные из всех географических расположений, администраторы должны [изменить настройки каждого центра поиска](#_Set_up_a_1). После этого пользователи станут получать результаты из всех географических расположений.</span><span class="sxs-lookup"><span data-stu-id="f1233-p106">After the multi-geo environment has been set up, each Search Center continues to only show results from their own geo location. Admins must [change the settings of each Search Center](#_Set_up_a_1) to get results from all geo locations. Afterwards, users that search in the Search Center get results from all geo locations.</span></span>

### <a name="custom-search-applications"></a><span data-ttu-id="f1233-129">Специальные поисковые приложения</span><span class="sxs-lookup"><span data-stu-id="f1233-129">Custom search applications</span></span>

<span data-ttu-id="f1233-p107">Как правило, специальные поисковые приложения взаимодействуют с индексами поиска при помощи существующих REST API поиска SharePoint. Для получения результатов из всех или некоторых географических расположений приложение должно [вызвать API и включить в запрос новые параметры поддержки нескольких регионов](#_Get_custom_search). Это действие активирует развертывание запроса для всех геообъектов.</span><span class="sxs-lookup"><span data-stu-id="f1233-p107">As usual, custom search applications interact with the search indexes by using the existing SharePoint Search REST APIs. To get results from all, or some geo locations, the application must [call the API and include the new Multi-Geo query parameters](#_Get_custom_search) in the request. This triggers a fan out of the query to all geo locations.</span></span>

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a><span data-ttu-id="f1233-133">Чем отличается поиск в среде с поддержкой нескольких регионов?</span><span class="sxs-lookup"><span data-stu-id="f1233-133">What's different about search in a multi-geo environment?</span></span>

<span data-ttu-id="f1233-134">Некоторые знакомые вам функции поиска работают иначе в среде с поддержкой нескольких регионов.</span><span class="sxs-lookup"><span data-stu-id="f1233-134">Some search features you might be familiar with, work differently in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f1233-135"><strong>Функция</strong></span><span class="sxs-lookup"><span data-stu-id="f1233-135"><strong>Feature</strong></span></span></th>
<th align="left"><span data-ttu-id="f1233-136"><strong>Принцип работы</strong></span><span class="sxs-lookup"><span data-stu-id="f1233-136"><strong>How it works</strong></span></span></th>
<th align="left"><span data-ttu-id="f1233-137"><strong>Решение</strong></span><span class="sxs-lookup"><span data-stu-id="f1233-137"><strong>Workaround</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="f1233-138">Повышение уровня результатов</span><span class="sxs-lookup"><span data-stu-id="f1233-138">Promoted results</span></span></td>
<td align="left"><span data-ttu-id="f1233-139">Вы можете создавать правила запросов с повышением уровня результатов для всего клиента, семейства веб-сайтов или отдельного сайта.</span><span class="sxs-lookup"><span data-stu-id="f1233-139">You can create query rules with promoted results at different levels: for the whole tenant, for a site collection, or for a site.</span></span> <span data-ttu-id="f1233-140">Чтобы в среде с поддержкой нескольких регионов повысить уровень результатов для центров поиска всех географических расположений, определите такие результаты для клиента.</span><span class="sxs-lookup"><span data-stu-id="f1233-140">In a multi-geo environment, define promoted results at the tenant level to promote the results to the Search Centers in all geo locations.</span></span> <span data-ttu-id="f1233-141">Чтобы повысить уровень результатов только для центра поиска, находящегося в географическом расположении семейства веб-сайтов или отдельного сайта, определите такие результаты для семейства веб-сайтов или сайта.</span><span class="sxs-lookup"><span data-stu-id="f1233-141">If you only want to promote results in the Search Center that's in the geo location of the site collection or site, define the promoted results at the site collection or site level.</span></span> <span data-ttu-id="f1233-142">Эти результаты не повышаются в других географических расположениях.</span><span class="sxs-lookup"><span data-stu-id="f1233-142">These results are not promoted in other geo locations.</span></span></td>
<td align="left"><span data-ttu-id="f1233-143">Если вам не нужны различные результаты с повышенным уровнем для каждого отдельного географического расположения (например, разные правила для перемещения), рекомендуем определять результаты с повышенным уровнем для клиента.</span><span class="sxs-lookup"><span data-stu-id="f1233-143">If you don't need different promoted results per geo location, for example different rules for traveling, we recommend defining promoted results at the tenant level.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="f1233-144">Уточнения поиска</span><span class="sxs-lookup"><span data-stu-id="f1233-144">Search refiners</span></span></td>
<td align="left"><span data-ttu-id="f1233-p109">При поиске возвращаются уточнения из всех географических расположений клиента, а затем объединяются. Объединение выполняется максимально правильно, но счетчики уточнений могут не быть точными на 100 %. Для большинства сценариев поиска такой точности вполне достаточно. </span><span class="sxs-lookup"><span data-stu-id="f1233-p109">Search returns refiners from all the geo locations of a tenant and then aggregates them. The aggregation is a best effort, meaning that the refiner counts might not be 100% accurate. For most search-driven scenarios, this accuracy is sufficient. </span></span></td>
<td align="left"><span data-ttu-id="f1233-148">Поисковые приложения, которые зависят от полноты уточнения, запрашивают каждое географическое расположение отдельно.</span><span class="sxs-lookup"><span data-stu-id="f1233-148">For search-driven applications that depend on refiner completeness, query each geo location independently.</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="f1233-149">При поиске в среде с поддержкой нескольких регионов невозможно динамическое группирование числовых уточнений.</span><span class="sxs-lookup"><span data-stu-id="f1233-149">Multi-geo search doesn't support dynamic bucketing for numerical refiners.</span></span></td>
<td align="left"><span data-ttu-id="f1233-150">Используйте <a href="https://docs.microsoft.com/sharepoint/dev/general-development/query-refinement-in-sharepoint">параметр дискретизировать</a> для числовых уточнений.</span><span class="sxs-lookup"><span data-stu-id="f1233-150">Use the <a href="https://docs.microsoft.com/sharepoint/dev/general-development/query-refinement-in-sharepoint">"Discretize" parameter</a> for numerical refiners.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="f1233-151">Идентификаторы документов</span><span class="sxs-lookup"><span data-stu-id="f1233-151">Document IDs</span></span></td>
<td align="left"><span data-ttu-id="f1233-152">При разработке поискового приложения, которое зависит от ИД документов, обратите внимание, что такие идентификаторы в среде с поддержкой нескольких регионов уникальны только для каждого отдельного географического расположения.</span><span class="sxs-lookup"><span data-stu-id="f1233-152">If you're developing a search-driven application that depends on document IDs, note that document IDs in a multi-geo environment aren't unique across geo locations, they are unique per geo location.</span></span></td>
<td align="left"><span data-ttu-id="f1233-153">Добавлен столбец, определяющий географическое расположение</span><span class="sxs-lookup"><span data-stu-id="f1233-153">We've added a column that identifies the geo location.</span></span> <span data-ttu-id="f1233-154">и позволяющий добиться уникальности.</span><span class="sxs-lookup"><span data-stu-id="f1233-154">Use this column to achieve uniqueness.</span></span> <span data-ttu-id="f1233-155">Этот столбец называется "Жеолокатионсаурце".</span><span class="sxs-lookup"><span data-stu-id="f1233-155">This column is named "GeoLocationSource".</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="f1233-156">Количество результатов</span><span class="sxs-lookup"><span data-stu-id="f1233-156">Number of results</span></span></td>
<td align="left"><span data-ttu-id="f1233-157">На странице результатов поиска отображаются объединенные данные из географических расположений (не более 500 результатов на одной странице).</span><span class="sxs-lookup"><span data-stu-id="f1233-157">The search results page shows combined results from the geo locations, but it's not possible to page beyond 500 results.</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="f1233-158">Гибридный поиск</span><span class="sxs-lookup"><span data-stu-id="f1233-158">Hybrid search</span></span></td>
<td align="left"><span data-ttu-id="f1233-159">В гибридной среде SharePoint с <a href="https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">облачным гибридным поиском</a> локальный контент добавляется в индекс Microsoft 365 центрального расположения.</span><span class="sxs-lookup"><span data-stu-id="f1233-159">In a hybrid SharePoint environment with <a href="https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">cloud hybrid search</a>,  on-premises content is added to the Microsoft 365 index of the central location.</span></span></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a><span data-ttu-id="f1233-160">Что не поддерживается при поиске в среде с несколькими регионами?</span><span class="sxs-lookup"><span data-stu-id="f1233-160">What's not supported for search in a multi-geo environment?</span></span>

<span data-ttu-id="f1233-161">Некоторые знакомые вам функции поиска в среде с несколькими регионами не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f1233-161">Some of the search features you might be familiar with, aren't supported in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f1233-162"><strong>Функция поиска</strong></span><span class="sxs-lookup"><span data-stu-id="f1233-162"><strong>Search feature</strong></span></span></th>
<th align="left"><span data-ttu-id="f1233-163"><strong>Примечание</strong></span><span class="sxs-lookup"><span data-stu-id="f1233-163"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="f1233-164">Проверка подлинности только для приложений</span><span class="sxs-lookup"><span data-stu-id="f1233-164">App-only authentication</span></span></td>
<td align="left"><span data-ttu-id="f1233-165">При поиске в среде с поддержкой нескольких регионов невозможна проверка подлинности только для приложений (привилегированный доступ из служб).</span><span class="sxs-lookup"><span data-stu-id="f1233-165">App-only authentication (privileged access from services) isn't supported in multi-geo search.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="f1233-166">Гостевые пользователи</span><span class="sxs-lookup"><span data-stu-id="f1233-166">Guest users</span></span></td>
<td align="left"><span data-ttu-id="f1233-167">Гостевые пользователи получают результаты только из того географического расположения, из которого они выполняют поиск.</span><span class="sxs-lookup"><span data-stu-id="f1233-167">Guest users only get results from the geo location that they're searching from.</span></span></td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a><span data-ttu-id="f1233-168">Каковы принципы поиска в среде с поддержкой нескольких регионов?</span><span class="sxs-lookup"><span data-stu-id="f1233-168">How does search work in a multi-geo environment?</span></span>

<span data-ttu-id="f1233-169">Все клиенты поиска взаимодействуют с индексами поиска, используя существующие REST API поиска SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f1233-169">All the search clients use the existing SharePoint Search REST APIs to interact with the search indexes.</span></span>

![Диаграмма, демонстрирующая способ взаимодействия REST API поиска SharePoint с индексами поиска](../media/configure-search-for-multi-geo-image1-1.png)

1. <span data-ttu-id="f1233-171">Клиент поиска вызывает конечную точку поиска REST с использованием свойства запроса EnableMultiGeoSearch = true.</span><span class="sxs-lookup"><span data-stu-id="f1233-171">A search client calls the Search REST endpoint with the query property EnableMultiGeoSearch= true.</span></span>
2. <span data-ttu-id="f1233-172">Запрос отправляется во все геообъекты, предусмотренные для клиента.</span><span class="sxs-lookup"><span data-stu-id="f1233-172">The query is sent to all geo locations in the tenant.</span></span>
3. <span data-ttu-id="f1233-173">Результаты поиска из каждого географического расположения объединяются и ранжируются.</span><span class="sxs-lookup"><span data-stu-id="f1233-173">Search results from each geo location are merged and ranked.</span></span>
4. <span data-ttu-id="f1233-174">Клиент получает объединенные результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="f1233-174">The client gets unified search results.</span></span>

<span data-ttu-id="f1233-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Обратите внимание, что результаты поиска не объединяются до тех пор, пока не будут получены данные из всех географических расположений.</span><span class="sxs-lookup"><span data-stu-id="f1233-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Notice that we don't merge the search results until we've received results from all the geo locations.</span></span> <span data-ttu-id="f1233-176">Это означает, что поиск в среде с поддержкой нескольких регионов выполняется с большей задержкой, чем поиск в среде с одним геообъектом.</span><span class="sxs-lookup"><span data-stu-id="f1233-176">This means that multi-geo searches have additional latency compared to searches in an environment with only one geo location.</span></span>

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a><span data-ttu-id="f1233-177">Настройка отображения в центре поиска результатов из всех географических расположений</span><span class="sxs-lookup"><span data-stu-id="f1233-177">Get a Search Center to show results from all geo locations</span></span>

<span data-ttu-id="f1233-178">Для каждого центра поиска предусмотрено несколько вертикалей, и каждую из них следует настраивать отдельно.</span><span class="sxs-lookup"><span data-stu-id="f1233-178">Each Search Center has several verticals and you have to set up each vertical individually.</span></span>

1. <span data-ttu-id="f1233-179">Убедитесь, что выполняете эти действия в учетной записи, у которой есть разрешение на изменение страницы результатов поиска и веб-части результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="f1233-179">Ensure that you perform these steps with an account that has permission to edit the search results page and the Search Result Web Part.</span></span>

2. <span data-ttu-id="f1233-180">Перейдите на страницу результатов поиска (см. [список](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) страниц результатов поиска).</span><span class="sxs-lookup"><span data-stu-id="f1233-180">Navigate to the search results page (see the [list](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) of search results pages)</span></span>

3. <span data-ttu-id="f1233-p112">Выберите вертикаль для настройки. В верхнем правом углу щелкните значок шестеренки **Параметры**, а затем выберите **Изменить страницу**. Откроется страница результатов поиска в режиме редактирования.</span><span class="sxs-lookup"><span data-stu-id="f1233-p112">Select the vertical to set up, click **Settings** gear icon in the upper, right corner, and then click **Edit Page**. The search results page opens in Edit mode.</span></span>

   ![Изменение выбора страницы в параметрах](../media/configure-search-for-multi-geo-image2.png)

4. <span data-ttu-id="f1233-184">В веб-части результатов поиска переместите указатель в верхний правый угол, щелкните стрелку, а затем в меню выберите **Изменить веб-часть**.</span><span class="sxs-lookup"><span data-stu-id="f1233-184">In the Search Results Web Part, move the pointer to the upper, right corner of the web part, click the arrow, and then click **Edit Web Part** on the menu.</span></span> <span data-ttu-id="f1233-185">Под лентой в верхней правой части страницы откроется область инструментов веб-части результатов поиска. </span><span class="sxs-lookup"><span data-stu-id="f1233-185">The Search Results Web Part tool pane opens under the ribbon in the top right of the page.</span></span>

   ![Изменение выбора веб-части](../media/configure-search-for-multi-geo-image3.png)

5. <span data-ttu-id="f1233-187">Чтобы в веб-части результатов поиска отображались результаты из всех геообъектов, в области инструментов веб-части выберите **Параметры** > **Параметры управления результатами** > **Отображение результатов с поддержкой нескольких регионов**.</span><span class="sxs-lookup"><span data-stu-id="f1233-187">In the Web Part tool pane, in the **Settings** section, under **Results control settings**, select **Show Multi-Geo results** to get the Search Results Web Part to show results from all geo locations.</span></span>

6. <span data-ttu-id="f1233-188">Чтобы сохранить изменения и закрыть область инструментов веб-части, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f1233-188">Click **OK** to save your change and close the Web Part tool pane.</span></span>

7. <span data-ttu-id="f1233-189">Проверьте изменения, внесенные в веб-часть результатов поиска, выбрав **Возврат** на вкладке "Страница" главного меню.</span><span class="sxs-lookup"><span data-stu-id="f1233-189">Check your changes to the Search Results Web Part by clicking **Check-In** on the Page tab of the main menu.</span></span>

8. <span data-ttu-id="f1233-190">Опубликуйте изменения, воспользовавшись ссылкой, предоставленной в примечании вверху страницы.</span><span class="sxs-lookup"><span data-stu-id="f1233-190">Publish the changes by using the link provided in the note at the top of the page.</span></span>

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a><span data-ttu-id="f1233-191">Настройка отображения в специальных поисковых приложениях результатов из всех или некоторых географических расположений</span><span class="sxs-lookup"><span data-stu-id="f1233-191">Get custom search applications to show results from all or some geo locations</span></span>

<span data-ttu-id="f1233-p114">Специальные поисковые приложения получают результаты из всех или некоторых географических расположений, указывая параметры запроса для REST API поиска SharePoint. В зависимости от этих параметров запрос развертывается для всех или некоторых геообъектов. Например, если нужно найти релевантные данные, отправив запрос только в подмножество географических расположений, можно выполнить развертывание запроса именно для них. Если запрос будет выполнен успешно, REST API поиска SharePoint возвратит данные отклика.</span><span class="sxs-lookup"><span data-stu-id="f1233-p114">Custom search applications get results from all, or some, geo locations by specifying query parameters with the request to the SharePoint Search REST API. Depending on the query parameters, the query is fanned out to all geo locations, or to some geo locations. For example, if you only need to query a subset of geo locations to find relevant information, you can control the fan out to only these. If the request succeeds, the SharePoint Search REST API returns response data.</span></span>

### <a name="requirement"></a><span data-ttu-id="f1233-196">Требование</span><span class="sxs-lookup"><span data-stu-id="f1233-196">Requirement</span></span>

<span data-ttu-id="f1233-p115">Для каждого географического расположения необходимо убедиться, что всем пользователям в организации предоставлено разрешение **на чтение** корневого веб-сайта (например, contoso**APAC**.sharepoint.com/ и contoso**EU**.sharepoint.com/). [Сведения о разрешениях](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span><span class="sxs-lookup"><span data-stu-id="f1233-p115">For each geo location, you must ensure that all users in the organization have been granted the **Read** permission level for the root website (for example contoso**APAC**.sharepoint.com/ and contoso**EU**.sharepoint.com/). [Learn about permissions](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span></span>

### <a name="query-parameters"></a><span data-ttu-id="f1233-199">Параметры запроса</span><span class="sxs-lookup"><span data-stu-id="f1233-199">Query parameters</span></span>

<span data-ttu-id="f1233-200">EnableMultiGeoSearch — это логическое значение, определяющее, должен ли запрос развертываться для индексов других геообъектов клиента с несколькими регионами.</span><span class="sxs-lookup"><span data-stu-id="f1233-200">EnableMultiGeoSearch - This is a Boolean value that specifies whether the query shall be fanned out to the indexes of other geo locations of the multi-geo tenant.</span></span> <span data-ttu-id="f1233-201">Чтобы выполнить развертывание запроса, задайте для этого параметра значение **true**. Чтобы не выполнять его, установите значение **false**.</span><span class="sxs-lookup"><span data-stu-id="f1233-201">Set it to **true** to fan out the query; **false** to not fan out the query.</span></span> <span data-ttu-id="f1233-202">Если не указать этот параметр, значением по умолчанию будет **false**, кроме случая выполнения вызова REST API для сайта, использующего шаблон корпоративного центра поиска, когда по умолчанию применяется значение **true**.</span><span class="sxs-lookup"><span data-stu-id="f1233-202">If you don't include this parameter, the default value is **false**, except when making a REST API call against a site which uses the Enterprise Search Center template, in this case the default value is **true**.</span></span> <span data-ttu-id="f1233-203">Если вы используете этот параметр в среде без поддержки нескольких регионов, он будет проигнорирован.</span><span class="sxs-lookup"><span data-stu-id="f1233-203">If you use the parameter in an environment that isn't multi-geo, the parameter is ignored.</span></span>

<span data-ttu-id="f1233-204">ClientType — строка.</span><span class="sxs-lookup"><span data-stu-id="f1233-204">ClientType - This is a string.</span></span> <span data-ttu-id="f1233-205">Введите для каждого поискового приложения уникальное имя клиента.</span><span class="sxs-lookup"><span data-stu-id="f1233-205">Enter a unique client name for each search application.</span></span> <span data-ttu-id="f1233-206">Если не указать этот параметр, развертывание запроса не будет выполнено для других геообъектов.</span><span class="sxs-lookup"><span data-stu-id="f1233-206">If you don't include this parameter, the query is not fanned out to other geo locations.</span></span>

<span data-ttu-id="f1233-207">MultiGeoSearchConfiguration — дополнительный список географических расположений клиента с поддержкой нескольких регионов. Он предназначен для развертывания запроса, когда параметру **EnableMultiGeoSearch** присвоено значение **true**.</span><span class="sxs-lookup"><span data-stu-id="f1233-207">MultiGeoSearchConfiguration - This is an optional list of which geo locations in the multi-geo tenant to fan the query out to when **EnableMultiGeoSearch** is **true**.</span></span> <span data-ttu-id="f1233-208">Если не указать этот параметр или его значение, развертывание запроса будет выполнено для всех географических расположений.</span><span class="sxs-lookup"><span data-stu-id="f1233-208">If you don't include this parameter, or leave it blank, the query is fanned out to all geo locations.</span></span> <span data-ttu-id="f1233-209">Для каждого географического расположения введите указанные ниже элементы в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="f1233-209">For each geo location, enter the following items, in JSON format:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f1233-210">Элемент</span><span class="sxs-lookup"><span data-stu-id="f1233-210">Item</span></span></th>
<th align="left"><span data-ttu-id="f1233-211">Описание</span><span class="sxs-lookup"><span data-stu-id="f1233-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="f1233-212">DataLocation</span><span class="sxs-lookup"><span data-stu-id="f1233-212">DataLocation</span></span></td>
<td align="left"><span data-ttu-id="f1233-213">Географическое расположение (например, NAM).</span><span class="sxs-lookup"><span data-stu-id="f1233-213">The geo location, for example NAM.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="f1233-214">EndPoint</span><span class="sxs-lookup"><span data-stu-id="f1233-214">EndPoint</span></span></td>
<td align="left"><span data-ttu-id="f1233-215">Конечная точка для подключения (например, https://contoso.sharepoint.com).</span><span class="sxs-lookup"><span data-stu-id="f1233-215">The endpoint to connect to, for example https://contoso.sharepoint.com</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="f1233-216">SourceId</span><span class="sxs-lookup"><span data-stu-id="f1233-216">SourceId</span></span></td>
<td align="left"><span data-ttu-id="f1233-217">GUID источника результатов, например B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span><span class="sxs-lookup"><span data-stu-id="f1233-217">The GUID of the result source, for example B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f1233-p119">Если опустить элемент DataLocation или EndPoint, а также если продублировать DataLocation, запрос будет выполнен с ошибкой. [Сведения о конечной точке геообъектов клиента можно получить с помощью Microsoft Graph](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-discovery).</span><span class="sxs-lookup"><span data-stu-id="f1233-p119">If you omit DataLocation or EndPoint, or if a DataLocation is duplicated, the request fails. [You can get information about the endpoint of a tenant's geo locations by using Microsoft Graph](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-discovery).</span></span>

### <a name="response-data"></a><span data-ttu-id="f1233-220">Данные отклика</span><span class="sxs-lookup"><span data-stu-id="f1233-220">Response data</span></span>

<span data-ttu-id="f1233-p120">MultiGeoSearchStatus — свойство, которое API поиска SharePoint возвращает в отклике на запрос. Значение этого свойства является строкой и предоставляет указанные ниже сведения о результатах, которые возвращает API поиска SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f1233-p120">MultiGeoSearchStatus – This is a property that the SharePoint Search API returns in response to a request. The value of the property is a string and gives the following information about the results that the SharePoint Search API returns:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f1233-223">Значение</span><span class="sxs-lookup"><span data-stu-id="f1233-223">Value</span></span></th>
<th align="left"><span data-ttu-id="f1233-224">Описание</span><span class="sxs-lookup"><span data-stu-id="f1233-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="f1233-225">Full</span><span class="sxs-lookup"><span data-stu-id="f1233-225">Full</span></span></td>
<td align="left"><span data-ttu-id="f1233-226">Полные результаты из <strong>всех</strong> географических расположений.</span><span class="sxs-lookup"><span data-stu-id="f1233-226">Full results from <strong>all</strong> the geo locations.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="f1233-227">Partial</span><span class="sxs-lookup"><span data-stu-id="f1233-227">Partial</span></span></td>
<td align="left"><span data-ttu-id="f1233-p121">Частичные результаты из одного или нескольких географических расположений. Такие результаты являются неполными из-за временной ошибки.</span><span class="sxs-lookup"><span data-stu-id="f1233-p121">Partial results from one or more geo locations. The results are incomplete due to a transient error.</span></span></td>
</tr>
</tbody>
</table>

### <a name="query-using-the-rest-service"></a><span data-ttu-id="f1233-230">Отправка запросов с помощью службы REST</span><span class="sxs-lookup"><span data-stu-id="f1233-230">Query using the REST service</span></span>

<span data-ttu-id="f1233-p122">Используя GET-запрос, нужно указать соответствующие параметры в URL-адресе. Параметры POST-запроса передаются в его теле в формате нотации объектов JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="f1233-p122">With a GET request, you specify the query parameters in the URL. With a POST request, you pass the query parameters in the body in JavaScript Object Notation (JSON) format.</span></span>

#### <a name="request-headers"></a><span data-ttu-id="f1233-233">Заголовки запросов</span><span class="sxs-lookup"><span data-stu-id="f1233-233">Request headers</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f1233-234">Имя</span><span class="sxs-lookup"><span data-stu-id="f1233-234">Name</span></span></th>
<th align="left"><span data-ttu-id="f1233-235">Значение</span><span class="sxs-lookup"><span data-stu-id="f1233-235">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="f1233-236">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f1233-236">Content-Type</span></span></td>
<td align="left"><span data-ttu-id="f1233-237">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="f1233-237">application/json;odata=verbose</span></span></td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="f1233-238">Пример GET-запроса, развертывание которого выполняется для **всех** геообъектов</span><span class="sxs-lookup"><span data-stu-id="f1233-238">Sample GET request that's fanned out to **all** geo locations</span></span>

<span data-ttu-id="f1233-239">HTTPS:// \<tenant\> / \_ API/Поиск/запрос? QueryText = ' SharePoint ' &свойства = ' енаблемултижеосеарч: true ' &ClientType = ' My \_ Client \_ ID '</span><span class="sxs-lookup"><span data-stu-id="f1233-239">https:// \<tenant\>/\_api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my\_client\_id'</span></span>

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a><span data-ttu-id="f1233-240">Пример GET-запроса, развертывание которого выполняется для **некоторых** геообъектов</span><span class="sxs-lookup"><span data-stu-id="f1233-240">Sample GET request to fan out to **some** geo locations</span></span>

<span data-ttu-id="f1233-241">HTTPS:// \<tenant\> / \_ API/Поиск/запрос? QueryText = ' site ' &ClientType = ' my_client_id ' &Properties = ' енаблемултижеосеарч: true, мултижеосеарчконфигуратион: [{расположение данных \\ : "тип" \\ , точка входа \\ : "HTTPS \\ ://contosoNAM.SharePoint.com" \\ , SourceID \\ : "B81EAB55-3140-4312-B0F4-9459D1B4FFEE"} \\ , {Location \\ : "Can" \\ , Endpoint \\ : "HTTPS \\ ://contosoCAN.SharePoint-DF.com"}] "</span><span class="sxs-lookup"><span data-stu-id="f1233-241">https:// \<tenant\>/\_api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation\\:"NAM"\\,Endpoint\\:"https\\://contosoNAM.sharepoint.com"\\,SourceId\\:"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"}\\,{DataLocation\\:"CAN"\\,Endpoint\\:"https\\://contosoCAN.sharepoint-df.com"}]'</span></span>

> [!NOTE]
> <span data-ttu-id="f1233-242">Перед запятыми и двоеточиями в списке геообъектов для свойства MultiGeoSearchConfiguration используется символ **обратной косой черты**.</span><span class="sxs-lookup"><span data-stu-id="f1233-242">Commas and colons in the list of geo locations for the MultiGeoSearchConfiguration property are preceded by the **backslash** character.</span></span> <span data-ttu-id="f1233-243">Это обусловлено тем, что запросы GET используют двоеточия для разделения свойств и запятые для разделения аргументов свойств.</span><span class="sxs-lookup"><span data-stu-id="f1233-243">This is because GET requests use colons to separate properties and commas to separate arguments of properties.</span></span> <span data-ttu-id="f1233-244">Без обратной косой черты в качестве экранирующего символа свойство MultiGeoSearchConfiguration будет распознаваться неправильно.</span><span class="sxs-lookup"><span data-stu-id="f1233-244">Without the backslash as an escape character, the MultiGeoSearchConfiguration property is interpreted wrongly.</span></span>

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="f1233-245">Пример POST-запроса, развертывание которого выполняется для **всех** геообъектов</span><span class="sxs-lookup"><span data-stu-id="f1233-245">Sample POST request that's fanned out to **all** geo locations</span></span>

```text
    {
    "request": {
            "__metadata": {
            "type": "Microsoft.Office.Server.Search.REST.SearchRequest"
        },
        "Querytext": "sharepoint",
        "Properties": {
            "results": [
                {
                    "Name": "EnableMultiGeoSearch",
                    "Value": {
                        "QueryPropertyValueTypeIndex": 3,
                        "BoolVal": true
                    }
                }
            ]
        },
        "ClientType": "my_client_id"
        }
    }
```

#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a><span data-ttu-id="f1233-246">Пример POST-запроса, развертывание которого выполняется для **некоторых** геообъектов</span><span class="sxs-lookup"><span data-stu-id="f1233-246">Sample POST request that's fanned out to **some** geo locations</span></span>

```text
    {
        "request": {
            "Querytext": "SharePoint",
            "ClientType": "my_client_id",
            "Properties": {
                "results": [
                    {
                        "Name": "EnableMultiGeoSearch",
                        "Value": {
                            "QueryPropertyValueTypeIndex": 3,
                            "BoolVal": true
                        }
                    },
                    {
                        "Name": "MultiGeoSearchConfiguration",
                        "Value": {
                        "StrVal": "[{\"DataLocation\":\"NAM\",\"Endpoint\":\"https://contoso.sharepoint.com\",\"SourceId\":\"B81EAB55-3140-4312-B0F4-9459D1B4FFEE\"},{\"DataLocation\":\"CAN\",\"Endpoint\":\"https://contosoCAN.sharepoint.com\"}]",
                            "QueryPropertyValueTypeIndex": 1
                        }
                    }
                ]
            }
        }
    }
```

### <a name="query-using-csom"></a><span data-ttu-id="f1233-247">Отправка запросов с помощью CSOM</span><span class="sxs-lookup"><span data-stu-id="f1233-247">Query using CSOM</span></span>

<span data-ttu-id="f1233-248">Пример CSOM-запроса, развертывание которого выполняется для **всех** геообъектов</span><span class="sxs-lookup"><span data-stu-id="f1233-248">Here's a sample CSOM query that's fanned out to **all** geo locations:</span></span>

```text
var keywordQuery = new KeywordQuery(ctx);
keywordQuery.QueryText = query.SearchQueryText;
keywordQuery.ClientType = <enter a string here>;
keywordQuery["EnableMultiGeoSearch"] = true;
```
