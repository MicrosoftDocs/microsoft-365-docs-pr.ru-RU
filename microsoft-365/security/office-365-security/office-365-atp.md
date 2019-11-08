---
title: Office 365 Advanced Threat Protection
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 10/03/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection включает безопасные вложения, безопасные ссылки, расширенные антифишинговые средства, инструменты создания отчетов и возможности аналитики угроз.
ms.openlocfilehash: dbfff642563117a479db1ac36e76700cca71dd75
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032204"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

> [!IMPORTANT]
> Эта статья предназначена для бизнес-клиентов, у которых есть [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Если вы используете Outlook.com, Office 365 для дома или Office 365 персональный и ищете сведения о функции "Безопасные ссылки" в Outlook, см. статью [Улучшенная безопасность Outlook.com](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="overview"></a>Общие сведения

Office 365 Advanced Threat Protection (ATP) защищает вашу организацию от угроз, которые могут представлять электронные сообщения, ссылки (URL-адреса) и средства совместной работы. ATP включает:

- [Политики защиты от угроз](#configure-atp-policies). Определите политики защиты от угроз, чтобы задать необходимый уровень защиты для организации. 

- [Отчеты](#view-atp-reports). Просматривайте отчеты в режиме реального времени, чтобы отслеживать производительность ATP в организации. 

- [Анализ угроз и реагирование на них](#use-threat-investigation-and-response-capabilities). Используйте передовые инструменты для анализа, изучения, моделирования и предотвращения угроз. 

- [Автоматизированный анализ угроз и реагирование на них](#save-time-with-automated-investigation-and-response). Экономьте время и усилия при анализе и устранении угроз.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP (план 1) и Office 365 ATP (план 2)

ATP входит в Office 365 E5. При этом ATP (план 1) и ATP (план 2) доступны как дополнение к некоторым подпискам. Дополнительные сведения см. в разделе [Доступность функций в планах ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="configure-atp-policies"></a>Настройка политик ATP

Office 365 ATP предоставляет множество средств настройки соответствующего уровня защиты для организации. 

Группе специалистов по безопасности в организации необходимо определить политики для каждого средства ATP в Центре безопасности и соответствия требованиям Office 365. Чтобы получить доступ к параметрам политики, перейдите в раздел **Управление угрозами** > **Политика**. Дополнительные сведения см. в статье [Защита от угроз](protect-against-threats.md).

От политик, определенных для организации, зависят поведение и уровень защиты, связанные с предопределенными угрозами. Параметры политик чрезвычайно гибкие. Например, группа специалистов по безопасности в вашей организации может детально настраивать защиту от угроз на уровне пользователя, организации, получателя и домена. Важно регулярно пересматривать политики, потому что новые угрозы и проблемы возникают ежедневно.  

- [Безопасные вложения ATP](atp-safe-attachments.md). Защита системы обмена сообщениями от атак нулевого дня, которая обеспечивается благодаря проверке вложений в электронные сообщения на наличие вредоносного содержимого. Эта политика предусматривает маршрутизацию всех сообщений и вложений, не имеющих сигнатуры вируса или вредоносной программы, в особую среду, а затем использование методов машинного обучения и техник анализа для обнаружения угроз. Если подозрительные действия не обнаружены, сообщение пересылается в почтовый ящик. Дополнительные сведения см. в статье [Настройка политик безопасных вложений ATP в Office 365](set-up-atp-safe-attachments-policies.md).

- [Безопасные ссылки ATP](atp-safe-links.md). Проверка URL-адресов в момент выбора ссылки (например, в электронных сообщениях и файлах Office). Защита будет действовать и в среде обмена сообщениями, и в среде Office. Ссылки сканируются при каждой попытке перехода. Безопасные ссылки остаются доступными, а вредоносные динамически блокируются. Дополнительные сведения см. в статье [Настройка политик безопасных ссылок ATP в Office 365](https://docs.microsoft.com/office365/securitycompliance/set-up-atp-safe-links-policies). 

- [ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md). Защита организации при совместной работе пользователей и предоставлении доступа к файлам, которая обеспечивается благодаря определению и блокировке вредоносных файлов на сайтах групп и в библиотеках документов. Дополнительные сведения см. в статье [Включение Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md). 

- [Защита от фишинга ATP](atp-anti-phishing.md). Обнаружение попыток олицетворения пользователей и личных доменов. Применение модели машинного обучения и улучшенных алгоритмов обнаружения олицетворения для предотвращения фишинговых атак. Дополнительные сведения см. в статье [Настройка защиты от фишинга, в том числе соответствующих политик, с помощью Office 365 ATP](set-up-anti-phishing-policies.md).

## <a name="view-atp-reports"></a>Просмотр отчетов ATP

В Office 365 ATP входит расширенная [панель мониторинга для отчетов](view-reports-for-atp.md), позволяющая отслеживать производительность ATP. Доступ к ней можно получить в разделе **Отчеты > Панель мониторинга** в Центре безопасности и соответствия требованиям. 

Отчеты обновляются в режиме реального времени, обеспечивая вас новейшей аналитикой. Кроме того, эти отчеты содержат рекомендации и оповещения о приближающихся угрозах. Стандартные отчеты включают в себя: 

- [отчет обозревателя угроз (или обнаружение в режиме реального времени)](threat-explorer.md);

- [отчет о состоянии защиты от угроз](view-reports-for-atp.md#threat-protection-status-report);

- [отчет о типах файлов ATP](view-reports-for-atp.md#atp-file-types-report);

- [отчет о действиях с сообщениями в ATP](view-reports-for-atp.md#atp-message-disposition-report);

- другое. 

## <a name="use-threat-investigation-and-response-capabilities"></a>Использование возможностей анализа угроз и реагирования на них

Office 365 ATP (план 2) включает лучшие [средства анализа угроз и реагирования на них](office-365-ti.md), позволяющие группе специалистов по безопасности в организации прогнозировать, изучать и предотвращать атаки злоумышленников. 

- [Трекеры угроз](threat-trackers.md) предоставляют новейшую аналитику касательно преобладающих проблем, связанных с кибербезопасностью. Например, можно просматривать сведения о новейших вредоносных программах и принимать контрмеры, прежде чем они станут реальной угрозой для организации. К числу доступных трекеров относятся [трекеры, заслуживающие внимания](threat-trackers.md#noteworthy-trackers), [трекеры тенденций](threat-trackers.md#trending-trackers), [Отслеживаемые запросы](threat-trackers.md#tracked-queries) и [Сохраненные запросы](threat-trackers.md#saved-queries).

- [Отчет обозревателя угроз (или обнаружение в режиме реального времени)](threat-explorer.md) — это отчет, получаемый в режиме реального времени, с помощью которого можно определить и проанализировать последние угрозы. Он еще зовется просто обозревателем. В обозревателе можно настроить отображение данных для определенных периодов.

- [Эмулятор атак](attack-simulator.md) позволяет запускать реалистичные сценарии атак в организации для определения уязвимостей. Доступны имитации актуальных типов атак, в том числе [атаки отображаемого имени (целевого фишинга)](attack-simulator.md#display-name-spear-phishing-attack), [атаки путем распыления пароля](attack-simulator.md#password-spray-attack), [атаки методом подбора пароля](attack-simulator.md#brute-force-password-attack).
    
## <a name="save-time-with-automated-investigation-and-response"></a>Экономия времени благодаря автоматизированному анализу угроз и реагированию на них

(**НОВИНКА!**) При анализе потенциальных кибератак время играет ключевую роль. Чем раньше вы сможете выявить и устранить угрозы, тем лучше для организации. Перечисленные ниже подписки теперь включают [автоматизированный анализ угроз и реагирование на них (AIR)](automated-investigation-response-office.md). (Если у вас еще нет этих возможностей, вы скоро получите их при наличии одной из этих подписок.)

AIR Office 365 входит в состав следующих подписок:

- Microsoft 365 E5
- Безопасность Microsoft 365 E5
- Office 365 E5
- Office 365 Advanced Threat Protection (план 2)

AIR включает сборники схем безопасности, которые можно запускать автоматически (например, при активации оповещения) или вручную (например, с помощью представления в обозревателе). AIR экономит время и усилия группы специалистов по безопасности, помогая эффективно устранять угрозы. Дополнительные сведения см. в статье [Автоматизированный анализ угроз и реагирование на них (AIR) в Office 365](automated-investigation-response-office.md).

## <a name="permissions-required-to-use-atp-features"></a>Разрешения, необходимые для использования возможностей ATP

Чтобы получить доступ к возможностям ATP в Центре безопасности и соответствия требованиям, вам нужна соответствующая роль. В таблице приведено несколько примеров.

|Роль или группа ролей  |Дополнительные ресурсы  |
|---------|---------|
|Глобальный администратор Office 365 |[Роли администраторов в Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Администратор безопасности |[Разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Управление организациями в Exchange Online |[Разрешения в Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>и<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

Дополнительные сведения см. в указанных ниже статьях.

- [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md) 

- [Предоставление пользователям доступа к Центру безопасности и соответствия требованиям](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a>Приобретение Office 365 ATP

Office 365 ATP (план 2) включен в Office 365 корпоративный E5, Office 365 для образования A5 и Microsoft 365 бизнес. Если ваша подписка не включает Office 365 ATP, ATP (план 1) и ATP (план 2) можно приобрести в дополнение к определенным подпискам. Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.

- Список подписок, в которые входят планы ATP, см. в разделе [Доступность Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability).

- Список возможностей, включенных в планы 1 и 2, см. в разделе [Доступность функций в планах Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Чтобы сравнить планы и приобрести Office 365 ATP, см. раздел [Выберите подходящее решение Office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content).

## <a name="new-features-in-office-365-atp"></a>Новые возможности Office 365 ATP

В Office 365 ATP постоянно добавляются новые возможности. Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.

- На странице [Стратегия развития Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) приведен список новых возможностей разработки и развертывания.

- Страница [Описание службы Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) содержит информацию о возможностях и доступности в рамках планов ATP.
