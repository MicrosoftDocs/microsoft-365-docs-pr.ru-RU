---
title: Интеграция SIEM с защитником Майкрософт для Office 365
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
description: Интеграция сервера SIEM в Организации с защитником Майкрософт для Office 365 и связанными событиями угроз в API управления действиями Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 185e6e816cfff4131d7b5af11c4e3ea9cf94b338
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843580"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Интеграция SIEM с защитником Майкрософт для Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Если в Организации используются сведения о безопасности и управление событиями (SIEM), можно интегрировать защитник Майкрософт для Office 365 с сервером SIEM. Эту интеграцию можно настроить с помощью [API управления действиями Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

Интеграция SIEM позволяет просматривать сведения, такие как вредоносные программы и фишинг, обнаруженные защитником Майкрософт для Office 365, в отчетах сервера SIEM. 

- Чтобы просмотреть пример интеграции SIEM с защитником Майкрософт для Office 365, посетите [блог технического сообщества: улучшите эффективность SoC с помощью защитника для Office 365 и API управления O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Дополнительные сведения об API управления Office 365 можно найти в статье [Обзор API управления office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Как работает интеграция SIEM

API управления действиями Office 365 извлекает сведения о действиях пользователя, администратора, системы, а также о событиях и политиках из журналов активности Microsoft 365 и Azure Active Directory. Если в вашей организации используется защитник Майкрософт для Office 365 (план 1 или 2) или Office 365 в ~, вы можете использовать [схему Microsoft Defender для office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).  

Недавно в API действий по управлению Office 365 были добавлены события автоматизированного исследования и возможности реагирования в [защитнике Майкрософт для office 365 (план 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) ). В дополнение к включению данных об основных сведениях расследования, таких как ID, Name и Status, API также содержит подробные сведения о действиях и сущностях расследования.

Сервер SIEM или другая подобная система опрашивает рабочую нагрузку **Audit. General** для доступа к событиям обнаружения. Чтобы узнать больше, ознакомьтесь [со статьей начало работы с API управления Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType; Type: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

В следующей таблице приведены значения **аудитлогрекордтипе** , относящиеся к защитнику Майкрософт для событий Office 365:

|Значение|Имя элемента|Описание|
|---|---|---|
|8|ThreatIntelligence|События фишинга и вредоносных программ из Exchange Online Protection и защитник Майкрософт для Office 365.|
|41|ThreatIntelligenceUrl|События времени блокировки и переопределения блокировки для безопасных ссылок в защитнике Майкрософт для Office 365.|
|47|ThreatIntelligenceAtpContent|События фишинга и вредоносных программ для файлов в SharePoint Online, OneDrive для бизнеса и Microsoft Teams от защитника Майкрософт для Office 365.|
|64|AirInvestigation|Автоматическое исследование и события ответа, такие как сведения об исследовании и необходимые артефакты, от защитника Майкрософт для Office 365 (план 2).|
|

> [!IMPORTANT]
> Для настройки интеграции SIEM с защитником Майкрософт для Office 365 необходимо быть глобальным администратором или иметь роль администратора безопасности, назначенную для центра безопасности & соответствия требованиям.<br/>Для вашей среды Microsoft 365 должна быть включена функция ведения журнала аудита. Чтобы получить помощь по этому, ознакомьтесь со статьей [Включение и отключение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>См. также

[Анализ угроз и реагирование на них в Office 365](office-365-ti.md)

[Автоматическое исследование и реагирование (AIR) в Office 365](automated-investigation-response-office.md)

