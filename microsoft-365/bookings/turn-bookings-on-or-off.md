---
title: Включение и отключение Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Узнайте, как получить доступ к Microsoft Bookings в Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126603"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="4e2de-103">Включение и отключение Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="4e2de-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="4e2de-104">Bookings можно отключить или отключить для всей организации или для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e2de-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="4e2de-105">Если вы включите Bookings для пользователей, они смогут создать страницу Bookings, создать календарь и разрешить другим пользователям резервировать время.</span><span class="sxs-lookup"><span data-stu-id="4e2de-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="4e2de-106">Средства администрирования, описанные в этих разделах, недоступны для клиентов Office 365 под управлением 21Vianet (Китай).</span><span class="sxs-lookup"><span data-stu-id="4e2de-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="4e2de-107">Включите или отключите Bookings для своей организации с помощью Центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4e2de-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="4e2de-108">Во sign in to the Microsoft 365 admin center as a global admin.</span><span class="sxs-lookup"><span data-stu-id="4e2de-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="4e2de-109">В Центре администрирования перейдите в  **"Параметры**   \> **организации"** и выберите **Bookings.**</span><span class="sxs-lookup"><span data-stu-id="4e2de-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="4e2de-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span><span class="sxs-lookup"><span data-stu-id="4e2de-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4e2de-111">Отключение Bookings отключит весь доступ к службе, включая создание страниц Bookings и управление ими.</span><span class="sxs-lookup"><span data-stu-id="4e2de-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="4e2de-112">Выберите **"Сохранить изменения"**.</span><span class="sxs-lookup"><span data-stu-id="4e2de-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="4e2de-113">Включите или отключите Bookings для своей организации с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e2de-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="4e2de-114">Чтобы включить или отключить Bookings для вашей организации с помощью командлета [PowerShell Set-OrganizationConfig,](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)подключите к [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4e2de-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="4e2de-115">Включить или отключить Bookings для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="4e2de-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="4e2de-116">Вы можете отключить Bookings для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e2de-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="4e2de-117">Перейдите в Центр администрирования Microsoft 365 и выберите **"Активные** \> **пользователи".**</span><span class="sxs-lookup"><span data-stu-id="4e2de-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="4e2de-118">Выберите нужного пользователя, а затем выберите **"Лицензии и приложения".**</span><span class="sxs-lookup"><span data-stu-id="4e2de-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="4e2de-119">Раз **развернуть приложения** и очистить этот контрольный список для Microsoft Bookings.</span><span class="sxs-lookup"><span data-stu-id="4e2de-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="4e2de-120">Требовать утверждения персонала перед обменом сведениями о занятости</span><span class="sxs-lookup"><span data-stu-id="4e2de-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="4e2de-121">Администраторы могут требовать от сотрудников своей организации получения доступа до того, как их сведения о доступности будут делиться через Bookings, и прежде чем их можно будет бронировать на странице резервирования.</span><span class="sxs-lookup"><span data-stu-id="4e2de-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="4e2de-122">Этот параметр доступен в Центре администрирования Microsoft 365 **в** параметрах \>  \> **Bookings.**</span><span class="sxs-lookup"><span data-stu-id="4e2de-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="4e2de-123">Если этот параметр включен, сотрудники, добавленные в качестве сотрудников в календарях резервирования, будут находить ссылку "Утвердить или отклонить" в уведомлении по электронной почте, которое они получают.</span><span class="sxs-lookup"><span data-stu-id="4e2de-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="4e2de-124">Эта функция постепенно развертывается по всему миру для пользователей Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e2de-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="4e2de-125">Если вы не видите этот параметр в Центре администрирования Microsoft 365, проверьте это в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="4e2de-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="4e2de-126">Блокировка параметров социального общего доступа</span><span class="sxs-lookup"><span data-stu-id="4e2de-126">Block social sharing options</span></span>

<span data-ttu-id="4e2de-127">Администраторы могут управлять общим доступом к страницам резервирования в социальных сетях.</span><span class="sxs-lookup"><span data-stu-id="4e2de-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="4e2de-128">Этот параметр доступен в Центре администрирования Microsoft 365 **в** параметрах \>  \> **Bookings.**</span><span class="sxs-lookup"><span data-stu-id="4e2de-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="4e2de-129">Эта функция постепенно развертывается по всему миру для пользователей Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e2de-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="4e2de-130">Если вы не видите этот параметр в Центре администрирования Microsoft 365, проверьте это в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="4e2de-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="4e2de-131">Разрешить только выбранным пользователям создавать календари Bookings</span><span class="sxs-lookup"><span data-stu-id="4e2de-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="4e2de-132">С помощью ограничений политики вы можете запретить лицензированным пользователям создавать календари Bookings.</span><span class="sxs-lookup"><span data-stu-id="4e2de-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="4e2de-133">Сначала необходимо включить Bookings для всей организации.</span><span class="sxs-lookup"><span data-stu-id="4e2de-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="4e2de-134">Все пользователи в вашей организации будут иметь лицензии Bookings, но только пользователи, включенные в политику, могут создавать календари Bookings и иметь полный контроль над доступом к календарям, которые они создают.</span><span class="sxs-lookup"><span data-stu-id="4e2de-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="4e2de-135">Пользователи, включенные в эту политику, могут создавать новые календари Bookings и добавляться в качестве персонала в любой емкости (включая роль администратора) в существующие календари Bookings.</span><span class="sxs-lookup"><span data-stu-id="4e2de-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="4e2de-136">Пользователи, не включенные в эту политику, не смогут создавать новые календари Bookings и получат сообщение об ошибке при попытке сделать это.</span><span class="sxs-lookup"><span data-stu-id="4e2de-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="4e2de-137">Вам потребуется выполнить следующие команды с помощью Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e2de-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="4e2de-138">Дополнительные сведения о запуске exchange Online см. в подключении [к Exchange Online PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="4e2de-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e2de-139">В шагах ниже предполагается, что в Outlook Web App почтовых ящиков (OWA) не были созданы другие политики почтовых ящиков OWA.</span><span class="sxs-lookup"><span data-stu-id="4e2de-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="4e2de-140">Создайте новую политику почтовых ящиков для пользователей, которые должны иметь возможность создавать календари Bookings.</span><span class="sxs-lookup"><span data-stu-id="4e2de-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="4e2de-141">(Создание календаря Bookings по умолчанию разрешено новыми политиками почтовых ящиков.)</span><span class="sxs-lookup"><span data-stu-id="4e2de-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="4e2de-142">Дополнительные сведения см. в [записи New-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="4e2de-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="4e2de-143">Назначьте эту политику соответствующим пользователям, выировав эту команду для каждого пользователя, который должен предоставить разрешение на создание календарей Bookings.</span><span class="sxs-lookup"><span data-stu-id="4e2de-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="4e2de-144">Дополнительные сведения см. в статье [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="4e2de-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="4e2de-145">Необязательно: если вы хотите отключить Bookings для всех остальных пользователей в вашей организации, запустите эту команду.</span><span class="sxs-lookup"><span data-stu-id="4e2de-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="4e2de-146">Дополнительные сведения см. в статье [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="4e2de-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="4e2de-147">Дополнительные сведения о политиках почтовых ящиков OWA можно узнать в следующих темах:</span><span class="sxs-lookup"><span data-stu-id="4e2de-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="4e2de-148">Создание политики почтовых ящиков Outlook в Интернете в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4e2de-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="4e2de-149">Применение или удаление политики почтовых ящиков Outlook в Интернете для почтового ящика в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4e2de-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
