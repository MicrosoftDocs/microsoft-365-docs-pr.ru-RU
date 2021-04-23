---
title: Получить релевантные сведения об объекте с помощью охоты
description: Узнайте, как использовать средство охоты go для быстрого запроса соответствующих сведений об объекте или событии с помощью продвинутой охоты.
keywords: advanced hunting, incident, pivot, entity, go hunt, relevant events, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a78f37d8c1fed1063095e25f19136f0362f17db7
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952660"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Быстрая охота за сведениями о сущности или событиях с помощью go hunt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender
- Microsoft Defender для конечной точки

С помощью *действия go hunt* можно быстро исследовать события и различные типы сущности с помощью мощных расширенных возможностей охоты на основе запросов. [](advanced-hunting-overview.md) Это действие автоматически запускает расширенный запрос на поиск соответствующих сведений о выбранном событии или объекте.

Действие *охоты на перейти* доступно в различных разделах центра безопасности всякий раз, когда отображаются сведения о событии или объекте. Например, можно использовать go *hunt* из следующих разделов:

- На странице [инцидента](investigate-incidents.md#summary)можно просмотреть сведения о пользователях, устройствах и многих других сущностях, связанных с инцидентом. При выборе объекта вы получаете дополнительные сведения, а также различные действия, которые можно принять для этого объекта. В приведенной ниже примере выбирается почтовый ящик, в котором отображаются сведения о почтовом ящике, а также возможность охоты за дополнительными сведениями о почтовом ящике.

    ![Изображение, на котором показаны сведения о почтовом ящике с помощью параметра go hunt](../../media/mtp-ah/go-hunt-email.png)

- На странице инцидента можно также получить доступ к списку сущностям в вкладке доказательства. Выбор одного из этих сущностей позволяет быстро искать сведения об этом объекте.

    ![Изображение, показывающая выбранный файл с параметром go hunt на вкладке Evidence](../../media/mtp-ah/go-hunt-evidence-file.png)


- При просмотре временной шкалы устройства можно выбрать событие в временной шкале, чтобы просмотреть дополнительные сведения об этом событии. После выбора события вы получите возможность охотиться за другими соответствующими событиями в продвинутой охоте.

    ![Изображение, показывающая сведения о событии с помощью параметра "Охота на перейдите"](../../media/mtp-ah/go-hunt-event.png)

Выбор **перейти на охоту** или **охоту для** связанных событий передает различные запросы в зависимости от того, выбрали ли вы объект или событие.

## <a name="query-for-entity-information"></a>Запрос сведений об объектах
При использовании *go hunt* для запроса сведений о пользователе, устройстве или любом другом типе сущности запрос проверяет все соответствующие таблицы схемы на наличие событий, связанных с этим объектом. Чтобы сохранить управляемые результаты, запрос охватывает примерно тот же период времени, что и самое раннее действие за последние 30 дней, связанное с объектом и связанное с инцидентом.

Вот пример запроса на поиск для устройства:

```kusto
let selectedTimestamp = datetime(2020-06-02T02:06:47.1167157Z);
let deviceName = "fv-az770.example.com";
let deviceId = "device-guid";
search in (DeviceLogonEvents, DeviceProcessEvents, DeviceNetworkEvents, DeviceFileEvents, DeviceRegistryEvents, DeviceImageLoadEvents, DeviceEvents, DeviceImageLoadEvents, IdentityLogonEvents, IdentityQueryEvents)
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
and DeviceName == deviceName
// or RemoteDeviceName == deviceName
// or DeviceId == deviceId
| take 100
```
### <a name="supported-entity-types"></a>Поддерживаемые типы сущности
Вы можете использовать *go hunt* после выбора любого из этих типов сущности:

- Файлы
- Сообщения электронной почты
- Кластеры электронной почты
- Почтовые ящики
- Пользователи
- Устройства
- IP-адреса
- URL-адреса

## <a name="query-for-event-information"></a>Запрос сведений о событиях
При использовании *go hunt* для запроса сведений о событии временной шкалы запрос проверяет все соответствующие таблицы схемы для других событий во время выбранного события. Например, в следующих запросах перечислены события в различных таблицах схем, которые происходили примерно в один и тот же период времени на одном устройстве:

```kusto
// List relevant events 30 minutes before and after selected LogonAttempted event
let selectedEventTimestamp = datetime(2020-06-04T01:29:09.2496688Z);
search in (DeviceFileEvents, DeviceProcessEvents, DeviceEvents, DeviceRegistryEvents, DeviceNetworkEvents, DeviceImageLoadEvents, DeviceLogonEvents)
    Timestamp between ((selectedEventTimestamp - 30m) .. (selectedEventTimestamp + 30m))
    and DeviceId == "079ecf9c5798d249128817619606c1c47369eb3e"
| sort by Timestamp desc
| extend Relevance = iff(Timestamp == selectedEventTimestamp, "Selected event", iff(Timestamp < selectedEventTimestamp, "Earlier event", "Later event"))
| project-reorder Relevance
```

## <a name="adjust-the-query"></a>Настройка запроса
С некоторым знанием языка [запроса](advanced-hunting-query-language.md)можно настроить запрос на свои предпочтения. Например, можно настроить эту строку, которая определяет размер окна времени:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Помимо изменения запроса, чтобы получить более релевантные результаты, вы также можете:
- [Просмотр результатов в качестве диаграмм](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Создание настраиваемой нормы обнаружения](custom-detection-rules.md)

>[!NOTE]
>Некоторые таблицы в этой статье могут быть недоступны в Microsoft Defender для конечной точки. [Включи Microsoft 365 Defender для](m365d-enable.md) охоты на угрозы с помощью дополнительных источников данных. Вы можете переместить расширенные процессы охоты из Microsoft Defender для конечной точки в Microsoft 365 Defender, следуя шагам в миграции расширенных запросов охоты из [Microsoft Defender для конечной](advanced-hunting-migrate-from-mde.md)точки .

## <a name="related-topics"></a>Похожие темы
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Правила настраиваемого обнаружения](custom-detection-rules.md)
