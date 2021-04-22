---
title: Расширение расширенного охвата охоты с помощью правильных параметров
description: Проверьте параметры аудита на устройствах Windows и другие параметры, чтобы убедиться в том, что вы получаете самые исчерпывающие данные в ходе предварительной охоты
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
ms.openlocfilehash: 40cec28bf88445df13f78e672c4289d440b2b848
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935861"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Расширение расширенного охвата охоты с помощью правильных параметров

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[Расширенный поиск](advanced-hunting-overview.md) зависит от данных из различных источников, включая устройства, рабочее пространство Office 365, Azure AD и Microsoft Defender for Identity. Чтобы получить наиболее исчерпывающие данные, убедитесь, что у вас есть правильные параметры в соответствующих источниках данных.

## <a name="advanced-security-auditing-on-windows-devices"></a>Расширенный аудит безопасности на устройствах Windows
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
| Контроллер домена | Данные из локального Active Directory, отправленные в Microsoft Defender для удостоверений, обогащая сведения, связанные с удостоверениями, такие как сведения об учетной записи, действия логотипа и запросы Active Directory | Несколько таблиц, включая [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)и [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Установка сенсора Microsoft Defender для удостоверений](/azure-advanced-threat-protection/install-atp-step4)<br>- [Включим соответствующие события Windows](/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Похожие темы
- [Обзор расширенной охоты](advanced-hunting-overview.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)