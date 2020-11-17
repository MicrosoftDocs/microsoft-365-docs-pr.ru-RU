---
title: Таблица клаудаппевентс в схеме расширенного поискового окна
description: Сведения о событиях из облачных приложений и служб в таблице Клаудаппевентс расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Клаудаппевентс, безопасность облачных приложений, МКАС
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087774"
---
# <a name="cloudappevents"></a>клаудаппевентс

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

В настоящее время в предварительной версии `CloudAppEvents` Таблица, содержащаяся в [расширенной](advanced-hunting-overview.md) схеме Поиск, содержит сведения о действиях в различных облачных приложениях и службах, в частности, Microsoft Teams и Exchange Online. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Эта таблица будет расширена для включения дополнительных действий, отслеживаемых Microsoft Cloud App Security. В конечном итоге, эта таблица будет включать в себя действия с файлами, хранящиеся в таблице [аппфиливентс](advanced-hunting-appfileevents-table.md) . Корпорация Майкрософт предоставит дополнительные рекомендации по мере перемещения данных в эту таблицу.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `ActionType` | string | Тип действия, вызвавшего событие |
| `Application` | string | Приложение, которое выполнило записанное действие |
| `ApplicationId` | string | Уникальный идентификатор приложения |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure Active Directory |
| `AccountDisplayName` | string | Имя пользователя учетной записи, отображаемое в адресной книге. Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия. |
| `IsAdminOperation` | string | Указывает, выполнялась ли действие администратором |
| `DeviceType` | string | Тип устройства, основанный на назначении и функциях, таких как "Сетевое устройство", "Рабочая станция", "сервер", "мобильное устройство", "игровая консоль" или "принтер" | 
| `OSPlatform` | string | Платформа операционной системы, запущенной на устройстве. В этом столбце указываются определенные операционные системы, в том числе варианты в пределах одного семейства, например Windows 10 и Windows 7. |
| `IPAddress` | string | IP-адрес, назначенный конечной точке и используемый во время связанных сетевых коммуникаций |
| `IsAnonymousProxy` | string | Указывает, принадлежит ли IP-адрес известному анонимному прокси-серверу |
| `CountryCode` | string | Код из двух букв, указывающий страну, в которой расположен IP-адрес клиента. |
| `City` | string | Город, в котором расположен IP-адрес клиента. |
| `Isp` | string | Поставщик услуг Интернета (ISP), связанный с IP-адресом |
| `UserAgent` | string | Сведения о агенте пользователя из веб-браузера или другого клиентского приложения |
| `ActivityType` | string | Тип действия, вызвавшего событие |
| `ActivityObjects` | string | Список объектов, например файлов или папок, которые участвовали в записанных действиях |
| `ObjectName` | string | Имя объекта, к которому было применено записанное действие |
| `ObjectType` | string | Тип объекта, например файл или папка, к которым было применено записанное действие |
| `ObjectId` | string | Уникальный идентификатор объекта, к которому было применено записанное действие |
| `ReportId` | string | Уникальный идентификатор для события |
| `RawEventData` | string | Сведения о событиях RAW из исходного приложения или службы в формате JSON |
| `AdditionalFields` | string | Дополнительные сведения о сущности или событии |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
