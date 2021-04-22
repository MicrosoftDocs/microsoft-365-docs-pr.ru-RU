---
title: Таблица DeviceTvmSecureConfigurationAssessment в схеме расширенной охоты
description: Узнайте о событиях оценки безопасности в таблице DeviceTvmSecureConfigurationAssessment продвинутой схемы охоты. Эти события & управления уязвимостями предоставляют сведения об устройстве, а также сведения о конфигурации безопасности, последствиях и соответствия требованиям.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, Microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, threat & vulnerability management, TVM, device management, security configuration, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: e128eabc43c73949b5c747e51f3b59ac8b9a0ac5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933029"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender



Каждая строка в таблице `DeviceTvmSecureConfigurationAssessment` содержит событие оценки для определенной настройки безопасности от функции [контроля угроз и уязвимостей](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Используйте этот справочник для проверки последних результатов оценки и определения соответствия устройства требованиям.

Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `DeviceId` | string | Уникальный идентификатор устройства в службе |
| `DeviceName` | Строка | Полное доменное имя (FQDN) устройства |
| `OSPlatform` | Строка | Платформа операционной системы, запущенной на устройстве. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.|
| `Timestamp` | datetime | Дата и время создания записи |
| `ConfigurationId` | string | Уникальный идентификатор определенной настройки |
| `ConfigurationCategory` | string | Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности |
| `ConfigurationSubcategory` | string | Подкатегория или подгруппа, к которой относится настройка. Во многих случаях здесь описываются конкретные возможности или функции. |
| `ConfigurationImpact` | string | Оценка влияния настройки на общую оценку конфигурации (1–10) |
| `IsCompliant` | boolean | Указывает, правильно ли настроена конфигурация или политика |
| `IsApplicable` | boolean | Указывает, применима ли конфигурация или политика к устройству |
| `Context` | Строка | Дополнительные контекстные сведения о конфигурации или политике |
| `IsExpectedUserImpact` | boolean | Указывает, будет ли влияние пользователя, если применяется конфигурация или политика |

## <a name="related-topics"></a>Статьи по теме

- [Заблаговременный поиск угроз](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
- [Обзор контроля угроз и уязвимостей](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)