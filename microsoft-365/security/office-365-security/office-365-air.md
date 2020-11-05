---
title: Начало работы с автоматическим исследованием и ответом в защитнике Майкрософт для Office 365
keywords: ВОЗДУШный, Аутоир, ATP, автоматизированный, исследование, ответ, исправление, угрозы, усовершенствованный, угроза, защита
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/04/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Приступите к работе с автоматизированным исследованием и возможностями реагирования в защитнике Майкрософт для Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 7e9b786a9d00a34f5e2e88a8481e82fa8425a501
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925608"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Начало работы с автоматизированным исследованием и откликом (AIR) в защитнике Майкрософт для Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Защитник Майкрософт для Office 365](office-365-atp.md) включает мощные возможности автоматического исследования и реагирования (AIR), которые могут сэкономить время и усилия группы по обеспечению безопасности. По мере инициирования оповещений группа действий по обеспечению безопасности может просматривать и отвечать на них, а также определять приоритеты и отвечать на них. Поддержание появления входящих оповещений может быть затруднительной. Автоматизация некоторых из этих задач может помочь. С помощью воздуха Группа управления операциями безопасности может сосредоточиться на задачах с более высоким приоритетом без потери сведений о важных оповещениях, которые запускаются.

В этой статье описываются:
- [Общий поток воздуха](#the-overall-flow-of-air);
- [Как получить воздух](#how-to-get-air); с 
- [Необходимые разрешения](#required-permissions-to-use-air-capabilities) для настройки или использования возможностей AIR. 

## <a name="the-overall-flow-of-air"></a>Общий поток воздуха

Инициируется оповещение, а стратегия безопасности начинает автоматическое исследование, что приводит к результатам и рекомендуемым действиям. Вот общий поток воздуха, пошаговые действия:

1. Автоматическое исследование инициируется одним из следующих способов:

   - [Оповещение](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) инициируется подозрительным сообщением электронной почты (например, сообщением, вложением или URL-адресом). Создается инцидент. В зависимости от типа инцидента, запускается [стратегия безопасности](automated-investigation-response-office.md#security-playbooks) , и начинается автоматическое исследование. 

     --- или ---
   
   - Аналитика безопасности [начинает автоматическое исследование](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) при использовании [обозревателя угроз](threat-explorer.md).

2. При запуске автоматизированного расследования он собирает дополнительные данные о рассматриваемой электронной почте и сущностях, связанных с этим сообщением. К таким объектам могут относиться файлы, URL-адреса и получатели.  Область расследования может увеличиваться по мере инициации новых и связанных оповещений.

3. Во время и после автоматического исследования можно просмотреть [подробные сведения и результаты](air-view-investigation-results.md) . Результаты включают [Рекомендуемые действия](air-remediation-actions.md) , которые могут быть предприняты для ответа на все обнаруженные угрозы и их исправления. Кроме того, доступен [Журнал стратегия](air-view-investigation-results.md#playbook-log) , отслеживающий все действия расследования.


4. Команда по обеспечению безопасности просматривает [результаты расследования и рекомендации](air-view-investigation-results.md), а [также утверждает или отвергает действия по исправлению](air-review-approve-pending-completed-actions.md). 

5. Как только ожидающие действия по исправлению утверждены (или отклоняются), автоматическое исследование завершается.

> [!IMPORTANT]
> В защитнике Майкрософт для Office 365 действия по исправлению не выполняются автоматически. Действия по устранению угроз и их последствий предпринимаются только после их утверждения группой безопасности вашей организации. Однако возможности воздуха сохраняют время Teaming Operations, определяя действия по исправлению и предоставляя сведения, необходимые для принятия обоснованного решения.

Во время и после каждого автоматического исследования группа управления действиями может:

- [Просмотр сведений о предупреждении, связанных с исследованием](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Просмотр подробных сведений о результатах расследования](air-view-investigation-results.md#view-details-of-an-investigation)

- [Просмотр и утверждение действий в результате расследования](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Более подробную информацию можно узнать в статье [работа воздуха](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Как получить воздух

Возможности воздуха включены в [защитник Майкрософт для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2), если политики и оповещения настроены. Если вы хотите получить какую бы то ни было помощь, следуйте указаниям в статье [Защита от угроз](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) , чтобы установить или настроить следующие параметры защиты: 

1. [Ведение журнала аудита](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (должно быть включено)

2. [Политики защиты от вредоносных программ](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-1---anti-malware-protection)

3. [Защита от фишинга](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
   
4. [Защита защиты от спама](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection).
   
5. [Безопасные ссылки и безопасные вложения](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).
   
6. [Безопасные вложения для SharePoint, OneDrive и Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).
   
7. [Автоматическая очистка электронной почты с нулевым часовым значением](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop).

Кроме того, обязательно ознакомьтесь со [своими политиками оповещений Организации](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), особенно [политиками по умолчанию в категории "Управление угрозами](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)". 

## <a name="which-alert-policies-trigger-automated-investigations"></a>Какие политики оповещений инициируют автоматическое расследование?

Microsoft 365 предоставляет множество встроенных политик оповещений, которые помогают определить разрешения администратора Exchange, опасные действия, потенциальные внешние и внутренние угрозы, а также риски управления сведениями. Некоторые [политики оповещений по умолчанию](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) могут инициировать автоматическое расследование. К ним относятся:

- Обнаружен потенциально вредоносный URL-адрес.
- Сообщение электронной почты отображается как "фишинг"
- Сообщения электронной почты, содержащие вредоносные программы, удаляются после доставки
- Сообщения электронной почты, содержащие URL-адреса фишинга, удаляются после доставки
- Обнаружены подозрительные шаблоны отправки электронной почты
- Пользователю запрещено отправлять электронную почту.

## <a name="required-permissions-to-use-air-capabilities"></a>Необходимые разрешения для использования возможностей AIR

Разрешения предоставляются с помощью определенных ролей, например, описанных в следующей таблице. 

|Задача |Требуются роли |
|--|--|
|Настройка функций AIR |Одна из следующих ролей: <br/>— Глобальный администратор<br/>— Администратор безопасности <br/>Эти роли можно назначить в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) или в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Утверждение или отклонение рекомендуемых действий|Одна из следующих ролей, назначенных в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) или в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>— Глобальный администратор <br/>— Администратор безопасности<br/>— Средство чтения безопасности <br/>--- и ---<br/>-Поиск и очистка (эта роль назначается только в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Возможно, вам потребуется создать новую группу ролей и добавить роль "Поиск и очистка" в новую группу ролей.)

## <a name="required-licenses"></a>Необходимые лицензии

Лицензии [Microsoft Defender для Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) должны быть назначены следующим продуктам:
- Администраторы безопасности (в том числе глобальные администраторы)
- Группа управления операциями безопасности Организации (включая средства чтения и очистки с ролью поиска и очистки).
- Пользователи


## <a name="next-steps"></a>Дальнейшие действия

- [Просмотр подробных сведений и результатов автоматизированного исследования](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Просмотр и утверждение ожидающих действий](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Статьи по теме

- [Автоматическое исследование и исправление в защитнике Майкрософт для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Автоматическое исследование и ответ в защитнике Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
