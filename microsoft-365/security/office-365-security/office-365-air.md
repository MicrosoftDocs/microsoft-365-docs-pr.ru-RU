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
ms.openlocfilehash: 7bfa07880a302f77769ee15e9108db21dac2519c
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228574"
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

## <a name="how-to-get-air"></a>Как получить воздух

AIR Office 365 входит в состав следующих подписок:

- Microsoft 365 E5
- Office 365 E5
- Защита от угроз (Майкрософт)
- Office 365 Advanced Threat Protection (план 2)

Если у вас нет ни одной из этих подписок, [запустите бесплатную пробную версию](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US).

Для получения дополнительных сведений о доступности функций посетите страницу [доступность функций в планах расширенной защиты от угроз (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="required-permissions-to-use-air-capabilities"></a>Необходимые разрешения для использования возможностей AIR

Разрешения предоставляются с помощью определенных ролей, например, описанных в следующей таблице. 

|Задача |Требуются роли |
|--|--|
|Настройка функций AIR |Одна из следующих ролей: <br/>- **Глобальный администратор**<br/>- **Администратор безопасности** <br/>Эти роли можно назначить в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) или в [центре безопасности & безопасности Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Утверждение или отклонение рекомендуемых действий|Одна из следующих ролей, назначенных в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) или в [центре безопасности & безопасности Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>- **Глобальный администратор** <br/>- **Администратор безопасности**<br/>- **Средство чтения безопасности** <br/>--- и ---<br/>- **Поиск и очистка** (эта роль назначается только в [центре безопасности Office 365 & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Возможно, вам потребуется создать новую группу ролей и добавить роль "Поиск и очистка" в новую группу ролей.)

## <a name="related-articles"></a>Статьи по теме

- [Автоматизированный анализ угроз и реакция на угрозы в службе защиты от угроз (Майкрософт)](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

- [Автоматическое исследование и устранение неполадок в Advanced Threat Protection в защитнике Майкрософт](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)