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
description: Узнайте, как получить доступ к microsoft Bookings в Microsoft 365.
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913770"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="a119b-103">Включение и отключение Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="a119b-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="a119b-104">Бронирование может быть включено или отключено для всей организации или для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a119b-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="a119b-105">При включании резервирования для пользователей они могут создать страницу Bookings, создать календарь и разрешить другим пользователям бронировать время с ними.</span><span class="sxs-lookup"><span data-stu-id="a119b-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="a119b-106">Элементы управления администратора, описанные в этих разделах, недоступны для клиентов Office 365, управляемых 21Vianet (Китай).</span><span class="sxs-lookup"><span data-stu-id="a119b-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="a119b-107">Включить или отключить бронирование для организации с помощью центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a119b-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a119b-108">Вопишитесь в центр администрирования Microsoft 365 в качестве глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="a119b-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="a119b-109">В центре администрирования перейдите в  **параметры**   \> **параметров org и** выберите **Bookings**.</span><span class="sxs-lookup"><span data-stu-id="a119b-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="a119b-110">Выберите почтовый ящик для разрешить вашей организации **использовать Bookings,** чтобы включить или отключить Бронирование для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a119b-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a119b-111">Отключение bookings отключит весь доступ к службе, включая создание и управление страницами Bookings.</span><span class="sxs-lookup"><span data-stu-id="a119b-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="a119b-112">Выберите **Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="a119b-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="a119b-113">Включить или отключить бронирование для организации с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a119b-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="a119b-114">Чтобы включить или отключить бронирование для вашей организации с помощью командлета [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) [PowerShell PowerShell PowerShell,](/powershell/exchange/connect-to-exchange-online-powershell) подключись к Exchange Online PowerShell и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a119b-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="a119b-115">Включить или отключить бронирование для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="a119b-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="a119b-116">Вы можете отключить бронирование для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a119b-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="a119b-117">Перейдите в центр администрирования Microsoft 365, а затем выберите **пользователей Users** \> **Active.**</span><span class="sxs-lookup"><span data-stu-id="a119b-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="a119b-118">Выберите нужного пользователя, а затем выберите **лицензии и приложения.**</span><span class="sxs-lookup"><span data-stu-id="a119b-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="a119b-119">Расширение **приложений** и очистка почтового ящика для Microsoft Bookings.</span><span class="sxs-lookup"><span data-stu-id="a119b-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="a119b-120">Требуются утверждения сотрудников перед обменом бесплатными и занятыми сведениями</span><span class="sxs-lookup"><span data-stu-id="a119b-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="a119b-121">Администраторы могут требовать от сотрудников в их организации сделать выбор до того, как их сведения о доступности будут делиться через Bookings и прежде чем их можно будет забронировать на странице бронирования.</span><span class="sxs-lookup"><span data-stu-id="a119b-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="a119b-122">Этот параметр доступен в центре администрирования Microsoft 365 в соответствии с **настройками** \>  \> **параметров.**</span><span class="sxs-lookup"><span data-stu-id="a119b-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="a119b-123">Когда этот параметр включен, сотрудники, добавленные в качестве сотрудников в календарях бронирования, найдут ссылку Утверждение или Отклонение в получаемом уведомлении электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a119b-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="a119b-124">Эта функция постепенно развертывается по всему миру для клиентов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a119b-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="a119b-125">Если вы не видите этот параметр в центре администрирования Microsoft 365, проверьте это в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="a119b-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="a119b-126">Блокировка параметров социального обмена</span><span class="sxs-lookup"><span data-stu-id="a119b-126">Block social sharing options</span></span>

<span data-ttu-id="a119b-127">Администраторы могут управлять общим доступом к страницам бронирования в социальных сетях.</span><span class="sxs-lookup"><span data-stu-id="a119b-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="a119b-128">Этот параметр доступен в центре администрирования Microsoft 365 в соответствии с **настройками** \>  \> **параметров.**</span><span class="sxs-lookup"><span data-stu-id="a119b-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="a119b-129">Эта функция постепенно развертывается по всему миру для клиентов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a119b-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="a119b-130">Если вы не видите этот параметр в центре администрирования Microsoft 365, проверьте это в ближайшее время.</span><span class="sxs-lookup"><span data-stu-id="a119b-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="a119b-131">Разрешить создавать календари Bookings только выбранным пользователям</span><span class="sxs-lookup"><span data-stu-id="a119b-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="a119b-132">С помощью ограничений политики можно запретить лицензированным пользователям создавать календари бронирований.</span><span class="sxs-lookup"><span data-stu-id="a119b-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="a119b-133">Сначала необходимо включить бронирование для всей организации.</span><span class="sxs-lookup"><span data-stu-id="a119b-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="a119b-134">Все пользователи в вашей организации будут иметь лицензии Bookings, но только те, которые включены в политику, могут создавать календари bookings и иметь полный контроль над тем, кто может получить доступ к создамым календарям.</span><span class="sxs-lookup"><span data-stu-id="a119b-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="a119b-135">Пользователи, включенные в эту политику, могут создавать новые календари резервирования и добавляться в качестве персонала в любом качестве (включая роль администратора) в существующие календари bookings.</span><span class="sxs-lookup"><span data-stu-id="a119b-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="a119b-136">Пользователи, не включенные в эту политику, не смогут создавать новые календари резервирования и получат сообщение об ошибке, если они попытаются это сделать.</span><span class="sxs-lookup"><span data-stu-id="a119b-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="a119b-137">Вам потребуется выполнить следующие команды с помощью Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a119b-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="a119b-138">Дополнительные сведения о запуске комлетов Exchange Online см. в рублях [Connect to Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="a119b-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a119b-139">Ниже приведены действия, которые предполагают, что Outlook Web App почтовых ящиков в вашей организации не были созданы никакие другие политики почтовых ящиков Outlook Web App OWA.</span><span class="sxs-lookup"><span data-stu-id="a119b-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="a119b-140">Создайте новую политику почтовых ящиков для пользователей, которые должны иметь право создавать календари бронирований.</span><span class="sxs-lookup"><span data-stu-id="a119b-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="a119b-141">(Создание календаря резервирования по умолчанию разрешено новыми политиками почтовых ящиков.)</span><span class="sxs-lookup"><span data-stu-id="a119b-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="a119b-142">Дополнительные сведения см. [в сообщении New-OwaMailboxPolicy.](/powershell/module/exchange/new-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="a119b-142">For more information, see [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="a119b-143">Назначьте эту политику соответствующим пользователям, запуская эту команду для каждого пользователя, который должен предоставить разрешение на создание календарей bookings.</span><span class="sxs-lookup"><span data-stu-id="a119b-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="a119b-144">Дополнительные сведения см. в статье [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="a119b-144">For more information, see [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="a119b-145">Необязательный вариант: запустите эту команду, если вы хотите отключить Bookings для всех остальных пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a119b-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="a119b-146">Дополнительные сведения см. в статье [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="a119b-146">For more information, see [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="a119b-147">Дополнительные сведения о политиках почтовых ящиков OWA можно узнать по следующим темам:</span><span class="sxs-lookup"><span data-stu-id="a119b-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="a119b-148">Создание Outlook для политики веб-почтовых ящиков в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a119b-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="a119b-149">Применить или удалить Outlook в политике веб-почтовых ящиков на почтовом ящике в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a119b-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)