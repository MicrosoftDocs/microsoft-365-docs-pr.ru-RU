---
title: Параметры навигации для SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
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
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: В этой статье описываются параметры навигации сайтов с включенной публикацией SharePoint в SharePoint Online.
ms.openlocfilehash: 86cefc60a26687835fd6a88de7f249143811de4f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696444"
---
# <a name="navigation-options-for-sharepoint-online"></a>Параметры навигации для SharePoint Online

В этой статье описываются параметры навигации сайтов с включенной публикацией SharePoint в SharePoint Online. Выбор и настройка навигации значительно влияют на производительность и масштабируемость сайтов в SharePoint Online. Шаблон сайта публикации SharePoint следует использовать только в том случае, если требуется для централизованного портала и компонент публикации должен быть включен только на определенных сайтах и только в случае крайней необходимости, если он может повлиять на производительность при неправильном использовании.

>[!NOTE]
>Если вы используете современные параметры навигации SharePoint, такие как меню мегапиксели, каскадная Навигация или Навигация по концентратору, эта статья не применяется к сайту. Современные архитектуры сайтов SharePoint используют более плоскую иерархию сайтов и Центрально-лучевую модель. Это позволяет добиться многих сценариев, при которых не требуется использовать функцию публикации SharePoint.

## <a name="overview-of-navigation-options"></a>Общие сведения о параметрах навигации

Конфигурация поставщика навигации может значительно повлиять на производительность всего сайта, поэтому следует тщательно продумать, чтобы выбрать поставщика навигации и конфигурацию, которая эффективно масштабируется для требований сайта SharePoint. Существует два встроенных поставщика навигации, а также пользовательские реализации навигации.

Первый вариант, [**структурная навигация**](#using-structural-navigation-in-sharepoint-online), — это рекомендуемый вариант навигации в SharePoint Online для классических сайтов SharePoint, **Если вы включите кэширование структуры навигации для сайта**. В этом поставщике навигации отображаются элементы навигации, расположенные ниже текущего сайта, а также (при необходимости) текущий сайт и его элементы того же уровня. Он предоставляет дополнительные возможности, такие как фильтрация по ролям безопасности и перечисление структуры сайта. Если кэширование отключено, это отрицательно повлияет на производительность и масштабируемость, и может быть подвергнуто регулированию.

Второй вариант, [**управляемая (метаданные)**](#using-managed-navigation-and-metadata-in-sharepoint-online), представляет элементы навигации с помощью набора терминов управляемых метаданных. Рекомендуется отключить фильтрацию по ролям безопасности, если это не требуется. Фильтрация по ролям безопасности включена по умолчанию для этого поставщика навигации; Однако многие сайты не требуют дополнительных затрат на фильтрацию по ролям безопасности, так как элементы навигации часто являются согласованными для всех пользователей сайта. С рекомендуемой конфигурацией для отключения фильтрации по ролям безопасности этот поставщик навигации не нуждается в перечислении структуры сайта и имеет высокую масштабируемость с приемлемым влиянием на производительность.

В дополнение к встроенным поставщикам навигации многие клиенты успешно реализовали альтернативные реализации пользовательских переходов. В этой статье рассказывается о [сценариях на стороне клиента](#using-search-driven-client-side-scripting) , основанных на поиске.
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>Преимущества и недостатки параметров навигации SharePoint Online

В следующей таблице обобщены преимущества и недостатки каждого из вариантов.

|Структурная навигация  |Управляемая навигация  |Навигация на основе поиска  |Поставщик настраиваемой навигации  |
|---------|---------|---------|---------|
|Технология<br/><br/>Простота обслуживания<br/>Фильтрация по ролям безопасности<br/>Автоматическое обновление в течение 24 часов при изменении содержимого<br/>     |Технология<br/><br/>Простота обслуживания<br/>|Технология<br/><br/>Фильтрация по ролям безопасности<br/>Автоматически обновляются при добавлении сайтов<br/>Время быстрой загрузки и локально кэшированная структура навигации<br/>|Технология<br/><br/>Широкий выбор доступных параметров<br/>Быстрая загрузка при правильном использовании кэширования<br/>Многие параметры хорошо подходят для страниц с откликом<br/>|
|Недостатк<br/><br/>**Влияет на производительность, если кэширование отключено**<br/>Тема регулирования<br/>|Недостатк<br/><br/>Не обновляется автоматически с учетом структуры сайта<br/>**Влияет на производительность, если фильтрация по ролям безопасности включена** или структура навигации сложна<br/>|Недостатк<br/><br/>Нет возможности легко упорядочивать сайты<br/>Требует настройки эталонной страницы (требуются технические навыки)<br/>|Недостатк<br/><br/>Необходима настраиваемая разработка<br/>Необходимо хранить внешний источник данных/кэш, например Azure<br/>|

Наиболее подходящий вариант для сайта будет зависеть от требований к сайту и технической возможности. Если вы хотите легко настроить поставщик навигации, который автоматически обновляется при изменении содержимого, то структурная навигация [с включенным кэшированием](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) является хорошим вариантом.

>[!NOTE]
>Применение того же принципа к современным сайтам SharePoint путем упрощения общей структуры сайта до плоская, неиерархической структуры повышает производительность и упрощает переход на современные сайты SharePoint. Это означает, что вместо одного семейства веб-сайтов с сотнями сайтов (дочерние веб-сайты) лучшим подходом будет наличие большого числа семейств веб-сайтов с очень малой дочерними сайтами (дочерние веб-сайты).

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>Анализ производительности навигации в SharePoint Online

[Средство диагностики страниц для SharePoint](https://aka.ms/perftool) — это расширение браузера для браузеров Microsoft EDGE и Chrome, которые анализируют как современный портал SharePoint Online, так и классические страницы сайта публикации. Это средство работает только для SharePoint Online и не может использоваться на странице системы SharePoint.

Средство создает отчет по каждой проанализированной странице, на которой показано, как страница выполняется для предопределенного набора правил, и отображает подробные сведения, если результаты тестирования выходят за границы базового значения. Администраторы и дизайнеры SharePoint Online могут использовать это средство для устранения неполадок, связанных с производительностью, чтобы обеспечить оптимизацию новых страниц перед публикацией.

**SPRequestDuration** в частности — это время, необходимое для обработки страницы в SharePoint. Большая область переходов (например, включение страниц в навигацию), сложных иерархий сайтов, а также другие параметры конфигурации и топологии могут значительно значительно отключаться к длительности.

## <a name="using-structural-navigation-in-sharepoint-online"></a>Использование структурной навигации в SharePoint Online

Это встроенная Навигация, используемая по умолчанию и которая является самым простым решением. Для него не требуется никаких настроек, и пользователь, не являющийся техническим, может легко добавлять элементы, скрывать элементы и управлять навигацией на странице "Параметры". Мы рекомендуем [включать кэширование](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), в противном случае снижение производительности.

### <a name="how-to-implement-structural-navigation-caching"></a>Реализация кэширования структуры навигации

В разделе **Параметры сайта**  >  **и Навигация по внешнему виду**  >  **Navigation**можно проверить, выбрана ли структурная навигация для глобальной навигации или текущей структуры навигации. Выбор пункта **Показать страницы** отрицательно влияет на производительность.

![Структурная навигация с выбранными дочерними сайтами](../media/SPONavOptionsStructuredShowSubsites.png)

Кэширование можно включать и отключать на уровне семейства веб-сайтов и на уровне сайта и по умолчанию включено. Для включения на уровне семейства веб-сайтов в разделе Навигация по семейству веб-сайтов " **Параметры сайта**  >  **Site Collection Administration**  >  **Site Collection Navigation**" установите флажок **включить кэширование**.

![Включение кэширования на уровне сайта](../media/structural-nav/structural-nav-caching-site-coll.png)

Чтобы включить на уровне сайта, в разделе Навигация по **параметрам сайта**  >  **Navigation**установите флажок **включить кэширование**.

![Включение кэширования на уровне сайта](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>Использование управляемой навигации и метаданных в SharePoint Online

Управляемая Навигация — это еще один встроенный параметр, который можно использовать для повторного создания большей части функций с структурной навигацией. Управляемые метаданные можно настроить так, чтобы фильтрация по ролям безопасности была включена или отключена. Если фильтрация по ролям безопасности отключена, управляемая Навигация довольно эффективна, так как она загружает все навигационные ссылки с постоянным числом вызовов сервера. Однако включение фильтрации по ролям безопасности отменяет некоторые преимущества управляемой навигации.

Если необходимо включить фильтрацию по ролям безопасности, рекомендуется выполнить указанные ниже действия.

- Обновление всех понятных URL-ссылок на простые ссылки
- Добавьте необходимые узлы фильтрации по ролям безопасности в качестве понятных URL-адресов
- Ограничьте число элементов навигации до 100 и не более трех уровней.

Многие сайты не нуждаются в фильтрации по ролям безопасности, так как структура навигации часто согласована для всех пользователей сайта. Если фильтрация по ролям безопасности отключена и ссылка добавлена на навигацию, к которой у всех пользователей есть доступ, ссылка по-прежнему будет отображаться, но будет вызывать сообщение об отказе в доступе. Нет риска случайного доступа к содержимому.

### <a name="how-to-implement-managed-navigation-and-the-results"></a>Как реализовать управляемую навигацию и результаты

В docs.microsoft.com содержатся несколько статей, посвященных управлению навигацией. Например, в разделе [Обзор управляемой навигации в SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).

Чтобы реализовать управляемую навигацию, вы можете настроить термины с URL-адресами, соответствующими структуре навигации сайта. Управляемую навигацию можно также выполнить вручную, чтобы заменить структурную навигацию во многих случаях. Например:

![Структура сайта SharePoint Online](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>Использование скрипта на стороне клиента на основе поиска

Один из распространенных классов реализации пользовательских переходов применяет к просмотру клиентские шаблоны, которые хранят локальный кэш узлов навигации.

Эти поставщики навигации имеют несколько ключевых преимуществ:

- Как правило, они хорошо работают с откликом от макетов страниц.
- Они чрезвычайно масштабируемыми и выполняемыми, так как они могут отображаться без затрат на ресурсы (и обновлять в фоновом режиме после истечения времени ожидания).
- Эти поставщики навигации могут получать данные навигации с помощью различных стратегий, начиная от простых статических конфигураций к различным поставщикам динамических данных.

В качестве примера поставщика данных можно использовать **навигацию на основе поиска**, что обеспечивает гибкость для перечисления узлов навигации и эффективного обработки фильтрации по ролям безопасности.

Существуют и другие популярные возможности для создания **пользовательских поставщиков навигации**. Ознакомьтесь с [решениями навигации для порталов SharePoint Online](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) , чтобы получить дополнительные рекомендации по созданию настраиваемого поставщика навигации.

С помощью функции поиска можно использовать индексы, встроенные в фоновый режим с помощью непрерывного обхода. Результаты поиска берутся из индекса поиска, и результаты отбрасываются с помощью средств безопасности. Как правило, это работает быстрее, чем готовые поставщики навигации, если фильтрация по ролям безопасности необходима. С помощью функции поиска структурной навигации, особенно при наличии сложной структуры сайта, значительно ускоряется время загрузки страниц. Основное преимущество этого подхода к управляемой навигации заключается в преимуществах фильтрации по ролям безопасности.

Такой подход включает создание настраиваемой эталонной страницы и замена встроенного кода навигации на пользовательский HTML-код. Выполните эту процедуру, описанную в следующем примере, чтобы заменить код навигации в файле `seattle.html` . В этом примере открывается `seattle.html` файл и заменяется весь элемент `id="DeltaTopNavigation"` на пользовательский HTML-код.

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>Пример: замена встроенного кода навигации на главной странице

1. Перейдите на страницу Параметры сайта.
2. Откройте коллекцию главных страниц, щелкнув **эталонные страницы**.
3. Отсюда вы можете перейти к библиотеке и скачать файл `seattle.master` .
4. Измените код с помощью текстового редактора и удалите блок кода на следующем снимке экрана.<br/>![Удаление блока кода, показанного](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. Удалите код между `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` тегами и замените его следующим фрагментом кода:<br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. Замените URL-адрес в открывающем теге привязки изображения на ссылку на загружаемое изображение в семействе веб-сайтов. После внесения изменений переименуйте файл и отправьте его в коллекцию главных страниц. При этом создается новый главный файл.<br/>
7. Этот HTML-код представляет собой базовую разметку, которая будет заполнена результатами поиска, возвращаемыми из кода JavaScript. Вам потребуется изменить код, чтобы изменить значение для параметра var root = "URL-адрес семейства веб-сайтов", как показано в следующем фрагменте кода:<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. Результаты назначаются для массива "My. Nodes", а иерархия — из объектов с помощью linq.js назначения выходных данных массиву. Иерархия массивов. Этот массив — это объект, связанный с HTML-кодом. Для этого в функции Тогглевиев () необходимо передать сам объект в функцию KO. Апплибиндинг ().<br/>Это приводит к тому, что массив иерархии будет привязан к следующему HTML-коду:<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

Обработчики событий для `mouseenter` и `mouseexit` добавляются в навигацию верхнего уровня для обработки раскрывающихся меню дочернего сайта, выполняемых в `addEventsToElements()` функции.

В нашем сложном примере навигации Новая загрузка страницы без локального кэширования показывает, что время, затраченное на работу сервера, было обрезано от структурной навигации, чтобы получить похожий результат в подходе управляемой навигации.

### <a name="about-the-javascript-file"></a>О файле JavaScript...

>[!NOTE]
>При использовании пользовательского кода JavaScript убедитесь, что общедоступная сеть CDN включена и файл находится в расположении CDN.

Весь файл JavaScript выглядит следующим образом:

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

Чтобы обобщеть код, приведенный выше в `jQuery $(document).ready` функции, `viewModel object` создается, а затем `loadNavigationNodes()` вызывается функция для этого объекта. Эта функция либо загружает ранее созданную иерархию навигации, хранящуюся в локальном хранилище HTML5 клиентского браузера, либо вызывает функцию `queryRemoteInterface()` .

`QueryRemoteInterface()` создает запрос с помощью `getRequest()` функции с параметром запроса, определенным ранее в сценарии, а затем возвращает данные с сервера. По сути, эти данные представляют собой массив всех сайтов в семействе веб-сайтов, представленных в виде объектов передачи данных с различными свойствами.

Затем эти данные анализируются в ранее определенных `SPO.Models.NavigationNode` объектах, которые используются `Knockout.js` для создания наблюдаемых свойств для использования данными в коде HTML, который мы определили ранее.

Затем объекты помещаются в массив Results. Этот массив разбивается на JSON с помощью функции маскирования и хранится в хранилище локального браузера для улучшения производительности при последующих загрузках страниц.

### <a name="benefits-of-this-approach"></a>Преимущества этого подхода

Одним из основных преимуществ [этого подхода](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) является то, что с помощью ЛОКАЛЬНОГО хранилища HTML5 структура навигации хранится локально для пользователя при следующей загрузке страницы. Мы получаем значительные улучшения производительности при использовании API поиска для структурной навигации; Тем не менее, для выполнения и настройки этих функций требуется техническая поддержка.

В [примере реализации](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)сайты упорядочиваются так же, как и встроенная структурная навигация; Алфавитный порядок. Если вы хотели бы отказываться от этого порядка, он был бы более сложным для разработки и обслуживания. Кроме того, этот подход требует отклонения от поддерживаемых эталонных страниц. Если настраиваемая эталонная страница не поддерживается, ваш сайт будет проигнорирован при обновлениях и улучшениях, которые корпорация Майкрософт делает с эталонными страницами.

[Приведенный выше код](#about-the-javascript-file) имеет следующие зависимости:

- jQuery https://jquery.com/
- Кноккаутжс — https://knockoutjs.com/
- Linq.js https://linqjs.codeplex.com/ или github.com/neuecc/linq.js

Текущая версия Линкжс не содержит метод Бихиерарчи, используемый в приведенном выше коде, и нарушает код навигации. Чтобы устранить эту проблему, добавьте следующий метод в файл Linq.js перед строкой `Flatten: function ()` .

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a>Связанные статьи

[Обзор управляемой навигации в SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

[Кэширование структуры навигации и производительность](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)
