---
title: Таблица CloudAppEvents в продвинутой схеме охоты
description: Узнайте о событиях из облачных приложений и служб в таблице CloudAppEvents продвинутой схемы охоты
keywords: передовая охота, охота на угрозы, поиск киберугроз, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка на схему, kusto, таблица, столбец, тип данных, описание, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 17f424d368c0df2f07cda41917f005e4163e5750
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935873"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender



Таблица в продвинутой схеме охоты содержит сведения о действиях в различных облачных приложениях и службах, охваченных `CloudAppEvents` microsoft Cloud App Security. [](advanced-hunting-overview.md) Для полного списка переперейти к [приложениям и службам, охваченным](#apps-and-services-covered). Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы. 

>[!IMPORTANT]
>В эту таблицу включены сведения, которые раньше были доступны в `AppFileEvents` таблице. Начиная с 7 марта 2021 г. пользователи, которые охотятся через действия, связанные с файлами, в облачных службах и после этой даты, должны использовать `CloudAppEvents` таблицу вместо этого. <br><br>Не забудьте найти запросы и пользовательские правила обнаружения, которые по-прежнему используются в таблице, и `AppFileEvents` изменить их для использования `CloudAppEvents` таблицы. Дополнительные инструкции по преобразованию затронутых запросов можно найти в Hunt в облачных приложениях с помощью расширенных методов охоты На защитника [Microsoft 365.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)


Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действий, которые вызвали событие |
| `Application` | Строка | Приложение, которое выполнило записанную акцию |
| `ApplicationId` | Строка | Уникальный идентификатор для приложения |
| `AccountObjectId` | Строка | Уникальный идентификатор учетной записи в Azure Active Directory |
| `AccountDisplayName` | Строка | Имя пользователя учетной записи, отображаемого в адресной книге. Как правило, сочетание данной или имени, среднего посвящения и фамилии или фамилии. |
| `IsAdminOperation` | Строка | Указывает, выполнялось ли действие администратором |
| `DeviceType` | Строка | Тип устройства на основе целей и функциональных возможностей, таких как "Сетевое устройство", "Workstation", "Server", "Mobile", "Gaming console" или "Printer" | 
| `OSPlatform` | Строка | Платформа операционной системы, запущенной на устройстве. В этом столбце указаны определенные операционные системы, в том числе варианты в одной семье, например Windows 10 и Windows 7. |
| `IPAddress` | Строка | IP-адрес, присвоенный конечной точке и используемый во время связанных сетевых коммуникаций |
| `IsAnonymousProxy` | Строка | Указывает, принадлежит ли IP-адрес известному анонимному прокси-серверу |
| `CountryCode` | Строка | Код из двух букв, указывающий страну, в которой расположен IP-адрес клиента |
| `City` | Строка | Город, в котором расположен IP-адрес клиента |
| `Isp` | Строка | Поставщик интернет-услуг (ISP), связанный с IP-адресом |
| `UserAgent` | Строка | Сведения агента пользователя из веб-браузера или другого клиентского приложения |
| `ActivityType` | Строка | Тип действий, которые вызвали событие |
| `ActivityObjects` | Строка | Список объектов, таких как файлы или папки, которые были вовлечены в записанную деятельность. |
| `ObjectName` | Строка | Имя объекта, к который было применено записанное действие |
| `ObjectType` | Строка | Тип объекта, например файла или папки, к который было применено записано действие |
| `ObjectId` | Строка | Уникальный идентификатор объекта, к котором было применено записано действие |
| `ReportId` | Строка | Уникальный идентификатор события |
| `RawEventData` | Строка | Необработанные сведения о событиях из исходных приложений или служб в формате JSON |
| `AdditionalFields` | Строка | Дополнительные сведения об объекте или событии |

## <a name="apps-and-services-covered"></a>Приложения и службы, охваченные

- Dropbox
- Dynamics 365
- Exchange Online
- Microsoft Teams
- OneDrive для бизнеса
- Power Automate
- Power BI
- SharePoint Online
- Skype для бизнеса
- Office 365
- Yammer 

## <a name="related-topics"></a>Похожие темы
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
