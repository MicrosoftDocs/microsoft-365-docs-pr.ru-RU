---
title: Задержка при загрузке изображений и JavaScript-файлов в SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
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
ms.assetid: 74d327e5-755f-4135-b9a5-7b79578c1bf9
description: Узнайте, как уменьшить время загрузки SharePoint веб-страниц с помощью JavaScript для задержки загрузки изображений и не важного JavaScript.
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919168"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a><span data-ttu-id="2326c-103">Задержка при загрузке изображений и JavaScript-файлов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2326c-103">Delay loading images and JavaScript in SharePoint Online</span></span>

<span data-ttu-id="2326c-104">В этой статье описывается, как можно уменьшить время загрузки страниц SharePoint Online, используя JavaScript для задержки загрузки изображений, а также ожидая загрузки несуществующих JavaScript до окончания загрузки страницы.</span><span class="sxs-lookup"><span data-stu-id="2326c-104">This article describes how you can decrease the load time for SharePoint Online pages by using JavaScript to delay loading images and also by waiting to load non-essential JavaScript until after the page loads.</span></span>
  
<span data-ttu-id="2326c-105">Изображения могут отрицательно повлиять на скорость загрузки страниц в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2326c-105">Images can negatively affect page load speeds on SharePoint Online.</span></span> <span data-ttu-id="2326c-106">По умолчанию большинство современных интернет-браузеров предварительно загружают изображения при загрузке HTML-страницы.</span><span class="sxs-lookup"><span data-stu-id="2326c-106">By default, most modern Internet browsers pre-fetch images when loading an HTML page.</span></span> <span data-ttu-id="2326c-107">Это может привести к излишне медленной загрузке страницы, если изображения не видны на экране до тех пор, пока пользователь не прокрутит вниз.</span><span class="sxs-lookup"><span data-stu-id="2326c-107">This can cause the page to be unnecessarily slow to load if the images are not visible on the screen until the user scrolls down.</span></span> <span data-ttu-id="2326c-108">Изображения могут блокировать загрузку видимой части страницы браузером.</span><span class="sxs-lookup"><span data-stu-id="2326c-108">The images can block the browser from loading the visible part of the page.</span></span> <span data-ttu-id="2326c-109">Чтобы решить эту проблему, сначала можно использовать JavaScript, чтобы пропустить загрузку изображений.</span><span class="sxs-lookup"><span data-stu-id="2326c-109">To work around this problem, you can use JavaScript to skip loading the images first.</span></span> <span data-ttu-id="2326c-110">Кроме того, загрузка не важного JavaScript может замедлить время загрузки SharePoint страниц.</span><span class="sxs-lookup"><span data-stu-id="2326c-110">Also, loading non-essential JavaScript can slow download times on your SharePoint pages too.</span></span> <span data-ttu-id="2326c-111">В этом разделе описаны некоторые методы, которые можно использовать для улучшения времени загрузки страниц с Помощью JavaScript в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2326c-111">This topic describes some methods you can use to improve page load times with JavaScript in SharePoint Online.</span></span>
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a><span data-ttu-id="2326c-112">Улучшение времени загрузки страниц путем задержки загрузки изображений на SharePoint веб-страницах с помощью JavaScript</span><span class="sxs-lookup"><span data-stu-id="2326c-112">Improve page load times by delaying image loading in SharePoint Online pages by using JavaScript</span></span>

<span data-ttu-id="2326c-113">Вы можете использовать JavaScript, чтобы предотвратить использование веб-браузера для предварительного получения изображений.</span><span class="sxs-lookup"><span data-stu-id="2326c-113">You can use JavaScript to prevent a web browser from pre-fetching images.</span></span> <span data-ttu-id="2326c-114">Это ускоряет общую отрисовку документов.</span><span class="sxs-lookup"><span data-stu-id="2326c-114">This speeds up overall document rendering.</span></span> <span data-ttu-id="2326c-115">Для этого из тега удаляется значение атрибута SRC и заменяется путь к файлу в атрибуте \<img\> данных, например: data-src.</span><span class="sxs-lookup"><span data-stu-id="2326c-115">To do this you remove the value of the src attribute from the \<img\> tag and replace it with the path to a file in a data attribute such as: data-src.</span></span> <span data-ttu-id="2326c-116">Пример.</span><span class="sxs-lookup"><span data-stu-id="2326c-116">For example:</span></span>
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

<span data-ttu-id="2326c-117">С помощью этого метода браузер загружает изображения не сразу.</span><span class="sxs-lookup"><span data-stu-id="2326c-117">By using this method, the browser doesn't download the images immediately.</span></span> <span data-ttu-id="2326c-118">Если изображение уже находится в представлении, JavaScript сообщает браузеру извлечь URL-адрес из атрибута данных и вставить его в качестве значения атрибута SRC.</span><span class="sxs-lookup"><span data-stu-id="2326c-118">If the image is already in the viewport, JavaScript tells the browser to retrieve the URL from the data attribute and insert it as the value for the src attribute.</span></span> <span data-ttu-id="2326c-119">Изображение загружается только при прокрутке пользователя, и оно появляется в представлении.</span><span class="sxs-lookup"><span data-stu-id="2326c-119">The image only loads as the user scrolls and it comes into view.</span></span>
  
<span data-ttu-id="2326c-120">Чтобы все это произошло, необходимо использовать JavaScript.</span><span class="sxs-lookup"><span data-stu-id="2326c-120">To make all of this happen, you'll need to use JavaScript.</span></span>
  
<span data-ttu-id="2326c-121">В текстовом файле определите функцию **isElementInViewport()** для проверки того, находится ли элемент в части браузера, которая видна пользователю.</span><span class="sxs-lookup"><span data-stu-id="2326c-121">In a text file, define the **isElementInViewport()** function to check whether or not an element is in the part of the browser that is visible to the user.</span></span>
  
```javascript
function isElementInViewport(el) {
  if (!el)
    return false;
  var rect = el.getBoundingClientRect();
  return (
    rect.top >= 0 &amp;&amp;
    rect.left >= 0 &amp;&amp;
    rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &amp;&amp;
    rect.right <= (window.innerWidth || document.documentElement.clientWidth)
  );
}
```

<span data-ttu-id="2326c-122">Далее используйте функцию **loadItemsInView()** **isElementInViewport().**</span><span class="sxs-lookup"><span data-stu-id="2326c-122">Next, use **isElementInViewport()** in the **loadItemsInView()** function.</span></span> <span data-ttu-id="2326c-123">Функция **loadItemsInView()** загружает все изображения, которые имеют значение атрибута data-src, если они находятся в части браузера, которая видна пользователю.</span><span class="sxs-lookup"><span data-stu-id="2326c-123">The **loadItemsInView()** function will load all images that have a value for the data-src attribute if they are in the part of the browser that is visible to the user.</span></span> <span data-ttu-id="2326c-124">Добавьте в текстовый файл следующую функцию:</span><span class="sxs-lookup"><span data-stu-id="2326c-124">Add the following function to the text file:</span></span>
  
```javascript
function loadItemsInView() {
  //Select elements by the row id.
  $("#row [data-src]").each(function () {
      var isVisible = isElementInViewport(this);
      if (isVisible) {
          if ($(this).attr("src") == undefined) {
              $(this).attr("src", $(this).data("src"));
          }
      }
  });
}
```

<span data-ttu-id="2326c-125">Наконец, вызов **loadItemsInView()** из **window.onscroll()** как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2326c-125">Finally, call **loadItemsInView()** from within **window.onscroll()** as shown in the following example.</span></span> <span data-ttu-id="2326c-126">Это гарантирует загрузку любых изображений, которые находятся в представлении, так как они нужны пользователю, но не ранее.</span><span class="sxs-lookup"><span data-stu-id="2326c-126">This ensures that any images that are in the viewport are loaded as the user needs them, but not before.</span></span> <span data-ttu-id="2326c-127">Добавьте в текстовый файл следующее:</span><span class="sxs-lookup"><span data-stu-id="2326c-127">Add the following to the text file:</span></span>
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

<span data-ttu-id="2326c-128">Для SharePoint Online необходимо прикрепить следующую функцию к событию прокрутки на теге #s4-workspace. \<div\></span><span class="sxs-lookup"><span data-stu-id="2326c-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span></span> <span data-ttu-id="2326c-129">Это происходит из-за переопределения событий окна, чтобы лента оставалась прикрепленной к верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="2326c-129">This is because the window events are overridden in order to ensure the ribbon remains attached to the top of the page.</span></span>
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

<span data-ttu-id="2326c-130">Сохраните текстовый файл в виде файла JavaScript с помощью .js, например delayLoadImages.js.</span><span class="sxs-lookup"><span data-stu-id="2326c-130">Save the text file as a JavaScript file with the extension .js, for example delayLoadImages.js.</span></span>
  
<span data-ttu-id="2326c-131">После завершения записи delayLoadImages.js можно добавить содержимое файла на мастер-страницу в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="2326c-131">Once you've finished writing delayLoadImages.js, you can add the contents of the file to a master page in SharePoint Online.</span></span> <span data-ttu-id="2326c-132">Это необходимо, добавив ссылку скрипта на заготвую страницу.</span><span class="sxs-lookup"><span data-stu-id="2326c-132">You do this by adding a script link to the header in the master page.</span></span> <span data-ttu-id="2326c-133">После того, как он будет на магистрали, JavaScript будет применяться на всех страницах на сайте SharePoint Online, которые используют эту макетную страницу.</span><span class="sxs-lookup"><span data-stu-id="2326c-133">Once it's in a master page, the JavaScript will be applied to all pages in your SharePoint Online site that use that master page layout.</span></span> <span data-ttu-id="2326c-134">Кроме того, если вы собираетесь использовать это только на одной странице сайта, используйте веб-часть редактора сценариев для встраить JavaScript на страницу.</span><span class="sxs-lookup"><span data-stu-id="2326c-134">Alternatively, if you intend to only use this on one page of your site, use the script editor Web Part to embed the JavaScript into the page.</span></span> <span data-ttu-id="2326c-135">Дополнительные сведения см. в этих разделах:</span><span class="sxs-lookup"><span data-stu-id="2326c-135">See these topics for more information:</span></span>
  
- [<span data-ttu-id="2326c-136">Инструкции. Применение эталонной страницы к сайту в SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="2326c-136">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [<span data-ttu-id="2326c-137">Инструкции. Создание макета страницы в SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="2326c-137">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a><span data-ttu-id="2326c-138">Пример. Ссылки на файл javaScript delayLoadImages.js с мастер-страницы в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2326c-138">Example: Referencing the JavaScript delayLoadImages.js file from a master page in SharePoint Online</span></span>
  
<span data-ttu-id="2326c-139">Чтобы это работало, необходимо также ссылаться на jQuery на мастер-странице.</span><span class="sxs-lookup"><span data-stu-id="2326c-139">In order for this to work, you also need to reference jQuery in the master page.</span></span> <span data-ttu-id="2326c-140">В следующем примере в начальной загрузке страницы можно увидеть, что загружено только одно изображение, но на странице есть еще несколько.</span><span class="sxs-lookup"><span data-stu-id="2326c-140">In the following example, you can see in the initial page load that there is only one image loaded but there are several more on the page.</span></span>
  
![Снимок экрана: одно изображение загружено на странице](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
<span data-ttu-id="2326c-142">На следующем скриншоте показаны остальные изображения, скачиваемые после их прокрутки.</span><span class="sxs-lookup"><span data-stu-id="2326c-142">The following screenshot shows the rest of the images that are downloaded after they scroll into view.</span></span>
  
![Снимок экрана: несколько изображений загружено на странице](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
<span data-ttu-id="2326c-144">Задержка загрузки изображений с помощью JavaScript может быть эффективным методом повышения производительности; однако, если метод применяется на общедоступный веб-сайт, поисковые системы не могут обхода изображений таким же образом, как они будут обходить регулярно сформированное изображение.</span><span class="sxs-lookup"><span data-stu-id="2326c-144">Delaying image loading by using JavaScript can be an effective technique in increasing performance; however, if the technique is applied on a public website then search engines are not able to crawl the images in the same way they would crawl a regularly formed image.</span></span> <span data-ttu-id="2326c-145">Это может повлиять на ранжирование в поисковых системах, так как метаданные на самом изображении на самом деле не существует до загрузки страницы.</span><span class="sxs-lookup"><span data-stu-id="2326c-145">This can affect rankings on search engines because metadata on the image itself is not really there until the page loads.</span></span> <span data-ttu-id="2326c-146">Обходчики поисковых систем только читают HTML и поэтому не видят изображения в качестве контента на странице.</span><span class="sxs-lookup"><span data-stu-id="2326c-146">Search engine crawlers only read the HTML and therefore will not see the images as content on the page.</span></span> <span data-ttu-id="2326c-147">Изображения — это один из факторов, используемых для ранживки страниц в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="2326c-147">Images are one of the factors used to rank pages in search results.</span></span> <span data-ttu-id="2326c-148">Один из способов обойти это — использовать вводный текст для изображений.</span><span class="sxs-lookup"><span data-stu-id="2326c-148">One way to work around this is to use introductory text for your images.</span></span>
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a><span data-ttu-id="2326c-149">GitHub кода: ввод JavaScript для повышения производительности</span><span class="sxs-lookup"><span data-stu-id="2326c-149">GitHub code sample: Injecting JavaScript to improve performance</span></span>

<span data-ttu-id="2326c-150">Не пропустите пример статьи и кода для впрыска [JavaScript,](https://go.microsoft.com/fwlink/p/?LinkId=524759) GitHub.</span><span class="sxs-lookup"><span data-stu-id="2326c-150">Don't miss the article and code sample on [JavaScript injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) provided on GitHub.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2326c-151">См. также</span><span class="sxs-lookup"><span data-stu-id="2326c-151">See also</span></span>

[<span data-ttu-id="2326c-152">Поддерживаемые браузеры Office 2013 и Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="2326c-152">Supported browsers in Office 2013 and Microsoft 365 Apps for enterprise</span></span>](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[<span data-ttu-id="2326c-153">Инструкции. Применение эталонной страницы к сайту в SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="2326c-153">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[<span data-ttu-id="2326c-154">Инструкции. Создание макета страницы в SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="2326c-154">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)