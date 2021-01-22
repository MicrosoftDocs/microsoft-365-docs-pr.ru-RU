---
title: Таблица DeviceInfo в схеме advanced hunting
description: Сведения об ОС, имени компьютера и других сведениях о компьютере в таблице DeviceInfo схемы расширенных поисков
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machineinfo, DeviceInfo, device, machine, OS, platform, users
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e445902ee83b734f84d02607905413a14c016b8f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931282"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender



Таблица в схеме advanced hunting содержит сведения о компьютерах в организации, включая версию `DeviceInfo` ОС, активных пользователей и имя компьютера. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `ClientVersion` | string | Версия агента конечной точки или датчика, запущенного на компьютере |
| `PublicIP` | string | Общедоступный IP-адрес, используемый подключенным компьютером для подключения к службе Microsoft Defender для конечных точек. Это может быть IP-адрес самого компьютера, устройство NAT или прокси-сервер. |
| `OSArchitecture` | string | Архитектура операционной системы, используемой на компьютере |
| `OSPlatform` | string | Платформа операционной системы, используемой на компьютере. Это указывает на определенные операционные системы, включая варианты одного семейства, такие как Windows 10 и Windows 7 |
| `OSBuild` | string | Версия сборки операционной системы, запущенной на компьютере |
| `IsAzureADJoined` | boolean | Boolean indicator of whether machine is joined to the Azure Active Directory |
| `LoggedOnUsers` | string | Список всех пользователей, которые вошли в систему на компьютере во время события в формате массива JSON |
| `RegistryDeviceTag` | string | Тег компьютера, добавленный через реестр |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и Timestamp |
| `OSVersion` | string | Версия операционной системы, используемой на компьютере |
| `MachineGroup` | string | Группа компьютера. Эта группа используется управлением доступом на основе ролей для определения доступа к компьютеру |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
