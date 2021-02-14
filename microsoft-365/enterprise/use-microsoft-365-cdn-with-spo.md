---
title: Использование сети доставки содержимого (CDN) Office 365 с SharePoint Online
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
description: Узнайте, как использовать сеть доставки содержимого (CDN) Office 365 для ускорения доставки ресурсов SharePoint Online.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692979"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a><span data-ttu-id="bb3e9-103">Использование сети доставки содержимого Office 365 с SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-103">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>

<span data-ttu-id="bb3e9-104">Вы можете использовать встроенную сеть доставки содержимого (CDN) Office 365 для размещения статических ресурсов, чтобы повысить производительность страниц SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-104">You can use the built-in Office 365 Content Delivery Network (CDN) to host static assets to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="bb3e9-105">Сеть CDN Office 365 повышает производительность путем кэширования статических ресурсов ближе к браузерам, которые их запрашивают, что повышает скорость скачиваний и снижает задержку.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="bb3e9-106">Кроме того, cdN Office 365 использует [протокол HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) для улучшения сжатия и конвейерной работы HTTP.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-106">Also, the Office 365 CDN uses the [HTTP/2 protocol](https://en.wikipedia.org/wiki/HTTP/2) for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="bb3e9-107">Служба CDN Office 365 входит в состав подписки на SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e9-108">Сеть CDN Office 365 доступна только для клиентов в облаке **Production** (по всему миру).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-108">The Office 365 CDN is only available to tenants in the **Production** (worldwide) cloud.</span></span> <span data-ttu-id="bb3e9-109">Клиенты в облаках для правительства США, Китая и Германии в настоящее время не поддерживают CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-109">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

<span data-ttu-id="bb3e9-110">Сети доставки содержимого Office 365 состоит из нескольких сетей CDN, позволяющих размещать статические ресурсы в нескольких расположениях или _источниках_ и использовать их из глобальных высокоскоростных сетей.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-110">The Office 365 CDN is composed of multiple CDNs that allow you to host static assets in multiple locations, or _origins_, and serve them from global high-speed networks.</span></span> <span data-ttu-id="bb3e9-111">В зависимости от типа содержимого, которое необходимо разместить в сети CDN Office 365, можно добавить **общедоступные** источники, **закрытые** источники или оба варианта.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-111">Depending on the kind of content you want to host in the Office 365 CDN, you can add **public** origins, **private** origins or both.</span></span> <span data-ttu-id="bb3e9-112">Дополнительные [сведения о](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) различиях между общедоступными и частными источниками см. в под вопросе "Выбор того, должен ли каждый источник быть общедоступным или частным".</span><span class="sxs-lookup"><span data-stu-id="bb3e9-112">See [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) for more information on the difference between public and private origins.</span></span>

<span data-ttu-id="bb3e9-113">![Концептуальная схема CDN Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Концептуальная схема CDN Office 365")</span><span class="sxs-lookup"><span data-stu-id="bb3e9-113">![Office 365 CDN conceptual diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptual diagram")</span></span>

<span data-ttu-id="bb3e9-114">Если вы уже знакомы с работой CDN, вам нужно выполнить всего несколько действий, чтобы включить CDN Office 365 для своего клиента.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-114">If you are already familiar with the way that CDNs work, you only need to complete a few steps to enable the Office 365 CDN for your tenant.</span></span> <span data-ttu-id="bb3e9-115">В этом разделе описывается, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-115">This topic describes how.</span></span> <span data-ttu-id="bb3e9-116">Сведения о том, как начать размещение статических ресурсов, можно найти в этом документе.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-116">Read on for information about how to get started hosting your static assets.</span></span>

> [!TIP]
> <span data-ttu-id="bb3e9-117">Существуют и другие сети CDN, которые можно использовать с Office 365 для специальных сценариев использования, но не обсуждаются в этом разделе, так как они не находятся за пределами сети CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-117">There are other Microsoft-hosted CDNs that can be used with Office 365 for specialized usage scenarios, but are not discussed in this topic because they fall outside the scope of the Office 365 CDN.</span></span> <span data-ttu-id="bb3e9-118">Дополнительные сведения [см. в других CDNs Майкрософт.](content-delivery-networks.md#other-microsoft-cdns)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-118">For more information, see [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).</span></span>

 <span data-ttu-id="bb3e9-119">**Вернуться к [планированию сети и настройке производительности для Office 365.](https://aka.ms/tune)**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-119">**Head back to [Network planning and performance tuning for Office 365](https://aka.ms/tune).**</span></span>

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a><span data-ttu-id="bb3e9-120">Обзор работы с сетью CDN Office 365 в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-120">Overview of working with the Office 365 CDN in SharePoint Online</span></span>

<span data-ttu-id="bb3e9-121">Чтобы настроить CDN Office 365 для организации, выполните следующие основные действия.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-121">To set up the Office 365 CDN for your organization, you follow these basic steps:</span></span>

+ [<span data-ttu-id="bb3e9-122">Планирование развертывания CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-122">Plan for deployment of the Office 365 CDN</span></span>](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + <span data-ttu-id="bb3e9-123">[Определите, какие статические ресурсы необходимо установить в CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-123">[Determine which static assets you want to host on the CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).</span></span>
  + <span data-ttu-id="bb3e9-124">[Определите, где вы хотите хранить активы.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-124">[Determine where you want to store your assets](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets).</span></span> <span data-ttu-id="bb3e9-125">Это расположение может быть сайтом, библиотекой или папкой SharePoint и называется _началом._</span><span class="sxs-lookup"><span data-stu-id="bb3e9-125">This location can be a SharePoint site, library or folder and is called an _origin_.</span></span>
  + <span data-ttu-id="bb3e9-126">[Выберите, должен ли каждый источник быть общедоступным или частным.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-126">[Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span> <span data-ttu-id="bb3e9-127">Можно добавить несколько источников как общедоступных, так и частных типов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-127">You can add multiple origins of both public and private types.</span></span>

+ <span data-ttu-id="bb3e9-128">Настройка сети CDN с помощью PowerShell или sharePoint Online CLI</span><span class="sxs-lookup"><span data-stu-id="bb3e9-128">Set up and configure the CDN, using either PowerShell or the SharePoint Online CLI</span></span>

  + [<span data-ttu-id="bb3e9-129">Настройка сети CDN с помощью оболочки управления SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-129">Set up and configure the CDN by using the SharePoint Online Management Shell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [<span data-ttu-id="bb3e9-130">Настройка и настройка CDN с помощью PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb3e9-130">Set up and configure the CDN by using PnP PowerShell</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [<span data-ttu-id="bb3e9-131">Настройка и настройка CDN с помощью Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="bb3e9-131">Set up and configure the CDN by using the Office 365 CLI</span></span>](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  <span data-ttu-id="bb3e9-132">После выполнения этого шага у вас будут:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-132">When you complete this step, you will have:</span></span>

  + <span data-ttu-id="bb3e9-133">Включена CDN для организации.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-133">Enabled the CDN for your organization.</span></span>
  + <span data-ttu-id="bb3e9-134">Добавлены ваши источника, определяющие каждый источник как общедоступный или частный.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-134">Added your origins, identifying each origin as public or private.</span></span>

<span data-ttu-id="bb3e9-135">После настройки вы сможете управлять [CDN Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) с помощью:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-135">Once you're done with setup, you can [Manage the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) over time by:</span></span>
  
+ <span data-ttu-id="bb3e9-136">Добавление, обновление и удаление активов</span><span class="sxs-lookup"><span data-stu-id="bb3e9-136">Adding, updating, and removing assets</span></span>
+ <span data-ttu-id="bb3e9-137">Добавление и удаление источника</span><span class="sxs-lookup"><span data-stu-id="bb3e9-137">Adding and removing origins</span></span>
+ <span data-ttu-id="bb3e9-138">Настройка политик CDN</span><span class="sxs-lookup"><span data-stu-id="bb3e9-138">Configuring CDN policies</span></span>
+ <span data-ttu-id="bb3e9-139">При необходимости отключать CDN</span><span class="sxs-lookup"><span data-stu-id="bb3e9-139">If necessary, disabling the CDN</span></span>

<span data-ttu-id="bb3e9-140">Наконец, [см. информацию](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) об использовании ресурсов CDN для получения доступа к своим активам CDN как из общедоступных, так и из частных источниках.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-140">Finally, see [Using your CDN assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) to learn about accessing your CDN assets from both public and private origins.</span></span>

<span data-ttu-id="bb3e9-141">Инструкции по устранению распространенных проблем см. в руководстве по устранению неполадок [в CDN Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-141">See [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues.</span></span>

## <a name="plan-for-deployment-of-the-office-365-cdn"></a><span data-ttu-id="bb3e9-142">Планирование развертывания CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-142">Plan for deployment of the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-143">Перед развертыванием CDN Office 365 для клиента Office 365 необходимо учесть следующие факторы в процессе планирования.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-143">Before you deploy the Office 365 CDN for your Office 365 tenant, you should consider the following factors as part of your planning process.</span></span>

  + [<span data-ttu-id="bb3e9-144">Определение статических ресурсов, которые необходимо установить в CDN</span><span class="sxs-lookup"><span data-stu-id="bb3e9-144">Determine which static assets you want to host on the CDN</span></span>](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [<span data-ttu-id="bb3e9-145">Определение места хранения активов</span><span class="sxs-lookup"><span data-stu-id="bb3e9-145">Determine where you want to store your assets</span></span>](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [<span data-ttu-id="bb3e9-146">Выберите, должен ли каждый источник быть общедоступным или частным</span><span class="sxs-lookup"><span data-stu-id="bb3e9-146">Choose whether each origin should be public or private</span></span>](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<span data-ttu-id="bb3e9-147"><a name="CDNAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-147"><a name="CDNAssets"> </a></span></span>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a><span data-ttu-id="bb3e9-148">Определение статических ресурсов, которые необходимо установить в CDN</span><span class="sxs-lookup"><span data-stu-id="bb3e9-148">Determine which static assets you want to host on the CDN</span></span>

<span data-ttu-id="bb3e9-149">Как правило, CDNs наиболее эффективны для размещения статических ресурсов или _ресурсов,_ которые не изменяются очень часто.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-149">In general, CDNs are most effective for hosting _static assets_, or assets that don't change very often.</span></span> <span data-ttu-id="bb3e9-150">Хорошим правилом является определение файлов, которые соответствуют некоторым или всем из этих условий:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-150">A good rule of thumb is to identify files that meet some or all of these conditions:</span></span>

+ <span data-ttu-id="bb3e9-151">Статические файлы, внедренные в страницу (например, сценарии и изображения), которые могут существенно повлиять на время загрузки страницы</span><span class="sxs-lookup"><span data-stu-id="bb3e9-151">Static files embedded in a page (like scripts and images) that may have a significant incremental impact on page load times</span></span>
+ <span data-ttu-id="bb3e9-152">Большие файлы, такие как исполняемые файлы и файлы установки</span><span class="sxs-lookup"><span data-stu-id="bb3e9-152">Large files like executables and installation files</span></span>
+ <span data-ttu-id="bb3e9-153">Библиотеки ресурсов, которые поддерживают клиентский код</span><span class="sxs-lookup"><span data-stu-id="bb3e9-153">Resource libraries that support client-side code</span></span>

<span data-ttu-id="bb3e9-154">Например, небольшие файлы, которые постоянно запрашиваются, например изображения сайта и сценарии, могут значительно повысить производительность отображения сайта и постепенно снизить нагрузку на сайты SharePoint Online при добавлении их в источник CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-154">For example, small files that are repeatedly requested like site images and scripts can significantly improve site rendering performance and incrementally reduce the load on your SharePoint Online sites when you add them to a CDN origin.</span></span> <span data-ttu-id="bb3e9-155">Большие файлы, такие как исполняемые файлы установки, можно загрузить из сети CDN, что положительно влияет на производительность и последующее снижение нагрузки на сайт SharePoint Online, даже если к ним не используется так часто.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-155">Larger files such as installation executables can be downloaded from the CDN, delivering a positive performance impact and subsequent reduction of the load on your SharePoint Online site, even if they are not accessed as often.</span></span>

<span data-ttu-id="bb3e9-156">Повышение производительности для каждого файла зависит от многих факторов, включая близость клиента к ближайшей конечной точке CDN, временные условия в локальной сети и т. д.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-156">Performance improvement on a per-file basis is dependent on many factors, including the client's proximity to the nearest CDN endpoint, transient conditions on the local network, and so forth.</span></span> <span data-ttu-id="bb3e9-157">Многие статические файлы довольно маленькие, и их можно скачать из Office 365 менее чем за секунду.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-157">Many static files are quite small, and can be downloaded from Office 365 in less than a second.</span></span> <span data-ttu-id="bb3e9-158">Однако веб-страница может содержать много внедренных файлов с накопительным временем загрузки в несколько секунд.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-158">However, a web page may contain many embedded files with a cumulative download time of several seconds.</span></span> <span data-ttu-id="bb3e9-159">Обслуживание этих файлов из СЕТИ CDN может значительно сократить общее время загрузки страницы.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-159">Serving these files from the CDN can significantly reduce the overall page load time.</span></span> <span data-ttu-id="bb3e9-160">Посмотрите, [какие показатели производительности обеспечивает CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) Например.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-160">See [What performance gains does a CDN provide?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) for an example.</span></span>

<span data-ttu-id="bb3e9-161"><a name="CDNStoreAssets"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-161"><a name="CDNStoreAssets"> </a></span></span>
### <a name="determine-where-you-want-to-store-your-assets"></a><span data-ttu-id="bb3e9-162">Определение места хранения активов</span><span class="sxs-lookup"><span data-stu-id="bb3e9-162">Determine where you want to store your assets</span></span>

<span data-ttu-id="bb3e9-163">CDN извлекает ресурсы из расположения, называемого _началом._</span><span class="sxs-lookup"><span data-stu-id="bb3e9-163">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="bb3e9-164">Источником может быть сайт SharePoint, библиотека документов или папка, доступная по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-164">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span> <span data-ttu-id="bb3e9-165">У вас есть большая гибкость при указании источника для организации.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-165">You have great flexibility when you specify origins for your organization.</span></span> <span data-ttu-id="bb3e9-166">Например, можно указать несколько источников или один источник, в который необходимо поместить все ресурсы CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-166">For example, you can specify multiple origins or a single origin where you want to put all your CDN assets.</span></span> <span data-ttu-id="bb3e9-167">Вы можете выбрать как общедоступные, так и частные источника для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-167">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="bb3e9-168">Большинство организаций предпочитают реализовать сочетание этих двух вариантов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-168">Most organizations will choose to implement a combination of the two.</span></span>

<span data-ttu-id="bb3e9-169">Вы можете создать новый контейнер для своего источника, например папок или библиотек документов, и добавить файлы, которые вы хотите сделать доступными из CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-169">You can create new container for your origins such as folders or document libraries, and add files you want to make available from the CDN.</span></span> <span data-ttu-id="bb3e9-170">Это хороший подход, если у вас есть определенный набор ресурсов, которые вы хотите получить из CDN и хотите ограничить набор ресурсов CDN только теми файлами в контейнере.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-170">This is a good approach if you have a specific set of assets you want to be available from the CDN, and want to restrict the set of CDN assets to only those files in the container.</span></span>

<span data-ttu-id="bb3e9-171">Можно также настроить существующее коллекцию веб-сайтов, сайт, библиотеку или папку в качестве источника, что сделает все доступные ресурсы в контейнере доступными из СЕТИ CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-171">You can also configure an existing site collection, site, library or folder as an origin, which will make all eligible assets in the container available from the CDN.</span></span> <span data-ttu-id="bb3e9-172">Перед добавлением существующего контейнера в качестве источника важно убедиться, что вы в курсе его содержимого и разрешений, чтобы случайно не дать доступ к активам анонимным пользователям или неавторизованным пользователям.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-172">Before you add an existing container as an origin, it's important to make sure you are aware of its contents and permissions so you do not inadvertently expose assets to anonymous access or unauthorized users.</span></span>

<span data-ttu-id="bb3e9-173">Вы можете определить политики _CDN,_ чтобы исключить содержимое в источниках из CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-173">You can define _CDN policies_ to exclude content in your origins from the CDN.</span></span> <span data-ttu-id="bb3e9-174">Политики CDN исключают ресурсы в общедоступных или частных источниках по атрибутам, таким как тип файла и классификация _сайтов,_ и применяются к всем источникам CdnType (закрытого или открытого), задаемого в политике. </span><span class="sxs-lookup"><span data-stu-id="bb3e9-174">CDN policies exclude assets in public or private origins by attributes such as _file type_ and _site classification_, and are applied to all origins of the CdnType (private or public) you specify in the policy.</span></span> <span data-ttu-id="bb3e9-175">Например, при добавлении частного источника, состоящего из сайта, который содержит несколько подсайтов, можно определить политику исключения сайтов, помеченных как конфиденциальные, чтобы контент с сайтов с примененной классификацией не обслуживался из сети CDN. </span><span class="sxs-lookup"><span data-stu-id="bb3e9-175">For example, if you add a private origin consisting of a site that contains multiple subsites, you can define a policy to exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span> <span data-ttu-id="bb3e9-176">Политика будет применяться к контенту из _всех частных_ источниках, добавленных в CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-176">The policy will apply to content from _all_ private origins you have added to the CDN.</span></span>
  
<span data-ttu-id="bb3e9-177">Помните, что чем больше количество источников, тем больше влияние на время обработки запросов службой CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-177">Keep in mind that the greater the number of origins, the greater the impact on the time it takes the CDN service to process requests.</span></span> <span data-ttu-id="bb3e9-178">Рекомендуется максимально ограничить количество источников.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-178">We recommend that you limit the number of origins as much as possible.</span></span>
  
<span data-ttu-id="bb3e9-179"><a name="CDNOriginChoosePublicPrivate"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-179"><a name="CDNOriginChoosePublicPrivate"> </a></span></span>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a><span data-ttu-id="bb3e9-180">Выберите, должен ли каждый источник быть общедоступным или частным</span><span class="sxs-lookup"><span data-stu-id="bb3e9-180">Choose whether each origin should be public or private</span></span>

<span data-ttu-id="bb3e9-181">При определении источника указывается, следует ли сделать его общедоступным _или_ _частным._</span><span class="sxs-lookup"><span data-stu-id="bb3e9-181">When you identify an origin, you specify whether it should be made _public_ or _private_.</span></span> <span data-ttu-id="bb3e9-182">Доступ к активам CDN в общедоступных источниках является анонимным, а содержимое CDN в частных источниках защищено динамически созданными маркерами для большей безопасности.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-182">Access to CDN assets in public origins is anonymous, and CDN content in private origins is secured by dynamically generated tokens for greater security.</span></span> <span data-ttu-id="bb3e9-183">Независимо от того, какой вариант вы выберете, Корпорация Майкрософт делает все возможное для вас, когда речь идет об администрировании самой CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-183">Regardless of which option you choose, Microsoft does all the heavy lifting for you when it comes to administration of the CDN itself.</span></span> <span data-ttu-id="bb3e9-184">Кроме того, вы можете изменить свое решение позже, после того как настроите CDN и настроите свои происхождение.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-184">Also, you can change your mind later, after you've set up the CDN and identified your origins.</span></span>

<span data-ttu-id="bb3e9-185">Как общедоступные, так и частные варианты обеспечивают одинаковый рост производительности, но каждый из них имеет уникальные атрибуты и преимущества.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-185">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span>

<span data-ttu-id="bb3e9-186">**Общедоступные** источники в сети CDN Office 365 доступны анонимно, а к общедоступным активам может получить доступ любой, у кого есть URL-адрес актива.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-186">**Public** origins within the Office 365 CDN are accessible anonymously, and hosted assets can be accessed by anyone who has the URL to the asset.</span></span> <span data-ttu-id="bb3e9-187">Так как доступ к содержимому в общедоступных источниках является анонимным, следует использовать их только для кэширования неконфиденциального общего содержимого, например файлов JavaScript, скриптов, значков и изображений.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-187">Because access to content in public origins is anonymous, you should only use them to cache non-sensitive generic content such as javascript files, scripts, icons and images.</span></span>

<span data-ttu-id="bb3e9-188">**Частные** источника в сети CDN Office 365 предоставляют закрытый доступ к пользовательскому контенту, например библиотекам документов SharePoint Online, сайтам и проприетарным изображениям.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-188">**Private** origins within the Office 365 CDN provide private access to user content such as SharePoint Online document libraries, sites and proprietary images.</span></span> <span data-ttu-id="bb3e9-189">Доступ к контенту в частных источниках защищен динамически созданными маркерами, поэтому доступ к нему могут получить только пользователи с разрешениями на доступ к исходной библиотеке документов или месту хранения.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-189">Access to content in private origins is secured by dynamically generated tokens so it can only be accessed by users with permissions to the original document library or storage location.</span></span> <span data-ttu-id="bb3e9-190">Частные источника в сети CDN Office 365 можно использовать только для контента SharePoint Online, и доступ к активам в частных источниках можно получить только через перенаправление из клиента SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-190">Private origins in the Office 365 CDN can only be used for SharePoint Online content, and you can only access assets in private origins through redirection from your SharePoint Online tenant.</span></span>

<span data-ttu-id="bb3e9-191">Подробнее о том, как работает доступ к активам в частном источнике в СЕТИ CDN, можно узнать в документе "Использование ресурсов [в частных источниках".](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-191">You can read more about how CDN access to assets in a private origin works in [Using assets in private origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a><span data-ttu-id="bb3e9-192">Атрибуты и преимущества размещения активов в общедоступных источниках</span><span class="sxs-lookup"><span data-stu-id="bb3e9-192">Attributes and advantages of hosting assets in public origins</span></span>
  
+ <span data-ttu-id="bb3e9-193">Ресурсы, предоставляемые из общедоступного источника, доступны всем анонимно.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-193">Assets exposed in a public origin are accessible by everyone anonymously.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="bb3e9-194">Никогда не следует разместить ресурсы, которые содержат сведения о пользователе или считаются конфиденциальными для вашей организации, в общедоступных источниках.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-194">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>
+ <span data-ttu-id="bb3e9-195">Если удалить ресурс из общедоступного источника, он может оставаться доступным в кэше до 30 дней. Однако ссылки на ресурс в сети CDN станут недействительными в течение 15 минут.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-195">If you remove an asset from a public origin, the asset may continue to be available for up to 30 days from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes.</span></span>
+ <span data-ttu-id="bb3e9-196">При размещении таблиц стилей (CSS-файлов) в общедоступном источнике можно использовать в коде относительные пути и URI.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-196">When you host style sheets (CSS files) in a public origin, you can use relative paths and URIs within the code.</span></span> <span data-ttu-id="bb3e9-197">Это означает, что вы можете ссылаться на расположение фоновых изображений и других объектов относительно расположения ресурса, который вызывает его.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-197">This means that you can reference the location of background images and other objects relative to the location of the asset that's calling it.</span></span>
+ <span data-ttu-id="bb3e9-198">Вы можете жестко задать URL-адрес общедоступного источника, но это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-198">While you can hard code a public origin's URL, doing so is not recommended.</span></span> <span data-ttu-id="bb3e9-199">Это связано с тем, что если сеть CDN станет недоступна, то URL-адрес не будет автоматически указывать на вашу организацию в SharePoint Online, что может привести к неработоспособности ссылок и другим ошибкам.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-199">The reason for this is that if access to the CDN becomes unavailable, the URL will not automatically resolve to your organization in SharePoint Online and might result in broken links and other errors.</span></span>
+ <span data-ttu-id="bb3e9-200">Типы файлов по умолчанию, включенные в общедоступные источника: CSS, EOT, GIF, ICO, JPEG, JPG, JS, MAP, PNG, SVG, TTF, WOFF и WOFF2.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-200">The default file types that are included for public origins are .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2.</span></span> <span data-ttu-id="bb3e9-201">Можно указать дополнительные типы файлов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-201">You can specify additional file types.</span></span>
+ <span data-ttu-id="bb3e9-202">Вы можете настроить политику, чтобы исключить ресурсы, выявленные по заданной классификации сайтов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-202">You can configure a policy to exclude assets that have been identified by site classifications that you specify.</span></span> <span data-ttu-id="bb3e9-203">Например, вы можете исключать все ресурсы, отмеченные как "конфиденциальные" или "с ограниченным доступом", даже если они относятся к разрешенным типам файлов и находятся в общедоступном источнике.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-203">For example, you can choose to exclude all assets that are marked as "confidential" or "restricted" even if they are an allowed file type and are located in a public origin.</span></span>

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a><span data-ttu-id="bb3e9-204">Атрибуты и преимущества размещения активов в частных источниках</span><span class="sxs-lookup"><span data-stu-id="bb3e9-204">Attributes and advantages of hosting assets in private origins</span></span>

+ <span data-ttu-id="bb3e9-205">Частные источника можно использовать только для активов SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-205">Private origins can only be used for SharePoint Online assets.</span></span>
+ <span data-ttu-id="bb3e9-206">Пользователи могут получить доступ к активам только из частного источника, если у них есть разрешения на доступ к контейнеру.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-206">Users can only access the assets from a private origin if they have permissions to access the container.</span></span> <span data-ttu-id="bb3e9-207">Анонимный доступ к таким ресурсам запрещен.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-207">Anonymous access to these assets is prevented.</span></span>
+ <span data-ttu-id="bb3e9-208">Ресурсы в частных источниках должны быть переданы из клиента SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-208">Assets in private origins must be referred from the SharePoint Online tenant.</span></span> <span data-ttu-id="bb3e9-209">Прямой доступ к частным активам CDN не работает.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-209">Direct access to private CDN assets does not work.</span></span>
+ <span data-ttu-id="bb3e9-210">Если удалить ресурс из частного источника, актив может оставаться доступным в течение часа из кэша; Однако ссылки на ресурс в CDN будут недействительны в течение 15 минут после удаления актива.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-210">If you remove an asset from the private origin, the asset may continue to be available for up to an hour from the cache; however, we will invalidate links to the asset in the CDN within 15 minutes of the asset's removal.</span></span>
+ <span data-ttu-id="bb3e9-211">По умолчанию для частных источников включены типы файлов GIF, ICO, JPEG, JPG, JS и PNG.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-211">The default file types that are included for private origins are .gif, .ico, .jpeg, .jpg, .js, and .png.</span></span> <span data-ttu-id="bb3e9-212">Можно указать дополнительные типы файлов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-212">You can specify additional file types.</span></span>
+ <span data-ttu-id="bb3e9-213">Как и в случае с общедоступными источниками, можно настроить политику для исключения активов, которые определены в классификациях сайтов, которые указываются, даже если вы используете поддиаптер для всех ресурсов в папке или библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-213">Just like with public origins, you can configure a policy to exclude assets that have been identified by site classifications that you specify even if you use wildcards to include all assets within a folder or document library.</span></span>

<span data-ttu-id="bb3e9-214">Дополнительные сведения о том, зачем использовать сеть CDN Office 365, общие концепции CDN и другие [](content-delivery-networks.md)сети CDN Майкрософт, которые можно использовать с клиентом Office 365, см. в подсетях доставки содержимого.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-214">For more information about why to use the Office 365 CDN, general CDN concepts, and other Microsoft CDNs you can use with your Office 365 tenant, see [Content Delivery Networks](content-delivery-networks.md).</span></span>

### <a name="default-cdn-origins"></a><span data-ttu-id="bb3e9-215">Источника CDN по умолчанию</span><span class="sxs-lookup"><span data-stu-id="bb3e9-215">Default CDN origins</span></span>

<span data-ttu-id="bb3e9-216">Если вы не указали иное, Office 365 настраивает некоторые стандартные источника для вас, когда вы включаете CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-216">Unless you specify otherwise, Office 365 sets up some default origins for you when you enable the Office 365 CDN.</span></span> <span data-ttu-id="bb3e9-217">Если изначально вы решили не заполнять их, вы можете добавить эти источника после завершения настройки.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-217">If you initially opt not to provision them, you can add these origins after you complete setup.</span></span> <span data-ttu-id="bb3e9-218">Если вы не понимаете последствия пропуска настройки источника по умолчанию и не имеете особой причины для этого, следует разрешить их создавать при в сети CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-218">Unless you understand the consequences of skipping the setup of default origins and have a specific reason for doing so, you should allow them to be created when you enable the CDN.</span></span>
  
<span data-ttu-id="bb3e9-219">Частные источника CDN по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-219">Default private CDN origins:</span></span>
  
+ <span data-ttu-id="bb3e9-220">\*/userphoto.aspx</span><span class="sxs-lookup"><span data-stu-id="bb3e9-220">\*/userphoto.aspx</span></span>
+ <span data-ttu-id="bb3e9-221">\*/siteassets</span><span class="sxs-lookup"><span data-stu-id="bb3e9-221">\*/siteassets</span></span>

<span data-ttu-id="bb3e9-222">Общедоступные источника CDN по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-222">Default public CDN origins:</span></span>
  
+ <span data-ttu-id="bb3e9-223">\*/masterpage</span><span class="sxs-lookup"><span data-stu-id="bb3e9-223">\*/masterpage</span></span>
+ <span data-ttu-id="bb3e9-224">\*/style library</span><span class="sxs-lookup"><span data-stu-id="bb3e9-224">\*/style library</span></span>
+ <span data-ttu-id="bb3e9-225">\*/clientsideassets</span><span class="sxs-lookup"><span data-stu-id="bb3e9-225">\*/clientsideassets</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e9-226">_clientsideassets_ — это общедоступный источник по умолчанию, который был добавлен в службу CDN Office 365 в декабре 2017 г.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-226">_clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017.</span></span> <span data-ttu-id="bb3e9-227">Этот источник должен присутствовать, чтобы решения SharePoint Framework в CDN работали.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-227">This origin must be present in order for SharePoint Framework solutions in the CDN to work.</span></span> <span data-ttu-id="bb3e9-228">Если вы включили CDN Office 365 до декабря 2017 г. или пропустили настройку источника по умолчанию при включив CDN, вы можете вручную добавить этот источник.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-228">If you enabled the Office 365 CDN prior to December 2017, or if you skipped setup of default origins when you enabled the CDN, you can manually add this origin.</span></span> <span data-ttu-id="bb3e9-229">Дополнительные сведения см. в сведениях о том, как не работает моя клиентская веб-часть или решение [SharePoint Framework.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-229">For more information, see [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).</span></span>

<span data-ttu-id="bb3e9-230"><a name="CDNSetupinPShell"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-230"><a name="CDNSetupinPShell"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a><span data-ttu-id="bb3e9-231">Настройка сети CDN Office 365 с помощью оболочки управления SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-231">Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell</span></span>

<span data-ttu-id="bb3e9-232">Процедуры в этом разделе требуют использования оболочки управления SharePoint Online для подключения к SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-232">The procedures in this section require you to use the SharePoint Online Management Shell to connect to SharePoint Online.</span></span> <span data-ttu-id="bb3e9-233">Инструкции см. в статье [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-233">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

<span data-ttu-id="bb3e9-234">Выполните следующие действия, чтобы настроить СЕТЬ CDN для организации активов в SharePoint Online с помощью оболочки управления SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-234">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the SharePoint Online Management Shell.</span></span>

<details>
  <summary><span data-ttu-id="bb3e9-235">Щелкните, чтобы развернуть</span><span class="sxs-lookup"><span data-stu-id="bb3e9-235">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="bb3e9-236">Включить в организации использование CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-236">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-237">Перед внесением изменений в параметры сети CDN клиента необходимо получить текущее состояние конфигурации частной сети CDN в клиенте Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-237">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="bb3e9-238">Подключитесь к вашему арендатору с помощью оболочки управления SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-238">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

<span data-ttu-id="bb3e9-239">Теперь используйте для извлечения параметров состояния CDN из клиента с помощью cmdlet **Get-SPOTenantCdnEnabled:**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-239">Now use the **Get-SPOTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="bb3e9-240">Состояние CDN для указанного CdnType будет выводит на экран.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-240">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="bb3e9-241">Используйте для организации использование CDN Office 365 с помощьюлета **Set-SPOTenantCdnEnabled.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-241">Use the **Set-SPOTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="bb3e9-242">Вы можете позволить организации использовать общедоступные, частные или оба источника одновременно.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-242">You can enable your organization to use public origins, private origins, or both at once.</span></span> <span data-ttu-id="bb3e9-243">Кроме того, можно настроить CDN так, чтобы она пропускала установку источника по умолчанию при ее в сети.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-243">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="bb3e9-244">Вы всегда можете добавить эти источника позже, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-244">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="bb3e9-245">В Windows Powershell для SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-245">In Windows Powershell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="bb3e9-246">Например, чтобы позволить организации использовать как общедоступные, так и частные источника, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-246">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="bb3e9-247">Чтобы позволить организации использовать как общедоступные, так и частные источника, но пропустить настройку источника по умолчанию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-247">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="bb3e9-248">В [источниках CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) по умолчанию вы можете получить сведения об источниках, которые по умолчанию одежные при в сети CDN Office 365, а также о возможном влиянии пропуска настройки источника по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-248">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="bb3e9-249">Чтобы позволить организации использовать общедоступные источника, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-249">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="bb3e9-250">Чтобы позволить организации использовать частные источника, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-250">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="bb3e9-251">Дополнительные сведения об этомлете см. в подстроке [Set-SPOTenantCdnEnabled.](https://technet.microsoft.com/library/mt790765.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-251">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

<span data-ttu-id="bb3e9-252"><a name="Office365CDNforSPOFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-252"><a name="Office365CDNforSPOFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="bb3e9-253">Изменение списка типов файлов для включаемой в CDN Office 365 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-253">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="bb3e9-254">При определении типов файлов с помощью **cmdlet Set-SPOTenantCdnPolicy** переопределяется текущий список.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-254">When you define file types by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="bb3e9-255">Если вы хотите добавить в список дополнительные типы файлов, сначала используйте этот cmdlet, чтобы узнать, какие типы файлов уже разрешены, и включите их в список вместе с новыми.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-255">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="bb3e9-256">С помощью **cmdlet Set-SPOTenantCdnPolicy** определите статические типы файлов, которые могут быть установлены общедоступными и частными источниками в CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-256">Use the **Set-SPOTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="bb3e9-257">По умолчанию разрешены общие типы активов, например CSS, GIF, JPG и JS.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-257">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="bb3e9-258">В Windows PowerShell sharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-258">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="bb3e9-259">Например, чтобы включить CDN для хост-файлов CSS и PNG, необходимо ввести команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-259">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="bb3e9-260">Чтобы узнать, какие типы файлов в настоящее время разрешены CDN, используйте **cmdlet Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-260">To see what file types are currently allowed by the CDN, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="bb3e9-261">Дополнительные сведения об этих cmdlets см. в [настройках Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) и [Get-SPOTenantCdnPolicies.](https://technet.microsoft.com/library/mt800838.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-261">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="bb3e9-262"><a name="Office365CDNforSPOSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-262"><a name="Office365CDNforSPOSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="bb3e9-263">Изменение списка классификаций сайтов, которые необходимо исключить из сети CDN Office 365 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-263">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="bb3e9-264">При исключении классификаций сайтов с помощью **cmdlet Set-SPOTenantCdnPolicy** переопределяется текущий определенный список.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-264">When you exclude site classifications by using the **Set-SPOTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="bb3e9-265">Если вы хотите исключить дополнительные классификации сайтов, сначала используйте его, чтобы узнать, какие классификации уже исключены, а затем добавьте их вместе с новыми.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-265">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="bb3e9-266">Чтобы исключить классификации сайтов, которые не должны быть доступны в сети CDN, используйте командлет **Set-SPOTenantCdnPolicy**.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-266">Use the **Set-SPOTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="bb3e9-267">По умолчанию не исключаются никакие классификации сайтов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-267">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="bb3e9-268">В Windows PowerShell sharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-268">In Windows PowerShell for SharePoint Online:</span></span>

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

<span data-ttu-id="bb3e9-269">Чтобы узнать, какие классификации сайтов в настоящее время ограничены, используйте **cmdlet Get-SPOTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-269">To see what site classifications are currently restricted, use the **Get-SPOTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="bb3e9-270">Будут возвращены следующие _свойства: IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ и _ExcludeIfNoScriptDisabled._</span><span class="sxs-lookup"><span data-stu-id="bb3e9-270">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="bb3e9-271">Свойство _IncludeFileExtensions_ содержит список расширений файлов, которые будут обслуживаться из CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-271">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e9-272">Расширения файлов по умолчанию отличаются между общедоступными и частными.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-272">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="bb3e9-273">Свойство _ExcludeRestrictedSiteClassifications_ содержит классификации сайтов, которые необходимо исключить из CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-273">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="bb3e9-274">Например, можно исключить сайты, помеченные как конфиденциальные, чтобы контент сайтов с примененной классификацией не обслуживался из сети CDN. </span><span class="sxs-lookup"><span data-stu-id="bb3e9-274">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="bb3e9-275">Свойство _ExcludeIfNoScriptDisabled_ исключает контент из СЕТИ CDN на основе параметров атрибута _NoScript_ на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-275">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="bb3e9-276">По умолчанию атрибут _NoScript_ имеет значение **Enabled** _для_ современных сайтов и **Disabled для** _классических_ сайтов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-276">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="bb3e9-277">Это зависит от параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-277">This depends on your tenant settings.</span></span>

<span data-ttu-id="bb3e9-278">Дополнительные сведения об этих cmdlets см. в [настройках Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) и [Get-SPOTenantCdnPolicies.](https://technet.microsoft.com/library/mt800838.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-278">For more information about these cmdlets, see [Set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) and [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).</span></span>

<span data-ttu-id="bb3e9-279"><a name="Office365CDNforSPOOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-279"><a name="Office365CDNforSPOOriginPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="bb3e9-280">Добавление источника для активов</span><span class="sxs-lookup"><span data-stu-id="bb3e9-280">Add an origin for your assets</span></span>

<span data-ttu-id="bb3e9-281">Чтобы определить источник, используйте **cmdlet Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-281">Use the **Add-SPOTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="bb3e9-282">Вы можете определить несколько источников.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-282">You can define multiple origins.</span></span> <span data-ttu-id="bb3e9-283">Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-283">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bb3e9-284">Никогда не следует разместить ресурсы, которые содержат сведения о пользователе или считаются конфиденциальными для вашей организации, в общедоступных источниках.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-284">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="bb3e9-285">Значение пути _— это_ относительный путь к библиотеке или папке, в которую входят активы.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-285">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="bb3e9-286">Помимо относительных путей, можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-286">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="bb3e9-287">В источниках поддерживаются поддиапцы в начале URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-287">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="bb3e9-288">Это позволяет создавать источника, охватывающие несколько сайтов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-288">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="bb3e9-289">Например, чтобы включить все ресурсы в папку masterpages для всех сайтов в качестве общего источника в сети CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-289">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="bb3e9-290">Модификатор с подданными знаками \* можно использовать только в начале пути и будет соответствовать всем сегментам URL-адресов по **/** указанному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-290">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="bb3e9-291">Путь может указать на библиотеку документов, папку или сайт.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-291">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="bb3e9-292">Например, путь _\*/site1_ будет соответствовать всем библиотекам документов на сайте.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-292">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="bb3e9-293">Вы можете добавить источник с определенным относительным путем.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-293">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="bb3e9-294">Нельзя добавить источник с использованием полного пути.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-294">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="bb3e9-295">В этом примере добавляется частный источник библиотеки siteassets на определенном сайте:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-295">This example adds a private origin of the siteassets library on a specific site:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="bb3e9-296">В этом примере добавляется частный источник папки _folder1_ в библиотеке активов сайта этого сайта:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-296">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="bb3e9-297">Если путь имеет пробел, его можно либо заместить двойными кавычками, либо заменить пробел кодировка URL-адреса %20.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-297">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="bb3e9-298">В следующих примерах добавляется частный источник папки _1_ в библиотеке активов сайта этого веб-сайта:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-298">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="bb3e9-299">Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-299">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e9-300">В частных источниках для доступа к активам из источника должна быть опубликована основная версия.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-300">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="bb3e9-301">После запуска команды система синхронизирует конфигурацию между центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-301">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bb3e9-302">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-302">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bb3e9-303"><a name="ExamplePublicOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-303"><a name="ExamplePublicOrigin"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="bb3e9-304">Пример. Настройка общего источника для этастерных страниц и библиотеки стилей для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-304">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="bb3e9-305">Как правило, эти источника задаются для вас по умолчанию при в том случае, если вы включаете CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-305">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="bb3e9-306">Однако если вы хотите включить их вручную, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-306">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="bb3e9-307">Чтобы определить библиотеку стилей как общедоступный источник, используйте cmdlet **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-307">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="bb3e9-308">Чтобы определить эталонные страницы в качестве общедоступных, используйте для этого cmdlet **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-308">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="bb3e9-309">Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-309">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="bb3e9-310">После запуска команды система синхронизирует конфигурацию между центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-310">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bb3e9-311">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-311">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bb3e9-312"><a name="ExamplePrivateOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-312"><a name="ExamplePrivateOrigin"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="bb3e9-313">Пример. Настройка частного источника для ресурсов сайта, страниц сайта и изображений публикации для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-313">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="bb3e9-314">Чтобы определить папку ресурсов сайта как частный источник, используйте для этого cmdlet **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-314">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="bb3e9-315">Чтобы определить папку страниц сайта как частный источник, используйте для этого cmdlet **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-315">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="bb3e9-316">Чтобы определить папку опубликованных изображений как частный источник, используйте для определения папки изображений публикации с помощью cmdlet **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-316">Use the **Add-SPOTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="bb3e9-317">Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-317">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>

<span data-ttu-id="bb3e9-318">После запуска команды система синхронизирует конфигурацию между центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-318">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bb3e9-319">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-319">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bb3e9-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-320"><a name="ExamplePrivateOriginSiteCollection"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="bb3e9-321">Пример. Настройка частного источника для коллекции веб-сайтов для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-321">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="bb3e9-322">Чтобы определить коллекцию веб-сайтов как частный источник, используйте для этого cmdlet **Add-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-322">Use the **Add-SPOTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="bb3e9-323">Пример:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-323">For example:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="bb3e9-324">Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790772.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-324">For more information about this command and its syntax, see [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).</span></span>
  
<span data-ttu-id="bb3e9-325">После запуска команды система синхронизирует конфигурацию между центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-325">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bb3e9-326">Вы можете увидеть _ожидающих_ сообщений о конфигурации, которые ожидаются по мере подключения клиента SharePoint Online к службе CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-326">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="bb3e9-327">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-327">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bb3e9-328"><a name="CDNManage"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-328"><a name="CDNManage"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="bb3e9-329">Управление CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-329">Manage the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-330">Настроив CDN, вы можете внести изменения в конфигурацию при обновлении содержимого или изменении потребностей, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-330">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="bb3e9-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-331"><a name="Office365CDNforSPOaddremoveasset"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="bb3e9-332">Добавление, обновление и удаление ресурсов из CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-332">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-333">После завершения действий по настройке можно добавлять новые активы, а также обновлять или удалять существующие активы, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-333">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="bb3e9-334">Просто внести изменения в ресурсы в папке или библиотеке SharePoint, которые вы определили как источник.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-334">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="bb3e9-335">При добавлении нового актива он сразу же будет доступен через CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-335">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="bb3e9-336">Однако при обновлении актива распространение новой копии и ее распространение в CDN займет до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-336">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="bb3e9-337">Если вам нужно получить расположение источника, можно использовать **cmdlet Get-SPOTenantCdnOrigins.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-337">If you need to retrieve the location of the origin, you can use the **Get-SPOTenantCdnOrigins** cmdlet.</span></span> <span data-ttu-id="bb3e9-338">Сведения об использовании этого cmdlet см. в сведениях [о get-SPOTenantCdnOrigins.](https://technet.microsoft.com/library/mt790770.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-338">For information on how to use this cmdlet, see [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx).</span></span>

<span data-ttu-id="bb3e9-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-339"><a name="Office365CDNforSPORemoveOriginPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="bb3e9-340">Удаление источника из CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-340">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-341">Можно удалить доступ к папке или библиотеке SharePoint, которые определены как источник.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-341">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="bb3e9-342">Для этого используйте cmdlet **Remove-SPOTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-342">To do this, use the **Remove-SPOTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="bb3e9-343">Сведения об использовании этого cmdlet см. в [remove-SPOTenantCdnOrigin.](https://technet.microsoft.com/library/mt790761.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-343">For information on how to use this cmdlet, see [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).</span></span>

<span data-ttu-id="bb3e9-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-344"><a name="Office365CDNforSPOModifyOrigin"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="bb3e9-345">Изменение источника в CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-345">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-346">Вы не можете изменить созданный источник.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-346">You cannot modify an origin you've created.</span></span> <span data-ttu-id="bb3e9-347">Вместо этого удалите источник и добавьте новый.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-347">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="bb3e9-348">Дополнительные сведения см. в сведениях о том, как удалить источник из [CDN Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) и добавить источник [ресурсов.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-348">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).</span></span>

<span data-ttu-id="bb3e9-349"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-349"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="bb3e9-350">Отключение CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-350">Disable the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-351">Используйте для отключения CDN для организации с помощью **cmdlet Set-SPOTenantCdnEnabled.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-351">Use the **Set-SPOTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="bb3e9-352">Если для CDN включены как общедоступные, так и частные источника, необходимо выполнить его дважды, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-352">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="bb3e9-353">Чтобы отключить использование общедоступных источника в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-353">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="bb3e9-354">Чтобы отключить использование частных источника в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-354">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="bb3e9-355">Дополнительные сведения об этомлете см. в подстроке [Set-SPOTenantCdnEnabled.](https://technet.microsoft.com/library/mt790765.aspx)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-355">For more information about this cmdlet, see [Set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).</span></span>

</details>

<span data-ttu-id="bb3e9-356"><a name="CDNSetupinPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-356"><a name="CDNSetupinPnPPosh"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a><span data-ttu-id="bb3e9-357">Настройка и настройка CDN Office 365 с помощью PnP PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb3e9-357">Set up and configure the Office 365 CDN by using PnP PowerShell</span></span>

<span data-ttu-id="bb3e9-358">В процедурах этого раздела для подключения к SharePoint Online необходимо использовать PnP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-358">The procedures in this section require you to use PnP PowerShell to connect to SharePoint Online.</span></span> <span data-ttu-id="bb3e9-359">Инструкции см. в [инструкциях по началу работы с PnP PowerShell.](https://github.com/SharePoint/PnP-PowerShell#getting-started)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-359">For instructions, see [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).</span></span>

<span data-ttu-id="bb3e9-360">Выполните указанные здесь действия, чтобы настроить сеть CDN для работы с активами в SharePoint Online с помощью PnP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-360">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using PnP PowerShell.</span></span>

<details>
  <summary><span data-ttu-id="bb3e9-361">Щелкните, чтобы развернуть</span><span class="sxs-lookup"><span data-stu-id="bb3e9-361">Click to expand</span></span></summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a><span data-ttu-id="bb3e9-362">Включить в организации использование CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-362">Enable your organization to use the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-363">Перед внесением изменений в параметры сети CDN клиента необходимо получить текущее состояние конфигурации частной сети CDN в клиенте Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-363">Before you make changes to the tenant CDN settings, you should retrieve the current status of the private CDN configuration in your Office 365 tenant.</span></span> <span data-ttu-id="bb3e9-364">Подключите клиент с помощью PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-364">Connect to your tenant using PnP PowerShell:</span></span>

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

<span data-ttu-id="bb3e9-365">Теперь с помощью **get-PnPTenantCdnEnabled** извлекает параметры состояния CDN из клиента:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-365">Now use the **Get-PnPTenantCdnEnabled** cmdlet to retrieve the CDN status settings from the tenant:</span></span>

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

<span data-ttu-id="bb3e9-366">Состояние CDN для указанного CdnType будет выводит на экран.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-366">The status of the CDN for the specified CdnType will output to the screen.</span></span>

<span data-ttu-id="bb3e9-367">Используйте для организации использование CDN Office 365 с помощьюлета **Set-PnPTenantCdnEnabled.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-367">Use the **Set-PnPTenantCdnEnabled** cmdlet to enable your organization to use the Office 365 CDN.</span></span> <span data-ttu-id="bb3e9-368">Вы можете позволить организации одновременно использовать общедоступные, частные или оба источника.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-368">You can enable your organization to use public origins, private origins, or both at at the same time.</span></span> <span data-ttu-id="bb3e9-369">Кроме того, можно настроить CDN так, чтобы она пропускала установку источника по умолчанию при ее в сети.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-369">You can also configure the CDN to skip the setup of default origins when you enable it.</span></span> <span data-ttu-id="bb3e9-370">Вы всегда можете добавить эти источника позже, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-370">You can always add these origins later as described in this topic.</span></span>
  
<span data-ttu-id="bb3e9-371">В PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-371">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

<span data-ttu-id="bb3e9-372">Например, чтобы позволить организации использовать как общедоступные, так и частные источника, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-372">For example, to enable your organization to use both public and private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="bb3e9-373">Чтобы позволить организации использовать как общедоступные, так и частные источника, но пропустить настройку источника по умолчанию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-373">To enable your organization to use both public and private origins but skip setting up the default origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

<span data-ttu-id="bb3e9-374">В [источниках CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) по умолчанию вы можете получить сведения об источниках, которые по умолчанию одежные при в сети CDN Office 365, а также о возможном влиянии пропуска настройки источника по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-374">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN, and the potential impact of skipping the setup of default origins.</span></span>

<span data-ttu-id="bb3e9-375">Чтобы позволить организации использовать общедоступные источника, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-375">To enable your organization to use public origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

<span data-ttu-id="bb3e9-376">Чтобы позволить организации использовать частные источника, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-376">To enable your organization to use private origins, type the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

<span data-ttu-id="bb3e9-377">Дополнительные сведения об этомлете см. в подстроке [Set-PnPTenantCdnEnabled.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-377">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

<span data-ttu-id="bb3e9-378"><a name="Office365CDNforPnPPoshFileType"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-378"><a name="Office365CDNforPnPPoshFileType"> </a></span></span>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a><span data-ttu-id="bb3e9-379">Изменение списка типов файлов для включаемой в CDN Office 365 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-379">Change the list of file types to include in the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="bb3e9-380">При определении типов файлов с помощью **cmdlet Set-PnPTenantCdnPolicy** переопределяется текущий список.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-380">When you define file types by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="bb3e9-381">Если вы хотите добавить в список дополнительные типы файлов, сначала используйте этот cmdlet, чтобы узнать, какие типы файлов уже разрешены, и включите их в список вместе с новыми.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-381">If you want to add additional file types to the list, use the cmdlet first to find out what file types are already allowed and include them in the list along with your new ones.</span></span>
  
<span data-ttu-id="bb3e9-382">С помощью **cmdlet Set-PnPTenantCdnPolicy** определите статические типы файлов, которые могут быть установлены общедоступными и частными источниками в CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-382">Use the **Set-PnPTenantCdnPolicy** cmdlet to define static file types that can be hosted by public and private origins in the CDN.</span></span> <span data-ttu-id="bb3e9-383">По умолчанию разрешены общие типы активов, например CSS, GIF, JPG и JS.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-383">By default, common asset types are allowed, for example .css, .gif, .jpg, and .js.</span></span>

<span data-ttu-id="bb3e9-384">В PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-384">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

<span data-ttu-id="bb3e9-385">Например, чтобы включить CDN для хост-файлов CSS и PNG, необходимо ввести команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-385">For example, to enable the CDN to host .css and .png files, you would enter the command:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

<span data-ttu-id="bb3e9-386">Чтобы узнать, какие типы файлов в настоящее время разрешены CDN, используйте **cmdlet Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-386">To see what file types are currently allowed by the CDN, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="bb3e9-387">Дополнительные сведения об этих cmdlets см. в [настройках Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) и [Get-PnPTenantCdnPolicies.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-387">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="bb3e9-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-388"><a name="Office365CDNforPnPPoshSiteClassification"> </a></span></span>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a><span data-ttu-id="bb3e9-389">Изменение списка классификаций сайтов, которые необходимо исключить из сети CDN Office 365 (необязательно)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-389">Change the list of site classifications you want to exclude from the Office 365 CDN (Optional)</span></span>

> [!TIP]
> <span data-ttu-id="bb3e9-390">При исключении классификаций сайтов с помощью **cmdlet Set-PnPTenantCdnPolicy** переопределяется текущий определенный список.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-390">When you exclude site classifications by using the **Set-PnPTenantCdnPolicy** cmdlet, you overwrite the currently defined list.</span></span> <span data-ttu-id="bb3e9-391">Если вы хотите исключить дополнительные классификации сайтов, сначала используйте его, чтобы узнать, какие классификации уже исключены, а затем добавьте их вместе с новыми.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-391">If you want to exclude additional site classifications, use the cmdlet first to find out what classifications are already excluded and then add them along with your new ones.</span></span>

<span data-ttu-id="bb3e9-392">Чтобы **исключить** классификации сайтов, которые не требуется делать доступными через CDN, используйте для исключения классификаций сайтов, которые не должны быть доступны через CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-392">Use the **Set-PnPTenantCdnPolicy** cmdlet to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="bb3e9-393">По умолчанию не исключаются никакие классификации сайтов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-393">By default, no site classifications are excluded.</span></span>

<span data-ttu-id="bb3e9-394">В PnP PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-394">In PnP PowerShell:</span></span>

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

<span data-ttu-id="bb3e9-395">Чтобы узнать, какие классификации сайтов в настоящее время ограничены, используйте **cmdlet Get-PnPTenantCdnPolicies:**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-395">To see what site classifications are currently restricted, use the **Get-PnPTenantCdnPolicies** cmdlet:</span></span>

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

<span data-ttu-id="bb3e9-396">Будут возвращены следующие _свойства: IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ и _ExcludeIfNoScriptDisabled._</span><span class="sxs-lookup"><span data-stu-id="bb3e9-396">The properties that will be returned are _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ and _ExcludeIfNoScriptDisabled_.</span></span>

<span data-ttu-id="bb3e9-397">Свойство _IncludeFileExtensions_ содержит список расширений файлов, которые будут обслуживаться из CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-397">The _IncludeFileExtensions_ property contains the list of file extensions that will be served from the CDN.</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e9-398">Расширения файлов по умолчанию отличаются между общедоступными и частными.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-398">The default file extensions are different between public and private.</span></span>

<span data-ttu-id="bb3e9-399">Свойство _ExcludeRestrictedSiteClassifications_ содержит классификации сайтов, которые необходимо исключить из CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-399">The _ExcludeRestrictedSiteClassifications_ property contains the site classifications that you want to exclude from the CDN.</span></span> <span data-ttu-id="bb3e9-400">Например, можно исключить сайты, помеченные как конфиденциальные, чтобы контент сайтов с примененной классификацией не обслуживался из сети CDN. </span><span class="sxs-lookup"><span data-stu-id="bb3e9-400">For example, you can exclude sites marked as **Confidential** so content from sites with that classification applied will not be served from the CDN.</span></span>

<span data-ttu-id="bb3e9-401">Свойство _ExcludeIfNoScriptDisabled_ исключает контент из СЕТИ CDN на основе параметров атрибута _NoScript_ на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-401">The _ExcludeIfNoScriptDisabled_ property excludes content from the CDN based on the site-level _NoScript_ attribute settings.</span></span> <span data-ttu-id="bb3e9-402">По умолчанию атрибут _NoScript_ имеет значение **Enabled** _для_ современных сайтов и **Disabled для** _классических_ сайтов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-402">By default, the _NoScript_ attribute is set to **Enabled** for _Modern_ sites and **Disabled** for _Classic_ sites.</span></span> <span data-ttu-id="bb3e9-403">Это зависит от параметров клиента.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-403">This depends on your tenant settings.</span></span>

<span data-ttu-id="bb3e9-404">Дополнительные сведения об этих cmdlets см. в [настройках Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) и [Get-PnPTenantCdnPolicies.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-404">For more information about these cmdlets, see [Set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).</span></span>

<span data-ttu-id="bb3e9-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-405"><a name="Office365CDNforSPOOriginPnPPosh"> </a></span></span>
### <a name="add-an-origin-for-your-assets"></a><span data-ttu-id="bb3e9-406">Добавление источника для активов</span><span class="sxs-lookup"><span data-stu-id="bb3e9-406">Add an origin for your assets</span></span>

<span data-ttu-id="bb3e9-407">Чтобы определить источник, используйте **cmdlet Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-407">Use the **Add-PnPTenantCdnOrigin** cmdlet to define an origin.</span></span> <span data-ttu-id="bb3e9-408">Вы можете определить несколько источников.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-408">You can define multiple origins.</span></span> <span data-ttu-id="bb3e9-409">Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-409">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bb3e9-410">Никогда не следует разместить ресурсы, которые содержат сведения о пользователе или считаются конфиденциальными для вашей организации, в общедоступных источниках.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-410">You should never place resources that contain user information or are considered sensitive to your organization in a public origin.</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

<span data-ttu-id="bb3e9-411">Значение пути _— это_ относительный путь к библиотеке или папке, в которую входят активы.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-411">The value of _path_ is the relative path to the library or folder that contains the assets.</span></span> <span data-ttu-id="bb3e9-412">Помимо относительных путей, можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-412">You can use wildcards in addition to relative paths.</span></span> <span data-ttu-id="bb3e9-413">В источниках поддерживаются поддиапцы в начале URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-413">Origins support wildcards prepended to the URL.</span></span> <span data-ttu-id="bb3e9-414">Это позволяет создавать источника, охватывающие несколько сайтов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-414">This allows you to create origins that span multiple sites.</span></span> <span data-ttu-id="bb3e9-415">Например, чтобы включить все ресурсы в папку masterpages для всех сайтов в качестве общего источника в сети CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-415">For example, to include all of the assets in the masterpages folder for all of your sites as a public origin within the CDN, type the following command:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ <span data-ttu-id="bb3e9-416">Модификатор с подданными знаками \* можно использовать только в начале пути и будет соответствовать всем сегментам URL-адресов по **/** указанному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-416">The wildcard modifier \***/** can only be used at the beginning of the path, and will match all URL segments under the specified URL.</span></span>
+ <span data-ttu-id="bb3e9-417">Путь может указать на библиотеку документов, папку или сайт.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-417">The path can point to a document library, folder or site.</span></span> <span data-ttu-id="bb3e9-418">Например, путь _\*/site1_ будет соответствовать всем библиотекам документов на сайте.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-418">For example, the path _\*/site1_ will match all the document libraries under the site.</span></span>

<span data-ttu-id="bb3e9-419">Вы можете добавить источник с определенным относительным путем.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-419">You can add an origin with a specific relative path.</span></span> <span data-ttu-id="bb3e9-420">Нельзя добавить источник с использованием полного пути.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-420">You cannot add an origin using the full path.</span></span>

<span data-ttu-id="bb3e9-421">В этом примере добавляется частный источник библиотеки активов сайта на определенном сайте:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-421">This example adds a private origin of the site assets library on a specific site:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="bb3e9-422">В этом примере добавляется частный источник папки _folder1_ в библиотеке активов сайта этого сайта:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-422">This example adds a private origin of the _folder1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

<span data-ttu-id="bb3e9-423">Если путь имеет пробел, его можно либо заместить двойными кавычками, либо заменить пробел кодировка URL-адреса %20.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-423">If there is a space in the path, you can either surround the path in double quotes or replace the space with the URL encoding %20.</span></span> <span data-ttu-id="bb3e9-424">В следующих примерах добавляется частный источник папки _1_ в библиотеке активов сайта этого веб-сайта:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-424">The following examples add a private origin of the _folder 1_ folder in the site collection's site assets library:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

<span data-ttu-id="bb3e9-425">Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-425">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e9-426">В частных источниках для доступа к активам из источника должна быть опубликована основная версия.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-426">In private origins, assets being shared from an origin must have a major version published before they can be accessed from the CDN.</span></span>
  
<span data-ttu-id="bb3e9-427">После запуска команды система синхронизирует конфигурацию между центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-427">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bb3e9-428">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-428">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bb3e9-429"><a name="ExamplePublicOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-429"><a name="ExamplePublicOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a><span data-ttu-id="bb3e9-430">Пример. Настройка общего источника для этастерных страниц и библиотеки стилей для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-430">Example: Configure a public origin for your master pages and for your style library for SharePoint Online</span></span>

<span data-ttu-id="bb3e9-431">Как правило, эти источника задаются для вас по умолчанию при в том случае, если вы включаете CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-431">Normally, these origins are set up for you by default when you enable the Office 365 CDN.</span></span> <span data-ttu-id="bb3e9-432">Однако если вы хотите включить их вручную, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-432">However, if you want to enable them manually, follow these steps.</span></span>
  
+ <span data-ttu-id="bb3e9-433">Чтобы определить библиотеку стилей как общедоступный источник, используйте для этого cmdlet **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-433">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the style library as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ <span data-ttu-id="bb3e9-434">Используйте для определения эталонных страниц в качестве общедоступных источника с помощью **cmdlet Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-434">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the master pages as a public origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

<span data-ttu-id="bb3e9-435">Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-435">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="bb3e9-436">После запуска команды система синхронизирует конфигурацию между центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-436">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bb3e9-437">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-437">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bb3e9-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-438"><a name="ExamplePrivateOriginPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a><span data-ttu-id="bb3e9-439">Пример. Настройка частного источника для ресурсов сайта, страниц сайта и изображений публикации для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-439">Example: Configure a private origin for your site assets, site pages, and publishing images for SharePoint Online</span></span>

+ <span data-ttu-id="bb3e9-440">Чтобы определить папку ресурсов сайта как частный источник, используйте для этого cmdlet **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-440">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site assets folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ <span data-ttu-id="bb3e9-441">Чтобы определить папку страниц сайта в качестве частного источника, используйте **cmdlet Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-441">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the site pages folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ <span data-ttu-id="bb3e9-442">Чтобы определить папку изображений публикации как частный источник, используйте для этого cmdlet **Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-442">Use the **Add-PnPTenantCdnOrigin** cmdlet to define the publishing images folder as a private origin.</span></span>

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

<span data-ttu-id="bb3e9-443">Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-443">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>

<span data-ttu-id="bb3e9-444">После запуска команды система синхронизирует конфигурацию между центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-444">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bb3e9-445">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-445">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bb3e9-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-446"><a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a></span></span>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a><span data-ttu-id="bb3e9-447">Пример. Настройка частного источника для коллекции веб-сайтов для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-447">Example: Configure a private origin for a site collection for SharePoint Online</span></span>

<span data-ttu-id="bb3e9-448">Чтобы определить коллекцию веб-сайтов как частный источник, используйте для этого **cmdlet Add-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-448">Use the **Add-PnPTenantCdnOrigin** cmdlet to define a site collection as a private origin.</span></span> <span data-ttu-id="bb3e9-449">Пример:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-449">For example:</span></span>

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

<span data-ttu-id="bb3e9-450">Дополнительные сведения об этой команде и ее синтаксис см. в под названием [Add-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-450">For more information about this command and its syntax, see [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).</span></span>
  
<span data-ttu-id="bb3e9-451">После запуска команды система синхронизирует конфигурацию между центрами обработки данных.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-451">Once you've run the command, the system synchronizes the configuration across the datacenter.</span></span> <span data-ttu-id="bb3e9-452">Вы можете увидеть _ожидающих_ сообщений о конфигурации, которые ожидаются по мере подключения клиента SharePoint Online к службе CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-452">You may see a _Configuration pending_ message which is expected as the SharePoint Online tenant connects to the CDN service.</span></span> <span data-ttu-id="bb3e9-453">Это может занять до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-453">This can take up to 15 minutes.</span></span>

<span data-ttu-id="bb3e9-454"><a name="CDNManagePnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-454"><a name="CDNManagePnPPosh"> </a></span></span>
### <a name="manage-the-office-365-cdn"></a><span data-ttu-id="bb3e9-455">Управление CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-455">Manage the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-456">Настроив CDN, вы можете внести изменения в конфигурацию при обновлении содержимого или изменении потребностей, как описано в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-456">Once you've set up the CDN, you can make changes to your configuration as you update content or as your needs change, as described in this section.</span></span>
  
<span data-ttu-id="bb3e9-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-457"><a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a></span></span>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a><span data-ttu-id="bb3e9-458">Добавление, обновление и удаление ресурсов из CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-458">Add, update, or remove assets from the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-459">После завершения действий по настройке можно добавлять новые активы, а также обновлять или удалять существующие активы, когда это необходимо.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-459">Once you've completed the setup steps, you can add new assets, and update or remove existing assets whenever you want.</span></span> <span data-ttu-id="bb3e9-460">Просто внести изменения в ресурсы в папке или библиотеке SharePoint, которые вы определили как источник.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-460">Just make your changes to the assets in the folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="bb3e9-461">При добавлении нового актива он сразу же будет доступен через CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-461">If you add a new asset, it is available through the CDN immediately.</span></span> <span data-ttu-id="bb3e9-462">Однако при обновлении актива распространение новой копии и ее распространение в CDN займет до 15 минут.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-462">However, if you update the asset, it will take up to 15 minutes for the new copy to propagate and become available in the CDN.</span></span>
  
<span data-ttu-id="bb3e9-463">Если вам нужно получить расположение источника, можно использовать **cmdlet Get-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-463">If you need to retrieve the location of the origin, you can use the **Get-PnPTenantCdnOrigin** cmdlet.</span></span> <span data-ttu-id="bb3e9-464">Сведения об использовании этого cmdlet см. в подтипе [Get-PnPTenantCdnOrigin.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-464">For information on how to use this cmdlet, see [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).</span></span>

<span data-ttu-id="bb3e9-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-465"><a name="Office365CDNforSPORemoveOriginPnPPosh"> </a></span></span>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a><span data-ttu-id="bb3e9-466">Удаление источника из CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-466">Remove an origin from the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-467">Можно удалить доступ к папке или библиотеке SharePoint, которые определены как источник.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-467">You can remove access to a folder or SharePoint library that you identified as an origin.</span></span> <span data-ttu-id="bb3e9-468">Для этого используйте **cmdlet Remove-PnPTenantCdnOrigin.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-468">To do this, use the **Remove-PnPTenantCdnOrigin** cmdlet.</span></span>

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

<span data-ttu-id="bb3e9-469">Сведения о том, как использовать этот cmdlet, см. в [remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-469">For information on how to use this cmdlet, see [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).</span></span>

<span data-ttu-id="bb3e9-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-470"><a name="Office365CDNforSPOModifyOriginPnPPosh"> </a></span></span>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a><span data-ttu-id="bb3e9-471">Изменение источника в CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-471">Modify an origin in the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-472">Вы не можете изменить созданный источник.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-472">You cannot modify an origin you've created.</span></span> <span data-ttu-id="bb3e9-473">Вместо этого удалите источник и добавьте новый.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-473">Instead, remove the origin and then add a new one.</span></span> <span data-ttu-id="bb3e9-474">Дополнительные сведения см. в сведениях о том, как удалить источник из [CDN Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) и добавить источник [ресурсов.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-474">For more information, see [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and [To add an origin for your assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).</span></span>

<span data-ttu-id="bb3e9-475"><a name="Office365CDNforSPODisable"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-475"><a name="Office365CDNforSPODisable"> </a></span></span>
#### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="bb3e9-476">Отключение CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-476">Disable the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-477">Используйте для отключения CDN для организации с помощью **cmdlet Set-PnPTenantCdnEnabled.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-477">Use the **Set-PnPTenantCdnEnabled** cmdlet to disable the CDN for your organization.</span></span> <span data-ttu-id="bb3e9-478">Если для CDN включены как общедоступные, так и частные источника, необходимо выполнить его дважды, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-478">If you have both the public and private origins enabled for the CDN, you need to run the cmdlet twice as shown in the following examples.</span></span>
  
<span data-ttu-id="bb3e9-479">Чтобы отключить использование общедоступных источника в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-479">To disable use of public origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

<span data-ttu-id="bb3e9-480">Чтобы отключить использование частных источника в CDN, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-480">To disable use of the private origins in the CDN, enter the following command:</span></span>

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

<span data-ttu-id="bb3e9-481">Дополнительные сведения об этомлете см. в подстроке [Set-PnPTenantCdnEnabled.](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-481">For more information about this cmdlet, see [Set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).</span></span>

</details>

<span data-ttu-id="bb3e9-482"><a name="CDNSetupinCLI"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-482"><a name="CDNSetupinCLI"> </a></span></span>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a><span data-ttu-id="bb3e9-483">Установка и настройка сети CDN Office 365 с помощью интерфейса командной строки Office 365:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-483">Set up and configure the Office 365 CDN using the Office 365 CLI</span></span>

<span data-ttu-id="bb3e9-484">Для процедур в этом разделе необходимо установить [Office 365 CLI.](https://aka.ms/o365cli)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-484">The procedures in this section require that you have installed the [Office 365 CLI](https://aka.ms/o365cli).</span></span> <span data-ttu-id="bb3e9-485">Затем подключите клиент Office 365 с помощью команды [входа.](https://pnp.github.io/office365-cli/cmd/login/)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-485">Next, connect to your Office 365 tenant using the [login](https://pnp.github.io/office365-cli/cmd/login/) command.</span></span>

<span data-ttu-id="bb3e9-486">Выполните указанные действия, чтобы настроить сеть CDN для работы с активами в SharePoint Online с помощью Office 365 CLI.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-486">Complete these steps to set up and configure the CDN to host your assets in SharePoint Online using the Office 365 CLI.</span></span>

<details>
  <summary><span data-ttu-id="bb3e9-487">Щелкните, чтобы развернуть</span><span class="sxs-lookup"><span data-stu-id="bb3e9-487">Click to expand</span></span></summary>

### <a name="enable-the-office-365-cdn"></a><span data-ttu-id="bb3e9-488">Включить CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-488">Enable the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-489">Вы можете управлять состоянием сети CDN Office 365 в клиенте с помощью команды [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-489">You can manage the state of the Office 365 CDN in your tenant using the [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) command.</span></span>

<span data-ttu-id="bb3e9-490">Чтобы включить в клиенте общедоступную сеть CDN Office 365, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-490">To enable the Office 365 Public CDN in your tenant execute:</span></span>

```sh
spo cdn set --type Public --enabled true
```

<span data-ttu-id="bb3e9-491">Чтобы включить CDN Office 365 SharePoint, выполните 3:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-491">To enable the Office 365 SharePoint CDN, execute:</span></span>

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a><span data-ttu-id="bb3e9-492">Просмотр текущего состояния сети CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-492">View the current status of the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-493">Чтобы проверить, включен ли определенный тип CDN Office 365, используйте команду [получения spo cdn.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-493">To check if the particular type of Office 365 CDN is enabled or disabled, use the [spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) command.</span></span>

<span data-ttu-id="bb3e9-494">Чтобы проверить, включена ли общедоступная сеть CDN Office 365, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-494">To check if the Office 365 Public CDN is enabled, execute:</span></span>

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a><span data-ttu-id="bb3e9-495">Просмотр источника CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-495">View the Office 365 CDN origins</span></span>

<span data-ttu-id="bb3e9-496">Чтобы просмотреть список настроенных в данный момент общедоступных источников CDN Office 365, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-496">To view the currently configured Office 365 Public CDN origins execute:</span></span>

```sh
spo cdn origin list --type Public
```

<span data-ttu-id="bb3e9-497">В [источниках CDN по](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) умолчанию вы можете получить сведения об источниках, которые по умолчанию являются резервами при ветвии CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-497">See [Default CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) for information about the origins that are provisioned by default when you enable the Office 365 CDN.</span></span>

### <a name="add-an-office-365-cdn-origin"></a><span data-ttu-id="bb3e9-498">Добавление источника CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-498">Add an Office 365 CDN origin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb3e9-499">Никогда не следует разместить ресурсы, которые считаются конфиденциальными для вашей организации, в библиотеку документов SharePoint, настроенную как общедоступный источник.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-499">You should never place resources that are considered sensitive to your organization in a SharePoint document library configured as a public origin.</span></span>

<span data-ttu-id="bb3e9-500">Чтобы определить источник CDN, используйте команду [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-500">Use the [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) command to define a CDN origin.</span></span> <span data-ttu-id="bb3e9-501">Вы можете определить несколько источников.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-501">You can define multiple origins.</span></span> <span data-ttu-id="bb3e9-502">Источник — это URL-адрес, указывающий на библиотеку или папку в SharePoint, содержащую ресурсы, которые требуется размещать в сети CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-502">The origin is a URL that points to a SharePoint library or folder that contains the assets that you want to be hosted by the CDN.</span></span>

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

<span data-ttu-id="bb3e9-503">Где `path` находится относительный путь к папке с активами.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-503">Where `path` is the relative path to the folder that contains the assets.</span></span> <span data-ttu-id="bb3e9-504">Помимо относительных путей, можно использовать подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-504">You can use wildcards in addition to relative paths.</span></span>

<span data-ttu-id="bb3e9-505">Чтобы включить все ресурсы в галерею **этастерных страниц** для всех сайтов в качестве общедоступных, выполните следующие реализации:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-505">To include all assets in the **Master Page Gallery** of all sites as a public origin, execute:</span></span>

```sh
spo cdn origin add --type Public --origin */masterpage
```

<span data-ttu-id="bb3e9-506">Чтобы настроить частный источник для определенного семейства веб-сайтов, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-506">To configure a private origin for a specific site collection, execute:</span></span>

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> <span data-ttu-id="bb3e9-507">После добавления источника CDN может понадобиться до 15 минут, чтобы получить файлы через службу CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-507">After adding a CDN origin, it might take up to 15 minutes for you to be able to retrieve files via the CDN service.</span></span> <span data-ttu-id="bb3e9-508">Вы можете проверить, включен ли тот или иной источник, с помощью команды [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-508">You can verify if the particular origin has already been enabled using the [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command.</span></span>

### <a name="remove-an-office-365-cdn-origin"></a><span data-ttu-id="bb3e9-509">Удаление источника CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-509">Remove an Office 365 CDN origin</span></span>

<span data-ttu-id="bb3e9-510">Чтобы удалить источник CDN для указанного типа CDN, используйте команду [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-510">Use the [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) command to remove a CDN origin for the specified CDN type.</span></span>

<span data-ttu-id="bb3e9-511">Чтобы удалить общедоступный источник из конфигурации CDN, выполните ок.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-511">To remove a public origin from the CDN configuration, execute:</span></span>

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> <span data-ttu-id="bb3e9-512">Удаление источника CDN не влияет на файлы, хранимые в любой библиотеке документов, которая соответствует этому источнику.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-512">Removing a CDN origin doesn't affect the files stored in any document library matching that origin.</span></span> <span data-ttu-id="bb3e9-513">Если на эти ресурсы ссылались с помощью URL-адреса SharePoint, SharePoint автоматически вернется к исходному URL-адресу, указывав на библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-513">If these assets have been referenced using their SharePoint URL, SharePoint will automatically switch back to the original URL pointing to the document library.</span></span> <span data-ttu-id="bb3e9-514">Однако если ссылки на ресурсы были указаны с использованием URL-адреса общедоступных CDN, удаление источника разрывает ссылку, и вам потребуется вручную изменить их.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-514">If, however, assets have been referenced using a public CDN URL, then removing the origin will break the link and you will need to manually change them.</span></span>

### <a name="modify-an-office-365-cdn-origin"></a><span data-ttu-id="bb3e9-515">Изменение источника CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-515">Modify an Office 365 CDN origin</span></span>

<span data-ttu-id="bb3e9-516">Изменить имеющийся источник CDN невозможно.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-516">It's not possible to modify an existing CDN origin.</span></span> <span data-ttu-id="bb3e9-517">Вместо этого следует удалить определенный ранее источник CDN с помощью команды `spo cdn origin remove` и добавить новый с помощью команды `spo cdn origin add`.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-517">Instead, you should remove the previously defined CDN origin using the `spo cdn origin remove` command and add a new one using the `spo cdn origin add` command.</span></span>

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a><span data-ttu-id="bb3e9-518">Изменение типов файлов для включаемой в CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-518">Change the types of files to include in the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-519">По умолчанию в CDN включены следующие типы файлов: _CSS, EOT, GIF, ICO, JPEG, JPG, JS, MAP, PNG, SVG, TTF, WOFF и WOFF2._</span><span class="sxs-lookup"><span data-stu-id="bb3e9-519">By default, the following file types are included in the CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff and .woff2_.</span></span> <span data-ttu-id="bb3e9-520">Если требуется включить в сеть CDN дополнительные типы файлов, вы можете изменить конфигурацию CDN с помощью команды [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-520">If you need to include additional file types in the CDN, you can change the CDN configuration using the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command.</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e9-521">При изменении списка типов файлов перезаписывается текущий список.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-521">When changing the list of file types, you overwrite the currently defined list.</span></span> <span data-ttu-id="bb3e9-522">Если требуется включить дополнительные типы файлов, сперва используйте команду [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/), чтобы узнать, какие типы файлов настроены в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-522">If you want to include additional file types, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) command to find out which file types are currently configured.</span></span>

<span data-ttu-id="bb3e9-523">Чтобы добавить _тип файла JSON_ в список типов файлов по умолчанию, включенных в обную CDN, выполните 2.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-523">To add the _JSON_ file type to the default list of file types included in the public CDN, execute:</span></span>

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a><span data-ttu-id="bb3e9-524">Изменение списка классификаций сайтов, которые требуется исключить из сети CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-524">Change the list of site classifications you want to exclude from the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-525">Чтобы исключить классификации сайтов, которые не должны быть доступны в сети CDN, используйте команду [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-525">Use the [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) command to exclude site classifications that you do not want to make available over the CDN.</span></span> <span data-ttu-id="bb3e9-526">По умолчанию не исключаются никакие классификации сайтов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-526">By default, no site classifications are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e9-527">При изменении списка исключаемых классификаций сайтов перезаписывается текущий список.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-527">When changing the list of excluded site classifications, you overwrite the currently defined list.</span></span> <span data-ttu-id="bb3e9-528">Если требуется исключить дополнительные классификации сайтов, сперва используйте команду [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/), чтобы узнать, какие классификации настроены в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-528">If you want to exclude additional classifications, first use the [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) command to find out which classifications are currently configured.</span></span>

<span data-ttu-id="bb3e9-529">Чтобы исключить сайты, классифицированные как _HBI,_ из публичной сети CDN, выполните</span><span class="sxs-lookup"><span data-stu-id="bb3e9-529">To exclude sites classified as _HBI_ from the public CDN, execute</span></span>

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a><span data-ttu-id="bb3e9-530">Отключение CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-530">Disable the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-531">Чтобы отключить сеть CDN Office 365, используйте команду `spo cdn set`. Пример:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-531">To disable the Office 365 CDN use the `spo cdn set` command, for example:</span></span>

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a><span data-ttu-id="bb3e9-532">Использование ресурсов CDN</span><span class="sxs-lookup"><span data-stu-id="bb3e9-532">Using your CDN assets</span></span>

<span data-ttu-id="bb3e9-533">Теперь, когда вы включили CDN и настроили источника и политики, можно приступить к использованию ресурсов CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-533">Now that you have enabled the CDN and configured origins and policies, you can begin using your CDN assets.</span></span>

<span data-ttu-id="bb3e9-534">Этот раздел поможет вам понять, как использовать URL-адреса CDN на страницах и содержимом SharePoint, чтобы SharePoint перенаправляет запросы на ресурсы из общедоступных и частных источниках в CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-534">This section will help you understand how to use CDN URLs in your SharePoint pages and content so that SharePoint redirects requests for assets in both public and private origins to the CDN.</span></span>

+ [<span data-ttu-id="bb3e9-535">Обновление ссылок на ресурсы CDN</span><span class="sxs-lookup"><span data-stu-id="bb3e9-535">Updating links to CDN assets</span></span>](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [<span data-ttu-id="bb3e9-536">Использование ресурсов в общедоступных источниках</span><span class="sxs-lookup"><span data-stu-id="bb3e9-536">Using assets in public origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [<span data-ttu-id="bb3e9-537">Использование ресурсов в частных источниках</span><span class="sxs-lookup"><span data-stu-id="bb3e9-537">Using assets in private origins</span></span>](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

<span data-ttu-id="bb3e9-538">Сведения об использовании СЕТИ CDN для размещения клиентских веб-частей см. в разделе "Размещение клиентской веб-части из сети [CDN Office 365 (Hello World, часть 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)".</span><span class="sxs-lookup"><span data-stu-id="bb3e9-538">For information on how to use the CDN for hosting client-side web parts, see the topic [Host your client-side web part from Office 365 CDN (Hello World part 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e9-539">Если добавить папку _ClientSideAssets_  в частный список источников CDN, пользовательские веб-части, в которые будет добавлена сеть CDN, не будут отрисовки.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-539">If you add the _ClientSideAssets_ folder to the **private** CDN origins list, CDN-hosted custom web parts will fail to render.</span></span> <span data-ttu-id="bb3e9-540">Файлы, используемые веб-частями SPFX, могут использовать только общедоступные сети CDN, а папка ClientSideAssets является источником по умолчанию для общедоступных CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-540">Files used by SPFX web parts can only utilize the public CDN and the ClientSideAssets folder is a default origin for public CDN.</span></span> 

### <a name="updating-links-to-cdn-assets"></a><span data-ttu-id="bb3e9-541">Обновление ссылок на ресурсы CDN</span><span class="sxs-lookup"><span data-stu-id="bb3e9-541">Updating links to CDN assets</span></span>

<span data-ttu-id="bb3e9-542">Чтобы использовать ресурсы, добавленные в источник, необходимо просто обновить ссылки на исходный файл с путем к файлу в источнике.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-542">To use assets that you have added to an origin, you simply update links to the original file with the path to the file in the origin.</span></span>

+ <span data-ttu-id="bb3e9-543">Изменить страницу или контент, содержащий ссылки на ресурсы, добавленные в источник.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-543">Edit the page or content that contains links to assets you have added to an origin.</span></span> <span data-ttu-id="bb3e9-544">Вы также можете использовать один из нескольких методов для глобального поиска и замены ссылок на сайт или введите в коллекцию веб-сайтов, если вы хотите обновить ссылку на заданный актив везде, где она отображается.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-544">You can also use one of several methods to globally search and replace links across an enter site or site collection if you want to update the link to a given asset everywhere it appears.</span></span>
+ <span data-ttu-id="bb3e9-545">Для каждой ссылки на ресурс в источнике замените путь путем к файлу в источнике CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-545">For each link to an asset in an origin, replace the path with the path to the file in the CDN origin.</span></span> <span data-ttu-id="bb3e9-546">Можно использовать относительные пути.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-546">You can use relative paths.</span></span>
+ <span data-ttu-id="bb3e9-547">Сохраните страницу или содержимое.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-547">Save the page or content.</span></span>

<span data-ttu-id="bb3e9-548">Например, рассмотрим изображение _/site/SiteAssets/images/image.png,_ которое вы скопировали в папку библиотеки документов _/site/CDN_origins/public/_.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-548">For example, consider the image _/site/SiteAssets/images/image.png_, which you have copied to the document library folder _/site/CDN_origins/public/_.</span></span> <span data-ttu-id="bb3e9-549">Чтобы использовать ресурс CDN, замените исходный путь к расположению файла изображения путем к источнику, чтобы новый URL-адрес _/site/CDN_origins/public/image.png_.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-549">To use the CDN asset, replace the original path to the image file location with the path to the origin to make the new URL _/site/CDN_origins/public/image.png_.</span></span>

<span data-ttu-id="bb3e9-550">Если вы хотите использовать полный URL-адрес актива вместо относительного пути, состройка ссылки выглядит так:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-550">If you want to use the full URL to the asset instead of a relative path, construct the link like so:</span></span>

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> <span data-ttu-id="bb3e9-551">Как правило, не следует жестко кодировать URL-адреса непосредственно к активам в CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-551">In general, you should not hardcode URLs directly to assets in the CDN.</span></span> <span data-ttu-id="bb3e9-552">Однако при необходимости вы можете вручную создать URL-адреса для ресурсов в общедоступных источниках.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-552">However, you can manually construct URLs for assets in public origins if needed.</span></span> <span data-ttu-id="bb3e9-553">Дополнительные сведения см. в [url-адресах cdn hardcoding для общедоступных активов.](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-553">For more information, see [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).</span></span>

<span data-ttu-id="bb3e9-554">Чтобы узнать, как проверить, обслуживаются ли ресурсы из CDN, см. раздел "Как проверить, обслуживаются ли ресурсы в [CDN?"](use-microsoft-365-cdn-with-spo.md#CDNConfirm) в разделе "Устранение неполадок в [CDN Office 365".](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-554">To learn about how to verify that assets are being served from the CDN, see [How do I confirm that assets are being served by the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in the [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) section.</span></span>

### <a name="using-assets-in-public-origins"></a><span data-ttu-id="bb3e9-555">Использование ресурсов в общедоступных источниках</span><span class="sxs-lookup"><span data-stu-id="bb3e9-555">Using assets in public origins</span></span>

<span data-ttu-id="bb3e9-556">Функция  публикации в SharePoint Online автоматически переозначает URL-адреса активов, хранимые в общедоступных источниках, в их эквиваленты CDN, чтобы ресурсы обслуживались из службы CDN, а не Из SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-556">The **Publishing feature** in SharePoint Online automatically rewrites URLs of assets stored in public origins to their CDN equivalents so that assets are served from the CDN service instead of SharePoint.</span></span>

<span data-ttu-id="bb3e9-557">Если ваш источник находится на сайте с включенной функцией публикации, а ресурсы, которые вы хотите разгрузить в CDN, находятся в одной из следующих категорий, SharePoint автоматически переопишет URL-адреса ресурсов в источнике, если актив не был исключен политикой CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-557">If your origin is in a site with the Publishing feature enabled, and the assets you want to offload to the CDN are in one of the following categories, SharePoint will automatically rewrite URLs for assets in the origin, provided that the asset has not been excluded by a CDN policy.</span></span>

<span data-ttu-id="bb3e9-558">Ниже представлен обзор ссылок, которые автоматически заменяет функция публикации в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-558">The following is an overview of which links are automatically rewritten by the SharePoint Publishing feature:</span></span>

+ <span data-ttu-id="bb3e9-559">URL-адреса IMG-, LINK- и CSS-файлов в HTML-откликах классической страницы публикации.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-559">IMG/LINK/CSS URLs in classic publishing page HTML responses</span></span>
  + <span data-ttu-id="bb3e9-560">Это относится и к изображениям, добавленным авторами в HTML-содержимом страницы.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-560">This includes images added by authors within the HTML content of a page</span></span>
+ <span data-ttu-id="bb3e9-561">URL-адреса изображений в веб-части "Слайд-шоу библиотеки рисунков".</span><span class="sxs-lookup"><span data-stu-id="bb3e9-561">Picture Library SlideShow webpart image URLs</span></span>
+ <span data-ttu-id="bb3e9-562">Поля изображений в результатах работы REST API SPList (RenderListDataAsStream).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-562">Image fields in SPList REST API (RenderListDataAsStream) results</span></span>
  + <span data-ttu-id="bb3e9-563">Использование нового свойства _ImageFieldsToTryRewriteToCdnUrls_ для предоставления списка полей, разделенных запятой</span><span class="sxs-lookup"><span data-stu-id="bb3e9-563">Use the new property _ImageFieldsToTryRewriteToCdnUrls_ to provide a comma separated list of fields</span></span>
  + <span data-ttu-id="bb3e9-564">Поддерживает поля гиперссылки и поля PublishingImage</span><span class="sxs-lookup"><span data-stu-id="bb3e9-564">Supports hyperlink fields and PublishingImage fields</span></span>
+ <span data-ttu-id="bb3e9-565">Представление изображений SharePoint</span><span class="sxs-lookup"><span data-stu-id="bb3e9-565">SharePoint image renditions</span></span>

<span data-ttu-id="bb3e9-566">На следующей схеме показано, как работает рабочий процесс, когда SharePoint получает запрос на страницу, содержащую ресурсы из публичного источника.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-566">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a public origin.</span></span>

<span data-ttu-id="bb3e9-567">![Схема рабочего процесса: искомые ресурсы CDN Office 365 из публичного источника](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Рабочий процесс: искомые ресурсы CDN Office 365 из публичного источника")</span><span class="sxs-lookup"><span data-stu-id="bb3e9-567">![Workflow diagram: Retrieving Office 365 CDN assets from a public origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a public origin")</span></span>

> [!TIP]
> <span data-ttu-id="bb3e9-568">Если вы хотите отключить автоматическое переописывание для определенных URL-адресов на странице, вы можете найти страницу и добавить параметр строки **запроса? NoAutoReWrites=true** в конце каждой ссылки, отключаемой.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-568">If you want to disable auto-rewriting for specific URLs on a page, you can check out the page and add the query string parameter **?NoAutoReWrites=true** to the end of each link you want to disable.</span></span>

#### <a name="hardcoding-cdn-urls-for-public-assets"></a><span data-ttu-id="bb3e9-569">Жесткое задание URL-адресов CDN для общедоступных активов</span><span class="sxs-lookup"><span data-stu-id="bb3e9-569">Hardcoding CDN URLs for public assets</span></span>

<span data-ttu-id="bb3e9-570">Если  функция публикации не включена для общего источника или ресурс не является одним из типов ссылок, поддерживаемых функцией автоматического перезаписи службы CDN, можно вручную создать URL-адреса в расположении ресурсов CDN и использовать эти URL-адреса в содержимом.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-570">If the _Publishing_ feature is not enabled for a public origin, or the asset is not one of the link types supported by the auto-rewrite feature of the CDN service, you can manually construct URLs to the CDN location of the assets and use these URLs in your content.</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e9-571">Невозможно жестко закодировать URL-адреса CDN для ресурсов в частном источнике, так как необходимый маркер доступа, формирующий последний раздел URL-адреса, создается во время запроса ресурса.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-571">You cannot hardcode CDN URLs to assets in a private origin because the required access token that forms the last section of the URL is generated at the time the resource is requested.</span></span>

<span data-ttu-id="bb3e9-572">Для общедоступных ресурсов CDN формат URL-адреса будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-572">For public CDN assets, the URL format will look like the following:</span></span>

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

<span data-ttu-id="bb3e9-573">Замените **TenantHostName** именем клиента.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-573">Replace **TenantHostName** with your tenant name.</span></span> <span data-ttu-id="bb3e9-574">Пример.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-574">Example:</span></span>

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a><span data-ttu-id="bb3e9-575">Использование ресурсов в частных источниках</span><span class="sxs-lookup"><span data-stu-id="bb3e9-575">Using assets in private origins</span></span>

<span data-ttu-id="bb3e9-576">Для использования активов в частных источниках не требуется дополнительная настройка.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-576">No additional configuration is required to use assets in private origins.</span></span> <span data-ttu-id="bb3e9-577">SharePoint Online автоматически переописает URL-адреса для активов в частных источниках, чтобы запросы на эти ресурсы всегда обслуживались из сети CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-577">SharePoint Online automatically rewrites URLs for assets in private origins so requests for those assets will always be served from the CDN.</span></span> <span data-ttu-id="bb3e9-578">Невозможно вручную создавать URL-адреса для ресурсов CDN в частных источниках, так как эти URL-адреса содержат маркеры, которые должны автоматически создаваться SharePoint Online во время запроса актива.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-578">You cannot manually build URLs to CDN assets in private origins because these URLs contain tokens that must be auto-generated by SharePoint Online at the time the asset is requested.</span></span>

<span data-ttu-id="bb3e9-579">Доступ к активам в частных источниках защищен динамически созданными маркерами на основе разрешений пользователя на доступ к источнику с оговорками, описанными в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-579">Access to assets in private origins is protected by dynamically generated tokens based on user permissions to the origin, with the caveats described in the following sections.</span></span> <span data-ttu-id="bb3e9-580">Пользователи должны иметь по крайней мере **доступ** на чтение к источникам, чтобы CDN отрисовыла содержимое.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-580">Users must have at least **read** access to the origins for the CDN to render content.</span></span>

<span data-ttu-id="bb3e9-581">На следующей схеме показано, как работает рабочий процесс, когда SharePoint получает запрос страницы, содержащей ресурсы из частного источника.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-581">The following diagram illustrates the workflow when SharePoint receives a request for a page containing assets from a private origin.</span></span>

<span data-ttu-id="bb3e9-582">![Схема рабочего процесса: искомые ресурсы CDN Office 365 из частного источника](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Рабочий процесс: искомые ресурсы CDN Office 365 из частного источника")</span><span class="sxs-lookup"><span data-stu-id="bb3e9-582">![Workflow diagram: Retrieving Office 365 CDN assets from a private origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Retrieving Office 365 CDN assets from a private origin")</span></span>

#### <a name="token-based-authorization-in-private-origins"></a><span data-ttu-id="bb3e9-583">Авторизация на основе маркеров в частных источниках</span><span class="sxs-lookup"><span data-stu-id="bb3e9-583">Token-based authorization in private origins</span></span>

<span data-ttu-id="bb3e9-584">Доступ к активам в частных источниках в сети CDN Office 365 предоставляется маркерами, созданными SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-584">Access to assets in private origins in the Office 365 CDN is granted by tokens generated by SharePoint Online.</span></span> <span data-ttu-id="bb3e9-585">Пользователям, у которых уже есть разрешение на доступ к папке или библиотеке, указанной в источнике, автоматически назначаются маркеры, которые позволяют пользователю получать доступ к файлу на основе их уровня разрешений.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-585">Users who already have permission to access to the folder or library designated by the origin are automatically granted tokens that permit the user to access the file based on their permission level.</span></span> <span data-ttu-id="bb3e9-586">Эти маркеры доступа действительны в течение 30–90 минут после их сгенерирований для предотвращения атак с повтором маркеров.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-586">These access tokens are valid for 30 to 90 minutes after they are generated to help prevent token replay attacks.</span></span>

<span data-ttu-id="bb3e9-587">После сгенерирования маркера доступа SharePoint Online возвращает настраиваемый URI клиенту, содержащим два параметра авторизации _(_ edge authorization token) и _oat_ (маркер авторизации источника).</span><span class="sxs-lookup"><span data-stu-id="bb3e9-587">Once the access token is generated, SharePoint Online returns a custom URI to the client containing two authorization parameters _eat_ (edge authorization token) and _oat_ (origin authorization token).</span></span> <span data-ttu-id="bb3e9-588">Структура каждого маркера< срок действия в формате времени >__< в формате >_._</span><span class="sxs-lookup"><span data-stu-id="bb3e9-588">The structure of each token is _<'expiration time in Epoch time format'>__<'secure signature'>_.</span></span> <span data-ttu-id="bb3e9-589">Пример:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-589">For example:</span></span>

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> <span data-ttu-id="bb3e9-590">Любой, кто владеет маркером, может получить доступ к ресурсу в сети CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-590">Anyone in possession of the token can access the resource in the CDN.</span></span> <span data-ttu-id="bb3e9-591">Однако URL-адреса, содержащие эти маркеры доступа, доступны только по протоколу HTTPS, поэтому если конечный пользователь явным образом не поделился URL-адресом до истечения срока действия маркера, ресурс будет недоступен неавторизованным пользователям.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-591">However, URLs containing these access tokens are only shared over HTTPS, so unless the URL is explicitly shared by an end user before the token expires, the asset won't be accessible to unauthorized users.</span></span>

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a><span data-ttu-id="bb3e9-592">Разрешения на уровне элементов не поддерживаются для активов в частных источниках</span><span class="sxs-lookup"><span data-stu-id="bb3e9-592">Item-level permissions are not supported for assets in private origins</span></span>

<span data-ttu-id="bb3e9-593">Важно отметить, что SharePoint Online не поддерживает разрешения на уровне элементов для активов в частных источниках.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-593">It is important to note that SharePoint Online does not support item-level permissions for assets in private origins.</span></span> <span data-ttu-id="bb3e9-594">Например, для файла, расположенного по адресу, пользователи имеют эффективный доступ к файлу при `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` следующих условиях:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-594">For example, for a file located at `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`, users have effective access to the file given the following conditions:</span></span>

|<span data-ttu-id="bb3e9-595">Пользователь</span><span class="sxs-lookup"><span data-stu-id="bb3e9-595">User</span></span>  |<span data-ttu-id="bb3e9-596">Permissions</span><span class="sxs-lookup"><span data-stu-id="bb3e9-596">Permissions</span></span>  |<span data-ttu-id="bb3e9-597">Эффективный доступ</span><span class="sxs-lookup"><span data-stu-id="bb3e9-597">Effective access</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="bb3e9-598">Пользователь 1</span><span class="sxs-lookup"><span data-stu-id="bb3e9-598">User 1</span></span>     |<span data-ttu-id="bb3e9-599">Имеет доступ к папке1</span><span class="sxs-lookup"><span data-stu-id="bb3e9-599">Has access to folder1</span></span>         |<span data-ttu-id="bb3e9-600">Доступ к image1.jpg из сети CDN</span><span class="sxs-lookup"><span data-stu-id="bb3e9-600">Can access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="bb3e9-601">Пользователь 2</span><span class="sxs-lookup"><span data-stu-id="bb3e9-601">User 2</span></span>     |<span data-ttu-id="bb3e9-602">Не имеет доступа к папке1</span><span class="sxs-lookup"><span data-stu-id="bb3e9-602">Does not have access to folder1</span></span>         |<span data-ttu-id="bb3e9-603">Не удается получить image1.jpg из сети CDN</span><span class="sxs-lookup"><span data-stu-id="bb3e9-603">Cannot access image1.jpg from the CDN</span></span>         |
|<span data-ttu-id="bb3e9-604">Пользователь 3</span><span class="sxs-lookup"><span data-stu-id="bb3e9-604">User 3</span></span>     |<span data-ttu-id="bb3e9-605">Не имеет доступа к папке1, но ему предоставлено явное разрешение на доступ к image1.jpg в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-605">Does not have access to folder1, but is granted explicit permission to access image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="bb3e9-606">Доступ к ресурсу image1.jpg непосредственно из SharePoint Online, но не из сети CDN</span><span class="sxs-lookup"><span data-stu-id="bb3e9-606">Can access the asset image1.jpg directly from SharePoint Online, but not from the CDN</span></span>         |
|<span data-ttu-id="bb3e9-607">Пользователь 4</span><span class="sxs-lookup"><span data-stu-id="bb3e9-607">User 4</span></span>     |<span data-ttu-id="bb3e9-608">Имеет доступ к папке1, но ему явным образом отказано в доступе к image1.jpg в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-608">Has access to folder1, but has been explicitly denied access to image1.jpg in SharePoint Online</span></span>         |<span data-ttu-id="bb3e9-609">Не удается получить доступ к активу из SharePoint Online, но он может получить доступ из СЕТИ CDN несмотря на то, что ему отказано в доступе к файлу в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-609">Cannot access the asset from SharePoint Online, but can access the asset from the CDN despite being denied access to the file in SharePoint Online</span></span>         |

<span data-ttu-id="bb3e9-610"><a name="CDNTroubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-610"><a name="CDNTroubleshooting"> </a></span></span>
## <a name="troubleshooting-the-office-365-cdn"></a><span data-ttu-id="bb3e9-611">Устранение неполадок в CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-611">Troubleshooting the Office 365 CDN</span></span>

<span data-ttu-id="bb3e9-612"><a name="CDNConfirm"> </a></span><span class="sxs-lookup"><span data-stu-id="bb3e9-612"><a name="CDNConfirm"> </a></span></span>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a><span data-ttu-id="bb3e9-613">Как подтвердить, что ресурсы обслуживаются CDN?</span><span class="sxs-lookup"><span data-stu-id="bb3e9-613">How do I confirm that assets are being served by the CDN?</span></span>

<span data-ttu-id="bb3e9-614">После того как вы добавили ссылки на ресурсы CDN на страницу, вы можете подтвердить, что ресурс обслуживается из CDN, перейдите на страницу, щелкнув правой кнопкой мыши изображение после его отрисовки и просмотрев URL-адрес изображения.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-614">Once you have added links to CDN assets to a page, you can confirm that the asset is being served from the CDN by browsing to the page, right clicking on the image once it has rendered and reviewing the image URL.</span></span>

<span data-ttu-id="bb3e9-615">Вы также можете использовать средства разработчика браузера для просмотра URL-адреса для каждого актива на странице или использовать стороне средство трассировки сети.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-615">You can also use your browser's developer tools to view the URL for each asset on a page, or use a third party network trace tool.</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e9-616">Если вы используете сетевое средство, например Fiddler, для тестирования ресурсов вне отображения актива со страницы SharePoint, необходимо вручную добавить загон "Referer:" в запрос GET, где URL-адрес является корневым URL-адресом клиента `https://yourdomain.sharepoint.com` SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-616">If you use a network tool such as Fiddler to test your assets outside of rendering the asset from a SharePoint page, you must manually add the referer header "Referer: `https://yourdomain.sharepoint.com`" to the GET request where the URL is the root URL of your SharePoint Online tenant.</span></span>

<span data-ttu-id="bb3e9-617">Вы не можете тестировать URL-адреса CDN непосредственно в веб-браузере, так как у вас должен быть ссылка из SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-617">You cannot test CDN URLs directly in a web browser because you must have a referer coming from SharePoint Online.</span></span> <span data-ttu-id="bb3e9-618">Однако если добавить URL-адрес ресурсов CDN на страницу SharePoint, а затем открыть страницу в браузере, ресурс CDN будет отрисован на странице.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-618">However, if you add the CDN asset URL to a SharePoint page and then open the page in a browser, you will see the CDN asset rendered on the page.</span></span>

<span data-ttu-id="bb3e9-619">Дополнительные сведения об использовании средств разработчика в браузере Microsoft Edge см. в средстве [разработчика Microsoft Edge.](https://docs.microsoft.com/microsoft-edge/devtools-guide)</span><span class="sxs-lookup"><span data-stu-id="bb3e9-619">For more information on using the developer tools in the Microsoft Edge browser, see [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).</span></span>

<span data-ttu-id="bb3e9-620">Чтобы посмотреть короткое видео, размещенное в канале [SharePoint Developer Patterns and Practices YouTube,](https://aka.ms/sppnp-videos) демонстрирующее, как проверить работу сети CDN, см. раздел "Проверка использования [сети CDN](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)и обеспечение оптимального сетевого подключения".</span><span class="sxs-lookup"><span data-stu-id="bb3e9-620">To watch a short video hosted in the [SharePoint Developer Patterns and Practices YouTube channel](https://aka.ms/sppnp-videos) demonstrating how to verify that your CDN is working, please see [Verifying your CDN usage and ensuring optimal network connectivity](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).</span></span>

### <a name="why-are-assets-from-a-new-origin-unavailable"></a><span data-ttu-id="bb3e9-621">Почему ресурсы из нового источника недоступны?</span><span class="sxs-lookup"><span data-stu-id="bb3e9-621">Why are assets from a new origin unavailable?</span></span>
<span data-ttu-id="bb3e9-622">Ресурсы в новых источниках не сразу станут доступны для использования, так как регистрация проходит через CDN и загружается из источника в хранилище CDN.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-622">Assets in new origins will not immediately be available for use, as it takes time for the registration to propagate through the CDN and for the assets to be uploaded from the origin to CDN storage.</span></span> <span data-ttu-id="bb3e9-623">Время, необходимое для того, чтобы активы были доступны в CDN, зависит от того, сколько ресурсов и размеров файлов.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-623">The time required for assets to be available in the CDN depends on how many assets and the files sizes.</span></span>

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a><span data-ttu-id="bb3e9-624">Не работает клиентская веб-часть или решение SharePoint Framework</span><span class="sxs-lookup"><span data-stu-id="bb3e9-624">My client-side web part or SharePoint Framework solution isn't working</span></span>

<span data-ttu-id="bb3e9-625">Когда вы включаете CDN Office 365 для общедоступных источниках, служба CDN автоматически создает эти источника по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-625">When you enable the Office 365 CDN for public origins, the CDN service automatically creates these default origins:</span></span>

+ <span data-ttu-id="bb3e9-626">\*/MASTERPAGE</span><span class="sxs-lookup"><span data-stu-id="bb3e9-626">\*/MASTERPAGE</span></span>
+ <span data-ttu-id="bb3e9-627">\*/STYLE LIBRARY</span><span class="sxs-lookup"><span data-stu-id="bb3e9-627">\*/STYLE LIBRARY</span></span>
+ <span data-ttu-id="bb3e9-628">\*/CLIENTSIDEASSETS</span><span class="sxs-lookup"><span data-stu-id="bb3e9-628">\*/CLIENTSIDEASSETS</span></span>

<span data-ttu-id="bb3e9-629">Если отсутствует источник \*/clientsideassets, решения SharePoint Framework не будут работать, и предупреждения или сообщения об ошибках не будут созданы.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-629">If the \*/clientsideassets origin is missing, SharePoint Framework solutions will fail, and no warning or error messages are generated.</span></span> <span data-ttu-id="bb3e9-630">Этот источник может отключаться либо из-за включения CDN с параметром _-NoDefaultOrigins,_ установленным **$true,** либо из-за того, что источник был удален вручную.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-630">This origin may be missing either because the CDN was enabled with the _-NoDefaultOrigins_ parameter set to **$true**, or because the origin was manually deleted.</span></span>

<span data-ttu-id="bb3e9-631">Чтобы узнать, какие источникы присутствуют, можно использовать следующую команду PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-631">You can check to see which origins are present with the following PowerShell command:</span></span>

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

<span data-ttu-id="bb3e9-632">Или вы можете проверить office 365 CLI:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-632">Or you can check with the Office 365 CLI:</span></span>

``` powershell
spo cdn origin list
```

<span data-ttu-id="bb3e9-633">Чтобы добавить источник в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-633">To add the origin in PowerShell:</span></span>

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

<span data-ttu-id="bb3e9-634">Чтобы добавить источник в Office 365 CLI:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-634">To add the origin in the Office 365 CLI:</span></span>

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a><span data-ttu-id="bb3e9-635">Какие модули PowerShell и оболочки CLI необходимы для работы с CDN Office 365?</span><span class="sxs-lookup"><span data-stu-id="bb3e9-635">What PowerShell modules and CLI shells do I need to work with the Office 365 CDN?</span></span>

<span data-ttu-id="bb3e9-636">Вы можете работать с сетью CDN Office 365 с помощью модуля PowerShell командной оболочки **SharePoint Online** или **office 365 CLI.**</span><span class="sxs-lookup"><span data-stu-id="bb3e9-636">You can choose to work with the Office 365 CDN using either the **SharePoint Online Management Shell** PowerShell module or the **Office 365 CLI**.</span></span>

+ [<span data-ttu-id="bb3e9-637">Начало работы с командной консолью SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bb3e9-637">Getting started with SharePoint Online Management Shell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [<span data-ttu-id="bb3e9-638">Установка Office 365 CLI</span><span class="sxs-lookup"><span data-stu-id="bb3e9-638">Installing the Office 365 CLI</span></span>](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a><span data-ttu-id="bb3e9-639">См. также</span><span class="sxs-lookup"><span data-stu-id="bb3e9-639">See also</span></span>

[<span data-ttu-id="bb3e9-640">Сети доставки содержимого</span><span class="sxs-lookup"><span data-stu-id="bb3e9-640">Content Delivery Networks</span></span>](https://aka.ms/o365cdns)

[<span data-ttu-id="bb3e9-641">Планирование сети и настройка производительности для Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-641">Network planning and performance tuning for Office 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="bb3e9-642">Серия о производительности SharePoint — серия видео о сети CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e9-642">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
