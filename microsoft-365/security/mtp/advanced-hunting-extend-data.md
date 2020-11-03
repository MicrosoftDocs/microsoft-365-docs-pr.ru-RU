---
title: Расширение расширенного контроля за пресроком действия с помощью правильных параметров
description: Проверьте параметры аудита на устройствах с Windows и другими параметрами, чтобы обеспечить получение самых полных данных в ходе расширенного поиска.
keywords: Расширенный поиск, инцидент, сводка, объект, параметры аудита, Управление учетными записями пользователей, Управление группами безопасности, Поиск угроз, Поиск угроз кибератак, поиск, запрос, телеметрии, Microsoft 365, защита от угроз Майкрософт
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 82faff2599cd61fa1a4deb3129e1e6780d3f529c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842480"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Расширение расширенного контроля за пресроком действия с помощью правильных параметров

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защитник Microsoft 365

[Расширенный](advanced-hunting-overview.md) Поиск использует данные, поступающие из различных источников, включая устройства, рабочие области Office 365, Azure AD и защитник Майкрософт для удостоверения. Чтобы получить наиболее полные данные, убедитесь, что у вас есть правильные параметры в соответствующих источниках данных.

## <a name="advanced-security-auditing-on-windows-devices"></a>Расширенный аудит безопасности для устройств с Windows
Включите эти расширенные параметры аудита, чтобы получить данные о действиях на устройствах, включая Управление локальными учетными записями, локальным управлением группами безопасности и созданием служб.

| Data | Описание | Таблица схемы | Способ настройки |
| --- | --- | --- | --- |
| Управление учетными записями | События, перехваченные как различные `ActionType` значения, указывающие создание локальной учетной записи, удаление и другие действия, связанные с учетными записями | [DeviceEvents](advanced-hunting-deviceevents-table.md) | — Развертывание расширенной политики аудита безопасности: [Аудит управления учетными записями пользователей](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Сведения о политиках расширенной проверки безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Управление группами безопасности | События, перехваченные как различные `ActionType` значения, указывающие на создание локальной группы безопасности и другие локальные действия по управлению группами | [DeviceEvents](advanced-hunting-deviceevents-table.md) | — Развертывание расширенной политики аудита безопасности: [Аудит управления группами безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Сведения о политиках расширенной проверки безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Установка службы | События, записанные со `ActionType` значением `ServiceInstalled` , указывающие на то, что служба была создана | [DeviceEvents](advanced-hunting-deviceevents-table.md) | — Развертывание расширенной политики аудита безопасности: [Аудит расширения системы безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Сведения о политиках расширенной проверки безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Защитник Майкрософт для датчика удостоверений на контроллере домена
Если вы используете Active Directory локально, вам необходимо установить защитник Майкрософт для датчика удостоверения на контроллере домена, чтобы получить данные для защитника Майкрософт для удостоверения. Если вы установили и правильно настроили, эти данные также помещаются на веб-каналы с помощью защитника Майкрософт для удостоверения и предоставляют более целостное изображение идентификационных данных и событий в сети. Эти данные также расширяют возможности защитника Майкрософт для удостоверения для создания соответствующих оповещений, которые также охватываются расширенным поиском. 

| Data | Описание | Таблица схемы | Способ настройки |
| --- | --- | --- | --- |
| Контроллер домена. | Данные из локальной службы Active Directory, отправленные в защитник Майкрософт для удостоверения, изменяя сведения, связанные с удостоверениями, такие как сведения об учетных записях, действиях входа и запросах Active Directory. | Несколько таблиц, включая [идентитинфо](advanced-hunting-identityinfo-table.md), [идентитилогоневентс](advanced-hunting-identitylogonevents-table.md)и [идентитикуеревентс](advanced-hunting-identityqueryevents-table.md)  | - [Установка защитника Майкрософт для датчика удостоверений](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Включение соответствующих событий Windows](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Статьи по теме
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
