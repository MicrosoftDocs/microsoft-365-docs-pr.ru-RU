---
title: Защита от угроз
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о защите от угроз в Microsoft 365 и о том, как ее использовать в организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8f1cecbb3141b4751778212025e5aad582707e12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826829"
---
# <a name="protect-against-threats"></a>Защита от угроз

В Microsoft 365 есть различные функции защиты от угроз. Ниже приведено краткое руководство для начала работы с exchange, с помощью которого можно выполнить настройку функций защиты от угроз в вашей организации. Если вы не знаете, с того, на каком этапе вы не знакомы с функциями защиты от угроз в Office 365 или незовыскаете, вы не знаете, с чего начать, используйте следующие рекомендации.

> [!IMPORTANT]
> **Начальные рекомендуемые параметры включаются для каждого типа политики. Однако доступны многие параметры,** и вы можете настроить параметры в соответствии с потребностями вашей организации. Дайте возможность пользователям работать с политиками или изменениями в центре обработки данных приблизительно через 30 минут.

## <a name="requirements"></a>Requirements

### <a name="subscriptions"></a>Подписки

Функции защиты от угроз включены во все подписки на Microsoft 365. Однако некоторые подписки включают более расширенные функции. В приведенной ниже таблице перечислены функции защиты, включенные в данную статью, а также минимальные требования к подписке.

****

|Тип защиты|Требование подписки|
|---|---|
|Защита от вредоносных программ|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)|
|Защита от вредоносных URL-адресов и файлов в электронных письмах и документах Office|[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)|
|Защита от фишинга|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Расширенная защита от фишинга|[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Защита от нежелательной почты|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Автоматическая очистка (для электронной почты)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Ведение журнала аудита (используется для создания отчетов)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>Роли и разрешения

Вам должна быть назначена соответствующая роль для настройки политик в [Центре безопасности & соответствия требованиям.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) В таблице приведено несколько примеров.

****

|Роль или группа ролей|Where to learn more|
|---|---|
|глобальный администратор|[О ролях администратора Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Администратор безопасности|[Разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Управление организациями в Exchange Online|[Разрешения в Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>и<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Дополнительные сведения см. в разделе ["Разрешения" в Центре &amp; соответствия требованиям безопасности.](permissions-in-the-security-and-compliance-center.md)

## <a name="part-1---anti-malware-protection"></a>Часть 1. Защита от вредоносных программ

[Защита от вредоносных](anti-malware-protection.md) программ доступна в подписках, включающих [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. В Центре [безопасности & соответствия требованиям выберите](https://protection.office.com)пункт **"Защита от**  >  **вредоносных**  >  **программ" политики управления угрозами.**

2. Дважды щелкните **политику по** умолчанию и выберите **параметры.**

3. Укажите следующие параметры:

    - В разделе **реагирования при обнаружении** вредоносных программ оставьте значение **"Нет" по умолчанию.**

    - В разделе **"Фильтр распространенных типов вложений"** выберите значение **"Включено".**

4. Щелкните **Сохранить**.

Дополнительные сведения о параметрах политикзащиты от вредоносных программ см. в статье ["Настройка политик защиты от вредоносных программ".](configure-anti-malware-policies.md)

## <a name="part-2---protection-from-malicious-urls-and-files"></a>Часть 2. Защита от вредоносных URL-адресов и файлов

Защита от щелчка по вредоносным URL-адресам и файлам доступна в подписках, [включающих Office 365 ATP (ATP),](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) и устанавливается с помощью [политик безопасных](atp-safe-attachments.md) вложений [и безопасных ссылок ATP.](atp-safe-links.md)

### <a name="atp-safe-attachments-policies"></a>Политики безопасных вложений ATP

Чтобы настроить [безопасные вложения ATP,](atp-safe-attachments.md)необходимо определить по крайней мере одну политику безопасных вложений ATP.

1. В Центре [безопасности & выберите](https://protection.office.com) **безопасные**  >  **вложения**  >  **ATP с политикой управления угрозами.**

2. Выберите параметр **"Включить ATP для SharePoint, OneDrive и Microsoft Teams".**

3. В разделе **"Защита вложений электронной почты"** выберите знак "плюс" ( **+**

4. Укажите следующие параметры:

   - В поле **"Имя"** введите `Block malware` .

   - В разделе ответа выберите **"Блокировать".**

   - В разделе **"Перенаправление вложений"** выберите параметр **"Включить перенаправление"** и укажите адрес электронной почты администратора безопасности вашей организации или оператора, который будет проверять обнаруженные файлы.

   - В разделе **"Применяется** к **разделу" выберите домен получателя.** Затем выберите домен, нажмите кнопку **"Добавить",** а затем нажмите кнопку **ОК.**

5. Щелкните **Сохранить**.

6. **(Рекомендуется дополнительного шага)** Как глобальный администратор или администратор SharePoint Online выполните **[командлет Set-SPOTenant,](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** у которого **для параметра DisallowInfectedFileDownload** *установлено* значение true для вашей среды Microsoft 365. (Это не позволяет открывать, перемещать, копировать и совместно использовать файлы, которые станут вредоносными.)

Дополнительные сведения см. в статье ["Настройка политик безопасных вложений ATP Office 365"](set-up-atp-safe-attachments-policies.md) и включение [Office 365 ATP для SharePoint, OneDrive и Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)

### <a name="atp-safe-links-policies"></a>Политики безопасных ссылок ATP

Чтобы настроить [безопасные ссылки ATP,](atp-safe-links.md)проверьте и измените политику по умолчанию, а также добавьте политику для определенных пользователей.

1. В Центре [безопасности & выберите](https://protection.office.com)пункт **"Безопасные**  >  **ссылки**  >  **ATP" в "Политика управления угрозами".**

2. Дважды щелкните **политику по умолчанию.**

3. В разделе **"Использование безопасных ссылок"** выберите вариант **"Приложения Microsoft 365 для предприятий", "Office для iOS и Android"** и нажмите кнопку **"Сохранить".**

4. В разделе **"Политики", применяемые к определенным получателям,** щелкните знак "плюс" **+** ().).

5. Укажите следующие параметры:

   - В поле **"Имя"** введите имя, `Safe Links` например.

   - В разделе **выбора действия** выберите **"Вкл.".**

   - Выберите эти параметры:

     - **Использование безопасных вложений для проверки загружаемого содержимого**

     - **Применение безопасных ссылок к сообщениям электронной почты, отправляемым в пределах организации**

     - **Не разрешать пользователям переходить по безопасным ссылкам на исходный URL-адрес**

   - В разделе **"Применяется** к **разделу" выберите домен получателя.** Затем выберите домен, нажмите кнопку **"Добавить",** а затем нажмите кнопку **ОК.**

6. Щелкните **Сохранить**.

Дополнительные сведения см. в статье [Настройка политик безопасных ссылок ATP в Office 365](set-up-atp-safe-links-policies.md).

## <a name="part-3---anti-phishing-protection"></a>Часть 3. Защита от фишинга

[Защита от фишинга]

[Защита от фишинга доступна](anti-phishing-protection.md) в подписках, включающих [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Расширенная защита от фишинга доступна [в ATP.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

Ниже описана настройка политики защиты от фишинга ATP. Действия аналогичны настройке политики защиты от фишинга (без ATP).

1. В [Центре безопасности & выберите](https://protection.office.com) **защиту от фишинга**политики  >  **Policy**  >  **управления угрозами ATP.**

2. Щелкните **"Политика по умолчанию".**

3. В разделе **олицетворения** нажмите **кнопку "Изменить"** и укажите следующие параметры.

   - На вкладке **"Добавить пользователей для защиты"** включите защиту. Затем добавьте пользователей, например членов доски вашей организации, исследовательский директор, использованный директор и другие старшего входящего директора. (Можно ввести отдельный адрес электронной почты или щелкнуть для отображения списка.)

   - На вкладке **"Добавить домены для защиты"** включите параметр "Автоматически включить **в ключ и домены, принадлежащие мне"** Если у вас есть пользовательские домены, добавьте их и для них.

   - На вкладке **"Действия"** выберите **"Поместить сообщение на** карантин" для **олицетворенного** пользователя и **олицетворенного** домена. Кроме того, включите советы по безопасности олицетворения.

   - На **вкладке "Аналитика почтовых ящиков"** убедитесь, что аналитика почтового ящика включена. Кроме того, включите защиту от олицетворения на основе аналитики почтовых ящиков. Если сообщение **отправляется из олицетворенного** списка пользователей, выберите команду **"Поместить сообщение в карантин".**

   - На **вкладке "Добавление надежных отправителей и доменов"** укажите надежных отправителей или домены для добавления.

   - На **вкладке "Проверьте параметры"** после проверки параметров нажмите кнопку **"Сохранить".**

4. В разделе **"Подделка"** щелкните **"Изменить"** и укажите следующие параметры.

   - На **вкладке параметров фильтра подделок** убедитесь, что защита от спуфинга включена.

   - На вкладке **"Действия" выберите** пункт **"Поместить сообщение в карантин".**

   - На **вкладке "Проверьте параметры"** после проверки параметров нажмите кнопку **"Сохранить".** (Если вы не вносили никаких изменений, нажмите кнопку **Отмена.**

5. Закройте страницу параметров политики по умолчанию.

Дополнительные сведения о параметрах политики защиты от фишинга см. в статье ["Настройка политик защиты от фишинга" ATP.](configure-atp-anti-phishing-policies.md)

## <a name="part-4---anti-spam-protection"></a>Часть 4. Защита от нежелательной почты

[Защита от нежелательной](anti-spam-protection.md) почты доступна в подписках, включающих [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. В Центре [безопасности & выберите защиту](https://protection.office.com) **от**  >  **Policy**  >  **политики управления угрозами.**

2. На вкладке **Custom (Настраиваемые)** включите **независимые** параметры.

3. Разверните **"Политика фильтрации нежелательной почты по**умолчанию", **щелкните**"Изменить политику" и укажите следующие параметры:

   - В разделе **"Нежелательная почта и** массовые действия" установите для порога значение 5 или 6.

   - В разделе **списков разрешений** просмотрите (и, при необходимости, измените список разрешенных отправителей и доменов).

4. Щелкните **Сохранить**.

Дополнительные сведения о параметрах политики защиты от нежелательной почты см. в статье ["Настройка политик защиты от нежелательной почты" в EOP.](configure-your-spam-filter-policies.md)

## <a name="part-5---additional-settings-to-configure"></a>Часть 5. Дополнительные параметры, которые необходимо настроить

Помимо настройки защиты от вредоносных, вредоносных URL-адресов и файлов, фишинговых сообщений и спама рекомендуется настроить параметры автоматической очистки и ведения журнала аудита.

### <a name="zero-hour-auto-purge-for-email"></a>Автоматическая очистка электронной почты

[Автоматическая очистка](zero-hour-auto-purge.md) (ZAP) доступна в подписках, включающих [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Защита включена по умолчанию; Однако для обеспечения их защиты необходимо соблюдать следующие условия:

- Действия с нежелательной почтой настроены на **перемещение сообщений в папку нежелательной почты в** [политиках защиты от нежелательной почты.](anti-spam-protection.md)

- Пользователи сохращают параметры [нежелательной почты](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)по умолчанию и не отключили защиту от нежелательной почты.

Дополнительные сведения см. в статье ["Автоматическая очистка" для защиты от спама и вредоносных программ.](zero-hour-auto-purge.md)

### <a name="audit-logging-for-reporting-and-investigation"></a>Ведение журнала аудита для отчетности и исследования

Ведение журнала аудита доступно в подписках, включающих [Exchange Online.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) Чтобы просматривать данные в отчетах о защите от угроз, таких как [информационная](security-dashboard.md)панель безопасности, [отчеты о безопасности](view-email-security-reports.md)электронных писем и [проводник,](threat-explorer.md)необходимо включить ведение журнала аудита для вашей организации. Дополнительные сведения см. в разделе ["Включение и отключение поиска в журнале аудита".](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="post-setup-tasks"></a>Задачи, выполняемые после установки

После настройки функций защиты от угроз обязательно отслеживайте работу этих функций, проверяйте и вносите изменения в свои политики при необходимости, а также просматривайте новые функции и обновления служб.

****

|Действия|Дополнительные ресурсы|
|---|---|
|Узнайте, как функции защиты от угроз работают в вашей организации путем просмотра отчетов|[Информационная панель безопасности](security-dashboard.md)<br/>[Отчеты о безопасности электронной почты](view-email-security-reports.md)<br/>[Отчеты для Office 365 ATP](view-reports-for-atp.md)<br/>[Обозреватель угроз](threat-explorer.md)|
|Периодический просмотр и изменение политик защиты от угроз по мере необходимости|[Оценка безопасности](../mtp/microsoft-secure-score.md)<br/>[Интеллектуальная аналитика и аналитика](reports-and-insights-in-security-and-compliance.md)<br/>[Функции анализа угроз и реагирования на них в Microsoft 365](keep-users-safe-with-office-365-ti.md)|
|Смотрите на наличие новых функций и обновлений служб|[Варианты выпусков стандартных и целевых версий](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Центр сообщений](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[План развития Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Описания служб](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
