---
title: Таблица CloudAppEvents в продвинутой схеме охоты
description: Узнайте о событиях из облачных приложений и служб в таблице CloudAppEvents продвинутой схемы охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft threat protection, Microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 2aa592e70bce7bb469f851bedc542ee58cac0037
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498667"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender



Таблица в схеме расширенных схем охоты содержит сведения о действиях в различных облачных приложениях и службах, охваченных безопасностью облачных приложений Microsoft, в частности `CloudAppEvents` Dropbox, [](advanced-hunting-overview.md) Exchange Online, OneDrive, Microsoft Teams и SharePoint. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

>[!IMPORTANT]
>В эту таблицу включены сведения, которые раньше были доступны в `AppFileEvents` таблице. Начиная с 7 марта 2021 г. пользователи, которые охотятся через действия, связанные с файлами, в облачных службах и после этой даты, должны использовать `CloudAppEvents` таблицу вместо этого. <br><br>Не забудьте найти запросы и пользовательские правила обнаружения, которые по-прежнему используются в таблице, и `AppFileEvents` изменить их для использования `CloudAppEvents` таблицы. Дополнительные инструкции по преобразованию затронутых запросов можно найти в Hunt в облачных приложениях с помощью расширенных методов охоты На защитника [Microsoft 365.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)


Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действий, которые вызвали событие |
| `Application` | string | Приложение, которое выполнило записанную акцию |
| `ApplicationId` | string | Уникальный идентификатор для приложения |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure Active Directory |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемого в адресной книге. Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии. |
| `IsAdminOperation` | string | Указывает, выполнялось ли действие администратором |
| `DeviceType` | string | Тип устройства на основе целей и функциональных возможностей, таких как "Сетевое устройство", "Workstation", "Server", "Mobile", "Gaming console" или "Printer" | 
| `OSPlatform` | string | Платформа операционной системы, запущенной на устройстве. В этом столбце указаны определенные операционные системы, в том числе варианты в одной семье, например Windows 10 и Windows 7. |
| `IPAddress` | string | IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций |
| `IsAnonymousProxy` | string | Указывает, принадлежит ли IP-адрес известному анонимному прокси-серверу |
| `CountryCode` | string | Код из двух букв, указывающий страну, в которой расположен IP-адрес клиента |
| `City` | string | Город, в котором расположен IP-адрес клиента |
| `Isp` | string | Поставщик интернет-услуг (ISP), связанный с IP-адресом |
| `UserAgent` | string | Сведения агента пользователя из веб-браузера или другого клиентского приложения |
| `ActivityType` | string | Тип действий, которые вызвали событие |
| `ActivityObjects` | string | Список объектов, таких как файлы или папки, которые были вовлечены в записанную деятельность. |
| `ObjectName` | string | Имя объекта, к который было применено записанное действие |
| `ObjectType` | string | Тип объекта, например файла или папки, к который было применено записано действие |
| `ObjectId` | string | Уникальный идентификатор объекта, к котором было применено записано действие |
| `ReportId` | string | Уникальный идентификатор события |
| `RawEventData` | string | Необработанные сведения о событиях из исходных приложений или служб в формате JSON |
| `AdditionalFields` | string | Дополнительные сведения об объекте или событии |


## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
