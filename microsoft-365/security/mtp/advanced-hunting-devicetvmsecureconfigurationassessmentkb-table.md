---
title: Таблица DeviceTvmSecureConfigurationAssessmentKB в схеме расширенного поиска угроз
description: Узнайте о различных настройках безопасности, оцененных в Контроле угроз и уязвимостей, в таблице DeviceTvmSecureConfigurationAssessmentKB схемы расширенного поиска угроз.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справочник по схемам, Кусто, таблица, столбец, тип данных, описание, угроза & уязвимости, ТВМ, Управление устройствами, Настройка безопасности, МИТРЕ ATT&а Framework, база знаний, KB, Девицетвмсекуреконфигуратионассессменткб
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
ms.openlocfilehash: f2642a46f952d3324cec4936aeb813d4ee5507d1
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412998"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)



В таблице `DeviceTvmSecureConfigurationAssessmentKB` в схеме расширенного поиска содержатся сведения о различных настройках безопасности,— в том числе сведения о том, включено ли на устройстве автоматическое обновление, — которые проверяются с помощью [Контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). Кроме того, в ней также содержатся сведения о рисках, связанных отраслевых контрольных показателях, а также о применимых приемах и тактиках MITRE ATT&CK. Используйте этот справочник для создания запросов, возвращающих данные из таблицы.

Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).

| Имя столбца | Тип данных | Описание |
|-------------|-----------|-------------|
| `ConfigurationId` | string | Уникальный идентификатор определенной настройки |
| `ConfigurationImpact` | string | Оценка влияния настройки на общую оценку конфигурации (1–10) |
| `ConfigurationName` | string | Отображение названия настройки |
| `ConfigurationDescription` | string | Описание ошибки настройки |
| `RiskDescription` | string | Описание связанного риска |
| `ConfigurationCategory` | string | Категория или группа, к которой относится настройка: приложение, ОС, сеть, учетные записи, элементы безопасности|
| `ConfigurationSubcategory` | string |Подкатегория или подгруппа, к которой относится настройка. Во многих случаях здесь описываются конкретные возможности или функции. |
| `ConfigurationBenchmarks` | string | Список отраслевых контрольных показателей с рекомендациями по аналогичной или схожей настройке |
| `RelatedMitreTechniques` | string | Список приемов платформы Mitre ATT&CK, относящихся к настройке |
| `RelatedMitreTactics ` | string | Список тактик платформы Mitre ATT&CK, относящихся к настройке |

## <a name="related-topics"></a>См. также

- [Заблаговременный поиск угроз](advanced-hunting-overview.md)
- [Изучение языка запросов](advanced-hunting-query-language.md)
- [Использование общих запросов](advanced-hunting-shared-queries.md)
- [Охота на различных устройствах, в письмах, приложениях и удостоверениях](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
- [Обзор контроля угроз и уязвимостей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
