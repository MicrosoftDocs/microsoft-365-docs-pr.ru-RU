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
ms.openlocfilehash: 60f4cf6b5c9a0b5dc2023b3ef7b6460685142d07
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244302"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="62882-103">Шаг 1 — запретить бывшему сотруднику войти в систему и заблокировать доступ к Microsoft 365 службам</span><span class="sxs-lookup"><span data-stu-id="62882-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="62882-104">Если необходимо немедленно предотвратить вход пользователя, необходимо сбросить пароль.</span><span class="sxs-lookup"><span data-stu-id="62882-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="62882-105">На этом шаге вынудить пользователя выйти из него Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62882-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

1. <span data-ttu-id="62882-106">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="62882-106">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="62882-107">Выберите поле рядом с именем пользователя, а затем выберите **пароль Reset**.</span><span class="sxs-lookup"><span data-stu-id="62882-107">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="62882-108">Введите новый пароль и выберите **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="62882-108">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="62882-109">(Не отправляйте его им.)</span><span class="sxs-lookup"><span data-stu-id="62882-109">(Don't send it to them.)</span></span>
4. <span data-ttu-id="62882-110">Выберите имя пользователя, чтобы перейти к области свойств, а на вкладке **Учетная** запись выберите **инициировать вход.**</span><span class="sxs-lookup"><span data-stu-id="62882-110">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

<span data-ttu-id="62882-111">В течение часа или после того, как они покидают текущую страницу Microsoft 365 они находятся на - им предложено войти снова.</span><span class="sxs-lookup"><span data-stu-id="62882-111">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="62882-112">Маркер доступа хорош в течение часа, поэтому сроки зависят от того, сколько времени осталось на этом маркере, и от того, будут ли они переходить из текущей веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="62882-112">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="62882-113">Если пользователь находится в Outlook в Интернете, просто щелкнув в почтовом ящике, его могут не выгнать сразу.</span><span class="sxs-lookup"><span data-stu-id="62882-113">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="62882-114">Как только они выбирают другую плитку, например OneDrive или обновляют браузер, инициировался выход.</span><span class="sxs-lookup"><span data-stu-id="62882-114">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="62882-115">Чтобы немедленно использовать PowerShell, чтобы выйти из-под действия пользователя, см. в этой ссылке см. в документе ["Revoke-AzureADUserAllRefreshToken".](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)</span><span class="sxs-lookup"><span data-stu-id="62882-115">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="62882-116">Дополнительные сведения о времени, требуемом для завершения почтового сеанса, см. в разделе [Что нужно знать о завершении почтового сеанса сотрудника](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span><span class="sxs-lookup"><span data-stu-id="62882-116">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="62882-117">Блокировка доступа бывшего сотрудника к Microsoft 365 службам</span><span class="sxs-lookup"><span data-stu-id="62882-117">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="62882-118">Блокировка учетной записи может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="62882-118">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="62882-119">Если необходимо немедленно предотвратить вход пользователя, выполните действия, которые были выше, и сбросйте пароль.</span><span class="sxs-lookup"><span data-stu-id="62882-119">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="62882-120">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="62882-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="62882-121">Выберите имя сотрудника, которого вы хотите заблокировать, и под именем пользователя выберите символ **Block этого пользователя.**</span><span class="sxs-lookup"><span data-stu-id="62882-121">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="62882-122">Выберите **Блок для пользователя при входе,** а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="62882-122">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="62882-123">Блокировка доступа бывшего сотрудника к электронной почте (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="62882-123">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="62882-124">Если у вас есть электронная почта в Microsoft 365 подписки, вопишитесь в центр администрирования Exchange и следуйте этим шагам, чтобы заблокировать доступ к электронной почте своему бывшему сотруднику.</span><span class="sxs-lookup"><span data-stu-id="62882-124">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="62882-125">Перейдите в <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Центр администрирования Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="62882-125">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="62882-126">В Центре администрирования Exchange выберите **Получатели** \> **Почтовые ящики**.</span><span class="sxs-lookup"><span data-stu-id="62882-126">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="62882-127">Дважды щелкните пользователя и перейдите на страницу функций **почтового ящика.**</span><span class="sxs-lookup"><span data-stu-id="62882-127">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="62882-128">В **статье Мобильные устройства** выберите **отключение Exchange ActiveSync** и отключение **OWA** для устройств и ответ **"Да"** на оба запроса.</span><span class="sxs-lookup"><span data-stu-id="62882-128">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="62882-129">В **статье Подключение к электронной почте** выберите **Отключение** и **ответ да** при запросе.</span><span class="sxs-lookup"><span data-stu-id="62882-129">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
