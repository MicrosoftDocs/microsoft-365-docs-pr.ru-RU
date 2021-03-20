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
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909742"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="387a4-103">Общие сведения о настройке производительности для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="387a4-104">В этой статье объясняется, какие конкретные аспекты необходимо учитывать при разработке страниц для лучшей производительности в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="387a4-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="387a4-105">Метрик SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-105">SharePoint Online metrics</span></span>

<span data-ttu-id="387a4-106">Следующие широкие показатели для SharePoint Online предоставляют реальные данные о производительности:</span><span class="sxs-lookup"><span data-stu-id="387a4-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="387a4-107">Скорость загрузки страниц</span><span class="sxs-lookup"><span data-stu-id="387a4-107">How fast pages load</span></span>
    
- <span data-ttu-id="387a4-108">Сколько разных поездок требуется на страницу</span><span class="sxs-lookup"><span data-stu-id="387a4-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="387a4-109">Проблемы со службой</span><span class="sxs-lookup"><span data-stu-id="387a4-109">Issues with the service</span></span>
    
- <span data-ttu-id="387a4-110">Другие вещи, которые вызывают ухудшение производительности</span><span class="sxs-lookup"><span data-stu-id="387a4-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="387a4-111">Выводы, сделанные из-за данных</span><span class="sxs-lookup"><span data-stu-id="387a4-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="387a4-112">Данные говорят нам:</span><span class="sxs-lookup"><span data-stu-id="387a4-112">The data tells us:</span></span>
  
- <span data-ttu-id="387a4-113">Большинство страниц хорошо выполняются в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="387a4-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="387a4-114">Не настраиваемые страницы загружаются очень быстро.</span><span class="sxs-lookup"><span data-stu-id="387a4-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="387a4-115">OneDrive для бизнеса, сайты команд и страницы системы, такие как _layouts и т.д., быстро загружаются.</span><span class="sxs-lookup"><span data-stu-id="387a4-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="387a4-116">Для загрузки самых медленных 1% страниц SharePoint Online требуется более 5000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="387a4-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="387a4-117">Один простой тест, который можно использовать для измерения производительности, сравнивая время загрузки собственного портала с временем загрузки домашней страницы OneDrive для бизнеса, так как она использует несколько настраиваемых функций.</span><span class="sxs-lookup"><span data-stu-id="387a4-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="387a4-118">Это часто будет первым шагом, который поддержка попросит вас завершить при устранении неполадок с производительностью сети.</span><span class="sxs-lookup"><span data-stu-id="387a4-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="387a4-119">Использование стандартной учетной записи пользователя при проверке производительности</span><span class="sxs-lookup"><span data-stu-id="387a4-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="387a4-120">Администратор коллекции сайтов, владелец сайта, редактор или участник относятся к дополнительным группам безопасности, имеют дополнительные разрешения и, следовательно, имеют дополнительные элементы, загружающие SharePoint на страницу.</span><span class="sxs-lookup"><span data-stu-id="387a4-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="387a4-121">Это применимо к локальной sharePoint и SharePoint Online, но в локальном сценарии различия будут не так легко заметить, как в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="387a4-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="387a4-122">Чтобы правильно оценить, как будет работать страница для пользователей, следует использовать стандартную учетную запись пользователя, чтобы избежать загрузки элементов управления авторизации и дополнительного трафика, связанного с группами безопасности.</span><span class="sxs-lookup"><span data-stu-id="387a4-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="387a4-123">Категории подключения для настройки производительности</span><span class="sxs-lookup"><span data-stu-id="387a4-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="387a4-124">Связи между сервером и пользователем можно классифицировать на три основных компонента.</span><span class="sxs-lookup"><span data-stu-id="387a4-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="387a4-125">Рассмотрите их при разработке страниц SharePoint Online, чтобы получить представление о времени нагрузки.</span><span class="sxs-lookup"><span data-stu-id="387a4-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="387a4-126">**Сервер** Серверы, на которые Майкрософт размещены в центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="387a4-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="387a4-127">**Сеть** Сеть Майкрософт, Интернет и локальное подключение между центром обработки данных и пользователями.</span><span class="sxs-lookup"><span data-stu-id="387a4-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="387a4-128">**Браузер** Загрузка страницы.</span><span class="sxs-lookup"><span data-stu-id="387a4-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="387a4-129">В этих трех подключениях обычно существует пять причин, которые вызывают 95% медленных страниц.</span><span class="sxs-lookup"><span data-stu-id="387a4-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="387a4-130">Каждая из этих причин обсуждается в этой статье:</span><span class="sxs-lookup"><span data-stu-id="387a4-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="387a4-131">Проблемы с навигацией</span><span class="sxs-lookup"><span data-stu-id="387a4-131">Navigation issues</span></span>
    
- <span data-ttu-id="387a4-132">Свернутый контент</span><span class="sxs-lookup"><span data-stu-id="387a4-132">Content roll up</span></span>
    
- <span data-ttu-id="387a4-133">Большие файлы</span><span class="sxs-lookup"><span data-stu-id="387a4-133">Large files</span></span>
    
- <span data-ttu-id="387a4-134">Много запросов на сервер</span><span class="sxs-lookup"><span data-stu-id="387a4-134">Many requests to the server</span></span>
    
- <span data-ttu-id="387a4-135">Обработка веб-части</span><span class="sxs-lookup"><span data-stu-id="387a4-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="387a4-136">Подключение к серверу</span><span class="sxs-lookup"><span data-stu-id="387a4-136">Server connection</span></span>

<span data-ttu-id="387a4-137">Многие проблемы, влияющие на производительность в локальной сети SharePoint, также относятся к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="387a4-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="387a4-138">Как вы и ожидали, у вас есть гораздо больше контроля над тем, как серверы выполняются с локальной SharePoint.</span><span class="sxs-lookup"><span data-stu-id="387a4-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="387a4-139">С SharePoint Online все немного по-другому.</span><span class="sxs-lookup"><span data-stu-id="387a4-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="387a4-140">Чем больше работы вы сделаете на сервере, тем дольше будет отрисовка страницы.</span><span class="sxs-lookup"><span data-stu-id="387a4-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="387a4-141">В SharePoint самыми крупными виновниками в этом отношении являются сложные страницы с несколькими веб-частями.</span><span class="sxs-lookup"><span data-stu-id="387a4-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="387a4-142">Локальное помещение SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="387a4-142">SharePoint Server on-premises</span></span>
  
![Снимок экрана: локальный сервер](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="387a4-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-144">SharePoint Online</span></span>
  
![Снимок экрана: сервер в сети](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="387a4-146">В SharePoint Online некоторые запросы на страницы могут вызывать несколько серверов.</span><span class="sxs-lookup"><span data-stu-id="387a4-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="387a4-147">Вы можете получить матрицу запросов между серверами для отдельного запроса.</span><span class="sxs-lookup"><span data-stu-id="387a4-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="387a4-148">Эти взаимодействия являются дорогостоящими с точки зрения нагрузки на страницу и замедляют процессы.</span><span class="sxs-lookup"><span data-stu-id="387a4-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="387a4-149">Примеры взаимодействия этих серверов с сервером:</span><span class="sxs-lookup"><span data-stu-id="387a4-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="387a4-150">Веб-SQL серверов</span><span class="sxs-lookup"><span data-stu-id="387a4-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="387a4-151">Веб-серверы приложений</span><span class="sxs-lookup"><span data-stu-id="387a4-151">Web to application servers</span></span>
    
<span data-ttu-id="387a4-152">Другая вещь, которая может замедлить взаимодействие серверов, это пропуска кэш.</span><span class="sxs-lookup"><span data-stu-id="387a4-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="387a4-153">В отличие от локальной SharePoint, существует очень малая вероятность того, что вы нажмитесь на тот же сервер для страницы, которую вы посещали ранее; это делает кэшинг объектов устаревшим.</span><span class="sxs-lookup"><span data-stu-id="387a4-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="387a4-154">Подключение к сети </span><span class="sxs-lookup"><span data-stu-id="387a4-154">Network connection</span></span>

<span data-ttu-id="387a4-155">С локальной sharePoint, которая не использует WAN, вы можете использовать высокоскоростное подключение между центрами обработки данных и конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="387a4-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="387a4-156">Как правило, с сетевой точки зрения все легко управлять.</span><span class="sxs-lookup"><span data-stu-id="387a4-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="387a4-157">В SharePoint Online необходимо учитывать еще несколько факторов. Например:</span><span class="sxs-lookup"><span data-stu-id="387a4-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="387a4-158">Сеть Майкрософт</span><span class="sxs-lookup"><span data-stu-id="387a4-158">The Microsoft network</span></span>
    
- <span data-ttu-id="387a4-159">Интернет</span><span class="sxs-lookup"><span data-stu-id="387a4-159">The Internet</span></span>
    
- <span data-ttu-id="387a4-160">The ISP</span><span class="sxs-lookup"><span data-stu-id="387a4-160">The ISP</span></span>
    
<span data-ttu-id="387a4-161">Независимо от того, какую версию SharePoint (и какую сеть) вы используете, к числу вещей, которые обычно приводят к загружению сети, относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="387a4-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="387a4-162">Большая полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="387a4-162">Large payload</span></span>
    
- <span data-ttu-id="387a4-163">Много файлов</span><span class="sxs-lookup"><span data-stu-id="387a4-163">Many files</span></span>
    
- <span data-ttu-id="387a4-164">Большое физическое расстояние до сервера</span><span class="sxs-lookup"><span data-stu-id="387a4-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="387a4-165">Одной из функций, которую можно использовать в SharePoint Online, является Microsoft CDN (Сеть доставки контента).</span><span class="sxs-lookup"><span data-stu-id="387a4-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="387a4-166">CDN — это в основном распределенная коллекция серверов, развернутых в нескольких центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="387a4-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="387a4-167">С помощью CDN содержимое на страницах может быть организовано на сервере, близком к клиенту, даже если клиент находится далеко от исходящего SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="387a4-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="387a4-168">В будущем корпорация Майкрософт будет использовать эти дополнительные данные для хранения локальных экземпляров страниц, которые невозможно настроить, например домашней страницы администратора SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="387a4-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="387a4-169">Дополнительные сведения о CDNs см. в [материалах сетей доставки контента.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="387a4-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="387a4-170">Что-то, что вам нужно знать, но не может быть в состоянии сделать много о является скорость подключения вашего isP.</span><span class="sxs-lookup"><span data-stu-id="387a4-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="387a4-171">Простой тестовый инструмент скорости скажет вам скорость подключения.</span><span class="sxs-lookup"><span data-stu-id="387a4-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="387a4-172">Подключение к браузеру</span><span class="sxs-lookup"><span data-stu-id="387a4-172">Browser connection</span></span>

<span data-ttu-id="387a4-173">Существует несколько факторов, которые следует учитывать с помощью веб-браузеров с точки зрения производительности.</span><span class="sxs-lookup"><span data-stu-id="387a4-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="387a4-174">Посещение сложных страниц повлияет на производительность.</span><span class="sxs-lookup"><span data-stu-id="387a4-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="387a4-175">Большинство браузеров имеют небольшой кэш (около 90 МБ), в то время как средняя веб-страница обычно составляет около 1,6 МБ.</span><span class="sxs-lookup"><span data-stu-id="387a4-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="387a4-176">Это не займет много времени, чтобы привыкнуть.</span><span class="sxs-lookup"><span data-stu-id="387a4-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="387a4-177">Пропускная способность также может быть проблемой.</span><span class="sxs-lookup"><span data-stu-id="387a4-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="387a4-178">Например, если пользователь смотрит видео на другом сеансе, это повлияет на производительность страницы SharePoint.</span><span class="sxs-lookup"><span data-stu-id="387a4-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="387a4-179">Хотя вы не можете запретить пользователям потоковое мультимедиа, вы можете управлять загрузкой страницы для пользователей.</span><span class="sxs-lookup"><span data-stu-id="387a4-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="387a4-180">Ознакомьтесь со следующими статьями для различных методов настройки страниц SharePoint Online и других методов, которые помогут вам достичь оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="387a4-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="387a4-181">Параметры навигации для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="387a4-182">Используйте средство диагностики страниц для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="387a4-183">Оптимизация изображений для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="387a4-184">Задержка при загрузке изображений и JavaScript-файлов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="387a4-185">Минификация и объединение в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="387a4-186">Использование сети доставки содержимого Office 365 с SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="387a4-187">Использование веб-части поиска контента вместо веб-части запроса контента для повышения производительности в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="387a4-188">Планирование и тестирование загрузки SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="387a4-189">Диагностика проблем производительности в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="387a4-190">Использование кэша объектов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="387a4-191">Как избежать регулирования количества запросов или блокировки в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="387a4-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
