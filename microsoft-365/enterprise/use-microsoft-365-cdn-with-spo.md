---
title: Используйте Office 365 сеть доставки содержимого (CDN) с SharePoint Online
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
description: Узнайте, как использовать Office 365 сеть доставки содержимого (CDN) для ускорения доставки SharePoint интернет-ресурсов.
ms.openlocfilehash: 5e9ed00462b7073c7e03f62a5de6bf26f1e586af
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289455"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="b4bd6-103">Использование сети доставки содержимого Office 365 с SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4bd6-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="b4bd6-104">Вы можете использовать встроенную сеть доставки содержимого (CDN) Office 365 для размещения статических ресурсов, чтобы повысить производительность страниц SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="b4bd6-105">Сеть CDN Office 365 повышает производительность путем кэширования статических ресурсов ближе к браузерам, которые их запрашивают, что повышает скорость скачиваний и снижает задержку.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="b4bd6-106">Кроме того, Office 365 CDN протокол [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) для улучшения сжатия и http pipelining.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="b4bd6-107">Служба CDN Office 365 входит в состав подписки на SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="b4bd6-108">Данные Office 365 CDN доступны только для клиентов в облаке **Production** (во всем мире).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="b4bd6-109">В настоящее время клиенты в облаках правительства США, Китая и Германии не поддерживают Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="b4bd6-110">Сети доставки содержимого Office 365 состоит из нескольких сетей CDN, позволяющих размещать статические ресурсы в нескольких расположениях или _источниках_ и использовать их из глобальных высокоскоростных сетей.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="b4bd6-111">В зависимости от типа содержимого, которое необходимо разместить в сети CDN Office 365, можно добавить **общедоступные** источники, **закрытые** источники или оба варианта.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="b4bd6-112">Дополнительные [сведения](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) о различиях между государственными и частными происхождениями см. в дополнительных сведениях о том, должно ли каждое происхождение быть общедоступным или частным.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="b4bd6-113">![Office 365 CDN схема](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN схема")</span><span class="sxs-lookup"><span data-stu-id="b4bd6-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="b4bd6-114">Если вы уже знакомы с тем, как работают cdNs, необходимо выполнить только несколько действий, чтобы включить Office 365 CDN для клиента.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="b4bd6-115">В этом разделе описывается, как.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-115">This topic describes how.</span></span> <span data-ttu-id="b4bd6-116">Ознакомьтесь с информацией о том, как начать размещение статических активов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="b4bd6-117">Существуют и другие cdNs, на которые можно использовать Office 365 для специализированных сценариев использования, но они не обсуждаются в этой теме, так как они не Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="b4bd6-118">Дополнительные сведения см. [в других cdNs Microsoft.](content-delivery-networks.md#other-microsoft-cdns)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="b4bd6-119">**Возвращайся к [планированию сети и настройке производительности для Office 365.](./network-planning-and-performance.md)**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-119">**Head back to [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="b4bd6-120">Обзор работы с Office 365 CDN в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4bd6-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="b4bd6-121">Чтобы настроить Office 365 CDN организации, выполните следующие основные действия:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="b4bd6-122">Планирование развертывания Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="b4bd6-123">[Определите, какие статические](use-microsoft-365-cdn-with-spo.md#CDNAssets)активы необходимо установить в CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="b4bd6-124">[Определите, где нужно хранить свои активы.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="b4bd6-125">Это расположение может быть SharePoint, библиотекой или папкой и называется _происхождением._</span><span class="sxs-lookup"><span data-stu-id="b4bd6-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="b4bd6-126">[Выберите, должно ли каждое происхождение быть общедоступным или частным.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="b4bd6-127">Можно добавить несколько источников как общедоступных, так и частных типов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="b4bd6-128">Настройка и настройка CDN с помощью PowerShell или SharePoint CLI</span><span class="sxs-lookup"><span data-stu-id="b4bd6-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="b4bd6-129">Настройка и настройка CDN с помощью SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="b4bd6-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="b4bd6-130">Настройка и настройка CDN с помощью PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4bd6-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="b4bd6-131">Настройка и настройка CDN с помощью Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="b4bd6-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="b4bd6-132">Когда вы выполните этот шаг, у вас будет:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="b4bd6-133">Включена CDN для организации.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="b4bd6-134">Добавлены истоки, определяющие каждое происхождение как общедоступные или частные.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="b4bd6-135">После установки можно управлять Office 365 CDN [с](use-microsoft-365-cdn-with-spo.md#CDNManage) помощью:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>

+ <span data-ttu-id="b4bd6-136">Добавление, обновление и удаление активов</span><span class="sxs-lookup"><span data-stu-id="b4bd6-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="b4bd6-137">Добавление и удаление истоков</span><span class="sxs-lookup"><span data-stu-id="b4bd6-137">Adding and removing origins</span></span>
+ <span data-ttu-id="b4bd6-138">Настройка CDN политик</span><span class="sxs-lookup"><span data-stu-id="b4bd6-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="b4bd6-139">При необходимости отключить CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="b4bd6-140">Наконец, см. в [CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) ресурсов, чтобы узнать о доступе к CDN активам как государственного, так и частного происхождения.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="b4bd6-141">См. [в Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) инструкции по решению распространенных проблем.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="b4bd6-142">Планирование развертывания Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-143">Прежде чем развернуть Office 365 CDN для Office 365 клиента, следует учитывать следующие факторы в процессе планирования.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="b4bd6-144">Определите, какие статические активы необходимо установить в CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="b4bd6-145">Определите, где нужно хранить свои активы</span><span class="sxs-lookup"><span data-stu-id="b4bd6-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="b4bd6-146">Выберите, должно ли каждое происхождение быть общедоступным или закрытым.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="b4bd6-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="b4bd6-148">Определите, какие статические активы необходимо установить в CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="b4bd6-149">В общем, CDNs наиболее эффективны для размещения статических активов _или_ активов, которые не очень часто изменяются.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="b4bd6-150">Хорошим правилом является определение файлов, которые соответствуют некоторым или всем этим условиям:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="b4bd6-151">Статические файлы, встроенные в страницу (например, сценарии и изображения), которые могут иметь существенное инкрементное влияние на время загрузки страницы.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="b4bd6-152">Большие файлы, такие как исполняемые и файлы установки</span><span class="sxs-lookup"><span data-stu-id="b4bd6-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="b4bd6-153">Библиотеки ресурсов, поддерживают клиентский код</span><span class="sxs-lookup"><span data-stu-id="b4bd6-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="b4bd6-154">Например, небольшие файлы, которые неоднократно запрашиваются, например изображения сайтов и сценарии, могут значительно повысить производительность отрисовки сайта и постепенно снизить нагрузку на сайты SharePoint Online при добавлении их в CDN происхождения.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="b4bd6-155">Более крупные файлы, такие как исполняемые установки, могут быть загружены из CDN, что оказывает положительное влияние на производительность и последующее снижение нагрузки на сайте SharePoint Online, даже если к ним не доступны так часто.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="b4bd6-156">Повышение производительности на основе каждого файла зависит от многих факторов, включая близость клиента к ближайшей CDN конечной точке, временные условия в локальной сети и т. д.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="b4bd6-157">Многие статические файлы довольно малы и могут быть загружены из Office 365 менее чем за секунду.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="b4bd6-158">Однако веб-страница может содержать множество встроенных файлов совокупным временем загрузки в несколько секунд.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="b4bd6-159">Обслуживание этих файлов из CDN может значительно сократить общее время загрузки страницы.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="b4bd6-160">В примере см. CDN [производительность.](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="b4bd6-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="b4bd6-162">Определите, где нужно хранить свои активы</span><span class="sxs-lookup"><span data-stu-id="b4bd6-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="b4bd6-163">The CDN извлекает ваши активы из расположения, называемого _происхождением._</span><span class="sxs-lookup"><span data-stu-id="b4bd6-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="b4bd6-164">Происхождение может быть SharePoint, библиотекой документов или папкой, доступной по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="b4bd6-165">У вас есть большая гибкость при указании истоков для организации.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="b4bd6-166">Например, можно указать несколько источников или одно происхождение, в которых необходимо поместить все CDN активы.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="b4bd6-167">Вы можете выбрать общедоступные или частные истоки для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="b4bd6-168">Большинство организаций будут выбирать для реализации сочетания этих двух.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="b4bd6-169">Вы можете создать новый контейнер для истоков, таких как папки или библиотеки документов, и добавить файлы, которые необходимо сделать доступными из CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="b4bd6-170">Это хороший подход, если у вас есть определенный набор активов, которые вы хотите быть доступны из CDN и хотите ограничить набор CDN только те файлы в контейнере.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="b4bd6-171">Вы также можете настроить существующую коллекцию сайтов, сайт, библиотеку или папку в качестве источника, что сделает все подходящие активы в контейнере доступными из CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="b4bd6-172">Перед добавлением существующего контейнера в качестве источника важно убедиться, что вы осведомлены о его содержимом и разрешениях, чтобы не случайно подвергать ресурсы анонимному доступу или неавторизованным пользователям.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="b4bd6-173">Вы можете _CDN политики,_ чтобы исключить контент из CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="b4bd6-174">CDN политики исключают активы государственного или частного происхождения  по атрибутам, таким как тип файла и классификация _сайтов,_ и применяются для всех истоков cdnType (частных или общедоступных), которые указаны в политике.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="b4bd6-175">Например, если вы добавляете частное происхождение, состоящее из сайта с несколькими подмитами, можно определить политику, исключаемую сайты, помеченные как Конфиденциальные, чтобы содержимое сайтов с применяемой классификацией не было подается из CDN. </span><span class="sxs-lookup"><span data-stu-id="b4bd6-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="b4bd6-176">Политика будет применяться к контенту из _всех_ частных истоков, добавленных в CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>

<span data-ttu-id="b4bd6-177">Помните, что чем больше количество истоков, тем большее влияние на время обработки запросов CDN службы.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="b4bd6-178">Рекомендуем максимально ограничить количество истоков.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-178">We recommend that you limit the number of origins as much as possible.</span></span>

<span data-ttu-id="b4bd6-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="b4bd6-180">Выберите, должно ли каждое происхождение быть общедоступным или закрытым.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="b4bd6-181">При определении источника указывается, следует ли сделать его общедоступным _или_ _закрытым._</span><span class="sxs-lookup"><span data-stu-id="b4bd6-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="b4bd6-182">Доступ к CDN в общедоступных источниках анонимный, а CDN содержимого частного происхождения обеспечивается динамически созданными маркерами для большей безопасности.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="b4bd6-183">Независимо от того, какой вариант вы выбрали, Корпорация Майкрософт делает все тяжелые для вас, когда дело доходит до администрирования CDN себя.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="b4bd6-184">Кроме того, вы можете изменить свое решение позже, после того как вы настроите CDN и идентифицировали свои истоки.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="b4bd6-185">Как общедоступные, так и частные параметры обеспечивают аналогичные преимущества производительности, но каждый из них имеет уникальные атрибуты и преимущества.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="b4bd6-186">**Общедоступные** истоки Office 365 CDN доступны анонимно, а к хост-активам может получить доступ любой, у кого есть URL-адрес актива.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="b4bd6-187">Так как доступ к содержимому в общедоступных источниках является анонимным, следует использовать их только для кэширования неконфиденциального общего содержимого, например файлов JavaScript, скриптов, значков и изображений.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as JavaScript files, scripts, icons and images.</span></span>

<span data-ttu-id="b4bd6-188">**Частные** истоки в Office 365 CDN предоставляют частный доступ к пользовательскому контенту, например SharePoint онлайн-библиотекам документов, сайтам и фирменным изображениям.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="b4bd6-189">Доступ к контенту частного происхождения обеспечивается динамически созданными маркерами, поэтому доступ к нему могут получить только пользователи с разрешениями на исходную библиотеку документов или расположение хранилища.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="b4bd6-190">Частные истоки в Office 365 CDN можно использовать только для контента SharePoint Online, а получить доступ к активам частного происхождения можно только через перенаправление с SharePoint Online клиента.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="b4bd6-191">Подробнее о том, как CDN к активам частного происхождения, читайте в публикации "Использование активов [в частном происхождении".](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="b4bd6-192">Атрибуты и преимущества размещения активов в общедоступных источниках</span><span class="sxs-lookup"><span data-stu-id="b4bd6-192">Attributes and advantages of hosting assets in public origins</span></span>

+ <span data-ttu-id="b4bd6-193">Ресурсы, предоставляемые из общедоступного источника, доступны всем анонимно.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="b4bd6-194">Никогда не следует разместить ресурсы, содержащие сведения о пользователях или которые считаются конфиденциальными для организации в публичном происхождении.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

+ <span data-ttu-id="b4bd6-195">Если удалить ресурс из общедоступного источника, он может оставаться доступным в кэше до 30 дней. Однако ссылки на ресурс в сети CDN станут недействительными в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>

+ <span data-ttu-id="b4bd6-196">При размещении таблиц стилей (CSS-файлов) в общедоступном источнике можно использовать в коде относительные пути и URI.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="b4bd6-197">Это означает, что вы можете ссылаться на расположение фоновых изображений и других объектов относительно расположения ресурса, который вызывает его.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>

+ <span data-ttu-id="b4bd6-198">Хотя вы можете создать URL-адрес общего происхождения, следует действовать с осторожностью и убедиться, что вы используете свойство контекста страницы и следуйте указаниям для этого.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-198">While you can construct a public origin's URL, you should proceed with caution and ensure you utilize the page context property and follow the guidance for doing so.</span></span> <span data-ttu-id="b4bd6-199">Это связано с тем, что если сеть CDN станет недоступна, то URL-адрес не будет автоматически указывать на вашу организацию в SharePoint Online, что может привести к неработоспособности ссылок и другим ошибкам.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span> <span data-ttu-id="b4bd6-200">Url-адрес также подлежит изменению, поэтому он не должен быть просто жестко закодироваться к текущему значению.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-200">The URL is also subject to change which is why it should not just be hard coded to its current value.</span></span>

+ <span data-ttu-id="b4bd6-201">Типы файлов по умолчанию, включенные для общедоступных истоков, относятся :css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff и .woff2.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-201">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="b4bd6-202">Можно указать дополнительные типы файлов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-202">You can specify additional file types.</span></span>

+ <span data-ttu-id="b4bd6-203">Можно настроить политику, чтобы исключить активы, которые были определены в классификациях сайтов, которые указаны.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-203">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="b4bd6-204">Например, вы можете исключать все ресурсы, отмеченные как "конфиденциальные" или "с ограниченным доступом", даже если они относятся к разрешенным типам файлов и находятся в общедоступном источнике.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-204">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="b4bd6-205">Атрибуты и преимущества размещения активов в частном происхождении</span><span class="sxs-lookup"><span data-stu-id="b4bd6-205">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="b4bd6-206">Частные истоки можно использовать только для SharePoint интернет-ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-206">Private origins can only be used for SharePoint Online assets.</span></span>

+ <span data-ttu-id="b4bd6-207">Пользователи могут получить доступ к активам частного происхождения только в том случае, если у них есть разрешения на доступ к контейнеру.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-207">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="b4bd6-208">Анонимный доступ к таким ресурсам запрещен.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-208">Anonymous access to these assets is prevented.</span></span>

+ <span data-ttu-id="b4bd6-209">Активы частного происхождения должны быть переданы из клиента SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-209">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="b4bd6-210">Прямой доступ к частным CDN не работает.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-210">Direct access to private CDN assets does not work.</span></span>

+ <span data-ttu-id="b4bd6-211">Если вы удалите актив из частного происхождения, актив может оставаться доступным в течение часа из кэша; однако в течение 15 минут после удаления CDN будут признаны недействительными ссылки на актив в CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-211">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>

+ <span data-ttu-id="b4bd6-212">По умолчанию для частных источников включены типы файлов GIF, ICO, JPEG, JPG, JS и PNG.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-212">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="b4bd6-213">Можно указать дополнительные типы файлов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-213">You can specify additional file types.</span></span>

+ <span data-ttu-id="b4bd6-214">Как и с общедоступными истоками, можно настроить политику, чтобы исключить активы, которые были определены классификациями сайтов, которые вы указываете, даже если вы используете поддиальды, чтобы включить все активы в папку или библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-214">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="b4bd6-215">Дополнительные сведения об использовании концепций Office 365 CDN, общих CDN и других cdNs Майкрософт, которые можно использовать с клиентом Office 365, см. в статью [Content Delivery Networks.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-215">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="b4bd6-216">Происхождение CDN по умолчанию</span><span class="sxs-lookup"><span data-stu-id="b4bd6-216">Default CDN origins</span></span>

<span data-ttu-id="b4bd6-217">Если не указать обратное, Office 365 при внии Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-217">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="b4bd6-218">Если изначально вы решите не добавлять их, вы можете добавить эти истоки после завершения установки.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-218">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="b4bd6-219">Если вы не понимаете последствия пропуска установки истоков по умолчанию и не имеете для этого конкретной причины, вы должны разрешить их создавать, когда вы включаете CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-219">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>

<span data-ttu-id="b4bd6-220">По умолчанию CDN истоки:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-220">Default private CDN origins:</span></span>

+ <span data-ttu-id="b4bd6-221">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="b4bd6-221">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="b4bd6-222">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="b4bd6-222">\*/siteassets</span></span>

<span data-ttu-id="b4bd6-223">Общедоступные CDN по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-223">Default public CDN origins:</span></span>

+ <span data-ttu-id="b4bd6-224">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="b4bd6-224">\*/masterpage</span></span>
+ <span data-ttu-id="b4bd6-225">\*/библиотека стилей</span><span class="sxs-lookup"><span data-stu-id="b4bd6-225">\*/style library</span></span>
+ <span data-ttu-id="b4bd6-226">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="b4bd6-226">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="b4bd6-227">_clientsideassets_ — это общедоступный источник по умолчанию, который был добавлен Office 365 CDN службе в декабре 2017 г.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-227">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="b4bd6-228">Это происхождение должно присутствовать для SharePoint Framework решений в CDN для работы.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-228">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="b4bd6-229">Если вы включили Office 365 CDN до декабря 2017 г. или пропустили установку истоков по умолчанию при включении CDN, можно вручную добавить это происхождение.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-229">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="b4bd6-230">Дополнительные сведения см. [в странице Моя клиентская веб-часть или SharePoint Framework решение не работает.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-230">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="b4bd6-231"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-231"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="b4bd6-232">Настройка и настройка Office 365 CDN с помощью SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="b4bd6-232">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="b4bd6-233">Процедуры в этом разделе требуют, чтобы вы использовали SharePoint Online Management Shell для подключения к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-233">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="b4bd6-234">Инструкции см. в статье [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-234">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

<span data-ttu-id="b4bd6-235">Выполните эти действия, чтобы настроить CDN для SharePoint Online с помощью SharePoint online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-235">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="b4bd6-236">Щелкните, чтобы развернуть</span><span class="sxs-lookup"><span data-stu-id="b4bd6-236">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="b4bd6-237">Включить организацию для использования Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-237">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-238">Прежде чем вносить изменения в параметры CDN клиента, необходимо получить текущее состояние конфигурации частных CDN в Office 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-238">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="b4bd6-239">Подключение клиенту с помощью SharePoint Online Management Shell:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-239">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="b4bd6-240">Теперь используйте **комлет Get-SPOTenantCdnEnabled** для получения параметров CDN состояния у клиента:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-240">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="b4bd6-241">Состояние CDN для указанного CdnType выводит на экран.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-241">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="b4bd6-242">Используйте **комлет Set-SPOTenantCdnEnabled,** чтобы позволить организации использовать Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-242">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="b4bd6-243">Вы можете включить организацию для использования общедоступных истоков, частных и одновременно обоих.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-243">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="b4bd6-244">Вы также можете настроить CDN, чтобы пропустить установку истоков по умолчанию при его впусте.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-244">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="b4bd6-245">Вы всегда можете добавить эти истоки позже, как описано в этой теме.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-245">You can always add these origins later as described in this topic.</span></span>

<span data-ttu-id="b4bd6-246">В Windows PowerShell для SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-246">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="b4bd6-247">Например, чтобы позволить организации использовать общедоступные и частные истоки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-247">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="b4bd6-248">Чтобы позволить организации использовать как общедоступные, так и частные истоки, но пропустить настройку истоков по умолчанию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-248">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="b4bd6-249">Сведения [об источниках,](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) которые по умолчанию CDN по умолчанию, если включить Office 365 CDN, и потенциальные последствия пропуска установки истоков по умолчанию см. в CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-249">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="b4bd6-250">Чтобы позволить организации использовать общедоступные истоки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-250">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="b4bd6-251">Чтобы позволить организации использовать частные истоки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-251">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="b4bd6-252">Дополнительные сведения об этом комлете см. в этой ленте [Set-SPOTenantCdnEnabled.](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-252">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

<span data-ttu-id="b4bd6-253"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-253"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="b4bd6-254">Измените список типов файлов, чтобы включить их в Office 365 CDN (необязательный)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-254">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b4bd6-255">При определении типов файлов с помощью комлета **Set-SPOTenantCdnPolicy** переопределяется определенный список.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-255">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b4bd6-256">Если вы хотите добавить в список дополнительные типы файлов, сначала используйте этот список, чтобы узнать, какие типы файлов уже разрешены, и включите их в список вместе с новыми.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-256">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>

<span data-ttu-id="b4bd6-257">Чтобы определить типы статических файлов, которые могут быть организованы общедоступными и частными истоками в CDN, используйте для этого код **set-SPOTenantCdnPolicy.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-257">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="b4bd6-258">По умолчанию разрешены общие типы активов, например .css, .gif, .jpg и .js.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-258">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="b4bd6-259">В Windows PowerShell для SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-259">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="b4bd6-260">Например, чтобы включить CDN для хозяйского и .png файлов, необходимо ввести команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-260">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="b4bd6-261">Чтобы узнать, какие типы файлов в настоящее время разрешены CDN, используйте **cmdlet Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-261">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b4bd6-262">Дополнительные сведения об этих cmdlets см. в [set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) и [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-262">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="b4bd6-263"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-263"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="b4bd6-264">Измените список классификаций сайтов, которые необходимо исключить из Office 365 CDN (необязательный)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-264">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b4bd6-265">При исключении классификации сайтов с помощью комлета **Set-SPOTenantCdnPolicy** переопределяется определенный список.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-265">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b4bd6-266">Если вы хотите исключить дополнительные классификации сайтов, сначала используйте cmdlet, чтобы узнать, какие классификации уже исключены, а затем добавить их вместе с новыми.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-266">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="b4bd6-267">Чтобы исключить классификации сайтов, которые не должны быть доступны в сети CDN, используйте командлет **Set-SPOTenantCdnPolicy**.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-267">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="b4bd6-268">По умолчанию не исключаются никакие классификации сайтов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-268">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="b4bd6-269">В Windows PowerShell для SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-269">In Windows PowerShell for SharePoint Online:</span></span>

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="b4bd6-270">Чтобы узнать, какие классификации сайтов в настоящее время ограничены, используйте см. в **рубриках Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-270">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b4bd6-271">Свойства, которые будут _возвращены: IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ и _ExcludeIfNoScriptDisabled._</span><span class="sxs-lookup"><span data-stu-id="b4bd6-271">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="b4bd6-272">Свойство _IncludeFileExtensions_ содержит список расширений файлов, которые будут подаваться из CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-272">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="b4bd6-273">Расширения файлов по умолчанию отличаются между общедоступными и закрытыми.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-273">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="b4bd6-274">Свойство _ExcludeRestrictedSiteClassifications_ содержит классификации сайтов, которые необходимо исключить из CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-274">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="b4bd6-275">Например, можно исключить сайты, помеченные как **Конфиденциальные,** чтобы содержимое сайтов с применяемой классификацией не было подается из CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-275">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="b4bd6-276">Свойство _ExcludeIfNoScriptDisabled_ исключает контент из CDN на основе параметров атрибута _NoScript_ на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-276">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="b4bd6-277">По умолчанию для _атрибута NoScript_ устанавливается значение **Включено** для _современных_ сайтов и **отключено для** _классических_ сайтов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-277">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="b4bd6-278">Это зависит от параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-278">This depends on your tenant settings.</span></span>

<span data-ttu-id="b4bd6-279">Дополнительные сведения об этих cmdlets см. в [set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) и [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-279">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) and [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).</span></span>

<span data-ttu-id="b4bd6-280"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-280"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="b4bd6-281">Добавление источника для ваших активов</span><span class="sxs-lookup"><span data-stu-id="b4bd6-281">Add an origin for your assets</span></span>

<span data-ttu-id="b4bd6-282">Чтобы определить происхождение, используйте кодлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-282">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="b4bd6-283">Вы можете определить несколько источников.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-283">You can define multiple origins.</span></span> <span data-ttu-id="b4bd6-284">Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-284">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4bd6-285">Никогда не следует разместить ресурсы, содержащие сведения о пользователях или которые считаются конфиденциальными для организации в публичном происхождении.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-285">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="b4bd6-286">Значение пути _—_ это относительный путь к библиотеке или папке, которая содержит активы.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-286">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="b4bd6-287">Помимо относительных путей, можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-287">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="b4bd6-288">Origins поддерживает подкарды, предварительно заранее заранее примыкает к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-288">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="b4bd6-289">Это позволяет создавать истоки, охватывающие несколько сайтов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-289">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="b4bd6-290">Например, чтобы включить все активы в папку masterpages для всех сайтов как общедоступный источник в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-290">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="b4bd6-291">Модификатор под диктовки \* может использоваться только в начале пути и будет соответствовать всем сегментам URL-адресов по **/** указанному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-291">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="b4bd6-292">Путь может указать на библиотеку документов, папку или сайт.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-292">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="b4bd6-293">Например, путь _\*/site1 будет_ соответствовать всем библиотекам документов на сайте.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-293">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="b4bd6-294">Можно добавить происхождение с определенным относительным путем.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-294">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="b4bd6-295">Невозможно добавить начало с помощью полного пути.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-295">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="b4bd6-296">В этом примере добавляется частное происхождение библиотеки siteassets на определенном сайте:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-296">This example adds a private origin of the siteassets library on a specific site:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b4bd6-297">В этом примере добавляется частное происхождение _папки1_ в библиотеке ресурсов сайтов коллекции сайтов:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-297">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="b4bd6-298">Если на пути есть пробел, можно либо окружить путь двойными кавычками, либо заменить пространство url-адресом, кодировка которого составляет %20.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-298">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="b4bd6-299">В следующих примерах добавлено частное происхождение папки _1_ в библиотеке ресурсов сайтов коллекции сайтов:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-299">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="b4bd6-300">Дополнительные сведения об этой команде и ее синтаксис см. в [обзоре Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-300">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

> [!NOTE]
> <span data-ttu-id="b4bd6-301">В частных источниках для доступа к активам из источника должна быть опубликована основная версия, прежде чем к ним можно будет получить доступ CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-301">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>

<span data-ttu-id="b4bd6-302">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-302">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b4bd6-303">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-303">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b4bd6-304"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-304"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="b4bd6-305">Пример: Настройка общедоступных страниц для ваших страниц и библиотеки стилей для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4bd6-305">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="b4bd6-306">Как правило, эти истоки устанавливаются для вас по умолчанию, когда вы включаете Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-306">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="b4bd6-307">Однако, если вы хотите включить их вручную, выполните эти действия.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-307">However, if you want to enable them manually, follow these steps.</span></span>

+ <span data-ttu-id="b4bd6-308">Чтобы определить библиотеку стилей как публичное происхождение, используйте смедлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="b4bd6-309">Для определения магистральных страниц как общедоступных страниц используйте смедлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-309">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="b4bd6-310">Дополнительные сведения об этой команде и ее синтаксис см. в [обзоре Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-310">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b4bd6-311">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-311">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b4bd6-312">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-312">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b4bd6-313"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-313"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="b4bd6-314">Пример: Настройка частного источника для активов сайта, страниц сайта и публикации изображений для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4bd6-314">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="b4bd6-315">Чтобы определить папку активов сайта как частное происхождение, используйте смлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="b4bd6-316">Чтобы определить папку страниц сайта как частное происхождение, используйте кодлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="b4bd6-317">Чтобы определить папку изображений публикации как частное происхождение, используйте кодлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-317">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="b4bd6-318">Дополнительные сведения об этой команде и ее синтаксис см. в [обзоре Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-318">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b4bd6-319">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-319">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b4bd6-320">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-320">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b4bd6-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-321"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="b4bd6-322">Пример: Настройка частного происхождения для коллекции сайтов для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4bd6-322">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="b4bd6-323">Чтобы определить коллекцию сайтов как частное происхождение, используйте смлет **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-323">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="b4bd6-324">Пример:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-324">For example:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b4bd6-325">Дополнительные сведения об этой команде и ее синтаксис см. в [обзоре Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-325">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b4bd6-326">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-326">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b4bd6-327">Вы можете  увидеть ожидаемое сообщение Конфигурация, которое ожидается по мере подключения клиента SharePoint Online к CDN службе.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-327">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="b4bd6-328">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-328">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b4bd6-329"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-329"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="b4bd6-330">Управление Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-330">Manage the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-331">После настройки CDN можно внести изменения в конфигурацию при обновлении контента или при изменении потребностей, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-331">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>

<span data-ttu-id="b4bd6-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-332"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="b4bd6-333">Добавление, обновление или удаление активов из Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-333">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-334">После завершения действий по настройке можно добавлять новые активы и обновлять или удалять существующие активы, когда захотите.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-334">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="b4bd6-335">Просто внося изменения в ресурсы в папке или SharePoint библиотеке, которую вы идентифицировали как источник.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-335">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b4bd6-336">Если вы добавим новый актив, он будет доступен CDN немедленно.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-336">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="b4bd6-337">Однако при обновлении актива для распространения и распространения новой копии в CDN займет до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-337">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>

<span data-ttu-id="b4bd6-338">Если вам нужно получить расположение источника, можно использовать **комлет Get-SPOTenantCdnOrigins.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-338">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="b4bd6-339">Сведения об использовании этого комлета см. в сайте [Get-SPOTenantCdnOrigins.](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-339">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).</span></span>

<span data-ttu-id="b4bd6-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-340"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="b4bd6-341">Удаление источника из Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-341">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-342">Можно удалить доступ к папке или библиотеке SharePoint, которую вы идентифицировали как источник.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-342">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b4bd6-343">Для этого используйте комлет **Remove-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-343">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="b4bd6-344">Сведения об использовании этого cmdlet см. в см. в этой ленте [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-344">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).</span></span>

<span data-ttu-id="b4bd6-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-345"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="b4bd6-346">Изменение источника в Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-346">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-347">Вы не можете изменить созданное происхождение.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-347">You cannot modify an origin you've created.</span></span> <span data-ttu-id="b4bd6-348">Вместо этого удалите начало и добавьте новый.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-348">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="b4bd6-349">Дополнительные сведения [см.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) в статью Удаление источника из Office 365 CDN и добавление источника [для ваших активов.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-349">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="b4bd6-350"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-350"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="b4bd6-351">Отключить Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-351">Disable the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-352">Чтобы отключить CDN организации, используйте комлет **Set-SPOTenantCdnEnabled.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-352">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="b4bd6-353">Если для CDN включено как государственное, так и частное происхождение, необходимо выполнить его дважды, чем показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-353">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>

<span data-ttu-id="b4bd6-354">Чтобы отключить использование общедоступных истоков в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-354">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="b4bd6-355">Чтобы отключить использование личных истоков в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-355">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="b4bd6-356">Дополнительные сведения об этом комлете см. в этой ленте [Set-SPOTenantCdnEnabled.](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-356">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).</span></span>

</details>

<span data-ttu-id="b4bd6-357"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-357"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="b4bd6-358">Настройка и настройка Office 365 CDN с помощью PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="b4bd6-358">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="b4bd6-359">Процедуры в этом разделе требуют, чтобы вы использовали PnP PowerShell для подключения к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-359">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="b4bd6-360">Инструкции см. в [инструкции "Начало работы с PnP PowerShell".](https://github.com/SharePoint/PnP-PowerShell#getting-started)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-360">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="b4bd6-361">Выполните эти действия для настройки и настройки CDN для хозяйского SharePoint Online с помощью PnP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-361">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="b4bd6-362">Щелкните, чтобы развернуть</span><span class="sxs-lookup"><span data-stu-id="b4bd6-362">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="b4bd6-363">Включить организацию для использования Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-363">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-364">Прежде чем вносить изменения в параметры CDN клиента, необходимо получить текущее состояние конфигурации частных CDN в Office 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-364">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="b4bd6-365">Подключение клиенту с помощью PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-365">Connect to your tenant using PnP PowerShell:</span></span>

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="b4bd6-366">Теперь используйте **комлет Get-PnPTenantCdnEnabled** для получения параметров CDN состояния у клиента:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-366">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="b4bd6-367">Состояние CDN для указанного CdnType выводит на экран.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-367">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="b4bd6-368">Используйте **комлет Set-PnPTenantCdnEnabled,** чтобы позволить организации использовать Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-368">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="b4bd6-369">Вы можете включить организацию для использования общедоступных и частных истоков одновременно.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-369">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="b4bd6-370">Вы также можете настроить CDN, чтобы пропустить установку истоков по умолчанию при его впусте.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-370">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="b4bd6-371">Вы всегда можете добавить эти истоки позже, как описано в этой теме.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-371">You can always add these origins later as described in this topic.</span></span>

<span data-ttu-id="b4bd6-372">В PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-372">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="b4bd6-373">Например, чтобы позволить организации использовать общедоступные и частные истоки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-373">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="b4bd6-374">Чтобы позволить организации использовать как общедоступные, так и частные истоки, но пропустить настройку истоков по умолчанию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-374">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="b4bd6-375">Сведения [об источниках,](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) которые по умолчанию CDN по умолчанию, если включить Office 365 CDN, и потенциальные последствия пропуска установки истоков по умолчанию см. в CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-375">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="b4bd6-376">Чтобы позволить организации использовать общедоступные истоки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-376">To enable your organization to use public origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="b4bd6-377">Чтобы позволить организации использовать частные истоки, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-377">To enable your organization to use private origins, type the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="b4bd6-378">Дополнительные сведения об этом комлете см. в дополнительных сведениях [set-PnPTenantCdnEnabled.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-378">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="b4bd6-379"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-379"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="b4bd6-380">Измените список типов файлов, чтобы включить их в Office 365 CDN (необязательный)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-380">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b4bd6-381">При определении типов файлов с помощью комлета **Set-PnPTenantCdnPolicy** переопределяется определенный список.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-381">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b4bd6-382">Если вы хотите добавить в список дополнительные типы файлов, сначала используйте этот список, чтобы узнать, какие типы файлов уже разрешены, и включите их в список вместе с новыми.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-382">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>

<span data-ttu-id="b4bd6-383">Для определения типов статических файлов, которые могут быть организованы общедоступными и частными истоками в CDN, используйте коммюлет **Set-PnPTenantCdnPolicy.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-383">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="b4bd6-384">По умолчанию разрешены общие типы активов, например .css, .gif, .jpg и .js.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-384">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="b4bd6-385">В PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-385">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="b4bd6-386">Например, чтобы включить CDN для хозяйского и .png файлов, необходимо ввести команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-386">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="b4bd6-387">Чтобы узнать, какие типы файлов в настоящее время разрешены CDN, используйте **cmdlet Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-387">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b4bd6-388">Дополнительные сведения об этих cmdlets см. в [set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) и [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-388">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="b4bd6-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-389"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="b4bd6-390">Измените список классификаций сайтов, которые необходимо исключить из Office 365 CDN (необязательный)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-390">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="b4bd6-391">При исключении классификаций сайтов с помощью комлета **Set-PnPTenantCdnPolicy** переопределяется определенный список.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-391">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="b4bd6-392">Если вы хотите исключить дополнительные классификации сайтов, сначала используйте cmdlet, чтобы узнать, какие классификации уже исключены, а затем добавить их вместе с новыми.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-392">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="b4bd6-393">Используйте **кодлет Set-PnPTenantCdnPolicy,** чтобы исключить классификации сайтов, которые вы не хотите CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-393">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="b4bd6-394">По умолчанию не исключаются никакие классификации сайтов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-394">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="b4bd6-395">В PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-395">In PnP PowerShell:</span></span>

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="b4bd6-396">Чтобы узнать, какие классификации сайтов в настоящее время ограничены, используйте **кодлет Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-396">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="b4bd6-397">Свойства, которые будут _возвращены: IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ и _ExcludeIfNoScriptDisabled._</span><span class="sxs-lookup"><span data-stu-id="b4bd6-397">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="b4bd6-398">Свойство _IncludeFileExtensions_ содержит список расширений файлов, которые будут подаваться из CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-398">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="b4bd6-399">Расширения файлов по умолчанию отличаются между общедоступными и закрытыми.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-399">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="b4bd6-400">Свойство _ExcludeRestrictedSiteClassifications_ содержит классификации сайтов, которые необходимо исключить из CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-400">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="b4bd6-401">Например, можно исключить сайты, помеченные как **Конфиденциальные,** чтобы содержимое сайтов с применяемой классификацией не было подается из CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-401">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="b4bd6-402">Свойство _ExcludeIfNoScriptDisabled_ исключает контент из CDN на основе параметров атрибута _NoScript_ на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-402">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="b4bd6-403">По умолчанию для _атрибута NoScript_ устанавливается значение **Включено** для _современных_ сайтов и **отключено для** _классических_ сайтов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-403">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="b4bd6-404">Это зависит от параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-404">This depends on your tenant settings.</span></span>

<span data-ttu-id="b4bd6-405">Дополнительные сведения об этих cmdlets см. в [set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) и [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-405">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="b4bd6-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-406"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="b4bd6-407">Добавление источника для ваших активов</span><span class="sxs-lookup"><span data-stu-id="b4bd6-407">Add an origin for your assets</span></span>

<span data-ttu-id="b4bd6-408">Чтобы определить происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-408">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="b4bd6-409">Вы можете определить несколько источников.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-409">You can define multiple origins.</span></span> <span data-ttu-id="b4bd6-410">Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-410">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4bd6-411">Никогда не следует разместить ресурсы, содержащие сведения о пользователях или которые считаются конфиденциальными для организации в публичном происхождении.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-411">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="b4bd6-412">Значение пути _—_ это относительный путь к библиотеке или папке, которая содержит активы.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-412">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="b4bd6-413">Помимо относительных путей, можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-413">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="b4bd6-414">Origins поддерживает подкарды, предварительно заранее заранее примыкает к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-414">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="b4bd6-415">Это позволяет создавать истоки, охватывающие несколько сайтов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-415">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="b4bd6-416">Например, чтобы включить все активы в папку masterpages для всех сайтов как общедоступный источник в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-416">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="b4bd6-417">Модификатор под диктовки \* может использоваться только в начале пути и будет соответствовать всем сегментам URL-адресов по **/** указанному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-417">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="b4bd6-418">Путь может указать на библиотеку документов, папку или сайт.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-418">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="b4bd6-419">Например, путь _\*/site1 будет_ соответствовать всем библиотекам документов на сайте.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-419">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="b4bd6-420">Можно добавить происхождение с определенным относительным путем.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-420">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="b4bd6-421">Невозможно добавить начало с помощью полного пути.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-421">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="b4bd6-422">В этом примере добавляется частное происхождение библиотеки ресурсов сайта на определенном сайте:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-422">This example adds a private origin of the site assets library on a specific site:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b4bd6-423">В этом примере добавляется частное происхождение _папки1_ в библиотеке ресурсов сайтов коллекции сайтов:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-423">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="b4bd6-424">Если на пути есть пробел, можно либо окружить путь двойными кавычками, либо заменить пространство url-адресом, кодировка которого составляет %20.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-424">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="b4bd6-425">В следующих примерах добавлено частное происхождение папки _1_ в библиотеке ресурсов сайтов коллекции сайтов:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-425">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="b4bd6-426">Дополнительные сведения об этой команде и ее синтаксис см. в [добавлении-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-426">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="b4bd6-427">В частных источниках для доступа к активам из источника должна быть опубликована основная версия, прежде чем к ним можно будет получить доступ CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-427">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>

<span data-ttu-id="b4bd6-428">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-428">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b4bd6-429">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-429">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b4bd6-430"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-430"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="b4bd6-431">Пример: Настройка общедоступных страниц для ваших страниц и библиотеки стилей для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4bd6-431">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="b4bd6-432">Как правило, эти истоки устанавливаются для вас по умолчанию, когда вы включаете Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-432">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="b4bd6-433">Однако, если вы хотите включить их вручную, выполните эти действия.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-433">However, if you want to enable them manually, follow these steps.</span></span>

+ <span data-ttu-id="b4bd6-434">Чтобы определить библиотеку стилей как общедоступный, используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="b4bd6-435">Для определения магистральных страниц как общедоступных страниц используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-435">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="b4bd6-436">Дополнительные сведения об этой команде и ее синтаксис см. в [добавлении-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-436">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b4bd6-437">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-437">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b4bd6-438">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-438">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b4bd6-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-439"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="b4bd6-440">Пример: Настройка частного источника для активов сайта, страниц сайта и публикации изображений для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4bd6-440">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="b4bd6-441">Чтобы определить папку активов сайта как частное происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="b4bd6-442">Чтобы определить папку страниц сайта как частное происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="b4bd6-443">Чтобы определить папку изображений публикации как частное происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-443">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="b4bd6-444">Дополнительные сведения об этой команде и ее синтаксис см. в [добавлении-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-444">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b4bd6-445">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-445">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b4bd6-446">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-446">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b4bd6-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-447"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="b4bd6-448">Пример: Настройка частного происхождения для коллекции сайтов для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4bd6-448">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="b4bd6-449">Чтобы определить коллекцию сайтов как частное происхождение, используйте кодлет **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-449">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="b4bd6-450">Пример:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-450">For example:</span></span>

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="b4bd6-451">Дополнительные сведения об этой команде и ее синтаксис см. в [добавлении-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-451">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b4bd6-452">После запуска команды система синхронизирует конфигурацию через центр обработки данных.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-452">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="b4bd6-453">Вы можете  увидеть ожидаемое сообщение Конфигурация, которое ожидается по мере подключения клиента SharePoint Online к CDN службе.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-453">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="b4bd6-454">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-454">This can take up to 15 minutes.</span></span>

<span data-ttu-id="b4bd6-455"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-455"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="b4bd6-456">Управление Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-456">Manage the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-457">После настройки CDN можно внести изменения в конфигурацию при обновлении контента или при изменении потребностей, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-457">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>

<span data-ttu-id="b4bd6-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-458"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="b4bd6-459">Добавление, обновление или удаление активов из Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-459">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-460">После завершения действий по настройке можно добавлять новые активы и обновлять или удалять существующие активы, когда захотите.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-460">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="b4bd6-461">Просто внося изменения в ресурсы в папке или SharePoint библиотеке, которую вы идентифицировали как источник.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-461">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b4bd6-462">Если вы добавим новый актив, он будет доступен CDN немедленно.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-462">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="b4bd6-463">Однако при обновлении актива для распространения и распространения новой копии в CDN займет до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-463">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>

<span data-ttu-id="b4bd6-464">Если вам нужно получить расположение источника, можно использовать **комлет Get-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-464">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="b4bd6-465">Сведения об использовании этого комлета см. в [сайте Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-465">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b4bd6-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-466"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="b4bd6-467">Удаление источника из Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-467">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-468">Можно удалить доступ к папке или библиотеке SharePoint, которую вы идентифицировали как источник.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-468">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="b4bd6-469">Для этого используйте комлет **Remove-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-469">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="b4bd6-470">Сведения о том, как использовать этот комлет, см. в этой брошюре [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-470">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="b4bd6-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-471"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="b4bd6-472">Изменение источника в Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-472">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-473">Вы не можете изменить созданное происхождение.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-473">You cannot modify an origin you've created.</span></span> <span data-ttu-id="b4bd6-474">Вместо этого удалите начало и добавьте новый.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-474">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="b4bd6-475">Дополнительные сведения [см.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) в статью Удаление источника из Office 365 CDN и добавление источника [для ваших активов.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-475">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="b4bd6-476"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-476"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="b4bd6-477">Отключить Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-477">Disable the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-478">Чтобы отключить CDN организации, используйте комлет **Set-PnPTenantCdnEnabled.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-478">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="b4bd6-479">Если для CDN включено как государственное, так и частное происхождение, необходимо выполнить его дважды, чем показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-479">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>

<span data-ttu-id="b4bd6-480">Чтобы отключить использование общедоступных истоков в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-480">To disable use of public origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="b4bd6-481">Чтобы отключить использование личных истоков в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-481">To disable use of the private origins in the CDN, enter the following command:</span></span>

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="b4bd6-482">Дополнительные сведения об этом комлете см. в дополнительных сведениях [set-PnPTenantCdnEnabled.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-482">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="b4bd6-483"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-483"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="b4bd6-484">Установка и настройка сети CDN Office 365 с помощью интерфейса командной строки Office 365:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-484">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="b4bd6-485">Процедуры в этом разделе требуют, чтобы вы установили Office 365 [CLI](https://aka.ms/o365cli).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-485">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="b4bd6-486">Далее подключите Office 365 клиента с помощью команды [входа.](https://pnp.github.io/office365-cli/cmd/login/)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-486">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="b4bd6-487">Выполните эти действия, чтобы настроить CDN для хозяйского SharePoint Online с помощью Office 365 CLI.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-487">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="b4bd6-488">Щелкните, чтобы развернуть</span><span class="sxs-lookup"><span data-stu-id="b4bd6-488">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="b4bd6-489">Включить Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-489">Enable the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-490">Вы можете управлять состоянием сети CDN Office 365 в клиенте с помощью команды [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-490">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="b4bd6-491">Чтобы включить в клиенте общедоступную сеть CDN Office 365, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-491">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```cli
spo cdn set --type Public --enabled true
```

<span data-ttu-id="b4bd6-492">Чтобы включить Office 365 SharePoint CDN, выполните:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-492">To enable the Office 365 SharePoint CDN, execute:</span></span>

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="b4bd6-493">Просмотр текущего состояния сети CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b4bd6-493">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-494">Чтобы проверить, включен или отключен определенный тип Office 365 CDN, используйте [команду spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-494">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="b4bd6-495">Чтобы проверить, включена ли общедоступная сеть CDN Office 365, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-495">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="b4bd6-496">Просмотр Office 365 CDN истоков</span><span class="sxs-lookup"><span data-stu-id="b4bd6-496">View the Office 365 CDN origins</span></span>

<span data-ttu-id="b4bd6-497">Чтобы просмотреть список настроенных в данный момент общедоступных источников CDN Office 365, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-497">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```cli
spo cdn origin list --type Public
```

<span data-ttu-id="b4bd6-498">Сведения [об источниках, которые](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) по умолчанию CDN по умолчанию, см. в Office 365 CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-498">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="b4bd6-499">Добавление Office 365 CDN происхождения</span><span class="sxs-lookup"><span data-stu-id="b4bd6-499">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4bd6-500">Ресурсы, которые считаются конфиденциальными для организации, не следует SharePoint библиотеку документов, настроенную как общедоступные.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-500">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="b4bd6-501">Чтобы определить источник CDN, используйте команду [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-501">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="b4bd6-502">Вы можете определить несколько источников.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-502">You can define multiple origins.</span></span> <span data-ttu-id="b4bd6-503">Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-503">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="b4bd6-504">Где `path` находится относительный путь к папке с активами.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-504">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="b4bd6-505">Помимо относительных путей, можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-505">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="b4bd6-506">Чтобы включить все активы в **Галерею основных** страниц всех сайтов как общедоступные, выполните:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-506">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```cli
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="b4bd6-507">Чтобы настроить частный источник для определенного семейства веб-сайтов, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-507">To configure a private origin for a specific site collection, execute:</span></span>

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="b4bd6-508">После добавления источника CDN может понадобиться до 15 минут, чтобы получить файлы через службу CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-508">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="b4bd6-509">Вы можете проверить, включен ли тот или иной источник, с помощью команды [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-509">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="b4bd6-510">Удаление Office 365 CDN происхождения</span><span class="sxs-lookup"><span data-stu-id="b4bd6-510">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="b4bd6-511">Чтобы удалить источник CDN для указанного типа CDN, используйте команду [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-511">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="b4bd6-512">Чтобы удалить общедоступный источник из конфигурации CDN, выполните:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-512">To remove a public origin from the CDN configuration, execute:</span></span>

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="b4bd6-513">Удаление CDN не влияет на файлы, хранимые в любой библиотеке документов, соответствующие этому происхождению.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-513">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="b4bd6-514">Если эти активы ссылались с SharePoint URL-адресом, SharePoint автоматически переключается на исходный URL-адрес, указывающий на библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-514">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="b4bd6-515">Если же ссылки на активы были указаны с CDN url-адресом, то удаление источника перебьет ссылку, и вам потребуется вручную изменить их.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-515">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="b4bd6-516">Изменение Office 365 CDN происхождения</span><span class="sxs-lookup"><span data-stu-id="b4bd6-516">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="b4bd6-517">Изменить имеющийся источник CDN невозможно.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-517">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="b4bd6-518">Вместо этого следует удалить определенный ранее источник CDN с помощью команды `spo cdn origin remove` и добавить новый с помощью команды `spo cdn origin add`.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-518">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="b4bd6-519">Измените типы файлов, чтобы включить их в Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-519">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-520">По умолчанию в CDN включены следующие типы файлов: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff и .woff2_.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-520">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="b4bd6-521">Если требуется включить в сеть CDN дополнительные типы файлов, вы можете изменить конфигурацию CDN с помощью команды [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-521">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="b4bd6-522">При изменении списка типов файлов перезаписывается текущий список.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-522">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="b4bd6-523">Если требуется включить дополнительные типы файлов, сперва используйте команду [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/), чтобы узнать, какие типы файлов настроены в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-523">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="b4bd6-524">Чтобы добавить _тип файла JSON_ в список типов файлов по умолчанию, включенных в общедоступный CDN, выполните:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-524">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="b4bd6-525">Изменение списка классификаций сайтов, которые требуется исключить из сети CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="b4bd6-525">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-526">Чтобы исключить классификации сайтов, которые не должны быть доступны в сети CDN, используйте команду [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-526">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="b4bd6-527">По умолчанию не исключаются никакие классификации сайтов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-527">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="b4bd6-528">При изменении списка исключаемых классификаций сайтов перезаписывается текущий список.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-528">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="b4bd6-529">Если требуется исключить дополнительные классификации сайтов, сперва используйте команду [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/), чтобы узнать, какие классификации настроены в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-529">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="b4bd6-530">Чтобы исключить сайты, классифицируются _как HBI,_ из общедоступных CDN выполните</span><span class="sxs-lookup"><span data-stu-id="b4bd6-530">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="b4bd6-531">Отключить Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-531">Disable the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-532">Чтобы отключить сеть CDN Office 365, используйте команду `spo cdn set`. Пример:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-532">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="b4bd6-533">Использование CDN активов</span><span class="sxs-lookup"><span data-stu-id="b4bd6-533">Using your CDN assets</span></span>

<span data-ttu-id="b4bd6-534">Теперь, когда вы включили CDN и настроенные истоки и политики, можно приступить к использованию CDN ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-534">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="b4bd6-535">В этом разделе вы сможете понять, как использовать URL CDN на страницах SharePoint и контенте, чтобы SharePoint перенаправлял запросы на активы как государственного, так и частного происхождения в CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-535">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="b4bd6-536">Обновление ссылок CDN ресурсов</span><span class="sxs-lookup"><span data-stu-id="b4bd6-536">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="b4bd6-537">Использование ресурсов в общедоступных источниках</span><span class="sxs-lookup"><span data-stu-id="b4bd6-537">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="b4bd6-538">Использование активов в частном происхождении</span><span class="sxs-lookup"><span data-stu-id="b4bd6-538">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="b4bd6-539">Сведения об использовании веб-CDN для размещения клиентских веб-частей см. в разделе Host [your client-side web part from Office 365 CDN (Hello World part 4).](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-539">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="b4bd6-540">Если вы добавим папку _ClientSideAssets_ в частный список CDN истоков, CDN пользовательские веб-части не будут отрисовки. </span><span class="sxs-lookup"><span data-stu-id="b4bd6-540">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="b4bd6-541">Файлы, используемые веб-частями SPFX, могут использовать только общедоступные CDN, а папка ClientSideAssets — это происхождение по умолчанию для общедоступных CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-541">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span>

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="b4bd6-542">Обновление ссылок CDN ресурсов</span><span class="sxs-lookup"><span data-stu-id="b4bd6-542">Updating links to CDN assets</span></span>

<span data-ttu-id="b4bd6-543">Чтобы использовать добавленные в источник ресурсы, просто обновив ссылки на исходный файл с помощью пути к файлу в начале.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-543">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="b4bd6-544">Изменить страницу или контент, содержащий ссылки на активы, добавленные в источник.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-544">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="b4bd6-545">Вы также можете использовать один из нескольких методов глобального поиска и замены ссылок на веб-сайт или коллекцию сайтов, если вы хотите обновить ссылку на данный актив везде, где он появится.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-545">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="b4bd6-546">Для каждой ссылки на актив в источнике замените путь путем к файлу в CDN происхождения.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-546">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="b4bd6-547">Можно использовать относительные пути.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-547">You can use relative paths.</span></span>
+ <span data-ttu-id="b4bd6-548">Сохранение страницы или контента.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-548">Save the page or content.</span></span>

<span data-ttu-id="b4bd6-549">Например, рассмотрим изображение _/site/SiteAssets/images/image.png_, которое вы скопировали в папку библиотеки документов _/site/CDN_origins/public/_.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-549">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="b4bd6-550">Чтобы использовать CDN, замените исходный путь к расположению файла изображений путем к источнику, чтобы сделать новый URL-адрес _/site/CDN_origins/public/image.png_.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-550">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="b4bd6-551">Если вы хотите использовать полный URL-адрес актива вместо относительного пути, сострой ссылку так:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-551">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="b4bd6-552">Как правило, не следует жестко кодировать URL-адреса непосредственно к активам в CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-552">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="b4bd6-553">Однако при необходимости можно вручную создавать URL-адреса для активов в общедоступных источниках.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-553">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="b4bd6-554">Дополнительные сведения см. в [CDN url-адресов hardcoding для общедоступных активов.](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-554">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="b4bd6-555">Чтобы узнать о том, как убедиться в том, что активы обслуживаются из CDN, см. в руб. Как подтвердить, что активы обслуживаются [CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) в устранении неполадок Office 365 CDN [.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-555">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="b4bd6-556">Использование ресурсов в общедоступных источниках</span><span class="sxs-lookup"><span data-stu-id="b4bd6-556">Using assets in public origins</span></span>

<span data-ttu-id="b4bd6-557">Функция **публикации** в SharePoint Online автоматически переписывала URL-адреса активов, хранимых в общедоступных источниках, в их эквиваленты CDN, чтобы активы обслуживались из службы CDN вместо SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-557">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="b4bd6-558">Если ваше происхождение находится на сайте с включенной функцией Публикации, а активы, которые необходимо разгрузить до CDN, находятся в одной из следующих категорий, SharePoint автоматически перезаписывание URL-адресов для активов в источнике при условии, что актив не был исключен политикой CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-558">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="b4bd6-559">Ниже представлен обзор ссылок, которые автоматически заменяет функция публикации в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-559">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="b4bd6-560">URL-адреса IMG-, LINK- и CSS-файлов в HTML-откликах классической страницы публикации.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-560">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="b4bd6-561">Это относится и к изображениям, добавленным авторами в HTML-содержимом страницы.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-561">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="b4bd6-562">URL-адреса изображений в веб-части "Слайд-шоу библиотеки рисунков".</span><span class="sxs-lookup"><span data-stu-id="b4bd6-562">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="b4bd6-563">Поля изображений в результатах работы REST API SPList (RenderListDataAsStream).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-563">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="b4bd6-564">Используйте новое свойство _ImageFieldsToTryRewriteToCdnUrls_ для предоставления разделенного запятой списка полей</span><span class="sxs-lookup"><span data-stu-id="b4bd6-564">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="b4bd6-565">Поддерживает поля гиперссылки и поля PublishingImage</span><span class="sxs-lookup"><span data-stu-id="b4bd6-565">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="b4bd6-566">SharePoint изображений</span><span class="sxs-lookup"><span data-stu-id="b4bd6-566">SharePoint image renditions</span></span>

<span data-ttu-id="b4bd6-567">Следующая схема иллюстрирует рабочий процесс, SharePoint получает запрос на страницу, содержащую активы из общего происхождения.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-567">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="b4bd6-568">![Схема рабочего процесса: Office 365 CDN ресурсов из общего происхождения](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Рабочий процесс: Office 365 CDN ресурсов из общего происхождения")</span><span class="sxs-lookup"><span data-stu-id="b4bd6-568">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="b4bd6-569">Если вы хотите отключить автоматическое переписывание определенных URL-адресов на странице, вы можете проверить страницу и добавить параметр строки **запроса? NoAutoReWrites=true** в конце каждой ссылки, отключаемой.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-569">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="constructing-cdn-urls-for-public-assets"></a><span data-ttu-id="b4bd6-570">Построение CDN URL-адресов для общедоступных активов</span><span class="sxs-lookup"><span data-stu-id="b4bd6-570">Constructing CDN URLs for public assets</span></span>

<span data-ttu-id="b4bd6-571">Если  функция публикации не включена для общего происхождения или актив не является одним из типов ссылок, поддерживаемых функцией автоматического перезаписи службы CDN, можно вручную создать URL-адреса для расположения CDN активов и использовать эти URL-адреса в контенте.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-571">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="b4bd6-572">Нельзя жестко кодировать или CDN URL-адреса с активами частного происхождения, так как необходимый маркер доступа, формирующий последний раздел URL-адреса, создается во время запроса ресурса.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-572">You cannot hardcode or construct CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span> <span data-ttu-id="b4bd6-573">Вы можете создать URL-адрес для CDN и URL-адрес не должен быть жестко закодироваться, так как он подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-573">You can construct the URL for Public CDN and the URL should not be hard coded as it is subject to change.</span></span>

<span data-ttu-id="b4bd6-574">Для общедоступных CDN, формат URL-адресов будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-574">For public CDN assets, the URL format will look like the following:</span></span>

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="b4bd6-575">Замените **TenantHostName** именем клиента.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-575">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="b4bd6-576">Пример.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-576">Example:</span></span>

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> <span data-ttu-id="b4bd6-577">Свойство контекста страницы должно использоваться для построения префикса вместо жесткого кодирования https://publiccdn.sharepointonline.com ".</span><span class="sxs-lookup"><span data-stu-id="b4bd6-577">The page context property should be used to construct the prefix instead of hard coding "https://publiccdn.sharepointonline.com".</span></span> <span data-ttu-id="b4bd6-578">URL-адрес подлежит изменению и не должен быть жестко закодироваться.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-578">The URL is subject to change and should not be hard coded.</span></span> <span data-ttu-id="b4bd6-579">Если вы используете шаблоны отображения с classic SharePoint Online, вы можете использовать свойство "window._spPageContextInfo.publicCdnBaseUrl" в шаблоне отображения для префикса URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-579">If you are using display templates with Classic SharePoint Online then you can use the property "window._spPageContextInfo.publicCdnBaseUrl" in your display template for the prefix of the URL.</span></span> <span data-ttu-id="b4bd6-580">Если вы SPFx для современных и классических SharePoint, вы можете использовать свойство "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span><span class="sxs-lookup"><span data-stu-id="b4bd6-580">If you are SPFx web parts for modern and classic SharePoint the you can utilize the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl".</span></span> <span data-ttu-id="b4bd6-581">При этом будет предоставляться префикс, чтобы если он был изменен, то реализация обновляется вместе с ним.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-581">This will provide the prefix so that if it is changed then your implementation will update with it.</span></span> <span data-ttu-id="b4bd6-582">В качестве примера для SPFx URL-адрес может быть построен с помощью свойства "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "relativeURL для элемента".</span><span class="sxs-lookup"><span data-stu-id="b4bd6-582">As an example for SPFx, the URL can be constructed using the property "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item".</span></span> <span data-ttu-id="b4bd6-583">См. [CDN в клиентской](https://youtu.be/IH1RbQlbhIA) стороне кода, который является частью серии производительности [1 сезона](https://aka.ms/sppnp-perfvideos)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-583">Please see [Using CDN in Client-side code](https://youtu.be/IH1RbQlbhIA) which is part of the [season 1 performance series](https://aka.ms/sppnp-perfvideos)</span></span>


### <a name="using-assets-in-private-origins"></a><span data-ttu-id="b4bd6-584">Использование активов в частном происхождении</span><span class="sxs-lookup"><span data-stu-id="b4bd6-584">Using assets in private origins</span></span>

<span data-ttu-id="b4bd6-585">Для использования активов в частном происхождении не требуется дополнительная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-585">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="b4bd6-586">SharePoint Online автоматически переписывал URL-адреса для активов частного происхождения, поэтому запросы на эти активы всегда будут подаваться из CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-586">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="b4bd6-587">Невозможно вручную создавать URL-адреса для CDN активов частного происхождения, так как эти URL-адреса содержат маркеры, которые должны быть автоматически созданы SharePoint Online во время запроса актива.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-587">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="b4bd6-588">Доступ к активам частного происхождения защищен динамически созданными маркерами на основе разрешений пользователей на происхождение с оговорками, описанными в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-588">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="b4bd6-589">Пользователи должны иметь по крайней мере **доступ** к истокам для CDN для отрисовки контента.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-589">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="b4bd6-590">Следующая схема иллюстрирует рабочий процесс, SharePoint получает запрос на страницу, содержащую активы частного происхождения.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-590">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="b4bd6-591">![Схема рабочего процесса: Office 365 CDN активы частного происхождения](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Рабочий процесс: Office 365 CDN активы частного происхождения")</span><span class="sxs-lookup"><span data-stu-id="b4bd6-591">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="b4bd6-592">Авторизация на основе маркеров в частном происхождении</span><span class="sxs-lookup"><span data-stu-id="b4bd6-592">Token-based authorization in private origins</span></span>

<span data-ttu-id="b4bd6-593">Доступ к активам частного происхождения в Office 365 CDN предоставляется маркерами, созданными SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-593">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="b4bd6-594">Пользователям, у которых уже есть разрешение на доступ к папке или библиотеке, назначенной происхождением, автоматически выдают маркеры, которые позволяют пользователю получать доступ к файлу на основе уровня разрешений.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-594">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="b4bd6-595">Эти маркеры доступа действительны в течение 30-90 минут после их получения, чтобы предотвратить атаки повтора маркеров.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-595">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="b4bd6-596">После сгенерирования маркера доступа SharePoint Online возвращает пользовательский URI клиенту, содержащим два параметра авторизации едят _(маркер_ авторизации края) и овсяный _(маркер_ авторизации происхождения).</span><span class="sxs-lookup"><span data-stu-id="b4bd6-596">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="b4bd6-597">Структура каждого маркера —< времени действия в формате времени эпохи _>__<'secure signature'>_.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-597">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="b4bd6-598">Пример:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-598">For example:</span></span>

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="b4bd6-599">Любой, кто владеет маркером, может получить доступ к ресурсу в CDN.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-599">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="b4bd6-600">Однако URL-адреса, содержащие эти маркеры доступа, делятся только по HTTPS, поэтому если URL-адрес явно не будет доступен конечному пользователю до истечения срока действия маркера, актив будет недоступен для неавторизованных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-600">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="b4bd6-601">Разрешения на уровне элементов не поддерживаются для активов в частном происхождении</span><span class="sxs-lookup"><span data-stu-id="b4bd6-601">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="b4bd6-602">Важно отметить, что SharePoint Online не поддерживает разрешения на уровне элементов для активов частного происхождения.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-602">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="b4bd6-603">Например, для файла, расположенного по адресу, пользователи имеют эффективный доступ к файлу с учетом `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` следующих условий:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-603">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="b4bd6-604">User</span><span class="sxs-lookup"><span data-stu-id="b4bd6-604">User</span></span>  |<span data-ttu-id="b4bd6-605">Разрешения</span><span class="sxs-lookup"><span data-stu-id="b4bd6-605">Permissions</span></span>  |<span data-ttu-id="b4bd6-606">Эффективный доступ</span><span class="sxs-lookup"><span data-stu-id="b4bd6-606">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b4bd6-607">Пользователь 1</span><span class="sxs-lookup"><span data-stu-id="b4bd6-607">User 1</span></span>     |<span data-ttu-id="b4bd6-608">Имеет доступ к папке1</span><span class="sxs-lookup"><span data-stu-id="b4bd6-608">Has access to folder1</span></span>         |<span data-ttu-id="b4bd6-609">Можно получить image1.jpg из CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-609">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="b4bd6-610">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="b4bd6-610">User 2</span></span>     |<span data-ttu-id="b4bd6-611">Не имеет доступа к папке1</span><span class="sxs-lookup"><span data-stu-id="b4bd6-611">Does not have access to folder1</span></span>         |<span data-ttu-id="b4bd6-612">Не удается image1.jpg из CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-612">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="b4bd6-613">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="b4bd6-613">User 3</span></span>     |<span data-ttu-id="b4bd6-614">Не имеет доступа к папке1, но имеет явное разрешение на доступ к image1.jpg в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4bd6-614">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="b4bd6-615">Доступ к активу image1.jpg непосредственно из SharePoint Online, но не из CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-615">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="b4bd6-616">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="b4bd6-616">User 4</span></span>     |<span data-ttu-id="b4bd6-617">Имеет доступ к папке1, но был явно отказано в доступе к image1.jpg в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4bd6-617">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="b4bd6-618">Не удается получить доступ к активу из SharePoint Online, но может получить доступ к активу из CDN несмотря на то, что ему было отказано в доступе к файлу в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4bd6-618">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="b4bd6-619"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-619"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="b4bd6-620">Устранение неполадок Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="b4bd6-620">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="b4bd6-621"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="b4bd6-621"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="b4bd6-622">Как подтвердить, что активы обслуживаются CDN?</span><span class="sxs-lookup"><span data-stu-id="b4bd6-622">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="b4bd6-623">После того как вы добавили ссылки на CDN на страницу, вы можете подтвердить, что актив обслуживается из CDN, просматривая страницу, щелкнув правой кнопкой мыши по изображению после отрисовки и просмотрев URL-адрес изображения.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-623">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="b4bd6-624">Вы также можете использовать средства разработчика браузера для просмотра URL-адреса для каждого актива на странице или с помощью средства трассировки сторонних сетей.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-624">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="b4bd6-625">Если вы используете сетевой инструмент, например Fiddler, чтобы проверить свои активы вне отрисовки актива со страницы SharePoint, необходимо вручную добавить загонщика ссылок "Referer:" в запрос GET, где URL-адрес является корневым URL-адресом клиента `https://yourdomain.sharepoint.com` SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-625">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="b4bd6-626">Вы не можете CDN URL-адреса непосредственно в веб-браузере, так как необходимо иметь ссылщик, исходя из SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-626">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="b4bd6-627">Однако если добавить URL CDN актива на страницу SharePoint, а затем открыть страницу в браузере, вы увидите CDN актива, отрисовав на странице.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-627">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="b4bd6-628">Дополнительные сведения об использовании средств разработчика в браузере Microsoft Edge см. в Microsoft Edge [Developer Tools.](/microsoft-edge/devtools-guide)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-628">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="b4bd6-629">Чтобы просмотреть короткое видео, размещенное в канале SharePoint Developer [Patterns and Practices YouTube,](https://aka.ms/sppnp-videos) демонстрирующее, как убедиться в том, что CDN работает, см. в странице Проверка использования CDN и обеспечение оптимального подключения к сети [.](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)</span><span class="sxs-lookup"><span data-stu-id="b4bd6-629">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="b4bd6-630">Почему недоступны активы нового происхождения?</span><span class="sxs-lookup"><span data-stu-id="b4bd6-630">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="b4bd6-631">Активы нового происхождения не будут сразу доступны для использования, так как для распространения регистрации через CDN и для отправки активов из источника в хранилище CDN требуется время.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-631">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="b4bd6-632">Время, необходимое для того, чтобы активы были доступны в CDN зависит от того, сколько ресурсов и размеров файлов.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-632">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="b4bd6-633">Моя клиентская веб-часть или SharePoint Framework не работает</span><span class="sxs-lookup"><span data-stu-id="b4bd6-633">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="b4bd6-634">Когда вы включаете Office 365 CDN для общедоступных истоков, CDN автоматически создает эти истоки по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-634">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="b4bd6-635">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="b4bd6-635">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="b4bd6-636">\*/STYLE LIBRARY</span><span class="sxs-lookup"><span data-stu-id="b4bd6-636">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="b4bd6-637">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="b4bd6-637">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="b4bd6-638">Если происхождение \*/clientsideassets отсутствует, SharePoint Framework не удастся, и не будут созданы предупреждения или сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="b4bd6-638">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="b4bd6-639">Это происхождение может быть пропущено, поскольку CDN включен с параметром _-NoDefaultOrigins,_ заданным $true, или потому, что происхождение было удалено вручную. </span><span class="sxs-lookup"><span data-stu-id="b4bd6-639">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="b4bd6-640">Вы можете проверить, какие истоки присутствуют со следующей командой PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-640">You can check to see which origins are present with the following PowerShell command:</span></span>

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="b4bd6-641">Или вы можете проверить с Office 365 CLI:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-641">Or you can check with the Office 365 CLI:</span></span>

```cli
spo cdn origin list
```

<span data-ttu-id="b4bd6-642">Чтобы добавить начало в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-642">To add the origin in PowerShell:</span></span>

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="b4bd6-643">Чтобы добавить источник в Office 365 CLI:</span><span class="sxs-lookup"><span data-stu-id="b4bd6-643">To add the origin in the Office 365 CLI:</span></span>

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="b4bd6-644">Какие модули PowerShell и оболочки CLI необходимы для работы с Office 365 CDN?</span><span class="sxs-lookup"><span data-stu-id="b4bd6-644">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="b4bd6-645">Вы можете работать с Office 365 CDN с помощью модуля powerShell SharePoint **сетевой** командной оболочки или **Office 365 CLI.**</span><span class="sxs-lookup"><span data-stu-id="b4bd6-645">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="b4bd6-646">Начало работы с командной консолью SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4bd6-646">Getting started with SharePoint Online Management Shell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
+ [<span data-ttu-id="b4bd6-647">Установка Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="b4bd6-647">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="b4bd6-648">См. также</span><span class="sxs-lookup"><span data-stu-id="b4bd6-648">See also</span></span>

[<span data-ttu-id="b4bd6-649">Сети доставки содержимого</span><span class="sxs-lookup"><span data-stu-id="b4bd6-649">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="b4bd6-650">Планирование сети и настройка производительности для Office 365</span><span class="sxs-lookup"><span data-stu-id="b4bd6-650">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="b4bd6-651">SharePoint Серия производительности — Office 365 CDN видеосериалов</span><span class="sxs-lookup"><span data-stu-id="b4bd6-651">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
