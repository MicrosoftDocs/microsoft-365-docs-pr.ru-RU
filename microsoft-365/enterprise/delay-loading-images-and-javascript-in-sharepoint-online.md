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
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>Задержка при загрузке изображений и JavaScript-файлов в SharePoint Online

В этой статье описывается, как уменьшить время загрузки страниц SharePoint Online с помощью JavaScript, чтобы задержать загрузку изображений, а также подождать, пока не загрузится страница.
  
Изображения могут негативно повлиять на скорость загрузки страниц в SharePoint Online. По умолчанию большинство современных браузеров Интернета предварительно извлекает изображения при загрузке HTML-страницы. Это может вызвать немедленную загрузку страницы, если изображения не отображаются на экране до тех пор, пока пользователь не прокручивается. Изображения могут заблокировать загрузку браузером видимой части страницы. Чтобы обойти эту проблему, вы можете использовать JavaScript, чтобы пропустить загрузку изображений первыми. Кроме того, Загрузка несущественных сценариев JavaScript может замедлить загрузку страниц SharePoint. В этом разделе описываются методы, которые можно использовать для оптимизации времени загрузки страниц с помощью JavaScript в SharePoint Online.
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>Увеличение времени загрузки страниц путем задержки загрузки изображений в страницах SharePoint Online с помощью JavaScript

Вы можете использовать JavaScript, чтобы запретить веб-браузеру получать изображения с предварительной отправкой. Это ускоряет обработку всего документа. Чтобы сделать это, удалите значение атрибута src из \<img\> тега и замените его на путь к файлу в атрибуте данных, например: Data — src. Например:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

При использовании этого метода браузер не скачивает изображения сразу же. Если изображение уже находится в окне просмотра, JavaScript предписывает браузеру получить URL-адрес из атрибута данных и вставить его в качестве значения атрибута src. Изображение загружается, только когда пользователь прокручивается и отображается в представлении.
  
Чтобы все это происходило, необходимо использовать JavaScript.
  
В текстовом файле определите функцию **иселементинвиевпорт ()** , чтобы проверить, находится ли элемент в части браузера, видимой для пользователя.
  
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

Затем используйте **иселементинвиевпорт ()** в функции **лоадитемсинвиев ()** . Функция **лоадитемсинвиев ()** загрузит все изображения, имеющие значение для атрибута Data-src, если они находятся в той части браузера, которая видна пользователю. Добавьте в текстовый файл указанную ниже функцию.
  
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

В заключение вызовите **лоадитемсинвиев ()** из **Window. OnScroll ()** , как показано в следующем примере. Это гарантирует, что все изображения в окне просмотра загружаются по мере необходимости. Добавьте следующий текст в текстовый файл:
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

Для SharePoint Online необходимо подключить следующую функцию к событию прокрутки в теге #s4-Workspace \<div\> . Это связано с тем, что события окон переопределяются, чтобы лента оставалась присоединенной к верхней части страницы.
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

Сохраните текстовый файл в виде файла JavaScript с расширением JS, например delayLoadImages.js.
  
После того как вы закончите запись delayLoadImages.js, вы можете добавить содержимое файла на главную страницу в SharePoint Online. Для этого добавьте ссылку на скрипт в заголовок главной страницы. Когда она находится на главной странице, JavaScript будет применен ко всем страницам на сайте SharePoint Online, которые используют этот макет эталонной страницы. Кроме того, если вы планируете использовать его только на одной странице сайта, используйте веб-часть редактора скриптов, чтобы внедрить JavaScript на страницу. Дополнительные сведения приведены в следующих статьях:
  
- [Инструкции. Применение эталонной страницы к сайту в SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525627)

- [Инструкции. Создание макета страницы в SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525628)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>Пример: ссылка на файл JavaScript delayLoadImages.js из эталонной страницы в SharePoint Online
  
Чтобы это работало, вам также потребуется ссылаться на jQuery на главной странице. В следующем примере показана загрузка на начальной странице, если загружено только одно изображение, но на странице есть несколько дополнительных.
  
![Снимок экрана: одно изображение загружено на странице](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
На следующем снимке экрана показаны остальные изображения, которые загружаются после прокрутки в представлении.
  
![Снимок экрана: несколько изображений загружено на странице](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
Откладывание загрузки изображений с помощью JavaScript может быть эффективным методом увеличения производительности; Тем не менее, если метод применяется на общедоступном веб-сайте, поисковые системы не могут выполнять обход изображений так же, как и при регулярном формировании изображения. Это может повлиять на ранжирование в поисковых машинах, так как метаданные на самом изображении не находятся в самом деле до тех пор, пока страница не загрузится. Средства для обхода поисковых систем читают только HTML-код, поэтому изображения не будут отображаться на странице. Изображения — это один из факторов, используемых для ранжирования страниц в результатах поиска. Один из способов обойти эту проблему — использовать вводный текст для изображений.
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>Пример кода GitHub: внедрение JavaScript для улучшения производительности

Не пропустите статью и пример кода на [JavaScript Injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) , предоставленном в GitHub.
  
## <a name="see-also"></a>См. также

[Поддерживаемые браузеры в приложениях Office 2013 и Майкрософт 365 для предприятий](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[Инструкции. Применение эталонной страницы к сайту в SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525627)
  
[Инструкции. Создание макета страницы в SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525628)
