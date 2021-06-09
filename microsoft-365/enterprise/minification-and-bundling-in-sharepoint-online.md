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
description: Узнайте, как использовать методы минирования и комплектации с помощью веб-элементов для уменьшения запросов http и времени загрузки страниц в SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692995"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a><span data-ttu-id="9c3ed-103">Минификация и объединение в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9c3ed-103">Minification and bundling in SharePoint Online</span></span>

<span data-ttu-id="9c3ed-104">В этой статье описывается использование методов минирования и комплектации с веб-сайтами для уменьшения количества запросов HTTP и сокращения времени загрузки страниц в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-104">This article describes how to use minification and bundling techniques with Web Essentials to reduce the number of HTTP requests and to reduce the time it takes to load pages in SharePoint Online.</span></span>
  
<span data-ttu-id="9c3ed-105">При настройке веб-сайта можно добавить на сервер большое количество дополнительных файлов для поддержки настройки.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-105">When you customize your website you can end up adding a large number of extra files to the server to support the customization.</span></span> <span data-ttu-id="9c3ed-106">Добавление дополнительных JavaScript, CSS и изображений увеличивает количество запросов HTTP на сервер, что, в свою очередь, увеличивает время отображения веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-106">Adding extra JavaScript, CSS, and images increases the number of HTTP requests to the server which in turn increases the time it takes to display a web page.</span></span> <span data-ttu-id="9c3ed-107">Если у вас есть несколько файлов одного типа, вы можете объединить эти файлы, чтобы сделать загрузку этих файлов быстрее.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-107">If you have multiple files of the same type, you can bundle these files to make downloading these files faster.</span></span>
  
<span data-ttu-id="9c3ed-108">Для файлов JavaScript и CSS можно также использовать подход под названием minification, в котором можно уменьшить общий размер файлов, удалив белое пространство и другие не нужные символы.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-108">For JavaScript and CSS files, you can also use an approach called minification, where you reduce the total size of files by removing whitespace and other characters that aren't necessary.</span></span>
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a><span data-ttu-id="9c3ed-109">Minification and bundling JavaScript and CSS files with Web Essentials</span><span class="sxs-lookup"><span data-stu-id="9c3ed-109">Minification and bundling JavaScript and CSS files with Web Essentials</span></span>

<span data-ttu-id="9c3ed-110">Сторонние программы, такие как Web Essentials, можно использовать для комплекта CSS и JavaScript-файлов.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-110">You can use third-party software such as Web Essentials to bundle CSS and JavaScript files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9c3ed-111">Web Essentials — это сторонний проект с открытым исходным кодом, основанный на сообществе.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-111">Web Essentials is a third-party, open-source, community-based project.</span></span> <span data-ttu-id="9c3ed-112">Программное обеспечение является расширением Visual Studio 2012 и Visual Studio 2013 и не поддерживается Корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-112">The software is an extension to Visual Studio 2012 and Visual Studio 2013 and is not supported by Microsoft.</span></span> <span data-ttu-id="9c3ed-113">Чтобы скачать web Essentials, посетите веб-сайт по [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) ссылке .</span><span class="sxs-lookup"><span data-stu-id="9c3ed-113">To download Web Essentials, visit the website at [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629).</span></span> 
  
<span data-ttu-id="9c3ed-114">Web Essentials предлагает две формы комплектов:</span><span class="sxs-lookup"><span data-stu-id="9c3ed-114">Web Essentials offers two forms of bundling:</span></span>
  
- <span data-ttu-id="9c3ed-115">.bundle: для файлов CSS и JavaScript</span><span class="sxs-lookup"><span data-stu-id="9c3ed-115">.bundle: for CSS and JavaScript files</span></span>
    
- <span data-ttu-id="9c3ed-116">.sprite: для изображений (доступны только в Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="9c3ed-116">.sprite: for images (only available in Visual Studio 2013)</span></span>
    
<span data-ttu-id="9c3ed-117">Можно использовать Web Essentials, если у вас есть существующая функция с некоторыми элементами брендинга, которые ссылались на пользовательские основные страницы, такие как:</span><span class="sxs-lookup"><span data-stu-id="9c3ed-117">You can use Web Essentials if you have an existing feature with some branding elements that are referenced inside a custom master page, such as:</span></span>
  
![Снимок экрана: элемент фирменной символики на настраиваемой эталонной странице](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 <span data-ttu-id="9c3ed-119">**Создание пакета TE000127218 и CSS в Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="9c3ed-119">**To create a TE000127218 and CSS bundle in Web Essentials**</span></span>
  
1. <span data-ttu-id="9c3ed-120">В Visual Studio в обозревателе решений выберите файлы, которые необходимо включить в пакет.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-120">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="9c3ed-121">Щелкните правой кнопкой мыши выбранные файлы, а затем выберите файл пакетов **Web Essentials** \> **Create JavaScript из** контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-121">Right-click the selected files and then select **Web Essentials** \> **Create JavaScript bundle file** from the context menu.</span></span> <span data-ttu-id="9c3ed-122">Пример.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-122">For example:</span></span> 
    
    ![Снимок экрана: параметры меню Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a><span data-ttu-id="9c3ed-124">Просмотр результатов комплектовки файлов JavaScript и CSS</span><span class="sxs-lookup"><span data-stu-id="9c3ed-124">Viewing the results of bundling JavaScript and CSS files</span></span>

<span data-ttu-id="9c3ed-125">При создании пакета JavaScript и CSS Web Essentials создает XML-файл, называемый файлом рецептов, который идентифицирует файлы JavaScript и CSS, а также некоторые другие сведения о конфигурации:</span><span class="sxs-lookup"><span data-stu-id="9c3ed-125">When you create a JavaScript and CSS bundle, Web Essentials creates an XML file called a recipe file that identifies the JavaScript and CSS files as well as some other configuration information:</span></span> 
  
![Снимок экрана: файл инструкций JavaScript и CSS](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
<span data-ttu-id="9c3ed-127">Кроме того, если в рецепте комплектов установлен true флага minify, файлы уменьшаются в размерах, а также в комплекте.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-127">In addition, if the minify flag is set to true in the bundling recipe the files are reduced in size as well as bundled together.</span></span> <span data-ttu-id="9c3ed-128">Это означает, что были созданы новые, заминированная версия файлов JavaScript, на которые можно ссылаться на своей странице.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-128">This means that new, minified versions of the JavaScript files were created that you can reference in your master page.</span></span>
  
![Снимок экрана: флаг минификации со значением true](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
<span data-ttu-id="9c3ed-130">При загрузке страницы с веб-сайта можно использовать средства разработчика из вашего веб-браузера, такие как Internet Explorer 11, чтобы увидеть количество отправленных на сервер запросов и время загрузки каждого файла.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-130">When you load a page from your web site, you can use the developer tools from your web browser, such as Internet Explorer 11, to see the number of requests sent to the server and how long each file took to load.</span></span>
  
<span data-ttu-id="9c3ed-131">Следующая цифра — это результат загрузки файлов JavaScript и CSS перед минификацией.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-131">The following figure is the result of loading the JavaScript and CSS files before minification.</span></span>
  
![Снимок экрана: скачивание 80 элементов](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
<span data-ttu-id="9c3ed-133">После объединяет CSS и JavaScript файлы, количество запросов сократилось до 74, и каждый файл занимает немного больше времени, чем исходные файлы, чтобы скачать по отдельности:</span><span class="sxs-lookup"><span data-stu-id="9c3ed-133">After bundling the CSS and JavaScript files together, the number of requests dropped to 74 and each file took only slightly longer than the original files to download individually:</span></span>
  
![Снимок экрана: скачивание 74 элементов](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
<span data-ttu-id="9c3ed-135">После комплектовки файл пакета JavaScript значительно сокращается с 815 КБ до 365 КБ:</span><span class="sxs-lookup"><span data-stu-id="9c3ed-135">After bundling, the JavaScript bundle file is reduced significantly from 815KB to 365KB:</span></span>
  
![Снимок экрана: сокращение размера скачиваемых элементов](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a><span data-ttu-id="9c3ed-137">Комплектирование изображений путем создания спрайта изображения</span><span class="sxs-lookup"><span data-stu-id="9c3ed-137">Bundling images by creating an image sprite</span></span>

<span data-ttu-id="9c3ed-138">Подобно тому, как вы объединяете файлы JavaScript и CSS, вы можете объединить множество небольших значков и других общих изображений в большой лист спрайта, а затем использовать CSS для раскрытия отдельных изображений.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-138">Similar to how you bundle JavaScript and CSS files, you can combine many small icons and other common images into a larger sprite sheet and then use CSS to reveal the individual images.</span></span> <span data-ttu-id="9c3ed-139">Вместо загрузки каждого отдельного изображения веб-браузер пользователя загружает лист спрайта один раз, а затем засеивает его на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-139">Instead of downloading each individual image, the user's web browser downloads the sprite sheet once and then caches it on the local computer.</span></span> <span data-ttu-id="9c3ed-140">Это повышает производительность загрузки страниц, сокращая количество скачиваемых и круглых поездок на веб-сервер.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-140">This improves page load performance by cutting down on the number of downloads and round trips to the web server.</span></span>
  
 <span data-ttu-id="9c3ed-141">**Создание спрайта изображения в Веб-основных**</span><span class="sxs-lookup"><span data-stu-id="9c3ed-141">**To create an image sprite in Web Essentials**</span></span>
  
1. <span data-ttu-id="9c3ed-142">В Visual Studio в обозревателе решений выберите файлы, которые необходимо включить в пакет.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-142">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="9c3ed-143">Щелкните правой кнопкой мыши выбранные файлы, а затем выберите **веб-материалы** \> **Создать спрайт** изображения из контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-143">Right-click the selected files and then select **Web Essentials** \> **Create image sprite** from the context menu.</span></span> <span data-ttu-id="9c3ed-144">Пример.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-144">For example:</span></span> 
    
    ![Снимок экрана: как создать спрайт изображения](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. <span data-ttu-id="9c3ed-146">Выберите расположение, чтобы сохранить спрайт-файл.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-146">Choose a location to save the sprite file.</span></span> <span data-ttu-id="9c3ed-147">Файл .sprite — это XML-файл, который описывает параметры и файлы в спрайте.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-147">The .sprite file is an XML file that describes the settings and files in the sprite.</span></span> <span data-ttu-id="9c3ed-148">На следующих рисунках покажите пример PNG-файла спрайта и соответствующего XML-файла спрайта.</span><span class="sxs-lookup"><span data-stu-id="9c3ed-148">The following figures show an example of a sprite PNG file and its corresponding .sprite XML file.</span></span>
    
    ![Снимок экрана: файл спрайта](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Снимок экрана: XML-файл спрайта](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

