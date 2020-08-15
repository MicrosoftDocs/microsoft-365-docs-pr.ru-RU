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
description: Сведения о том, как уменьшить время загрузки страниц SharePoint Online с помощью JavaScript, чтобы задержать загрузку изображений и несущественных JavaScript.
ms.openlocfilehash: ee86ae0813c11fbfd836d7d38ea124c1e3f277d0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693327"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a><span data-ttu-id="263d7-103">Задержка при загрузке изображений и JavaScript-файлов в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="263d7-103">Delay loading images and JavaScript in SharePoint Online</span></span>

<span data-ttu-id="263d7-104">В этой статье описывается, как уменьшить время загрузки страниц SharePoint Online с помощью JavaScript, чтобы задержать загрузку изображений, а также подождать, пока не загрузится страница.</span><span class="sxs-lookup"><span data-stu-id="263d7-104">This article describes how you can decrease the load time for SharePoint Online pages by using JavaScript to delay loading images and also by waiting to load non-essential JavaScript until after the page loads.</span></span>
  
<span data-ttu-id="263d7-105">Изображения могут негативно повлиять на скорость загрузки страниц в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="263d7-105">Images can negatively affect page load speeds on SharePoint Online.</span></span> <span data-ttu-id="263d7-106">По умолчанию большинство современных браузеров Интернета предварительно извлекает изображения при загрузке HTML-страницы.</span><span class="sxs-lookup"><span data-stu-id="263d7-106">By default, most modern Internet browsers pre-fetch images when loading an HTML page.</span></span> <span data-ttu-id="263d7-107">Это может вызвать немедленную загрузку страницы, если изображения не отображаются на экране до тех пор, пока пользователь не прокручивается.</span><span class="sxs-lookup"><span data-stu-id="263d7-107">This can cause the page to be unnecessarily slow to load if the images are not visible on the screen until the user scrolls down.</span></span> <span data-ttu-id="263d7-108">Изображения могут заблокировать загрузку браузером видимой части страницы.</span><span class="sxs-lookup"><span data-stu-id="263d7-108">The images can block the browser from loading the visible part of the page.</span></span> <span data-ttu-id="263d7-109">Чтобы обойти эту проблему, вы можете использовать JavaScript, чтобы пропустить загрузку изображений первыми.</span><span class="sxs-lookup"><span data-stu-id="263d7-109">To work around this problem, you can use JavaScript to skip loading the images first.</span></span> <span data-ttu-id="263d7-110">Кроме того, Загрузка несущественных сценариев JavaScript может замедлить загрузку страниц SharePoint.</span><span class="sxs-lookup"><span data-stu-id="263d7-110">Also, loading non-essential JavaScript can slow download times on your SharePoint pages too.</span></span> <span data-ttu-id="263d7-111">В этом разделе описываются методы, которые можно использовать для оптимизации времени загрузки страниц с помощью JavaScript в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="263d7-111">This topic describes some methods you can use to improve page load times with JavaScript in SharePoint Online.</span></span>
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a><span data-ttu-id="263d7-112">Увеличение времени загрузки страниц путем задержки загрузки изображений в страницах SharePoint Online с помощью JavaScript</span><span class="sxs-lookup"><span data-stu-id="263d7-112">Improve page load times by delaying image loading in SharePoint Online pages by using JavaScript</span></span>

<span data-ttu-id="263d7-113">Вы можете использовать JavaScript, чтобы запретить веб-браузеру получать изображения с предварительной отправкой.</span><span class="sxs-lookup"><span data-stu-id="263d7-113">You can use JavaScript to prevent a web browser from pre-fetching images.</span></span> <span data-ttu-id="263d7-114">Это ускоряет обработку всего документа.</span><span class="sxs-lookup"><span data-stu-id="263d7-114">This speeds up overall document rendering.</span></span> <span data-ttu-id="263d7-115">Чтобы сделать это, удалите значение атрибута src из \<img\> тега и замените его на путь к файлу в атрибуте данных, например: Data — src.</span><span class="sxs-lookup"><span data-stu-id="263d7-115">To do this you remove the value of the src attribute from the \<img\> tag and replace it with the path to a file in a data attribute such as: data-src.</span></span> <span data-ttu-id="263d7-116">Например:</span><span class="sxs-lookup"><span data-stu-id="263d7-116">For example:</span></span>
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

<span data-ttu-id="263d7-117">При использовании этого метода браузер не скачивает изображения сразу же.</span><span class="sxs-lookup"><span data-stu-id="263d7-117">By using this method, the browser doesn't download the images immediately.</span></span> <span data-ttu-id="263d7-118">Если изображение уже находится в окне просмотра, JavaScript предписывает браузеру получить URL-адрес из атрибута данных и вставить его в качестве значения атрибута src.</span><span class="sxs-lookup"><span data-stu-id="263d7-118">If the image is already in the viewport, JavaScript tells the browser to retrieve the URL from the data attribute and insert it as the value for the src attribute.</span></span> <span data-ttu-id="263d7-119">Изображение загружается, только когда пользователь прокручивается и отображается в представлении.</span><span class="sxs-lookup"><span data-stu-id="263d7-119">The image only loads as the user scrolls and it comes into view.</span></span>
  
<span data-ttu-id="263d7-120">Чтобы все это происходило, необходимо использовать JavaScript.</span><span class="sxs-lookup"><span data-stu-id="263d7-120">To make all of this happen, you'll need to use JavaScript.</span></span>
  
<span data-ttu-id="263d7-121">В текстовом файле определите функцию **иселементинвиевпорт ()** , чтобы проверить, находится ли элемент в части браузера, видимой для пользователя.</span><span class="sxs-lookup"><span data-stu-id="263d7-121">In a text file, define the **isElementInViewport()** function to check whether or not an element is in the part of the browser that is visible to the user.</span></span>
  
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

<span data-ttu-id="263d7-122">Затем используйте **иселементинвиевпорт ()** в функции **лоадитемсинвиев ()** .</span><span class="sxs-lookup"><span data-stu-id="263d7-122">Next, use **isElementInViewport()** in the **loadItemsInView()** function.</span></span> <span data-ttu-id="263d7-123">Функция **лоадитемсинвиев ()** загрузит все изображения, имеющие значение для атрибута Data-src, если они находятся в той части браузера, которая видна пользователю.</span><span class="sxs-lookup"><span data-stu-id="263d7-123">The **loadItemsInView()** function will load all images that have a value for the data-src attribute if they are in the part of the browser that is visible to the user.</span></span> <span data-ttu-id="263d7-124">Добавьте в текстовый файл указанную ниже функцию.</span><span class="sxs-lookup"><span data-stu-id="263d7-124">Add the following function to the text file:</span></span>
  
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

<span data-ttu-id="263d7-125">В заключение вызовите **лоадитемсинвиев ()** из **Window. OnScroll ()** , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="263d7-125">Finally, call **loadItemsInView()** from within **window.onscroll()** as shown in the following example.</span></span> <span data-ttu-id="263d7-126">Это гарантирует, что все изображения в окне просмотра загружаются по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="263d7-126">This ensures that any images that are in the viewport are loaded as the user needs them, but not before.</span></span> <span data-ttu-id="263d7-127">Добавьте следующий текст в текстовый файл:</span><span class="sxs-lookup"><span data-stu-id="263d7-127">Add the following to the text file:</span></span>
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

<span data-ttu-id="263d7-128">Для SharePoint Online необходимо подключить следующую функцию к событию прокрутки в теге #s4-Workspace \<div\> .</span><span class="sxs-lookup"><span data-stu-id="263d7-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span></span> <span data-ttu-id="263d7-129">Это связано с тем, что события окон переопределяются, чтобы лента оставалась присоединенной к верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="263d7-129">This is because the window events are overridden in order to ensure the ribbon remains attached to the top of the page.</span></span>
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

<span data-ttu-id="263d7-130">Сохраните текстовый файл в виде файла JavaScript с расширением JS, например delayLoadImages.js.</span><span class="sxs-lookup"><span data-stu-id="263d7-130">Save the text file as a JavaScript file with the extension .js, for example delayLoadImages.js.</span></span>
  
<span data-ttu-id="263d7-131">После того как вы закончите запись delayLoadImages.js, вы можете добавить содержимое файла на главную страницу в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="263d7-131">Once you've finished writing delayLoadImages.js, you can add the contents of the file to a master page in SharePoint Online.</span></span> <span data-ttu-id="263d7-132">Для этого добавьте ссылку на скрипт в заголовок главной страницы.</span><span class="sxs-lookup"><span data-stu-id="263d7-132">You do this by adding a script link to the header in the master page.</span></span> <span data-ttu-id="263d7-133">Когда она находится на главной странице, JavaScript будет применен ко всем страницам на сайте SharePoint Online, которые используют этот макет эталонной страницы.</span><span class="sxs-lookup"><span data-stu-id="263d7-133">Once it's in a master page, the JavaScript will be applied to all pages in your SharePoint Online site that use that master page layout.</span></span> <span data-ttu-id="263d7-134">Кроме того, если вы планируете использовать его только на одной странице сайта, используйте веб-часть редактора скриптов, чтобы внедрить JavaScript на страницу.</span><span class="sxs-lookup"><span data-stu-id="263d7-134">Alternatively, if you intend to only use this on one page of your site, use the script editor Web Part to embed the JavaScript into the page.</span></span> <span data-ttu-id="263d7-135">Дополнительные сведения приведены в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="263d7-135">See these topics for more information:</span></span>
  
- [<span data-ttu-id="263d7-136">Инструкции. Применение эталонной страницы к сайту в SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="263d7-136">How to: Apply a master page to a site in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525627)

- [<span data-ttu-id="263d7-137">Инструкции. Создание макета страницы в SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="263d7-137">How to: Create a page layout in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525628)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a><span data-ttu-id="263d7-138">Пример: ссылка на файл JavaScript delayLoadImages.js из эталонной страницы в SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="263d7-138">Example: Referencing the JavaScript delayLoadImages.js file from a master page in SharePoint Online</span></span>
  
<span data-ttu-id="263d7-139">Чтобы это работало, вам также потребуется ссылаться на jQuery на главной странице.</span><span class="sxs-lookup"><span data-stu-id="263d7-139">In order for this to work, you also need to reference jQuery in the master page.</span></span> <span data-ttu-id="263d7-140">В следующем примере показана загрузка на начальной странице, если загружено только одно изображение, но на странице есть несколько дополнительных.</span><span class="sxs-lookup"><span data-stu-id="263d7-140">In the following example, you can see in the initial page load that there is only one image loaded but there are several more on the page.</span></span>
  
![Снимок экрана: одно изображение загружено на странице](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
<span data-ttu-id="263d7-142">На следующем снимке экрана показаны остальные изображения, которые загружаются после прокрутки в представлении.</span><span class="sxs-lookup"><span data-stu-id="263d7-142">The following screenshot shows the rest of the images that are downloaded after they scroll into view.</span></span>
  
![Снимок экрана: несколько изображений загружено на странице](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
<span data-ttu-id="263d7-144">Откладывание загрузки изображений с помощью JavaScript может быть эффективным методом увеличения производительности; Тем не менее, если метод применяется на общедоступном веб-сайте, поисковые системы не могут выполнять обход изображений так же, как и при регулярном формировании изображения.</span><span class="sxs-lookup"><span data-stu-id="263d7-144">Delaying image loading by using JavaScript can be an effective technique in increasing performance; however, if the technique is applied on a public website then search engines are not able to crawl the images in the same way they would crawl a regularly formed image.</span></span> <span data-ttu-id="263d7-145">Это может повлиять на ранжирование в поисковых машинах, так как метаданные на самом изображении не находятся в самом деле до тех пор, пока страница не загрузится.</span><span class="sxs-lookup"><span data-stu-id="263d7-145">This can affect rankings on search engines because metadata on the image itself is not really there until the page loads.</span></span> <span data-ttu-id="263d7-146">Средства для обхода поисковых систем читают только HTML-код, поэтому изображения не будут отображаться на странице.</span><span class="sxs-lookup"><span data-stu-id="263d7-146">Search engine crawlers only read the HTML and therefore will not see the images as content on the page.</span></span> <span data-ttu-id="263d7-147">Изображения — это один из факторов, используемых для ранжирования страниц в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="263d7-147">Images are one of the factors used to rank pages in search results.</span></span> <span data-ttu-id="263d7-148">Один из способов обойти эту проблему — использовать вводный текст для изображений.</span><span class="sxs-lookup"><span data-stu-id="263d7-148">One way to work around this is to use introductory text for your images.</span></span>
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a><span data-ttu-id="263d7-149">Пример кода GitHub: внедрение JavaScript для улучшения производительности</span><span class="sxs-lookup"><span data-stu-id="263d7-149">GitHub code sample: Injecting JavaScript to improve performance</span></span>

<span data-ttu-id="263d7-150">Не пропустите статью и пример кода на [JavaScript Injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) , предоставленном в GitHub.</span><span class="sxs-lookup"><span data-stu-id="263d7-150">Don't miss the article and code sample on [JavaScript injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) provided on GitHub.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="263d7-151">См. также</span><span class="sxs-lookup"><span data-stu-id="263d7-151">See also</span></span>

[<span data-ttu-id="263d7-152">Поддерживаемые браузеры в приложениях Office 2013 и Майкрософт 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="263d7-152">Supported browsers in Office 2013 and Microsoft 365 Apps for enterprise</span></span>](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[<span data-ttu-id="263d7-153">Инструкции. Применение эталонной страницы к сайту в SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="263d7-153">How to: Apply a master page to a site in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525627)
  
[<span data-ttu-id="263d7-154">Инструкции. Создание макета страницы в SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="263d7-154">How to: Create a page layout in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525628)
