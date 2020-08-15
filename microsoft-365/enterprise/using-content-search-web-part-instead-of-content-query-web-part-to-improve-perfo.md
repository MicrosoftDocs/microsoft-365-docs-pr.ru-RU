---
title: Использование веб-части поиска контента вместо веб-части "Запрос контента" для улучшения производительности в SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
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
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: Узнайте, как повысить производительность, заменив веб-часть "запрос содержимого" на веб-часть "поиск контента" в SharePoint Server 2013 и SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693557"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a><span data-ttu-id="06477-103">Использование веб-части поиска контента вместо веб-части "Запрос контента" для улучшения производительности в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="06477-103">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>

<span data-ttu-id="06477-104">В этой статье описывается, как повысить производительность, заменив веб-часть "запрос содержимого" на веб-часть "поиск контента" в SharePoint Server 2013 и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="06477-104">This article describes how to increase performance by replacing the Content Query Web Part with the Content Search Web Part in SharePoint Server 2013 and SharePoint Online.</span></span>
  
<span data-ttu-id="06477-105">Одной из самых мощных новых функций SharePoint Server 2013 и SharePoint Online является веб-часть поиска контента (CSWP).</span><span class="sxs-lookup"><span data-stu-id="06477-105">One of the most powerful new features of SharePoint Server 2013 and SharePoint Online is the Content Search Web Part (CSWP).</span></span> <span data-ttu-id="06477-106">Эта веб-часть использует индекс поиска для быстрого извлечения результатов, отображаемых для пользователя.</span><span class="sxs-lookup"><span data-stu-id="06477-106">This Web Part uses the search index to quickly retrieve results which are shown to the user.</span></span> <span data-ttu-id="06477-107">Используйте веб-часть "поиск контента", а не веб-часть "запрос содержимого" (CQWP) на страницах, чтобы увеличить производительность для пользователей.</span><span class="sxs-lookup"><span data-stu-id="06477-107">Use the Content Search Web Part instead of the Content Query Web Part (CQWP) in your pages to improve performance for your users.</span></span>
  
<span data-ttu-id="06477-108">Использование веб-части поиска контента по сравнению с веб-частью "запрос содержимого" почти всегда приводит к значительному повышению производительности загрузки страниц в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="06477-108">Using a Content Search Web Part over a Content Query Web Part will almost always result in significantly better page load performance on SharePoint Online.</span></span> <span data-ttu-id="06477-109">Чтобы получить правильный запрос, существует немного дополнительная настройка, но повышение производительности повышает производительность и довольные пользователи.</span><span class="sxs-lookup"><span data-stu-id="06477-109">There is a little additional configuration to get the right query, but the rewards are improved performance and happier users.</span></span>
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a><span data-ttu-id="06477-110">Сравнение повышения производительности с использованием веб-части "поиск контента" вместо веб-части "Запрос контента"</span><span class="sxs-lookup"><span data-stu-id="06477-110">Comparing the performance gain you get from using Content Search Web Part instead of Content Query Web Part</span></span>

<span data-ttu-id="06477-111">В следующих примерах показано снижение производительности, которое может быть получено при использовании веб-части "поиск контента" вместо веб-части "запрос содержимого".</span><span class="sxs-lookup"><span data-stu-id="06477-111">The following examples show the relative performance gains you may receive when you use a Content Search Web Part instead of a Content Query Web Part.</span></span> <span data-ttu-id="06477-112">Эти эффекты более очевидны с помощью сложной структуры сайта и очень широкого спектра запросов к содержимому.</span><span class="sxs-lookup"><span data-stu-id="06477-112">The effects are more obvious with a complex site structure and very broad content queries.</span></span>
  
<span data-ttu-id="06477-113">Этот пример сайта имеет следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="06477-113">This example site has the following characteristics:</span></span>
  
- <span data-ttu-id="06477-114">8 уровней дочерних сайтов.</span><span class="sxs-lookup"><span data-stu-id="06477-114">8 levels of subsites.</span></span>
    
- <span data-ttu-id="06477-115">Списки, использующие настраиваемый тип контента "фруктов".</span><span class="sxs-lookup"><span data-stu-id="06477-115">Lists using a custom "fruit" content type.</span></span>
    
- <span data-ttu-id="06477-116">В веб-части Запрос контента является широким, возвращая все элементы с типом контента "фруктов".</span><span class="sxs-lookup"><span data-stu-id="06477-116">In the Web Part, the content query is broad, returning all items with the content type of "fruit".</span></span>
    
- <span data-ttu-id="06477-117">В этом примере используются только элементы 50 на 8 сайтах.</span><span class="sxs-lookup"><span data-stu-id="06477-117">The example only uses 50 items across the 8 sites.</span></span> <span data-ttu-id="06477-118">Эти эффекты станут еще более выраженными для сайтов с большим содержимым.</span><span class="sxs-lookup"><span data-stu-id="06477-118">The effects will be even more pronounced for sites with more content.</span></span>
    
<span data-ttu-id="06477-119">Ниже приведен снимок результатов веб-части "запрос содержимого".</span><span class="sxs-lookup"><span data-stu-id="06477-119">Here is a screen shot of the results of the Content Query Web Part.</span></span>
  
![Рисунок: запрос контента для веб-части](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
<span data-ttu-id="06477-121">В Internet Explorer используйте вкладку **сеть** в средствах разработчика F12, чтобы просмотреть сведения о заголовке отклика.</span><span class="sxs-lookup"><span data-stu-id="06477-121">In Internet Explorer, use the **Network** tab of the F12 developer tools to look at the details for the response header.</span></span> <span data-ttu-id="06477-122">На следующем снимке экрана значение **SPRequestDuration** для этой страницы загружается 924 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="06477-122">In the following screen shot, the value for the **SPRequestDuration** for this page load is 924 milliseconds.</span></span> 
  
![Снимок экрана со значением длительности запроса (924)](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 <span data-ttu-id="06477-124">**SPRequestDuration** указывает объем трудозатрат, выполняемых на сервере для подготовки страницы.</span><span class="sxs-lookup"><span data-stu-id="06477-124">**SPRequestDuration** indicates the amount of work that is done on the server to prepare the page.</span></span> <span data-ttu-id="06477-125">Переключение контента по веб-частям запроса с контентом с помощью веб-частей поиска значительно сокращает время, необходимое для отображения страницы.</span><span class="sxs-lookup"><span data-stu-id="06477-125">Switching Content by Query Web Parts with Content by Search Web Parts dramatically reduces the time it takes to render the page.</span></span> <span data-ttu-id="06477-126">В отличие от того, что страница с эквивалентной веб-частью поиска контента возвращает такое же количество результатов, значение **SPRequestDuration** равно 106 миллисекунд, как показано на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="06477-126">By contrast, a page with an equivalent Content Search Web Part, returning the same number of results has an **SPRequestDuration** value of 106 milliseconds as shown in this screen shot:</span></span> 
  
![Снимок экрана со значением длительности запроса (106)](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a><span data-ttu-id="06477-128">Добавление веб-части поиска контента в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="06477-128">Adding a Content Search Web Part in SharePoint Online</span></span>

<span data-ttu-id="06477-129">Добавление веб-части поиска контента очень похоже на стандартную веб-часть "запрос содержимого".</span><span class="sxs-lookup"><span data-stu-id="06477-129">Adding a Content Search Web Part is very similar to a regular Content Query Web Part.</span></span> <span data-ttu-id="06477-130">В разделе  *"Добавление веб-части поиска контента"*  в разделе [Настройка веб-части поиска контента в SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span><span class="sxs-lookup"><span data-stu-id="06477-130">See the section  *"Add a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a><span data-ttu-id="06477-131">Создание правого запроса поиска для веб-части поиска контента</span><span class="sxs-lookup"><span data-stu-id="06477-131">Creating the right search query for your Content Search Web Part</span></span>

<span data-ttu-id="06477-132">После добавления веб-части "поиск контента" вы можете уточнить поиск и возвратить нужные элементы.</span><span class="sxs-lookup"><span data-stu-id="06477-132">Once you have added a Content Search Web Part, you can refine the search and return the items you want.</span></span> <span data-ttu-id="06477-133">Подробные инструкции по выполнению этой процедуры приведены в разделе  *"Отображение содержимого путем настройки расширенного запроса в веб-части" поиск контента "*  в SharePoint" [Настройка веб-части "поиск контента" в SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span><span class="sxs-lookup"><span data-stu-id="06477-133">For detailed instructions on how to do this, see the section,  *"Display content by configuring an advanced query in a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="query-building-and-testing-tool"></a><span data-ttu-id="06477-134">Средство построения и тестирования запросов</span><span class="sxs-lookup"><span data-stu-id="06477-134">Query building and testing tool</span></span>

<span data-ttu-id="06477-135">Для создания и тестирования сложных запросов в средстве поиска обратитесь к разделу [поисковый запрос](https://sp2013searchtool.codeplex.com/) на сайте CodePlex.</span><span class="sxs-lookup"><span data-stu-id="06477-135">For a tool to build and test complex queries, see the [Search Query Tool](https://sp2013searchtool.codeplex.com/) on Codeplex.</span></span> 
  

