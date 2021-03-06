---
title: Шаг 7 . Удаление учетной записи пользователя бывшего сотрудника
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
description: Выполните следующие действия, чтобы удалить учетную запись пользователя бывшего сотрудника.
ms.openlocfilehash: e2e1b234eaee3818321761af8f737bad8d131b62
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286327"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>Шаг 7 . Удаление учетной записи пользователя бывшего сотрудника

После сохранения всех пользовательских данных бывшего сотрудника и обеспечения доступа к ним вы можете удалить его учетную запись.

> [!IMPORTANT]
> Не удаляйте учетную запись, если вы настроили для нее переадресацию электронной почты или преобразовали ее в общий почтовый ящик. Она потребуется для привязки переадресации или общего почтового ящика.

1. В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.
2. Выберите имя сотрудника, которого необходимо удалить.
3. Под именем пользователя выберите **Удалить пользователя**. Выберите параметры, которые вы хотите для этого пользователя, а затем выберите **Удалить пользователя**. Если вы уже предоставили другому пользователю доступ к электронной почте и OneDrive этого пользователя, вам не придется делать это снова здесь.

После удаления пользователя его учетная запись становится неактивной на около 30 дней. Вы можете восстановить ее в течение этого срока.

## <a name="watch-delete-a-former-employees-user-account"></a>Watch: Delete a former employee's user account

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

Если этот видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](../../business-video/index.yml).

## <a name="does-your-organization-use-active-directory"></a>Ваша организация использует Active Directory?

Если ваша организация синхронизирует учетные записи пользователей Microsoft 365 из локальной среды Active Directory, необходимо удалить и восстановить эти учетные записи пользователей в локальной службе Active Directory. Учетные записи нельзя удалить или восстановить в Office 365.

Подробнее об удалении и восстановлении учетной записи пользователя в Active Directory см. в публикации [Delete a User Account.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))
  
Если вы используете Azure Active Directory, см. в рубке [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell.
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Что нужно знать о завершении почтового сеанса сотрудника

Ниже описаны способы завершения почтового сеанса сотрудника (Exchange).

<br>

****

|Возможное действие|Способ выполнения|
|:-----|:-----|
|Завершение сеанса (например, Outlook в Интернете, Outlook, Exchange Active Sync и т. д.) и принудительное открытие нового сеанса|Сброс пароля|
|Завершение сеанса и блокировка доступа к будущим сеансам (для всех протоколов)|Отключение учетной записи. Например, (в центре администрирования Exchange или с помощью PowerShell): <p>  `Set-Mailbox user@contoso.com -AccountDisabled:$true`|
|Завершение сеанса для определенного протокола (например, ActiveSync)|Отключение протокола. Например, (в центре администрирования Exchange или с помощью PowerShell): <p>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false`|
|

Вышеперечисленные операции можно сделать в трех местах:
  
<br>

****

|Место завершения сеанса|Длительность операции|
|---|---|
|В Центре администрирования Exchange или с помощью PowerShell|Ожидаемая задержка составляет менее 30 минут|
|В Центре администрирования Azure Active Directory|Ожидаемая задержка составляет 60 минут|
|В локальной среде|Ожидаемая задержка составляет более 3 часов|
|

### <a name="how-to-get-fastest-response-for-account-termination"></a>Как добиться быстрого прекращения действия учетной записи

**Самый быстрый способ.** Используйте Центр администрирования Exchange (используйте PowerShell) или Центр администрирования Azure Active Directory. В локальной среде синхронизация изменений с помощью DirSync может занять несколько часов.
  
**Самый быстрый способ для пользователя, присутствующего в локальной среде и в центре обработки данных Exchange.** Завершите сеанс с помощью Центра администрирования Azure Active Directory или Центра администрирования Exchange И внесите это изменение в локальной среде. В противном случае изменение, внесенное в Центре администрирования Azure Active Directory или Центре администрирования Exchange, будет перезаписано средством DirSync.
  
## <a name="related-content"></a>Связанные материалы

[Восстановление паролей](restore-user.md) пользователя (статья)/ [Сброс паролей](reset-passwords.md) (статья)
