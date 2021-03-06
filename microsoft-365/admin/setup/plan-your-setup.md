---
title: Планирование установки Microsoft 365 для бизнеса
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Узнайте о требованиях и соображениях по переходу на Microsoft 365 для бизнеса.
ms.openlocfilehash: b4d2b5d500b73b62c67d3f8126b6313484e2bc78
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297036"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Планирование установки Microsoft 365 для бизнеса

Эта статья для людей, подписавшихся на Microsoft 365 бизнес-плана.
  
Перед перемещением организации в Microsoft 365 необходимо выполнить требования, сведения, которые необходимо иметь под рукой, и решения, которые необходимо принять.


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>Сведения, которые необходимо иметь под рукой перед запуском мастера установки

Когда вы будете готовы запустить мастер установки и переместить домен в Microsoft 365, вот сведения, которые необходимо иметь под рукой:
  
- Список людей, которые необходимо добавить в Microsoft 365. Даже если вы уже добавили их в Microsoft 365, если вы обновляете сведения о домене, необходимо ввести их имена здесь.

- Как вы собираетесь уведомить сотрудников об их пользовательском ИД и пароле, чтобы они могли войти. Будете ли вы сообщать им их данные по телефону? Или отправлять их на личные адреса электронной почты? Они не будут иметь доступ к своей электронной почте, поэтому вы не можете использовать это.

- Если у вас есть доменное имя для организации (например, **contoso.com)** и вы планируете использовать электронную почту Майкрософт, вам необходимо знать, где зарегистрирован ваш домен и есть сведения о входе.

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Что происходит при запуске мастера Microsoft 365 установки

Мастер установки позволяет установить Microsoft 365 на компьютере, добавить и проверить домен, добавить пользователей и назначить им лицензии, а также подключить домен.

> [!NOTE]
> Если необходимо назначить роли [администратора](../add-users/assign-admin-roles.md) в Microsoft 365 для бизнеса пользователям, которых вы добавляете в мастере, вы можете сделать это позже на странице **Пользователи.** 
  
Если вы не завершили мастер установки, вы можете выполнить задачи установки в любое время из [центра администрирования](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **Установки**. Здесь можно перенести электронную почту и контакты из другой службы электронной почты, изменить домен учетной записи администратора, управлять сведениями о выставлении счетов, добавлять или удалять пользователей, сбрасывать пароли и выполнять другие бизнес-функции. Дополнительные сведения о различиях между мастером установки и страницей установки см. в странице Различия между мастером установки Microsoft 365 и [страницей установки.](o365-setup-wizard-and-setup-page.md) 

Если у вас возникнут проблемы, позвоните нам. [Мы с радостью ответим на ваши вопросы.](../../business-video/get-help-support.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>Ситуации, когда не следует использовать мастер настройки: синхронизация Active Directory и гибридные среды

Существует несколько сценариев, включающих перенос данных или пользователей из локальной среды или создание гибридной системы, которая включает синхронизацию каталогов. Если вы в любой категории, следуйте инструкциям в этих статьях:
  
- Чтобы настроить синхронизацию каталогов с локальной службой Active Directory, см. в публикации Настройка синхронизации каталогов для [Microsoft 365,](../../enterprise/set-up-directory-synchronization.md)а также для понимания различных моделей удостоверений в Microsoft 365 см. статью [Understanding Microsoft 365 identity and Azure Active Directory](../../enterprise/about-microsoft-365-identity.md).

- Полный набор инструкций по настройке гибридного развертывания Exchange, которые помогут вам в использовании различных способов настройки (включая настройку записей DNS), можно найти здесь: [Помощник по развертыванию Exchange Server](/exchange/exchange-deployment-assistant)

- Сведения о настройке гибридного развертывания SharePoint, в частности гибридного поиска и сайтов, см. в статье [Гибридный поиск в SharePoint](/SharePoint/hybrid/hybrid-search-in-sharepoint).

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Перемещение Microsoft 365 всех одновременно или поэтапно

- **Вы хотите переместить организацию на Microsoft 365 одновременно?** Если это так, то запланируйте перемещение домена Microsoft 365 сразу. Начните с запуска мастера Microsoft 365 настройки; это поможет вам настроить домен.

- **Вы хотите перейти к Microsoft 365 постепенно?** Если вы хотите перейти к Microsoft 365 поэтапно, пропустите запуск мастера Microsoft 365 установки и рассмотрите возможность принятия Microsoft 365 в следующем порядке:

    1. [Добавьте сотрудников в Microsoft 365,](../add-users/add-users.md) чтобы они могли скачать и установить Office приложения.

    2. [Скачайте и установите приложения Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658), чтобы использовать Word, Excel и PowerPoint на компьютере и устройствах.

    3. [Настройка Microsoft Teams](#plan-for-teams) для собраний.

    4. [Переместите содержимое в Microsoft 365 облачное](set-up-file-storage-and-sharing.md) хранилище (OneDrive или SharePoint сайты группы).

    5. Когда вы будете готовы, в центре  администрирования [выберите](https://go.microsoft.com/fwlink/p/?linkid=2024339)настройка в левой  области навигации и используйте страницу Установки для перемещения домена [и электронной почты.](add-domain.md)

## <a name="check-that-your-devices-meet-system-requirements"></a>Проверка соответствия требованиям к системе

Каждый человек в вашей организации может установить набор приложений Office 2016 г. (Word, Excel, PowerPoint и так далее) на пять компьютеров и компьютеров Mac. См. требования к операционной системе и компьютеру для [установки Office 2016](https://go.microsoft.com/fwlink/?LinkId=534827) для бизнеса.
  
Мобильные приложения можно установить на устройствах iOS, Android и Windows. Сведения о поддержке мобильных устройств и браузеров можно найти в [system requirements for Office.](https://go.microsoft.com/fwlink/?LinkId=534827)
  
## <a name="plan-for-email"></a>Планирование службы электронной почты

Если вы планируете перейти из существующей службы электронной почты в Microsoft 365, для этого обычно требуется два дня.
  
### <a name="plan-for-email-downtime"></a>Планирование простоя электронной почты
  
Если вы собираетесь использовать Microsoft 365 для электронной почты:
  
- Чтобы переместить бизнес-адрес электронной почты *\@ (например,* contoso.com) из другой службы электронной почты в Microsoft 365, необходимо направить почту, которая будет доставлена в Microsoft 365 почтовый ящик. Это необходимо сделать,  выбрав миграцию данных  пользователей на страницу Установки, где мы пошаговую информацию об обновлениях, которые необходимо сделать в хосте домена.

- После обновления узла домена изменения обычно вступают в силу через час или два. Но следует помнить, что иногда для обновления в Интернете может занять до 72 часов.

- Так как время простоя электронной почты может быть простоем, рекомендуется перейти на электронную почту Майкрософт вечером или в выходные дни, когда вы получаете меньше сообщений электронной почты.

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>Планирование перемещения существующей электронной почты, контактов и календаря
  
Если вы собираетесь использовать Microsoft 365 учетную запись электронной почты, вы можете взять с собой существующую электронную почту, контакты и календарь. Страница **Установки** позволяет перемещать существующую электронную почту и контакты для большинства сценариев. Кроме того, предлагаются пошаговые инструкции по перемещению одного или нескольких почтовых ящиков.
  
|**Сколько у вас почтовых ящиков?**|**Рекомендации**|
|:-----|:-----|
|Один или два  <br/> |Если вы не хотите использовать страницу **Установки** для переноса почтовых ящиков, вы можете позволить владельцам почтовых ящиков перенести свою собственную электронную почту и контакты. См. миграцию электронной почты и [контактов Microsoft 365 для бизнеса](migrate-email-and-contacts-admin.md).  <br/> |
|Несколько  <br/> |Если вы мигрируете из Gmail, см. в записи Миграция почтовых ящиков [G Suite на Microsoft 365.](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)  <br/> Если вы мигрируете из другого поставщика электронной почты, в том числе Exchange, см. в примере Способы переноса нескольких учетных записей электронной почты [в Microsoft 365.](/Exchange/mailbox-migration/mailbox-migration)  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>Планирование хранения и переноса файлов

Microsoft 365 облачное хранилище для физических лиц, малых организаций и предприятий. Инструкции по хранимым документам см. в [Microsoft 365.](../../business-video/store-files.md)
  
- **Вы можете переместить сотни файлов в OneDrive** или на сайт SharePoint [](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) [группы.](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242) За один раз можно добавить 100 файлов. Не добавляйте файлы размером более 2 ГБ (по умолчанию это максимальный размер файлов).
  
- **Если вы хотите переместить несколько** тысяч файлов для Microsoft 365 хранения, просмотрите SharePoint [ограничения.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) Рекомендуется использовать средство миграции или нанимать [](https://go.microsoft.com/fwlink/?linkid=391089) партнера, чтобы помочь вам с миграцией. Сведения о переносе большого количества файлов см. в SharePoint Online и [OneDrive Migration User Guide.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)
  
## <a name="plan-for-teams"></a>Планирование Teams

Вы можете использовать Microsoft Teams для звонков другим людям в вашей организации, которые находятся на вашей подписке. Например, если в организации 10 человек, вы можете вызывать и вызывать друг друга с помощью Teams без какой-либо специальной установки. Дополнительные сведения см. в [Microsoft Teams.](/MicrosoftTeams/get-started-with-teams-quick-start)

Для более крупных организаций или если вы начинаете с Skype для бизнеса, локального или гибридного развертывания, см. в Microsoft Teams [.](/MicrosoftTeams/how-to-roll-out-teams)
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Планирование интеграции с Active Directory и другим программным обеспечением

- **Хотите интегрироваться с локальной службой Active Directory?** Вы можете интегрировать локальное Active Directory с Microsoft 365 с помощью Azure Active Directory Подключение. Инструкции см. в инструкции Настройка синхронизации [каталогов для Microsoft 365.](../../enterprise/set-up-directory-synchronization.md)
  
- **Вы хотите интегрировать Microsoft 365 с программным обеспечением, сделанным другими компаниями?** Если вам необходимо интегрировать Microsoft 365 с другим программным обеспечением [](https://go.microsoft.com/fwlink/?linkid=391089) в организации, рекомендуем вам рассмотреть возможность найма партнера, чтобы помочь вам с развертыванием.
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Вы хотите, чтобы кто-то помог вам настроить Microsoft 365?

- **Если у вас менее 50 сотрудников:**

  - **Оставьте запрос, и мы вам позвоним**. После покупки Microsoft 365 вы можете получить доступ к центру администрирования (вам не нужно запускать установку, чтобы добраться до него). В нижней части центра администрирования выберите **"Нужна помощь"?** Опишите свою проблему, и мы вам позвоним. 
  - **Позвоните [Microsoft 365 для поддержки бизнеса с](../../business-video/get-help-support.md) вашими вопросами**. We're here to help! 
  - **Подумайте над тем, не стоит ли обратиться к [партнеру Майкрософт](https://go.microsoft.com/fwlink/?linkid=391089)**. Если у вас нет времени или у вас есть расширенные требования (например, перемещение тысяч файлов в облачное хранилище Microsoft 365 или интеграция с другим программным обеспечением), опытный партнер может быть большим помощником. 

- **Если у вас более 50 сотрудников**, [FastTrack Onboarding Center](https://go.microsoft.com/fwlink/?LinkId=517115) поможет вам с развертыванием.