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
description: В этой статье описываются сайты параметров навигации с включенной публикацией SharePoint в SharePoint Online.
ms.openlocfilehash: 86cefc60a26687835fd6a88de7f249143811de4f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696444"
---
# <a name="navigation-options-for-sharepoint-online"></a>Параметры навигации для SharePoint Online

В этой статье описываются сайты параметров навигации с включенной публикацией SharePoint в SharePoint Online. Выбор и настройка навигации значительно влияют на производительность и масштабируемость сайтов в SharePoint Online. Шаблон сайта публикации SharePoint следует использовать только в том случае, если это необходимо для централизованного портала, а функция публикации должна быть включена только на определенных сайтах и только тогда, когда это абсолютно необходимо, так как это может повлиять на производительность при неправильном используется.

>[!NOTE]
>Если вы используете современные параметры навигации SharePoint, такие как мегаменю, каскадная навигация или навигация в центре, эта статья не относится к сайту. Современные архитектуры сайтов SharePoint используют более плоскую иерархию сайтов и модель центрального сайта. Это позволяет достичь многих сценариев, не требующих использования функции публикации SharePoint.

## <a name="overview-of-navigation-options"></a>Обзор параметров навигации

Конфигурация поставщика навигации может значительно повлиять на производительность всего сайта, и следует тщательно пронабделить выбор поставщика навигации и конфигурации, которая эффективно масштабирования соответствует требованиям сайта SharePoint. Существует два готовых поставщика навигации, а также настраиваемые реализации навигации.

Первый [**вариант,**](#using-structural-navigation-in-sharepoint-online)структурная навигация, — это рекомендуемый вариант навигации в SharePoint Online для классических сайтов SharePoint, если вы включите структурную навигацию для своего **сайта.** Этот поставщик навигации отображает элементы навигации под текущим сайтом и, при необходимости, текущий сайт и его элементы уровня. Он предоставляет дополнительные возможности, такие как обрезка по ролям безопасности и нумерация структуры сайта. Если кэширование отключено, это отрицательно скажется на производительности и масштабируемости и может влиять на регулирование.

Второй вариант, [**управл. Навигация (метаданные)**](#using-managed-navigation-and-metadata-in-sharepoint-online)представляет элементы навигации с использованием набора терминов управляемых метаданных. Рекомендуется отключить триммер безопасности, если это не требуется. Триммер безопасности включен в качестве параметра безопасности по умолчанию для этого поставщика навигации; Однако многие сайты не требуют дополнительных расходов на триммер безопасности, так как элементы навигации часто согласуются для всех пользователей сайта. При рекомендуемой конфигурации для отключения триммеров безопасности этот поставщик навигации не требует нумерации структуры сайта и имеет высокую масштабируемость с приемлемым влиянием на производительность.

В дополнение к внедренным поставщикам навигации, многие клиенты успешно реализовали альтернативные реализации настраиваемой навигации. См. сценарии на [основе поиска на стороне клиента](#using-search-driven-client-side-scripting) в этой статье.
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>Преимущества и недостатки параметров навигации SharePoint Online

В следующей таблице водятся преимущества и недостатки каждого из вариантов.

|Структурная навигация  |Управляемая навигация  |Навигация на основе поиска  |Поставщик настраиваемой навигации  |
|---------|---------|---------|---------|
|Плюсы:<br/><br/>Простое обслуживание<br/>Триммер безопасности<br/>Автоматическое обновление в течение 24 часов после изменения содержимого<br/>     |Плюсы:<br/><br/>Простое обслуживание<br/>|Плюсы:<br/><br/>Триммер безопасности<br/>Автоматическое обновление при добавлении сайтов<br/>Быстрая загрузка времени и локально кэшировать структуру навигации<br/>|Плюсы:<br/><br/>Более широкий выбор доступных вариантов<br/>Быстрая загрузка при правильном кэшинге<br/>Многие параметры хорошо работают с адаптивной разработкой страницы<br/>|
|Минусы:<br/><br/>**Влияет на производительность, если кэшинг отключен**<br/>Подавно к регулированием<br/>|Минусы:<br/><br/>Автоматическое обновление для отражения структуры сайта<br/>**Влияет на производительность, если** включена триммер безопасности или сложная структура навигации<br/>|Минусы:<br/><br/>Нет возможности легко заказать сайты<br/>Требуется настройка этакого страницы (требуются технические навыки)<br/>|Минусы:<br/><br/>Требуется настраиваемая разработка<br/>Требуется внешний источник данных или хранимый кэш, например Azure<br/>|

Наиболее подходящий вариант для сайта зависит от требований к сайту и технических возможностей. Если вам нужен простой в настройке поставщик навигации, который автоматически обновляется [](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) при смене содержимого, то структурная навигация с включенным кэшингом является хорошим вариантом.

>[!NOTE]
>Применение того же принципа, что и современные сайты SharePoint, упрощая общую структуру сайтов до плоской, неиехронной структуры, повышает производительность и упрощает переход на современные сайты SharePoint. Это означает, что вместо одного веб-сайта с сотнями сайтов (подсайтов) лучше использовать большое количество сайтов с очень большим количеством подсайтов ..

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>Анализ производительности навигации в SharePoint Online

Средство диагностики страниц [для SharePoint](https://aka.ms/perftool) — это расширение браузера для браузеров Microsoft Edge и Chrome, которое анализирует как современный портал SharePoint Online, так и страницы классического сайта публикации. Это средство работает только для SharePoint Online и не может использоваться на системной странице SharePoint.

Средство создает отчет для каждой проанализированой страницы, в котором показывая, как страница работает с заранее определенным набором правил, и отображает подробные сведения, когда результаты теста не попадают за пределы базового значения. Администраторы и дизайнеры SharePoint Online могут использовать это средство для устранения проблем с производительностью, чтобы обеспечить оптимизацию новых страниц перед публикацией.

**В частности, SPRequestDuration** — это время, необходимое SharePoint для обработки страницы. Интенсивное навигационное управление (например, включит страницы в структуру навигации), сложные иерархии сайтов и другие параметры конфигурации и топологии могут существенно ухудшить продолжительность.

## <a name="using-structural-navigation-in-sharepoint-online"></a>Использование структурной навигации в SharePoint Online

Это стандартная навигация, используемая по умолчанию, и является самым простым решением. Он не требует какой-либо настройки, и не технические пользователи также могут легко добавлять элементы, скрывать элементы и управлять навигацией со страницы параметров. Рекомендуется [включать кэшинг,](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)в противном случае существует дорогостоящая компромиссная возможность производительности.

### <a name="how-to-implement-structural-navigation-caching"></a>Реализация структурного кэшинга навигации

В **области навигации "Параметры** сайта" можно проверить, выбрана ли структурная навигация для глобальной или  >    >  текущей навигации. Выбор страницы **"Показать" будет** отрицательно влиять на производительность.

![Структурная навигация с выбранным представлением подсайтов](../media/SPONavOptionsStructuredShowSubsites.png)

Кэш можно включить или отключить на уровне и на уровне сайта, и включено для обоих этих режимов по умолчанию. Чтобы включить на уровне коллекции сайтов, в области **навигации**"Администрирование веб-сайтов для параметров сайта" в поле "Администрирование веб-сайтов" в поле "Включить кэшировать" в поле "Включить  >    >   **кэшинг".**

![Включить кэш на уровне сайта](../media/structural-nav/structural-nav-caching-site-coll.png)

Чтобы включить на уровне сайта, в **области** навигации "Параметры сайта" в поле "Включить  >   **кэш".**

![Включить кэш на уровне сайта](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>Использование управляемой навигации и метаданных в SharePoint Online

У управляемой навигации есть еще один вариант, который можно использовать для воссоздания большинства функций, таких как структурная навигация. Для управляемых метаданных можно настроить отключение или отключение триммеров безопасности. Если отключена триммерация безопасности, управличенная навигация является относительно эффективной, так как загружает все навигационные ссылки с постоянным числом вызовов сервера. Включение триммеров безопасности, однако, отменяет некоторые преимущества производительности управляемой навигации.

Если необходимо включить триммер безопасности, рекомендуется:

- Обновление всех ссылок на простые URL-адреса
- Добавление необходимых узлов триммеров безопасности в качестве url-адресов
- Ограничение числа элементов навигации не более 100 и не более 3 уровней в глубине

Для многих сайтов не требуется триммер безопасности, так как структура навигации часто согласована для всех пользователей сайта. Если триммер безопасности отключен и в навигацию добавлена ссылка, доступ к которую есть не у всех пользователей, ссылка будет по-прежнему отображена, но при этом будет отказано в доступе. Не существует риска случайного доступа к контенту.

### <a name="how-to-implement-managed-navigation-and-the-results"></a>Реализация управляемой навигации и результатов

Существует несколько статей о docs.microsoft.com о подробностях управляемой навигации. Например, [см. обзор управляемой навигации в SharePoint Server.](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

Для реализации управляемой навигации необходимо настроить термины с URL-адресами, соответствующими структуре навигации сайта. Управлию навигацию можно даже вручную сменить структурную навигацию во многих случаях. Пример:

![Структура сайта SharePoint Online](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>Использование клиентских сценариев на основе поиска

Один распространенный класс реализации настраиваемой навигации охватывает шаблоны проектирования, отрисоваемые клиентом, которые хранят локальный кэш узлов навигации.

Эти поставщики навигации имеют несколько ключевых преимуществ:

- Как правило, они хорошо работают с адаптивной схемой страниц.
- Они чрезвычайно масштабируемые и высоковыполнимы, так как они могут отрисовки без затрат на ресурсы (и обновления в фоновом режиме после окончания времени.
- Эти поставщики навигации могут получать данные навигации с помощью различных стратегий, от простых статических конфигураций до различных динамических поставщиков данных.

Примером поставщика данных является использование навигации на основе **поиска,** которая обеспечивает гибкость для эффективного нумерации узлов навигации и обработки триммеров безопасности.

Существуют другие популярные варианты создания **пользовательских поставщиков навигации.** Дополнительные [рекомендации по построению](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) настраиваемой службы навигации для порталов SharePoint Online можно найти в решениях навигации для SharePoint Online.

С помощью поиска можно использовать индексы, встроенные в фоновом режиме, с помощью непрерывного обхода контента. Результаты поиска извлекаются из индекса поиска, а результаты обрезаются по безопасности. Как правило, это быстрее, чем у поставщиков навигации, которые уже есть в комплекте, если требуется обрезка по ролю безопасности. Использование поиска для структурной навигации, особенно при использовании сложной структуры сайта, значительно ускоряет загрузку страниц. Основное преимущество этого по сравнению с управляемой навигацией заключается в том, что вы можете воспользоваться триммером безопасности.

Этот подход включает создание настраиваемой эталовой страницы и замену стандартного кода навигации на пользовательский HTML. Выполните следующую процедуру, описанную в следующем примере, чтобы заменить код навигации в `seattle.html` файле. В этом примере мы откроем файл и замените `seattle.html` весь элемент `id="DeltaTopNavigation"` пользовательским HTML-кодом.

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>Пример. Замена замещаемого кода навигации на этакодной странице

1. Перейдите на страницу "Параметры сайта".
2. Откройте галерею этастерных страниц, щелкнув **"Этакое страницы".**
3. Здесь вы можете перейти по библиотеке и скачать `seattle.master` файл.
4. Отредактировать код с помощью текстового редактора и удалить блок кода на следующем снимке экрана.<br/>![Удаление блока кода, показанного](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. Удалите код между тегами и `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` тегами и замените его следующим фрагментом кода:<br/>

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
6. Замените URL-адрес в загружаемом теге привязки изображения в начале ссылкой на загружающий образ в вашем коллекции веб-сайтов. После внесения изменений переименуем файл и загрузите его в галерею этакого страницы. При этом создается новый MASTER-файл.<br/>
7. Этот HTML-код — это базовая разметка, которая будет заполнена результатами поиска, возвращенными кодом JavaScript. Вам потребуется изменить код, чтобы изменить значение var root = "URL-адрес коллекции веб-сайтов", как показано в следующем фрагменте кода:<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. Результаты назначаются массиву self.nodes, а иерархия строится из объектов с помощью linq.js назначения выходных данных массиву self.hierarchy. Этот массив является объектом, привязанным к HTML. Это делается в функции toggleView() путем передачи самостоятельного объекта в функцию ko.applyBinding().<br/>После этого массив иерархии будет привязан к следующему HTML-коду:<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

Обработчики событий для навигации верхнего уровня и добавляются в них для обработки выпадающих меню подсайтов, которые `mouseenter` `mouseexit` делаются в `addEventsToElements()` функции.

В нашем примере сложной навигации новая нагрузка на страницу без локального кэшинга показывает, что время, затраченное на сервере, было сокращено из структурной навигации производительности, чтобы получить такой же результат, как и у управляемой навигации.

### <a name="about-the-javascript-file"></a>О файле JavaScript...

>[!NOTE]
>Если используется пользовательский JavaScript, убедитесь, что общедоступный CDN включен и файл находится в расположении CDN.

Весь файл JavaScript будет следующим:

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

Чтобы обобщить код, показанный выше в функции, создается и затем функция для `jQuery $(document).ready` `viewModel object` этого `loadNavigationNodes()` объекта. Эта функция загружает ранее созданную иерархию навигации, храняную в локальном хранилище HTML5 клиентского браузера, или вызывает `queryRemoteInterface()` функцию.

`QueryRemoteInterface()` создает запрос с помощью функции с параметром запроса, определенным ранее в сценарии, а затем возвращает данные `getRequest()` с сервера. По сути, эти данные представляют собой массив всех сайтов в коллекции сайтов, представленных в качестве объектов передачи данных с различными свойствами.

Затем эти данные анализются в ранее определенных объектах, которые используются для создания наблюдаемых свойств для использования при привязке данных значений в HTML-код, определенный `SPO.Models.NavigationNode` `Knockout.js` ранее.

Затем объекты помещаются в массив результатов. Этот массив разбит на JSON с помощью Knockout и сохраняется в локальном хранилище браузера для повышения производительности при будущих загрузках страниц.

### <a name="benefits-of-this-approach"></a>Преимущества этого подхода

Одно из [](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) основных преимуществ этого подхода заключается в том, что при использовании локального хранилища HTML5 навигация сохраняется локально для пользователя при следующей загрузке страницы. Мы получаем основные улучшения производительности благодаря использованию API поиска для структурной навигации; Однако для выполнения и настройки этой функции требуется техническая возможность.

В [примере реализации](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)сайты упорядочены так же, как и готовые структуры навигации; алфавитный порядок. Если вы хотите отклоняться от этого порядка, будет сложнее разрабатывать и поддерживать. Кроме того, для этого подхода необходимо отклоняться от поддерживаемых этастерных страниц. Если настраиваемая этаповая страница не поддерживается, на вашем сайте не будут обновлены и усовершенствования, которые корпорация Майкрософт вносит в этакое страницы.

[Вышеперечисленный](#about-the-javascript-file) код имеет следующие зависимости:

- jQuery — https://jquery.com/
- KnockoutJS — https://knockoutjs.com/
- Linq.js - https://linqjs.codeplex.com/ или github.com/neuecc/linq.js

Текущая версия LinqJS не содержит метод ByHierarchy, используемый в коде выше, и разорвет код навигации. Чтобы устранить эту проблему, добавьте следующий метод в Linq.js перед `Flatten: function ()` строкой.

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

[Кэшинг и производительность структурной навигации](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)
