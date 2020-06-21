---
title: Удаление бывшего сотрудника
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: 'Используйте этот контрольный список, чтобы удалить сотрудника из Microsoft 365 и защищенных данных. '
ms.openlocfilehash: adf5c683828b30a978199145fa2c54f17d1b6b37
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780581"
---
# <a name="remove-a-former-employee"></a>Удаление бывшего сотрудника

::: moniker range="o365-21vianet"

> [!NOTE]
> Изменяется Центр администрирования. Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
## <a name="sign-out-now"></a>Немедленный выход

::: moniker range="o365-worldwide"

Посмотрите короткое видео об удалении сотрудника. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Если этот видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

Чтобы удалить сотрудника, выполните указанные ниже действия.

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.

2. Установите флажок рядом с именем пользователя, а затем нажмите кнопку **сбросить пароль**.

3. Введите новый пароль, а затем нажмите кнопку **сбросить**. (Не отправляйте их.)
    
4. Выберите имя пользователя, чтобы перейти в область свойств, и на вкладке **OneDrive** нажмите кнопку **начать выход**.

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

2. Выберите пользователя, а затем нажмите кнопку **сбросить пароль**.

3. Введите новый пароль, а затем нажмите кнопку **сбросить**. (Не отправляйте их.)

4. Снова выберите пользователя, разверните узел **Параметры OneDrive**, а затем нажмите кнопку **начать** возле **выхода.**

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.

2. Выберите пользователя, а затем нажмите кнопку **сбросить пароль**.

3. Введите новый пароль, а затем нажмите кнопку **сбросить**. (Не отправляйте их.)

4. Снова выберите пользователя, разверните узел **Параметры OneDrive**, а затем нажмите кнопку **начать** возле **выхода.**

::: moniker-end

    
В течение часа или после того, как они покидают текущую страницу Microsoft 365, на которой они включены, вам будет предложено выполнить вход повторно. (Маркер доступа хорошо подходит для часа, поэтому временная шкала зависит от того, сколько времени осталось на этом маркере и как они выходят из текущей веб-страницы.)
  
 **Внимание!** если пользователь находится в Outlook в Интернете, просто щелкайте его в своем почтовом ящике, вы не можете сразу отступить к работе. После выбора другой плитки, например OneDrive, или обновления браузера выйдите из нее. 
  
Инструкции по немедленному отключению пользователя с помощью PowerShell см. в описании командлета [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345). 
  
Дополнительные сведения о времени, требуемом для завершения почтового сеанса, см. в разделе [Что нужно знать о завершении почтового сеанса сотрудника](#what-you-need-to-know-about-terminating-an-employees-email-session).
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>Обзор всех действий по удалению сотрудника и защите данных
<a name="bkmk_now"> </a>

Нас часто спрашивают о том, что нужно делать для защиты данных при увольнении сотрудников. В этой статье описывается блокировка доступа к Microsoft 365 и действия, которые необходимо предпринять для защиты данных.
  
> [!NOTE]
> Если вы являетесь глобальным администратором, вы можете удалить сотрудника, переслать его, а затем выбрать, что делать с контентом OneDrive с помощью нового интерактивного интерфейса. Для получения дополнительных сведений см [глобальный администратор: Удаление пользователя](remove-former-employee.md). Тем не менее, мы рекомендуем выполнить все дополнительные действия, указанные в этом разделе, чтобы убедиться, что у сотрудника нет доступа к данным вашей компании. 
  
Here's a quick overview. Each step is explained in detail in this article.
  
|||
|:-----|:-----|
|**Шаг** <br/> |**Причина** <br/> |
|1. [Сохранение содержимого почтового ящика бывшего сотрудника](#save-the-contents-of-a-former-employees-mailbox) <br/> |Содержимое почтового ящика может пригодиться новому сотруднику, который будет принимать должность, а также в случае судебного разбирательства.  <br/> |
|2. [Переадресация электронной почты бывшего сотрудника другому сотруднику или преобразование в общий почтовый ящик](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.  <br/> |
|3. [Очистка и блокирование мобильного устройства бывшего сотрудника](#wipe-and-block-a-former-employees-mobile-device) <br/> |Бизнес-данные будут удалены с телефона или планшета.  <br/> |
|4. [Блокировка доступа бывшего сотрудника к данным Microsoft 365](#block-a-former-employees-access-to-microsoft-365-data)<br/> |Он предотвращает доступ пользователя к своим старым почтовым ящикам и данным Microsoft 365.  <br/><br/> **Совет**: когда вы блокируете доступ пользователя, вы по-прежнему оплачиваете лицензию. Чтобы перестать платить за лицензию, ее необходимо удалить из подписки (шаг 5).           |
|5. [Перемещение содержимого OneDrive сотрудника](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |Если удалить лицензию пользователя, но не удалять его учетную запись, его содержимое в OneDrive останется доступным для вас даже по истечении 30-дневного периода.  <br/><br/> Before you delete the account, you should move the content of their OneDrive to another location that's easy for you to access. After you delete an employee's account, the content in their OneDrive is retained for **30** days. During that 30 days, however, you can restore the user's account, and gain access to their OneDrive content. If you restore the user's account, the OneDrive content will remain accessible to you even after 30 days.  <br/> |
|5a. What if the person used their personal computer to access OneDrive and SharePoint?  <br/> |Если для скачивания файлов из OneDrive и SharePoint использовался не корпоративный, а личный компьютер, удалить сохраненные файлы невозможно.  <br/><br/> У пользователей сохранится доступ к файлам, которые были синхронизированы с их компьютером.  <br/> |
|6. [Удаление и удаление лицензии Microsoft 365 из бывшего сотрудника](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person.  <br/><br/> When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  <br/> |
|7. [Удаление учетной записи бывшего сотрудника](#delete-a-former-employees-user-account)<br/> |Эта учетная запись будет удалена из центра администрирования. Это помогает поддерживать порядок.  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>Сохранение содержимого почтового ящика бывшего сотрудника
<a name="bkmk_preserve"> </a>

Сохранить содержимое почтового ящика бывшего сотрудника можно двумя способами:
  
1. Add the former employee's email address to your version of Outlook 2013 or 2016, and then export the data to a .pst file. You can import the data to another email account as needed. To learn how to do this, see [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).
    
    ИЛИ
    
2. Place a Litigation Hold or In-Place Hold on the mailbox before the deleting the user account. This is much more complicated than the first option but worth doing if: your Enterprise plan includes archiving and legal hold, litigation is a possibility, and you have a technically strong IT department.
    
    После перевода почтового ящика в неактивное состояние администраторы, документоведы или лица, ответственные за обеспечение соответствия требованиям, могут использовать средства обнаружения электронных данных и удержания на месте в Exchange Online для доступа к нему и поиска в его содержимом.
    
    Неактивные почтовые ящики не могут принимать электронную почту и не отображаются в общей адресной книге организации и других списках.
    
    Чтобы узнать, как разместить удержание в почтовом ящике, ознакомьтесь со статьей [управление неактивными почтовыми ящиками в Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>Переадресация электронной почты бывшего сотрудника другому сотруднику или преобразование в общий почтовый ящик
<a name="bkmk_forward"> </a>

На этом этапе вы назначаете адрес электронной почты бывшего сотрудника другому сотруднику или [преобразуете почтовый ящик пользователя в уже созданный общий почтовый ящик](../email/convert-user-mailbox-to-shared-mailbox.md). 
  
- Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it. 
    
- If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.
    
- Если вы настроите переадресацию электронной почты, только  *новые*  сообщения, отправленные бывшему сотруднику, будут отправляться действующему сотруднику. 
    
- Для переадресации электронной почты учетной записи бывшего сотрудника должна быть назначена лицензия.
    
 > [!IMPORTANT] 
 > Если вы настраиваете переадресацию электронной почты или общий почтовый ящик, в конце не удаляйте учетную запись бывшего сотрудника. Учетная запись должна находиться в этой учетной записи, чтобы привязать пересылку электронной почты или общий почтовый ящик. 

::: moniker range="o365-worldwide"  

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.

2. Выберите имя сотрудника, которого вы хотите заблокировать, а затем перейдите на вкладку **почта** .

3. В разделе **переадресация электронной почты**выберите **Управление переадресацией электронной почты**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Нажмите кнопку **Сохранить**. 
    
6. Помните, что учетную запись бывшего сотрудника удалять не нужно.
 
::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

2. Выберите сотрудника, для которого вы хотите заблокировать и развернуть **Параметры почты**.

3. Рядом с пунктом **переадресация электронной почты**нажмите кнопку **изменить**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Нажмите кнопку **Сохранить**. 
    
6. Помните, что учетную запись бывшего сотрудника удалять не нужно.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.

2. Выберите сотрудника, для которого вы хотите заблокировать и развернуть **Параметры почты**.

3. Рядом с пунктом **переадресация электронной почты**нажмите кнопку **изменить**.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Нажмите кнопку **Сохранить**. 
    
6. Помните, что учетную запись бывшего сотрудника удалять не нужно.

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>Очистка и блокирование мобильного устройства бывшего сотрудника
<a name="bkmk_mobile"> </a>

Если бывший сотрудник пользовался телефоном, принадлежащим компании, вы можете очистить и заблокировать его через Центр администрирования Exchange. Все данные организации будут удалены с устройства, и с него невозможно будет подключиться к Office 365.
  

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.

3. В Центре администрирования Exchange выберите **Получатели** \> **Почтовые ящики**. 
    
4. Выберите пользователя и в разделе **мобильные устройства**выберите **Просмотреть сведения**. 
    
5. На странице " **сведения о мобильном устройстве** " в разделе **мобильные устройства**Выберите мобильное устройство, нажмите кнопку **очистить** ![ устройство очистки данных ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) , а затем выберите пункт **блокировать**. 
    
6. Нажмите кнопку **Сохранить**. 
    
    **Tip**: Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service. You should also disable any Blackberry devices for the user. Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Блокировка доступа бывшего сотрудника к данным Microsoft 365
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > Для вступления в силу блокировки учетной записи может потребоваться до 24 часов. Если необходимо немедленно запретить вход пользователя, необходимо [сбросить пароль](reset-passwords.md) и затем запустить одноразовое событие, которое будет подписывать их из сеансов Microsoft 365 на всех устройствах. Сведения о [выходе!](#sign-out-now)
 

::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.

2. Выберите имя сотрудника, которого вы хотите заблокировать, и под именем пользователя выберите символ для **блокирования этого пользователя**.

3. Выберите **блокировать вход пользователя**и нажмите кнопку **сохранить**. 

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

2. Выберите сотрудника, которого вы хотите заблокировать, а затем выберите пункт **блокировать вход**.

3. Выберите **блокировать вход пользователя**и нажмите кнопку **сохранить**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.

2. Выберите сотрудника, которого вы хотите заблокировать, а затем выберите пункт **блокировать вход**.

3. Выберите **блокировать вход пользователя**и нажмите кнопку **сохранить**. 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Блокировка доступа бывшего сотрудника к электронной почте (Exchange Online)
<a name="bkmk_block_email"> </a>

Если вы используете электронную почту в рамках подписки на Microsoft 365, вам необходимо войти в центр администрирования Exchange, чтобы выполнить указанные ниже действия, чтобы заблокировать доступ к электронной почте бывшим сотрудником.
  

1. Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.
     
2. В Центре администрирования Exchange выберите **Получатели** \> **Почтовые ящики**. 
    
3. Дважды щелкните пользователя и перейдите на страницу **функции почтового ящика** . В разделе **мобильные устройства**выберите **отключить Exchange ACTIVESYNC** и **Отключить OWA для устройств,** а затем ответьте **Да** на приглашение. 
    
4. В разделе **Подключение к электронной почте**выберите **Отключить** и ответьте **Да** по запросу. 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>Удаление и удаление лицензии Microsoft 365 из бывшего сотрудника
<a name="bkmk_remove"> </a>

Поэтому вы не будете платить за лицензию после того, как кто-то покидает вашу организацию, вам нужно удалить лицензию на Microsoft 365 и затем удалить ее из вашей подписки. Если вы не хотите удалять лицензию, ее можно назначить другому пользователю.
  
После освобождения лицензии все данные этого пользователя будут храниться в течение 30 дней. Вы сможете [получить доступ](get-access-to-and-back-up-a-former-user-s-data.md) к данным или [восстановить](restore-user.md) учетную запись, если пользователь вернется. Через 30 дней все данные пользователя (Кроме документов, хранящихся в SharePoint Online) удаляются без возможности восстановления из Microsoft 365 и не могут быть восстановлены. 

::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.

2. Выберите имя сотрудника, которого вы хотите заблокировать, а затем перейдите на вкладку **лицензии и приложения** .

4. Снимите флажки для лицензий, которые нужно удалить, а затем нажмите кнопку **сохранить изменения**.

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

2. Выберите сотрудника, которого вы хотите заблокировать, а затем рядом с пунктом **лицензии на продукты**выберите **изменить**.

3. На странице **лицензии на продукты** отключите лицензии, которые нужно удалить, а затем нажмите кнопку **сохранить**.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.

2. Выберите сотрудника, которого вы хотите заблокировать, а затем рядом с пунктом **лицензии на продукты**выберите **изменить**.

3. На странице **лицензии на продукты** отключите лицензии, которые нужно удалить, а затем нажмите кнопку **сохранить**.

::: moniker-end


**Чтобы уменьшить число оплачиваемых лицензий**, пока вы не наймете другого сотрудника, выполните указанные ниже действия. 

::: moniker range="o365-worldwide"



1. В Центре администрирования перейдите на страницу **Выставление счетов** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ваши продукты</a>.


::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования перейдите на страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Подписки</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования перейдите на страницу **Выставление счетов** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Подписки</a>.

::: moniker-end
    
2. Выберите **Добавить/удалить лицензии** , чтобы удалить лицензию, чтобы она не была оплачена до приема другого человека.

Когда вы [добавите](add-users.md) в свой бизнес другого пользователя, вам будет предложено купить лицензию одновременно с одним действием!
    
Дополнительные сведения об управлении пользовательскими лицензиями для Microsoft 365 для бизнеса приведены в статье [Назначение лицензий пользователям в microsoft 365 для бизнеса](../manage/assign-licenses-to-users.md)и [Удаление лицензий пользователей в Microsoft 365 для бизнеса](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Как удаление учетной записи сотрудника влияет на Skype для бизнеса
<a name="bkmk_remove"> </a>

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue. 
  
## <a name="delete-a-former-employees-user-account"></a>Удаление учетной записи бывшего сотрудника
<a name="bkmk_delete"> </a>

После сохранения всех пользовательских данных бывшего сотрудника и обеспечения доступа к ним вы можете удалить его учетную запись.
  
Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.

::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.

2. Выберите имя сотрудника, которого вы хотите удалить.

3. В разделе Имя пользователя выберите символ для параметра **удалить пользователя**. Выберите нужные параметры для этого пользователя, а затем нажмите кнопку **удалить пользователя**.

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.

2. Выберите имя сотрудника, которого вы хотите удалить.

3. В верхней части страницы выберите **удалить пользователя**. Выберите нужные параметры для этого пользователя, а затем нажмите кнопку **удалить пользователя**.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>.

2. Выберите имя сотрудника, которого вы хотите удалить.

3. В верхней части страницы выберите **удалить пользователя**. Выберите нужные параметры для этого пользователя, а затем нажмите кнопку **удалить пользователя**.

::: moniker-end

When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.
  
### <a name="does-your-organization-use-active-directory"></a>Ваша организация использует Active Directory?

Если ваша организация синхронизирует учетные записи пользователей с Microsoft 365 из локальной среды Active Directory, необходимо удалить и восстановить эти учетные записи пользователей в локальной службе Active Directory. Учетные записи нельзя удалить или восстановить в Office 365.
  
Инструкции по работе с этой статьей: [Удаление учетной записи пользователя](https://go.microsoft.com/fwlink/?linkid=841808).
  
Если вы используете Azure Active Directory, см. статью [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) командлет PowerShell. 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Что нужно знать о завершении почтового сеанса сотрудника
<a name="bkmk_session"> </a>

Ниже описаны способы завершения почтового сеанса сотрудника (Exchange).
  
|||
|:-----|:-----|
|**Возможное действие** <br/> |**Способ выполнения** <br/> |
|Завершение сеанса (например, Outlook в Интернете, Outlook, Exchange Active Sync и т. д.) и принудительное открытие нового сеанса  <br/> |Сброс пароля  <br/> |
|Завершение сеанса и блокировка доступа к будущим сеансам (для всех протоколов)  <br/> |Disable the account. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Завершение сеанса для определенного протокола (например, ActiveSync)  <br/> |Disable the protocol. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
Описанные выше операции можно выполнить в 3 местах.
  
|||
|:-----|:-----|
|**Место завершения сеанса** <br/> |**Длительность операции** <br/> |
|В Центре администрирования Exchange или с помощью PowerShell  <br/> |Ожидаемая задержка составляет менее 30 минут  <br/> |
|В Центре администрирования Azure Active Directory  <br/> |Ожидаемая задержка составляет 60 минут  <br/> |
|В локальной среде  <br/> |Ожидаемая задержка составляет более 3 часов  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>Как добиться быстрого прекращения действия учетной записи

 **Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync. 
  
 **Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync. 
  
## <a name="related-articles"></a>Связанные статьи

[Восстановление пользователя](restore-user.md)
  
