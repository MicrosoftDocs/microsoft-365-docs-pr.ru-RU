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
description: Узнайте, как уменьшить время загрузки страниц SharePoint Online с помощью JavaScript для задержки загрузки изображений и не важного JavaScript.
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919168"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>Задержка при загрузке изображений и JavaScript-файлов в SharePoint Online

В этой статье описывается, как уменьшить время загрузки страниц SharePoint Online с помощью JavaScript для задержки загрузки изображений, а также ожидания загрузки не важного JavaScript до окончания загрузки страницы.
  
Изображения могут отрицательно повлиять на скорость загрузки страниц в SharePoint Online. По умолчанию большинство современных интернет-браузеров предварительно загружают изображения при загрузке HTML-страницы. Это может привести к излишне медленной загрузке страницы, если изображения не видны на экране до тех пор, пока пользователь не прокрутит вниз. Изображения могут блокировать загрузку видимой части страницы браузером. Чтобы решить эту проблему, сначала можно использовать JavaScript, чтобы пропустить загрузку изображений. Кроме того, загрузка несуществующих JavaScript также может замедлить время загрузки на страницах SharePoint. В этом разделе описаны некоторые методы, которые можно использовать для улучшения времени загрузки страниц с Помощью JavaScript в SharePoint Online.
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>Улучшение времени загрузки страницы путем задержки загрузки изображений на страницах SharePoint Online с помощью JavaScript

Вы можете использовать JavaScript, чтобы предотвратить использование веб-браузера для предварительного получения изображений. Это ускоряет общую отрисовку документов. Для этого из тега удаляется значение атрибута SRC и заменяется путь к файлу в атрибуте \<img\> данных, например: data-src. Например:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

С помощью этого метода браузер загружает изображения не сразу. Если изображение уже находится в представлении, JavaScript сообщает браузеру извлечь URL-адрес из атрибута данных и вставить его в качестве значения атрибута SRC. Изображение загружается только при прокрутке пользователя, и оно появляется в представлении.
  
Чтобы все это произошло, необходимо использовать JavaScript.
  
В текстовом файле определите функцию **isElementInViewport()** для проверки того, находится ли элемент в части браузера, которая видна пользователю.
  
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

Далее используйте функцию **loadItemsInView()** **isElementInViewport().** Функция **loadItemsInView()** загружает все изображения, которые имеют значение атрибута data-src, если они находятся в части браузера, которая видна пользователю. Добавьте в текстовый файл следующую функцию:
  
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

Наконец, вызов **loadItemsInView()** из **window.onscroll()** как показано в следующем примере. Это гарантирует загрузку любых изображений, которые находятся в представлении, так как они нужны пользователю, но не ранее. Добавьте в текстовый файл следующее:
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

Для SharePoint Online необходимо прикрепить следующую функцию к событию прокрутки на теге #s4 рабочей \<div\> области. Это происходит из-за переопределения событий окна, чтобы лента оставалась прикрепленной к верхней части страницы.
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

Сохраните текстовый файл в виде файла JavaScript с расширением .js, например delayLoadImages.js.
  
После завершения записи delayLoadImages.js можно добавить содержимое файла на мастер-страницу в SharePoint Online. Это необходимо, добавив ссылку скрипта на заготвую страницу. После того, как он будет на магистрали, JavaScript будет применяться на всех страницах сайта SharePoint Online, которые используют эту макетную страницу. Кроме того, если вы собираетесь использовать это только на одной странице сайта, используйте веб-часть редактора сценариев для встраить JavaScript на страницу. Дополнительные сведения см. в этих разделах:
  
- [Инструкции. Применение эталонной страницы к сайту в SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [Инструкции. Создание макета страницы в SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>Пример. Ссылки на файл JavaScript delayLoadImages.js с мастер-страницы в SharePoint Online
  
Чтобы это работало, необходимо также ссылаться на jQuery на мастер-странице. В следующем примере в начальной загрузке страницы можно увидеть, что загружено только одно изображение, но на странице есть еще несколько.
  
![Снимок экрана: одно изображение загружено на странице](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
На следующем скриншоте показаны остальные изображения, скачиваемые после их прокрутки.
  
![Снимок экрана: несколько изображений загружено на странице](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
Задержка загрузки изображений с помощью JavaScript может быть эффективным методом повышения производительности; однако, если метод применяется на общедоступный веб-сайт, поисковые системы не могут обхода изображений таким же образом, как они будут обходить регулярно сформированное изображение. Это может повлиять на ранжирование в поисковых системах, так как метаданные на самом изображении на самом деле не существует до загрузки страницы. Обходчики поисковых систем только читают HTML и поэтому не видят изображения в качестве контента на странице. Изображения — это один из факторов, используемых для ранживки страниц в результатах поиска. Один из способов обойти это — использовать вводный текст для изображений.
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>Пример кода GitHub: ввод JavaScript для повышения производительности

Не пропустите пример статьи и кода в [javaScript-впрыски,](https://go.microsoft.com/fwlink/p/?LinkId=524759) предоставленные на GitHub.
  
## <a name="see-also"></a>См. также

[Поддерживаемые браузеры в Office 2013 и Microsoft 365 Apps для предприятия](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[Инструкции. Применение эталонной страницы к сайту в SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[Инструкции. Создание макета страницы в SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)