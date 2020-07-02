---
title: Изменение имени пользователя и адреса электронной почты
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb5ac074-e203-4e1f-9843-b9d1a3e03297
description: 'Узнайте, как глобальный администратор может изменить адрес электронной почты и отображаемое имя. '
ms.openlocfilehash: 0c94114a50ce369ffb809e8f41060994f635a36c
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936531"
---
# <a name="change-a-user-name-and-email-address"></a>Изменение имени пользователя и адреса электронной почты

Изменение адреса электронной почты и отображаемого имени пользователя может потребоваться, например, если этот пользователь сменил фамилию при вступлении в брак.

Просмотрите короткий видеоролик о том, как менять адрес электронной почты пользователя. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1SJuc] 

Если этот видеоролик помог вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="change-a-users-email-address"></a>Изменение адреса электронной почты пользователя

Эти действия может выполнять только [глобальный администратор](about-admin-roles.md). 

::: moniker range="o365-worldwide"
 
1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.
    
2. Выберите имя пользователя, а затем на вкладке **Учетная запись** выберите **Управление именем пользователя**.
    
3. В первом поле введите первую часть нового адреса электронной почты. Если вы добавили в Office 365 собственный домен, его можно выбрать для нового псевдонима в раскрывающемся списке. 

4. Нажмите кнопку **Сохранить изменения**.

   
::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.  

2. Выберите пользователя. Во всплывающей панели рядом с пунктом **Имя пользователя / электронная почта**выберите **Изменить**.

3. В первом поле введите первую часть нового адреса электронной почты. Если вы добавили в Office 365 собственный домен, его можно выбрать для нового псевдонима в раскрывающемся списке.

4. Нажмите кнопку **Сохранить**.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>. 

2. Выберите пользователя. Во всплывающей панели рядом с пунктом **Имя пользователя / электронная почта**выберите **Изменить**.

3. В первом поле введите первую часть нового адреса электронной почты. Если вы добавили в Office 365 собственный домен, его можно выбрать для нового псевдонима в раскрывающемся списке.

4. Нажмите кнопку **Сохранить**.

::: moniker-end

**ВНИМАНИЕ**! Если появляется сообщение об ошибке, см. статью [Устранение сообщений об ошибках](#resolve-error-messages).

## <a name="set-the-primary-email-address"></a>Настройка основного адреса электронной почты пользователя

::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.
    
2. Выберите имя пользователя, а затем на вкладке **Учетная запись** выберите **Управление псевдонимами электронной почты**.

3. Выберите параметр **Сделать основным** для адреса электронной почты, который необходимо установить основным адресом электронной почты для этого пользователя. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Кроме того, этот параметр отображается только для глобального администратора. Если вы не видите его, это означает, что у вас нет разрешения на изменение имени пользователя и его основного адреса электронной почты.
  
4. Вы увидите большое желтое предупреждение о том, что будут изменены данные для входа пользователя. Нажмите кнопку **Сохранить**, а затем — **Закрыть**.
    
5. Сообщите пользователю следующие данные:
 
  - Это изменение может занять некоторое время.
  
  - Their new username. They'll need it to sign in to Microsoft 365.
    
  - Если он пользуется Skype для бизнеса online, ему потребуется перепланировать все свои организованные собрания в Skype для бизнеса online, а также попросить своих внешних контактов обновить его контактные данные.

  - Если они используют OneDrive, URL-адрес этого расположения будет изменен. Если у них есть записные книжки OneNote на OneDrive,то им может потребоваться закрыть и повторно открыть их в OneNote. Если они открыли общий доступ к файлам из своего OneDrive, то ссылки на файлы могут не работать и пользователь сможет повторно открыть к ним общий доступ.    
  
  - Если пароль пользователя тоже изменился, ему потребуется ввести новый пароль на мобильном устройстве, иначе не будет выполнена синхронизация.
  
::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.  

2. Выберите пользователя. Во всплывающей панели рядом с пунктом **Имя пользователя / электронная почта**выберите **Изменить**.

3. Выберите параметр **Сделать основным** для адреса электронной почты, который необходимо установить основным адресом электронной почты для этого пользователя. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Кроме того, этот параметр отображается только для глобального администратора. Если вы не видите его, это означает, что у вас нет разрешения на изменение имени пользователя и его основного адреса электронной почты.
  
4. Вы увидите большое желтое предупреждение о том, что будут изменены данные для входа пользователя. Нажмите кнопку **Сохранить**, а затем — **Закрыть**.
    
5. Сообщите пользователю следующие данные:
 
  - Для вступления в силу этого изменения может потребоваться время.
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - Если он пользуется Skype для бизнеса online, сообщите, что ему потребуется перепланировать все свои организованные собрания в Skype для бизнеса online, а также попросить своих внешних контактов обновить его контактные данные.

  - Если они используют OneDrive, сообщите им, что URL-адрес этого расположения изменен. Если у них есть записные книжки OneNote на OneDrive,то им может потребоваться закрыть и повторно открыть их в OneNote. Если они открыли общий доступ к файлам из своего OneDrive, то ссылки на файлы могут не работать и пользователь сможет повторно открыть к ним общий доступ.    
  
  - Если пароль пользователя тоже изменился, сообщите, что ему потребуется ввести новый пароль на мобильном устройстве, иначе не будет выполнена синхронизация.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>. 

2. Выберите пользователя. Во всплывающей панели рядом с пунктом **Имя пользователя / электронная почта**выберите **Изменить**.

3. Выберите параметр **Сделать основным** для адреса электронной почты, который необходимо установить основным адресом электронной почты для этого пользователя. 
    
    **IMPORTANT**: You won't see this option to Set as Primary if you purchased Office 365 from GoDaddy or another Partner service that provides a management console. Instead, sign in to the GoDaddy / partner's management console to set the primary alias. 
    
    Кроме того, этот параметр отображается только для глобального администратора. Если вы не видите его, это означает, что у вас нет разрешения на изменение имени пользователя и его основного адреса электронной почты.
  
4. Вы увидите большое желтое предупреждение о том, что будут изменены данные для входа пользователя. Нажмите кнопку **Сохранить**, а затем — **Закрыть**.
    
5. Сообщите пользователю следующие данные:
 
  - Для вступления в силу этого изменения может потребоваться время.
  
  - What their new username is. They'll need it to sign in to Office 365.
    
  - Если он пользуется Skype для бизнеса online, сообщите, что ему потребуется перепланировать все свои организованные собрания в Skype для бизнеса online, а также попросить своих внешних контактов обновить его контактные данные.

  - Если они используют OneDrive, сообщите им, что URL-адрес этого расположения изменен. Если у них есть записные книжки OneNote на OneDrive,то им может потребоваться закрыть и повторно открыть их в OneNote. Если они открыли общий доступ к файлам из своего OneDrive, то ссылки на файлы могут не работать и пользователь сможет повторно открыть к ним общий доступ.    
  
  - Если пароль пользователя тоже изменился, сообщите, что ему потребуется ввести новый пароль на мобильном устройстве, иначе не будет выполнена синхронизация.

::: moniker-end
  
## <a name="change-a-users-display-name"></a>Изменение отображаемого имени пользователя

::: moniker range="o365-worldwide"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.

2. Выберите имя пользователя, а затем на вкладке **Учетная запись** выберите **Управление контактными данными**.

3. В поле **Отображаемое имя** введите новое имя и нажмите кнопку **Сохранить**.

    При отображении сообщения об ошибке "**Не удалось изменить пользователя. Проверьте сведения о пользователе и повторите попытку**" см. статью [Устранение сообщений об ошибке](#resolve-error-messages).

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username.

::: moniker-end

::: moniker range="o365-germany"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Активные пользователи</a>.  

2. Выберите пользователя. Во всплывающей панели рядом с пунктом **Контактная информация**выберите **Изменить**.

3. В поле **Отображаемое имя** введите новое имя и нажмите кнопку **Сохранить**.

    При отображении сообщения об ошибке "**Не удалось изменить пользователя. Проверьте сведения о пользователе и повторите попытку**" см. статью [Устранение сообщений об ошибке](#resolve-error-messages).

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

::: moniker range="o365-21vianet"

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Активные пользователи</a>. 

2. Выберите пользователя. Во всплывающей панели рядом с пунктом **Контактная информация**выберите **Изменить**.

3. В поле **Отображаемое имя** введите новое имя и нажмите кнопку **Сохранить**.

    При отображении сообщения об ошибке "**Не удалось изменить пользователя. Проверьте сведения о пользователе и повторите попытку**" см. статью [Устранение сообщений об ошибке](#resolve-error-messages).

It might take up to 24 hours for this change to take effect across all services. After the change has taken effect, the person will have to sign in to Outlook, Skype for Business and SharePoint with their updated username, so be sure to tell them about this change.

::: moniker-end

## <a name="resolve-error-messages"></a>Устранение сообщений об ошибке

### <a name="a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"Не удается найти параметр, соответствующий имени параметра EmailAddresses"

If you get the error message " **A parameter cannot be found that matches parameter name 'EmailAddresses**" it means that it's taking a bit longer to finish setting up your tenant, or your custom domain if you recently added one. The setup process can take up to 4 hours to complete. Wait a while so the set up process has time to finish, and then try again. If the problem persists, call [support](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products) and ask them to do a full sync for you.
  
### <a name="were-sorry-the-user-couldnt-be-edited-review-the-user-information-and-try-again"></a>"Не удалось изменить пользователя. Проверьте сведения о пользователе и повторите попытку"

При отображении сообщения об ошибке "**Не удалось изменить пользователя. Проверьте сведения о пользователе и повторите попытку**." Это означает, что вы не являетесь глобальным администратором и у вас нет разрешений на изменение имени пользователя. Найдите глобального администратора и попросите его внести это изменение.


## <a name="what-to-do-with-old-email-addresses"></a>Что делать с устаревшими адресами электронной почты

A person's previous primary email address is retained as an additional email address. **We strongly recommend that you don't remove the old email address.**
  
Some people might continue to send email to the person's old email address and deleting it may result in NDR failures. Microsoft automatically routes it to the new one. Also, do not reuse old SMTP email addresses and apply them to new accounts. This can also cause NDR failures or delivery to an unintended mailbox.
   
## <a name="what-if-the-persons-offline-address-book-wont-sync-with-the-global-address-list"></a>Что делать, если автономная адресная книга пользователя не синхронизируется с глобальным списком адресов?

If they are using Exchange Online or if their account is linked with your organization's on-premises Exchange environment, you might see this error when you try to change a username and email address: "This user is synchronized with your local Active Directory. Some details can be edited only through your local Active Directory."
  
This is due to the Microsoft Online Email Routing Address (MOERA). The MOERA is constructed from the person's  _userPrincipalName_ attribute in Active Directory and is automatically assigned to the cloud account during the initial sync and once created, it cannot be modified or removed in Office 365. You can subsequently change the username in the Active Directory, but it doesn't change the MOERA and you may run into issues displaying the newly changed name in the Global Address List. 
  
Чтобы это исправить, войдите в [Модуль Azure Active Directory для PowerShell]( https://go.microsoft.com/fwlink/?LinkId=823193) с учетными данными администратора Microsoft 365 и используйте следующий синтаксис: 
  
```powershell
Set-MsolUserPrincipalName -UserPrincipalName anne.wallace@contoso.onmicrosoft.com -NewUserPrincipalName anne.jones@contoso.com
```

> [!TIP]
> Это меняет атрибут **userPrincipalName** пользователя и никак не влияет на его адрес маршрутизации электронной почты Microsoft Online (MOERA). Однако лучше всего, когда имя участника-пользователя для входа совпадает с его основным SMTP-адресом. 
  
О том, как изменить имя пользователя в Active Directory в Windows Server 2003 и более ранних версиях, можно узнать в статье [Переименование учетной записи пользователя](https://go.microsoft.com/fwlink/?LinkId=809091).
  
## <a name="related-articles"></a>Связанные статьи

[Для администраторов: сброс пароля для одного или нескольких пользователей](reset-passwords.md)
  
[Добавление еще одного адреса электронной почты для пользователя](../email/add-another-email-alias-for-a-user.md)
