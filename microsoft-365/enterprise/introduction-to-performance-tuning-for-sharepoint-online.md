---
title: Общие сведения о настройке производительности для SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: В этой статье объясняется, какие конкретные аспекты необходимо учитывать при разработке страниц для лучшей производительности в SharePoint Online.
ms.openlocfilehash: d3a9dedbd5812774b81494af0f8defa5568f7dac
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693457"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="f691e-103">Общие сведения о настройке производительности для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="f691e-104">В этой статье объясняется, какие конкретные аспекты необходимо учитывать при разработке страниц для лучшей производительности в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f691e-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="f691e-105">Показатели SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-105">SharePoint Online metrics</span></span>

<span data-ttu-id="f691e-106">Следующие показатели для SharePoint Online предоставляют реальные данные о производительности:</span><span class="sxs-lookup"><span data-stu-id="f691e-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="f691e-107">Скорость загрузки страниц</span><span class="sxs-lookup"><span data-stu-id="f691e-107">How fast pages load</span></span>
    
- <span data-ttu-id="f691e-108">Количество необходимых кругов на страницу</span><span class="sxs-lookup"><span data-stu-id="f691e-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="f691e-109">Проблемы со службой</span><span class="sxs-lookup"><span data-stu-id="f691e-109">Issues with the service</span></span>
    
- <span data-ttu-id="f691e-110">Другие причины ухудшения производительности</span><span class="sxs-lookup"><span data-stu-id="f691e-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="f691e-111">Выводы, полученные из-за данных</span><span class="sxs-lookup"><span data-stu-id="f691e-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="f691e-112">Данные подсказывает нам:</span><span class="sxs-lookup"><span data-stu-id="f691e-112">The data tells us:</span></span>
  
- <span data-ttu-id="f691e-113">Большинство страниц хорошо работает в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f691e-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="f691e-114">Ненастройные страницы загружаются очень быстро.</span><span class="sxs-lookup"><span data-stu-id="f691e-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="f691e-115">OneDrive для бизнеса, сайты группы и системные страницы, такие как _layouts и т. д., быстро загружаются.</span><span class="sxs-lookup"><span data-stu-id="f691e-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="f691e-116">Загрузка самых медленных 1% страниц SharePoint Online составляет более 5000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="f691e-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="f691e-117">Одним из простых тестов производительности может быть измерение производительности путем сравнения времени загрузки собственного портала с временем загрузки домашней страницы OneDrive для бизнеса, так как в ней используется мало пользовательских функций.</span><span class="sxs-lookup"><span data-stu-id="f691e-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="f691e-118">Зачастую это первый шаг, который будет запросить у вас при устранении неполадок с производительностью сети.</span><span class="sxs-lookup"><span data-stu-id="f691e-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="f691e-119">Использование стандартной учетной записи пользователя при проверке производительности</span><span class="sxs-lookup"><span data-stu-id="f691e-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="f691e-120">Администратор, владелец сайта, редактор или участник относятся к дополнительным группам безопасности, имеют дополнительные разрешения и, следовательно, имеют дополнительные элементы, которые SharePoint загружает на страницу.</span><span class="sxs-lookup"><span data-stu-id="f691e-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="f691e-121">Это применимо к локальной sharePoint и SharePoint Online, но в локальном сценарии различия будут не так легко заметить, как в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f691e-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="f691e-122">Чтобы правильно оценить, как страница будет работать для пользователей, следует использовать стандартную учетную запись пользователя, чтобы избежать загрузки элементов управления для авторизации и дополнительного трафика, связанного с группами безопасности.</span><span class="sxs-lookup"><span data-stu-id="f691e-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="f691e-123">Категории подключений для настройки производительности</span><span class="sxs-lookup"><span data-stu-id="f691e-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="f691e-124">Связи между сервером и пользователем можно классифицировать на три основных компонента.</span><span class="sxs-lookup"><span data-stu-id="f691e-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="f691e-125">Учитывайте эти моменты при разработке страниц SharePoint Online, чтобы получить представление о времени загрузки.</span><span class="sxs-lookup"><span data-stu-id="f691e-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="f691e-126">**Сервер** Серверы, которые корпорация Майкрософт размещена в центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="f691e-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="f691e-127">**Сеть** Сеть Майкрософт, Интернет и ваша локальной сеть между центром обработки данных и вашими пользователями.</span><span class="sxs-lookup"><span data-stu-id="f691e-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="f691e-128">**Браузер** Место загрузки страницы.</span><span class="sxs-lookup"><span data-stu-id="f691e-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="f691e-129">В этих трех подключениях обычно есть пять причин, которые вызывают 95 % медленных страниц.</span><span class="sxs-lookup"><span data-stu-id="f691e-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="f691e-130">Каждая из этих причин обсуждается в этой статье:</span><span class="sxs-lookup"><span data-stu-id="f691e-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="f691e-131">Проблемы навигации</span><span class="sxs-lookup"><span data-stu-id="f691e-131">Navigation issues</span></span>
    
- <span data-ttu-id="f691e-132">Свернутый контент</span><span class="sxs-lookup"><span data-stu-id="f691e-132">Content roll up</span></span>
    
- <span data-ttu-id="f691e-133">Большие файлы</span><span class="sxs-lookup"><span data-stu-id="f691e-133">Large files</span></span>
    
- <span data-ttu-id="f691e-134">Большое количество запросов к серверу</span><span class="sxs-lookup"><span data-stu-id="f691e-134">Many requests to the server</span></span>
    
- <span data-ttu-id="f691e-135">Обработка веб-части</span><span class="sxs-lookup"><span data-stu-id="f691e-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="f691e-136">Подключение к серверу</span><span class="sxs-lookup"><span data-stu-id="f691e-136">Server connection</span></span>

<span data-ttu-id="f691e-137">Многие проблемы, влияющие на производительность локальной точки SharePoint, также применимы к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f691e-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="f691e-138">Как и ожидаось, вы имеете гораздо больше контроля над тем, как серверы выполняются с локальной sharePoint.</span><span class="sxs-lookup"><span data-stu-id="f691e-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="f691e-139">В SharePoint Online все немного по-другому.</span><span class="sxs-lookup"><span data-stu-id="f691e-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="f691e-140">Чем больше работы вы делаете на сервере, тем дольше требуется отрисовка страницы.</span><span class="sxs-lookup"><span data-stu-id="f691e-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="f691e-141">В SharePoint самыми главными злоумышленниками в этом отношении являются сложные страницы с несколькими веб-частями.</span><span class="sxs-lookup"><span data-stu-id="f691e-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="f691e-142">Локальное sharePoint Server</span><span class="sxs-lookup"><span data-stu-id="f691e-142">SharePoint Server on-premises</span></span>
  
![Снимок экрана: локальный сервер](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="f691e-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-144">SharePoint Online</span></span>
  
![Снимок экрана: сервер в сети](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="f691e-146">В SharePoint Online некоторые запросы страниц могут вызывать несколько серверов.</span><span class="sxs-lookup"><span data-stu-id="f691e-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="f691e-147">Вы можете получить матрицу запросов между серверами для отдельного запроса.</span><span class="sxs-lookup"><span data-stu-id="f691e-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="f691e-148">Эти взаимодействия являются дорогостоящими с точки зрения загрузки страницы и замедляют процесс.</span><span class="sxs-lookup"><span data-stu-id="f691e-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="f691e-149">Примеры взаимодействия между сервером и сервером:</span><span class="sxs-lookup"><span data-stu-id="f691e-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="f691e-150">Веб-SQL серверов</span><span class="sxs-lookup"><span data-stu-id="f691e-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="f691e-151">Веб-серверы приложений</span><span class="sxs-lookup"><span data-stu-id="f691e-151">Web to application servers</span></span>
    
<span data-ttu-id="f691e-152">Еще одно, что может замедлить взаимодействие с сервером, — промахи кэша.</span><span class="sxs-lookup"><span data-stu-id="f691e-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="f691e-153">В отличие от локальной точки SharePoint существует очень большой вероятность того, что вы будете работать на том же сервере для страницы, которую вы уже посещали; это делает кэш объектов устаревшим.</span><span class="sxs-lookup"><span data-stu-id="f691e-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="f691e-154">Подключение к сети </span><span class="sxs-lookup"><span data-stu-id="f691e-154">Network connection</span></span>

<span data-ttu-id="f691e-155">В локальной sharePoint, которая не использует WAN, можно использовать высокоскоростное подключение между центрами обработки данных и конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="f691e-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="f691e-156">Как правило, с точки зрения сети управление с точки зрения сети является простым.</span><span class="sxs-lookup"><span data-stu-id="f691e-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="f691e-157">В SharePoint Online следует учитывать еще несколько факторов. Например:</span><span class="sxs-lookup"><span data-stu-id="f691e-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="f691e-158">Сеть Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f691e-158">The Microsoft network</span></span>
    
- <span data-ttu-id="f691e-159">Интернет</span><span class="sxs-lookup"><span data-stu-id="f691e-159">The Internet</span></span>
    
- <span data-ttu-id="f691e-160">The ISP</span><span class="sxs-lookup"><span data-stu-id="f691e-160">The ISP</span></span>
    
<span data-ttu-id="f691e-161">Независимо от используемой версии SharePoint (и сети) в сети обычно используются следующие точки:</span><span class="sxs-lookup"><span data-stu-id="f691e-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="f691e-162">Большие полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="f691e-162">Large payload</span></span>
    
- <span data-ttu-id="f691e-163">Много файлов</span><span class="sxs-lookup"><span data-stu-id="f691e-163">Many files</span></span>
    
- <span data-ttu-id="f691e-164">Большое физическое расстояние до сервера</span><span class="sxs-lookup"><span data-stu-id="f691e-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="f691e-165">Одной из функций, которую можно использовать в SharePoint Online, является сеть доставки содержимого (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="f691e-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="f691e-166">CdN — это, по сути, распределенная коллекция серверов, развернутых в нескольких центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="f691e-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="f691e-167">С помощью сети CDN контент на страницах может быть находится на сервере рядом с клиентом, даже если клиент находится далеко от сервера SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="f691e-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="f691e-168">В будущем корпорация Майкрософт будет использовать эту функцию для хранения локальных экземпляров страниц, которые невозможно настроить, например домашней страницы администратора SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f691e-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="f691e-169">Дополнительные сведения о сетях ДОСТАВКИ содержимого см. в сетях [доставки содержимого.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="f691e-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="f691e-170">Что-то, о чем вам необходимо знать, но, возможно, не удастся многое сделать, — это скорость подключения вашего isP.</span><span class="sxs-lookup"><span data-stu-id="f691e-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="f691e-171">Простое средство тестирования скорости покажет вам скорость подключения.</span><span class="sxs-lookup"><span data-stu-id="f691e-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="f691e-172">Подключение к браузеру</span><span class="sxs-lookup"><span data-stu-id="f691e-172">Browser connection</span></span>

<span data-ttu-id="f691e-173">Существует несколько факторов, которые следует учитывать при работе с веб-браузерами с точки зрения производительности.</span><span class="sxs-lookup"><span data-stu-id="f691e-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="f691e-174">Просмотр сложных страниц влияет на производительность.</span><span class="sxs-lookup"><span data-stu-id="f691e-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="f691e-175">В большинстве браузеров имеется только небольшой кэш (около 90 МБ), а средняя веб-страница обычно составляет около 1,6 МБ.</span><span class="sxs-lookup"><span data-stu-id="f691e-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="f691e-176">Это не займет много времени.</span><span class="sxs-lookup"><span data-stu-id="f691e-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="f691e-177">Кроме того, может возникнуть проблема с пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="f691e-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="f691e-178">Например, если пользователь смотрит видео в другом сеансе, это повлияет на производительность страницы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f691e-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="f691e-179">Хотя вы не можете запретить пользователям потоковую передачу мультимедиа, вы можете управлять тем, как страница будет загружаться для пользователей.</span><span class="sxs-lookup"><span data-stu-id="f691e-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="f691e-180">Ознакомьтесь со следующими статьями о различных методах настройки страниц SharePoint Online и других практических методиках, которые помогут вам достичь оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="f691e-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="f691e-181">Параметры навигации для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="f691e-182">Использование средства диагностики страниц для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="f691e-183">Оптимизация изображений для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="f691e-184">Задержка при загрузке изображений и JavaScript-файлов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="f691e-185">Минификация и объединение в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="f691e-186">Использование сети доставки содержимого Office 365 с SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="f691e-187">Использование веб-части поиска контента вместо веб-части "Запрос содержимого" для повышения производительности в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="f691e-188">Планирование и тестирование загрузки SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="f691e-189">Диагностика проблем производительности в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="f691e-190">Использование кэша объектов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="f691e-191">Как избежать регулирования количества запросов или блокировки в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f691e-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](https://msdn.microsoft.com/library/office/dn889829.aspx)
    

