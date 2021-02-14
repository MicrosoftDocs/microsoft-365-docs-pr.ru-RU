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
description: В этой статье показано, как диагностировать распространенные проблемы с сайтом SharePoint Online с помощью средств разработчика Internet Explorer.
ms.openlocfilehash: a8a79afd860006a16874370b1124696550dab029
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693186"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="ab13e-103">Диагностика проблем производительности в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ab13e-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="ab13e-104">В этой статье показано, как диагностировать распространенные проблемы с сайтом SharePoint Online с помощью средств разработчика Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ab13e-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="ab13e-105">Существует три различных способа определить, что страница на сайте SharePoint Online имеет проблемы с производительностью при настройке.</span><span class="sxs-lookup"><span data-stu-id="ab13e-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="ab13e-106">Сетевой монитор панели инструментов F12</span><span class="sxs-lookup"><span data-stu-id="ab13e-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="ab13e-107">Сравнение с ненастройными базовыми показателями</span><span class="sxs-lookup"><span data-stu-id="ab13e-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="ab13e-108">Показатели заголала ответа SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ab13e-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="ab13e-109">В этом разделе описывается, как использовать каждый из этих методов для диагностики проблем с производительностью.</span><span class="sxs-lookup"><span data-stu-id="ab13e-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="ab13e-110">Выявив причину проблемы, вы можете приработать решение, используя статьи о повышении производительности SharePoint, которые можно https://aka.ms/tune найти.</span><span class="sxs-lookup"><span data-stu-id="ab13e-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="ab13e-111">Использование панели инструментов F12 для диагностики производительности в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ab13e-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="ab13e-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ab13e-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ab13e-113">В этой статье мы используем Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="ab13e-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="ab13e-114">Версии средств разработчика F12 в других браузерах имеют похожие функции, хотя они могут выглядеть немного иначе.</span><span class="sxs-lookup"><span data-stu-id="ab13e-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="ab13e-115">Сведения о средствах разработчика F12 см. в:</span><span class="sxs-lookup"><span data-stu-id="ab13e-115">For information on the F12 developer tools, see:</span></span>
  
- [<span data-ttu-id="ab13e-116">Новые возможности средств F12</span><span class="sxs-lookup"><span data-stu-id="ab13e-116">What's new in F12 Tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522545)

- [<span data-ttu-id="ab13e-117">Использование средств разработчика F12</span><span class="sxs-lookup"><span data-stu-id="ab13e-117">Using the F12 developer tools</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=522546)

<span data-ttu-id="ab13e-118">Чтобы вывести средства разработчика, нажмите **F12** и нажмите значок Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="ab13e-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![Снимок экрана со значком Wi-Fi для средств разработчика (F12)](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="ab13e-120">На **вкладке "Сеть"** нажмите зеленую кнопку воспроизведения, чтобы загрузить страницу.</span><span class="sxs-lookup"><span data-stu-id="ab13e-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="ab13e-121">Средство возвращает все файлы, которые браузер запрашивает, чтобы получить запрашиваемую страницу.</span><span class="sxs-lookup"><span data-stu-id="ab13e-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="ab13e-122">На следующем снимке экрана показан один такой список.</span><span class="sxs-lookup"><span data-stu-id="ab13e-122">The following screen shot shows one such list.</span></span>
  
![Снимок экрана со списком возвращенных файлов, которые браузер запрашивает для отображения страницы.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="ab13e-124">Вы также можете увидеть время загрузки файлов в правой части экрана, как показано на этом снимке экрана.</span><span class="sxs-lookup"><span data-stu-id="ab13e-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![Схема, показывающая время, которое требуется для загрузки запрошенных из SharePoint страниц](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="ab13e-126">Это дает визуальное представление о том, сколько времени потребовалось файлу для загрузки.</span><span class="sxs-lookup"><span data-stu-id="ab13e-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="ab13e-127">Зеленая линия представляет, когда страница готова к отрисовки браузером.</span><span class="sxs-lookup"><span data-stu-id="ab13e-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="ab13e-128">Это может дать возможность быстро просмотреть различные файлы, которые могут вызывать медленную загрузку страниц на сайте.</span><span class="sxs-lookup"><span data-stu-id="ab13e-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="ab13e-129">Настройка ненастройного базового плана для SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ab13e-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="ab13e-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ab13e-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ab13e-131">Лучший способ определить слабые места производительности сайта — это настроить в SharePoint Online полностью затейное коллекцию веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="ab13e-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="ab13e-132">Таким образом можно сравнить все различные аспекты сайта с тем, что вы получите без настройки на странице.</span><span class="sxs-lookup"><span data-stu-id="ab13e-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="ab13e-133">Домашняя страница OneDrive для бизнеса является хорошим примером отдельного коллекции сайтов, которое вряд ли будет иметь какие-либо настройки.</span><span class="sxs-lookup"><span data-stu-id="ab13e-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="ab13e-134">Просмотр сведений о загонке ответа SharePoint</span><span class="sxs-lookup"><span data-stu-id="ab13e-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="ab13e-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ab13e-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ab13e-136">В SharePoint Online можно получить доступ к сведениям, которые отправляются обратно в браузер в загонке ответа для каждого файла.</span><span class="sxs-lookup"><span data-stu-id="ab13e-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="ab13e-137">Наиболее полезным значением для диагностики проблем производительности является **SPRequestDuration,** который отображает время обработки запроса на сервере.</span><span class="sxs-lookup"><span data-stu-id="ab13e-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="ab13e-138">Это поможет определить, является ли запрос очень интенсивным и ресурсоемким.</span><span class="sxs-lookup"><span data-stu-id="ab13e-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="ab13e-139">Это лучший анализ того, сколько работы сервер делает для обслуживания страницы.</span><span class="sxs-lookup"><span data-stu-id="ab13e-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="ab13e-140">Просмотр сведений о загонке ответа SharePoint</span><span class="sxs-lookup"><span data-stu-id="ab13e-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="ab13e-141">Убедитесь, что установлены средства F12.</span><span class="sxs-lookup"><span data-stu-id="ab13e-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="ab13e-142">Дополнительные сведения о загрузке и установке этих средств см. в новых средствах [F12.](https://go.microsoft.com/fwlink/p/?LinkId=522545)</span><span class="sxs-lookup"><span data-stu-id="ab13e-142">For more information on downloading and installing these tools, see [What's new in F12 tools](https://go.microsoft.com/fwlink/p/?LinkId=522545).</span></span>

2. <span data-ttu-id="ab13e-143">В средстве F12 на **вкладке** "Сеть" нажмите зеленую кнопку воспроизведения, чтобы загрузить страницу.</span><span class="sxs-lookup"><span data-stu-id="ab13e-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="ab13e-144">Щелкните один из ASPX-файлов, возвращенных средством, а затем щелкните **"СВЕДЕНИЯ".**</span><span class="sxs-lookup"><span data-stu-id="ab13e-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![Показывает сведения заголовка ответа](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="ab13e-146">Щелкните **заглавные кнопки ответа.**</span><span class="sxs-lookup"><span data-stu-id="ab13e-146">Click **Response headers**.</span></span>

    ![Схема, показывающая URL-адрес заголовка ответа](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="ab13e-148">Что вызывает проблемы с производительностью в SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="ab13e-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="ab13e-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ab13e-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ab13e-150">В статье "Параметры навигации для [SharePoint Online"](navigation-options-for-sharepoint-online.md) показан пример использования значения SPRequestDuration, чтобы определить, что сложная структурная навигация приводит к длительной обработке страницы на сервере.</span><span class="sxs-lookup"><span data-stu-id="ab13e-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="ab13e-151">Принимая значение для базового сайта (без настройки), можно определить, загружается ли какой-либо файл длительное время.</span><span class="sxs-lookup"><span data-stu-id="ab13e-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="ab13e-152">В примере, используемом в [параметрах навигации для SharePoint Online,](navigation-options-for-sharepoint-online.md) используется основной ASPX-файл.</span><span class="sxs-lookup"><span data-stu-id="ab13e-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="ab13e-153">Этот файл содержит большую часть ASP.NET кода, который выполняется для загрузки страницы.</span><span class="sxs-lookup"><span data-stu-id="ab13e-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="ab13e-154">В зависимости от используемого шаблона сайта это может быть start.aspx, home.aspx, default.aspx или другое имя при настройке домашней страницы.</span><span class="sxs-lookup"><span data-stu-id="ab13e-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="ab13e-155">Если это число значительно превышает базовый сайт, это хороший признак того, что на странице происходит что-то сложное, что вызывает проблемы с производительностью.</span><span class="sxs-lookup"><span data-stu-id="ab13e-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="ab13e-156">После того как вы определили проблему, характерную для вашего сайта, рекомендуемый способ выяснить, что приводит к низкой производительности, — устранить все возможные причины, например настройки страниц, а затем добавить их на сайт по одному.</span><span class="sxs-lookup"><span data-stu-id="ab13e-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="ab13e-157">После удаления достаточного количества настроек, которые хорошо работает страница, можно добавить отдельные настройки по одному.</span><span class="sxs-lookup"><span data-stu-id="ab13e-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="ab13e-158">Например, если у вас очень сложная навигация, попробуйте изменить навигацию так, чтобы она не показывать вложенные сайты, проверьте средства разработчика, чтобы узнать, имеет ли это значение.</span><span class="sxs-lookup"><span data-stu-id="ab13e-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="ab13e-159">Или если у вас есть большой объем контента, попробуйте удалить их со страницы и посмотреть, улучшит ли это.</span><span class="sxs-lookup"><span data-stu-id="ab13e-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="ab13e-160">Если устранить все возможные причины и добавить их по одному, можно легко определить, какие функции являются самой большой проблемой, а затем двигаться к решению.</span><span class="sxs-lookup"><span data-stu-id="ab13e-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>
