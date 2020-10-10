---
title: Таблица девицеинфо в схеме расширенного поискового окна
description: Сведения о ОС, имени компьютера и других сведениях о компьютере в таблице Девицеинфо расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, мачинеинфо, Девицеинфо, устройство, компьютер, ОС, платформа, пользователи
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 1fa093798b4e7704d5c6c5368dce7cb4081df48b
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413238"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)



`DeviceInfo`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит сведения о машинах в Организации, включая версию ОС, активные пользователи и имя компьютера. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `DeviceName` | string | Полное доменное имя компьютера |
| `ClientVersion` | string | Версия агента конечной точки или датчика, запущенного на компьютере |
| `PublicIP` | string | Общедоступный IP-адрес, используемый подключенным компьютером для подключения к службе Microsoft Defender ATP. Это может быть IP-адрес самого компьютера, устройства NAT или прокси-сервера. |
| `OSArchitecture` | string | Архитектура операционной системы, используемой на компьютере |
| `OSPlatform` | string | Платформа операционной системы, используемой на компьютере. Это указывает на конкретные операционные системы, в том числе варианты в пределах одного семейства, например Windows 10 и Windows 7. |
| `OSBuild` | string | Сборка версии операционной системы, запущенной на компьютере |
| `IsAzureADJoined` | boolean | Логический индикатор того, присоединен ли компьютер к Azure Active Directory. |
| `LoggedOnUsers` | string | Список всех пользователей, вошедших в систему на момент события в формате массива JSON |
| `RegistryDeviceTag` | string | Тег компьютера добавлен через реестр |
| `ReportId` | long | Идентификатор события на основе повторяющегося счетчика. Чтобы определить уникальные события, этот столбец должен использоваться в сочетании со столбцами DeviceName и timestamp |
| `OSVersion` | string | Версия операционной системы, используемой на компьютере |
| `MachineGroup` | string | Группа компьютеров компьютера. Эта группа используется в управлении доступом на основе ролей для определения доступа к компьютеру. |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
