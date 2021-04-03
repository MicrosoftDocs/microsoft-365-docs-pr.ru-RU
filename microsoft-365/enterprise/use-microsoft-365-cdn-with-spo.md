---
title: Используйте сеть доставки контента Office 365 (CDN) с SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
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
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Узнайте, как использовать сеть доставки контента Office 365 (CDN) для ускорения доставки ресурсов SharePoint Online.
ms.openlocfilehash: 6819f627d3590cd2739b36cb1bc303f197d6aaa5
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570409"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="b81fd-103">Использование сети доставки содержимого Office 365 с SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="b81fd-104">Вы можете использовать встроенную сеть доставки содержимого (CDN) Office 365 для размещения статических ресурсов, чтобы повысить производительность страниц SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b81fd-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="b81fd-105">Сеть CDN Office 365 повышает производительность путем кэширования статических ресурсов ближе к браузерам, которые их запрашивают, что повышает скорость скачиваний и снижает задержку.</span><span class="sxs-lookup"><span data-stu-id="b81fd-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="b81fd-106">Кроме того, CDN Office 365 использует [протокол HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) для улучшения сжатия и http pipelining.</span><span class="sxs-lookup"><span data-stu-id="b81fd-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="b81fd-107">Служба CDN Office 365 входит в состав подписки на SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b81fd-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="b81fd-108">CdN Office 365 доступен только для клиентов в облаке **Production** (по всему миру).</span><span class="sxs-lookup"><span data-stu-id="b81fd-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="b81fd-109">Клиенты в облаках правительства США, Китая и Германии в настоящее время не поддерживают CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="b81fd-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="b81fd-110">Сети доставки содержимого Office 365 состоит из нескольких сетей CDN, позволяющих размещать статические ресурсы в нескольких расположениях или _источниках_ и использовать их из глобальных высокоскоростных сетей.</span><span class="sxs-lookup"><span data-stu-id="b81fd-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="b81fd-111">В зависимости от типа содержимого, которое необходимо разместить в сети CDN Office 365, можно добавить **общедоступные** источники, **закрытые** источники или оба варианта.</span><span class="sxs-lookup"><span data-stu-id="b81fd-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="b81fd-112">Дополнительные [сведения](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) о различиях между государственными и частными происхождениями см. в дополнительных сведениях о том, должно ли каждое происхождение быть общедоступным или частным.</span><span class="sxs-lookup"><span data-stu-id="b81fd-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="b81fd-113">![Концептуальная схема CDN Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Концептуальная схема CDN Office 365")</span><span class="sxs-lookup"><span data-stu-id="b81fd-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="b81fd-114">Если вы уже знакомы с тем, как работают cdNs, необходимо выполнить только несколько действий, чтобы включить CDN Office 365 для клиента.</span><span class="sxs-lookup"><span data-stu-id="b81fd-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="b81fd-115">В этом разделе описывается, как.</span><span class="sxs-lookup"><span data-stu-id="b81fd-115">This topic describes how.</span></span> <span data-ttu-id="b81fd-116">Ознакомьтесь с информацией о том, как начать размещение статических активов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="b81fd-117">Существуют другие cdNs, которые можно использовать с Office 365 для специализированных сценариев использования, но не обсуждаются в этой теме, так как они не находятся за рамками CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="b81fd-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="b81fd-118">Дополнительные сведения см. [в других cdNs Microsoft.](content-delivery-networks.md#other-microsoft-cdns)</span><span class="sxs-lookup"><span data-stu-id="b81fd-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="b81fd-119">**Возвращайся к [планированию сети и настройке производительности для Office 365.](./network-planning-and-performance.md)**</span><span class="sxs-lookup"><span data-stu-id="b81fd-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="b81fd-120">Обзор работы с CDN Office 365 в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="b81fd-121">Чтобы настроить CDN Office 365 для организации, выполните следующие основные действия:</span><span class="sxs-lookup"><span data-stu-id="b81fd-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="b81fd-122">Планирование развертывания CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="b81fd-123">[Определите, какие статические активы необходимо установить в CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)</span><span class="sxs-lookup"><span data-stu-id="b81fd-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="b81fd-124">[Определите, где нужно хранить свои активы.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)</span><span class="sxs-lookup"><span data-stu-id="b81fd-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="b81fd-125">Это расположение может быть сайтом SharePoint, библиотекой или папкой и называется _происхождением._</span><span class="sxs-lookup"><span data-stu-id="b81fd-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="b81fd-126">[Выберите, должно ли каждое происхождение быть общедоступным или частным.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="b81fd-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="b81fd-127">Можно добавить несколько источников как общедоступных, так и частных типов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="b81fd-128">Настройка и настройка CDN с помощью PowerShell или CLI SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="b81fd-129">Настройка и настройка CDN с помощью оболочки управления SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="b81fd-130">Настройка и настройка CDN с помощью PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="b81fd-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="b81fd-131">Настройка и настройка CDN с помощью CLI Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="b81fd-132">Когда вы выполните этот шаг, у вас будет:</span><span class="sxs-lookup"><span data-stu-id="b81fd-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="b81fd-133">Включен cdN для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b81fd-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="b81fd-134">Добавлены истоки, определяющие каждое происхождение как общедоступные или частные.</span><span class="sxs-lookup"><span data-stu-id="b81fd-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="b81fd-135">После установки можно управлять [CDN Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) с течением времени:</span><span class="sxs-lookup"><span data-stu-id="b81fd-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="b81fd-136">Добавление, обновление и удаление активов</span><span class="sxs-lookup"><span data-stu-id="b81fd-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="b81fd-137">Добавление и удаление истоков</span><span class="sxs-lookup"><span data-stu-id="b81fd-137">Adding and removing origins</span></span>
+ <span data-ttu-id="b81fd-138">Настройка политик CDN</span><span class="sxs-lookup"><span data-stu-id="b81fd-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="b81fd-139">При необходимости отключение CDN</span><span class="sxs-lookup"><span data-stu-id="b81fd-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="b81fd-140">Наконец, см. в выпуске Использование ресурсов [CDN,](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) чтобы узнать о доступе к вашим cdN-активам как из государственного, так и из частного происхождения.</span><span class="sxs-lookup"><span data-stu-id="b81fd-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="b81fd-141">Инструкции по решению распространенных проблем см. в инструкции по устранению неполадок [cdN Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="b81fd-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="b81fd-142">Планирование развертывания CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-143">Перед развертыванием CDN Office 365 для клиента Office 365 необходимо учитывать следующие факторы в процессе планирования.</span><span class="sxs-lookup"><span data-stu-id="b81fd-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="b81fd-144">Определение статических активов, которые необходимо установить в CDN</span><span class="sxs-lookup"><span data-stu-id="b81fd-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="b81fd-145">Определите, где нужно хранить свои активы</span><span class="sxs-lookup"><span data-stu-id="b81fd-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="b81fd-146">Выберите, должно ли каждое происхождение быть общедоступным или закрытым.</span><span class="sxs-lookup"><span data-stu-id="b81fd-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="b81fd-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="b81fd-148">Определение статических активов, которые необходимо установить в CDN</span><span class="sxs-lookup"><span data-stu-id="b81fd-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="b81fd-149">В общем, CDNs наиболее эффективны для размещения статических активов _или_ активов, которые не очень часто изменяются.</span><span class="sxs-lookup"><span data-stu-id="b81fd-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="b81fd-150">Хорошим правилом является определение файлов, которые соответствуют некоторым или всем этим условиям:</span><span class="sxs-lookup"><span data-stu-id="b81fd-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="b81fd-151">Статические файлы, встроенные в страницу (например, сценарии и изображения), которые могут иметь существенное инкрементное влияние на время загрузки страницы.</span><span class="sxs-lookup"><span data-stu-id="b81fd-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="b81fd-152">Большие файлы, такие как исполняемые и файлы установки</span><span class="sxs-lookup"><span data-stu-id="b81fd-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="b81fd-153">Библиотеки ресурсов, поддерживают клиентский код</span><span class="sxs-lookup"><span data-stu-id="b81fd-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="b81fd-154">Например, небольшие файлы, которые неоднократно запрашиваются, например изображения сайтов и сценарии, могут значительно повысить производительность отрисовки сайтов и постепенно снизить нагрузку на сайты SharePoint Online при добавлении их в cdN-источник.</span><span class="sxs-lookup"><span data-stu-id="b81fd-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="b81fd-155">Более крупные файлы, такие как исполняемые установки, могут быть скачаны из CDN, что положительно сказывается на производительности и последующем снижении нагрузки на сайте SharePoint Online, даже если к ним не доступны так часто.</span><span class="sxs-lookup"><span data-stu-id="b81fd-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="b81fd-156">Улучшение производительности на основе каждого файла зависит от многих факторов, включая близость клиента к ближайшей конечной точке CDN, временные условия в локальной сети и т. д.</span><span class="sxs-lookup"><span data-stu-id="b81fd-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="b81fd-157">Многие статические файлы довольно малы и могут быть загружены из Office 365 менее чем за секунду.</span><span class="sxs-lookup"><span data-stu-id="b81fd-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="b81fd-158">Однако веб-страница может содержать множество встроенных файлов совокупным временем загрузки в несколько секунд.</span><span class="sxs-lookup"><span data-stu-id="b81fd-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="b81fd-159">Обслуживание этих файлов из CDN может значительно сократить общее время загрузки страницы.</span><span class="sxs-lookup"><span data-stu-id="b81fd-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="b81fd-160">Узнайте, [какие результаты обеспечивает CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) в примере.</span><span class="sxs-lookup"><span data-stu-id="b81fd-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="b81fd-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="b81fd-162">Определите, где нужно хранить свои активы</span><span class="sxs-lookup"><span data-stu-id="b81fd-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="b81fd-163">CDN извлекает ваши активы из расположения, называемого _происхождением._</span><span class="sxs-lookup"><span data-stu-id="b81fd-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="b81fd-164">Происхождение может быть веб-сайтОм SharePoint, библиотекой документов или папкой, доступной по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="b81fd-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="b81fd-165">У вас есть большая гибкость при указании истоков для организации.</span><span class="sxs-lookup"><span data-stu-id="b81fd-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="b81fd-166">Например, можно указать несколько источников или одно происхождение, куда необходимо поместить все ресурсы CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="b81fd-167">Вы можете выбрать общедоступные или частные истоки для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b81fd-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="b81fd-168">Большинство организаций будут выбирать для реализации сочетания этих двух.</span><span class="sxs-lookup"><span data-stu-id="b81fd-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="b81fd-169">Вы можете создать новый контейнер для истоков, таких как папки или библиотеки документов, и добавить файлы, которые необходимо сделать доступными из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="b81fd-170">Это хороший подход, если у вас есть определенный набор активов, которые вы хотите быть доступными из CDN, и хотите ограничить набор cdN-активов только этими файлами в контейнере.</span><span class="sxs-lookup"><span data-stu-id="b81fd-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="b81fd-171">Вы также можете настроить существующую коллекцию сайтов, сайт, библиотеку или папку в качестве источника, что сделает все подходящие активы в контейнере доступными из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="b81fd-172">Перед добавлением существующего контейнера в качестве источника важно убедиться, что вы осведомлены о его содержимом и разрешениях, чтобы не случайно подвергать ресурсы анонимному доступу или неавторизованным пользователям.</span><span class="sxs-lookup"><span data-stu-id="b81fd-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="b81fd-173">Вы можете определить _политики CDN,_ чтобы исключить содержимое в истоках из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="b81fd-174">Политики CDN исключают активы государственного или частного  происхождения по атрибутам, таким как тип файла и классификация _сайтов,_ и применяются для всех истоков cdnType (частных или общедоступных), которые указаны в политике.</span><span class="sxs-lookup"><span data-stu-id="b81fd-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="b81fd-175">Например, если вы добавляете частное происхождение, состоящее из сайта с несколькими подмитами, можно определить политику, исключаемую сайты, помеченные как **Конфиденциальные,** чтобы содержимое сайтов с примененной классификацией не было подается из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="b81fd-176">Политика будет применяться к контенту из _всех_ частных истоков, добавленных в CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="b81fd-177">Имейте в виду, что чем больше количество истоков, тем больше влияние на время обработки запросов службой CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="b81fd-178">Рекомендуем максимально ограничить количество истоков.</span><span class="sxs-lookup"><span data-stu-id="b81fd-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="b81fd-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="b81fd-180">Выберите, должно ли каждое происхождение быть общедоступным или закрытым.</span><span class="sxs-lookup"><span data-stu-id="b81fd-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="b81fd-181">При определении источника указывается, следует ли сделать его общедоступным _или_ _закрытым._</span><span class="sxs-lookup"><span data-stu-id="b81fd-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="b81fd-182">Доступ к активам CDN в общедоступных источниках анонимный, а контент CDN частного происхождения обеспечивается динамически созданными маркерами для большей безопасности.</span><span class="sxs-lookup"><span data-stu-id="b81fd-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="b81fd-183">Независимо от того, какой из вариантов вы выбираете, Корпорация Майкрософт делает все, что необходимо для вас, когда речь заходит об администрировании самого CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="b81fd-184">Кроме того, вы можете изменить свое решение позже, после того как вы настроите CDN и идентифицировали свои истоки.</span><span class="sxs-lookup"><span data-stu-id="b81fd-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="b81fd-185">Как общедоступные, так и частные параметры обеспечивают аналогичные преимущества производительности, но каждый из них имеет уникальные атрибуты и преимущества.</span><span class="sxs-lookup"><span data-stu-id="b81fd-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="b81fd-186">**Общедоступные** истоки в CDN Office 365 доступны анонимно, а к общедоступным активам может получить доступ любой, у кого есть URL-адрес актива.</span><span class="sxs-lookup"><span data-stu-id="b81fd-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="b81fd-187">Так как доступ к содержимому в общедоступных источниках является анонимным, следует использовать их только для кэширования неконфиденциального общего содержимого, например файлов JavaScript, скриптов, значков и изображений.</span><span class="sxs-lookup"><span data-stu-id="b81fd-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as JavaScript files, scripts, icons and images.</span></span>

<span data-ttu-id="b81fd-188">**Частные** истоки в CDN Office 365 предоставляют частный доступ к пользовательскому контенту, такому как библиотеки документов SharePoint Online, сайты и собственные изображения.</span><span class="sxs-lookup"><span data-stu-id="b81fd-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="b81fd-189">Доступ к контенту частного происхождения обеспечивается динамически созданными маркерами, поэтому доступ к нему могут получить только пользователи с разрешениями на исходную библиотеку документов или расположение хранилища.</span><span class="sxs-lookup"><span data-stu-id="b81fd-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="b81fd-190">Частные истоки CDN Office 365 можно использовать только для контента SharePoint Online, а получить доступ к активам частного происхождения можно только через перенаправление с клиента SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b81fd-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="b81fd-191">Подробнее о том, как работает доступ CDN к активам частного происхождения, читайте в публикации "Использование активов [в частном происхождении".](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)</span><span class="sxs-lookup"><span data-stu-id="b81fd-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="b81fd-192">Атрибуты и преимущества размещения активов в общедоступных источниках</span><span class="sxs-lookup"><span data-stu-id="b81fd-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="b81fd-193">Ресурсы, предоставляемые из общедоступного источника, доступны всем анонимно.</span><span class="sxs-lookup"><span data-stu-id="b81fd-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="b81fd-194">Никогда не следует разместить ресурсы, содержащие сведения о пользователях или которые считаются конфиденциальными для организации в публичном происхождении.</span><span class="sxs-lookup"><span data-stu-id="b81fd-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

+ <span data-ttu-id="b81fd-195">Если удалить ресурс из общедоступного источника, он может оставаться доступным в кэше до 30 дней. Однако ссылки на ресурс в сети CDN станут недействительными в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b81fd-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>

+ <span data-ttu-id="b81fd-196">При размещении таблиц стилей (CSS-файлов) в общедоступном источнике можно использовать в коде относительные пути и URI.</span><span class="sxs-lookup"><span data-stu-id="b81fd-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="b81fd-197">Это означает, что вы можете ссылаться на расположение фоновых изображений и других объектов относительно расположения ресурса, который вызывает его.</span><span class="sxs-lookup"><span data-stu-id="b81fd-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>

+ <span data-ttu-id="b81fd-198">Хотя вы можете создать URL-адрес общего происхождения, следует действовать с осторожностью и убедиться, что вы используете свойство контекста страницы и следуйте указаниям для этого.</span><span class="sxs-lookup"><span data-stu-id="b81fd-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="b81fd-199">Это связано с тем, что если сеть CDN станет недоступна, то URL-адрес не будет автоматически указывать на вашу организацию в SharePoint Online, что может привести к неработоспособности ссылок и другим ошибкам.</span><span class="sxs-lookup"><span data-stu-id="b81fd-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="b81fd-200">Url-адрес также подлежит изменению, поэтому он не должен быть просто жестко закодироваться к текущему значению.</span><span class="sxs-lookup"><span data-stu-id="b81fd-200">The URL is also subject to change which is why it should not just be hard coded to its current value.</span></span>

+ <span data-ttu-id="b81fd-201">Типы файлов по умолчанию, включенные для общедоступных истоков, являются .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff и .woff2.</span><span class="sxs-lookup"><span data-stu-id="b81fd-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="b81fd-202">Можно указать дополнительные типы файлов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-202">You can specify additional file types.</span></span>

+ <span data-ttu-id="b81fd-203">Можно настроить политику, чтобы исключить активы, которые были определены в классификациях сайтов, которые указаны.</span><span class="sxs-lookup"><span data-stu-id="b81fd-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="b81fd-204">Например, вы можете исключать все ресурсы, отмеченные как "конфиденциальные" или "с ограниченным доступом", даже если они относятся к разрешенным типам файлов и находятся в общедоступном источнике.</span><span class="sxs-lookup"><span data-stu-id="b81fd-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="b81fd-205">Атрибуты и преимущества размещения активов в частном происхождении</span><span class="sxs-lookup"><span data-stu-id="b81fd-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="b81fd-206">Частные истоки можно использовать только для активов SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b81fd-206">Private origins can only be used for SharePoint Online assets.</span></span>

+ <span data-ttu-id="b81fd-207">Пользователи могут получить доступ к активам частного происхождения только в том случае, если у них есть разрешения на доступ к контейнеру.</span><span class="sxs-lookup"><span data-stu-id="b81fd-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="b81fd-208">Анонимный доступ к таким ресурсам запрещен.</span><span class="sxs-lookup"><span data-stu-id="b81fd-208">Anonymous access to these assets is prevented.</span></span>

+ <span data-ttu-id="b81fd-209">Активы частного происхождения должны быть переданы из клиента SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b81fd-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="b81fd-210">Прямой доступ к частным cdN-активам не работает.</span><span class="sxs-lookup"><span data-stu-id="b81fd-210">Direct access to private CDN assets does not work.</span></span>

+ <span data-ttu-id="b81fd-211">Если вы удалите актив из частного происхождения, актив может оставаться доступным в течение часа из кэша; однако в течение 15 минут после удаления актива ссылки на актив в CDN будут признаны недействительными.</span><span class="sxs-lookup"><span data-stu-id="b81fd-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>

+ <span data-ttu-id="b81fd-212">По умолчанию для частных источников включены типы файлов GIF, ICO, JPEG, JPG, JS и PNG.</span><span class="sxs-lookup"><span data-stu-id="b81fd-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="b81fd-213">Можно указать дополнительные типы файлов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-213">You can specify additional file types.</span></span>

+ <span data-ttu-id="b81fd-214">Как и с общедоступными истоками, можно настроить политику, чтобы исключить активы, которые были определены классификациями сайтов, которые вы указываете, даже если вы используете поддиальды, чтобы включить все активы в папку или библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="b81fd-215">Дополнительные сведения о том, зачем использовать CDN Office 365, общие концепции CDN и другие CDN Майкрософт, которые можно использовать с клиентом Office 365, см. в статью [Content Delivery Networks.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="b81fd-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="b81fd-216">Происхождение CDN по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b81fd-216">Default CDN origins</span></span>

<span data-ttu-id="b81fd-217">Если не указать обратное, Office 365 устанавливает для вас некоторые истоки по умолчанию, если вы включаете CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="b81fd-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="b81fd-218">Если изначально вы решите не добавлять их, вы можете добавить эти истоки после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="b81fd-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="b81fd-219">Если вы не понимаете последствия пропуска установки истоков по умолчанию и не имеете для этого конкретной причины, вы должны разрешить их создавать, когда вы включаете CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="b81fd-220">Частные истоки CDN по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="b81fd-220">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="b81fd-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="b81fd-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="b81fd-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="b81fd-222">\*/siteassets</span></span>

<span data-ttu-id="b81fd-223">Общедоступные истоки CDN по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="b81fd-223">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="b81fd-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="b81fd-224">\*/masterpage</span></span>
+ <span data-ttu-id="b81fd-225">\*/библиотека стилей</span><span class="sxs-lookup"><span data-stu-id="b81fd-225">\*/style library</span></span>
+ <span data-ttu-id="b81fd-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="b81fd-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="b81fd-227">_clientsideassets_ — это общедоступный источник по умолчанию, который был добавлен в службу CDN Office 365 в декабре 2017 г.</span><span class="sxs-lookup"><span data-stu-id="b81fd-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="b81fd-228">Это происхождение должно присутствовать для того, чтобы решения SharePoint Framework в CDN работали.</span><span class="sxs-lookup"><span data-stu-id="b81fd-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="b81fd-229">Если вы включили CDN Office 365 до декабря 2017 г. или пропустили установку истоков по умолчанию при включении CDN, можно вручную добавить это начало.</span><span class="sxs-lookup"><span data-stu-id="b81fd-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="b81fd-230">Дополнительные сведения см. в [раздел Моя клиентская веб-часть или решение SharePoint Framework не работает.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)</span><span class="sxs-lookup"><span data-stu-id="b81fd-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="b81fd-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="b81fd-232">Настройка и настройка CDN Office 365 с помощью оболочки управления SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="b81fd-233">Процедуры в этом разделе требуют, чтобы вы использовали оболочку управления SharePoint Online для подключения к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b81fd-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="b81fd-234">Инструкции см. в статье [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="b81fd-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="b81fd-235">Выполните эти действия, чтобы настроить CDN для организации активов в SharePoint Online с помощью оболочки управления SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b81fd-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="b81fd-236">Щелкните, чтобы развернуть</span><span class="sxs-lookup"><span data-stu-id="b81fd-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="b81fd-237">Включить организацию для использования CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-238">Прежде чем вносить изменения в параметры CDN клиента, необходимо получить текущее состояние закрытой конфигурации CDN в клиенте Office 365.</span><span class="sxs-lookup"><span data-stu-id="b81fd-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="b81fd-239">Подключение к клиенту с помощью оболочки управления SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="b81fd-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="b81fd-240">Теперь используйте **комлет Get-SPOTenantCdnEnabled** для получения параметров состояния CDN у клиента:</span><span class="sxs-lookup"><span data-stu-id="b81fd-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="b81fd-241">Состояние CDN для указанного CdnType выводит на экран.</span><span class="sxs-lookup"><span data-stu-id="b81fd-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="b81fd-242">Используйте **комлет Set-SPOTenantCdnEnabled,** чтобы позволить организации использовать CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="b81fd-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="b81fd-243">Вы можете включить организацию для использования общедоступных истоков, частных и одновременно обоих.</span><span class="sxs-lookup"><span data-stu-id="b81fd-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="b81fd-244">Можно также настроить CDN, чтобы пропустить настройку истоков по умолчанию при его впусте.</span><span class="sxs-lookup"><span data-stu-id="b81fd-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="b81fd-245">Вы всегда можете добавить эти истоки позже, как описано в этой теме.</span><span class="sxs-lookup"><span data-stu-id="b81fd-245">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="b81fd-246">В Windows PowerShell SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="b81fd-246">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="b81fd-247">Например, чтобы позволить организации использовать общедоступные и частные истоки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="b81fd-248">Чтобы позволить организации использовать как общедоступные, так и частные истоки, но пропустить настройку истоков по умолчанию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="b81fd-249">Сведения о происхождении по умолчанию, которые предусмотрены по умолчанию при встройки [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) Office 365, и о потенциальном влиянии пропуска установки истоков по умолчанию см. в истоках CDN по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b81fd-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="b81fd-250">Чтобы позволить организации использовать общедоступные истоки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-250">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="b81fd-251">Чтобы позволить организации использовать частные истоки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-251">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="b81fd-252">Дополнительные сведения об этом комлете см. в этой ленте [Set-SPOTenantCdnEnabled.](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)</span><span class="sxs-lookup"><span data-stu-id="b81fd-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="b81fd-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="b81fd-254">Измените список типов файлов, чтобы включить их в CDN Office 365 (необязательный)</span><span class="sxs-lookup"><span data-stu-id="b81fd-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b81fd-255">При определении типов файлов с помощью комлета **Set-SPOTenantCdnPolicy** переопределяется определенный список.</span><span class="sxs-lookup"><span data-stu-id="b81fd-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b81fd-256">Если вы хотите добавить в список дополнительные типы файлов, сначала используйте этот список, чтобы узнать, какие типы файлов уже разрешены, и включите их в список вместе с новыми.</span><span class="sxs-lookup"><span data-stu-id="b81fd-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="b81fd-257">Для определения типов статических файлов, которые могут быть организованы государственным и частным происхождением в CDN, используйте коммюлет **Set-SPOTenantCdnPolicy.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="b81fd-258">По умолчанию разрешены общие типы активов, например .css, .gif, .jpg и .js.</span><span class="sxs-lookup"><span data-stu-id="b81fd-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="b81fd-259">В Windows PowerShell SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="b81fd-259">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="b81fd-260">Например, чтобы включить CDN для хозяйских файлов .css и .png, необходимо ввести команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="b81fd-261">Чтобы узнать, какие типы файлов в настоящее время разрешены CDN, используйте **cmdlet Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="b81fd-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b81fd-262">Дополнительные сведения об этих cmdlets см. в [set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) и [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span><span class="sxs-lookup"><span data-stu-id="b81fd-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="b81fd-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="b81fd-264">Измените список классификаций сайтов, которые необходимо исключить из CDN Office 365 (необязательный)</span><span class="sxs-lookup"><span data-stu-id="b81fd-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b81fd-265">При исключении классификации сайтов с помощью комлета **Set-SPOTenantCdnPolicy** переопределяется определенный список.</span><span class="sxs-lookup"><span data-stu-id="b81fd-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b81fd-266">Если вы хотите исключить дополнительные классификации сайтов, сначала используйте cmdlet, чтобы узнать, какие классификации уже исключены, а затем добавить их вместе с новыми.</span><span class="sxs-lookup"><span data-stu-id="b81fd-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="b81fd-267">Чтобы исключить классификации сайтов, которые не должны быть доступны в сети CDN, используйте командлет **Set-SPOTenantCdnPolicy**.</span><span class="sxs-lookup"><span data-stu-id="b81fd-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="b81fd-268">По умолчанию не исключаются никакие классификации сайтов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="b81fd-269">В Windows PowerShell SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="b81fd-269">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="b81fd-270">Чтобы узнать, какие классификации сайтов в настоящее время ограничены, используйте см. в **рубриках Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="b81fd-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b81fd-271">Свойства, которые будут _возвращены: IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ и _ExcludeIfNoScriptDisabled._</span><span class="sxs-lookup"><span data-stu-id="b81fd-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="b81fd-272">Свойство _IncludeFileExtensions_ содержит список расширений файлов, которые будут подаваться из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="b81fd-273">Расширения файлов по умолчанию отличаются между общедоступными и закрытыми.</span><span class="sxs-lookup"><span data-stu-id="b81fd-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="b81fd-274">Свойство _ExcludeRestrictedSiteClassifications_ содержит классификации сайтов, которые необходимо исключить из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="b81fd-275">Например, можно исключить сайты, помеченные как **Конфиденциальные,** чтобы содержимое сайтов с применяемой классификацией не обслуживалось из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="b81fd-276">Свойство _ExcludeIfNoScriptDisabled_ исключает контент из CDN на основе параметров атрибута _NoScript_ на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="b81fd-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="b81fd-277">По умолчанию для _атрибута NoScript_ устанавливается значение **Включено** для _современных_ сайтов и **отключено для** _классических_ сайтов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="b81fd-278">Это зависит от параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="b81fd-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="b81fd-279">Дополнительные сведения об этих cmdlets см. в [set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) и [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span><span class="sxs-lookup"><span data-stu-id="b81fd-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="b81fd-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="b81fd-281">Добавление источника для ваших активов</span><span class="sxs-lookup"><span data-stu-id="b81fd-281">Add an origin for your assets</span></span>

<span data-ttu-id="b81fd-282">Чтобы определить происхождение, используйте кодлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="b81fd-283">Вы можете определить несколько источников.</span><span class="sxs-lookup"><span data-stu-id="b81fd-283">You can define multiple origins.</span></span> <span data-ttu-id="b81fd-284">Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b81fd-285">Никогда не следует разместить ресурсы, содержащие сведения о пользователях или которые считаются конфиденциальными для организации в публичном происхождении.</span><span class="sxs-lookup"><span data-stu-id="b81fd-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="b81fd-286">Значение пути _—_ это относительный путь к библиотеке или папке, которая содержит активы.</span><span class="sxs-lookup"><span data-stu-id="b81fd-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="b81fd-287">Помимо относительных путей, можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b81fd-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="b81fd-288">Origins поддерживает подкарды, предварительно заранее заранее примыкает к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="b81fd-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="b81fd-289">Это позволяет создавать истоки, охватывающие несколько сайтов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="b81fd-290">Например, чтобы включить все активы в папку masterpages для всех сайтов в качестве общедоступных в cdN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="b81fd-291">Модификатор под диктовки \* может использоваться только в начале пути и будет соответствовать всем сегментам URL-адресов по **/** указанному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="b81fd-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="b81fd-292">Путь может указать на библиотеку документов, папку или сайт.</span><span class="sxs-lookup"><span data-stu-id="b81fd-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="b81fd-293">Например, путь _\*/site1 будет_ соответствовать всем библиотекам документов на сайте.</span><span class="sxs-lookup"><span data-stu-id="b81fd-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="b81fd-294">Можно добавить происхождение с определенным относительным путем.</span><span class="sxs-lookup"><span data-stu-id="b81fd-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="b81fd-295">Невозможно добавить начало с помощью полного пути.</span><span class="sxs-lookup"><span data-stu-id="b81fd-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="b81fd-296">В этом примере добавляется частное происхождение библиотеки siteassets на определенном сайте:</span><span class="sxs-lookup"><span data-stu-id="b81fd-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b81fd-297">В этом примере добавляется частное происхождение _папки1_ в библиотеке ресурсов сайтов коллекции сайтов:</span><span class="sxs-lookup"><span data-stu-id="b81fd-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="b81fd-298">Если на пути есть пробел, можно либо окружить путь двойными кавычками, либо заменить пространство url-адресом, кодировка которого составляет %20.</span><span class="sxs-lookup"><span data-stu-id="b81fd-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="b81fd-299">В следующих примерах добавлено частное происхождение папки _1_ в библиотеке ресурсов сайтов коллекции сайтов:</span><span class="sxs-lookup"><span data-stu-id="b81fd-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="b81fd-300">Дополнительные сведения об этой команде и ее синтаксис см. в [обзоре Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="b81fd-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="b81fd-301">В частных источниках ресурсы, общие для происхождения, должны иметь крупную версию, опубликованную до того, как к ним можно получить доступ из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="b81fd-302">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b81fd-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b81fd-303">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b81fd-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b81fd-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="b81fd-305">Пример: Настройка общедоступных страниц и библиотеки стилей для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="b81fd-306">Обычно эти истоки устанавливаются для вас по умолчанию, когда вы включаете CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="b81fd-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="b81fd-307">Однако, если вы хотите включить их вручную, выполните эти действия.</span><span class="sxs-lookup"><span data-stu-id="b81fd-307">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="b81fd-308">Чтобы определить библиотеку стилей как публичное происхождение, используйте смедлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="b81fd-309">Для определения магистральных страниц как общедоступных страниц используйте смедлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="b81fd-310">Дополнительные сведения об этой команде и ее синтаксис см. в [обзоре Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="b81fd-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b81fd-311">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b81fd-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b81fd-312">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b81fd-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b81fd-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="b81fd-314">Пример: Настройка частного происхождения для активов сайта, страниц сайта и публикации изображений для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="b81fd-315">Чтобы определить папку активов сайта как частное происхождение, используйте смлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="b81fd-316">Чтобы определить папку страниц сайта как частное происхождение, используйте кодлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="b81fd-317">Чтобы определить папку изображений публикации как частное происхождение, используйте кодлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="b81fd-318">Дополнительные сведения об этой команде и ее синтаксис см. в [обзоре Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="b81fd-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b81fd-319">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b81fd-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b81fd-320">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b81fd-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b81fd-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="b81fd-322">Пример: Настройка частного происхождения для коллекции сайтов для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="b81fd-323">Чтобы определить коллекцию сайтов как частное происхождение, используйте смлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="b81fd-324">Например,</span><span class="sxs-lookup"><span data-stu-id="b81fd-324">For example:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b81fd-325">Дополнительные сведения об этой команде и ее синтаксис см. в [обзоре Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="b81fd-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>
  
<span data-ttu-id="b81fd-326">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b81fd-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b81fd-327">Вы можете увидеть ожидаемое сообщение _Конфигурация,_ которое ожидается по мере подключения клиента SharePoint Online к службе CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="b81fd-328">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b81fd-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b81fd-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="b81fd-330">Управление CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-331">После настройки CDN можно внести изменения в конфигурацию при обновлении контента или изменении потребностей, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b81fd-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="b81fd-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="b81fd-333">Добавление, обновление или удаление активов из CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-334">После завершения действий по настройке можно добавлять новые активы и обновлять или удалять существующие активы, когда захотите.</span><span class="sxs-lookup"><span data-stu-id="b81fd-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="b81fd-335">Просто внести изменения в ресурсы в папке или библиотеке SharePoint, которые вы определили в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="b81fd-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b81fd-336">При добавлении нового актива он сразу же будет доступен через CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="b81fd-337">Однако при обновлении актива для распространения и распространения новой копии в CDN может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b81fd-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="b81fd-338">Если вам нужно получить расположение источника, можно использовать **комлет Get-SPOTenantCdnOrigins.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="b81fd-339">Сведения об использовании этого комлета см. в сайте [Get-SPOTenantCdnOrigins.](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)</span><span class="sxs-lookup"><span data-stu-id="b81fd-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="b81fd-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="b81fd-341">Удаление источника из CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-342">Вы можете удалить доступ к папке или библиотеке SharePoint, которые были определены в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="b81fd-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b81fd-343">Для этого используйте комлет **Remove-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="b81fd-344">Сведения об использовании этого cmdlet см. в см. в этой ленте [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="b81fd-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b81fd-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="b81fd-346">Изменение источника в CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-347">Вы не можете изменить созданное происхождение.</span><span class="sxs-lookup"><span data-stu-id="b81fd-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="b81fd-348">Вместо этого удалите начало и добавьте новый.</span><span class="sxs-lookup"><span data-stu-id="b81fd-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="b81fd-349">Дополнительные сведения см. в статью Удаление источника из [CDN Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) и добавление источника [для ваших активов.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)</span><span class="sxs-lookup"><span data-stu-id="b81fd-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="b81fd-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="b81fd-351">Отключение CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-352">Чтобы отключить CDN для организации, используйте комлет **Set-SPOTenantCdnEnabled.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="b81fd-353">Если для CDN включены как общедоступные, так и частные истоки, необходимо выполнить этот код дважды, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="b81fd-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="b81fd-354">Чтобы отключить использование общедоступных истоков в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-354">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="b81fd-355">Чтобы отключить использование личных истоков в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="b81fd-356">Дополнительные сведения об этом комлете см. в этой ленте [Set-SPOTenantCdnEnabled.](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)</span><span class="sxs-lookup"><span data-stu-id="b81fd-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="b81fd-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="b81fd-358">Настройка и настройка CDN Office 365 с помощью PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="b81fd-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="b81fd-359">Процедуры в этом разделе требуют, чтобы вы использовали PnP PowerShell для подключения к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b81fd-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="b81fd-360">Инструкции см. в [инструкции "Начало работы с PnP PowerShell".](https://github.com/SharePoint/PnP-PowerShell#getting-started)</span><span class="sxs-lookup"><span data-stu-id="b81fd-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="b81fd-361">Выполните эти действия, чтобы настроить CDN для хозяйского хозяйского актива в SharePoint Online с помощью PnP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b81fd-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="b81fd-362">Щелкните, чтобы развернуть</span><span class="sxs-lookup"><span data-stu-id="b81fd-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="b81fd-363">Включить организацию для использования CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-364">Прежде чем вносить изменения в параметры CDN клиента, необходимо получить текущее состояние закрытой конфигурации CDN в клиенте Office 365.</span><span class="sxs-lookup"><span data-stu-id="b81fd-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="b81fd-365">Подключение к клиенту с помощью PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b81fd-365">Connect to your tenant using PnP PowerShell:</span></span>

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="b81fd-366">Теперь используйте **комлет Get-PnPTenantCdnEnabled** для получения параметров состояния CDN у клиента:</span><span class="sxs-lookup"><span data-stu-id="b81fd-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="b81fd-367">Состояние CDN для указанного CdnType выводит на экран.</span><span class="sxs-lookup"><span data-stu-id="b81fd-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="b81fd-368">Используйте **комлет Set-PnPTenantCdnEnabled,** чтобы позволить организации использовать CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="b81fd-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="b81fd-369">Вы можете включить организацию для использования общедоступных и частных истоков одновременно.</span><span class="sxs-lookup"><span data-stu-id="b81fd-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="b81fd-370">Можно также настроить CDN, чтобы пропустить настройку истоков по умолчанию при его впусте.</span><span class="sxs-lookup"><span data-stu-id="b81fd-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="b81fd-371">Вы всегда можете добавить эти истоки позже, как описано в этой теме.</span><span class="sxs-lookup"><span data-stu-id="b81fd-371">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="b81fd-372">В PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b81fd-372">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="b81fd-373">Например, чтобы позволить организации использовать общедоступные и частные истоки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="b81fd-374">Чтобы позволить организации использовать как общедоступные, так и частные истоки, но пропустить настройку истоков по умолчанию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="b81fd-375">Сведения о происхождении по умолчанию, которые предусмотрены по умолчанию при встройки [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) Office 365, и о потенциальном влиянии пропуска установки истоков по умолчанию см. в истоках CDN по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b81fd-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="b81fd-376">Чтобы позволить организации использовать общедоступные истоки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-376">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="b81fd-377">Чтобы позволить организации использовать частные истоки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-377">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="b81fd-378">Дополнительные сведения об этом комлете см. в дополнительных сведениях [set-PnPTenantCdnEnabled.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="b81fd-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="b81fd-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="b81fd-380">Измените список типов файлов, чтобы включить их в CDN Office 365 (необязательный)</span><span class="sxs-lookup"><span data-stu-id="b81fd-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b81fd-381">При определении типов файлов с помощью комлета **Set-PnPTenantCdnPolicy** переопределяется определенный список.</span><span class="sxs-lookup"><span data-stu-id="b81fd-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b81fd-382">Если вы хотите добавить в список дополнительные типы файлов, сначала используйте этот список, чтобы узнать, какие типы файлов уже разрешены, и включите их в список вместе с новыми.</span><span class="sxs-lookup"><span data-stu-id="b81fd-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="b81fd-383">Для определения типов статических файлов, которые могут быть организованы государственными и частными истоками в CDN, используйте коммюлет **Set-PnPTenantCdnPolicy.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="b81fd-384">По умолчанию разрешены общие типы активов, например .css, .gif, .jpg и .js.</span><span class="sxs-lookup"><span data-stu-id="b81fd-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="b81fd-385">В PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b81fd-385">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="b81fd-386">Например, чтобы включить CDN для хозяйских файлов .css и .png, необходимо ввести команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="b81fd-387">Чтобы узнать, какие типы файлов в настоящее время разрешены CDN, используйте **cmdlet Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="b81fd-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b81fd-388">Дополнительные сведения об этих cmdlets см. в [set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) и [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="b81fd-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="b81fd-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="b81fd-390">Измените список классификаций сайтов, которые необходимо исключить из CDN Office 365 (необязательный)</span><span class="sxs-lookup"><span data-stu-id="b81fd-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b81fd-391">При исключении классификаций сайтов с помощью комлета **Set-PnPTenantCdnPolicy** переопределяется определенный список.</span><span class="sxs-lookup"><span data-stu-id="b81fd-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b81fd-392">Если вы хотите исключить дополнительные классификации сайтов, сначала используйте cmdlet, чтобы узнать, какие классификации уже исключены, а затем добавить их вместе с новыми.</span><span class="sxs-lookup"><span data-stu-id="b81fd-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="b81fd-393">Используйте **комлет Set-PnPTenantCdnPolicy,** чтобы исключить классификации сайтов, которые не требуется делать доступными в CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="b81fd-394">По умолчанию не исключаются никакие классификации сайтов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="b81fd-395">В PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b81fd-395">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="b81fd-396">Чтобы узнать, какие классификации сайтов в настоящее время ограничены, используйте **кодлет Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="b81fd-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b81fd-397">Свойства, которые будут _возвращены: IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ и _ExcludeIfNoScriptDisabled._</span><span class="sxs-lookup"><span data-stu-id="b81fd-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="b81fd-398">Свойство _IncludeFileExtensions_ содержит список расширений файлов, которые будут подаваться из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="b81fd-399">Расширения файлов по умолчанию отличаются между общедоступными и закрытыми.</span><span class="sxs-lookup"><span data-stu-id="b81fd-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="b81fd-400">Свойство _ExcludeRestrictedSiteClassifications_ содержит классификации сайтов, которые необходимо исключить из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="b81fd-401">Например, можно исключить сайты, помеченные как **Конфиденциальные,** чтобы содержимое сайтов с применяемой классификацией не обслуживалось из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="b81fd-402">Свойство _ExcludeIfNoScriptDisabled_ исключает контент из CDN на основе параметров атрибута _NoScript_ на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="b81fd-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="b81fd-403">По умолчанию для _атрибута NoScript_ устанавливается значение **Включено** для _современных_ сайтов и **отключено для** _классических_ сайтов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="b81fd-404">Это зависит от параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="b81fd-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="b81fd-405">Дополнительные сведения об этих cmdlets см. в [set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) и [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="b81fd-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="b81fd-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="b81fd-407">Добавление источника для ваших активов</span><span class="sxs-lookup"><span data-stu-id="b81fd-407">Add an origin for your assets</span></span>

<span data-ttu-id="b81fd-408">Чтобы определить происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="b81fd-409">Вы можете определить несколько источников.</span><span class="sxs-lookup"><span data-stu-id="b81fd-409">You can define multiple origins.</span></span> <span data-ttu-id="b81fd-410">Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b81fd-411">Никогда не следует разместить ресурсы, содержащие сведения о пользователях или которые считаются конфиденциальными для организации в публичном происхождении.</span><span class="sxs-lookup"><span data-stu-id="b81fd-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="b81fd-412">Значение пути _—_ это относительный путь к библиотеке или папке, которая содержит активы.</span><span class="sxs-lookup"><span data-stu-id="b81fd-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="b81fd-413">Помимо относительных путей, можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b81fd-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="b81fd-414">Origins поддерживает подкарды, предварительно заранее заранее примыкает к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="b81fd-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="b81fd-415">Это позволяет создавать истоки, охватывающие несколько сайтов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="b81fd-416">Например, чтобы включить все активы в папку masterpages для всех сайтов в качестве общедоступных в cdN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="b81fd-417">Модификатор под диктовки \* может использоваться только в начале пути и будет соответствовать всем сегментам URL-адресов по **/** указанному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="b81fd-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="b81fd-418">Путь может указать на библиотеку документов, папку или сайт.</span><span class="sxs-lookup"><span data-stu-id="b81fd-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="b81fd-419">Например, путь _\*/site1 будет_ соответствовать всем библиотекам документов на сайте.</span><span class="sxs-lookup"><span data-stu-id="b81fd-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="b81fd-420">Можно добавить происхождение с определенным относительным путем.</span><span class="sxs-lookup"><span data-stu-id="b81fd-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="b81fd-421">Невозможно добавить начало с помощью полного пути.</span><span class="sxs-lookup"><span data-stu-id="b81fd-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="b81fd-422">В этом примере добавляется частное происхождение библиотеки ресурсов сайта на определенном сайте:</span><span class="sxs-lookup"><span data-stu-id="b81fd-422">This example adds a private origin of the site assets library on a specific site:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b81fd-423">В этом примере добавляется частное происхождение _папки1_ в библиотеке ресурсов сайтов коллекции сайтов:</span><span class="sxs-lookup"><span data-stu-id="b81fd-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="b81fd-424">Если на пути есть пробел, можно либо окружить путь двойными кавычками, либо заменить пространство url-адресом, кодировка которого составляет %20.</span><span class="sxs-lookup"><span data-stu-id="b81fd-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="b81fd-425">В следующих примерах добавлено частное происхождение папки _1_ в библиотеке ресурсов сайтов коллекции сайтов:</span><span class="sxs-lookup"><span data-stu-id="b81fd-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="b81fd-426">Дополнительные сведения об этой команде и ее синтаксис см. в [добавлении-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="b81fd-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="b81fd-427">В частных источниках ресурсы, общие для происхождения, должны иметь крупную версию, опубликованную до того, как к ним можно получить доступ из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="b81fd-428">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b81fd-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b81fd-429">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b81fd-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b81fd-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="b81fd-431">Пример: Настройка общедоступных страниц и библиотеки стилей для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="b81fd-432">Обычно эти истоки устанавливаются для вас по умолчанию, когда вы включаете CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="b81fd-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="b81fd-433">Однако, если вы хотите включить их вручную, выполните эти действия.</span><span class="sxs-lookup"><span data-stu-id="b81fd-433">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="b81fd-434">Чтобы определить библиотеку стилей как общедоступный, используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="b81fd-435">Для определения магистральных страниц как общедоступных страниц используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="b81fd-436">Дополнительные сведения об этой команде и ее синтаксис см. в [добавлении-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="b81fd-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b81fd-437">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b81fd-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b81fd-438">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b81fd-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b81fd-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="b81fd-440">Пример: Настройка частного происхождения для активов сайта, страниц сайта и публикации изображений для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="b81fd-441">Чтобы определить папку активов сайта как частное происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="b81fd-442">Чтобы определить папку страниц сайта как частное происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="b81fd-443">Чтобы определить папку изображений публикации как частное происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="b81fd-444">Дополнительные сведения об этой команде и ее синтаксис см. в [добавлении-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="b81fd-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b81fd-445">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b81fd-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b81fd-446">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b81fd-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b81fd-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="b81fd-448">Пример: Настройка частного происхождения для коллекции сайтов для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="b81fd-449">Чтобы определить коллекцию сайтов как частное происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="b81fd-450">Например,</span><span class="sxs-lookup"><span data-stu-id="b81fd-450">For example:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b81fd-451">Дополнительные сведения об этой команде и ее синтаксис см. в [добавлении-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="b81fd-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="b81fd-452">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b81fd-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b81fd-453">Вы можете увидеть ожидаемое сообщение _Конфигурация,_ которое ожидается по мере подключения клиента SharePoint Online к службе CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="b81fd-454">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b81fd-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b81fd-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="b81fd-456">Управление CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-457">После настройки CDN можно внести изменения в конфигурацию при обновлении контента или изменении потребностей, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b81fd-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="b81fd-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="b81fd-459">Добавление, обновление или удаление активов из CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-460">После завершения действий по настройке можно добавлять новые активы и обновлять или удалять существующие активы, когда захотите.</span><span class="sxs-lookup"><span data-stu-id="b81fd-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="b81fd-461">Просто внести изменения в ресурсы в папке или библиотеке SharePoint, которые вы определили в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="b81fd-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b81fd-462">При добавлении нового актива он сразу же будет доступен через CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="b81fd-463">Однако при обновлении актива для распространения и распространения новой копии в CDN может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b81fd-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="b81fd-464">Если вам нужно получить расположение источника, можно использовать **комлет Get-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="b81fd-465">Сведения об использовании этого комлета см. в [сайте Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="b81fd-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b81fd-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="b81fd-467">Удаление источника из CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-468">Вы можете удалить доступ к папке или библиотеке SharePoint, которые были определены в качестве источника.</span><span class="sxs-lookup"><span data-stu-id="b81fd-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b81fd-469">Для этого используйте комлет **Remove-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="b81fd-470">Сведения о том, как использовать этот комлет, см. в этой брошюре [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="b81fd-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b81fd-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="b81fd-472">Изменение источника в CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-473">Вы не можете изменить созданное происхождение.</span><span class="sxs-lookup"><span data-stu-id="b81fd-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="b81fd-474">Вместо этого удалите начало и добавьте новый.</span><span class="sxs-lookup"><span data-stu-id="b81fd-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="b81fd-475">Дополнительные сведения см. в статью Удаление источника из [CDN Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) и добавление источника [для ваших активов.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)</span><span class="sxs-lookup"><span data-stu-id="b81fd-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="b81fd-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="b81fd-477">Отключение CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-478">Чтобы отключить CDN для организации, используйте комлет **Set-PnPTenantCdnEnabled.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="b81fd-479">Если для CDN включены как общедоступные, так и частные истоки, необходимо выполнить этот код дважды, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="b81fd-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="b81fd-480">Чтобы отключить использование общедоступных истоков в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-480">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="b81fd-481">Чтобы отключить использование личных истоков в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="b81fd-482">Дополнительные сведения об этом комлете см. в дополнительных сведениях [set-PnPTenantCdnEnabled.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="b81fd-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="b81fd-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="b81fd-484">Установка и настройка сети CDN Office 365 с помощью интерфейса командной строки Office 365:</span><span class="sxs-lookup"><span data-stu-id="b81fd-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="b81fd-485">Процедуры в этом разделе требуют установки [CLI Office 365.](https://aka.ms/o365cli)</span><span class="sxs-lookup"><span data-stu-id="b81fd-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="b81fd-486">Далее подключите клиента Office 365 с помощью команды [входа.](https://pnp.github.io/office365-cli/cmd/login/)</span><span class="sxs-lookup"><span data-stu-id="b81fd-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="b81fd-487">Выполните эти действия, чтобы настроить CDN для пребывания активов в SharePoint Online с помощью CLI Office 365.</span><span class="sxs-lookup"><span data-stu-id="b81fd-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="b81fd-488">Щелкните, чтобы развернуть</span><span class="sxs-lookup"><span data-stu-id="b81fd-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="b81fd-489">Включить CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-490">Вы можете управлять состоянием сети CDN Office 365 в клиенте с помощью команды [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/).</span><span class="sxs-lookup"><span data-stu-id="b81fd-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="b81fd-491">Чтобы включить в клиенте общедоступную сеть CDN Office 365, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```cli
spo cdn set --type Public --enabled true
```

<span data-ttu-id="b81fd-492">Чтобы включить CDN SharePoint Office 365, выполните:</span><span class="sxs-lookup"><span data-stu-id="b81fd-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="b81fd-493">Просмотр текущего состояния сети CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-494">Чтобы проверить, включен или отключен определенный тип CDN Office 365, используйте [команду spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)</span><span class="sxs-lookup"><span data-stu-id="b81fd-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="b81fd-495">Чтобы проверить, включена ли общедоступная сеть CDN Office 365, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="b81fd-496">Просмотр истоков CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="b81fd-497">Чтобы просмотреть список настроенных в данный момент общедоступных источников CDN Office 365, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```cli
spo cdn origin list --type Public
```

<span data-ttu-id="b81fd-498">Сведения [о происхождении](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) по умолчанию, которые будут предусмотрены по умолчанию при внии CDN Office 365, см. в истоках CDN по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b81fd-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="b81fd-499">Добавление источника CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b81fd-500">Никогда не следует разместить ресурсы, которые считаются конфиденциальными для организации, в библиотеку документов SharePoint, настроенную как общедоступный источник.</span><span class="sxs-lookup"><span data-stu-id="b81fd-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="b81fd-501">Чтобы определить источник CDN, используйте команду [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/).</span><span class="sxs-lookup"><span data-stu-id="b81fd-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="b81fd-502">Вы можете определить несколько источников.</span><span class="sxs-lookup"><span data-stu-id="b81fd-502">You can define multiple origins.</span></span> <span data-ttu-id="b81fd-503">Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="b81fd-504">Где `path` находится относительный путь к папке с активами.</span><span class="sxs-lookup"><span data-stu-id="b81fd-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="b81fd-505">Помимо относительных путей, можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b81fd-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="b81fd-506">Чтобы включить все активы в **Галерею основных** страниц всех сайтов как общедоступные, выполните:</span><span class="sxs-lookup"><span data-stu-id="b81fd-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```cli
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="b81fd-507">Чтобы настроить частный источник для определенного семейства веб-сайтов, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b81fd-507">To configure a private origin for a specific site collection, execute:</span></span>

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="b81fd-508">После добавления источника CDN может понадобиться до 15 минут, чтобы получить файлы через службу CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="b81fd-509">Вы можете проверить, включен ли тот или иной источник, с помощью команды [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/).</span><span class="sxs-lookup"><span data-stu-id="b81fd-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="b81fd-510">Удаление источника CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="b81fd-511">Чтобы удалить источник CDN для указанного типа CDN, используйте команду [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/).</span><span class="sxs-lookup"><span data-stu-id="b81fd-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="b81fd-512">Чтобы удалить общедоступный источник из конфигурации CDN, выполните:</span><span class="sxs-lookup"><span data-stu-id="b81fd-512">To remove a public origin from the CDN configuration, execute:</span></span>

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="b81fd-513">Удаление происхождения CDN не влияет на файлы, хранимые в любой библиотеке документов, соответствующие этому происхождению.</span><span class="sxs-lookup"><span data-stu-id="b81fd-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="b81fd-514">Если эти активы ссылались с помощью URL-адреса SharePoint, SharePoint автоматически переключается на исходный URL-адрес, указывав на библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="b81fd-515">Если же ссылки на активы были указаны с помощью общедоступных URL-адресов CDN, то удаление источника перебьет ссылку, и вам потребуется вручную изменить их.</span><span class="sxs-lookup"><span data-stu-id="b81fd-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="b81fd-516">Изменение происхождения CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="b81fd-517">Изменить имеющийся источник CDN невозможно.</span><span class="sxs-lookup"><span data-stu-id="b81fd-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="b81fd-518">Вместо этого следует удалить определенный ранее источник CDN с помощью команды `spo cdn origin remove` и добавить новый с помощью команды `spo cdn origin add`.</span><span class="sxs-lookup"><span data-stu-id="b81fd-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="b81fd-519">Измените типы файлов, чтобы включить их в CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-520">По умолчанию в CDN включаются следующие типы файлов: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff и .woff2_.</span><span class="sxs-lookup"><span data-stu-id="b81fd-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="b81fd-521">Если требуется включить в сеть CDN дополнительные типы файлов, вы можете изменить конфигурацию CDN с помощью команды [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).</span><span class="sxs-lookup"><span data-stu-id="b81fd-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="b81fd-522">При изменении списка типов файлов перезаписывается текущий список.</span><span class="sxs-lookup"><span data-stu-id="b81fd-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="b81fd-523">Если требуется включить дополнительные типы файлов, сперва используйте команду [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/), чтобы узнать, какие типы файлов настроены в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="b81fd-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="b81fd-524">Чтобы добавить _тип файла JSON_ в список типов файлов по умолчанию, включенных в общедоступный CDN, выполните:</span><span class="sxs-lookup"><span data-stu-id="b81fd-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="b81fd-525">Изменение списка классификаций сайтов, которые требуется исключить из сети CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-526">Чтобы исключить классификации сайтов, которые не должны быть доступны в сети CDN, используйте команду [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).</span><span class="sxs-lookup"><span data-stu-id="b81fd-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="b81fd-527">По умолчанию не исключаются никакие классификации сайтов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="b81fd-528">При изменении списка исключаемых классификаций сайтов перезаписывается текущий список.</span><span class="sxs-lookup"><span data-stu-id="b81fd-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="b81fd-529">Если требуется исключить дополнительные классификации сайтов, сперва используйте команду [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/), чтобы узнать, какие классификации настроены в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="b81fd-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="b81fd-530">Чтобы исключить сайты, классифицируются _как HBI_ из общедоступных CDN, выполните</span><span class="sxs-lookup"><span data-stu-id="b81fd-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="b81fd-531">Отключение CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-532">Чтобы отключить сеть CDN Office 365, используйте команду `spo cdn set`. Пример:</span><span class="sxs-lookup"><span data-stu-id="b81fd-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="b81fd-533">Использование ресурсов CDN</span><span class="sxs-lookup"><span data-stu-id="b81fd-533">Using your CDN assets</span></span>

<span data-ttu-id="b81fd-534">Теперь, когда вы включили CDN и настроенные истоки и политики, можно приступить к использованию ресурсов CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="b81fd-535">Этот раздел поможет вам понять, как использовать URL-адреса CDN на страницах и контенте SharePoint, чтобы SharePoint перенаправляла запросы на активы как государственного, так и частного происхождения в CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="b81fd-536">Обновление ссылок на ресурсы CDN</span><span class="sxs-lookup"><span data-stu-id="b81fd-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="b81fd-537">Использование ресурсов в общедоступных источниках</span><span class="sxs-lookup"><span data-stu-id="b81fd-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="b81fd-538">Использование активов в частном происхождении</span><span class="sxs-lookup"><span data-stu-id="b81fd-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="b81fd-539">Сведения об использовании CDN для размещения клиентских веб-частей см. в разделе Host [your client-side web part from Office 365 CDN (Hello World part 4).](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)</span><span class="sxs-lookup"><span data-stu-id="b81fd-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="b81fd-540">Если вы добавим _папку ClientSideAssets_ в частный список истоков **CDN,** пользовательские веб-части, на которые будет организовано CDN, не будут отрисовки.</span><span class="sxs-lookup"><span data-stu-id="b81fd-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="b81fd-541">Файлы, используемые веб-частями SPFX, могут использовать только общедоступные CDN, а папка ClientSideAssets является по умолчанию для общедоступных CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="b81fd-542">Обновление ссылок на ресурсы CDN</span><span class="sxs-lookup"><span data-stu-id="b81fd-542">Updating links to CDN assets</span></span>

<span data-ttu-id="b81fd-543">Чтобы использовать добавленные в источник ресурсы, просто обновив ссылки на исходный файл с помощью пути к файлу в начале.</span><span class="sxs-lookup"><span data-stu-id="b81fd-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="b81fd-544">Изменить страницу или контент, содержащий ссылки на активы, добавленные в источник.</span><span class="sxs-lookup"><span data-stu-id="b81fd-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="b81fd-545">Вы также можете использовать один из нескольких методов глобального поиска и замены ссылок на веб-сайт или коллекцию сайтов, если вы хотите обновить ссылку на данный актив везде, где он появится.</span><span class="sxs-lookup"><span data-stu-id="b81fd-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="b81fd-546">Для каждой ссылки на актив в источнике замените путь путем к файлу в происхождении CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="b81fd-547">Можно использовать относительные пути.</span><span class="sxs-lookup"><span data-stu-id="b81fd-547">You can use relative paths.</span></span>
+ <span data-ttu-id="b81fd-548">Сохранение страницы или контента.</span><span class="sxs-lookup"><span data-stu-id="b81fd-548">Save the page or content.</span></span>

<span data-ttu-id="b81fd-549">Например, рассмотрим изображение _/site/SiteAssets/images/image.png_, которое вы скопировали в папку библиотеки документов _/site/CDN_origins/public/_.</span><span class="sxs-lookup"><span data-stu-id="b81fd-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="b81fd-550">Чтобы использовать актив CDN, замените исходный путь к расположению файла изображений путем к источнику, чтобы сделать новый _URL-адрес /site/CDN_origins/public/image.png_.</span><span class="sxs-lookup"><span data-stu-id="b81fd-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="b81fd-551">Если вы хотите использовать полный URL-адрес актива вместо относительного пути, сострой ссылку так:</span><span class="sxs-lookup"><span data-stu-id="b81fd-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="b81fd-552">В общем, не следует жестко кодировать URL-адреса непосредственно к активам в CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="b81fd-553">Однако при необходимости можно вручную создавать URL-адреса для активов в общедоступных источниках.</span><span class="sxs-lookup"><span data-stu-id="b81fd-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="b81fd-554">Дополнительные сведения см. в [выпуске Url-адресов CDN hardcoding для общедоступных активов.](use-microsoft-365-cdn-with-spo.md)</span><span class="sxs-lookup"><span data-stu-id="b81fd-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md).</span></span>

<span data-ttu-id="b81fd-555">Чтобы узнать о том, как убедиться в том, что ресурсы обслуживаются из CDN, см. в руб. Как подтвердить, что ресурсы обслуживаются [cdN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) в деле устранения неполадок [cdN Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="b81fd-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="b81fd-556">Использование ресурсов в общедоступных источниках</span><span class="sxs-lookup"><span data-stu-id="b81fd-556">Using assets in public origins</span></span>

<span data-ttu-id="b81fd-557">Функция **публикации** в SharePoint Online автоматически переписывала URL-адреса активов, хранимых в общедоступных источниках, в их эквиваленты CDN, чтобы активы обслуживались из службы CDN вместо SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b81fd-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="b81fd-558">Если ваше происхождение находится на сайте с включенной функцией Публикации, а активы, которые необходимо разгрузить в CDN, находятся в одной из следующих категорий, SharePoint автоматически переписывание URL-адресов для активов в происхождении при условии, что актив не был исключен политикой CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="b81fd-559">Ниже представлен обзор ссылок, которые автоматически заменяет функция публикации в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b81fd-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="b81fd-560">URL-адреса IMG-, LINK- и CSS-файлов в HTML-откликах классической страницы публикации.</span><span class="sxs-lookup"><span data-stu-id="b81fd-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="b81fd-561">Это относится и к изображениям, добавленным авторами в HTML-содержимом страницы.</span><span class="sxs-lookup"><span data-stu-id="b81fd-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="b81fd-562">URL-адреса изображений в веб-части "Слайд-шоу библиотеки рисунков".</span><span class="sxs-lookup"><span data-stu-id="b81fd-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="b81fd-563">Поля изображений в результатах работы REST API SPList (RenderListDataAsStream).</span><span class="sxs-lookup"><span data-stu-id="b81fd-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="b81fd-564">Используйте новое свойство _ImageFieldsToTryRewriteToCdnUrls_ для предоставления разделенного запятой списка полей</span><span class="sxs-lookup"><span data-stu-id="b81fd-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="b81fd-565">Поддерживает поля гиперссылки и поля PublishingImage</span><span class="sxs-lookup"><span data-stu-id="b81fd-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="b81fd-566">Renditions изображений SharePoint</span><span class="sxs-lookup"><span data-stu-id="b81fd-566">SharePoint image renditions</span></span>

<span data-ttu-id="b81fd-567">Следующая схема иллюстрирует рабочий процесс, когда SharePoint получает запрос на страницу, содержащую активы из общего происхождения.</span><span class="sxs-lookup"><span data-stu-id="b81fd-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="b81fd-568">![Схема рабочего процесса: ирисовка активов CDN Office 365 из общего происхождения](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Рабочий процесс: ирисовка активов CDN Office 365 из общего происхождения")</span><span class="sxs-lookup"><span data-stu-id="b81fd-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="b81fd-569">Если вы хотите отключить автоматическое переписывание определенных URL-адресов на странице, вы можете проверить страницу и добавить параметр строки **запроса? NoAutoReWrites=true** в конце каждой ссылки, отключаемой.</span><span class="sxs-lookup"><span data-stu-id="b81fd-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="b81fd-570">Создание URL-адресов CDN для общедоступных активов</span><span class="sxs-lookup"><span data-stu-id="b81fd-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="b81fd-571">Если  функция Публикации не включена для общего происхождения или актив не является одним из типов ссылок, поддерживаемых функцией автоматического перезаписи службы CDN, можно вручную создать URL-адреса для расположения ресурсов CDN и использовать эти URL-адреса в контенте.</span><span class="sxs-lookup"><span data-stu-id="b81fd-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="b81fd-572">Нельзя жестко кодировать или создавать URL-адреса CDN для активов частного происхождения, так как необходимый маркер доступа, формирующий последний раздел URL-адреса, создается во время запроса ресурса.</span><span class="sxs-lookup"><span data-stu-id="b81fd-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="b81fd-573">Вы можете создать URL-адрес для общедоступных CDN, и URL-адрес не должен быть жестко закодироваться, так как он подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="b81fd-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="b81fd-574">Для общедоступных ресурсов CDN формат URL-адресов будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b81fd-574">For public CDN assets, the URL format will look like the following:</span></span>

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="b81fd-575">Замените **TenantHostName** именем клиента.</span><span class="sxs-lookup"><span data-stu-id="b81fd-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="b81fd-576">Пример.</span><span class="sxs-lookup"><span data-stu-id="b81fd-576">Example:</span></span>

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> <span data-ttu-id="b81fd-577">Свойство контекста страницы должно использоваться для построения префикса вместо жесткого кодирования https://publiccdn.sharepointonline.com ".</span><span class="sxs-lookup"><span data-stu-id="b81fd-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="b81fd-578">URL-адрес подлежит изменению и не должен быть жестко закодироваться.</span><span class="sxs-lookup"><span data-stu-id="b81fd-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="b81fd-579">Если вы используете шаблоны отображения с помощью Classic SharePoint Online, вы можете использовать свойство "window._spPageContextInfo.publicCdnBaseUrl" в шаблоне отображения для префикса URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="b81fd-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="b81fd-580">Если вы являетсяе веб-частями SPFx для современной и классической SharePoint, вы можете использовать свойство this.context.pageContext.legacyPageContext.publicCdnBaseUrl" (this.context.pageContext.legacyPageContext.publicCdnBaseUrl).</span><span class="sxs-lookup"><span data-stu-id="b81fd-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="b81fd-581">При этом будет предоставляться префикс, чтобы если он был изменен, то реализация обновляется вместе с ним.</span><span class="sxs-lookup"><span data-stu-id="b81fd-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="b81fd-582">В качестве примера для SPFx URL-адрес можно построить с помощью свойства "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "relativeURL для элемента".</span><span class="sxs-lookup"><span data-stu-id="b81fd-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="b81fd-583">См. [в тексте Использование CDN в клиентском коде,](https://youtu.be/IH1RbQlbhIA) который является частью серии производительности [1 сезона](https://aka.ms/sppnp-perfvideos)</span><span class="sxs-lookup"><span data-stu-id="b81fd-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="b81fd-584">Использование активов в частном происхождении</span><span class="sxs-lookup"><span data-stu-id="b81fd-584">Using assets in private origins</span></span>

<span data-ttu-id="b81fd-585">Для использования активов в частном происхождении не требуется дополнительная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="b81fd-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="b81fd-586">SharePoint Online автоматически переписывал URL-адреса для активов частного происхождения, поэтому запросы на эти активы всегда будут подаваться из CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="b81fd-587">Невозможно вручную создавать URL-адреса для активов CDN в частном происхождении, так как эти URL-адреса содержат маркеры, которые должны быть автоматически созданы SharePoint Online во время запроса актива.</span><span class="sxs-lookup"><span data-stu-id="b81fd-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="b81fd-588">Доступ к активам частного происхождения защищен динамически созданными маркерами на основе разрешений пользователей на происхождение с оговорками, описанными в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b81fd-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="b81fd-589">Пользователи должны иметь по крайней мере **доступ** к истокам для отображения контента cdN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="b81fd-590">Следующая схема иллюстрирует рабочий процесс, когда SharePoint получает запрос на страницу, содержащую активы частного происхождения.</span><span class="sxs-lookup"><span data-stu-id="b81fd-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="b81fd-591">![Схема рабочего процесса: ирисовка активов CDN Office 365 из частного происхождения](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Рабочий процесс: ирисовка активов CDN Office 365 из частного происхождения")</span><span class="sxs-lookup"><span data-stu-id="b81fd-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="b81fd-592">Авторизация на основе маркеров в частном происхождении</span><span class="sxs-lookup"><span data-stu-id="b81fd-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="b81fd-593">Доступ к активам частного происхождения в CDN Office 365 предоставляется маркерами, созданными SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b81fd-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="b81fd-594">Пользователям, у которых уже есть разрешение на доступ к папке или библиотеке, назначенной происхождением, автоматически выдают маркеры, которые позволяют пользователю получать доступ к файлу на основе уровня разрешений.</span><span class="sxs-lookup"><span data-stu-id="b81fd-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="b81fd-595">Эти маркеры доступа действительны в течение 30-90 минут после их получения, чтобы предотвратить атаки повтора маркеров.</span><span class="sxs-lookup"><span data-stu-id="b81fd-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="b81fd-596">После получения маркера доступа SharePoint Online возвращает клиенту настраиваемый URI, содержащий два параметра авторизации _(маркер_ авторизации края) и _овсяный_ (маркер авторизации происхождения).</span><span class="sxs-lookup"><span data-stu-id="b81fd-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="b81fd-597">Структура каждого маркера —< времени действия в формате времени эпохи _>__<'secure signature'>_.</span><span class="sxs-lookup"><span data-stu-id="b81fd-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="b81fd-598">Например,</span><span class="sxs-lookup"><span data-stu-id="b81fd-598">For example:</span></span>

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="b81fd-599">Любой, кто владеет маркером, может получить доступ к ресурсу cdN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="b81fd-600">Однако URL-адреса, содержащие эти маркеры доступа, делятся только по HTTPS, поэтому если URL-адрес явно не будет доступен конечному пользователю до истечения срока действия маркера, актив будет недоступен для неавторизованных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b81fd-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="b81fd-601">Разрешения на уровне элементов не поддерживаются для активов в частном происхождении</span><span class="sxs-lookup"><span data-stu-id="b81fd-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="b81fd-602">Важно отметить, что SharePoint Online не поддерживает разрешения на уровне элементов для активов частного происхождения.</span><span class="sxs-lookup"><span data-stu-id="b81fd-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="b81fd-603">Например, для файла, расположенного по адресу, пользователи имеют эффективный доступ к файлу с учетом `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` следующих условий:</span><span class="sxs-lookup"><span data-stu-id="b81fd-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="b81fd-604">User</span><span class="sxs-lookup"><span data-stu-id="b81fd-604">User</span></span>  |<span data-ttu-id="b81fd-605">Разрешения</span><span class="sxs-lookup"><span data-stu-id="b81fd-605">Permissions</span></span>  |<span data-ttu-id="b81fd-606">Эффективный доступ</span><span class="sxs-lookup"><span data-stu-id="b81fd-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b81fd-607">Пользователь 1</span><span class="sxs-lookup"><span data-stu-id="b81fd-607">User 1</span></span>     |<span data-ttu-id="b81fd-608">Имеет доступ к папке1</span><span class="sxs-lookup"><span data-stu-id="b81fd-608">Has access to folder1</span></span>         |<span data-ttu-id="b81fd-609">Доступ к image1.jpg из CDN</span><span class="sxs-lookup"><span data-stu-id="b81fd-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="b81fd-610">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="b81fd-610">User 2</span></span>     |<span data-ttu-id="b81fd-611">Не имеет доступа к папке1</span><span class="sxs-lookup"><span data-stu-id="b81fd-611">Does not have access to folder1</span></span>         |<span data-ttu-id="b81fd-612">Не удается image1.jpg из CDN</span><span class="sxs-lookup"><span data-stu-id="b81fd-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="b81fd-613">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="b81fd-613">User 3</span></span>     |<span data-ttu-id="b81fd-614">Не имеет доступа к папке1, но имеет явное разрешение на доступ к image1.jpg в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="b81fd-615">Можно получить доступ к image1.jpg непосредственно из SharePoint Online, но не из CDN</span><span class="sxs-lookup"><span data-stu-id="b81fd-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="b81fd-616">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="b81fd-616">User 4</span></span>     |<span data-ttu-id="b81fd-617">Имеет доступ к папке1, но ему явно было отказано в доступе к image1.jpg SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="b81fd-618">Не удается получить доступ к активу из SharePoint Online, но может получить доступ к активу из CDN, несмотря на то, что ему было отказано в доступе к файлу в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="b81fd-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="b81fd-620">Устранение неполадок cdN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="b81fd-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="b81fd-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="b81fd-622">Как подтвердить, что ресурсы обслуживаются cdN?</span><span class="sxs-lookup"><span data-stu-id="b81fd-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="b81fd-623">После того как вы добавили ссылки на ресурсы CDN на страницу, вы можете подтвердить, что актив обслуживается из CDN, просматривая страницу, щелкнув правой кнопкой мыши по изображению после отрисовки и просмотрев URL-адрес изображения.</span><span class="sxs-lookup"><span data-stu-id="b81fd-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="b81fd-624">Вы также можете использовать средства разработчика браузера для просмотра URL-адреса для каждого актива на странице или с помощью средства трассировки сторонних сетей.</span><span class="sxs-lookup"><span data-stu-id="b81fd-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="b81fd-625">Если вы используете сетевой инструмент, например Fiddler, чтобы протестировать свои активы вне отрисовки актива со страницы SharePoint, необходимо вручную добавить загонщика ссылок "Referer:" в запрос GET, где URL-адрес является корневым URL-адресом клиента `https://yourdomain.sharepoint.com` SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b81fd-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="b81fd-626">Невозможно протестировать URL-адреса CDN непосредственно в веб-браузере, так как должен быть ссылщик из SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b81fd-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="b81fd-627">Однако если добавить URL-адрес актива CDN на страницу SharePoint, а затем открыть страницу в браузере, на странице будет отрисован актив CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="b81fd-628">Дополнительные сведения об использовании средств разработчика в браузере Microsoft Edge см. в [веб-сайте Microsoft Edge Developer Tools.](/microsoft-edge/devtools-guide)</span><span class="sxs-lookup"><span data-stu-id="b81fd-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="b81fd-629">Чтобы просмотреть короткое видео, размещенное на youTube-канале Шаблоны и практики разработчика [SharePoint,](https://aka.ms/sppnp-videos) демонстрирующее, как убедиться, что ваш CDN работает, см. в раздел Проверка использования [CDN](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)и обеспечение оптимального подключения к сети.</span><span class="sxs-lookup"><span data-stu-id="b81fd-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="b81fd-630">Почему недоступны активы нового происхождения?</span><span class="sxs-lookup"><span data-stu-id="b81fd-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="b81fd-631">Активы нового происхождения не будут сразу доступны для использования, так как для регистрации требуется время для распространения через CDN и для отправки активов из происхождения в хранилище CDN.</span><span class="sxs-lookup"><span data-stu-id="b81fd-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="b81fd-632">Время, необходимое для того, чтобы активы были доступны в CDN, зависит от того, сколько ресурсов и размеров файлов.</span><span class="sxs-lookup"><span data-stu-id="b81fd-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="b81fd-633">Моя клиентская веб-часть или решение SharePoint Framework не работают</span><span class="sxs-lookup"><span data-stu-id="b81fd-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="b81fd-634">Когда вы включаете CDN Office 365 для общедоступных истоков, служба CDN автоматически создает эти истоки по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="b81fd-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="b81fd-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="b81fd-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="b81fd-636">\*/STYLE LIBRARY</span><span class="sxs-lookup"><span data-stu-id="b81fd-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="b81fd-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="b81fd-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="b81fd-638">Если происхождение \*/clientsideassets отсутствует, решения SharePoint Framework сбой, и не создаются предупреждения или сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="b81fd-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="b81fd-639">Это происхождение может быть пропущено либо из-за включения CDN с параметром _-NoDefaultOrigins,_ заданным $true, либо потому, что происхождение было удалено вручную. </span><span class="sxs-lookup"><span data-stu-id="b81fd-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="b81fd-640">Вы можете проверить, какие истоки присутствуют со следующей командой PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b81fd-640">You can check to see which origins are present with the following PowerShell command:</span></span>

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="b81fd-641">Или вы можете проверить cLI Office 365:</span><span class="sxs-lookup"><span data-stu-id="b81fd-641">Or you can check with the Office 365 CLI:</span></span>

```cli
spo cdn origin list
```

<span data-ttu-id="b81fd-642">Чтобы добавить начало в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b81fd-642">To add the origin in PowerShell:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="b81fd-643">Чтобы добавить источник в CLI Office 365:</span><span class="sxs-lookup"><span data-stu-id="b81fd-643">To add the origin in the Office 365 CLI:</span></span>

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="b81fd-644">Какие модули PowerShell и оболочки CLI необходимы для работы с CDN Office 365?</span><span class="sxs-lookup"><span data-stu-id="b81fd-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="b81fd-645">Вы можете работать с CDN Office 365 с помощью модуля PowerShell командной оболочки **SharePoint Online** или **CLI Office 365.**</span><span class="sxs-lookup"><span data-stu-id="b81fd-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="b81fd-646">Начало работы с командной консолью SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b81fd-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="b81fd-647">Установка Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="b81fd-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="b81fd-648">См. также</span><span class="sxs-lookup"><span data-stu-id="b81fd-648">See also</span></span>

[<span data-ttu-id="b81fd-649">Сети доставки содержимого</span><span class="sxs-lookup"><span data-stu-id="b81fd-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="b81fd-650">Планирование сети и настройка производительности для Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="b81fd-651">Серия производительности SharePoint — видеосерия CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b81fd-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)