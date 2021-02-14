---
title: Оптимизация изображений на современных страницах сайтов SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Узнайте, как использовать средства, включенные в SharePoint Online, для оптимизации изображений на современных страницах сайтов SharePoint Online.
ms.openlocfilehash: 09122dfd0bc832cf9a09cfb05bf0540e323797d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693448"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a><span data-ttu-id="8faa9-103">Оптимизация изображений на современных страницах сайтов SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8faa9-103">Optimize images in SharePoint Online modern site pages</span></span>

<span data-ttu-id="8faa9-104">С помощью этой статьи вы узнаете, как оптимизировать изображения на современных страницах сайтов SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8faa9-104">This article will help you understand how to optimize images in SharePoint Online modern site pages.</span></span>

<span data-ttu-id="8faa9-105">Сведения об оптимизации изображений на классических сайтах публикации см. в статье [Оптимизация изображений для SharePoint Online](image-optimization-for-sharepoint-online.md).</span><span class="sxs-lookup"><span data-stu-id="8faa9-105">For information about optimizing images in classic publishing sites, see [Image optimization for SharePoint Online](image-optimization-for-sharepoint-online.md)..</span></span>

>[!NOTE]
><span data-ttu-id="8faa9-106">Дополнительные сведения о производительности на современных порталах SharePoint Online см. в статье [Производительность в современном интерфейсе SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="8faa9-106">For more information about performance in SharePoint Online modern portals, see [Performance in the modern SharePoint experience](https://docs.microsoft.com/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a><span data-ttu-id="8faa9-107">Использование средства диагностики страниц SharePoint для анализа оптимизации изображений</span><span class="sxs-lookup"><span data-stu-id="8faa9-107">Use the Page Diagnostics for SharePoint tool to analyze image optimization</span></span>

<span data-ttu-id="8faa9-108">Средство "Диагностика страниц SharePoint" — это браузерное расширение для браузеров Chrome и новой версии Microsoft Edge (https://www.microsoft.com/edge), анализирующее страницы современных и классических сайтов публикаций SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8faa9-108">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="8faa9-109">Это средство предоставляет отчет о каждой проанализированной странице, показывающий, как она работает при заданных критериях производительности.</span><span class="sxs-lookup"><span data-stu-id="8faa9-109">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="8faa9-110">Чтобы установить и изучить средство диагностики страниц SharePoint, ознакомьтесь со статьей [Использование средства диагностики страниц SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="8faa9-110">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="8faa9-111">Средство диагностики страниц работает только в SharePoint Online, и его нельзя использовать на системной странице SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8faa9-111">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="8faa9-112">При анализе современного сайта SharePoint с помощью средства диагностики страниц SharePoint вы можете просматривать сведения о больших изображениях в панели _Диагностические тесты_.</span><span class="sxs-lookup"><span data-stu-id="8faa9-112">When you analyze a SharePoint modern site with the Page Diagnostics for SharePoint tool, you can see information about large images in the _Diagnostic tests_ pane.</span></span>

<span data-ttu-id="8faa9-113">Возможные результаты:</span><span class="sxs-lookup"><span data-stu-id="8faa9-113">Possible results include:</span></span>

- <span data-ttu-id="8faa9-114">**Внимание!** (красный цвет). Страница содержит **одно или несколько** изображений размером более 300 КБ</span><span class="sxs-lookup"><span data-stu-id="8faa9-114">**Attention required** (red): The page contains **one or more** images over 300KB in size</span></span>
- <span data-ttu-id="8faa9-115">**Действия не требуются** (зеленый цвет). Страница не содержит изображений размером более 300 КБ</span><span class="sxs-lookup"><span data-stu-id="8faa9-115">**No action required** (green): The page contains no images over 300KB in size</span></span>

<span data-ttu-id="8faa9-116">Если результат **Обнаружены большие изображения** отображается в разделе результатов **Внимание!**, вы можете щелкнуть его для просмотра дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="8faa9-116">If the **Large images detected** result appears in the **Attention required** section of the results, you can click the result to see additional details.</span></span>

![Результаты средства диагностики страниц](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a><span data-ttu-id="8faa9-118">Исправление проблем с большими изображениями</span><span class="sxs-lookup"><span data-stu-id="8faa9-118">Remediate large image issues</span></span>

<span data-ttu-id="8faa9-119">Если страница содержит изображения с размером более 300 КБ, щелкните результат **Обнаружены большие изображения**, чтобы увидеть, какие изображения являются слишком большими.</span><span class="sxs-lookup"><span data-stu-id="8faa9-119">If a page contains images over 300KB in size, select the **Large images detected** result to see which images are too large.</span></span> <span data-ttu-id="8faa9-120">На современных страницах SharePoint Online представления изображений создаются автоматически с подбором размеров с учетом окна браузера и разрешения монитора клиента.</span><span class="sxs-lookup"><span data-stu-id="8faa9-120">In modern SharePoint Online pages, renditions of images are automatically provided and sized depending on the size of the browser window and the resolution of the client monitor.</span></span> <span data-ttu-id="8faa9-121">Перед отправкой в SharePoint Online всегда следует оптимизировать изображения для использования в Интернете.</span><span class="sxs-lookup"><span data-stu-id="8faa9-121">You should always optimize images for web use prior to upload to SharePoint Online.</span></span> <span data-ttu-id="8faa9-122">Размеры и разрешение очень больших изображений автоматически уменьшаются, что может привести к непредвиденным параметрам представления.</span><span class="sxs-lookup"><span data-stu-id="8faa9-122">Very large images will be automatically reduced in size and resolution which can result in unexpected rendering characteristics.</span></span>

<span data-ttu-id="8faa9-123">Перед внесением изменений в страницы для исправления проблем с производительностью запомните время загрузки страницы в результатах анализа.</span><span class="sxs-lookup"><span data-stu-id="8faa9-123">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="8faa9-124">Снова запустите средство после внесения изменений, чтобы узнать, соответствует ли новый результат базовому стандарту, и проверить, сократилось ли время загрузки.</span><span class="sxs-lookup"><span data-stu-id="8faa9-124">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Анализ времени загрузки страницы](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="8faa9-126">Время загрузки страницы зависит от множества факторов, например от загрузки сети, времени суток и других переменных условий.</span><span class="sxs-lookup"><span data-stu-id="8faa9-126">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="8faa9-127">Следует несколько раз проверить время загрузки страницы до и после внесения изменений, чтобы получить среднестатистические данные.</span><span class="sxs-lookup"><span data-stu-id="8faa9-127">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8faa9-128">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8faa9-128">Related topics</span></span>

[<span data-ttu-id="8faa9-129">Настройка производительности SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8faa9-129">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="8faa9-130">Настройка производительности Office 365</span><span class="sxs-lookup"><span data-stu-id="8faa9-130">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="8faa9-131">Производительность в современном интерфейсе SharePoint</span><span class="sxs-lookup"><span data-stu-id="8faa9-131">Performance in the modern SharePoint experience</span></span>](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[<span data-ttu-id="8faa9-132">Сети доставки содержимого</span><span class="sxs-lookup"><span data-stu-id="8faa9-132">Content delivery networks</span></span>](content-delivery-networks.md)

[<span data-ttu-id="8faa9-133">Использование сети доставки содержимого Office 365 с SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8faa9-133">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
