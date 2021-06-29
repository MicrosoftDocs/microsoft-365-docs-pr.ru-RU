---
title: Шаг 1 . Остановить вход сотрудника в систему Microsoft 365
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
description: Блокирование входа в систему бывшего сотрудника и блокировка доступа к Microsoft 365 службам.
ms.openlocfilehash: 58b65a0a886460e8be01635c857433773cfc9059
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177121"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="afe12-103">Шаг 1 — запретить бывшему сотруднику войти в систему и заблокировать доступ к Microsoft 365 службам</span><span class="sxs-lookup"><span data-stu-id="afe12-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="afe12-104">Если необходимо немедленно предотвратить вход пользователя, необходимо сбросить пароль.</span><span class="sxs-lookup"><span data-stu-id="afe12-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="afe12-105">На этом шаге вынудить пользователя выйти из него Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="afe12-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="afe12-106">Чтобы инициировать регистрацию для других администраторов, необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="afe12-106">You need to be a global administrator to initiate sign-out for other administrators.</span></span> <span data-ttu-id="afe12-107">Для выполнения этого действия можно использовать администратора пользователя или пользователя-администратора helpdesk.</span><span class="sxs-lookup"><span data-stu-id="afe12-107">For non administrator users, you can use a User Administrator or a Helpdesk Administrator user to perform this action.</span></span> [<span data-ttu-id="afe12-108">Дополнительные информацию о ролях администратора</span><span class="sxs-lookup"><span data-stu-id="afe12-108">Learn more about the Admin Roles</span></span>](about-admin-roles.md)

1. <span data-ttu-id="afe12-109">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="afe12-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="afe12-110">Выберите поле рядом с именем пользователя, а затем выберите **пароль Reset**.</span><span class="sxs-lookup"><span data-stu-id="afe12-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="afe12-111">Введите новый пароль и выберите **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="afe12-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="afe12-112">(Не отправляйте его им.)</span><span class="sxs-lookup"><span data-stu-id="afe12-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="afe12-113">Выберите имя пользователя, чтобы перейти к области свойств, а на вкладке **Учетная** запись выберите **Sign из всех сеансов.**</span><span class="sxs-lookup"><span data-stu-id="afe12-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Sign out of all sessions**.</span></span>

<span data-ttu-id="afe12-114">В течение часа или после того, как они покидают текущую страницу Microsoft 365 они находятся на - им предложено войти снова.</span><span class="sxs-lookup"><span data-stu-id="afe12-114">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="afe12-115">Маркер доступа хорош в течение часа, поэтому сроки зависят от того, сколько времени осталось на этом маркере, и от того, будут ли они переходить из текущей веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="afe12-115">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="afe12-116">Если пользователь находится в Outlook в Интернете, просто щелкнув в почтовом ящике, его могут не выгнать сразу.</span><span class="sxs-lookup"><span data-stu-id="afe12-116">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="afe12-117">Как только они выбирают другую плитку, например OneDrive или обновляют браузер, инициировался выход.</span><span class="sxs-lookup"><span data-stu-id="afe12-117">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="afe12-118">Чтобы немедленно использовать PowerShell, чтобы выйти из-под действия пользователя, см. в этой ссылке см. в документе ["Revoke-AzureADUserAllRefreshToken".](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)</span><span class="sxs-lookup"><span data-stu-id="afe12-118">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="afe12-119">Дополнительные сведения о времени, требуемом для завершения почтового сеанса, см. в разделе [Что нужно знать о завершении почтового сеанса сотрудника](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span><span class="sxs-lookup"><span data-stu-id="afe12-119">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="afe12-120">Блокировка доступа бывшего сотрудника к Microsoft 365 службам</span><span class="sxs-lookup"><span data-stu-id="afe12-120">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="afe12-121">Блокировка учетной записи может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="afe12-121">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="afe12-122">Если необходимо немедленно предотвратить вход пользователя, выполните действия, которые были выше, и сбросйте пароль.</span><span class="sxs-lookup"><span data-stu-id="afe12-122">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="afe12-123">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="afe12-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="afe12-124">Выберите имя сотрудника, которого вы хотите заблокировать, и под именем пользователя выберите символ **Block этого пользователя.**</span><span class="sxs-lookup"><span data-stu-id="afe12-124">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="afe12-125">Выберите **Блок для пользователя при входе,** а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="afe12-125">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="afe12-126">Блокировка доступа бывшего сотрудника к электронной почте (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="afe12-126">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="afe12-127">Если у вас есть электронная почта в Microsoft 365 подписки, вопишитесь в центр администрирования Exchange и следуйте этим шагам, чтобы заблокировать доступ к электронной почте своему бывшему сотруднику.</span><span class="sxs-lookup"><span data-stu-id="afe12-127">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="afe12-128">Перейдите в <a href="https://admin.exchange.microsoft.com/" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="afe12-128">Go to the <a href="https://admin.exchange.microsoft.com/" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="afe12-129">В Центре администрирования Exchange выберите **Получатели** \> **Почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="afe12-129">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="afe12-130">Дважды щелкните пользователя и перейдите к **управлению настройками приложений** электронной почты в **приложениях электронной почты.**</span><span class="sxs-lookup"><span data-stu-id="afe12-130">Double-click the user and go to **Manage email apps settings** under **Email apps**.</span></span> <span data-ttu-id="afe12-131">**Выключите** ползунок для всех параметров; **Мобильный (Exchange ActiveSync),** **Outlook в Интернете,** **Outlook настольный компьютер (MAPI),** Exchange веб-службы, **POP3** и **IMAP**. </span><span class="sxs-lookup"><span data-stu-id="afe12-131">Turn **Off** the slider for all the options; **Mobile (Exchange ActiveSync)**, **Outlook on the web**, **Outlook desktop (MAPI)**, **Exchange web services**, **POP3**, and **IMAP**.</span></span>
4. <span data-ttu-id="afe12-132">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="afe12-132">Select **Save**.</span></span>
