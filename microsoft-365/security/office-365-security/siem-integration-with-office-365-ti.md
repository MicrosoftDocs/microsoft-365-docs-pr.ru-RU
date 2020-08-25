---
title: Интеграция SIEM с Advanced Threat Protection
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
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Интеграция сервера SIEM вашей организации с Office 365 Advanced Threat Protection и связанными событиями в API управления действиями Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e9dcf24adfb227d0c454b4f5952c879cea511f7
ms.sourcegitcommit: 37da941919036a714da42eaa039682ccbe0da670
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860693"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>Интеграция SIEM с Advanced Threat Protection

Если ваша организация использует сервер SIEM инцидентов безопасности и событий безопасности, вы можете интегрировать Office 365 Advanced Threat Protection (Office 365 ATP) с сервером SIEM. Эту интеграцию можно настроить с помощью [API управления действиями Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) 

Интеграция SIEM позволяет просматривать сведения, например вредоносное ПО или фишинг, обнаруженный Office 365 ATP, в отчетах сервера SIEM. 

- Пример интеграции SIEM с Office 365 ATP см. в блоге [Tech Community: Улучшение эффективности SOC с помощью Office 365 ATP и API управления Office 365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

- Дополнительные сведения об API управления Office 365 см. в обзоре API управления [Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>Принцип интеграции SIEM

API управления действиями Office 365 получает информацию о действиях и событиях пользователя, администратора, системы и политики из журналов действий Microsoft 365 и Azure Active Directory вашей организации. Если у вашей организации есть План 1, 2 или Office 365 E5, вы можете использовать [схему Office 365 ATP.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)  

Недавно события возможностей автоматизированного анализа угроз и реагирования на них в [Office 365 ATP (план 2) были](office-365-atp.md#office-365-atp-plan-1-and-plan-2) добавлены в API действий управления Office 365. Помимо сведений об основных сведениях об исследовании, таких как идентификатор, имя и состояние, API также содержит высокоуровневые сведения о действиях и объектах анализа.

Сервер SIEM или другая подобная система опросит **участие audit.general** workload, чтобы получить доступ к событиям обнаружения. Дополнительные сведения см. в статье ["Начало работы с API управления Office 365".](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis) 


## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType; Type: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

Значения **свойства AuditLogRecordType,** относящиеся к событиям Office 365 ATP, см. в следующей таблице.

|Значение|Имя элемента|Описание|
|---|---|---|
|28|ThreatIntelligence|События фишинга и вредоносных программ из Exchange Online Protection и Office 365 ATP.|
|41|ThreatIntelligenceUrl|События времени блокировки безопасных ссылок ATP и переопределения блокировки из Office 365 ATP.|
|47|ThreatIntelligenceAtpContent|События фишинга и вредоносных программ для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams из Office 365 ATP.|
|64|AirInvestigation|Автоматизированное исследование событий анализа угроз и реагирование на них, например сведения об исследовании и соответствующие артефакты, из Office 365 ATP (план 2).|
|

> [!IMPORTANT]
> Для настройки интеграции SIEM & с Office 365 Advanced Threat Protection вам необходимо быть глобальным администратором или вам должна быть назначена роль администратора безопасности, назначенная в Центре соответствия требованиям безопасности.<br/>Ведение журнала аудита должно быть включено для вашей среды Microsoft 365. Чтобы получить справку, см. раздел ["Включение и отключение поиска в журнале аудита".](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>См. также

[Анализ угроз и реагирование на них в Office 365](office-365-ti.md)

[Автоматизированный анализ угроз и реагирование на них (AIR) в Office 365](automated-investigation-response-office.md)


