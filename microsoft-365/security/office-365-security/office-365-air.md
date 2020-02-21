---
title: Автоматическое исследование и ответ на Office 365
keywords: ВОЗДУШный, Аутоир, ATP, автоматизированный, исследование, ответ, исправление, угрозы, усовершенствованный, угроза, защита
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Приступите к работе с автоматизированным исследованием и возможностями реагирования в Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: d777ca0a61655c8df16d62c72691195bdec330a9
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175783"
---
# <a name="office-365-automated-investigation-and-response"></a>Автоматическое исследование и ответ на Office 365

[Office 365 Advanced Threat protection](office-365-atp.md) План 2 включает мощные возможности автоматического исследования и реагирования (AIR), которые могут сэкономить время и усилия группы по обеспечению безопасности. При инициации определенных оповещений запускается один или несколько "Playbooks" безопасности, а также запускается процесс автоматического исследования. Это позволяет команде системы безопасности сосредоточиться на задачах с высоким приоритетом, не теряя при этом уведомления о триггерах. 

На высоком уровне поток воздуха работает следующим образом:

|Шаг  |Что происходит  |
|---------|---------|
|1,1     |Оповещение инициируется событием Office, а [стратегия безопасности](automated-investigation-response-office.md#security-playbooks) — автоматическим исследованием выбранных оповещений. <br/><br/>Кроме того, аналитика безопасности может [инициировать автоматическое исследование](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) при использовании [обозревателя угроз](threat-explorer.md).        |
|2     |При запуске автоматизированного расследования он собирает дополнительные сведения об электронной почте и сущностях, связанных с этими сообщениями, файлами, URL-адресами и получателями.  Область расследования может увеличиться, так как запускаются новые связанные оповещения.         |
|4     |Во время и после автоматического исследования можно просмотреть [подробные сведения и результаты](air-view-investigation-results.md) . Результаты включают [Рекомендуемые действия](air-remediation-actions.md) , которые можно предпринять для ответа и устранения обнаруженных угроз. Кроме того, доступен [Журнал стратегия](air-view-investigation-results.md#playbook-log) , отслеживающий все действия расследования.<br/><br/>Если в организации используется настраиваемое решение для создания отчетов или стороннее решение, вы можете [использовать API действий управления Office 365](air-custom-reporting.md) для просмотра сведений об автоматическом расследовании и угрозах.         |
|SP4     |Команда по обеспечению безопасности просматривает [результаты расследования и рекомендации](air-view-investigation-results.md)и [утверждает действия по исправлению](air-remediation-actions.md#approve-or-reject-pending-actions). В Office 365 никакие действия не выполняются автоматически. Действия по исправлению принимаются только при утверждении группой безопасности Организации.         |

Во время и после автоматического исследования группа безопасности может выполнить следующие действия:

- [Просмотр сведений о предупреждении, связанных с исследованием](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Просмотр подробных сведений о результатах расследования](air-view-investigation-results.md#view-details-of-an-investigation)
- [Просмотр и утверждение действий в результате расследования](air-remediation-actions.md#approve-or-reject-pending-actions)

Чтобы узнать больше, посмотрите, [как воздух работает](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).