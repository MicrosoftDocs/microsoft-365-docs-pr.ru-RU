---
title: Использование кэша объектов в SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: В этой статье объясняется разница между использованием кэша объектов в локальной sharePoint Server 2013 и SharePoint Online.
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696483"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a><span data-ttu-id="30f26-103">Использование кэша объектов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="30f26-103">Using the object cache with SharePoint Online</span></span>

<span data-ttu-id="30f26-104">В этой статье объясняется разница между использованием кэша объектов в локальной sharePoint Server 2013 и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="30f26-104">This article explains the difference between using the object cache in SharePoint Server 2013 on-premises and SharePoint Online.</span></span>
  
<span data-ttu-id="30f26-105">В развертывании SharePoint Online существует значительное отрицательное влияние на кэш объектов.</span><span class="sxs-lookup"><span data-stu-id="30f26-105">There is significant negative impact of relying on the object cache in SharePoint Online deployment.</span></span> <span data-ttu-id="30f26-106">Любая зависимость от кэша объектов в SharePoint Online снизит надежность страницы.</span><span class="sxs-lookup"><span data-stu-id="30f26-106">Any dependency on object cache in SharePoint Online will reduce the reliability of your page.</span></span> 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a><span data-ttu-id="30f26-107">Как работает кэш объектов SharePoint Online и SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="30f26-107">How the SharePoint Online and SharePoint Server 2013 object cache works</span></span>

<span data-ttu-id="30f26-108">Когда SharePoint Server 2013 находится в локальной сети, у клиента есть частные серверы переднего сервера, на которые находится кэш объектов.</span><span class="sxs-lookup"><span data-stu-id="30f26-108">When SharePoint Server 2013 is hosted on-premises, the customer has private front-end web servers that host the object cache.</span></span> <span data-ttu-id="30f26-109">Это означает, что кэш выделен для одного клиента и ограничен только объемом доступной памяти и выделенным для кэша объектов.</span><span class="sxs-lookup"><span data-stu-id="30f26-109">This means the cache is dedicated to one customer and is only limited by how much memory is available and allocated to the object cache.</span></span> <span data-ttu-id="30f26-110">Так как в локальном сценарии обслуживается только один клиент, на серверах переднего сервера обычно есть пользователи, которые снова и снова запрашивают один и тот же сайт.</span><span class="sxs-lookup"><span data-stu-id="30f26-110">Because only one customer is served in the on-premises scenario the front-end web servers typically have users making requests to the same sites over and over.</span></span> <span data-ttu-id="30f26-111">Это означает, что кэш быстро заполнен и остается полным результатов запроса списка и объектов SharePoint, которые пользователи запрашивают регулярно.</span><span class="sxs-lookup"><span data-stu-id="30f26-111">This means that the cache gets full quickly and remains full of the list query results and SharePoint objects that your users are requesting on a regular basis.</span></span>
  
![Показывает трафик и нагрузку на локальные веб-серверы переднего плана](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
<span data-ttu-id="30f26-113">В результате при втором посещении страницы время загрузки страницы улучшается.</span><span class="sxs-lookup"><span data-stu-id="30f26-113">As a result, the second time a user visits a page, the page load time improves.</span></span> <span data-ttu-id="30f26-114">После не менее четырех нагрузок одной страницы страница кэшется на всех веб-серверах переднего уровня.</span><span class="sxs-lookup"><span data-stu-id="30f26-114">After a minimum of four loads of the same page, the page is cached on all of the front-end web servers.</span></span>
  
<span data-ttu-id="30f26-115">С другой стороны, в SharePoint Online существует намного больше серверов, но и намного больше сайтов.</span><span class="sxs-lookup"><span data-stu-id="30f26-115">In contrast, in SharePoint Online there are many more servers but also many more sites.</span></span> <span data-ttu-id="30f26-116">Каждый пользователь может подключаться к разным интерфейсным веб-серверам, кэш которых не заполнен.</span><span class="sxs-lookup"><span data-stu-id="30f26-116">Each user may connect to a different front-end web server that doesn't have the cache populated.</span></span> <span data-ttu-id="30f26-117">Или, возможно, кэш заполняется для сервера, но следующий пользователь на этом интерфейсном веб-сервере запрашивает страницу с другого сайта.</span><span class="sxs-lookup"><span data-stu-id="30f26-117">Or, perhaps the cache does get populated for a server, but the next user to that front-end web server requests a page from a different site.</span></span> <span data-ttu-id="30f26-118">Или, даже если следующий пользователь запросит ту же страницу, что и во время предыдущего посещения, он балансирует нагрузку на другой интерфейсный веб-сервер, на который эта страница не есть в кэше.</span><span class="sxs-lookup"><span data-stu-id="30f26-118">Or, even if the next user requests the same page as on their previous visit, they are load-balanced to a different front-end web server that doesn't have that page in its cache.</span></span> <span data-ttu-id="30f26-119">В последнем случае кэшинг не помогает пользователям.</span><span class="sxs-lookup"><span data-stu-id="30f26-119">In this last case, caching doesn't help the users at all.</span></span>
  
<span data-ttu-id="30f26-120">На следующем рисунке каждая точка представляет страницу, запрашиваемую пользователем, и ее кэш.</span><span class="sxs-lookup"><span data-stu-id="30f26-120">In the following figure, each dot represents a page that a user is requesting and where it cached.</span></span> <span data-ttu-id="30f26-121">Различные цвета представляют различные клиенты, которые совместно используют инфраструктуру SaaS.</span><span class="sxs-lookup"><span data-stu-id="30f26-121">Different colors represent different customers making shared use of the SaaS infrastructure.</span></span>
  
![Показывает результаты кэширования объектов в SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
<span data-ttu-id="30f26-123">Как видно из схемы, вероятность того, что какой-либо пользователь нападет на сервер с кэшной версией своей страницы, ниже.</span><span class="sxs-lookup"><span data-stu-id="30f26-123">As you can see from the diagram, the chances of any given user hitting a server with the cached version of their page are slim.</span></span> <span data-ttu-id="30f26-124">Кроме того, из-за большой пропускной способности и того, что серверы совместно размещены между многими сайтами, кэш не длится долго, так как доступно только столько места для кэшинга.</span><span class="sxs-lookup"><span data-stu-id="30f26-124">Also, due to the large throughput and fact that the servers are shared between many sites, the cache doesn't last long since there is only so much space for caching available.</span></span>
  
<span data-ttu-id="30f26-125">По всем этим причинам получение пользователями кэшных объектов не является эффективным способом обеспечения качественного пользовательского интерфейса и времени загрузки страниц в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="30f26-125">For all of these reasons, relying on users getting cached objects is not an effective way to ensure a quality user experience and page load times in SharePoint Online.</span></span>
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a><span data-ttu-id="30f26-126">Если мы не можем полагаться на кэш объектов для повышения производительности в SharePoint Online, что мы используем вместо этого?</span><span class="sxs-lookup"><span data-stu-id="30f26-126">If we can't rely on the object cache to improve performance in SharePoint Online, what do we use instead?</span></span>

<span data-ttu-id="30f26-127">Так как не следует использовать кэширование в SharePoint Online, следует оценить альтернативные подходы к проектированию для настроек SharePoint, которые используют кэш объектов.</span><span class="sxs-lookup"><span data-stu-id="30f26-127">Since you shouldn't rely on caching in SharePoint Online, you should evaluate alternative design approaches for SharePoint customizations that use the object cache.</span></span> <span data-ttu-id="30f26-128">Это означает использование подходов для проблем производительности, которые не зависят от кэшинга объектов, чтобы дать пользователям хорошие результаты.</span><span class="sxs-lookup"><span data-stu-id="30f26-128">This means using approaches for performance issues which do not rely on the object caching in order to produce good results for users.</span></span> <span data-ttu-id="30f26-129">Это описано в некоторых других статьях этой серии, в том числе:</span><span class="sxs-lookup"><span data-stu-id="30f26-129">This is described in some of the other articles in this series and include:</span></span>
  
- [<span data-ttu-id="30f26-130">Параметры навигации для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="30f26-130">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="30f26-131">Минификация и объединение в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="30f26-131">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="30f26-132">Использование сети доставки содержимого Office 365 с SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="30f26-132">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="30f26-133">Задержка при загрузке изображений и JavaScript-файлов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="30f26-133">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

