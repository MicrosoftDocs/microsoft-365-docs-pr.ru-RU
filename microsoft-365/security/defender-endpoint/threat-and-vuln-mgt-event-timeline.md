---
title: Хронология событий в контроль угроз и уязвимостей
description: Временная шкала событий — это лента новостей о рисках, которая позволяет интерпретировать, как вводится риск в организацию и какие меры по ее снижению были смягчаемы.
keywords: временной шкале событий, временной шкале событий Microsoft Defender для конечных точек, временной шкале событий Microsoft Defender для конечной точки, контроль угроз и уязвимостей, Microsoft Defender для endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 64362598ff4b0512eb110917071e6d32abb8ede9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933485"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a>Временная шкала событий — контроль угроз и уязвимостей

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Область применения:**
- [Microsoft Defender для конечной точки](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Хотите испытать Microsoft Defender для конечной точки? [Зарегистрився для бесплатной пробной.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Временная шкала событий — это лента новостей о рисках, которая помогает интерпретировать, как риск вводится в организацию с помощью новых уязвимостей или эксплойтов. Можно просмотреть события, которые могут повлиять на риск организации. Например, вы можете найти новые уязвимости, которые были введены, уязвимости, которые стали эксплуатироваться, использовать, которые были добавлены в набор эксплойтов и другие.

В хронике событий также [](tvm-exposure-score.md) рассказывается история оценки экспозиции и [microsoft Secure Score для](tvm-microsoft-secure-score-devices.md) устройств, чтобы можно было определить причину больших изменений. События могут повлиять на ваши устройства или оценку для устройств. Уменьшите воздействие, реась на то, что необходимо устранять, основываясь на приоритетных [рекомендациях по безопасности.](tvm-security-recommendation.md)

>[!TIP]
>Чтобы получить сообщения о новых событиях уязвимости, см. в руб. Настройка уведомлений об уязвимости в [Microsoft Defender для endpoint](configure-vulnerability-email-notifications.md)

## <a name="navigate-to-the-event-timeline-page"></a>Перейдите на страницу временной шкалы событий

Кроме того, на панели мониторинга контроль угроз и уязвимостей [три точки входа:](tvm-dashboard-insights.md)

- **Карта оценки экспозиции** организации. Наведите курсор над точками событий в графе "Оценка экспозиции со временем" и выберите "См. все события этого дня". События представляют уязвимости программного обеспечения.
- **Microsoft Secure Score for Devices:** Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day". События представляют собой новые оценки конфигурации.
- **Верхняя карта** событий: Выберите "Показать больше" в нижней части таблицы событий верхней части. Карта отображает три наиболее важных события за последние 7 дней. Важные события могут включать, если событие затрагивает большое количество устройств или является критической уязвимостью.

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a>Оценка экспозиции и microsoft Secure Score для устройств

На панели контроль угроз и уязвимостей наведите курсор над графиком показателей экспозиции, чтобы просмотреть события уязвимости программного обеспечения с того дня, которые повлияли на ваши устройства. Наведите курсор над графом Microsoft Secure Score для устройств, чтобы просмотреть новые оценки конфигурации безопасности, влияющие на ваш результат.

Если нет событий, влияющих на устройства или оценку для устройств, то ни одно из них не будет показано.

![Оценка экспозиции ](images/tvm-event-timeline-exposure-score350.png) 
 ![ колеблется Microsoft Secure Score для устройств наведении](images/tvm-event-timeline-device-hover360.png)

### <a name="drill-down-to-events-from-that-day"></a>Сверлить до событий с этого дня

Выбор show **all events from this day** takes you to the Event timeline page with a custom date range for that day.

![Временная шкала событий, выбранный настраиваемый диапазон дат](images/tvm-event-timeline-drilldown.png)

Выберите **настраиваемый** диапазон, чтобы изменить диапазон дат на другой настраиваемый или заранее установленный диапазон времени.

![Параметры диапазона даты даты событий](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a>Обзор временной шкалы событий

На странице Временной шкалы событий можно просмотреть всю необходимую информацию, связанную с событием. 

Функции:

- Настройка столбцов
- Фильтр по типу событий или процентам устройств с влиянием
- Просмотр 30, 50 или 100 элементов на страницу

Два больших числа в верхней части страницы показывают количество новых уязвимостей и уязвимостей, которые можно использовать, а не событий. Некоторые события могут иметь несколько уязвимостей, а некоторые уязвимости могут иметь несколько событий.

![Страница временной шкалы событий](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a>Columns

- **Дата:** месяц, день, год
- **Event:** impactful event, including component, type and number of impacted devices
- **Связанный компонент:** программное обеспечение
- **Первоначально повлияли устройства:** количество и процент, на которые повлияли устройства, когда это событие первоначально произошло. Кроме того, можно фильтровать на проценте от общего числа устройств, на которые первоначально повлияли устройства.
- **В настоящее время влияет на устройства:** текущее число и процент устройств, которые это событие в настоящее время влияет. Это поле можно найти, выбрав **столбцы Customize.**
- **Типы:** отражают события, отпечатав время, которые влияют на результат. Их можно отфильтровать.
    - Эксплойт, добавленный в набор эксплойтов
    - Проверка эксплойтов
    - Новый общедоступный эксплойт
    - Новая уязвимость
    - Новая оценка конфигурации
- **Тенденция показателей:** тенденция оценки экспозиции

### <a name="icons"></a>Значки

Рядом с событиями отображаются следующие значки:

- ![значок ошибки](images/tvm-black-bug-icon.png) Новый общедоступный эксплойт
- ![значок предупреждения об отчете](images/report-warning-icon.png) Опубликована новая уязвимость
- ![набор эксплойтов](images/bug-lightning-icon2.png) Эксплойт, найденный в наборе эксплойтов
- ![Значок ошибки с значоком предупреждения](images/bug-caution-icon2.png) Проверка эксплойтов

### <a name="drill-down-to-a-specific-event"></a>Сверлить до определенного события

После выбора события вылет появится со списком сведений и текущих резюме, влияющих на устройства. Вы можете показать больше резюме или просмотреть связанную рекомендацию.

Стрелка ниже "тенденция оценки" помогает определить, было ли это событие потенциально поднято или понижено для оценки воздействия организации. Более высокая оценка экспозиции означает, что устройства более уязвимы для эксплуатации.

![Вылет временной шкалы событий](images/tvm-event-timeline-flyout500.png)

Оттуда выберите **Перейти к** связанной рекомендации по безопасности, чтобы просмотреть рекомендации, которые касаются новой уязвимости программного обеспечения на странице [рекомендации безопасности](tvm-security-recommendation.md). После прочтения сведений о описании и уязвимости в рекомендации по безопасности можно отправить запрос на исправление и отслеживать запрос на странице [исправление.](tvm-remediation.md)  

## <a name="view-event-timelines-in-software-pages"></a>Просмотр временной шкалы событий на страницах программного обеспечения

Чтобы открыть страницу программного обеспечения, выберите событие > имя гиперссылки программного обеспечения (например, Visual Studio 2017 г.) в разделе "Связанный компонент" в вылете. [Дополнительные новости о страницах программного обеспечения](tvm-software-inventory.md#software-pages)

Полная страница будет отображаться со всеми деталями определенного программного обеспечения. Мышь над графиком, чтобы увидеть хронологию событий для этого конкретного программного обеспечения.

![Страница программного обеспечения с графиком событий](images/tvm-event-timeline-software2.png)

Перейдите на вкладку временной шкалы событий, чтобы просмотреть все события, связанные с этим программным обеспечением. Также можно увидеть рекомендации по безопасности, обнаруженные уязвимости, установленные устройства и распространение версий.

![Страница программного обеспечения со вкладками Временной шкалы событий](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a>Статьи по теме

- [Обзор угроз и управление уязвимостями](next-gen-threat-and-vuln-mgt.md)
- [Панель мониторинга](tvm-dashboard-insights.md)
- [Показатель уязвимости](tvm-exposure-score.md)
- [Рекомендации по безопасности](tvm-security-recommendation.md)
- [Устранение уязвимостей](tvm-remediation.md)
- [Инвентаризация программного обеспечения](tvm-software-inventory.md)

