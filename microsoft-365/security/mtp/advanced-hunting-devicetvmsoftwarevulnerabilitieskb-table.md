---
title: Таблица DeviceTvmSoftwareVulnerabilitiesKB в схеме расширенного поиска
description: Узнайте об уязвимостях программного обеспечения, отслеживаемых средством контроля угроз и уязвимостей, в таблице DeviceTvmSoftwareVulnerabilitiesKB схемы расширенного поиска.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, метрическое содержание, схема, справочные материалы, Кусто, таблица, столбец, тип данных, описание, угроза & уязвимости, ТВМ, Управление устройствами, программное обеспечение, наличие уязвимостей, CVE ID, КВСС, Девицетвмсофтваревулнерабилитиескб
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
ms.openlocfilehash: d4969cdfa2851acc6f94e5e1a903a9b59f73489e
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648925"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

**Область применения:**
- Защита от угроз (Майкрософт)



Таблица `DeviceTvmSoftwareVulnerabilitiesKB` в схеме расширенного поиска содержит список уязвимостей, на наличие которых [средство контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) оценивает устройства. Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `CveId` | string | Уникальный идентификатор, назначенный уязвимости в системе общеизвестных уязвимостей и рисков (CVE) |
| `CvssScore` | string | Оценка серьезности, назначенная уязвимости в общей системе оценки уязвимостей (CVSS) |
| `IsExploitAvailable` | boolean | Указывает, является ли общедоступным код эксплойта для уязвимости |
| `VulnerabilitySeverityLevel` | string | Уровень серьезности, назначенный уязвимости на основании оценки CVSS и динамических коэффициентов, на которые влияет картина угроз |
| `LastModifiedTime` | datetime | Дата и время последнего изменения элемента или связанных метаданных |
| `PublishedDate` | datetime | Дата, когда уязвимость была раскрыта для общественности |
| `VulnerabilityDescription` | string | Описание уязвимостей и связанных рисков |
| `AffectedSoftware` | string | Список всех программных продуктов, на которые влияет уязвимость |

## <a name="related-topics"></a>См. также

- [Заблаговременный поиск угроз](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Слежение за устройствами, сообщениями электронной почты, приложениями и удостоверениями](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
- [Обзор контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
