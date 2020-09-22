---
title: Автоматическое исследование и ответ (AIR) — Начало работы
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
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: adee64461d06b46f467682835a493a7eebe89aef
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202655"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a>Начало работы с автоматизированным исследованием и откликом (AIR) в Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365 Advanced Threat protection](office-365-atp.md) (Office 365 ATP), план 2 включает мощные возможности автоматического исследования и реагирования (AIR), которые могут сэкономить время и усилия группы по обеспечению безопасности. По мере инициирования оповещений группа действий по обеспечению безопасности может просматривать и отвечать на них, а также определять приоритеты и отвечать на них. Поддержание появления входящих оповещений может быть затруднительной. Автоматизация некоторых из них может помочь. В среде AIR группа управления операциями безопасности может сосредоточиться на задачах с более высоким приоритетом, не теряя уведомления о триггерах.

В этой статье описаны следующие проблемы:
- [Общий поток](#the-overall-flow-of-air) воздуха;
- [Как получить воздух](#how-to-get-air); с 
- [Необходимые разрешения](#required-permissions-to-use-air-capabilities) для настройки или использования возможностей AIR. 

## <a name="the-overall-flow-of-air"></a>Общий поток воздуха

На высоком уровне инициируется оповещение, а стратегия безопасности запускает автоматическое исследование, что приводит к результатам и рекомендациям. Вот общий поток воздуха, пошаговые действия:

1. Автоматическое исследование инициируется одним из следующих способов:

   - [Оповещение](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) инициируется событием Office, которое создает инцидент. В зависимости от типа инцидента, [стратегия безопасности](automated-investigation-response-office.md#security-playbooks) начинает автоматическое исследование. 

     --- или ---
   
   - Аналитика безопасности [начинает автоматическое исследование](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) при использовании [обозревателя угроз](threat-explorer.md).

2. При запуске автоматизированного расследования он собирает дополнительные данные о рассматриваемой электронной почте и сущностях, связанных с этим сообщением. К таким объектам могут относиться файлы, URL-адреса и получатели.  Область расследования может увеличиваться по мере инициации новых и связанных оповещений.

3. Во время и после автоматического исследования можно просмотреть [подробные сведения и результаты](air-view-investigation-results.md) . Результаты включают [Рекомендуемые действия](air-remediation-actions.md) , которые можно предпринять для ответа и устранения обнаруженных угроз. Кроме того, доступен [Журнал стратегия](air-view-investigation-results.md#playbook-log) , отслеживающий все действия расследования.

    Если в организации используется настраиваемое решение для создания отчетов или стороннее решение, вы можете [использовать API действий управления Office 365](air-custom-reporting.md) для просмотра сведений об автоматическом расследовании и угрозах.

4. Команда по обеспечению безопасности просматривает [результаты расследования и рекомендации](air-view-investigation-results.md), а [также утверждает или отвергает действия по исправлению](air-review-approve-pending-completed-actions.md). 

    Как только ожидающие действия по исправлению утверждены (или отклоняются), автоматическое исследование завершается.

> [!NOTE]
> В Office 365 ATP никакие действия по исправлению не выполняются автоматически. Действия по устранению угроз и их последствий предпринимаются только после их утверждения группой безопасности вашей организации. 

Во время и после автоматического исследования группа безопасности может выполнить следующие действия:

- [Просмотр сведений о предупреждении, связанных с исследованием](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Просмотр подробных сведений о результатах расследования](air-view-investigation-results.md#view-details-of-an-investigation)

- [Просмотр и утверждение действий в результате расследования](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Более подробную информацию можно узнать в статье [работа воздуха](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Как получить воздух

Возможности AIR в Office 365 включены в [план 2 для office 365 Advanced Threat protection (план 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)). Тем не менее, [политики Office 365 ATP должны быть настроены](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) , чтобы воздух работал должным образом. Кроме того, необходимо проверить и, возможно, настроить [политики оповещений](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)в Организации. 

Microsoft 365 предоставляет множество встроенных политик оповещений, которые помогают определить разрешения администратора Exchange, опасные действия, потенциальные внешние и внутренние угрозы, а также риски управления сведениями. Некоторые [политики оповещений по умолчанию](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) могут инициировать автоматическое расследование. К ним относятся:

- Обнаружен потенциально вредоносный URL-адрес.

- Сообщение электронной почты отображается как "фишинг"

- Сообщения электронной почты, содержащие вредоносные программы, удаляются после доставки

- Сообщения электронной почты, содержащие URL-адреса фишинга, удаляются после доставки

- Обнаружены подозрительные шаблоны отправки электронной почты

- Пользователю запрещено отправлять электронную почту.

[Узнайте больше о оповещениях и воздухах](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="required-permissions-to-use-air-capabilities"></a>Необходимые разрешения для использования возможностей AIR

Разрешения предоставляются с помощью определенных ролей, например, описанных в следующей таблице. 

|Задача |Требуются роли |
|--|--|
|Настройка функций AIR |Одна из следующих ролей: <br/>— Глобальный администратор<br/>— Администратор безопасности <br/>Эти роли можно назначить в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) или в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Утверждение или отклонение рекомендуемых действий|Одна из следующих ролей, назначенных в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) или в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>— Глобальный администратор <br/>— Администратор безопасности<br/>— Средство чтения безопасности <br/>--- и ---<br/>-Поиск и очистка (эта роль назначается только в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Возможно, вам потребуется создать новую группу ролей и добавить роль "Поиск и очистка" в новую группу ролей.)

Лицензии на [Office 365 ATP 2 (план 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) ) должны быть назначены следующим:
- Администраторы безопасности (в том числе глобальные администраторы)
- Группа управления операциями безопасности Организации (включая средства чтения и очистки с ролью поиска и очистки).
- Пользователи

Кроме того, необходимо определить и применить [политики Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) , чтобы обеспечить защиту.

## <a name="next-steps"></a>Дальнейшие действия

- [Просмотр подробных сведений и результатов автоматизированного исследования](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Просмотр и утверждение ожидающих действий](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Статьи по теме

- [Автоматическое исследование и устранение неполадок в Advanced Threat Protection в защитнике Майкрософт](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Автоматизированный анализ угроз и реакция на угрозы в службе защиты от угроз (Майкрософт)](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
