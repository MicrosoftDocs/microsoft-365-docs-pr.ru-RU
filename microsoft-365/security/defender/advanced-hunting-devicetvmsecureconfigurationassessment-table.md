---
title: Таблица DeviceTvmSecureConfigurationAssessment в схеме расширенной охоты
description: Узнайте о событиях оценки безопасности в таблице DeviceTvmSecureConfigurationAssessment продвинутой схемы охоты. Эти события & управление уязвимостями предоставляют сведения об устройстве, а также сведения о конфигурации безопасности, влияние и сведения о соответствии требованиям.
keywords: передовая охота, охота на угрозы, охота на киберугрозы, Microsoft 365 Defender, Microsoft 365, m365, поиск, запрос, телеметрия, ссылка схемы, кусто, таблица, столбец, тип данных, описание, описание, угроза & управление уязвимостями, TVM, управление устройствами, конфигурация безопасности, DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 2e3e649911cb2ce63c2a49be0ebc93e35e8055d6
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2021
ms.locfileid: "52024221"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender
- Microsoft Defender для конечной точки



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