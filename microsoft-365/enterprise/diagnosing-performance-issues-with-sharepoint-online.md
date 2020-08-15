---
title: Диагностика проблем производительности в SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: В этой статье показано, как можно диагностировать распространенные проблемы с сайтом SharePoint Online с помощью средств разработчика Internet Explorer.
ms.openlocfilehash: a8a79afd860006a16874370b1124696550dab029
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693186"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="e6c97-103">Диагностика проблем производительности в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e6c97-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="e6c97-104">В этой статье показано, как можно диагностировать распространенные проблемы с сайтом SharePoint Online с помощью средств разработчика Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e6c97-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="e6c97-105">Существует три разных способа определить, что страница на сайте SharePoint Online имеет проблемы с производительностью, связанную с настройками.</span><span class="sxs-lookup"><span data-stu-id="e6c97-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="e6c97-106">Сетевой монитор панели инструментов F12</span><span class="sxs-lookup"><span data-stu-id="e6c97-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="e6c97-107">Сравнение с ненастраиваемым базовым планом</span><span class="sxs-lookup"><span data-stu-id="e6c97-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="e6c97-108">Метрики заголовков ответа SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e6c97-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="e6c97-109">В этом разделе описывается, как использовать каждый из этих методов для диагностики проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="e6c97-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="e6c97-110">Определив причину проблемы, вы можете работать над решением, используя статьи о повышении производительности SharePoint, на которых можно найти https://aka.ms/tune .</span><span class="sxs-lookup"><span data-stu-id="e6c97-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="e6c97-111">Использование панели инструментов F12 для диагностики производительности в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e6c97-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="e6c97-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="e6c97-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="e6c97-113">В этой статье мы используем Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="e6c97-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="e6c97-114">В версиях средств разработчика F12 в других браузерах есть похожие функции, хотя они могут выглядеть немного иначе.</span><span class="sxs-lookup"><span data-stu-id="e6c97-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="e6c97-115">Сведения о средствах разработчика F12 приведены в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="e6c97-115">For information on the F12 developer tools, see:</span></span>
  
- [<span data-ttu-id="e6c97-116">Новые возможности средств F12</span><span class="sxs-lookup"><span data-stu-id="e6c97-116">What's new in F12 Tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522545)

- [<span data-ttu-id="e6c97-117">Использование средств разработчика F12</span><span class="sxs-lookup"><span data-stu-id="e6c97-117">Using the F12 developer tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522546)

<span data-ttu-id="e6c97-118">Чтобы открыть инструменты разработчика, нажмите клавишу **F12** , а затем щелкните значок Wi/Fi:</span><span class="sxs-lookup"><span data-stu-id="e6c97-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![Снимок экрана со значком Wi-Fi для средств разработчика (F12)](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="e6c97-120">На вкладке **сеть** нажмите зеленую кнопку проигрывания, чтобы загрузить страницу.</span><span class="sxs-lookup"><span data-stu-id="e6c97-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="e6c97-121">Средство возвращает все файлы, запрашиваемые браузером, чтобы получить запрашиваемую страницу.</span><span class="sxs-lookup"><span data-stu-id="e6c97-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="e6c97-122">На следующем снимке экрана показан один из таких списков.</span><span class="sxs-lookup"><span data-stu-id="e6c97-122">The following screen shot shows one such list.</span></span>
  
![Снимок экрана со списком возвращенных файлов, которые браузер запрашивает для отображения страницы.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="e6c97-124">Кроме того, можно просмотреть время загрузки файлов в правой части, как показано на снимке экрана.</span><span class="sxs-lookup"><span data-stu-id="e6c97-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![Схема, показывающая время, которое требуется для загрузки запрошенных из SharePoint страниц](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="e6c97-126">Это позволяет получить визуальное представление о том, сколько времени заняло Загрузка файла.</span><span class="sxs-lookup"><span data-stu-id="e6c97-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="e6c97-127">Зеленая линия показывает, когда страница готова к отображению в браузере.</span><span class="sxs-lookup"><span data-stu-id="e6c97-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="e6c97-128">Это может привести к быстрому просмотру различных файлов, которые могут вызывать снижение загрузки страниц на сайте.</span><span class="sxs-lookup"><span data-stu-id="e6c97-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="e6c97-129">Настройка не настраиваемого базового плана для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e6c97-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="e6c97-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="e6c97-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="e6c97-131">Лучший способ определить производительность сайта слабые точки — настроить полностью готовое семейство сайтов в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e6c97-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="e6c97-132">Таким образом вы можете сравнить все различные аспекты сайта с тем, что не нужно настраивать на странице.</span><span class="sxs-lookup"><span data-stu-id="e6c97-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="e6c97-133">Домашняя страница OneDrive для бизнеса — это хороший пример отдельного семейства веб-сайтов, для которого вряд ли настроены какие-либо настройки.</span><span class="sxs-lookup"><span data-stu-id="e6c97-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="e6c97-134">Просмотр сведений о заголовках ответа SharePoint</span><span class="sxs-lookup"><span data-stu-id="e6c97-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="e6c97-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="e6c97-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="e6c97-136">В SharePoint Online можно получить доступ к сведениям, которые отправляются обратно в браузер в заголовке ответа для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="e6c97-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="e6c97-137">Наиболее полезное значение для диагностики проблем с производительностью — **SPRequestDuration**, в котором отображается время, в течение которого запрос обрабатывается на сервере.</span><span class="sxs-lookup"><span data-stu-id="e6c97-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="e6c97-138">Это поможет определить, является ли запрос очень большим и интенсивным для ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e6c97-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="e6c97-139">Это оптимальное понимание того, сколько работы выполняет сервер для обслуживания страницы.</span><span class="sxs-lookup"><span data-stu-id="e6c97-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="e6c97-140">Просмотр сведений о заголовке ответа SharePoint</span><span class="sxs-lookup"><span data-stu-id="e6c97-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="e6c97-141">Убедитесь, что у вас установлены средства F12.</span><span class="sxs-lookup"><span data-stu-id="e6c97-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="e6c97-142">Более подробную информацию о загрузке и установке этих средств можно узнать [в статье новые возможности средств F12](https://go.microsoft.com/fwlink/p/?LinkId=522545).</span><span class="sxs-lookup"><span data-stu-id="e6c97-142">For more information on downloading and installing these tools, see [What's new in F12 tools](https://go.microsoft.com/fwlink/p/?LinkId=522545).</span></span>

2. <span data-ttu-id="e6c97-143">В инструментах F12 на вкладке **сеть** нажмите зеленую кнопку проигрывания, чтобы загрузить страницу.</span><span class="sxs-lookup"><span data-stu-id="e6c97-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="e6c97-144">Щелкните один из файлов. aspx, возвращенных средством, а затем нажмите кнопку **сведения**.</span><span class="sxs-lookup"><span data-stu-id="e6c97-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![Показывает сведения заголовка ответа](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="e6c97-146">Щелкните **заголовки ответа**.</span><span class="sxs-lookup"><span data-stu-id="e6c97-146">Click **Response headers**.</span></span>

    ![Схема, показывающая URL-адрес заголовка ответа](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="e6c97-148">Что вызывает проблемы с производительностью в SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="e6c97-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="e6c97-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="e6c97-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="e6c97-150">[Параметры навигации по статье для SharePoint Online](navigation-options-for-sharepoint-online.md) показаны пример использования значения SPRequestDuration для определения того, что сложная структурная навигация привела к длительному времени для обработки страницы на сервере.</span><span class="sxs-lookup"><span data-stu-id="e6c97-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="e6c97-151">Принимая значение для базового сайта (без настройки), можно определить, занимается ли заданный файл длительное время для загрузки.</span><span class="sxs-lookup"><span data-stu-id="e6c97-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="e6c97-152">Пример, используемый в [параметрах навигации для SharePoint Online](navigation-options-for-sharepoint-online.md) , — это файл main. aspx.</span><span class="sxs-lookup"><span data-stu-id="e6c97-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="e6c97-153">В этом файле содержится большая часть кода ASP.NET, который выполняется при загрузке страницы.</span><span class="sxs-lookup"><span data-stu-id="e6c97-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="e6c97-154">В зависимости от используемого шаблона сайта может быть Start. aspx, Home. aspx, Default. aspx или другое имя, если вы настроите домашнюю страницу.</span><span class="sxs-lookup"><span data-stu-id="e6c97-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="e6c97-155">Если это число значительно выше, чем у базового сайта, это хорошо указывает на то, что на странице возникла какая-то сложность, которая вызывает проблемы с производительностью.</span><span class="sxs-lookup"><span data-stu-id="e6c97-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="e6c97-156">После того как вы определили, что проблема связана с вашим сайтом, рекомендуемый способ выяснить, что вызывает низкую производительность — устранить все возможные причины, например настройки страницы, а затем добавить их обратно на сайт по одному.</span><span class="sxs-lookup"><span data-stu-id="e6c97-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="e6c97-157">После удаления достаточной настройки, которая хорошо работает на странице, можно добавить отдельные настройки по одному.</span><span class="sxs-lookup"><span data-stu-id="e6c97-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="e6c97-158">Например, если у вас очень сложная навигация, попробуйте изменить навигацию, чтобы не показывать дочерние сайты, а затем проверьте, не изменились ли другие средства разработчика.</span><span class="sxs-lookup"><span data-stu-id="e6c97-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="e6c97-159">Если вы используете большой объем контента, попробуйте удалить их со страницы и проверить, улучшается ли эта проблема.</span><span class="sxs-lookup"><span data-stu-id="e6c97-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="e6c97-160">Если вы устраните все возможные причины и добавите их по одному, вы можете легко определить, какие функции являются крупнейшими проблемами, а затем работать над решением.</span><span class="sxs-lookup"><span data-stu-id="e6c97-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>
