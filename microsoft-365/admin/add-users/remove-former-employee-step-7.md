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
ms.openlocfilehash: 0afa9b112919d2668d7553ac5bcf08e664bc1749
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244291"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="3776e-103">Шаг 7 . Удаление учетной записи пользователя бывшего сотрудника</span><span class="sxs-lookup"><span data-stu-id="3776e-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="3776e-104">После сохранения всех пользовательских данных бывшего сотрудника и обеспечения доступа к ним вы можете удалить его учетную запись.</span><span class="sxs-lookup"><span data-stu-id="3776e-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3776e-p101">Не удаляйте учетную запись, если вы настроили для нее переадресацию электронной почты или преобразовали ее в общий почтовый ящик. Она потребуется для привязки переадресации или общего почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="3776e-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="3776e-107">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="3776e-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="3776e-108">Выберите имя сотрудника, которого необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="3776e-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="3776e-109">Под именем пользователя выберите **Удалить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="3776e-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="3776e-110">Выберите параметры, которые вы хотите для этого пользователя, а затем выберите **Удалить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="3776e-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="3776e-111">Если вы уже предоставили другому пользователю доступ к электронной почте и OneDrive этого пользователя, вам не придется делать это снова здесь.</span><span class="sxs-lookup"><span data-stu-id="3776e-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="3776e-p103">После удаления пользователя его учетная запись становится неактивной на около 30 дней. Вы можете восстановить ее в течение этого срока.</span><span class="sxs-lookup"><span data-stu-id="3776e-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>
  
## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="3776e-114">Ваша организация использует Active Directory?</span><span class="sxs-lookup"><span data-stu-id="3776e-114">Does your organization use Active Directory?</span></span>

<span data-ttu-id="3776e-115">Если ваша организация синхронизирует учетные записи пользователей Microsoft 365 из локальной среды Active Directory, необходимо удалить и восстановить эти учетные записи пользователей в локальной службе Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3776e-115">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="3776e-116">Учетные записи нельзя удалить или восстановить в Office 365.</span><span class="sxs-lookup"><span data-stu-id="3776e-116">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="3776e-117">Подробнее об удалении и восстановлении учетной записи пользователя в Active Directory см. в публикации [Delete a User Account.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="3776e-117">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="3776e-118">Если вы используете Azure Active Directory, см. в рубке [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3776e-118">If you're using Azure Active Directory, see the [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="3776e-119">Что нужно знать о завершении почтового сеанса сотрудника</span><span class="sxs-lookup"><span data-stu-id="3776e-119">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="3776e-120">Ниже описаны способы завершения почтового сеанса сотрудника (Exchange).</span><span class="sxs-lookup"><span data-stu-id="3776e-120">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3776e-121">**Возможное действие**</span><span class="sxs-lookup"><span data-stu-id="3776e-121">**What you can do**</span></span> <br/> |<span data-ttu-id="3776e-122">**Способ выполнения**</span><span class="sxs-lookup"><span data-stu-id="3776e-122">**How you do it**</span></span> <br/> |
|<span data-ttu-id="3776e-123">Завершение сеанса (например, Outlook в Интернете, Outlook, Exchange Active Sync и т. д.) и принудительное открытие нового сеанса</span><span class="sxs-lookup"><span data-stu-id="3776e-123">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="3776e-124">Сброс пароля</span><span class="sxs-lookup"><span data-stu-id="3776e-124">Reset password</span></span>  <br/> |
|<span data-ttu-id="3776e-125">Завершение сеанса и блокировка доступа к будущим сеансам (для всех протоколов)</span><span class="sxs-lookup"><span data-stu-id="3776e-125">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="3776e-126">Отключение учетной записи.</span><span class="sxs-lookup"><span data-stu-id="3776e-126">Disable the account.</span></span> <span data-ttu-id="3776e-127">Например, (в центре администрирования Exchange или с помощью PowerShell):</span><span class="sxs-lookup"><span data-stu-id="3776e-127">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="3776e-128">Завершение сеанса для определенного протокола (например, ActiveSync)</span><span class="sxs-lookup"><span data-stu-id="3776e-128">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="3776e-129">Отключение протокола.</span><span class="sxs-lookup"><span data-stu-id="3776e-129">Disable the protocol.</span></span> <span data-ttu-id="3776e-130">Например, (в центре администрирования Exchange или с помощью PowerShell):</span><span class="sxs-lookup"><span data-stu-id="3776e-130">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="3776e-131">Вышеперечисленные операции можно сделать в трех местах:</span><span class="sxs-lookup"><span data-stu-id="3776e-131">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3776e-132">**Место завершения сеанса**</span><span class="sxs-lookup"><span data-stu-id="3776e-132">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="3776e-133">**Длительность операции**</span><span class="sxs-lookup"><span data-stu-id="3776e-133">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="3776e-134">В Центре администрирования Exchange или с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="3776e-134">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="3776e-135">Ожидаемая задержка составляет менее 30 минут</span><span class="sxs-lookup"><span data-stu-id="3776e-135">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="3776e-136">В Центре администрирования Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3776e-136">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="3776e-137">Ожидаемая задержка составляет 60 минут</span><span class="sxs-lookup"><span data-stu-id="3776e-137">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="3776e-138">В локальной среде</span><span class="sxs-lookup"><span data-stu-id="3776e-138">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="3776e-139">Ожидаемая задержка составляет более 3 часов</span><span class="sxs-lookup"><span data-stu-id="3776e-139">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="3776e-140">Как добиться быстрого прекращения действия учетной записи</span><span class="sxs-lookup"><span data-stu-id="3776e-140">How to get fastest response for account termination</span></span>

 <span data-ttu-id="3776e-p107">**Самый быстрый способ.** Используйте Центр администрирования Exchange (используйте PowerShell) или Центр администрирования Azure Active Directory. В локальной среде синхронизация изменений с помощью DirSync может занять несколько часов.</span><span class="sxs-lookup"><span data-stu-id="3776e-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="3776e-p108">**Самый быстрый способ для пользователя, присутствующего в локальной среде и в центре обработки данных Exchange.** Завершите сеанс с помощью Центра администрирования Azure Active Directory или Центра администрирования Exchange И внесите это изменение в локальной среде. В противном случае изменение, внесенное в Центре администрирования Azure Active Directory или Центре администрирования Exchange, будет перезаписано средством DirSync.</span><span class="sxs-lookup"><span data-stu-id="3776e-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="3776e-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3776e-145">Related articles</span></span>

[<span data-ttu-id="3776e-146">Восстановление пользователя</span><span class="sxs-lookup"><span data-stu-id="3776e-146">Restore a user</span></span>](restore-user.md)
