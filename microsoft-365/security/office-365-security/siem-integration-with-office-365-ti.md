---
title: Интеграция SIEM с Microsoft Defender для Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Интеграция сервера SIEM организации с Microsoft Defender для Office 365 и связанными с ними событиями угроз в API управления действиями Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f637750a31b5034d2ee1110ab0070fa6abcda49b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290397"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Интеграция SIEM с Microsoft Defender для Office 365

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Если в вашей организации используется сервер SIEM, вы можете интегрировать Microsoft Defender для Office 365 с сервером SIEM. Вы можете настроить эту интеграцию с помощью API управления действиями [Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

Интеграция SIEM позволяет просматривать сведения, такие как вредоносные программы или фишинг, обнаруженные Microsoft Defender для Office 365, в отчетах сервера SIEM.

- Пример интеграции SIEM с Microsoft Defender для Office 365 см. в блоге Tech Community: улучшение эффективности SOC с Помощью [Защитника для Office 365 и API управления O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

- Дополнительные сведения об API управления Office 365 см. в обзоре [API управления Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>Как работает интеграция SIEM

API управления действиями Office 365 извлекает сведения о действиях и событиях пользователей, администраторов, систем и политик из журналов действий Microsoft 365 и Azure Active Directory вашей организации. Если в вашей организации есть Microsoft Defender для Office 365 (план 1 или 2) или Office 365 E5, вы можете использовать схему [Microsoft Defender для Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)

Недавно в API действий управления Office 365 были добавлены события из автоматизированного исследования и реагирования в Microsoft Defender для [Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) (план 2). Помимо данных об основных сведениях исследования, таких как ИД, имя и состояние, API также содержит высокоуровневую информацию о действиях и сущностях расследования.

Сервер SIEM или другая аналогичная система оповещую нагрузку **audit.general** для доступа к событиям обнаружения. Дополнительные информации см. в руководстве ["Начало работы с API управления Office 365".](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType; Type: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

В следующей таблице сводятся значения **AuditLogRecordType,** релевантные для событий Microsoft Defender в Office 365:

|Значение|Имя элемента|Описание|
|---|---|---|
|28|ThreatIntelligence|События фишинга и вредоносных программ из Exchange Online Protection и Microsoft Defender для Office 365.|
|41|ThreatIntelligenceUrl|События переопределения времени блокировки и блокировки безопасных ссылок из Microsoft Defender для Office 365.|
|47|ThreatIntelligenceAtpContent|События фишинга и вредоносных программ для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams из Microsoft Defender для Office 365.|
|64|AirInvestigation|События автоматического исследования и реагирования, такие как сведения об исследованиях и соответствующие артефакты, из Microsoft Defender для Office 365 (план 2).|
|

> [!IMPORTANT]
> Чтобы настроить интеграцию SIEM с Microsoft Defender для Office 365, необходимо быть глобальным администратором или иметь роль администратора безопасности, назначенную Центру безопасности & соответствия требованиям.
>
> Ведение журнала аудита должно быть включено для вашей среды Microsoft 365. Чтобы получить помощь по этой теме, см. "Включите или отключите поиск [в журнале аудита".](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>См. также

[Анализ угроз и реагирование на них в Office 365](office-365-ti.md)

[Автоматическое исследование и реагирование на них (AIR) в Office 365](automated-investigation-response-office.md)

