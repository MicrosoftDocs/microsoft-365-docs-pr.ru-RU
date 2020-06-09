---
title: Таблица алертевиденце в схеме расширенного поискового окна
description: Сведения о файлах, сетевых адресах, пользователях или сведениях об устройствах, связанных с созданными оповещениями в таблице Алертевиденце расширенной схемы подсистемы Поиск
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Алертинфо, оповещения, сущности, пользователь, учетная запись
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da6e84725aa391e4cb6056fadd327fdba2436214
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617090"
---
# <a name="alertevidence"></a>AlertEvidence

**Область применения:**
- Защита от угроз (Майкрософт)

`AlertEvidence`Таблица в схеме [расширенного](advanced-hunting-overview.md) поискового заданных содержит сведения о различных сущностях — файлах, IP-адресах, URL-адресах, пользователях или устройствах, связанных с оповещениями из пакета ATP (Майкрософт) atp, Office 365 ATP, Microsoft Cloud App Security и Azure ATP. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `AlertId` | string | Уникальный идентификатор оповещения |
| `EntityType` | string | Тип объекта, например файл, процесс, устройство или пользователь |
| `EvidenceRole` | string | Способ участия объекта в оповещении, указывающий на то, что он повлиял или является просто связанным |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполняется. Используйте столбец SHA1, если он доступен. |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `RemoteUrl` | string | URL-адрес или полное доменное имя, к которому выполнено подключение |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure AD |
| `DeviceId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `ThreatFamily` | string | Семейство вредоносных программ, которые были классифицированы подозрительным или вредоносным файлом или процессом |
| `EvidenceDirection` | string | Указывает, является ли объект источником или местом назначения сетевого подключения. |
| `AdditionalFields` | string | Дополнительные сведения о событии в формате массива JSON |

## <a name="related-topics"></a>Статьи по теме
- [Заблаговременный поиск угроз](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
