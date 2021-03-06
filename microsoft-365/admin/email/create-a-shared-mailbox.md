---
title: Создание общего почтового ящика
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Создайте общий почтовый ящик, чтобы позволить сразу нескольким сотрудникам организации читать электронную почту и отвечать на сообщения, отправленные на один адрес.
ms.openlocfilehash: 6fff7b1eaa73944bc4dd744046ad97ee9d2379b1
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393191"
---
# <a name="create-a-shared-mailbox"></a>Создание общего почтового ящика 

> [!NOTE]
> Если ваша организация использует гибридную среду Exchange, вам следует использовать локальный Центр администрирования Exchange (EAC) для создания общих почтовых ящиков и управления ими. См. статью [Создание общих почтовых ящиков в Центре администрирования Exchange](/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?preserve-view=true.&view=exchserver-2019)<br><br>
> Если вы не знаете, нужен ли вам общий почтовый ящик или группа Microsoft 365 для Outlook, см. инструкции в статье [Сравнение групп](../create-groups/compare-groups.md). Обратите внимание, что в настоящее время невозможно перенести общий почтовый ящик в группу Microsoft 365. Если вам нужна эта возможность, дайте нам знать, [проголосовав здесь](https://go.microsoft.com/fwlink/?linkid=871518).

Общие почтовые ящики позволяют группе пользователей отслеживать и отправлять сообщения с общего адреса, например info@contoso.com. Когда пользователь из группы отвечает на сообщение, отправленное на общий почтовый ящик, оно отображается как отправленное с общего почтового ящика, а не от отдельного пользователя.

Общие почтовые ящики включают общий календарь. На многих малых предприятиях сотрудники отмечают в общем календаре свои встречи. Например, если посещение клиентов входит в обязанности трех сотрудников, все они могут отмечать свои встречи в общем календаре. Таким образом все будут знать, кто и где находится.

Перед созданием общего почтового ящика ознакомьтесь со статьей [Сведения об общих почтовых ящиках](about-shared-mailboxes.md) для получения дополнительной информации.

## <a name="create-a-shared-mailbox-and-add-members"></a>Создание общего почтового ящика и добавление участников
  
1. Войдите с помощью учетной записи глобального администратора Exchange. Если появится сообщение "**Вам не предоставлены разрешения на доступ к этой странице или выполнение этого действия**", у вас нет прав администратора. 

::: moniker range="o365-worldwide"

2. В Центре администрирования откройте страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Общие почтовые ящики</a>.

::: moniker-end

::: moniker range="o365-germany"

2. В [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=848041) откройте страницу **Группы** \> **Общие почтовые ящики**.

::: moniker-end

::: moniker range="o365-21vianet"

2. В [Центре администрирования](https://go.microsoft.com/fwlink/p/?linkid=850627) откройте страницу **Группы** \> **Общие почтовые ящики**.

::: moniker-end
    
3. На странице **Общие почтовые ящики** нажмите **+ Добавить почтовый ящик**. Введите имя для общего почтового ящика. Затем мастер выберет адрес электронной почты, но его можно будет изменить.
    
    ![Присвойте имя общему почтовому ящику.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. Нажмите **Добавить**. Через несколько минут вы сможете добавить участников.

5. В разделе **Дальнейшие действия** щелкните **Добавить участников в этот почтовый ящик**. Участники — это люди, которые смогут просматривать входящую почту и исходящие ответы в этом почтовом ящике.

   ![Нажмите "Добавить участников"](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. Нажмите кнопку **+ Добавить участников**. Установите флажки напротив пользователей, которым вы хотите разрешить использовать этот общий почтовый ящик, и нажмите **Сохранить**.

   ![Назначение участников в общий почтовый ящик](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. Нажмите **Закрыть**.

У вас есть общий почтовый ящик, содержащий общий календарь. Теперь перейдите к следующему шагу: блокирование входа для учетной записи общего почтового ящика.

## <a name="which-permissions-should-you-use"></a>Какие разрешения следует использовать?

Для общего почтового ящика можно использовать следующие разрешения:

- **Полный доступ**. Разрешение на полный доступ позволяет пользователю открывать общий почтовый ящик и действовать с правами владельца этого почтового ящика. Получив доступ к общему почтовому ящику, пользователь может создавать элементы календаря; читать, просматривать, удалять и изменять сообщения электронной почты; создавать задачи и контакты в календаре. Тем не менее, пользователь с разрешением на полный доступ не может отправлять электронную почту из общего почтового ящика, если у него нет также разрешения "Отправить как" или "Отправить от имени".

- **Отправить как**. Разрешение "Отправить как" позволяет пользователю олицетворять общий почтовый ящик при отправке почты. Например, если Катерина войдет в общий почтовый ящик отдела маркетинга и отправит из него сообщение, отправителем будет считаться отдел маркетинга.

- **Отправить от имени.** Разрешение "Отправить от имени" позволяет пользователю отправлять электронную почту от имени общего почтового ящика. Например, если Алексей войдет в общий почтовый ящик приемной, здание 32, и отправит из него сообщение, отправителем будет считаться Алексей от имени приемной, здание 32. Разрешение "Отправить от имени" невозможно предоставить с помощью Центра администрирования Exchange. Для этого необходимо использовать командлет **Set-Mailbox** с параметром _GrantSendonBehalf_.

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a>Изменение делегирования общего почтового ящика с помощью Центра администрирования Exchange

1. В Центре администрирования Exchange выберите **Получатели** \> **Общий**. Выберите общий почтовый ящик и нажмите **Изменить** ![Значок "Изменить"](../../media/ITPro-EAC-EditIcon.png).

2. Выберите **Делегирование почтового ящика**.

3. Чтобы предоставить или удалить разрешение на полный доступ или "Отправить как", нажмите **Добавить** ![Значок "Добавить"](../../media/ITPro-EAC-AddIcon.png) или **Удалить** ![Значок "Удалить"](../../media/ITPro-EAC-RemoveIcon.gif) и выберите соответствующих пользователей.

   > [!NOTE]
   > Разрешение "Полный доступ" позволяет пользователю открывать почтовый ящик, а также создавать из изменять в нем элементы. Разрешение "Отправлять как" позволяет всем пользователям, кроме владельца почтового ящика, отправлять электронную почту из этого общего почтового ящика. Для эффективной работы с общим почтовым ящиком необходимы оба разрешения.

4. Нажмите кнопку **Сохранить**, чтобы сохранить изменения.


## <a name="block-sign-in-for-the-shared-mailbox-account"></a>Блокирование входа для учетной записи общего почтового ящика

У каждого общего почтового ящика есть соответствующая учетная запись пользователя. Вы заметили, что вам не потребовалось указывать пароль при создании общего почтового ящика? У этой учетной записи есть пароль, но он создается системой (неизвестен). Вы не должны использовать учетную запись для входа в общий почтовый ящик.

Но что если администратор просто сбросит пароль учетной записи общего почтового ящика? Или злоумышленник получит доступ к учетным данным общего почтового ящика? Это позволило бы с помощью учетной записи пользователя выполнять вход в общий почтовый ящик и отправлять электронную почту. Чтобы не допустить этого, требуется заблокировать вход для учетной записи, связанной с общим почтовым ящиком.

::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.
::: moniker-end

1. В списке учетных записей пользователей найдите учетную запись общего почтового ящика (например, примените фильтр **Нелицензированные пользователи**).

1. Выберите пользователя, чтобы открыть область свойств, и щелкните значок **Заблокировать этого пользователя** ![Снимок экрана: значок "Заблокировать этого пользователя"](../../media/block-user-icon.png).

   **Примечание**. Если учетная запись уже заблокирована, вверху отобразится надпись **Вход заблокирован**, а для значка выводится текст **Разблокировать этого пользователя**.

1. В области **Заблокировать этого пользователя?** выберите **Запретить этому пользователю вход** и нажмите **Сохранить изменения**.

Инструкции по блокированию входа для учетных записей с помощью Azure AD PowerShell (в том числе для нескольких учетных записей одновременно) см. в статье [Блокировка учетных записей пользователей с помощью PowerShell в Office 365](../../enterprise/block-user-accounts-with-microsoft-365-powershell.md).

## <a name="add-the-shared-mailbox-to-outlook"></a>Добавление общего почтового ящика в Outlook

Если в вашей организации включена функция AutoMapping (чаще всего она включена по умолчанию), общий почтовый ящик появится у пользователей в Outlook автоматически после закрытия и перезапуска приложения. 

Функция AutoMapping применяется к почтовому ящику пользователя, а не к общему почтовому ящику.   Это означает, что при попытке использовать группу безопасности для управления доступом к общему почтовому ящику функция AutoMapping работать не будет. Таким образом, чтобы работала функция AutoMapping, необходимо явно назначить разрешения. Функция AutoMapping включена по умолчанию. Сведения о ее отключении см. в статье [Удаление функции AutoMapping для общего почтового ящика](/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).

Дополнительные сведения об общих почтовых ящиках в Outlook:

- <a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Открытие и использование общего почтового ящика в Outlook</a>

- <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Добавление общего почтового ящика в Outlook в Интернете</a>

- <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Добавление общего почтового ящика в Outlook Mobile</a>

- <a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Открытие общей папки или почтового ящика в Outlook для Mac</a>

- <a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Добавление правил в общий почтовый ящик</a>

## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>Использование общего почтового ящика на мобильных устройствах (смартфонах и планшетах)

Вы можете получить доступ к общему почтовому ящику на мобильном устройстве двумя способами:
- Добавьте общий почтовый ящик в <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">приложении Outlook для iOS</a> или <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">мобильном приложении Outlook для Android</a>. 
    
    Инструкции см. в статье <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Добавление общего почтового ящика в Outlook Mobile</a>.

- Откройте браузер, выполните вход и перейдите в Outlook в Интернете. Через приложение Outlook в Интернете вы можете открыть общий почтовый ящик.

    Инструкции см. в статье <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Добавление общего почтового ящика в Outlook в Интернете</a>.
    
> [!NOTE]
> Общий почтовый ящик можно добавить только в приложение Outlook для iOS или мобильное приложение Outlook для Android.

## <a name="use-the-shared-calendar"></a>Использование общего календаря

При создании общего почтового ящика автоматически создается общий календарь. Для отслеживания встреч и местонахождения пользователей предпочтительнее использовать календарь общего почтового ящика, а не календарь SharePoint. Общий календарь интегрирован с Outlook и работать с ним проще, чем с календарем SharePoint.

1. В приложении Outlook перейдите в представление календаря и выберите общий почтовый ящик.

2. Если вы добавите встречи, они будут видны всем участникам общего почтового ящика.

3. Любой участник общего почтового ящика может создавать, просматривать и управлять встречами в календаре так же, как личными встречами. Изменения общего календаря будут видны всем участникам общего почтового ящика.

## <a name="related-content"></a>См. также:

[Сведения об общих почтовых ящиках](about-shared-mailboxes.md) (статья)\
[Настройка общего почтового ящика](configure-a-shared-mailbox.md) (статья)\
[Преобразование почтового ящика пользователя в общий почтовый ящик](convert-user-mailbox-to-shared-mailbox.md) (статья)\
[Удаление лицензии из общего почтового ящика](remove-license-from-shared-mailbox.md) (статья)\
[Решение проблем с общими почтовыми ящиками](resolve-issues-with-shared-mailboxes.md) (статья)