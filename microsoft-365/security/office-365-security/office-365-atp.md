---
title: Office 365 Advanced Threat Protection
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/03/2019
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
ms.openlocfilehash: 65f123e77d5b38163dfe4e8971426d8a1135b571
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866711"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

> [!IMPORTANT]
> Эта статья предназначена для бизнес-клиентов, у которых есть [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Если вы используете Outlook.com, Office 365 для дома или Office 365 персональный и ищете сведения о функции "Безопасные ссылки" в Outlook, см. статью [Улучшенная безопасность Outlook.com](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="overview"></a>Общие сведения

Office 365 Advanced Threat Protection (ATP) защищает вашу организацию от угроз, которые могут представлять электронные сообщения, ссылки (URL-адреса) и средства совместной работы. ATP включает:

- [Политики защиты от угроз](#configure-atp-policies). Определите политики защиты от угроз, чтобы задать необходимый уровень защиты для организации. 

- [Отчеты](#view-office-365-atp-reports). Просматривайте отчеты в режиме реального времени, чтобы отслеживать производительность ATP в организации. 

- [Анализ угроз и реагирование на них](#use-threat-investigation-and-response-capabilities). Используйте передовые инструменты для анализа, изучения, моделирования и предотвращения угроз. 

- [Автоматизированное реагирование на инциденты](#save-time-with-automated-incident-response). Экономьте время и усилия при анализе и устранении угроз.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP (план 1) и Office 365 ATP (план 2)

ATP входит в Office 365 E5. При этом Office 365 ATP (план 1) и Office 365 ATP (план 2) доступны как дополнение к некоторым подпискам. Дополнительные сведения см. в разделе [Доступность функций в планах ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

> [!TIP]
> Если у вас нет Office 365 ATP, [попробуйте бесплатную пробную версию](https://go.microsoft.com/fwlink/p/?LinkID=698279).


## <a name="configure-atp-policies"></a>Настройка политик ATP

С помощью Office 365 ATP команда безопасности вашей организации может настраивать защиту, определяя политики в Центре безопасности и соответствия требованиям Office 365 (выберите [https://protection.office.com](https://protection.office.com) > **Управление угрозами** > **Политики**). 

> [!TIP]
> Краткий список политик для определения см. в статье [Защита от угроз](protect-against-threats.md).

От политик, определенных для организации, зависят поведение и уровень защиты, связанные с предопределенными угрозами. Параметры политик чрезвычайно гибкие. Например, группа специалистов по безопасности в вашей организации может детально настраивать защиту от угроз на уровне пользователя, организации, получателя и домена. Важно регулярно пересматривать политики, потому что новые угрозы и проблемы возникают ежедневно.  

- **[Безопасные вложения ATP](atp-safe-attachments.md)**. Защита системы обмена сообщениями от угроз нулевого дня путем проверки вложений в сообщениях электронной почты на наличие вредоносного содержимого. Эта политика предусматривает маршрутизацию всех сообщений и вложений, не имеющих сигнатуры вируса или вредоносной программы, в особую среду, а затем использование методов машинного обучения и техник анализа для обнаружения угроз. Если подозрительные действия не обнаружены, сообщение пересылается в почтовый ящик. Дополнительные сведения см. в статье [Настройка политик безопасных вложений ATP в Office 365](set-up-atp-safe-attachments-policies.md).

- **[Безопасные ссылки ATP](atp-safe-links.md)**. Проверка URL-адресов (например, в сообщениях электронной почты и файлах Office) в момент щелчка по ним. Защита будет действовать и в среде обмена сообщениями, и в среде Office. Ссылки сканируются при каждой попытке перехода. Безопасные ссылки остаются доступными, а вредоносные динамически блокируются. Дополнительные сведения см. в статье [Настройка политик безопасных ссылок ATP в Office 365](https://docs.microsoft.com/office365/securitycompliance/set-up-atp-safe-links-policies). 

- **[ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md)**. Защита организации при совместной работе пользователей и совместном использовании файлов путем определения и блокировки вредоносных файлов на сайтах групп и в библиотеках документов. Дополнительные сведения см. в статье [Включение Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md). 

- **[Защита от фишинга ATP](atp-anti-phishing.md)**. Обнаружение попыток олицетворения пользователей и личных доменов. Применение модели машинного обучения и улучшенных алгоритмов обнаружения олицетворения для предотвращения фишинговых атак. Дополнительные сведения см. в статье [Настройка защиты от фишинга, в том числе соответствующих политик, с помощью Office 365 ATP](set-up-anti-phishing-policies.md).

## <a name="view-office-365-atp-reports"></a>Просмотр отчетов Office 365 ATP

В Office 365 ATP входит расширенная [панель мониторинга для отчетов](view-reports-for-atp.md), позволяющая отслеживать производительность ATP. Она доступна в разделе **Отчеты** > **Панель мониторинга** в Центре безопасности и соответствия требованиям. 

Отчеты обновляются в режиме реального времени, обеспечивая вас новейшей аналитикой. Кроме того, эти отчеты содержат рекомендации и оповещения о приближающихся угрозах. Стандартные отчеты включают в себя: 

- [отчет обозревателя угроз (или обнаружение в режиме реального времени)](threat-explorer.md);

- [отчет о состоянии защиты от угроз](view-reports-for-atp.md#threat-protection-status-report);

- [отчет о типах файлов ATP](view-reports-for-atp.md#atp-file-types-report);

- [отчет о действиях с сообщениями в ATP](view-reports-for-atp.md#atp-message-disposition-report);

- и некоторые другие. 

## <a name="use-threat-investigation-and-response-capabilities"></a>Использование возможностей анализа угроз и реагирования на них

Office 365 ATP (план 2) включает лучшие [средства анализа угроз и реагирования на них](office-365-ti.md), позволяющие группе специалистов по безопасности в организации прогнозировать, изучать и предотвращать атаки злоумышленников. 

- **[Трекеры угроз](threat-trackers.md)** предоставляют новейшую аналитику касательно преобладающих проблем кибербезопасности. Например, можно просматривать сведения о новейших вредоносных программах и принимать контрмеры, прежде чем они станут реальной угрозой для организации. К числу доступных трекеров относятся [трекеры, заслуживающие внимания](threat-trackers.md#noteworthy-trackers), [трекеры тенденций](threat-trackers.md#trending-trackers), [Отслеживаемые запросы](threat-trackers.md#tracked-queries) и [Сохраненные запросы](threat-trackers.md#saved-queries).

- **[Отчет обозревателя угроз, также именуемого обозревателем (или обнаружение в режиме реального времени)](threat-explorer.md)**, — это отчет, получаемый в режиме реального времени, с помощью которого можно определить и проанализировать последние угрозы. В обозревателе можно настроить отображение данных для определенных периодов.

- **[Эмулятор атак](attack-simulator.md)** позволяет запускать реалистичные сценарии атак в организации для определения уязвимостей. Доступны имитации актуальных типов атак, в том числе [атаки отображаемого имени (целевого фишинга)](attack-simulator.md#display-name-spear-phishing-attack), [атаки путем распыления пароля](attack-simulator.md#password-spray-attack), [атаки методом подбора пароля](attack-simulator.md#brute-force-password-attack).
    
## <a name="save-time-with-automated-incident-response"></a>Экономия времени с помощью автоматизированного реагирования на инциденты

(**НОВИНКА!**) При анализе потенциальных кибератак время играет ключевую роль. Чем раньше вы сможете выявить и устранить угрозы, тем лучше для организации. Функции [автоматизированного реагирования на инциденты](automated-investigation-response-office.md) (AIR) включают сборники схем безопасности, которые можно запускать автоматически (например, при активации оповещения) или вручную (например, с помощью представления в обозревателе). AIR экономит время и усилия группы специалистов по безопасности, помогая эффективно устранять угрозы. Дополнительные сведения см. в статье [AIR в Office 365](automated-investigation-response-office.md).

## <a name="permissions-required-to-use-atp-features"></a>Разрешения, необходимые для использования возможностей ATP

Чтобы получить доступ к возможностям ATP в Центре безопасности и соответствия требованиям, вам нужна соответствующая роль. В таблице приведено несколько примеров.

|Роль или группа ролей  |Дополнительные ресурсы  |
|---------|---------|
|Глобальный администратор Office 365 (назначается Azure Active Directory или Центром безопасности и соответствия требованиям Office 365) |[Роли администраторов в Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Администратор безопасности (назначается Azure Active Directory или Центром безопасности и соответствия требованиям Office 365) |[Разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md)|
|Управление организациями в Exchange Online (назначается Exchange Online)|[Разрешения в Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|Search and Purge (назначается только Центром безопасности и соответствия требованиям Office 365) |[Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md) |

Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

## <a name="get-office-365-atp"></a>Приобретение Office 365 ATP

Служба Office 365 ATP включена в определенные подписки, такие как Microsoft 365 E5, Office 365 E5, Office 365 A5 и Microsoft 365 бизнес. Если ваша подписка не включает Office 365 ATP, ATP (план 1) и ATP (план 2) можно приобрести в дополнение к определенным подпискам. Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.

- Раздел [Доступность Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) со списком подписок, включающих планы ATP.

- Раздел [Доступность функций в планах Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) со списком возможностей, включенных в планы 1 и 2.

- Раздел [Выберите подходящее решение Office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) для сравнения планов и приобретения Office 365 ATP.

- [Начало использования бесплатной пробной версии](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Новые возможности Office 365 ATP

В Office 365 ATP постоянно добавляются новые возможности. Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.

- На странице [Дорожная карта Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) приведен список новых возможностей разработки и развертывания.

- Статья [Описание службы Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) содержит информацию о возможностях и доступности в рамках планов ATP.
