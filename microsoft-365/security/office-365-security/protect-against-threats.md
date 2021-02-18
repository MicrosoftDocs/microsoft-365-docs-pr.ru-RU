---
title: Защита от угроз
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Администраторы могут узнать о защите от угроз в Microsoft 365 и настроить ее использование для вашей организации.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c9ca420609628476faba6262fe7ed412b8fa5746
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288805"
---
# <a name="protect-against-threats"></a>Защита от угроз

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Область применения**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender для Office 365 (план 1 и план 2)](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Вот краткое руководство, которое разбивает конфигурацию Защитника для Office 365 на блоки. Если вы еще не используете функции защиты от угроз в Office 365, не знаете, с чего начать, или если вы научитесь лучше всего это *делать,* воспользуйтесь этим руководством в качестве контрольного списка и отправной точки.

> [!IMPORTANT]
> **Начальные рекомендуемые** параметры включены для каждого типа политики; однако доступно множество параметров, и вы можете настроить параметры в удовлетворении потребностей вашей организации. Разрешите приблизительно 30 минут, чтобы политики или изменения работали через центр обработки данных.

## <a name="requirements"></a>Требования

### <a name="subscriptions"></a>Подписки

Функции защиты от угроз включены во *все* подписки Microsoft или Office 365; однако некоторые подписки имеют расширенные возможности. В таблице ниже перечислены функции защиты, включенные в эту статью, а также минимальные требования к подписке.

> [!TIP]
> Обратите внимание, что помимо действий по  включаемой проверке, необходимо запустить защиту от вредоносных программ, фишинга и нежелательной почты, которые помечены как часть Office 365 Exchange Online Protection **(EOP).** This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.

****

|Тип защиты|Требование к подписке|
|---|---|
|Ведение журнала аудита (для создания отчетов)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Защита от вредоносных программ|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) **(EOP)**|
|Защита от фишинга|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Защита от нежелательной почты|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Автоматическая очистка (для электронной почты)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Защита от вредоносных URL-адресов и файлов в электронной почте и документах Office (безопасные ссылки и безопасные вложения)|[Microsoft Defender для Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Включить безопасные вложения для рабочих нагрузок SharePoint, OneDrive и Microsoft Teams|[Защитник для Office 365 ](atp-for-spo-odb-and-teams.md)|
|Расширенные средства защиты от фишинга|[Defender для Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Роли и разрешения

Чтобы настроить Защитник для политик Office 365, вам должна быть назначена соответствующая роль в Центре безопасности [& соответствия требованиям.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) В приведенной ниже таблице приведены роли, которые могут делать эти действия.

****

|Роль или группа ролей|Где можно узнать больше|
|---|---|
|глобальный администратор|[О ролях администратора Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Администратор безопасности|[Разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Управление организациями в Exchange Online|[Разрешения в Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> и <p> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Дополнительные узнать [см. в центре безопасности и соответствия & Permissions.](permissions-in-the-security-and-compliance-center.md)

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Перед началом включите ведение журнала аудита для отчетности и исследования

Начните ведение журнала аудита раньше. Для некоторых действий вам потребуется, чтобы аудит был в **действии.** Ведение журнала аудита доступно в подписках, в том числе [Exchange Online.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) Для просмотра данных в отчетах о защите от [](view-email-security-reports.md)угроз, таких как панель мониторинга [безопасности,](security-dashboard.md)отчеты о безопасности электронной почты и [проводник,](threat-explorer.md)ведение журнала аудита должно быть *в порядке.* Дополнительные данные см. в записи "Включить или отключить [поиск в журнале аудита".](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>Часть 1. Защита от вредоносных программ

[Защита от вредоносных программ](anti-malware-protection.md) доступна в подписках, в том числе [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. В Центре [безопасности & соответствия требованиям](https://protection.office.com)выберите политику **управления** угрозами для защиты от \>  \> **вредоносных программ.**

2. Дважды щелкните политику **по** умолчанию и выберите **параметры.**

3. Укажите следующие параметры:

    - В разделе **"Реагирование на обнаружение** вредоносных программ" оохраняем значение по умолчанию **"Нет".**

    - В разделе **"Фильтр общих типов вложений"** выберите **"В.**

4. Щелкните **Сохранить**.

Дополнительные информацию о параметрах политики для борьбы с вредоносными программами см. в подстройке "Настройка политик для борьбы с вредоносными [программами".](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection"></a>Часть 2. Защита от фишинга

[Защита от фишинга](anti-phishing-protection.md) доступна в подписках, включающих [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Advanced anti-phishing protection is available in [Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

В следующей процедуре описывается настройка политики защиты от фишинга в Microsoft Defender для Office 365. Эти действия аналогичны настройке политики защиты от фишинга в EOP.

1. В Центре [безопасности & соответствия](https://protection.office.com)требованиям выберите **политику** управления угрозами ATP для защиты \>  \> **от фишинга.**

2. Щелкните **политику по умолчанию.**

3. В разделе **"Под вопросом"** нажмите **кнопку "Изменить"** и укажите следующие параметры:

   - На **вкладке "Добавление пользователей для защиты"** включите *защиту.* Затем добавьте пользователей, таких как члены совета директоров организации, исполнительный директор, CFO и другие старшие руководители. (Можно ввести отдельный адрес электронной почты или щелкнуть, чтобы отобразить список.)

   - On the **Add domains to protect** tab, turn on **Automatically include the domains I own**. Если у вас есть настраиваемые домены, добавьте их сейчас.

   - На **вкладке "Действия"** выберите "Карантин сообщения" для параметров как для подручного пользователя, так и для  **подмащенного домена.**  Кроме того, включите советы по безопасности при подналичии.

   - На **вкладке "Аналитика почтовых** ящиков" убедитесь, что включена аналитика почтовых ящиков, и включите защиту от поднабора на основе аналитики почтовых ящиков. In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.

   - На **вкладке "Добавление надежных отправителей и доменов"** укажите всех надежных отправителей или домены, которые вы хотите добавить.

   - **Сохраните** вкладку **"Просмотр параметров"** после просмотра параметров.

4. В разделе **"Спуфинг"** нажмите кнопку **"Изменить"** и укажите следующие параметры:

   - **Убедитесь,** что на вкладке параметров фильтра спуфинга включена защита от спуфинга.

   - На **вкладке "Действия"** выберите **"Карантин сообщения".**

   - **Сохраните** **вкладку "Просмотр параметров"** после просмотра изменений. (Если вы не влияли на изменения, **отмените.)**

5. Закроем страницу параметров политики по умолчанию.

Дополнительные узнать о параметрах политики защиты от фишинга см. в подстроке "Настройка политик защиты от фишинга" в [Microsoft Defender для Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="part-3---anti-spam-protection"></a>Часть 3. Защита от нежелательной почты

[Защита от нежелательной почты](anti-spam-protection.md) доступна в подписках, в том числе [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. В Центре [безопасности & соответствия](https://protection.office.com)требованиям выберите **политику** управления угрозами для защиты \>  \> **от нежелательной почты.**

2. На **вкладке "Настраиваемые"** включите настраиваемые параметры.

3. **Разойдите политику фильтрации нежелательной** почты по умолчанию, нажмите кнопку **"Изменить политику"** и укажите следующие параметры:

   - В разделе **"Спам и** массовые действия" установите пороговое значение 5 или 6.

   - В разделе **"Списки разрешенных"** просмотрите (и/или отредактируете) разрешенных отправителей и домены.

4. Щелкните **Сохранить**.

Дополнительные информацию о параметрах политики нежелательной почты см. в подстройке "Настройка политик нежелательной [почты" в EOP.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Часть 4. Защита от вредоносных URL-адресов и файлов (безопасные ссылки и безопасные вложения в Защитнике office 365)

Защита от вредоносных URL-адресов и файлов во время щелчка доступна в подписках, в том числе [в Microsoft Defender для Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) Она настроена с помощью политик безопасных [вложений](atp-safe-attachments.md) и [безопасных](atp-safe-links.md) ссылок.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Политики безопасных вложений в Microsoft Defender для Office 365

Чтобы настроить [безопасные вложения,](atp-safe-attachments.md)создайте по крайней мере одну политику безопасных ссылок.

1. In the [Security & Compliance Center,](https://protection.office.com)choose **Threat management** \> **Policy** \> **ATP Safe Attachments,** and then click **Create**.

2. В **мастере создания** политики безопасных вложений настройте следующие параметры:

   - В поле **"Имя"** введите `Block malware` и нажмите кнопку **"Далее".**

   - На странице **"Параметры"** настройте следующие параметры:
     - В разделе **"Безопасные вложения неизвестные вредоносные программы"** выберите **"Блокировать".**
     - В разделе **"Перенаправление** вложений" выберите параметр **"Включить перенаправление".** Укажите адрес электронной почты администратора или оператора безопасности организации, который будет рассматривать обнаруженные файлы.

     Нажмите **Далее**.

3. On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is,** click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.

4. Просмотрите параметры и нажмите кнопку **"Готово".**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Политики безопасных ссылок в Microsoft Defender для Office 365

Чтобы настроить [безопасные ссылки,](atp-safe-links.md)просмотрите и отредактируете глобальные параметры безопасных ссылок и создайте по крайней мере одну политику безопасных ссылок.

1. В Центре [безопасности & соответствия](https://protection.office.com)  требованиям выберите "Безопасные ссылки ATP для политики управления угрозами" и щелкните "Глобальные параметры" и настройте \>  \> следующие параметры: 

   - Проверьте **использование безопасных ссылок: приложения Office 365** включены: ![ переключение. ](../../media/scc-toggle-on.png)
   - **Не отслеживайте, когда пользователи нажимают** кнопку "Безопасные ссылки": отключите этот параметр для отслеживания щелчков: ![ "Отключить". ](../../media/scc-toggle-off.png)
   - **Не позволяйте пользователям пережимать безопасные** ссылки на исходный URL-адрес: убедитесь, что этот параметр включен: ![ "Переключение" ](../../media/scc-toggle-on.png) .

   По завершении нажмите кнопку **Сохранить**.

2. На главной странице "Безопасные ссылки" нажмите кнопку **"Создать".**

3. В **мастере создания политики** безопасных ссылок настройте следующие параметры:

   - В поле **"Имя"** введите имя, например `Safe Links` , и нажмите кнопку **"Далее".**

   - На странице **"Параметры"** настройте следующие параметры:
     - **Выберите действие для неизвестных потенциально вредоносных URL-адресов в сообщениях:** выберите **"В"**.
     - **Выберите действие для неизвестных или потенциально вредоносных URL-адресов в Microsoft Teams:** выберите **"В"**.
     - **Применение безопасных ссылок к электронным письмам, отправленным в организации**
     - **Дождись завершения проверки URL-адресов перед доставкой сообщения**
     - **Применение безопасных ссылок к электронным письмам, отправленным в организации**
     - **Не разрешайте пользователям перенажимать исходный URL-адрес**

     Нажмите кнопку **Далее**.

4. On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is,** click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.

5. Просмотрите параметры и нажмите кнопку **"Готово".**

Дополнительные сведения см. в статье [Настройка политик безопасных ссылок](set-up-atp-safe-links-policies.md).

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Часть 5. Проверка того, что безопасные вложения для SharePoint, OneDrive и Microsoft Teams включены

Рабочие нагрузки, такие как SharePoint, OneDrive и Teams, построены для совместной работы. Использование Защитника для Office 365 помогает блокировать и обнаруживать файлы, которые определены как вредоносные на сайтах группы и в библиотеках документов. Подробнее о том, как это работает, можно узнать [здесь.](atp-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> **Перед началом этой процедуры убедитесь,** что ведение журнала аудита уже включено для вашей среды Microsoft 365. Обычно это делается человеком, которому назначена роль "Журналы аудита" в Exchange Online. Дополнительные сведения см. в записи "Включить или отключить поиск [в журнале аудита".](../../compliance/turn-audit-log-search-on-or-off.md)

1. В Центре [безопасности & соответствия](https://protection.office.com)требованиям  выберите "Безопасные вложения ATP" политики управления угрозами, а затем щелкните \>  \>  **"Глобальные параметры".**

2. Убедитесь, что выключатель "Включить Защитник для **Office 365 для SharePoint", OneDrive** и Microsoft Teams находится справа: "Включить" и нажмите кнопку ![ ](../../media/scc-toggle-on.png) **"Сохранить".**

3. Просмотрите (и при необходимости отредактируете) политики безопасных вложений организации и политики [безопасных ссылок.](set-up-atp-safe-links-policies.md) [](set-up-atp-safe-attachments-policies.md)

4. (Рекомендуется) Как глобальный администратор или администратор SharePoint Online запустите cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** с параметром _DisallowInfectedFileDownload,_ заданным как `$true` .

   - `$true` блокирует все действия (кроме удаления) для обнаруженных файлов. Люди не могут открывать, перемещать, копировать или делиться обнаруженными файлами.
   - `$false` блокирует все действия, кроме удаления и скачивания. Люди могут принять риск и скачать обнаруженный файл.

   > [!TIP]
   > Чтобы узнать больше об использовании PowerShell с Microsoft 365, см. "Управление [Microsoft 365 с помощью PowerShell".](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)

5. В течение 30 минут изменения распространяются на все центры обработки данных Microsoft 365.

### <a name="now-set-up-alerts-for-detected-files"></a>Теперь настройка оповещений для обнаруженных файлов

Чтобы получать уведомления о том, что файл в SharePoint Online, OneDrive для бизнеса или Microsoft Teams определен как вредоносный, можно настроить оповещение.

1. В Центре [безопасности & соответствия](https://protection.office.com)требованиям выберите **"Alerts** \> **Manage alerts" (Управление оповещениями).**

2. Выберите **новую политику оповещений.**

3. Укажите имя оповещения. Например, можно ввести вредоносные файлы в библиотеках.

4. Введите описание оповещения. Например, вы можете ввести "Нотировать администраторам" при обнаружении вредоносных файлов в SharePoint Online, OneDrive или Microsoft Teams.

5. В разделе **"Отправить это оповещение, когда...** установите:

   а. В **списке действий** выберите **"Обнаруженная вредоносная программа" в файле.**

   б. Оставьте **поле "Пользователи"** пустым.

6. В разделе **"Отправить это** оповещение... выберите одного или несколько глобальных администраторов, администраторов безопасности или читателей безопасности, которые должны получать уведомления при обнаружении вредоносного файла".

7. **Сохраните**.

Дополнительные информацию об оповещениях см. в центре безопасности [и & соответствия требованиям.](../../compliance/create-activity-alerts.md)

> [!NOTE]
> Завершив настройку, воспользуйтесь этими ссылками, чтобы начать исследование рабочей нагрузки:
>
>- [отчет о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report);
>- [Использование Центра безопасности & соответствия требованиям для управления файлами на карантине](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Действия при обнаружении вредоносного файла в SharePoint Online, OneDrive или Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Управление сообщениями и файлами на карантине от администратора в Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Часть 6. Дополнительные параметры для настройки

Наряду с настройкой защиты от вредоносных программ, вредоносных URL-адресов и файлов, фишинга и нежелательной почты, мы рекомендуем настроить автоматическую очистку.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Автоматическая очистка электронной почты в EOP

[Автоматическая очистка](zero-hour-auto-purge.md) (ZAP) нулевого часа доступна в подписках, включая [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Эта защита включена по умолчанию; однако для того, чтобы защита вступила в силу, должны быть выполнены следующие условия:

- Для действий с нежелательной **почтой** в политиках борьбы с нежелательной почтой настроено перемещение сообщения в папку [нежелательной почты.](anti-spam-protection.md)

- Пользователи сохранили параметры нежелательной почты по умолчанию [и](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)не отключили защиту от нежелательной почты.

Дополнительные узнать см. в автоматической очистке нулевого часа [— защите от нежелательной почты и вредоносных программ.](zero-hour-auto-purge.md)

## <a name="post-setup-tasks-and-next-steps"></a>Задачи после установки и дальнейшие действия

После настройки функций защиты от угроз обязательно отслеживайте их работу! Просмотрите и изредкайте политики, чтобы они могли делать то, что вам нужно. Кроме того, следите за новыми функциями и обновлениями служб, которые могут добавить значение.

****

|Действия|Дополнительные ресурсы|
|---|---|
|Просмотр отчетов о работе функций защиты от угроз в организации|[Панель мониторинга безопасности](security-dashboard.md) <p> [Отчеты о безопасности электронной почты](view-email-security-reports.md) <p> [Отчеты для Microsoft Defender для Office 365](view-reports-for-atp.md) <p> [Обозреватель угроз](threat-explorer.md)|
|Периодически проверяйте и пересматривайте политики защиты от угроз по мере необходимости|[Оценка безопасности](../mtp/microsoft-secure-score.md) <p> [Интеллектуальные отчеты и анализ](reports-and-insights-in-security-and-compliance.md) <p> [Функции исследования угроз и реагирования на них в Microsoft 365](keep-users-safe-with-office-365-ti.md)|
|Следите за новыми функциями и обновлениями служб|[Стандартные и целевые варианты выпуска](../../admin/manage/release-options-in-office-365.md) <p> [Центр сообщений](../../admin/manage/message-center.md) <p> [Дорожная карта Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Описание службы](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Сведения о рекомендуемых конфигурациях безопасности Standard и Strict для EOP и Defender для Office 365|[Рекомендуемые параметры для EOP и Microsoft Defender для безопасности Office 365](recommended-settings-for-eop-and-office365-atp.md)|
