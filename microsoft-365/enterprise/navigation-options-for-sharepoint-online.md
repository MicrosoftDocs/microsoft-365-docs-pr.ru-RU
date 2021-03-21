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
description: В этой статье описываются сайты вариантов навигации с поддержкой SharePoint Publishing в SharePoint Online.
ms.openlocfilehash: b5989bf26ebf7bb1452f983af89a6e6739821d53
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923628"
---
# <a name="navigation-options-for-sharepoint-online"></a>Параметры навигации для SharePoint Online

В этой статье описываются сайты вариантов навигации с поддержкой SharePoint Publishing в SharePoint Online. Выбор и конфигурация навигации существенно влияют на производительность и масштабируемость сайтов в SharePoint Online. Шаблон сайта SharePoint Publishing следует использовать только в том случае, если это необходимо для централизованного портала, а функция публикации должна быть включена только на определенных сайтах и только в том случае, если это абсолютно необходимо, так как это может повлиять на производительность при неправильном использования.

>[!NOTE]
>Если вы используете современные параметры навигации SharePoint, такие как мега-меню, каскадная навигация или навигация в концентраторах, эта статья не применяется к вашему сайту. Современные архитектуры сайтов SharePoint используют более уплощенную иерархию сайтов и модель с использованием концентраторов и спичек. Это позволяет достичь многих сценариев, не требующих использования функции Публикации SharePoint.

## <a name="overview-of-navigation-options"></a>Обзор параметров навигации

Конфигурация поставщика навигации может существенно повлиять на производительность для всего сайта, и необходимо тщательно рассмотреть выбор поставщика навигации и конфигурации, которая эффективно масштабирования для требований сайта SharePoint. Существует два поставщика навигации, а также настраиваемые реализации навигации.

Первый вариант— [**структурная**](#using-structural-navigation-in-sharepoint-online)навигация — это рекомендуемый вариант навигации в SharePoint Online для классических сайтов Sharepoint, если включить структурную навигационную кэшинг **для вашего сайта.** Этот поставщик навигации отображает элементы навигации ниже текущего сайта, а также необязательно текущего сайта и его братьев и сестер. Он предоставляет дополнительные возможности, такие как обрезка безопасности и переумежение структуры сайта. Если кэширование отключено, это отрицательно скажется на производительности и масштабируемости и может быть подвержено регулирование.

Второй вариант — [**навигация управляемых (метаданных)**](#using-managed-navigation-and-metadata-in-sharepoint-online)— представляет элементы навигации с помощью набора терминов Управляемые метаданные. Мы рекомендуем отключить обрезку безопасности, если это не требуется. Обрезка безопасности включена в качестве параметра безопасности по умолчанию для этого поставщика навигации; однако многие сайты не требуют накладных расходов на обрезку безопасности, так как элементы навигации часто являются последовательными для всех пользователей сайта. При рекомендуемой конфигурации для отключения обрезки безопасности этот поставщик навигации не требует переоформить структуру сайта и имеет высокую масштабируемость с приемлемым влиянием на производительность.

Помимо поставщиков нестандартной навигации многие клиенты успешно реализовали альтернативные пользовательские реализации навигации. В [этой статье см.](#using-search-driven-client-side-scripting) сценарий с клиентской стороной поиска.
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>Плюсы и минусы параметров навигации SharePoint Online

В следующей таблице подводятся доводы "за" и "против" каждого варианта.

|Структурная навигация  |Управляемая навигация  |Навигация на основе поиска  |Поставщик настраиваемой навигации  |
|---------|---------|---------|---------|
|Плюсы:<br/><br/>Простой в обслуживании<br/>Безопасность обрезана<br/>Автоматически обновляется в течение 24 часов после изменения контента<br/>     |Плюсы:<br/><br/>Простой в обслуживании<br/>|Плюсы:<br/><br/>Безопасность обрезана<br/>Автоматически обновляется при добавлении сайтов<br/>Быстрая загрузка времени и локально кэшировать структуру навигации<br/>|Плюсы:<br/><br/>Более широкий выбор доступных вариантов<br/>Быстрая загрузка при правильном кэшинге<br/>Многие параметры хорошо работают с адаптивной конструкцией страницы<br/>|
|Минусы:<br/><br/>**Влияет на производительность при отключении кэшинга**<br/>При условии регулирования<br/>|Минусы:<br/><br/>Не обновляется автоматически для отражения структуры сайта<br/>**Влияет на производительность, если** включена обрезка безопасности или сложная структура навигации<br/>|Минусы:<br/><br/>Нет возможности легко заказать сайты<br/>Требуется настройка мастер-страницы (необходимые технические навыки)<br/>|Минусы:<br/><br/>Требуется настраиваемая разработка<br/>Необходимы внешние источники данных и кэш, хранимые, например Azure<br/>|

Наиболее подходящий вариант для сайта зависит от требований к сайту и от технических возможностей. Если вам нужен простой в настройке поставщик навигации, который автоматически обновляется [](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) при смене контента, то структурная навигация с включенной кэшированием — это хороший вариант.

>[!NOTE]
>Применение того же принципа, что и современные сайты SharePoint, упрощая общую структуру сайта в более лестную, не иерархическую структуру, повышает производительность и упрощает переход на современные сайты SharePoint. Это означает, что вместо одной коллекции сайтов с сотнями сайтов (subwebs) лучше использовать множество коллекций сайтов с очень немногими подвидами (subwebs).

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>Анализ производительности навигации в SharePoint Online

Средство [Page Diagnostics for SharePoint](./page-diagnostics-for-spo.md) — это расширение браузера для браузеров Microsoft Edge и Chrome, которое анализирует современный портал SharePoint Online и классические страницы сайтов публикации. Этот инструмент работает только для SharePoint Online и не может использоваться на странице системы SharePoint.

Средство создает отчет для каждой анализируемой страницы с указанием того, как страница выполняется в отношении заранее определенного набора правил, и отображает подробные сведения, когда результаты теста выпадают за пределы базового значения. Администраторы и дизайнеры SharePoint Online могут использовать этот инструмент для устранения проблем с производительностью, чтобы обеспечить оптимизацию новых страниц до публикации.

**SPRequestDuration** — это время, необходимое SharePoint для обработки страницы. Тяжелая навигация (например, в том числе страницы в навигации), сложные иерархии сайтов и другие параметры конфигурации и топологии могут значительно способствовать более длительным срокам.

## <a name="using-structural-navigation-in-sharepoint-online"></a>Использование структурной навигации в SharePoint Online

Это навигация, используемая по умолчанию, и является самым простым решением. Она не требует настройки, и не технический пользователь может легко добавлять элементы, скрывать элементы и управлять навигацией со страницы параметров. Рекомендуется [включить кэшинг,](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)в противном случае существует дорогостоящая компромиссная производительность.

### <a name="how-to-implement-structural-navigation-caching"></a>Реализация структурного кэшинга навигации

В **статье Параметры сайта** Look and Feel Navigation можно проверить, выбрана ли структурная навигация для глобальной навигации или текущей  >    >  навигации. Выбор страниц **Show отрицательно** скажется на производительности.

![Структурная навигация с выбранными подвидами Show](../media/SPONavOptionsStructuredShowSubsites.png)

Кэшинг может быть включен или отключен на уровне коллекции сайтов и на уровне сайта, и включен для обоих по умолчанию. Чтобы включить на уровне коллекции веб-сайтов, в статье **Параметры** веб-сайтов Администрирование коллекций веб-сайтов навигации, проверьте поле  >    >  для **включить кэшировать**.

![Включить кэшинг на уровне сайта](../media/structural-nav/structural-nav-caching-site-coll.png)

Чтобы включить на уровне сайта, в **статье Параметры** сайта  >  **навигации,** проверьте поле для **включить кэшировать**.

![Включить кэшинг на уровне сайта](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>Использование управляемой навигации и метаданных в SharePoint Online

Управление навигацией — это еще один вариант, который можно использовать для воссоздания большей части функций, что и структурная навигация. Управляемые метаданные можно настроить для включения или отключения обрезки безопасности. При настройке с отключенной обрезкой безопасности управление навигацией достаточно эффективно, так как загружает все ссылки навигации с постоянным количеством вызовов сервера. Включение обрезки безопасности, однако, отменяет некоторые преимущества управляемой навигации.

Если необходимо включить обрезку безопасности, рекомендуем:

- Обновление всех дружественных ссылок URL-адресов на простые ссылки
- Добавление необходимых узлов обрезки безопасности в качестве дружественных URL-адресов
- Ограничение количества элементов навигации не более 100 и не более 3 уровней глубиной

Многие сайты не требуют обрезки безопасности, так как структура навигации часто согласуется для всех пользователей сайта. Если обрезка безопасности отключена и в навигацию добавляется ссылка, доступ к которую имеют не все пользователи, ссылка будет по-прежнему показываться, но приведет к отказу в доступе. Нет риска случайного доступа к содержимому.

### <a name="how-to-implement-managed-navigation-and-the-results"></a>Реализация управляемой навигации и результатов

Существует несколько статей по docs.microsoft.com сведения об управляемой навигации. Например, см. [обзор управляемой навигации в SharePoint Server.](/sharepoint/administration/overview-of-managed-navigation)

Для реализации управляемой навигации необходимо настроить термины с URL-адресами, соответствующими структуре навигации сайта. Управляемые навигации можно даже вручную курировать, чтобы заменить структурную навигацию во многих случаях. Например:

![Структура сайта SharePoint Online](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>Использование клиентского сценария на основе поиска

Один распространенный класс пользовательских реализации навигации охватывает клиентские шаблоны проектирования, хранимые локальный кэш узлов навигации.

Эти поставщики навигации имеют несколько ключевых преимуществ:

- Как правило, они хорошо работают с отзывчивыми проектами страниц.
- Они чрезвычайно масштабируемы и исполняемы, так как они могут отрисовки без затрат ресурсов (и обновления в фоновом режиме после разового времени).
- Эти поставщики навигации могут получать данные навигации с помощью различных стратегий, от простых статических конфигураций до различных динамических поставщиков данных.

Примером поставщика данных является использование навигации, управляемой поиском, которая позволяет гибко скомпрометировать узлы навигации и эффективно обрабатывать обрезку безопасности.

Существуют и другие популярные варианты создания **настраиваемого поставщика навигации.** Просмотрите [решения навигации для порталов SharePoint Online,](/sharepoint/dev/solution-guidance/portal-navigation) чтобы получить дополнительные рекомендации по построению пользовательского поставщика навигации.

С помощью поиска можно использовать индексы, встроенные в фоновом режиме, с помощью непрерывного обхода. Результаты поиска извлекаются из индекса поиска, а результаты подрезаются. Обычно это происходит быстрее, чем у поставщиков навигации из-за необходимости обеспечения безопасности. Использование поиска для структурной навигации, особенно если у вас сложная структура сайта, значительно ускорит время загрузки страницы. Основное преимущество этого перед управляемой навигацией заключается в том, что вы извлекаем пользу из обрезки безопасности.

Этот подход предполагает создание настраиваемой мастер-страницы и замену нестандартного кода навигации на пользовательский HTML. Следуйте этой процедуре, описанной в следующем примере, чтобы заменить код навигации в `seattle.html` файле. В этом примере вы откроете файл и замените весь элемент `seattle.html` `id="DeltaTopNavigation"` пользовательским HTML-кодом.

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>Пример: Замена кода навигации из окна на мастер-странице

1. Перейдите на страницу Параметры сайта.
2. Откройте галерею мастер-страниц, нажав **мастер-страницы.**
3. Здесь вы можете перемещаться по библиотеке и скачивать `seattle.master` файл.
4. Изменить код с помощью текстового редактора и удалить блок кода в следующем снимке экрана.<br/>![Удаление показанного блока кода](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. Удалите код между тегами и тегами и замените его `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` следующим фрагментом:<br/>

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
6. Замените URL-адрес в якорной метке загрузки изображения в начале ссылкой на изображение загрузки в коллекции веб-сайтов. После внесения изменений переименуем файл и загрузите его в галерею страниц. Это создает новый файл .master.<br/>
7. Этот HTML — это базовая разметка, которая будет заполняться результатами поиска, возвращаемыми из кода JavaScript. Вам потребуется изменить код, чтобы изменить значение корневого значения var = URL-адрес коллекции сайтов, как показано в следующем фрагменте:<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. Результаты назначаются массиву self.nodes, и иерархия строится из объектов с помощью linq.js, назначающих выход в массив self.hierarchy. Этот массив является объектом, привязанным к HTML. Это делается в функции toggleView() путем передачи самостоятельного объекта функции ko.applyBinding() .<br/>Это приводит к тому, что массив иерархии должен быть привязан к следующему HTML:<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

Обработчики событий и добавлены в навигацию верхнего уровня для обработки подмышных выпадающих меню, которые делаются `mouseenter` `mouseexit` в `addEventsToElements()` функции.

В нашем сложном примере навигации новая загрузка страницы без локального кэшинга показывает, что время, затраченное на сервере, было сокращено с базовой структурной навигации, чтобы получить такой же результат, как и управляемый подход к навигации.

### <a name="about-the-javascript-file"></a>О файле JavaScript...

>[!NOTE]
>При использовании настраиваемого JavaScript убедитесь, что общедоступный CDN включен и файл находится в расположении CDN.

Весь файл JavaScript следующим образом:

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

Чтобы обобщить код, показанный выше в функции, создается, а затем называется функция на `jQuery $(document).ready` `viewModel object` этом `loadNavigationNodes()` объекте. Эта функция либо загружает ранее построенную иерархию навигации, хранимую в локальном хранилище HTML5 клиентского браузера, либо вызывает функцию `queryRemoteInterface()` .

`QueryRemoteInterface()` создает запрос с помощью функции с параметром запроса, определенным ранее в сценарии, а затем возвращает `getRequest()` данные с сервера. Эти данные по сути являются массивом всех сайтов в коллекции сайтов, представленных в качестве объектов передачи данных с различными свойствами.

Затем эти данные анализются в ранее определенные объекты, которые используются для создания наблюдаемых свойств для использования с помощью привязки данных к `SPO.Models.NavigationNode` значениям HTML, которые мы определили `Knockout.js` ранее.

Затем объекты помещаются в массив результатов. Этот массив разрезан в JSON с помощью knockout и хранится в локальном хранилище браузера для повышения производительности будущих нагрузок страниц.

### <a name="benefits-of-this-approach"></a>Преимущества этого подхода

Одно из [](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) основных преимуществ этого подхода заключается в том, что при использовании локального хранилища HTML5 навигация сохраняется локально для пользователя при следующей загрузке страницы. Мы получаем основные улучшения производительности с помощью API поиска для структурной навигации; однако для выполнения и настройки этой функции требуется некоторое техническое оснащение.

В [примере реализации](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)сайты заказываться так же, как и в случае с внеупорядоченной структурной навигацией; алфавитный порядок. Если вы хотите отклоняться от этого порядка, будет сложнее разрабатывать и поддерживать. Кроме того, этот подход требует отклоняться от поддерживаемых мастер-страниц. Если настраиваемая мастер-страница не поддерживается, на сайте будут не хватать обновлений и улучшений, которые корпорация Майкрософт вносит на мастер-страницы.

В [вышеуказанной](#about-the-javascript-file) коде есть следующие зависимости:

- jQuery — https://jquery.com/
- KnockoutJS — https://knockoutjs.com/
- Linq.js - https://linqjs.codeplex.com/ или github.com/neuecc/linq.js

Текущая версия LinqJS не содержит метода ByHierarchy, используемого в вышеуказанном коде, и будет нарушать код навигации. Чтобы исправить это, добавьте следующий метод в файл Linq.js перед `Flatten: function ()` строкой.

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
  
## <a name="related-topics"></a>Родственные темы

[Обзор управляемой навигации в SharePoint Server](/sharepoint/administration/overview-of-managed-navigation)

[Кэшинг и производительность структурной навигации](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)