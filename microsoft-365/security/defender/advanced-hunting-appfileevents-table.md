---
title: Таблица AppFileEvents в продвинутой схеме охоты
description: Узнайте о событиях, связанных с файлами, связанных с облачными приложениями и службами, в таблице AppFileEvents продвинутой схемы охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AppFileEvents, Cloud App App Security, MCAS
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f25570916692c4568a6d09d92faaf57b0c155029
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071638"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в продвинутой схеме охоты содержит сведения о действиях, связанных с файлами, в облачных приложениях и службах, под наблюдением `AppFileEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!WARNING]
>Эта таблица скоро будет отменена. По 7 марта 2021 г. таблица больше не является `AppFileEvents` записями журналов. Пользователи, которые охотятся за действиями, связанными с файлами, в облачных службах и за пределами этой даты, должны использовать таблицу [CloudAppEvents.](advanced-hunting-cloudappevents-table.md) <br><br>Не забудьте найти запросы и пользовательские правила обнаружения, которые по-прежнему используются в таблице, и `AppFileEvents` изменить их для использования `CloudAppEvents` таблицы. Дополнительные инструкции по преобразованию затронутых запросов можно найти в Hunt в облачных приложениях с помощью расширенных методов охоты На защитника [Microsoft 365.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)


Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действий, которые вызвали событие. Подробные [сведения см. в](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) справке по схеме на портале |
| `Application` | строка | Приложение, которое выполнило записанную акцию |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FolderPath` | string | Папка, содержащая файл, к котором было применено записано действие |
| `PreviousFileName` | строка | Исходное имя файла, переименованного в результате действия |
| `PreviousFolderPath` | строка | Оригинальная папка, содержащая файл перед примененным действием |
| `Protocol` | строка | Используемый сетевой протокол |
| `AccountName` | строка | Имя пользователя учетной записи |
| `AccountDomain` | строка | Домен учетной записи |
| `AccountSid` | строка | Идентификатор безопасности (SID) учетной записи |
| `AccountUpn` | строка | Основное имя пользователя (UPN) учетной записи |
| `AccountObjectId` | строка | Уникальный идентификатор учетной записи в Azure AD |
| `AccountDisplayName` | строка | Имя пользователя учетной записи, отображаемого в адресной книге. Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии. |
| `DeviceName` | строка | Полное доменное имя (FQDN) устройства |
| `DeviceType` | строка | Тип устройства | 
| `OSPlatform` | строка | Платформа операционной системы, запущенной на устройстве. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7. |
| `IPAddress` | string | IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций |
| `Port` | строка | Порт TCP, используемый во время связи  |
| `DestinationDeviceName` | строка | Имя устройства под управлением серверного приложения, обрабатываемого записанным действием |
| `DestinationIPAddress` | строка | IP-адрес устройства под управлением серверного приложения, обработав записанное действие |
| `DestinationPort` | строка | Порт назначения связанных сетевых коммуникаций |
| `Location` | строка | Город, страна или другое географическое расположение, связанное с событием |
| `Isp` | строка | Поставщик интернет-услуг (ISP), связанный с IP-адресом конечной точки |
| `ReportId` | long | Уникальный идентификатор события |
| `AdditionalFields` | строка | Дополнительные сведения об объекте или событии |

>[!TIP]
> Подробные сведения о типах событий (значениях), поддерживаемых таблицей, используйте встроенную ссылку на схему, доступную `ActionType` в центре безопасности.


## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
