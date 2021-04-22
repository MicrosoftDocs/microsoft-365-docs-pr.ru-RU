---
title: Таблица AlertEvidence в продвинутой схеме охоты
description: Сведения о сведениях, связанных с оповещениями в таблице AlertEvidence в продвинутой схеме охоты
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AlertInfo, alert, entities, entities, evidence, file, IP address, device, machine, user, account
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
ms.openlocfilehash: 5ecab217a6181096e4689d78fa2bdddc0a767d0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932587"
---
# <a name="alertevidence"></a>AlertEvidence

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

Таблица в схеме расширенных схем охоты содержит сведения о различных сущностям, файлах, IP-адресах, URL-адресах, пользователях или устройствах, связанных с оповещениями из `AlertEvidence` Microsoft Defender для конечной точки, Microsoft Defender for Office 365, Microsoft Cloud App Security и Microsoft Defender for Identity. [](advanced-hunting-overview.md) Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Дата и время записи события |
| `AlertId` | string | Уникальный идентификатор оповещения |
| `ServiceSource` | Строка | Продукт или служба, которые предоставили сведения об оповещении |
| `EntityType` | Строка | Тип объекта, например файл, процесс, устройство или пользователь |
| `EvidenceRole` | Строка | Участие объекта в оповещении, указывающее, влияет ли оно на него или связано только с ним |
| `EvidenceDirection` | Строка | Указывает, является ли объект источником или предназначением сетевого подключения |
| `FileName` | string | Имя файла, к которому было применено записанное действие |
| `FolderPath` | string | Папка, содержащая файл, к котором было применено записано действие |
| `SHA1` | string | SHA-1 файла, к которому было применено записанное действие |
| `SHA256` | string | SHA-256 файла, к которому было применено записанное действие Это поле обычно не заполнено— используйте столбец SHA1 при наличии. |
| `FileSize` | int | Размер файла в bytes |
| `ThreatFamily` | Строка | Семейство вредоносных программ, засекреченное под подозрительным или вредоносным файлом или процессом |
| `RemoteIP` | string | IP-адрес, к которому выполнено подключение |
| `RemoteUrl` | string | URL-адрес или полное доменное имя, к которому выполнено подключение |
| `AccountName` | string | Имя пользователя учетной записи |
| `AccountDomain` | Строка | Домен учетной записи |
| `AccountSid` | Строка | Идентификатор безопасности (SID) учетной записи |
| `AccountObjectId` | Строка | Уникальный идентификатор учетной записи в Azure Active Directory |
| `AccountUpn` | Строка | Основное имя пользователя (UPN) учетной записи |
| `DeviceId` | Строка | Уникальный идентификатор устройства в службе |
| `DeviceName` | string | Полное доменное имя компьютера |
| `LocalIP` | string | IP-адрес, присвоенный локальному устройству, используемму во время связи |
| `NetworkMessageId` | string | Уникальный идентификатор сообщения электронной почты, сформированный в Office 365 |
| `EmailSubject` | string | Тема письма |
| `ApplicationId` | string | Уникальный идентификатор для приложения |
| `Application` | Строка | Приложение, которое выполнило записанную акцию |
| `ProcessCommandLine` | Строка | Командная строка, используемая для создания нового процесса |
| `AdditionalFields` | Строка | Дополнительные сведения о событии в формате массива JSON |
| `RegistryKey` |Строка | Ключ реестра, к который было применено записано действие |
| `RegistryValueName` |Строка | Имя значения реестра, к которое было применено записанное действие |
| `RegistryValueData` |Строка | Данные о значении реестра, которое было применено к зарегистрированным действиям |

## <a name="related-topics"></a>Похожие темы
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Применение рекомендаций по использованию запросов](advanced-hunting-best-practices.md)
