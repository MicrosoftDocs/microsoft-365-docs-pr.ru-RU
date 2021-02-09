---
title: Таблица AlertEvidence в схеме повышенной охоты
description: Сведения о сведениях, связанных с оповещениями, в таблице AlertEvidence схемы повышенной охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, evidence, file, IP address, device, machine, user, account
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
ms.openlocfilehash: 7457084d49c5a9fef4ef79abc7702c6b473efcd2
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145305"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в схеме повышенной охоты содержит сведения о различных сущностями — файлах, IP-адресах, URL-адресах, пользователях или устройствах, связанных с оповещениями из `AlertEvidence` Microsoft Defender для конечной точки, Microsoft Defender для Office 365, Microsoft Cloud App Security и Microsoft Defender для удостоверений. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `AlertId` | string | Уникальный идентификатор оповещения |
| `ServiceSource` | string | Продукт или служба, которые предоставили сведения об оповещении |
| `EntityType` | string | Тип объекта, например файл, процесс, устройство или пользователь |
| `EvidenceRole` | string | Как сущность участвует в оповещении, указывающее, влияет ли он или просто связан |
| `EvidenceDirection` | string | Указывает, является ли сущность источником или местом назначения сетевого подключения |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FolderPath` | string | Папка, содержащая файл, к которой было применено записано действие |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполняется — используйте столбец SHA1, если он доступен. |
| `FileSize` | int | Размер файла в ветвях |
| `ThreatFamily` | string | Семейство вредоносных программ, под которые был классифицирован подозрительный или вредоносный файл или процесс |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `RemoteUrl` | string | URL-адрес или полное доменное имя, к которому выполнено подключение |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | string | Домен учетной записи |
| `AccountSid` | string | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | string | Уникальный идентификатор учетной записи в Azure Active Directory |
| `AccountUpn` | string | Имя пользователя-пользователя (UPN) учетной записи |
| `DeviceId` | string | Уникальный идентификатор устройства в службе |
| `DeviceName` | string | Полное доменное имя компьютера |
| `LocalIP` | string | IP-адрес, присвоенный локальному устройству, используемму во время связи |
| `NetworkMessageId` | string | Уникальный идентификатор сообщения электронной почты, сформированный в Office 365 |
| `EmailSubject` | string | Тема письма |
| `ApplicationId` | string | Уникальный идентификатор приложения |
| `Application` | string | Приложение, которое выполнило записанную действие |
| `ProcessCommandLine` | string | Командная строка, используемая для создания нового процесса |
| `AdditionalFields` | string | Дополнительные сведения о событии в формате массива JSON |
| `RegistryKey` |string | Ключ реестра, к который было применено записано действие |
| `RegistryValueName` |string | Имя значения реестра, к которое было применено записанное действие |
| `RegistryValueData` |string | Данные значения реестра, к которое было применено записано действие |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
