---
title: Microsoft Defender для Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender для Office 365 включает безопасные вложения, безопасные ссылки, расширенные средства защиты от фишинга, инструменты создания отчетов и возможности аналитики угроз.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eab7cdbed592975739fdcfa1089e6f7d2c25d880
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904120"
---
# <a name="microsoft-defender-for-office-365"></a>Microsoft Defender для Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Microsoft Defender для Office 365 (план 1 и план 2)](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Эта статья предназначена для бизнес-клиентов, использующих [Microsoft Defender для Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Если вы используете Outlook.com, Microsoft 365 для семьи или Microsoft 365 персональный и ищете сведения о функции "Безопасные ссылки"или "Безопасные вложения" в Outlook, см. статью [Расширенные возможности безопасности Outlook.com для подписчиков Microsoft 365](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Microsoft Defender для Office 365 защищает организацию от злонамеренных угроз, связанных с сообщениями электронной почты, ссылками (URL-адресами) и средствами для совместной работы. Defender для Office 365 включает:

- **[Политики защиты от угроз.](#configure-microsoft-defender-for-office-365-policies)** Определите политики защиты от угроз, чтобы задать необходимый уровень защиты для организации.

- **[Отчеты.](#view-microsoft-defender-for-office-365-reports)** Просматривайте отчеты в режиме реального времени, чтобы отслеживать производительность Defender для Office 365 в организации.

- **[Анализ угроз и реагирование на них.](#use-threat-investigation-and-response-capabilities)** Используйте передовые инструменты для анализа, изучения, моделирования и предотвращения угроз.

- **[Автоматизированный анализ угроз и реагирование на них.](office-365-air.md)** Экономьте время и усилия при анализе и устранении угроз.

## <a name="interactive-guide-to-microsoft-defender-for-office-365"></a>Интерактивное руководство по Microsoft Defender для Office 365
В этом интерактивном руководстве рассказывается, как защитить вашу организацию с помощью Microsoft Defender для Office 365. Вы узнаете, как Microsoft Defender для Office 365 поможет определить политики защиты, проанализировать угрозы для организации и отреагировать на атаки.

[Ознакомьтесь с интерактивным руководством](https://aka.ms/MSDO-IG)

## <a name="getting-started"></a>Начало работы

Если вы не знакомы с Microsoft Defender для Office 365 или изучаете эту службу на *практике*, вам может помочь разбиение исходной настройки Defender для Office 365 на блоки, изучение и проверка отчетов с использованием этой статьи в качестве справочника. Ниже приведены логические блоки исходной настройки:

- Настраивайте все элементы с добавлением слова "*защита*" к имени.
  - защита от вредоносных программ
  - защита от фишинга
  - защита от нежелательной почты
- Настраивайте все элементы с добавлением слова "*безопасный*" к имени.
  - Безопасные ссылки
  - Безопасные вложения
- Защищайте рабочие нагрузки (например, SharePoint Online, OneDrive и Teams)
- Защищайте с использованием автоматической очистки

Для изучения на практике [щелкните эту ссылку](protect-against-threats.md).

> [!NOTE]
> Microsoft Defender для Office 365 предлагается в планах двух разных типов. Вы используете **План 1**, если у вас есть функция "Обнаружение в режиме реального времени", и **План 2**, если у вас есть обозреватель угроз. Ваш План влияет на средства, которые вы видите, поэтому в процессе обучения вы должны знать, какой у вас План.

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender для Office 365 (план 1 и план 2)

В таблице ниже приведена сводка о содержании каждого плана.

****

|Microsoft Defender для Office 365 (план 1)|Microsoft Defender для Office 365 (план 2)|
|---|---|
|Конфигурация, защита и возможности обнаружения: <ul><li>[Безопасные вложения](safe-attachments.md)</li><li>[Безопасные ссылки](safe-links.md)</li><li>[Безопасные вложения для SharePoint, OneDrive и Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Защита от фишинга в Defender для Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Обнаружение в режиме реального времени](threat-explorer.md)</li></ul>|Возможности Microsoft Defender для Office 365 (план 1) <br>--- плюс ---<br> Автоматизация, исследование, исправления и возможности образования.<ul><li>[Трекеры угроз](threat-trackers.md)</li><li>[Обозреватель угроз](threat-explorer.md)</li><li>[Автоматизированный анализ угроз и реагирование на них](office-365-air.md)</li><li>[Эмулятор атак](attack-simulator.md)</li><li>[Представления кампании](campaigns.md)</li></ul>|
|

- Пакет Microsoft Defender для Office 365 с планом 2 входит в состав Office 365 E5, Office 365 A5, Безопасность Microsoft 365 E5 и Microsoft 365 E5.

- Microsoft Defender для Office 365 с планом 1 входит в состав Microsoft 365 бизнес премиум.

- Microsoft Defender для Office 365 (план 1) и Microsoft Defender для Office 365 (план 2) доступны как дополнение к некоторым подпискам. Дополнительные сведения см. в разделе [Доступность функций в планах Microsoft Defender для Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Функция [безопасных документов](safe-docs.md) доступна только пользователям с лицензией Microsoft 365 E5 или Безопасность Microsoft 365 E5 (не предусмотренные планами Microsoft Defender для Office 365).

- Если текущая подписка не включает в себя Microsoft Defender для Office 365, [обратитесь в отдел продаж для начала использования пробной версии](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) и посмотрите, как Defender для Office 365 может работать в вашей организации.

## <a name="configure-microsoft-defender-for-office-365-policies"></a>Настройка политик Microsoft Defender для Office 365

С помощью Microsoft Defender для Office 365 команда безопасности вашей организации может настраивать защиту, определяя политики в Центре безопасности и соответствия требованиям (выберите <https://protection.office.com> \> **Управление угрозами** \> **Политики**).

Узнайте больше, посмотрев [это](https://www.youtube.com/watch?v=vivvTmWJ_3c) видео. 

> [!TIP]
> Краткий список политик для определения см. в статье [Защита от угроз](protect-against-threats.md).

## <a name="defender-for-office-365-policies"></a>Политики Defender для Office 365

От политик, определенных для организации, зависят поведение и уровень защиты, связанные с предопределенными угрозами. Параметры политик чрезвычайно гибкие. Например, группа специалистов по безопасности в вашей организации может детально настраивать защиту от угроз на уровне пользователя, организации, получателя и домена. Важно регулярно пересматривать политики, потому что новые угрозы и проблемы возникают ежедневно.

- **[Безопасные вложения ATP](safe-attachments.md)**. Защита системы обмена сообщениями от угроз нулевого дня путем проверки вложений в сообщениях электронной почты на наличие вредоносного содержимого. Эта политика предусматривает маршрутизацию всех сообщений и вложений, не имеющих сигнатуры вируса или вредоносной программы, в особую среду, а затем использование методов машинного обучения и техник анализа для обнаружения угроз. Если подозрительные действия не обнаружены, сообщение пересылается в почтовый ящик. Дополнительные сведения см. в статье [Настройка политик безопасных вложений ATP](set-up-safe-attachments-policies.md).

- **[Безопасные ссылки ATP](safe-links.md)**. Проверка URL-адресов (например, в сообщениях электронной почты и файлах Office) в момент щелчка по ним. Защита будет действовать и в среде обмена сообщениями, и в среде Office. Ссылки сканируются при каждой попытке перехода. Безопасные ссылки остаются доступными, а вредоносные динамически блокируются. Дополнительные сведения см. в статье [Настройка политик безопасных ссылок](set-up-safe-links-policies.md).

- **[Безопасные вложения для SharePoint, OneDrive и Microsoft Teams](mdo-for-spo-odb-and-teams.md)**. Защита организации при совместной работе пользователей и совместном использовании файлов путем определения и блокировки вредоносных файлов на сайтах групп и в библиотеках документов. Дополнительные сведения см. в статье [Включение Defender для Office 365 в SharePoint, OneDrive и Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

- **[Защита от фишинга ATP в Defender для Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**. Обнаружение попыток олицетворения пользователей и внутренних или личных доменов. Применение модели машинного обучения и улучшенных алгоритмов обнаружения олицетворения для предотвращения фишинговых атак. Дополнительные сведения см. в статье [Настройка политик защиты от фишинга в Microsoft Defender для Office 365](configure-atp-anti-phishing-policies.md).

## <a name="view-microsoft-defender-for-office-365-reports"></a>Просмотр отчетов Microsoft Defender для Office 365

В Microsoft Defender для Office 365 входит расширенная [панель мониторинга для отчетов](view-reports-for-mdo.md), позволяющая отслеживать производительность Defender для Office 365. Она доступна в разделе **Отчеты** \> **Панель мониторинга** в Центре безопасности и соответствия требованиям.

Отчеты обновляются в режиме реального времени, обеспечивая вас новейшей аналитикой. Кроме того, эти отчеты содержат рекомендации и оповещения о приближающихся угрозах. Стандартные отчеты включают в себя:

- [отчет обозревателя угроз (или обнаружение в режиме реального времени)](threat-explorer.md);

- [отчет о состоянии защиты от угроз](view-reports-for-mdo.md#threat-protection-status-report);

- [отчет о типах файлов Defender для Office 365](view-reports-for-mdo.md#defender-for-office-365-file-types-report);

- [отчет о действиях с сообщениями в Defender для Office 365](view-reports-for-mdo.md#defender-for-office-365-message-disposition-report)

- и некоторые другие.

## <a name="use-threat-investigation-and-response-capabilities"></a>Использование возможностей анализа угроз и реагирования на них

Microsoft Defender для Office 365 (план 2) включает лучшие [средства анализа угроз и реагирования на них](office-365-ti.md), позволяющие группе специалистов по безопасности в организации прогнозировать, изучать и предотвращать атаки злоумышленников.

- **[Трекеры угроз](threat-trackers.md)** предоставляют новейшую аналитику касательно преобладающих проблем кибербезопасности. Например, можно просматривать сведения о новейших вредоносных программах и принимать контрмеры, прежде чем они станут реальной угрозой для организации. К числу доступных трекеров относятся [трекеры, заслуживающие внимания](threat-trackers.md#noteworthy-trackers), [трекеры тенденций](threat-trackers.md#trending-trackers), [Отслеживаемые запросы](threat-trackers.md#tracked-queries) и [Сохраненные запросы](threat-trackers.md#saved-queries).

- **[Отчет обозревателя угроз, также именуемого обозревателем (или обнаружение в режиме реального времени)](threat-explorer.md)**, — это отчет, получаемый в режиме реального времени, с помощью которого можно определить и проанализировать последние угрозы. В обозревателе можно настроить отображение данных для определенных периодов.

- **[Эмулятор атак](attack-simulator.md)** позволяет запускать реалистичные сценарии атак в организации для определения уязвимостей. Доступны имитации актуальных типов атак, в том числе целевой фишинг с целью сбора учетных данных, атаки с вложением, атаки путем распыления пароля, атаки методом подбора пароля.

## <a name="save-time-with-automated-investigation-and-response"></a>Экономия времени благодаря автоматизированному анализу угроз и реагированию на них

(**НОВИНКА!**) При анализе потенциальных кибератак время играет ключевую роль. Чем раньше вы сможете выявить и устранить угрозы, тем лучше для организации. Возможности [Автоматизированного анализа угроз и реагирование на них](office-365-air.md) (AIR) включают сборники схем безопасности, которые можно запускать автоматически (например, при срабатывании оповещения) или вручную (например, с помощью представления в обозревателе). AIR экономит время и усилия группы специалистов по безопасности, помогая эффективно устранять угрозы. Дополнительные сведения см. в статье [AIR в Office 365](office-365-air.md).

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a>Разрешения, необходимые для использования возможностей Microsoft Defender для Office 365

Чтобы получить доступ к возможностям Microsoft Defender для Office 365 в Центре безопасности и соответствия требованиям, вам нужна соответствующая роль. В следующей таблице приведено несколько примеров.

|Роль или группа ролей|Дополнительные ресурсы|
|---|---|
|глобальный администратор (назначается Azure Active Directory или Центром безопасности и соответствия требованиям)|[О ролях администратора Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Администратор безопасности (назначается Azure Active Directory или Центром безопасности и соответствия требованиям)|[Разрешения роли администратора в Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md)|
|Управление организациями в Exchange Online (назначается Exchange Online)|[Разрешения в Exchange Online](/exchange/permissions-exo/permissions-exo) <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|Роль "Search and Purge" (поиск и очистка) (назначается только Центром безопасности и соответствия требованиям)|[Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md)|

Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

## <a name="get-microsoft-defender-for-office-365"></a>Получение Microsoft Defender для Office 365

Служба Microsoft Defender для Office 365 включена в определенные подписки, такие как Microsoft 365 E5, Office 365 E5, Office 365 A5 и Microsoft 365 бизнес премиум. Если ваша подписка не включает Defender для Office 365, Defender для Office 365 (план 1) и Defender для Office 365 (план 2) можно приобрести в дополнение к определенным подпискам. Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.

- Раздел [Доступность Microsoft Defender для Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) со списком подписок, включающих планы Defender для Office 365.

- Раздел [Доступность функций в планах Microsoft Defender для Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) со списком возможностей, включенных в планы 1 и 2.

- Раздел [Выберите подходящее решение Microsoft Defender для Office 365](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) для сравнения планов и приобретения Defender для Office 365.

- [Начало использования бесплатной пробной версии](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a>Новые возможности в Microsoft Defender для Office 365

В Microsoft Defender для Office 365 постоянно добавляются новые возможности. Для получения дополнительных сведений ознакомьтесь с приведенными ниже ресурсами.

- На странице [Дорожная карта Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=Microsoft%2CDefender%2Cfor%2COffice%2C365) приведен список новых возможностей разработки и развертывания.

- Статья [Описание службы Microsoft Defender для Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) содержит информацию о возможностях и доступности в рамках планов Defender для Office 365.

## <a name="see-also"></a>См. также

- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

- [Автоматическое исследование и реагирование в Microsoft 365 Defender](../defender/m365d-autoir.md) 1
