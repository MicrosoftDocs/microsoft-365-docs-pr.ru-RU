---
title: Получение релевантных сведений об объекте с помощью слежения за Go
description: Узнайте, как использовать средство "Поиск", чтобы быстро запросить релевантные сведения о сущности или событии с помощью расширенного поиска.
keywords: Расширенный поиск, инцидент, сведение, объект, отслеживание, релевантные события, Поиск угроз, Поиск угроз кибератак, поиск, запрос, телеметрии, Microsoft 365, защита от угроз Майкрософт
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 9ddad74d179ac16a25640e2bdf4ed4906f920102
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846884"
---
# <a name="quickly-hunt-for-entity-or-event-information-with-go-hunt"></a>Быстрый поиск сведений об объекте или событии с помощью службы поиска Go

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защитник Microsoft 365

С помощью действия *"Go Go* " можно быстро исследовать события и различные типы сущностей с помощью мощных [расширенных](advanced-hunting-overview.md) возможностей поиска на основе запросов. Это действие автоматически запускает Расширенный запрос поиска для поиска релевантных сведений о выбранном событии или сущности.

Действие по восвыполнению *Go* доступно в различных разделах центра безопасности, когда отображаются сведения о событиях или объектах. Например, можно использовать *слежение* за следующими разделами:

- На [странице инцидент](investigate-incidents.md#incident-overview)можно просмотреть сведения о пользователях, устройствах и многих других сущностях, связанных с инцидентом. При выборе объекта вы получаете дополнительные сведения, а также различные действия, которые можно выполнять с ентитити. В приведенном ниже примере выбирается почтовый ящик, в котором содержатся сведения о почтовом ящике, а также возможность поиска для получения дополнительных сведений о почтовом ящике.

    ![Изображение, содержащее сведения о почтовом ящике с параметром "Go"](../../media/mtp-ah/go-hunt-email.png)

- На странице инцидент можно также получить доступ к списку сущностей на вкладке свидетельство. Выбор одной из этих сущностей предоставляет возможность быстрого поиска сведений об этой сущности.

    ![Изображение, в котором показан выбранный файл с параметром "Go Go" на вкладке "свидетельство"](../../media/mtp-ah/go-hunt-evidence-file.png)


- При просмотре временной шкалы для устройства можно выбрать событие на временной шкале, чтобы просмотреть дополнительные сведения об этом событии. После выбора события вы получаете возможность поиска других важных событий в разделе Advanced поиске.

    ![Изображение, в котором показаны сведения о событиях с параметром "Go"](../../media/mtp-ah/go-hunt-event.png)

Выбор команды **"перейти" или "Поиск"** **для связанных событий** передает различные запросы в зависимости от того, выбрана сущность или событие.

## <a name="query-for-entity-information"></a>Запрос сведений об объекте
При использовании команды *Go* для получения сведений о пользователях, устройствах и других типах сущностей запрос проверяет все релевантные таблицы схемы для всех событий, содержащих эту сущность. Чтобы обеспечить управляемость результатов, запрос ограничивается до того же периода времени, что и самое раннее действие за прошедшие 30 дней, включающее сущность и связанное с инцидентом.

Ниже приведен пример запроса на перезапись для устройства.

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
### <a name="supported-entity-types"></a>Поддерживаемые типы объектов
С помощью команды *"слежение"* можно использовать следующие типы сущностей:

- Файлы
- Сообщения электронной почты
- Кластеры электронной почты
- Почтовые ящики
- Пользователи
- Устройства
- IP-адреса
- URL-адреса

## <a name="query-for-event-information"></a>Запрос сведений о событиях
При использовании команды *Go* для получения сведений о событии временной шкалы запрос проверяет все релевантные таблицы схемы для других событий во время выбранного события. Например, следующий запрос перечисляет события в различных таблицах схемы, которые выполнялись за один и тот же период времени, на одном устройстве:

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

## <a name="adjust-the-query"></a>Изменение запроса
С некоторыми знаниями [языка запросов](advanced-hunting-query-language.md), вы можете скорректировать запрос на свой выбор. Например, вы можете скорректировать эту строку, которая определяет размер временного интервала:

```kusto
Timestamp between ((selectedTimestamp - 1h) .. (selectedTimestamp + 1h))
```

Кроме изменения запроса для получения более релевантных результатов, можно также выполнить следующие действия:
- [Просмотр результатов в виде диаграмм](advanced-hunting-query-results.md#view-query-results-as-a-table-or-chart)
- [Создание настраиваемого правила обнаружения](custom-detection-rules.md)

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Работа с результатами запросов](advanced-hunting-query-results.md)
- [Настраиваемые правила обнаружения](custom-detection-rules.md)
