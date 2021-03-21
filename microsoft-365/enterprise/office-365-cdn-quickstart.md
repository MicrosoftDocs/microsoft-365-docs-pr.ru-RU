---
title: Сеть доставки контента Office 365 (CDN) Quickstart
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Сеть доставки контента Office 365 (CDN) Quickstart
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921598"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="5ac3a-103">Сеть доставки контента Office 365 (CDN) Quickstart</span><span class="sxs-lookup"><span data-stu-id="5ac3a-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="5ac3a-104">Встроенная сеть доставки **контента Office 365 (CDN)** может использовать встроенную сеть доставки контента (CDN) для статических активов (изображений, JavaScript, Stylesheets, WOFF-файлов), чтобы обеспечить лучшую производительность для страниц SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="5ac3a-105">Сеть CDN Office 365 повышает производительность путем кэширования статических ресурсов ближе к браузерам, которые их запрашивают, что повышает скорость скачиваний и снижает задержку.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="5ac3a-106">Кроме того, CDN Office 365 использует протокол HTTP/2 для улучшения сжатия и http pipelining.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="5ac3a-107">Служба CDN Office 365 входит в состав подписки на SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="5ac3a-108">Дополнительные сведения см. в раздел Использование сети доставки [контента Office 365 (CDN) с SharePoint Online.](use-microsoft-365-cdn-with-spo.md)</span><span class="sxs-lookup"><span data-stu-id="5ac3a-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="5ac3a-109">CdN Office 365 доступен только для клиентов в производственном (по всему миру) облаке.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="5ac3a-110">Клиенты в облаках правительства США, Китая и Германии в настоящее время не поддерживают CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="5ac3a-111">Используйте средство диагностики страниц для SharePoint для идентификации элементов, не в CDN</span><span class="sxs-lookup"><span data-stu-id="5ac3a-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="5ac3a-112">Чтобы легко перечислить активы на страницах SharePoint Online, которые можно добавить в cdN-источник, можно использовать расширение браузера page **Diagnostics for SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="5ac3a-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="5ac3a-113">Средство **Page Diagnostics for SharePoint** — это расширение браузера для нового браузера Microsoft Edge (и браузеры Chrome, которые анализируют современный портал SharePoint Online и классические страницы сайтов https://www.microsoft.com/edge) публикации.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="5ac3a-114">Это средство предоставляет отчет о каждой проанализированной странице, показывающий, как она работает при заданных критериях производительности.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="5ac3a-115">Чтобы установить и изучить средство диагностики страниц SharePoint, ознакомьтесь со статьей [Использование средства диагностики страниц SharePoint Online](./page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="5ac3a-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](./page-diagnostics-for-spo.md).</span></span>

<span data-ttu-id="5ac3a-116">При запуске средства диагностики страниц для SharePoint на странице SharePoint Online можно нажать вкладку Диагностические тесты, чтобы увидеть список активов, не принимающихся cdN. </span><span class="sxs-lookup"><span data-stu-id="5ac3a-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="5ac3a-117">Эти активы будут перечислены в статье Проверка сети доставки контента **(CDN),** как показано на скриншоте ниже.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![Диагностика страниц](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="5ac3a-119">Средство диагностики страниц работает только в SharePoint Online, и его нельзя использовать на системной странице SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="5ac3a-120">Обзор CDN</span><span class="sxs-lookup"><span data-stu-id="5ac3a-120">CDN Overview</span></span>

<span data-ttu-id="5ac3a-121">CDN Office 365 предназначен для оптимизации производительности для пользователей путем распространения часто доступных объектов, таких как изображения и файлы javascript по высокоскоростной глобальной сети, сокращая время загрузки страниц и обеспечивая доступ к объектам, которые находятся как можно ближе к пользователю.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="5ac3a-122">CDN извлекает ваши активы из расположения, называемого _происхождением._</span><span class="sxs-lookup"><span data-stu-id="5ac3a-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="5ac3a-123">Происхождение может быть веб-сайтОм SharePoint, библиотекой документов или папкой, доступной по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="5ac3a-124">CDN Office 365 разделен на два основных типа:</span><span class="sxs-lookup"><span data-stu-id="5ac3a-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="5ac3a-125">**Общедоступный CDN** предназначен для использования для JS (JavaScript), CSS (StyleSheets), Файла веб-шрифтов (WOFF, WOFF2) и несвободных изображений, таких как логотипы компании.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="5ac3a-126">**Частный CDN** предназначен для использования для изображений (PNG, JPG, JPEG и т.д.).</span><span class="sxs-lookup"><span data-stu-id="5ac3a-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="5ac3a-127">Вы можете выбрать общедоступные или частные истоки для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="5ac3a-128">Большинство организаций будут выбирать для реализации сочетания этих двух.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="5ac3a-129">Как общедоступные, так и частные параметры обеспечивают аналогичные преимущества производительности, но каждый из них имеет уникальные атрибуты и преимущества.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="5ac3a-130">Дополнительные сведения о общедоступных и частных источниках CDN см. в выпуске Выберите, должно ли каждое происхождение быть [общедоступным или частным.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)</span><span class="sxs-lookup"><span data-stu-id="5ac3a-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="5ac3a-131">Как включить общедоступный и частный CDN с конфигурацией по умолчанию</span><span class="sxs-lookup"><span data-stu-id="5ac3a-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="5ac3a-132">Прежде чем вносить изменения в параметры CDN клиента, необходимо убедиться, что он соответствует требованиям, политикам безопасности и конфиденциальности вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5ac3a-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="5ac3a-133">Дополнительные параметры конфигурации или если вы уже включили CDN и хотите добавить дополнительные расположения (истоки), см. в разделе Настройка и настройка [CDN Office 365](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) с помощью оболочки управления SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5ac3a-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="5ac3a-134">Подключение к клиенту с помощью оболочки управления SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="5ac3a-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="5ac3a-135">Чтобы позволить организации использовать общедоступные и частные истоки с конфигурацией по умолчанию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5ac3a-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="5ac3a-136">Выход этих комлетов должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5ac3a-136">Output of these cmdlets should look like the following:</span></span>

![Выход Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="5ac3a-138">См. также</span><span class="sxs-lookup"><span data-stu-id="5ac3a-138">See also</span></span>

[<span data-ttu-id="5ac3a-139">Используйте средство диагностики страниц для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5ac3a-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](./page-diagnostics-for-spo.md)

[<span data-ttu-id="5ac3a-140">Использование сети доставки содержимого Office 365 с SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5ac3a-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="5ac3a-141">Сети доставки содержимого</span><span class="sxs-lookup"><span data-stu-id="5ac3a-141">Content Delivery Networks</span></span>](./content-delivery-networks.md)

[<span data-ttu-id="5ac3a-142">Планирование сети и настройка производительности для Office 365</span><span class="sxs-lookup"><span data-stu-id="5ac3a-142">Network planning and performance tuning for Office 365</span></span>](./network-planning-and-performance.md)

[<span data-ttu-id="5ac3a-143">Серия производительности SharePoint — видеосерия CDN Office 365</span><span class="sxs-lookup"><span data-stu-id="5ac3a-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)