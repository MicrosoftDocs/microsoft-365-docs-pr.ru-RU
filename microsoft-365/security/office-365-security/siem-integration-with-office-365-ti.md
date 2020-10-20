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
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Интеграция сервера SIEM в Организации с Office 365 Advanced Threat Protection и связанными событиями угроз в API управления действиями Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c4c92fc45546d3d8022a3925baa9c10f9bd0090b
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600557"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>Интеграция SIEM с расширенной защитой угроз

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Если в Организации используются сведения о безопасности и управление событиями (SIEM), можно интегрировать Office 365 Advanced Threat protection (Office 365 ATP) с сервером SIEM. Эту интеграцию можно настроить с помощью [API управления действиями Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

Интеграция SIEM позволяет просматривать сведения, такие как вредоносные и фишингы, обнаруженные в Office 365 ATP, в отчетах сервера SIEM. 

- Пример интеграции SIEM с Office 365 ATP можно найти в [блоге технического сообщества: улучшите эффективность SoC с помощью office 365 ATP и API управления O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Дополнительные сведения об API управления Office 365 можно найти в статье [Обзор API управления office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Как работает интеграция SIEM

API управления действиями Office 365 извлекает сведения о действиях пользователя, администратора, системы, а также о событиях и политиках из журналов активности Microsoft 365 и Azure Active Directory. Если в вашей организации используется Office 365 ATP, план 1 или 2, или Office 365 в ~, вы можете использовать [схему office 365 ATP](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).  

Недавно в API действий управления Office 365 были добавлены события автоматизированного исследования и возможности реагирования в [office 365 ATP 2 (план 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) ). В дополнение к включению данных об основных сведениях расследования, таких как ID, Name и Status, API также содержит подробные сведения о действиях и сущностях расследования.

Сервер SIEM или другая подобная система опрашивает рабочую нагрузку **Audit. General** для доступа к событиям обнаружения. Чтобы узнать больше, ознакомьтесь [со статьей начало работы с API управления Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType; Type: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

В следующей таблице приведены значения **аудитлогрекордтипе** , относящиеся к событиям ATP для Office 365:

|Значение|Имя элемента|Описание|
|---|---|---|
|8|ThreatIntelligence|События фишинга и вредоносных программ из Exchange Online Protection и Office 365 ATP.|
|41|ThreatIntelligenceUrl|События времени блокировки и переопределения блоков для безопасных ссылок из Office 365 ATP.|
|47|ThreatIntelligenceAtpContent|События фишинга и вредоносных программ для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams из Office 365 ATP.|
|64|AirInvestigation|Автоматическое исследование и события ответа, такие как сведения об исследовании и необходимые артефакты, из Office 365 ATP (план 2).|
|

> [!IMPORTANT]
> Для настройки интеграции SIEM с Office 365 Advanced Threat Protection необходимо быть глобальным администратором или иметь роль администратора безопасности, назначенную для центра безопасности & соответствия требованиям.<br/>Для вашей среды Microsoft 365 должна быть включена функция ведения журнала аудита. Чтобы получить помощь по этому, ознакомьтесь со статьей [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>См. также

[Анализ угроз и реагирование на них в Office 365](office-365-ti.md)

[Автоматическое исследование и реагирование (AIR) в Office 365](automated-investigation-response-office.md)

