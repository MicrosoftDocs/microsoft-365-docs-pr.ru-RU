---
title: Таблица CloudAppEvents в схеме advanced hunting
description: Узнайте о событиях из облачных приложений и служб в таблице CloudAppEvents схемы advanced hunting
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928457"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

В настоящее время доступна в предварительной версии, таблица в схеме advanced hunting содержит сведения о действиях в различных облачных приложениях и службах, в частности `CloudAppEvents` Microsoft Teams и Exchange Online. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Эта таблица будет расширена и будет включать дополнительные действия, отслеживаемые Microsoft Cloud App Security. В итоге эта таблица будет включать действия с файлами, хранимые в таблице [AppFileEvents.](advanced-hunting-appfileevents-table.md) Корпорация Майкрософт предоставит дополнительные рекомендации по мере перемещения дополнительных данных в эту таблицу.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действия, которое вызвало событие |
| `Application` | string | Приложение, которое выполнило записанную действие |
| `ApplicationId` | string | Уникальный идентификатор приложения |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure Active Directory |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемой в адресной книге. Обычно сочетание заданного или имени, инициации по середине и фамилии или фамилии. |
| `IsAdminOperation` | string | Указывает, было ли действие выполнено администратором |
| `DeviceType` | string | Тип устройства, основанного на назначении и функциональных возможностях, таких как "Сетевое устройство", "Рабочие станции", "Сервер", "Мобильные устройства", "Игровая консоль" или "Принтер" | 
| `OSPlatform` | string | Платформа операционной системы, запущенной на устройстве. В этом столбце указаны определенные операционные системы, включая варианты одного семейства, такие как Windows 10 и Windows 7. |
| `IPAddress` | string | IP-адрес, присвоенный конечной точке и используемый при связанных сетевых коммуникациях |
| `IsAnonymousProxy` | string | Указывает, принадлежит ли IP-адрес известному анонимному прокси-серверу |
| `CountryCode` | string | Двух буквный код, указывающий страну, в которой расположен IP-адрес клиента |
| `City` | string | Город, в котором расположен IP-адрес клиента |
| `Isp` | string | Поставщик услуг Интернета, связанный с IP-адресом |
| `UserAgent` | string | Сведения об агенте пользователя из веб-браузера или другого клиентского приложения |
| `ActivityType` | string | Тип действия, которое вызвало событие |
| `ActivityObjects` | string | Список объектов, таких как файлы или папки, которые были задействованы в записанной активности |
| `ObjectName` | string | Имя объекта, к который было применено записанное действие |
| `ObjectType` | string | Тип объекта, например файла или папки, к который было применено записано действие |
| `ObjectId` | string | Уникальный идентификатор объекта, к котором было применено записано действие |
| `ReportId` | string | Уникальный идентификатор события |
| `RawEventData` | string | Необработанные сведения о событиях из источника приложения или службы в формате JSON |
| `AdditionalFields` | string | Дополнительные сведения об объекте или событии |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
