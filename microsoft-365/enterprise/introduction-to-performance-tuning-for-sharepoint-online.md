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
description: В этой статье объясняется, какие конкретные аспекты необходимо учитывать при разработке страниц для лучшей производительности SharePoint Online.
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909742"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="f2a7d-103">Общие сведения о настройке производительности для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="f2a7d-104">В этой статье объясняется, какие конкретные аспекты необходимо учитывать при разработке страниц для лучшей производительности SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="f2a7d-105">SharePoint Online metrics</span><span class="sxs-lookup"><span data-stu-id="f2a7d-105">SharePoint Online metrics</span></span>

<span data-ttu-id="f2a7d-106">Следующие широкие показатели для SharePoint Online предоставляют реальные данные о производительности:</span><span class="sxs-lookup"><span data-stu-id="f2a7d-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="f2a7d-107">Скорость загрузки страниц</span><span class="sxs-lookup"><span data-stu-id="f2a7d-107">How fast pages load</span></span>
    
- <span data-ttu-id="f2a7d-108">Сколько разных поездок требуется на страницу</span><span class="sxs-lookup"><span data-stu-id="f2a7d-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="f2a7d-109">Проблемы со службой</span><span class="sxs-lookup"><span data-stu-id="f2a7d-109">Issues with the service</span></span>
    
- <span data-ttu-id="f2a7d-110">Другие вещи, которые вызывают ухудшение производительности</span><span class="sxs-lookup"><span data-stu-id="f2a7d-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="f2a7d-111">Выводы, сделанные из-за данных</span><span class="sxs-lookup"><span data-stu-id="f2a7d-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="f2a7d-112">Данные говорят нам:</span><span class="sxs-lookup"><span data-stu-id="f2a7d-112">The data tells us:</span></span>
  
- <span data-ttu-id="f2a7d-113">Большинство страниц хорошо выполняются на SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="f2a7d-114">Не настраиваемые страницы загружаются очень быстро.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="f2a7d-115">OneDrive для бизнеса, сайты группы и страницы системы, такие как _layouts и т.д., быстро загружаются.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="f2a7d-116">Для загрузки самых медленных 1% SharePoint веб-страниц требуется более 5000 миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="f2a7d-117">Одним из простых тестовых показателей можно использовать для измерения производительности, сравнивая время загрузки собственного портала с временем загрузки домашней страницы OneDrive для бизнеса, так как она использует несколько настраиваемых функций.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="f2a7d-118">Это часто будет первым шагом, который поддержка попросит вас завершить при устранении неполадок с производительностью сети.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="f2a7d-119">Использование стандартной учетной записи пользователя при проверке производительности</span><span class="sxs-lookup"><span data-stu-id="f2a7d-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="f2a7d-120">Администратор коллекции сайтов, владелец сайта, редактор или участник относятся к дополнительным группам безопасности, имеют дополнительные разрешения и, следовательно, имеют дополнительные элементы, SharePoint нагрузки на странице.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="f2a7d-121">Это применимо к SharePoint и SharePoint Online, но в локальном сценарии различия будут не так легко заметить, как в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="f2a7d-122">Чтобы правильно оценить, как будет работать страница для пользователей, следует использовать стандартную учетную запись пользователя, чтобы избежать загрузки элементов управления авторизации и дополнительного трафика, связанного с группами безопасности.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="f2a7d-123">Категории подключения для настройки производительности</span><span class="sxs-lookup"><span data-stu-id="f2a7d-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="f2a7d-124">Связи между сервером и пользователем можно классифицировать на три основных компонента.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="f2a7d-125">Рассмотрите их при разработке SharePoint страниц в Интернете для анализа времени загрузки.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="f2a7d-126">**Сервер** Серверы, на которые Майкрософт размещены в центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="f2a7d-127">**Сеть** Сеть Майкрософт, Интернет и локальное подключение между центром обработки данных и пользователями.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="f2a7d-128">**Браузер** Загрузка страницы.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="f2a7d-129">В этих трех подключениях обычно существует пять причин, которые вызывают 95% медленных страниц.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="f2a7d-130">Каждая из этих причин обсуждается в этой статье:</span><span class="sxs-lookup"><span data-stu-id="f2a7d-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="f2a7d-131">Проблемы с навигацией</span><span class="sxs-lookup"><span data-stu-id="f2a7d-131">Navigation issues</span></span>
    
- <span data-ttu-id="f2a7d-132">Свернутый контент</span><span class="sxs-lookup"><span data-stu-id="f2a7d-132">Content roll up</span></span>
    
- <span data-ttu-id="f2a7d-133">Большие файлы</span><span class="sxs-lookup"><span data-stu-id="f2a7d-133">Large files</span></span>
    
- <span data-ttu-id="f2a7d-134">Много запросов на сервер</span><span class="sxs-lookup"><span data-stu-id="f2a7d-134">Many requests to the server</span></span>
    
- <span data-ttu-id="f2a7d-135">Обработка веб-части</span><span class="sxs-lookup"><span data-stu-id="f2a7d-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="f2a7d-136">Подключение к серверу</span><span class="sxs-lookup"><span data-stu-id="f2a7d-136">Server connection</span></span>

<span data-ttu-id="f2a7d-137">Многие из проблем, влияющих на производительность SharePoint локальной работе, также применимы к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="f2a7d-138">Как и ожидается, у вас гораздо больше контроля над тем, как серверы выполняются с локальной SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="f2a7d-139">С SharePoint в Интернете все немного по-другому.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="f2a7d-140">Чем больше работы вы сделаете на сервере, тем дольше будет отрисовка страницы.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="f2a7d-141">С SharePoint самыми крупными виновниками в этом отношении являются сложные страницы с несколькими веб-частями.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="f2a7d-142">SharePoint Локальное серверное</span><span class="sxs-lookup"><span data-stu-id="f2a7d-142">SharePoint Server on-premises</span></span>
  
![Снимок экрана: локальный сервер](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="f2a7d-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-144">SharePoint Online</span></span>
  
![Снимок экрана: сервер в сети](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="f2a7d-146">С SharePoint Online некоторые запросы на страницы могут вызывать несколько серверов.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="f2a7d-147">Вы можете получить матрицу запросов между серверами для отдельного запроса.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="f2a7d-148">Эти взаимодействия являются дорогостоящими с точки зрения нагрузки на страницу и замедляют процессы.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="f2a7d-149">Примеры взаимодействия этих серверов с сервером:</span><span class="sxs-lookup"><span data-stu-id="f2a7d-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="f2a7d-150">Веб-SQL серверов</span><span class="sxs-lookup"><span data-stu-id="f2a7d-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="f2a7d-151">Веб-серверы приложений</span><span class="sxs-lookup"><span data-stu-id="f2a7d-151">Web to application servers</span></span>
    
<span data-ttu-id="f2a7d-152">Другая вещь, которая может замедлить взаимодействие серверов, это пропуска кэш.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="f2a7d-153">В отличие от локального SharePoint, существует очень малая вероятность того, что вы нажмете один и тот же сервер на страницу, которую вы посетили ранее; это делает кэшинг объектов устаревшим.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="f2a7d-154">Подключение к сети </span><span class="sxs-lookup"><span data-stu-id="f2a7d-154">Network connection</span></span>

<span data-ttu-id="f2a7d-155">С локальной SharePoint, которая не использует WAN, вы можете использовать высокоскоростное подключение между центрами обработки данных и конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="f2a7d-156">Как правило, с сетевой точки зрения все легко управлять.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="f2a7d-157">С SharePoint Online необходимо учитывать еще несколько факторов; Например:</span><span class="sxs-lookup"><span data-stu-id="f2a7d-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="f2a7d-158">Сеть Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f2a7d-158">The Microsoft network</span></span>
    
- <span data-ttu-id="f2a7d-159">Интернет</span><span class="sxs-lookup"><span data-stu-id="f2a7d-159">The Internet</span></span>
    
- <span data-ttu-id="f2a7d-160">The ISP</span><span class="sxs-lookup"><span data-stu-id="f2a7d-160">The ISP</span></span>
    
<span data-ttu-id="f2a7d-161">Независимо от того, какую SharePoint (и какую сеть) вы используете, к числу вещей, которые обычно приводят к загружению сети, относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="f2a7d-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="f2a7d-162">Большая полезной нагрузки</span><span class="sxs-lookup"><span data-stu-id="f2a7d-162">Large payload</span></span>
    
- <span data-ttu-id="f2a7d-163">Много файлов</span><span class="sxs-lookup"><span data-stu-id="f2a7d-163">Many files</span></span>
    
- <span data-ttu-id="f2a7d-164">Большое физическое расстояние до сервера</span><span class="sxs-lookup"><span data-stu-id="f2a7d-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="f2a7d-165">Одной из функций, которую можно использовать в SharePoint Online, является microsoft CDN (сеть доставки содержимого).</span><span class="sxs-lookup"><span data-stu-id="f2a7d-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="f2a7d-166">A CDN это в основном распределенная коллекция серверов, развернутых в нескольких центрах обработки данных.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="f2a7d-167">С помощью CDN содержимое на страницах может быть организовано на сервере, близком к клиенту, даже если клиент находится далеко от SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="f2a7d-168">Microsoft будет использовать это больше в будущем для хранения локальных экземпляров страниц, которые не могут быть настроены, например SharePoint домашней странице администратора Online.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="f2a7d-169">Дополнительные сведения о CDNs см. в [материалах сетей доставки контента.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="f2a7d-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="f2a7d-170">Что-то, что вам нужно знать, но не может быть в состоянии сделать много о является скорость подключения вашего isP.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="f2a7d-171">Простой тестовый инструмент скорости скажет вам скорость подключения.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="f2a7d-172">Подключение к браузеру</span><span class="sxs-lookup"><span data-stu-id="f2a7d-172">Browser connection</span></span>

<span data-ttu-id="f2a7d-173">Существует несколько факторов, которые следует учитывать с помощью веб-браузеров с точки зрения производительности.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="f2a7d-174">Посещение сложных страниц повлияет на производительность.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="f2a7d-175">Большинство браузеров имеют небольшой кэш (около 90 МБ), в то время как средняя веб-страница обычно составляет около 1,6 МБ.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="f2a7d-176">Это не займет много времени, чтобы привыкнуть.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="f2a7d-177">Пропускная способность также может быть проблемой.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="f2a7d-178">Например, если пользователь смотрит видео на другом сеансе, это повлияет на производительность SharePoint страницы.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="f2a7d-179">Хотя вы не можете запретить пользователям потоковое мультимедиа, вы можете управлять загрузкой страницы для пользователей.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="f2a7d-180">Ознакомьтесь со следующими статьями для различных методов настройки SharePoint веб-страниц и других методов, которые помогут вам достичь оптимальной производительности.</span><span class="sxs-lookup"><span data-stu-id="f2a7d-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="f2a7d-181">Параметры навигации для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="f2a7d-182">Используйте средство диагностики страниц для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="f2a7d-183">Оптимизация изображений для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="f2a7d-184">Задержка при загрузке изображений и JavaScript-файлов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="f2a7d-185">Минификация и объединение в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="f2a7d-186">Использование сети доставки содержимого Office 365 с SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="f2a7d-187">Использование веб-части поиска контента вместо веб-части запроса контента для повышения производительности SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="f2a7d-188">Планирование и тестирование загрузки SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="f2a7d-189">Диагностика проблем производительности в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="f2a7d-190">Использование кэша объектов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="f2a7d-191">Как избежать регулирования количества запросов или блокировки в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f2a7d-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
