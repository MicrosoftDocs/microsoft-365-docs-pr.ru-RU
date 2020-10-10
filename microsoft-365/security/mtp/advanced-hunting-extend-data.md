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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 39beff1ea5e983af53cdb954783c11f13569a022
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413954"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Расширение расширенного контроля за пресроком действия с помощью правильных параметров

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Область применения:**
- Защита от угроз (Майкрософт)

[Расширенные](advanced-hunting-overview.md) функции поискового зависят от данных, поступающих из различных источников, в том числе устройств, рабочих областей Office 365, Azure AD и Azure ATP. Чтобы получить наиболее полные данные, убедитесь, что у вас есть правильные параметры в соответствующих источниках данных.

## <a name="advanced-security-auditing-on-windows-devices"></a>Расширенный аудит безопасности для устройств с Windows
Включите эти расширенные параметры аудита, чтобы получить данные о действиях на устройствах, включая Управление локальными учетными записями, локальным управлением группами безопасности и созданием служб.

| Data | Описание | Таблица схемы | Способ настройки |
| --- | --- | --- | --- |
| Управление учетными записями | События, перехваченные как различные `ActionType` значения, указывающие создание локальной учетной записи, удаление и другие действия, связанные с учетными записями | [DeviceEvents](advanced-hunting-deviceevents-table.md) | — Развертывание расширенной политики аудита безопасности: [Аудит управления учетными записями пользователей](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Сведения о политиках расширенной проверки безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Управление группами безопасности | События, перехваченные как различные `ActionType` значения, указывающие на создание локальной группы безопасности и другие локальные действия по управлению группами | [DeviceEvents](advanced-hunting-deviceevents-table.md) | — Развертывание расширенной политики аудита безопасности: [Аудит управления группами безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Сведения о политиках расширенной проверки безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Установка службы | События, записанные со `ActionType` значением `ServiceInstalled` , указывающие на то, что служба была создана | [DeviceEvents](advanced-hunting-deviceevents-table.md) | — Развертывание расширенной политики аудита безопасности: [Аудит расширения системы безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Сведения о политиках расширенной проверки безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="azure-atp-sensor-on-the-domain-controller"></a>Датчик Azure ATP на контроллере домена
Если вы используете Active Directory локально, вам необходимо установить на контроллере домена датчик Azure ATP для получения данных для Azure ATP. Если вы установили и правильно настроили, эти данные также помещаются на веб-каналы с помощью Azure ATP и предоставляют более целостное изображение идентификационных данных и событий в сети. Эти данные также расширяют возможности Azure ATP для создания соответствующих оповещений, которые также покрываются при расширенном поиске. 

| Data | Описание | Таблица схемы | Способ настройки |
| --- | --- | --- | --- |
| Контроллер домена. | Данные из локальной службы Active Directory, отправленные в Azure ATP, дополнительные сведения об удостоверении, такие как сведения об учетных записях, действиях входа и запросах Active Directory | Несколько таблиц, включая [идентитинфо](advanced-hunting-identityinfo-table.md), [идентитилогоневентс](advanced-hunting-identitylogonevents-table.md)и [идентитикуеревентс](advanced-hunting-identityqueryevents-table.md)  | - [Установка датчика Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Включение соответствующих событий Windows](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Связанные статьи
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
