---
title: Таблица алертевиденце в схеме расширенного поискового окна
description: Сведения, связанные с оповещениями в таблице Алертевиденце расширенной схемы поискового подсистемы
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ec6fe3d080efb396ce0ecacadd3d5d9a8fa9f8d1
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413202"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)

`AlertEvidence`Таблица в схеме [расширенного](advanced-hunting-overview.md) поискового заданных содержит сведения о различных сущностях — файлах, IP-адресах, URL-адресах, пользователях или устройствах, связанных с оповещениями из пакета ATP (Майкрософт) atp, Office 365 ATP, Microsoft Cloud App Security и Azure ATP. Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `AlertId` | string | Уникальный идентификатор оповещения |
| `ServiceSource` | string | Продукт или услуга, которые предоставили информацию оповещений |
| `EntityType` | string | Тип объекта, например файл, процесс, устройство или пользователь |
| `EvidenceRole` | string | Способ участия объекта в оповещении, указывающий на то, что он повлиял или является просто связанным |
| `EvidenceDirection` | string | Указывает, является ли объект источником или местом назначения сетевого подключения. |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FolderPath` | string | Папка, содержащая файл, к которому было применено записанное действие |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполняется — используйте столбец SHA1, если он доступен. |
| `FileSize` | int | Размер файла в байтах |
| `ThreatFamily` | string | Семейство вредоносных программ, которые были классифицированы подозрительным или вредоносным файлом или процессом |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `RemoteUrl` | string | URL-адрес или полное доменное имя, к которому выполнено подключение |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure Active Directory |
| `DeviceId` | string | Уникальный идентификатор устройства в службе |
| `DeviceName` | string | Полное доменное имя компьютера |
| `LocalIP` | string | IP-адрес, назначенный локальному устройству, используемому при обмене данными |
| `NetworkMessageId` | string | Уникальный идентификатор сообщения электронной почты, сформированный в Office 365 |
| `EmailSubject` | string | Тема письма |
| `ApplicationId` | string | Уникальный идентификатор приложения |
| `Application` | string | Приложение, которое выполнило записанное действие |
| `ProcessCommandLine` | string | Командная строка, используемая для создания нового процесса |
| `AdditionalFields` | string | Дополнительные сведения о событии в формате массива JSON |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
