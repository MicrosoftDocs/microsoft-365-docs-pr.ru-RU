---
title: Краткое руководство по сети доставки содержимого (CDN) Office 365
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
- M365initiative-CoreDeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Краткое руководство по сети доставки содержимого (CDN) Office 365
ms.openlocfilehash: e9975721b5cfaaed2c9ad7562c47f12c7a5a5bc3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326893"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a><span data-ttu-id="f9090-103">Краткое руководство по сети доставки содержимого (CDN) Office 365</span><span class="sxs-lookup"><span data-stu-id="f9090-103">Office 365 Content Delivery Network (CDN) Quickstart</span></span>

<span data-ttu-id="f9090-104">Вы можете использовать встроенную **сеть доставки содержимого (CDN) Office 365** для размещения статических ресурсов (изображений, JavaScript, таблиц стилей, файлов WOFF), чтобы обеспечить лучшую производительность для страниц SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f9090-104">You can use the built-in **Office 365 Content Delivery Network (CDN)** to host static assets (images, JavaScript, Stylesheets, WOFF files) to provide better performance for your SharePoint Online pages.</span></span> <span data-ttu-id="f9090-105">Сеть CDN Office 365 повышает производительность путем кэширования статических ресурсов ближе к браузерам, которые их запрашивают, что повышает скорость скачиваний и снижает задержку.</span><span class="sxs-lookup"><span data-stu-id="f9090-105">The Office 365 CDN improves performance by caching static assets closer to the browsers requesting them, which helps to speed up downloads and reduce latency.</span></span> <span data-ttu-id="f9090-106">Кроме того, в сети CDN Office 365 используется протокол HTTP/2 для улучшения сжатия и конвейерной передачи данных по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="f9090-106">Also, the Office 365 CDN uses the HTTP/2 protocol for improved compression and HTTP pipelining.</span></span> <span data-ttu-id="f9090-107">Служба CDN Office 365 входит в состав подписки на SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f9090-107">The Office 365 CDN service is included as part of your SharePoint Online subscription.</span></span>

<span data-ttu-id="f9090-108">Более подробную информацию можно узнать [в статье Использование сети доставки содержимого (CDN) Office 365 с SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span><span class="sxs-lookup"><span data-stu-id="f9090-108">For more detailed information guidance see [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="f9090-109">Сеть CDN Office 365 доступна только клиентам в облачной среде.</span><span class="sxs-lookup"><span data-stu-id="f9090-109">The Office 365 CDN is only available to tenants in the production (worldwide) cloud.</span></span> <span data-ttu-id="f9090-110">Клиенты в облаках США, Китая и Германии в настоящее время не поддерживают CDN Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9090-110">Tenants in the US Government, China and Germany clouds do not currently support the Office 365 CDN.</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a><span data-ttu-id="f9090-111">Использование средства диагностики страниц для SharePoint для определения элементов, отсутствующих в сети CDN</span><span class="sxs-lookup"><span data-stu-id="f9090-111">Use the Page Diagnostics for SharePoint tool to identify items not in CDN</span></span>

<span data-ttu-id="f9090-112">С помощью расширения браузера **средства диагностики страниц для SharePoint** можно легко перечислить ресурсы на страницах SharePoint Online, которые можно добавить в источник CDN.</span><span class="sxs-lookup"><span data-stu-id="f9090-112">You can use the **Page Diagnostics for SharePoint tool** browser extension to easily list assets in your SharePoint Online pages that can be added to a CDN origin.</span></span>

<span data-ttu-id="f9090-113">**Средство диагностики страниц для SharePoint** — это расширение браузера для новых веб-браузеров Microsoft EDGE ( https://www.microsoft.com/edge) и браузеров Chrome, которые анализируют как современный портал SharePoint Online, так и классические страницы сайта публикации.</span><span class="sxs-lookup"><span data-stu-id="f9090-113">The **Page Diagnostics for SharePoint tool** is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="f9090-114">Это средство предоставляет отчет о каждой проанализированной странице, показывающий, как она работает при заданных критериях производительности.</span><span class="sxs-lookup"><span data-stu-id="f9090-114">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="f9090-115">Чтобы установить и изучить средство диагностики страниц SharePoint, ознакомьтесь со статьей [Использование средства диагностики страниц SharePoint Online](https://aka.ms/perftool).</span><span class="sxs-lookup"><span data-stu-id="f9090-115">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](https://aka.ms/perftool).</span></span>

<span data-ttu-id="f9090-116">При запуске средства диагностики страниц для SharePoint на странице SharePoint Online можно щелкнуть вкладку **диагностические тесты** , чтобы просмотреть список ресурсов, не размещенных в сети CDN.</span><span class="sxs-lookup"><span data-stu-id="f9090-116">When you run the Page Diagnostics for SharePoint tool on a SharePoint Online page, you can click the **Diagnostic Tests** tab to see a list of assets not being hosted by the CDN.</span></span> <span data-ttu-id="f9090-117">Эти ресурсы будут перечислены в разделе заголовков **сеть доставки содержимого (CDN)** , как показано на снимке экрана ниже.</span><span class="sxs-lookup"><span data-stu-id="f9090-117">These assets will be listed under the heading **Content Delivery Network (CDN) check** as shown in the screenshot below.</span></span>

![Диагностика страницы](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
><span data-ttu-id="f9090-119">Средство диагностики страниц работает только в SharePoint Online, и его нельзя использовать на системной странице SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f9090-119">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

## <a name="cdn-overview"></a><span data-ttu-id="f9090-120">Обзор сети CDN</span><span class="sxs-lookup"><span data-stu-id="f9090-120">CDN Overview</span></span>

<span data-ttu-id="f9090-121">Сеть CDN Office 365 разработана для оптимизации производительности пользователей за счет распределения часто используемых объектов, таких как изображения и файлы JavaScript, в высокоскоростной глобальной сети, уменьшая время загрузки страницы и предоставляя доступ к размещенным объектам максимально близкому пользователю.</span><span class="sxs-lookup"><span data-stu-id="f9090-121">The Office 365 CDN is designed to optimize performance for users by distributing frequently accessed objects like images and javascript files over a high-speed global network, reducing page load time and providing access to hosted objects as close as possible to the user.</span></span> <span data-ttu-id="f9090-122">CDN извлекает ресурсы из расположения, называемого _источником_.</span><span class="sxs-lookup"><span data-stu-id="f9090-122">The CDN fetches your assets from a location called an _origin_.</span></span> <span data-ttu-id="f9090-123">Источником может быть сайт SharePoint, Библиотека документов или папка, доступ к которым можно получить по URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="f9090-123">An origin can be a SharePoint site, document library or folder that is accessible by a URL.</span></span>

<span data-ttu-id="f9090-124">CDN Office 365 разделяется на два основных типа:</span><span class="sxs-lookup"><span data-stu-id="f9090-124">The Office 365 CDN is separated into two basic types:</span></span>

- <span data-ttu-id="f9090-125">**Общедоступная сеть CDN** предназначена для использования в JS (JavaScript), CSS (таблицы стилей), файле веб-шрифтов (WOFF, WOFF2) и нечастных изображениях, таких как логотипы компаний.</span><span class="sxs-lookup"><span data-stu-id="f9090-125">**Public CDN** is designed to be used for JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) and non-proprietary images like company logos.</span></span>
- <span data-ttu-id="f9090-126">**Частная сеть CDN** предназначена для использования в изображениях (PNG, JPG, JPEG и т. д.).</span><span class="sxs-lookup"><span data-stu-id="f9090-126">**Private CDN** is designed to be used for images (PNG, JPG, JPEG, etc.).</span></span>

<span data-ttu-id="f9090-127">Вы можете использовать как общедоступные, так и частные источники для Организации.</span><span class="sxs-lookup"><span data-stu-id="f9090-127">You can choose to have both public or private origins for your organization.</span></span> <span data-ttu-id="f9090-128">В большинстве организаций будет выбрана комбинация этих двух интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="f9090-128">Most organizations will choose to implement a combination of the two.</span></span> <span data-ttu-id="f9090-129">Общедоступные и частные параметры обеспечивают одинаковый выигрыш в производительности, но каждый из них имеет уникальные атрибуты и преимущества.</span><span class="sxs-lookup"><span data-stu-id="f9090-129">Both public and private options provide similar performance gains, but each has unique attributes and advantages.</span></span> <span data-ttu-id="f9090-130">Дополнительные сведения об источниках общедоступных и частных сетей CDN можно узнать в статье Выбор между общедоступными и частными [источниками](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span><span class="sxs-lookup"><span data-stu-id="f9090-130">For more information about public and private CDN origins, see [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).</span></span>

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a><span data-ttu-id="f9090-131">Включение общедоступной и частной сети CDN с конфигурацией по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f9090-131">How to enable Public and Private CDN with the default configuration</span></span>
<span data-ttu-id="f9090-132">Перед внесением изменений в параметры CDN клиента необходимо убедиться, что он соответствует политикам соответствия требованиям, безопасности и конфиденциальности вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f9090-132">Before you make changes to the tenant CDN settings, you should verify that it meets compliance, security and privacy policies of your organization.</span></span>

<span data-ttu-id="f9090-133">Для получения дополнительных сведений о параметрах конфигурации или если вы уже включили сеть CDN и хотите добавить дополнительные расположения (источники), ознакомьтесь с разделом [Установка и настройка сети CDN Office 365 с помощью командной консоли SharePoint Online](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) .</span><span class="sxs-lookup"><span data-stu-id="f9090-133">For more detailed configuration settings, or if you have already enabled CDN and want to add additional locations (origins), please see the section [Set up and configure the Office 365 CDN by using the SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)</span></span>

<span data-ttu-id="f9090-134">Подключитесь к клиенту с помощью командной консоли SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="f9090-134">Connect to your tenant using the SharePoint Online Management Shell:</span></span>

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

<span data-ttu-id="f9090-135">Чтобы разрешить в Организации использование общедоступных и частных источников с конфигурацией по умолчанию, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f9090-135">To enable your organization to use both public and private origins with the default configuration, type the following command:</span></span>

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

<span data-ttu-id="f9090-136">Выходные данные этих командлетов должны выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f9090-136">Output of these cmdlets should look like the following:</span></span>

![Выходные данные команды Set — SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a><span data-ttu-id="f9090-138">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f9090-138">See also</span></span>

[<span data-ttu-id="f9090-139">Использование средства диагностики страниц для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f9090-139">Use the Page Diagnostics tool for SharePoint Online</span></span>](https://aka.ms/perftool)

[<span data-ttu-id="f9090-140">Использование сети доставки содержимого Office 365 с SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f9090-140">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)

[<span data-ttu-id="f9090-141">Сети доставки содержимого</span><span class="sxs-lookup"><span data-stu-id="f9090-141">Content Delivery Networks</span></span>](https://aka.ms/o365cdns)

[<span data-ttu-id="f9090-142">Планирование сети и настройка производительности для Office 365</span><span class="sxs-lookup"><span data-stu-id="f9090-142">Network planning and performance tuning for Office 365</span></span>](https://aka.ms/tune)

[<span data-ttu-id="f9090-143">Ряды производительности SharePoint — серия видеороликов Office 365 CDN</span><span class="sxs-lookup"><span data-stu-id="f9090-143">SharePoint Performance Series - Office 365 CDN video series</span></span>](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
