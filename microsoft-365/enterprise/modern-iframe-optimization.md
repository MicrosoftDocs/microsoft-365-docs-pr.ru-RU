---
title: Оптимизация окон iFrame на страницах современных и классических сайтов публикаций SharePoint Online
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
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Узнайте, как оптимизировать производительность iFrame на современных и классических страницах сайта публикаций SharePoint Online.
ms.openlocfilehash: d6e9aefa23972589c752540959b17f5d20ed0889
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923066"
---
# <a name="optimize-iframes-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a><span data-ttu-id="4b398-103">Оптимизация окон iFrame на страницах современных и классических сайтов публикаций SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4b398-103">Optimize iFrames in SharePoint Online modern and classic publishing site pages</span></span>

<span data-ttu-id="4b398-104">Окна iFrame можно использовать для предварительного просмотра расширенного контента, например видео или других файлов мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="4b398-104">iFrames can be useful for previewing rich content such as videos or other media.</span></span> <span data-ttu-id="4b398-105">Так как iFrame загружает отдельную страницу на странице сайта SharePoint, содержимое, загружаемое в iFrame, может содержать крупные изображения, видео или другие элементы, которые часто увеличивают общее время загрузки страниц и ограничивают управление страницей.</span><span class="sxs-lookup"><span data-stu-id="4b398-105">However, because iFrames load a separate page within the SharePoint site page, content loaded in the iFrame could contain large images, videos or other elements that can contribute to overall page load times and that you cannot control on the page.</span></span> <span data-ttu-id="4b398-106">Из этой статьи вы узнаете, как определять, насколько используемые на страницах окна iFrame влияют на задержку, распознаваемую конечным пользователем, и как устранять распространенные проблемы.</span><span class="sxs-lookup"><span data-stu-id="4b398-106">This article will help you understand how to determine how iFrames in your pages affect user perceived latency, and how to remediate common issues.</span></span>

>[!NOTE]
><span data-ttu-id="4b398-107">Дополнительные сведения о производительности на современных сайтах SharePoint Online см. в статье [Производительность в современном интерфейсе SharePoint](/sharepoint/modern-experience-performance).</span><span class="sxs-lookup"><span data-stu-id="4b398-107">For more information about performance in SharePoint Online modern sites, see [Performance in the modern SharePoint experience](/sharepoint/modern-experience-performance).</span></span>

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts-using-iframes"></a><span data-ttu-id="4b398-108">Применение средства диагностики страниц SharePoint для анализа веб-частей, использующих окна iFrame</span><span class="sxs-lookup"><span data-stu-id="4b398-108">Use the Page Diagnostics for SharePoint tool to analyze web parts using iFrames</span></span>

<span data-ttu-id="4b398-109">Средство "Диагностика страниц SharePoint" — это браузерное расширение для браузеров Chrome и новой версии Microsoft Edge (https://www.microsoft.com/edge), анализирующее страницы современных и классических сайтов публикаций SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4b398-109">The Page Diagnostics for SharePoint tool is a browser extension for the new Microsoft Edge (https://www.microsoft.com/edge) and Chrome browsers that analyzes both SharePoint Online modern portal and classic publishing site pages.</span></span> <span data-ttu-id="4b398-110">Это средство предоставляет отчет о каждой проанализированной странице, показывающий, как она работает при заданных критериях производительности.</span><span class="sxs-lookup"><span data-stu-id="4b398-110">The tool provides a report for each analyzed page showing how the page performs against a defined set of performance criteria.</span></span> <span data-ttu-id="4b398-111">Чтобы установить и изучить средство диагностики страниц SharePoint, ознакомьтесь со статьей [Использование средства диагностики страниц SharePoint Online](page-diagnostics-for-spo.md).</span><span class="sxs-lookup"><span data-stu-id="4b398-111">To install and learn about the Page Diagnostics for SharePoint tool, visit [Use the Page Diagnostics tool for SharePoint Online](page-diagnostics-for-spo.md).</span></span>

>[!NOTE]
><span data-ttu-id="4b398-112">Средство диагностики страниц работает только в SharePoint Online, и его нельзя использовать на системной странице SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4b398-112">The Page Diagnostics tool only works for SharePoint Online, and cannot be used on a SharePoint system page.</span></span>

<span data-ttu-id="4b398-113">При анализе сайта SharePoint с помощью средства диагностики страниц SharePoint вы можете просматривать сведения о веб-частях, содержащих окна iFrame, в области _Диагностические тесты_.</span><span class="sxs-lookup"><span data-stu-id="4b398-113">When you analyze a SharePoint site page with the Page Diagnostics for SharePoint tool, you can see information about web parts containing iFrames in the _Diagnostic tests_ pane.</span></span> <span data-ttu-id="4b398-114">Для современных и классических страниц базовый показатель будет одинаковым.</span><span class="sxs-lookup"><span data-stu-id="4b398-114">The baseline metric is the same for modern and classic pages.</span></span>

<span data-ttu-id="4b398-115">Возможные результаты:</span><span class="sxs-lookup"><span data-stu-id="4b398-115">Possible results include:</span></span>

- <span data-ttu-id="4b398-116">**Внимание!** (красный цвет) Страница содержит **три или более** веб-частей, использующие окна iFrame</span><span class="sxs-lookup"><span data-stu-id="4b398-116">**Attention required** (red): The page contains **three or more** web parts using iFrames</span></span>
- <span data-ttu-id="4b398-117">**Возможна оптимизация** (желтый цвет): Страница содержит **одну или две** веб-части, использующие блоки iFrame</span><span class="sxs-lookup"><span data-stu-id="4b398-117">**Improvement opportunities** (yellow): The page contains **one or two** web parts using iFrames</span></span>
- <span data-ttu-id="4b398-118">**Действия не требуются** (зеленый цвет). Страница не содержит веб-части, использующие блоки iFrame</span><span class="sxs-lookup"><span data-stu-id="4b398-118">**No action required** (green): The page contains no web parts using iFrames</span></span>

<span data-ttu-id="4b398-119">В случае **Обнаружены веб-части, использующие блоки iFrame,** в разделе «Результаты» появятся уведомления **Возможна оптимизация** или **Внимание!**, при нажатии на которые будут показаны выявленные веб-части.</span><span class="sxs-lookup"><span data-stu-id="4b398-119">If the **Web parts using iFrames detected** result appears in either the **Improvement opportunities** or **Attention required)** section of the results, you can click the result to see the web parts that contain iFrames.</span></span>

![Результаты диагностики страниц](../media/modern-portal-optimization/pagediag-iframe-yellow.png)

## <a name="remediate-iframe-performance-issues"></a><span data-ttu-id="4b398-121">Устранение проблем производительности окон iFrame</span><span class="sxs-lookup"><span data-stu-id="4b398-121">Remediate iFrame performance issues</span></span>

<span data-ttu-id="4b398-122">Определяйте, какие веб-части содержат элементы iFrame и могут замедлять загрузку страниц, используя результаты средства диагностики страниц **Обнаружены веб-части, использующие окна iFrame**.</span><span class="sxs-lookup"><span data-stu-id="4b398-122">Use the **Web parts using iFrames detected** result in the Page Diagnostic tool to determine which web parts contain iFrames and may be contributing to slow page load times.</span></span>

<span data-ttu-id="4b398-123">Окна iFrame всегда работают медленно, так как они загружают отдельную внешнюю страницу со всем связанным с ней контентом, например JavaScript, CSS и элементами платформы, потенциально увеличивая служебные данные страницы сайта в два раза или более.</span><span class="sxs-lookup"><span data-stu-id="4b398-123">iFrames are inherently slow because they load a separate external page including all associated content such as javascript, CSS and framework elements, potentially increasing the overhead of the site page by a factor of two or more.</span></span>

<span data-ttu-id="4b398-124">Чтобы обеспечить оптимальное использование iFrame, следуйте указанным ниже рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="4b398-124">Follow the guidance below to ensure optimal use of iFrames.</span></span>

- <span data-ttu-id="4b398-125">По возможности вместо окон iFrame используйте изображения, если предварительный просмотр слишком мал для запуска или не интерактивен.</span><span class="sxs-lookup"><span data-stu-id="4b398-125">When possible, use images instead of iFrames if the preview is small to begin with or non-interactive.</span></span>
- <span data-ttu-id="4b398-126">При необходимости использовать элементы iFrame минимизируйте их количество и (или) удалите из окна просмотра.</span><span class="sxs-lookup"><span data-stu-id="4b398-126">If iFrames must be used, minimize the number and/or move them out of the viewport.</span></span>
- <span data-ttu-id="4b398-127">Внедренные файлы Office, такие как Word, Excel и PowerPoint, остаются интерактивными, но медленно загружаются.</span><span class="sxs-lookup"><span data-stu-id="4b398-127">Embedded Office files like Word, Excel and PowerPoint are interactive, but are slow to load.</span></span> <span data-ttu-id="4b398-128">Эскизы изображений со ссылкой на полный документ обычно выполняются лучше.</span><span class="sxs-lookup"><span data-stu-id="4b398-128">Image thumbnails with a link to the full document will often perform better.</span></span>
- <span data-ttu-id="4b398-129">Внедренные видео YouTube и ленты Twitter успешнее работают в окнах iFrame, но эти виды объектов следует использовать обдуманно.</span><span class="sxs-lookup"><span data-stu-id="4b398-129">Embedded YouTube videos and Twitter feeds tend to perform better in iFrames, but use these kinds of embeds judiciously.</span></span>
- <span data-ttu-id="4b398-130">Исключением являются изолированные веб-части, но их количество в окне просмотра должно быть минимальным.</span><span class="sxs-lookup"><span data-stu-id="4b398-130">Isolated web parts are a reasonable exception, but minimize their number and placement in the viewport.</span></span>
- <span data-ttu-id="4b398-131">Если iFrame не находится в окне просмотра, можно использовать функцию _IntersectionObserver_ для отсрочки отображения окна iFrame, пока оно само не появится.</span><span class="sxs-lookup"><span data-stu-id="4b398-131">If an iFrame is located out of the viewport, consider using an _IntersectionObserver_ to delay rendering the iFrame until it comes into view.</span></span>

<span data-ttu-id="4b398-132">Перед изменением в страниц для устранения проблем производительности запомните время загрузки страницы по результатам анализа.</span><span class="sxs-lookup"><span data-stu-id="4b398-132">Before you make page revisions to remediate performance issues, make a note of the page load time in the analysis results.</span></span> <span data-ttu-id="4b398-133">Снова запустите средство после внесения изменений, чтобы узнать, соответствует ли новый результат базовому стандарту, и проверить, сократилось ли время загрузки.</span><span class="sxs-lookup"><span data-stu-id="4b398-133">Run the tool again after your revision to see if the new result is within the baseline standard, and check the new page load time to see if there was an improvement.</span></span>

![Анализ времени загрузки страницы](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
><span data-ttu-id="4b398-135">Время загрузки страницы зависит от множества факторов, например от загрузки сети, времени суток и других переменных условий.</span><span class="sxs-lookup"><span data-stu-id="4b398-135">Page load time can vary based on a variety of factors such as network load, time of day, and other transient conditions.</span></span> <span data-ttu-id="4b398-136">Следует несколько раз проверить время загрузки страницы до и после внесения изменений, чтобы получить среднестатистические данные.</span><span class="sxs-lookup"><span data-stu-id="4b398-136">You should test page load time a few times before and after making changes to help you average the results.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4b398-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4b398-137">Related topics</span></span>

[<span data-ttu-id="4b398-138">Настройка производительности SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4b398-138">Tune SharePoint Online performance</span></span>](tune-sharepoint-online-performance.md)

[<span data-ttu-id="4b398-139">Настройка производительности Office 365</span><span class="sxs-lookup"><span data-stu-id="4b398-139">Tune Office 365 performance</span></span>](tune-microsoft-365-performance.md)

[<span data-ttu-id="4b398-140">Производительность в современном интерфейсе SharePoint</span><span class="sxs-lookup"><span data-stu-id="4b398-140">Performance in the modern SharePoint experience</span></span>](/sharepoint/modern-experience-performance)