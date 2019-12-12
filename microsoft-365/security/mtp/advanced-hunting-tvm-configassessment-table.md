---
title: Таблица DeviceTvmSecureConfigurationAssessment в схеме расширенной охоты
description: Сведения о событиях оценки безопасности функцией контроля угроз и уязвимостей в таблице DeviceTvmSecureConfigurationAssessment схемы расширенной охоты. Эти события предоставляют сведения о компьютере, а также сведения о настройке безопасности, влиянии и соответствии требованиям.
keywords: расширенная охота, охота на угрозы, охота на киберугрозы, поиск, запрос, телеметрия, ссылки на схему, kusto, таблица, столбец, тип данных, описание, контроль угроз и уязвимостей, TVM, управление устройствами, настройка безопасности, DeviceTvmSecureConfigurationAssessment
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 2fee44c0d9c9ff30ca23ccef863e056cadee7de8
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2019
ms.locfileid: "39911508"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

**Область применения:**
- Защита от угроз (Майкрософт)

[!include[Prerelease information](prerelease.md)]

Каждая строка в таблице `DeviceTvmSecureConfigurationAssessment` содержит событие оценки для определенной настройки безопасности от функции [контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Используйте этот справочник для проверки последних результатов оценки и определения соответствия устройства требованиям.

Сведения о других таблицах в схеме расширенной охоты см. в [справочнике по расширенной охоте](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `MachineId` | string | Уникальный идентификатор для обслуживаемого компьютера |
| `ComputerName` | string | Полное доменное имя компьютера |
| `OSPlatform` | string | Платформа операционной системы, используемой на компьютере. Здесь указываются конкретные операционные системы, включая варианты одного семейства, например Windows 10 и Windows 7.|
| `Timestamp` | datetime | Дата и время создания записи |
| `ConfigurationId` | string | Уникальный идентификатор определенной настройки |
| `ConfigurationCategory` | string | Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности |
| `ConfigurationSubcategory` | string | Подкатегория или подгруппа, к которой относится настройка. Во многих случаях здесь описываются конкретные возможности или функции. |
| `ConfigurationImpact` | string | Оценка влияния настройки на общую оценку конфигурации (1–10) |
| `IsCompliant` | boolean | Указывает, правильно ли настроена конфигурация или политика |

## <a name="related-topics"></a>См. также

- [Профилактическая охота на угрозы](advanced-hunting-overview.md)
- [Сведения о языке запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на угрозы в электронной почте и устройствах](advanced-hunting-query-emails-devices.md)
- [Общие сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
- [Обзор контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
