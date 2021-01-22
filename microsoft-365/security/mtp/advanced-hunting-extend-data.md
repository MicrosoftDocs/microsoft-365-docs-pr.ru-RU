---
title: Расширение расширенного охвата охоты с помощью правильных параметров
description: Проверьте параметры аудита на устройствах с Windows и другие параметры, чтобы убедиться, что вы получаете наиболее полный набор данных в области расширенных поисков
keywords: advanced hunting, incident, pivot, entity, audit settings, user account management, security group management, threat hunting, cyber threat hunting, search, query, telemetry, Microsoft 365, Microsoft Threat Protection
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
ms.openlocfilehash: 9773658bea752175fe7988b9322fb26a9d5b7f05
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929590"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Расширение расширенного охвата охоты с помощью правильных параметров

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Microsoft 365 Defender

[Расширенный поиск](advanced-hunting-overview.md) основывается на данных, полученных из различных источников, в том числе устройств, ваших рабочей области Office 365, Azure AD и Microsoft Defender для удостоверений. Чтобы получить наиболее полный набор данных, убедитесь, что у вас есть правильные параметры в соответствующих источниках данных.

## <a name="advanced-security-auditing-on-windows-devices"></a>Расширенный аудит безопасности на устройствах с Windows
Включите эти расширенные параметры аудита, чтобы получать данные о действиях на своих устройствах, включая локальное управление учетной записью, локальное управление группой безопасности и создание служб.

| Data | Описание | Таблица схемы | Способ настройки |
| --- | --- | --- | --- |
| Управление учетными записями | События, захваченные в качестве различных значений, указывающих на создание, удаление и другие действия, связанные с учетной `ActionType` записью | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Развертывание политики аудита безопасности: аудит [управления учетной записью пользователя](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Дополнительные политики аудита безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Управление группой безопасности | События, захваченные в качестве различных значений, указывающих на создание локальной группы безопасности `ActionType` и другие действия по управлению локальной группой | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Развертывание политики аудита безопасности: аудит [управления группой безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Дополнительные политики аудита безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Установка службы | События, захваченные со `ActionType` значением, указывающие на то, что `ServiceInstalled` служба создана | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Развертывание расширенных политик аудита безопасности: [аудит расширения системы безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Дополнительные политики аудита безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Датчик Microsoft Defender для удостоверений на контроллере домена
Если вы работаете с Active Directory локально, необходимо установить датчик Microsoft Defender для удостоверений на контроллере домена, чтобы получить данные для Microsoft Defender для удостоверений. При установке и правильной настройке эти данные также обеспечивают расширенный поиск через Microsoft Defender для удостоверений и предоставляют более целостную картину сведений об удостоверениях и событиях в вашей сети. Эти данные также улучшают возможности Microsoft Defender для удостоверений создавать соответствующие оповещения, на которые также распространяется расширенная охота. 

| Data | Описание | Таблица схемы | Способ настройки |
| --- | --- | --- | --- |
| Контроллер домена | Данные из локальной службы Active Directory, отсылаемой в Microsoft Defender для идентификации, обогащение сведений, связанных с удостоверениями, таких как сведения об учетной записи, действия при лоинге и запросы Active Directory | Несколько таблиц, включая [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)и [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Установка датчика Удостоверения в Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Включить соответствующие события Windows](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
