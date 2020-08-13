---
title: Интеграция SIEM с расширенной защитой угроз
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: Интеграция сервера SIEM в Организации с Office 365 Advanced Threat Protection и связанными событиями угроз в API управления действиями Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3ed2efd2b59397853623ffcec93e8011793ab43
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656603"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>Интеграция SIEM с расширенной защитой угроз

Если в организации используется сервер управления инцидентами и событиями SIEM, вы можете интегрировать Office 365 Advanced Threat protection с сервером SIEM. Интеграция SIEM позволяет просматривать сведения, такие как вредоносные программы и фишинг, обнаруженные в Office 365 Advanced Protection, в отчетах сервера SIEM. Для настройки интеграции с SIEM используется [API управления действиями Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).

API управления действиями Office 365 получает сведения о действиях пользователя, администратора, системы, а также о событиях и политиках в журналах активности организации Microsoft 365 для бизнеса и Azure Active Directory. [Схема Advanced Threat Protection в office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) работает с Advanced Threat Protection, поэтому если в 365 организации используется Advanced Threat protection (план 1) или план 2 или Office 365, вы по-прежнему можете использовать тот же API для интеграции сервера SIEM.

В ходе последних обновлений мы также добавили события из автоматизированного исследования и возможности реагирования в Office 365 ATP (план 2) в API действий управления Office 365. Помимо включения данных об основных сведениях расследования, таких как ID, Name и Status, он также содержит сведения высокого уровня о действиях и сущностях расследования.

Сервер SIEM или другая подобная система должны опрашивать события **аудита. Общая** Рабочая нагрузка для доступа к событиям обнаружения. Чтобы узнать больше, ознакомьтесь [со статьей начало работы с API управления Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). Кроме того, для событий Office 365 ATP важны следующие значения **аудитлогрекордтипе** :

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType; Type: Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

****

|Значение|Имя элемента|Описание|
|---|---|---|
|8|ThreatIntelligence|События фишинга и вредоносных программ из Exchange Online Protection и Office 365 Advanced Threat Protection.|
|41|ThreatIntelligenceUrl|События "безопасные ссылки" ATP "время блокировки" и "переопределение блока" из Office 365 Advanced Threat protection.|
|47|ThreatIntelligenceAtpContent|События фишинга и вредоносных программ для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams из Office 365 Advanced Threat protection.|
|64|AirInvestigation|Автоматизированные события расследования и реагирования, такие как сведения об исследовании и необходимые компоненты из Office 365 Advanced Threat Protection Plan 2.|
|

> [!IMPORTANT]
> Для настройки интеграции SIEM с Office 365 Advanced Threat Protection необходимо быть глобальным администратором или иметь роль администратора безопасности, назначенную для центра безопасности & соответствия требованиям.<br/>Для вашей среды Microsoft 365 должна быть включена функция ведения журнала аудита. Чтобы получить помощь по этому, ознакомьтесь со статьей [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Связанные статьи

[Анализ угроз и реагирование на них в Office 365](office-365-ti.md)

[Автоматическое исследование и реагирование (AIR) в Office 365](automated-investigation-response-office.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Интеллектуальные отчеты и аналитика в центре безопасности и &amp; соответствия требованиям](reports-and-insights-in-security-and-compliance.md)

[Разрешения в центре безопасности и &amp; соответствия требованиям](permissions-in-the-security-and-compliance-center.md)
