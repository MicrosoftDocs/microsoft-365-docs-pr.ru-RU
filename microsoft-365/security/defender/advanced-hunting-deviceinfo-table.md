---
title: Таблица DeviceInfo в продвинутой схеме охоты
description: Сведения об ОС, имени компьютера и других сведениях о машине в таблице DeviceInfo в продвинутой схеме охоты
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка схемы, kusto, таблица, столбец, тип данных, описание, machineinfo, DeviceInfo, устройство, машина, ОС, платформа, пользователи
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
ms.openlocfilehash: 99a07b1517058b0e5ab241aaae9c6899e2994432
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689113"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender
- Microsoft Defender для конечной точки



Таблица в продвинутой схеме охоты содержит сведения о устройствах в организации, включая версию ОС, активных пользователей `DeviceInfo` и имя компьютера. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `ClientVersion` | string | Версия агента конечной точки или датчика, запущенного на компьютере |
| `PublicIP` | Строка | Общедоступный IP-адрес, используемый бортовой машиной для подключения к службе Microsoft Defender для конечных точек. Это может быть IP-адрес самой машины, устройство NAT или прокси-сервер |
| `OSArchitecture` | string | Архитектура операционной системы, используемой на компьютере |
| `OSPlatform` | string | Платформа операционной системы, используемой на компьютере. Это указывает на конкретные операционные системы, в том числе варианты в одной семье, такие как Windows 10 и Windows 7 |
| `OSBuild` | Строка | Сборка версии операционной системы, запущенной на компьютере |
| `IsAzureADJoined` | boolean | Индикатор Boolean о том, присоединяется ли машина к Azure Active Directory |
| `AadObjectId` | Строка | Уникальный идентификатор устройства в Azure AD |
| `LoggedOnUsers` | Строка | Список всех пользователей, зарегистрированных на компьютере во время события в формате массива JSON |
| `RegistryDeviceTag` | Строка | Тег машины, добавленный в реестр |
| `OSVersion` | string | Версия операционной системы, используемой на компьютере |
| `MachineGroup` | string | Машинная группа машины. Эта группа используется управлением доступом на основе ролей для определения доступа к машине |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Для определения уникальных событий этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp. |
| `OnboardingStatus` | Строка | Указывает, является ли устройство в настоящее время на борту или нет в Microsoft Defender Для конечной точки или если устройство не поддерживается |
|`AdditionalFields` | Строка | Дополнительные сведения о событии в формате массива JSON |
|`DeviceCategory` | Строка | Более широкая классификация, которая группировать определенные типы устройств в следующих категориях: Endpoint, Network device, IoT, Unknown |
|`DeviceType` | Строка | Тип устройства, основанного на целях и функциональных возможностях, таких как сетевое устройство, рабочие станции, сервер, мобильный телефон, игровая консоль или принтер |
|`DeviceSubType` | Строка | Дополнительный модификатор для определенных типов устройств, например, мобильное устройство может быть планшетом или смартфоном |
|`Model` | Строка | Имя модели или номер продукта от поставщика или производителя |
|`Vendor` | Строка | Имя поставщика или производителя продукта |
|`OSDistribution` | Строка | Распространение платформы ОС, таких как Ubuntu или RedHat для платформ Linux |
|`OSVersionInfo` | Строка | Дополнительные сведения о версии ОС, таких как популярное имя, кодовое имя или номер версии |
|`MergedDeviceIds` | Строка | Предыдущие ID устройства, которые были назначены одному устройству |
|`MergedToDeviceId` | Строка | Самый последний ID устройства, присвоенный устройству |

В таблице содержится информация об устройстве на основе пульса, которые являются периодическими отчетами или `DeviceInfo` сигналами с устройства. Каждые 15 минут устройство отправляет частичное сердцебиение, которое содержит часто меняющиеся атрибуты, такие как `LoggedOnUsers` . Один раз в день отправляется полное сердцебиение, содержащее атрибуты устройства.

Чтобы получить последнее состояние устройства, можно использовать следующий пример запроса:

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
