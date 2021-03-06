---
title: Оптимизация настраиваемых расширений на современных страницах сайтов SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Узнайте, как оптимизировать производительность настраиваемых расширений на страницах современных сайтов SharePoint Online.
ms.openlocfilehash: af3645274b800a4eb8090957fc62397465022343
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288951"
---
# <a name="optimize-custom-extension-performance-in-sharepoint-online-modern-site-pages"></a>Оптимизация производительности настраиваемых расширений страниц современных сайтов SharePoint Online

Из этой статьи вы узнаете, как определять влияние настраиваемых расширений на задержку, распознаваемую конечным пользователем, и как устранять распространенные проблемы.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-custom-extensions"></a>Использование средства диагностики страниц SharePoint для анализа настраиваемых расширений

Средство "Диагностика страниц SharePoint" — это браузерное расширение для браузеров Chrome и новой версии Microsoft Edge (https://www.microsoft.com/edge), анализирующее страницы современных и классических сайтов публикаций SharePoint Online. Это средство предоставляет отчет о каждой проанализированной странице, показывающий, как она работает при заданных критериях производительности. Чтобы установить и изучить средство диагностики страниц SharePoint, ознакомьтесь со статьей [Использование средства диагностики страниц SharePoint Online](page-diagnostics-for-spo.md).

>[!NOTE]
>Средство диагностики страниц работает только в SharePoint Online, и его нельзя использовать на системной странице SharePoint.

При анализе страницы сайта SharePoint с помощью средства диагностики страниц SharePoint можно просматривать сведения о настраиваемых расширениях, превышающих базовые показатели, в результатах **Влияние расширений на время загрузки** и/или **Использовано слишком много расширений** на панели _Диагностические тесты_. 

Возможные результаты:

- **Внимание** (красный цвет) — любое _настраиваемое_ расширение, требующее более **одной** секунды на загрузку. Общее время загрузки распределяется в результатах теста в зависимости от времени, потраченного на загрузку модулей и инициализацию. Кроме того, если на странице слишком много расширений, они могут влиять на время загрузки страницы, что будет выделено, если на странице используется **семь** и более расширений.
- **Возможности улучшения** (желтый цвет). Если используется **пять** и более расширений, они будут выделены в этом разделе как предупреждение, пока не начнется использование семи и более расширений, которые будут выделены как "Внимание".
- **Действия не требуются** (зеленый цвет) — загрузка любого расширения занимает не больше одной секунды.

Если расширение влияет на время загрузки страницы или на странице слишком много расширений, результат отображается в разделе **Внимание,** требуемом для результатов. Щелкните результаты, чтобы просмотреть сведения о том, какое расширение загружается медленно, или если выделено слишком много расширений. В последующих обновлениях средства диагностики страниц SharePoint могут быть обновленные правила анализа, поэтому убедитесь, что у вас всегда есть последняя версия средства.

![Анализ времени загрузки страницы](../media/page-diagnostics-for-spo/pagediag-extensions-load-time.png)

Результаты содержат следующие данные:

- **Имя и идентификатор** — идентификационные данные, необходимые при поиске расширения на странице
- **Total** показывает общее время для расширения для загрузки модуля и инициализации. Это общее относительное время, заемного расширением для выполнения на странице от начала до конца.
- **МодульНая** нагрузка показывает время загрузки, оценки и загрузки файлов JavaScript и CSS. Затем начнется процесс Init.
- **Init** показывает время, необходимое для расширения для инициализации данных.

  Это асинхронный вызов, и время init — это вычисление времени для функции onInit, когда возвращенное обещание будет разрешено.

Эта информация предназначена для того, чтобы помочь проектировщикам и разработчикам устранять проблемы. С ней следует ознакомить команду по проектированию и разработке.

## <a name="overview-of-extensions"></a>Обзор расширений

С помощью расширений SharePoint Framework (SPFx) можно сделать SharePoint удобнее для пользователей. Используя расширения SharePoint Framework, можно настроить области уведомлений, панели инструментов, представления данных списков и другие аспекты SharePoint.

Расширения могут негативно влиять на производительность страницы SharePoint, так как она также использует ресурсы ЦП и сети для выполнения необходимых действий.

Существует четыре типа расширений:

- **Настройщики приложений** позволяют добавлять скрипты на страницу и получать доступ к заполнителям известных элементов HTML и дополнять их с использованием специальной отрисовки.
- **Настройщики полей** предоставляют измененные представления данных для полей списка.
- **Наборы команд** позволяют добавлять новые действия для команд SharePoint, а также предоставляют клиентский код, с помощью которого можно реализовать определенное поведение.
- **Модификатор поискового запроса (только предварительная версия)** вызывается непосредственно перед выполнением поискового запроса.

## <a name="remediate-extension-performance-issues"></a>Устранение проблем производительности расширений

Чтобы определить и устранить проблемы с производительностью расширений, указанных в окне **Влияние расширений на время загрузки страниц**, используйте инструкции, приведенные в этом разделе.

>[!NOTE]
>Настройщики приложений можно выполнять на раннем этапе жизненного цикла страницы, и это может влиять на производительность других расширений на странице.

Результаты аудита в средстве диагностики страниц содержат два этапа выполнения расширения, чтобы определить потенциальное влияние на производительность.

- **Загрузка модуля** — это время, необходимое для загрузки расширения, на которое влияет размер расширения. Поэтому рекомендуется объединять в расширении только необходимые библиотеки и выбирать облегченные библиотеки.
- **Инициализация** — это время инициализации расширения. Разработчики расширений должны учитывать, выполняет ли расширение ненужные действия или слишком много команд на этапе инициализации.

Авторы страниц также могут использовать результаты аудита, чтобы определить, содержит ли страница слишком много расширений, так как слишком большое количество расширений будет негативно влиять на производительность страницы.

- **Размер расширения и зависимости**
  - Для оптимальной статической загрузки ресурсов следует использовать сеть доставки содержимого (CDN) Office 365. Открытые источники CDN предпочтительнее использовать для файлов _JS и CSS_. Дополнительные сведения о сети Office 365 CDN см. в статье [Использование сети доставки содержимого Office 365 с SharePoint Online](use-microsoft-365-cdn-with-spo.md).
  - Повторно используйте такие платформы, как _React_ и _Fabric imports_, которые входят в состав SharePoint Framework (SPFx). Дополнительные сведения см. в статье [Обзор SharePoint Framework](/sharepoint/dev/spfx/sharepoint-framework-overview).
  - Убедитесь, что у вас установлена последняя версия SharePoint Framework, и обновляйте до новых версий, когда они станут доступны.
- **Извлечение или кэширование данных**
  - Если расширение использует дополнительные вызовы сервера, чтобы извлечь данные для отображения, убедитесь, что эти серверные API достаточно быстры и (или) выполняют кэширование на стороне клиента (например, с использованием _localStorage_ или _IndexDB_ для более крупных наборов).
  - Если для отображения важных данных требуется несколько вызовов, воспользуйтесь пакетной обработкой на сервере или другими методами объединения запросов в один вызов.
  - Если определенные данные задействуют медленные серверные API, а отображение может начаться и без них, рекомендуется отделить их в независимый вызов, который будет выполнен после отображения критически важных данных.
  - Когда одни и те же данные повторяются в разных частях, используйте один уровень данных, чтобы избежать повторения вызовов.
- **Время отображения**
  - Любые мультимедийные источники, такие как изображения и видеоролики, следует уменьшать до размера контейнера, устройства и (или) сети во избежание загрузки ненужных больших активов. Дополнительные сведения о пакетных зависимостях см. в статье [Использование сети доставки содержимого Office 365 с SharePoint Online](use-microsoft-365-cdn-with-spo.md).
  - Избегайте вызовов API, которые приводят к перегруппировке, применению сложных правил CSS или сложной анимации. Дополнительные сведения см. в статье [Минимизация перегруппировки браузера](https://developers.google.com/speed/docs/insights/browser-reflow).
  - Избегайте выполнения длительных цепных задач. Разбивайте такие задачи на отдельные очереди. Дополнительные сведения см. в статье [Оптимизация выполнения JavaScript](https://developers.google.com/web/fundamentals/performance/rendering/optimize-javascript-execution).
  - Резервируйте соответствующее место для асинхронного отображения визуальных элементов или элементов мультимедиа, чтобы избежать пропуска кадров и перебоев, известных как _подвисания_.
  - Если какой-либо из браузеров не поддерживает функцию, используемую для отображения, загрузите полизаполнение или исключите выполнение зависимого кода. А если эта функция не является критической, удалите ресурсы, например, обработчики событий, чтобы избежать утечки памяти.

Перед изменением в страниц для устранения проблем производительности запомните время загрузки страницы по результатам анализа. Снова запустите средство после внесения изменений, чтобы узнать, соответствует ли новый результат базовому стандарту, и проверить, сократилось ли время загрузки.

![Анализ времени загрузки страницы](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>Время загрузки страницы зависит от множества факторов, например от загрузки сети, времени суток и других переменных условий. Следует несколько раз проверить время загрузки страницы до и после внесения изменений, чтобы получить среднестатистические данные.

## <a name="related-topics"></a>Статьи по теме

[Настройка производительности SharePoint Online](tune-sharepoint-online-performance.md)

[Настройка производительности Office 365](tune-microsoft-365-performance.md)

[Производительность в современном интерфейсе SharePoint](/sharepoint/modern-experience-performance)

[Сети доставки содержимого](content-delivery-networks.md)

[Использование сети доставки содержимого Office 365 с SharePoint Online](use-microsoft-365-cdn-with-spo.md)