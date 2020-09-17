---
title: Office 365 Advanced Threat Protection
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
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
ms.custom:
- seo-marvel-apr2020
description: Office 365 Advanced Threat Protection включает безопасные вложения, безопасные ссылки, расширенные антифишинговые средства, инструменты создания отчетов и возможности аналитики угроз.
ms.openlocfilehash: 184ab53059a73de534d9a67a45fc41b20a73f13f
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949699"
---
# <a name="office-365-advanced-threat-protection-atp"></a>Office 365 Advanced Threat Protection (ATP)

> [!IMPORTANT]
> Эта статья предназначена для бизнес-клиентов, у которых есть [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Если вы используете Outlook.com, Microsoft 365 для семьи или Microsoft 365 персональный и ищете сведения о функции "Безопасные ссылки"или "Безопасные вложения" в Outlook, см. статью [Расширенные возможности безопасности Outlook.com для подписчиков Microsoft 365](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Office 365 Advanced Threat Protection (ATP) защищает вашу организацию от угроз, которые могут представлять электронные сообщения, ссылки (URL-адреса) и средства совместной работы. ATP включает:

- **[Политики защиты от угроз.](#configure-atp-policies)** Определите политики защиты от угроз, чтобы задать необходимый уровень защиты для организации.

- **[Отчеты.](#view-office-365-atp-reports)** Просматривайте отчеты в режиме реального времени, чтобы отслеживать производительность ATP в организации.

- **[Анализ угроз и реагирование на них.](#use-threat-investigation-and-response-capabilities)** Используйте передовые инструменты для анализа, изучения, моделирования и предотвращения угроз.

- **[Автоматизированный анализ угроз и реагирование на них.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)** Экономьте время и усилия при анализе и устранении угроз.

## <a name="getting-started"></a>Начало работы

Если вы не знакомы с Office 365 Advanced Threat Protection или изучаете эту службу на *практике*, вам может помочь разбиение исходной настройки ATP на блоки, изучение и проверка отчетов с использованием этой статьи в качестве справочника. Ниже приведены логические блоки исходной настройки:

- Настраивайте все элементы с добавлением слова "*защита*" к имени.
    - защита от вредоносных программ
    - защита от фишинга
    - защита от нежелательной почты
- Настраивайте все элементы с добавлением слова "*безопасный*" к имени.
    - безопасные ссылки
    - безопасные вложения
- Защищайте рабочие нагрузки (например, SharePoint Online, OneDrive и Teams) 
- Защищайте с использованием автоматической очистки

Для изучения на практике [щелкните эту ссылку](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide&preserve-view=true). 

> [!NOTE]
> ATP предлагается в Планах двух разных типов. Вы используете **План 1**, если у вас есть функция "Обнаружение в режиме реального времени", и **План 2**, если у вас есть обозреватель угроз. Ваш План влияет на средства, которые вы видите, поэтому в процессе обучения вы должны знать, какой у вас План.

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP (план 1) и Office 365 ATP (план 2)

В таблице ниже приведена сводка о содержании каждого плана.

****

|Office 365 ATP, План 1|Office 365 ATP, План 2|
|---|---|
|<br/>Конфигурация, защита и возможности обнаружения: <ul><li>[Безопасные вложения](atp-safe-attachments.md)</li><li>[Безопасные ссылки](atp-safe-links.md)</li><li>[ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Защита от фишинга ATP](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[Обнаружение в режиме реального времени](threat-explorer.md)</li></ul>|Возможности Office 365 ATP (план 1)<br/>--- плюс ---<br/>Автоматизация, исследование, исправления и возможности образования.</li><li>[Трекеры угроз](threat-trackers.md)</li><li>[Обозреватель угроз](threat-explorer.md)</li><li>[Автоматизированный анализ угроз и реагирование на них](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[Эмулятор атак](attack-simulator.md)</li></ul>|
|

- Пакет Office 365 ATP с Планом 2 входит в состав Office 365 E5, Office 365 A5, Безопасность Microsoft 365 E5 и Microsoft 365 E5.

- Office 365 ATP с Планом 1 входит в состав Microsoft 365 бизнес премиум.

- При этом Office 365 ATP с Планом 1 и Office 365 ATP с Планом 2 доступны как дополнение к некоторым подпискам. Дополнительные сведения см. в разделе [Доступность функций в планах ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Функция [безопасных документов](safe-docs.md) доступна только пользователям с лицензией Microsoft 365 E5 или Безопасность Microsoft 365 E5 (не предусмотренные планами Office 365 ATP).

- Если текущая подписка не включает в себя Office 365 ATP, [то обратитесь в отдел продаж для запуска пробной версии](https://go.microsoft.com/fwlink/p/?LinkId=518644) и посмотрите, как ATP может работать в вашей организации.

## <a name="configure-atp-policies"></a>Настройка политик ATP

С помощью Office 365 ATP команда безопасности вашей организации может настраивать защиту, определяя политики в Центре безопасности и соответствия требованиям (выберите [https://protection.office.com](https://protection.office.com) > **Управление угрозами** > **Политики**).

> [!TIP]
> Краткий список политик для определения см. в статье [Защита от угроз](protect-against-threats.md).

## <a name="advanced-threat-protection-policies"></a>Политики расширенной защиты от угроз

От политик, определенных для организации, зависят поведение и уровень защиты, связанные с предопределенными угрозами. Параметры политик чрезвычайно гибкие. Например, группа специалистов по безопасности в вашей организации может детально настраивать защиту от угроз на уровне пользователя, организации, получателя и домена. Важно регулярно пересматривать политики, потому что новые угрозы и проблемы возникают ежедневно.

- **[Безопасные вложения ATP](atp-safe-attachments.md)**. Защита системы обмена сообщениями от угроз нулевого дня путем проверки вложений в сообщениях электронной почты на наличие вредоносного содержимого. Эта политика предусматривает маршрутизацию всех сообщений и вложений, не имеющих сигнатуры вируса или вредоносной программы, в особую среду, а затем использование методов машинного обучения и техник анализа для обнаружения угроз. Если подозрительные действия не обнаружены, сообщение пересылается в почтовый ящик. Дополнительные сведения см. в статье [Настройка политик безопасных вложений ATP в Office 365](set-up-atp-safe-attachments-policies.md).

- **[Безопасные ссылки ATP](atp-safe-links.md)**. Проверка URL-адресов (например, в сообщениях электронной почты и файлах Office) в момент щелчка по ним. Защита будет действовать и в среде обмена сообщениями, и в среде Office. Ссылки сканируются при каждой попытке перехода. Безопасные ссылки остаются доступными, а вредоносные динамически блокируются. Дополнительные сведения см. в статье [Настройка политик безопасных ссылок ATP в Office 365](set-up-atp-safe-links-policies.md).

- **[ATP для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md)**. Защита организации при совместной работе пользователей и совместном использовании файлов путем определения и блокировки вредоносных файлов на сайтах групп и в библиотеках документов. Дополнительные сведения см. в статье [Включение Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

- **[Защита от фишинга ATP](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)**. Обнаружение попыток олицетворения пользователей и внутренних или личных доменов. Применение модели машинного обучения и улучшенных алгоритмов обнаружения олицетворения для предотвращения фишинговых атак. Дополнительные сведения см. в статье [Настройка политик защиты от фишинга ATP в Office 365](configure-atp-anti-phishing-policies.md).

## <a name="view-office-365-atp-reports"></a>Просмотр отчетов Office 365 ATP

В Office 365 ATP входит расширенная [панель мониторинга для отчетов](view-reports-for-atp.md), позволяющая отслеживать производительность ATP. Она доступна в разделе **Отчеты** > **Панель мониторинга** в Центре безопасности и соответствия требованиям.

Отчеты обновляются в режиме реального времени, обеспечивая вас новейшей аналитикой. Кроме того, эти отчеты содержат рекомендации и оповещения о приближающихся угрозах. Стандартные отчеты включают в себя:

- [отчет обозревателя угроз (или обнаружение в режиме реального времени)](threat-explorer.md);

- [отчет о состоянии защиты от угроз](view-reports-for-atp.md#threat-protection-status-report);

- [отчет о типах файлов расширенной защиты от угроз](view-reports-for-atp.md#advanced-threat-protection-file-types-report);

- [отчет о ликвидации сообщений расширенной защиты от угроз](view-reports-for-atp.md#advanced-threat-protection-message-disposition-report)

- и некоторые другие.

## <a name="use-threat-investigation-and-response-capabilities"></a>Использование возможностей анализа угроз и реагирования на них

Office 365 ATP (план 2) включает лучшие [средства анализа угроз и реагирования на них](office-365-ti.md), позволяющие группе специалистов по безопасности в организации прогнозировать, изучать и предотвращать атаки злоумышленников.

- **[Трекеры угроз](threat-trackers.md)** предоставляют новейшую аналитику касательно преобладающих проблем кибербезопасности. Например, можно просматривать сведения о новейших вредоносных программах и принимать контрмеры, прежде чем они станут реальной угрозой для организации. К числу доступных трекеров относятся [трекеры, заслуживающие внимания](threat-trackers.md#noteworthy-trackers), [трекеры тенденций](threat-trackers.md#trending-trackers), [Отслеживаемые запросы](threat-trackers.md#tracked-queries) и [Сохраненные запросы](threat-trackers.md#saved-queries).

- **[Отчет обозревателя угроз, также именуемого обозревателем (или обнаружение в режиме реального времени)](threat-explorer.md)**, — это отчет, получаемый в режиме реального времени, с помощью которого можно определить и проанализировать последние угрозы. В обозревателе можно настроить отображение данных для определенных периодов.

- **[Эмулятор атак](attack-simulator.md)** позволяет запускать реалистичные сценарии атак в организации для определения уязвимостей. Доступны имитации актуальных типов атак, в том числе целевой фишинг с целью сбора учетных данных, атаки с вложением, атаки путем распыления пароля, атаки методом подбора пароля.

## <a name="save-time-with-automated-investigation-and-response"></a>Экономия времени благодаря автоматизированному анализу угроз и реагированию на них

(**НОВИНКА!**) При анализе потенциальных кибератак время играет ключевую роль. Чем раньше вы сможете выявить и устранить угрозы, тем лучше для организации. Возможности [Автоматизированного анализа угроз и реагирование на них](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) включают сборники схем безопасности, которые можно запускать автоматически (например, при срабатывании оповещения) или вручную (например, с помощью представления в обозревателе). AIR экономит время и усилия группы специалистов по безопасности, помогая эффективно устранять угрозы. Дополнительные сведения см. в статье [AIR в Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).

## <a name="permissions-required-to-use-atp-features"></a>Разрешения, необходимые для использования возможностей ATP

Чтобы получить доступ к возможностям ATP в Центре безопасности и соответствия требованиям, вам нужна соответствующая роль. В таблице приведено несколько примеров.

|Роль или группа ролей|Дополнительные ресурсы|
|---|---|
|глобальный администратор (назначается Azure Active Directory или Центром безопасности и соответствия требованиям)|[О ролях администратора Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Администратор безопасности (назначается Azure Active Directory или Центром безопасности и соответствия требованиям)|[Разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md)|
|Управление организациями в Exchange Online (назначается Exchange Online)|[Разрешения в Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|Роль "Search and Purge" (поиск и очистка) (назначается только Центром безопасности и соответствия требованиям)|[Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md)|

Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

## <a name="get-office-365-atp"></a>Приобретение Office 365 ATP

Служба Office 365 ATP включена в определенные подписки, такие как Microsoft 365 E5, Office 365 E5, Office 365 A5 и Microsoft 365 бизнес премиум. Если ваша подписка не включает Office 365 ATP, ATP (план 1) и ATP (план 2) можно приобрести в дополнение к определенным подпискам. Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.

- Раздел [Доступность Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) со списком подписок, включающих планы ATP.

- Раздел [Доступность функций в планах Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) со списком возможностей, включенных в планы 1 и 2.

- Раздел [Выберите подходящее решение Office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) для сравнения планов и приобретения Office 365 ATP.

- [Начало использования бесплатной пробной версии](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a>Новые возможности Office 365 ATP

В Office 365 ATP постоянно добавляются новые возможности. Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.

- На странице [Дорожная карта Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) приведен список новых возможностей разработки и развертывания.

- Статья [Описание службы Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) содержит информацию о возможностях и доступности в рамках планов ATP.

## <a name="see-also"></a>См. также

- [Защита от угроз (Майкрософт)](../mtp/microsoft-threat-protection.md)

- [Автоматизированный анализ угроз и реагирование на них в Защите от угроз (Майкрософт)](../mtp/mtp-autoir.md)
