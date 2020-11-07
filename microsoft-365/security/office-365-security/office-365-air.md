---
title: Автоматическое исследование и ответ в защитнике Майкрософт для Office 365
keywords: ВОЗДУШный, Аутоир, ATP, автоматизированный, исследование, ответ, исправление, угрозы, усовершенствованный, угроза, защита
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/05/2020
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
ms.openlocfilehash: 5a7995e0aeba0f29efb1a085a04a299b1e709b1f
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941467"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Автоматическое исследование и реагирование (AIR) в защитнике Майкрософт для Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Защитник Майкрософт для Office 365](office-365-atp.md) включает мощные возможности автоматического исследования и реагирования (AIR), которые могут сэкономить время и усилия группы по обеспечению безопасности. По мере инициирования оповещений группа действий по обеспечению безопасности может просматривать и отвечать на них, а также определять приоритеты и отвечать на них. Поддержание появления входящих оповещений может быть затруднительной. Автоматизация некоторых из этих задач может помочь. 

Воздушный поток позволяет группе управления безопасностью работать эффективнее и эффективно. Возможности воздуха включают автоматизированные процессы расследования в ответ на известные угрозы, существующие сегодня. Соответствующие действия по исправлению ожидают утверждения, позволяя группе управления операциями безопасности эффективно реагировать на обнаруженные угрозы. С помощью воздуха Группа управления операциями безопасности может сосредоточиться на задачах с более высоким приоритетом без потери сведений о важных оповещениях, которые запускаются.

В этой статье описываются:
- [Общий поток воздуха](#the-overall-flow-of-air);
- [Как получить воздух](#how-to-get-air); с 
- [Необходимые разрешения](#required-permissions-to-use-air-capabilities) для настройки или использования возможностей AIR. 

Кроме того, в этой статье приведены [дальнейшие действия](#next-steps)и ресурсы для получения дополнительных сведений.

## <a name="the-overall-flow-of-air"></a>Общий поток воздуха

Инициируется оповещение, а стратегия безопасности начинает автоматическое исследование, что приводит к результатам и рекомендуемым действиям. Вот общий поток воздуха, пошаговые действия:

1. Автоматическое исследование инициируется одним из следующих способов:

   - [Оповещение инициируется](#which-alert-policies-trigger-automated-investigations) подозрительным сообщением электронной почты (например, сообщением, вложением, URL-адресом или скомпрометированной учетной записью пользователя). Создается инцидент, и начинается автоматическое исследование. 

     --- или ---
   
   - Аналитика безопасности [начинает автоматическое исследование](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) при использовании [обозревателя угроз](threat-explorer.md).

2. При запуске автоматизированного расследования он собирает дополнительные данные о рассматриваемой электронной почте и сущностях, связанных с этим сообщением. К таким объектам могут относиться файлы, URL-адреса и получатели.  Область расследования может увеличиваться по мере инициации новых и связанных оповещений.

3. Во время и после автоматического исследования можно просмотреть [подробные сведения и результаты](air-view-investigation-results.md) . Результаты включают [Рекомендуемые действия](air-remediation-actions.md) , которые могут быть предприняты для ответа на все обнаруженные угрозы и их исправления. Кроме того, доступен [Журнал стратегия](air-view-investigation-results.md#playbook-log) , отслеживающий все действия расследования.


4. Команда по обеспечению безопасности просматривает [результаты расследования и рекомендации](air-view-investigation-results.md), а [также утверждает или отвергает действия по исправлению](air-review-approve-pending-completed-actions.md). 

5. Как только ожидающие действия по исправлению утверждены (или отклоняются), автоматическое исследование завершается.

> [!IMPORTANT]
> В защитнике Майкрософт для Office 365 действия по исправлению не выполняются автоматически. Действия по устранению угроз и их последствий предпринимаются только после их утверждения группой безопасности вашей организации. 
>
> Возможности AIR сохраняют время работы группы по обеспечению безопасности, определяя действия по исправлению и предоставляя сведения, необходимые для принятия обоснованного решения.

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

Microsoft 365 предоставляет множество встроенных политик оповещений, которые помогают определить разрешения администратора Exchange, опасные действия, потенциальные внешние и внутренние угрозы, а также риски управления сведениями. Некоторые [политики оповещений по умолчанию](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) могут инициировать автоматическое расследование. В следующей таблице описаны оповещения, которые инициируют автоматическое расследование, их серьезность в центре безопасности Microsoft 365 и способ их создания:


|Акций  |Severity |Способ создания оповещения  |
|---------|---------|--------|
|Обнаружен потенциально вредоносный URL-адрес.     |**Высокий** |Это оповещение создается в следующих случаях:<br/> — Пользователь, защищенный с помощью [безопасных ссылок](atp-safe-links.md) в вашей организации, щелкает вредоносную ссылку <br/>-Изменения вредоносности для URL-адресов определяются защитником Майкрософт для Office 365 <br/>— Пользователи переопределяют страницы предупреждений о безопасных ссылках (в зависимости от [политики безопасных ссылок](set-up-atp-safe-links-policies.md)в организации).<br/><br/> Дополнительные сведения о событиях, инициирующих это оповещение, приведены в разделе [Настройка политик безопасных ссылок](set-up-atp-safe-links-policies.md).         |
|Сообщение электронной почты от пользователя в качестве вредоносной программы или фишинга |**Справоч**    |Это оповещение создается, когда пользователи в организации сообщают сообщения в виде фишинговых сообщений с помощью [надстройки Report Message](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in). |
|Сообщения электронной почты, содержащие вредоносные программы, удаляются после доставки |**Справоч**     |Это оповещение создается, когда сообщения электронной почты, содержащие вредоносные программы, доставляются в почтовые ящики в Организации. При возникновении этого события Майкрософт удаляет зараженные сообщения из почтовых ящиков Exchange Online, используя [Автоматическое удаление с нулевым временем](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge).   |
|Сообщения электронной почты, содержащие URL-адреса фишинга, удаляются после доставки     |**Справоч**        |Это оповещение создается, когда сообщения, содержащие фишинг, доставляются в почтовые ящики в Организации. При возникновении этого события Майкрософт удаляет зараженные сообщения из почтовых ящиков Exchange Online, используя [Автоматическое удаление с нулевым временем](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge).  |
|Обнаружены подозрительные шаблоны отправки электронной почты     |**Средний**         |Это оповещение создается, когда кто-то из вашей организации отправил подозрительные сообщения электронной почты и подвержено неограниченной отправке электронной почты. Это раннее предупреждение о поведении, которое может означать, что учетная запись скомпрометирована, но недостаточно серьезна для ограничения пользователя.<br/><br/> Несмотря на то что это редкие, оповещение, создаваемое этой политикой, может быть аномалией. Тем не менее, рекомендуется [проверить, скомпрометирована ли учетная запись пользователя](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).  |
|Пользователю запрещено отправлять электронную почту.    |**Высокий** |Это оповещение создается, если кто-то из вашей организации запретил отправку исходящей почты. Обычно это происходит при [компрометации учетной записи электронной почты](responding-to-a-compromised-email-account.md).<br/><br/>Дополнительные сведения об ограниченных пользователях приведены [в статье Удаление заблокированных пользователей с портала ограниченных пользователей в Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).    |

> [!TIP]
> Чтобы узнать больше о политиках оповещений или изменить параметры по умолчанию, ознакомьтесь со статьей [политики оповещений в центре соответствия требованиям Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="required-permissions-to-use-air-capabilities"></a>Необходимые разрешения для использования возможностей AIR

Разрешения предоставляются с помощью определенных ролей, например, описанных в следующей таблице. 

|Задача |Требуются роли |
|:--|:--|
|Настройка функций AIR |Одна из следующих ролей: <br/>— Глобальный администратор<br/>— Администратор безопасности <br/>Эти роли можно назначить в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) или в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Запуск автоматического исследования <br/><br/>--- или ---<br/><br/>Утверждение или отклонение рекомендуемых действий|Одна из следующих ролей, назначенных в [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) или в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>— Глобальный администратор <br/>— Администратор безопасности<br/>— Средство чтения безопасности <br/>--- и ---<br/>-Поиск и очистка (эта роль назначается только в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Возможно, вам потребуется создать новую группу ролей и добавить роль "Поиск и очистка" в новую группу ролей.) |

## <a name="required-licenses"></a>Необходимые лицензии

[Защитник Майкрософт для Office 365 Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#microsoft-defender-for-office-365-plan-1-and-plan-2) лицензии должен быть назначен следующим:
- Администраторы безопасности (в том числе глобальные администраторы)
- Группа управления операциями безопасности Организации (включая средства чтения и очистки с ролью **поиска и очистки** ).
- Пользователи


## <a name="next-steps"></a>Дальнейшие действия

- [Просмотр подробных сведений и результатов автоматизированного исследования](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Просмотр и утверждение ожидающих действий](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="see-also"></a>См. также

- [Автоматическое исследование и исправление в защитнике Майкрософт для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Автоматическое исследование и ответ в защитнике Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
