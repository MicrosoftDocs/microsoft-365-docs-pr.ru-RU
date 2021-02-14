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
description: Узнайте, как уменьшить время загрузки страниц SharePoint Online, используя JavaScript для задержки загрузки изображений и несуществующих JavaScript.
ms.openlocfilehash: ee86ae0813c11fbfd836d7d38ea124c1e3f277d0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693327"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>Задержка при загрузке изображений и JavaScript-файлов в SharePoint Online

В этой статье описывается, как уменьшить время загрузки страниц SharePoint Online с помощью JavaScript для задержки загрузки изображений, а также путем ожидания загрузки некритические JavaScript до загрузки страницы.
  
Изображения могут отрицательно влиять на скорость загрузки страниц в SharePoint Online. По умолчанию большинство современных интернет-браузеров предварительно загружают изображения при загрузке HTML-страницы. Это может привести к излишней медленной загрузке страницы, если изображения не будут видны на экране, пока пользователь не прокрутит страницу вниз. Изображения могут блокировать загрузку видимой части страницы браузером. Чтобы обойти эту проблему, сначала можно пропустить загрузку изображений с помощью JavaScript. Кроме того, загрузка некритого кода JavaScript также может замедлить загрузку страниц SharePoint. В этом разделе описываются некоторые методы, которые можно использовать для улучшения времени загрузки страниц с помощью JavaScript в SharePoint Online.
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>Улучшение времени загрузки страницы путем задержки загрузки изображений на страницах SharePoint Online с помощью JavaScript

JavaScript можно использовать для предотвращения предварительного извлечения изображений в веб-браузере. Это ускоряет общую отрисовку документов. Для этого удалите значение атрибута src из тега и замените его путем к файлу в атрибуте данных, например \<img\> data-src. Пример:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

С помощью этого метода браузер не скачивает изображения немедленно. Если изображение уже находится в окнове просмотра, JavaScript сообщает браузеру, что необходимо извлечь URL-адрес из атрибута данных и вставить его в качестве значения атрибута src. Изображение загружается только по мере прокрутки и просмотра пользователем.
  
Для этого необходимо использовать JavaScript.
  
В текстовом файле определите функцию **isElementInViewport(),** чтобы проверить, находится ли элемент в части браузера, видимой пользователю.
  
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

Затем используйте **isElementInViewport() в** **функции loadItemsInView().** Функция **loadItemsInView()** загружает все изображения, которые имеют значение атрибута data-src, если они находятся в части браузера, видимой пользователю. Добавьте в текстовый файл следующую функцию:
  
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

Наконец, вызовите **loadItemsInView()** из **window.onscroll(),** как показано в следующем примере. Это гарантирует, что любые изображения, которые находятся в окнах просмотра, загружаются по мере их потребностей пользователем, но не ранее. Добавьте в текстовый файл следующее:
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

Для SharePoint Online необходимо присоединить следующую функцию к событию прокрутки в теге #s4 рабочей \<div\> области. Это происходит потому, что события окна переопределяются, чтобы лента оставалась прикрепленной к верхней части страницы.
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

Сохраните текстовый файл в виде файла JavaScript с расширением JS, например delayLoadImages.js.
  
Завершив написание delayLoadImages.js, вы можете добавить содержимое файла на этаго страницу в SharePoint Online. Для этого добавьте ссылку на сценарий в загорную страницу. После того как он будет включен в этаповую страницу, JavaScript будет применен к всем страницам сайта SharePoint Online, которые используют этот макет этакого страницы. Кроме того, если вы собираетесь использовать его только на одной странице сайта, используйте веб-часть редактора скриптов, чтобы встраить JavaScript в страницу. Дополнительные сведения см. в указанных здесь темах.
  
- [Инструкции. Применение эталонной страницы к сайту в SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525627)

- [Инструкции. Создание макета страницы в SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525628)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>Пример. Ссылка на файл delayLoadImages.js JavaScript с эталовой страницы в SharePoint Online
  
Чтобы это работало, необходимо также со ссылкой на jQuery на эталонной странице. В следующем примере при начальной загрузке страницы можно увидеть, что загружено только одно изображение, но на странице есть еще несколько изображений.
  
![Снимок экрана: одно изображение загружено на странице](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
На следующем снимке экрана показаны остальные изображения, скачиваемые после прокрутки в представлении.
  
![Снимок экрана: несколько изображений загружено на странице](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
Задержка загрузки изображений с помощью JavaScript может быть эффективным методом повышения производительности; Однако если этот метод применяется на общедоступных веб-сайтах, поисковые системы не смогут обходить изображения так же, как они будут обходить регулярно сформированный образ. Это может повлиять на ранжирование в поисковых системах, так как метаданные на самом изображении на самом деле не существуют, пока страница не загрузится. Обходчики поисковых систем только читают HTML-код и поэтому не будут видеть изображения в качестве содержимого на странице. Изображения — это один из факторов, используемых для ранж в результатах поиска. Один из способов обойти эту возможность — использовать вводный текст для изображений.
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>Пример кода GitHub: ввод JavaScript для повышения производительности

Не пропустите статью и пример кода для впрыска [JavaScript](https://go.microsoft.com/fwlink/p/?LinkId=524759) на GitHub.
  
## <a name="see-also"></a>См. также

[Поддерживаемые браузеры в Office 2013 и приложениях Microsoft 365 для предприятий](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[Инструкции. Применение эталонной страницы к сайту в SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525627)
  
[Инструкции. Создание макета страницы в SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525628)
