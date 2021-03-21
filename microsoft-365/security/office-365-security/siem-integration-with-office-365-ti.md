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
description: Интеграция siEM-сервера организации с Microsoft Defender для Office 365 и связанными с ними событиями угрозы в API управления деятельностью Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 86a716499a25af2a2907d9c502d31474b27ef7bc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916602"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Интеграция SIEM с Microsoft Defender для Office 365

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Если ваша организация использует сервер управления данными безопасности и событиями (SIEM), вы можете интегрировать Microsoft Defender для Office 365 с сервером SIEM. Эту интеграцию можно настроить с помощью API управления деятельностью [Office 365.](/office/office-365-management-api/office-365-management-activity-api-reference)

Интеграция SIEM позволяет просматривать сведения, например вредоносные программы или фишинг, обнаруженные Microsoft Defender для Office 365, в отчетах на сервере SIEM.

- Пример интеграции SIEM с Microsoft Defender для Office 365 см. в блоге Tech Community: Повышение эффективности soc с [помощью Defender для Office 365 и API управления O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

- Дополнительные сведения об API управления Office 365 см. в обзоре API управления [Office 365.](/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>Работа интеграции SIEM

API управления действиями Office 365 извлекает сведения о действиях пользователя, администратора, системы и политик и событиях из журналов действий Microsoft 365 и Azure Active Directory вашей организации. Если в вашей организации есть Microsoft Defender для Office 365 Plan 1 или 2 или Office 365 E5, можно использовать схему [Microsoft Defender для Office 365.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)

Недавно в API управления Office 365 были добавлены события из возможностей автоматического расследования и реагирования в [Microsoft Defender для Office 365 Plan 2.](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) Помимо добавления данных о основных данных расследования, таких как ID, имя и состояние, API также содержит сведения высокого уровня о следственных действиях и сущностях.

SiEM-сервер или другая аналогичная система опове-вает данные о рабочей нагрузке **audit.general** для доступа к событиям обнаружения. Дополнительные дополнительные ссылки см. в [руб. Начало работы с API управления Office 365.](/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType; Type: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

В следующей таблице суммируют значения **AuditLogRecordType,** которые актуальны для событий Microsoft Defender для Office 365:

|Значение|Имя элемента|Описание|
|---|---|---|
|28|ThreatIntelligence|События фишинга и вредоносных программ из Exchange Online Protection и Microsoft Defender для Office 365.|
|41|ThreatIntelligenceUrl|Время блокировки безопасных ссылок и блокировка переопределения событий из Microsoft Defender для Office 365.|
|47|ThreatIntelligenceAtpContent|События фишинга и вредоносных программ для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams из Microsoft Defender для Office 365.|
|64|AirInvestigation|Автоматические события расследования и реагирования, такие как сведения о расследовании и соответствующие артефакты, из Microsoft Defender для Office 365 Plan 2.|
|

> [!IMPORTANT]
> Вы должны быть глобальным администратором или иметь роль администратора безопасности, назначенную Центру & безопасности, чтобы настроить интеграцию SIEM с Microsoft Defender для Office 365.
>
> Ведение журнала аудита должно быть включено для среды Microsoft 365. Чтобы получить помощь в этом, см. в справке о включите поиск [журнала аудита включите или отключите.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>См. также

[Анализ угроз и реагирование на них в Office 365](office-365-ti.md)

[Автоматическое расследование и ответ (AIR) в Office 365](automated-investigation-response-office.md)