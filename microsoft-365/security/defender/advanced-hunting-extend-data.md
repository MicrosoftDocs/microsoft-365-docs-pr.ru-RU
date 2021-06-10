---
title: Расширение расширенного охвата охоты с помощью правильных параметров
description: Проверьте параметры аудита на Windows устройствах и других параметрах, чтобы убедиться в том, что вы получаете самые исчерпывающие данные в ходе предварительной охоты
keywords: advanced hunting, incident, pivot, entity, audit settings, user account management, security group management, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft 365, Microsoft 365 Defender
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
ms.openlocfilehash: f4b1399b77583e95b109575a9577d8b1af89e6ad
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952672"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Расширение расширенного охвата охоты с помощью правильных параметров

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender
- Microsoft Defender для конечной точки

[Расширенный поиск](advanced-hunting-overview.md) зависит от данных из различных источников, включая устройства, Office 365, Azure AD и Microsoft Defender for Identity. Чтобы получить наиболее исчерпывающие данные, убедитесь, что у вас есть правильные параметры в соответствующих источниках данных.

## <a name="advanced-security-auditing-on-windows-devices"></a>Расширенный аудит безопасности на Windows устройствах
Включите эти расширенные параметры аудита, чтобы получить данные о действиях на устройствах, включая локальное управление учетной записью, локальное управление группой безопасности и создание службы.

| Data | Описание | Таблица схемы | Способ настройки |
| --- | --- | --- | --- |
| Управление учетными записями | События, запечатленные в качестве различных значений, указывающих на локальное создание учетной записи, удаление и другие действия, связанные `ActionType` с учетной записью | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Развертывание усовершенствованой политики аудита безопасности: [управление учетной записью пользователей аудита](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Дополнительные политики аудита безопасности](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Управление группой безопасности | События, запечатленные в качестве различных значений, указывающих на создание локальной группы безопасности и другие локальные действия `ActionType` по управлению группой | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Развертывание усовершенствованой политики аудита безопасности: [управление группой аудита безопасности](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Дополнительные политики аудита безопасности](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Установка службы | События, захваченные со `ActionType` значением, указывающие на то, что `ServiceInstalled` была создана служба | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Развертывание усовершенствованой политики аудита безопасности: [расширение системы безопасности аудита](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Дополнительные политики аудита безопасности](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Датчик Microsoft Defender для удостоверений на контроллере домена
Если вы работаете в помещении Active Directory, необходимо установить датчик Microsoft Defender для удостоверений на контроллере домена, чтобы получить данные для Microsoft Defender для identity. При установке и правильной настройке эти данные также обеспечивают расширенный поиск через Microsoft Defender для удостоверений и предоставляют более целостную картину сведений о удостоверениях и событиях в сети. Эти данные также улучшают возможности Microsoft Defender для удостоверений для создания соответствующих оповещений, которые также охватываются расширенной охотой. 

| Data | Описание | Таблица схемы | Способ настройки |
| --- | --- | --- | --- |
| Контроллер домена | Данные из локального Active Directory, отправленные в Microsoft Defender для удостоверений, обогащая сведения, связанные с удостоверениями, такие как сведения об учетной записи, действия логотипа и запросы Active Directory | Несколько таблиц, включая [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)и [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Установка сенсора Microsoft Defender для удостоверений](/azure-advanced-threat-protection/install-atp-step4)<br>- [Включим соответствующие Windows события](/azure-advanced-threat-protection/configure-event-collection) |

>[!NOTE]
>Некоторые таблицы в этой статье могут быть недоступны в Microsoft Defender для конечной точки. [Включи Microsoft 365 Defender,](m365d-enable.md) чтобы искать угрозы с помощью дополнительных источников данных. Вы можете переместить расширенные процессы охоты из Microsoft Defender для endpoint в Microsoft 365 Defender, следуя шагам в миграции расширенных запросов охоты из [Microsoft Defender для конечной точки](advanced-hunting-migrate-from-mde.md).

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)