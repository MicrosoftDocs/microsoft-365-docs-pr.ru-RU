---
title: Минификация и объединение в SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
audience: Admin
ms.topic: troubleshooting
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
- SPO160
- MET150
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Узнайте, как использовать методы сокращения и объединения с Web Essentials для сокращения HTTP-запросов и времени, необходимого для загрузки страниц в SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692995"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a><span data-ttu-id="08c0f-103">Минификация и объединение в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="08c0f-103">Minification and bundling in SharePoint Online</span></span>

<span data-ttu-id="08c0f-104">В этой статье описано, как использовать методы сокращения и объединения с Web Essentials, чтобы уменьшить количество HTTP-запросов и сократить время загрузки страниц в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="08c0f-104">This article describes how to use minification and bundling techniques with Web Essentials to reduce the number of HTTP requests and to reduce the time it takes to load pages in SharePoint Online.</span></span>
  
<span data-ttu-id="08c0f-105">При настройке веб-сайта можно добавить на сервер большое количество дополнительных файлов для поддержки настройки.</span><span class="sxs-lookup"><span data-stu-id="08c0f-105">When you customize your website you can end up adding a large number of extra files to the server to support the customization.</span></span> <span data-ttu-id="08c0f-106">Добавление дополнительного кода JavaScript, CSS и изображений увеличивает число HTTP-запросов на сервер, что, в свою очередь, увеличивает время, необходимое для отображения веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="08c0f-106">Adding extra JavaScript, CSS, and images increases the number of HTTP requests to the server which in turn increases the time it takes to display a web page.</span></span> <span data-ttu-id="08c0f-107">Если у вас несколько файлов одного типа, вы можете объединить эти файлы, чтобы ускорить загрузку этих файлов.</span><span class="sxs-lookup"><span data-stu-id="08c0f-107">If you have multiple files of the same type, you can bundle these files to make downloading these files faster.</span></span>
  
<span data-ttu-id="08c0f-108">Для файлов JavaScript и CSS можно также использовать подход, называемый уменьшением общего размера файлов, удалив необязательное пространство и другие символы.</span><span class="sxs-lookup"><span data-stu-id="08c0f-108">For JavaScript and CSS files, you can also use an approach called minification, where you reduce the total size of files by removing whitespace and other characters that aren't necessary.</span></span>
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a><span data-ttu-id="08c0f-109">Minification and bundling JavaScript and CSS files with Web Essentials</span><span class="sxs-lookup"><span data-stu-id="08c0f-109">Minification and bundling JavaScript and CSS files with Web Essentials</span></span>

<span data-ttu-id="08c0f-110">Вы можете использовать стороне программное обеспечение, например Web Essentials, для набора CSS-файлов и файлов JavaScript.</span><span class="sxs-lookup"><span data-stu-id="08c0f-110">You can use third-party software such as Web Essentials to bundle CSS and JavaScript files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="08c0f-111">Web Essentials — это сторонний проект, основанный на сообществе с открытым кодом.</span><span class="sxs-lookup"><span data-stu-id="08c0f-111">Web Essentials is a third-party, open-source, community-based project.</span></span> <span data-ttu-id="08c0f-112">Программное обеспечение является расширением Visual Studio 2012 и Visual Studio 2013 и не поддерживается корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="08c0f-112">The software is an extension to Visual Studio 2012 and Visual Studio 2013 and is not supported by Microsoft.</span></span> <span data-ttu-id="08c0f-113">Чтобы скачать Web Essentials, посетите веб-сайт по ссылке [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) .</span><span class="sxs-lookup"><span data-stu-id="08c0f-113">To download Web Essentials, visit the website at [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629).</span></span> 
  
<span data-ttu-id="08c0f-114">Web Essentials предлагает два вида совме-</span><span class="sxs-lookup"><span data-stu-id="08c0f-114">Web Essentials offers two forms of bundling:</span></span>
  
- <span data-ttu-id="08c0f-115">.bundle: для CSS-файлов и файлов JavaScript</span><span class="sxs-lookup"><span data-stu-id="08c0f-115">.bundle: for CSS and JavaScript files</span></span>
    
- <span data-ttu-id="08c0f-116">.sprite: для изображений (доступно только в Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="08c0f-116">.sprite: for images (only available in Visual Studio 2013)</span></span>
    
<span data-ttu-id="08c0f-117">Можно использовать Web Essentials, если у вас есть функция с некоторыми элементами фирменой настройки, на которые ссылается настраиваемая эталонная страница, например:</span><span class="sxs-lookup"><span data-stu-id="08c0f-117">You can use Web Essentials if you have an existing feature with some branding elements that are referenced inside a custom master page, such as:</span></span>
  
![Снимок экрана: элемент фирменной символики на настраиваемой эталонной странице](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 <span data-ttu-id="08c0f-119">**Создание пакета TE000127218 и CSS в Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="08c0f-119">**To create a TE000127218 and CSS bundle in Web Essentials**</span></span>
  
1. <span data-ttu-id="08c0f-120">В Visual Studio в обозревателе решений выберите файлы, которые необходимо включить в пакет.</span><span class="sxs-lookup"><span data-stu-id="08c0f-120">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="08c0f-121">Щелкните выбранные файлы правой кнопкой мыши и выберите файл пакета **Web Essentials** \> **Create JavaScript** из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="08c0f-121">Right-click the selected files and then select **Web Essentials** \> **Create JavaScript bundle file** from the context menu.</span></span> <span data-ttu-id="08c0f-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="08c0f-122">For example:</span></span> 
    
    ![Снимок экрана: параметры меню Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a><span data-ttu-id="08c0f-124">Просмотр результатов по включению файлов JavaScript и CSS</span><span class="sxs-lookup"><span data-stu-id="08c0f-124">Viewing the results of bundling JavaScript and CSS files</span></span>

<span data-ttu-id="08c0f-125">При создании пакета JavaScript и CSS Web Essentials создает XML-файл, называемый файлом рецепта, который идентифицирует файлы JavaScript и CSS, а также некоторые другие сведения о конфигурации:</span><span class="sxs-lookup"><span data-stu-id="08c0f-125">When you create a JavaScript and CSS bundle, Web Essentials creates an XML file called a recipe file that identifies the JavaScript and CSS files as well as some other configuration information:</span></span> 
  
![Снимок экрана: файл инструкций JavaScript и CSS](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
<span data-ttu-id="08c0f-127">Кроме того, если для флага minify установлено true в рецепте для пакета, файлы уменьшаются в размере, а также вместе.</span><span class="sxs-lookup"><span data-stu-id="08c0f-127">In addition, if the minify flag is set to true in the bundling recipe the files are reduced in size as well as bundled together.</span></span> <span data-ttu-id="08c0f-128">Это означает, что были созданы новые, минифицированные версии файлов JavaScript, на которые можно ссылаться на эталонной странице.</span><span class="sxs-lookup"><span data-stu-id="08c0f-128">This means that new, minified versions of the JavaScript files were created that you can reference in your master page.</span></span>
  
![Снимок экрана: флаг минификации со значением true](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
<span data-ttu-id="08c0f-130">При загрузке страницы с веб-сайта можно использовать средства разработчика из веб-браузера, такие как Internet Explorer 11, чтобы увидеть количество запросов, отправленных на сервер, и время загрузки каждого файла.</span><span class="sxs-lookup"><span data-stu-id="08c0f-130">When you load a page from your web site, you can use the developer tools from your web browser, such as Internet Explorer 11, to see the number of requests sent to the server and how long each file took to load.</span></span>
  
<span data-ttu-id="08c0f-131">На следующем рисунке по результатам загрузки файлов JavaScript и CSS перед их минификацией.</span><span class="sxs-lookup"><span data-stu-id="08c0f-131">The following figure is the result of loading the JavaScript and CSS files before minification.</span></span>
  
![Снимок экрана: скачивание 80 элементов](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
<span data-ttu-id="08c0f-133">После объединяет CSS-файлы и файлы JavaScript, число запросов, отброшенных до 74, и каждый файл занимает немного больше времени, чем исходные файлы для отдельной загрузки:</span><span class="sxs-lookup"><span data-stu-id="08c0f-133">After bundling the CSS and JavaScript files together, the number of requests dropped to 74 and each file took only slightly longer than the original files to download individually:</span></span>
  
![Снимок экрана: скачивание 74 элементов](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
<span data-ttu-id="08c0f-135">После этого размер файла пакета JavaScript значительно сокращается с 815 КБ до 365 КБ:</span><span class="sxs-lookup"><span data-stu-id="08c0f-135">After bundling, the JavaScript bundle file is reduced significantly from 815KB to 365KB:</span></span>
  
![Снимок экрана: сокращение размера скачиваемых элементов](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a><span data-ttu-id="08c0f-137">Создание спрайта изображения в единой компании</span><span class="sxs-lookup"><span data-stu-id="08c0f-137">Bundling images by creating an image sprite</span></span>

<span data-ttu-id="08c0f-138">Подобно тому, как вы объединяете файлы JavaScript и CSS, вы можете объединить множество небольших значков и других распространенных изображений в большую спрайтовую таблицу, а затем использовать CSS для раскрытия отдельных изображений.</span><span class="sxs-lookup"><span data-stu-id="08c0f-138">Similar to how you bundle JavaScript and CSS files, you can combine many small icons and other common images into a larger sprite sheet and then use CSS to reveal the individual images.</span></span> <span data-ttu-id="08c0f-139">Вместо того чтобы загружать каждое отдельное изображение, веб-браузер пользователя загружает спрайтовый лист один раз, а затем кэшировать его на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="08c0f-139">Instead of downloading each individual image, the user's web browser downloads the sprite sheet once and then caches it on the local computer.</span></span> <span data-ttu-id="08c0f-140">Это повышает производительность загрузки страниц, сокращая количество загрузок и обращений к веб-серверу.</span><span class="sxs-lookup"><span data-stu-id="08c0f-140">This improves page load performance by cutting down on the number of downloads and round trips to the web server.</span></span>
  
 <span data-ttu-id="08c0f-141">**Создание спрайта изображения в Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="08c0f-141">**To create an image sprite in Web Essentials**</span></span>
  
1. <span data-ttu-id="08c0f-142">В Visual Studio в обозревателе решений выберите файлы, которые необходимо включить в пакет.</span><span class="sxs-lookup"><span data-stu-id="08c0f-142">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="08c0f-143">Щелкните выбранные файлы правой кнопкой мыши и выберите спрайт создания изображения **Web Essentials** \>  из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="08c0f-143">Right-click the selected files and then select **Web Essentials** \> **Create image sprite** from the context menu.</span></span> <span data-ttu-id="08c0f-144">Пример:</span><span class="sxs-lookup"><span data-stu-id="08c0f-144">For example:</span></span> 
    
    ![Снимок экрана: как создать спрайт изображения](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. <span data-ttu-id="08c0f-146">Выберите расположение для сохранения спрайт-файла.</span><span class="sxs-lookup"><span data-stu-id="08c0f-146">Choose a location to save the sprite file.</span></span> <span data-ttu-id="08c0f-147">Sprite-файл — это XML-файл, в который описываются параметры и файлы в спрайте.</span><span class="sxs-lookup"><span data-stu-id="08c0f-147">The .sprite file is an XML file that describes the settings and files in the sprite.</span></span> <span data-ttu-id="08c0f-148">На следующих рисунках приводится пример PNG-файла спрайта и соответствующего XML-файла sprite.</span><span class="sxs-lookup"><span data-stu-id="08c0f-148">The following figures show an example of a sprite PNG file and its corresponding .sprite XML file.</span></span>
    
    ![Снимок экрана: файл спрайта](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Снимок экрана: XML-файл спрайта](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

