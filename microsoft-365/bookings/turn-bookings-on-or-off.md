---
title: Включение и отключение резервирований Майкрософт
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Узнайте, как получить доступ к книгам Майкрософт в Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126603"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="a10cb-103">Включение и отключение резервирований Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a10cb-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="a10cb-104">Резервирования можно включать и отключать для всей организации или для определенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a10cb-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="a10cb-105">Когда вы включаете резервирование для пользователей, они могут создать страницу резервирования, создать календарь и разрешить другим пользователям заносить время с помощью.</span><span class="sxs-lookup"><span data-stu-id="a10cb-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="a10cb-106">Элементы управления администратора, описанные в этих разделах, недоступны для пользователей Office 365 под управлением 21Vianet (Китай).</span><span class="sxs-lookup"><span data-stu-id="a10cb-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="a10cb-107">Включение и выключение учета для Организации с помощью центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a10cb-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a10cb-108">Войдите в центр администрирования Microsoft 365 в качестве глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="a10cb-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="a10cb-109">В центре администрирования  **перейдите в раздел Параметры**   \> **Организации** и выберите пункт **резервирования**.</span><span class="sxs-lookup"><span data-stu-id="a10cb-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="a10cb-110">Установите флажок, чтобы **Разрешить в Организации использование резервирований** для включения или отключения учета для Организации.</span><span class="sxs-lookup"><span data-stu-id="a10cb-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a10cb-111">Отключение учета приведет к отключению всех обращений к службе, включая создание и управление страницами резервирования.</span><span class="sxs-lookup"><span data-stu-id="a10cb-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="a10cb-112">Нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="a10cb-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="a10cb-113">Включение и выключение учета для Организации с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a10cb-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="a10cb-114">Чтобы включить или отключить резервирование для Организации с помощью командлета PowerShell [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [подключитесь к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a10cb-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="a10cb-115">Включение и выключение учета для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="a10cb-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="a10cb-116">Вы можете отключить резервирование для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a10cb-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="a10cb-117">Перейдите в центр администрирования Microsoft 365 и выберите **Пользователи** \> **Активные пользователи**.</span><span class="sxs-lookup"><span data-stu-id="a10cb-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="a10cb-118">Выберите нужного пользователя, а затем выберите пункт **лицензии и приложения**.</span><span class="sxs-lookup"><span data-stu-id="a10cb-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="a10cb-119">Разверните **приложения** и снимите флажок для резервирований Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a10cb-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="a10cb-120">Требовать утверждения персонала перед предоставлением доступа к сведениям о доступности</span><span class="sxs-lookup"><span data-stu-id="a10cb-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="a10cb-121">Администраторам может потребоваться, чтобы сотрудники Организации могли принять участие в совместном доступе к сведениям о доступности с помощью резервирования и до того, как их можно будет резервируемые с помощью страницы резервирования.</span><span class="sxs-lookup"><span data-stu-id="a10cb-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="a10cb-122">Этот параметр доступен в центре администрирования Microsoft 365 **в разделе Параметры** \> **Settings** \> **учета** параметров.</span><span class="sxs-lookup"><span data-stu-id="a10cb-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="a10cb-123">Если этот параметр включен, сотрудники, добавленные как сотрудники в календарях резервирования, смогут найти ссылку утвердить или отклонить в уведомлении по электронной почте, которые они получают.</span><span class="sxs-lookup"><span data-stu-id="a10cb-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="a10cb-124">Эта функция постепенно выдается всем пользователям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a10cb-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="a10cb-125">Если вы не видите этот параметр в центре администрирования Microsoft 365, вернитесь к началу.</span><span class="sxs-lookup"><span data-stu-id="a10cb-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="a10cb-126">Блокировать параметры общего доступа в социальных сетях</span><span class="sxs-lookup"><span data-stu-id="a10cb-126">Block social sharing options</span></span>

<span data-ttu-id="a10cb-127">Администраторы могут контролировать общий доступ к страницам резервирования в социальных сетях.</span><span class="sxs-lookup"><span data-stu-id="a10cb-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="a10cb-128">Этот параметр доступен в центре администрирования Microsoft 365 **в разделе Параметры** \> **Settings** \> **учета** параметров.</span><span class="sxs-lookup"><span data-stu-id="a10cb-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="a10cb-129">Эта функция постепенно выдается всем пользователям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a10cb-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="a10cb-130">Если вы не видите этот параметр в центре администрирования Microsoft 365, вернитесь к началу.</span><span class="sxs-lookup"><span data-stu-id="a10cb-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="a10cb-131">Разрешить только выбранным пользователям создавать календари учета</span><span class="sxs-lookup"><span data-stu-id="a10cb-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="a10cb-132">С помощью ограничений политики вы можете ограничить лицензированные пользователи от возможности создавать календари учета.</span><span class="sxs-lookup"><span data-stu-id="a10cb-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="a10cb-133">Сначала необходимо включить резервирование для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="a10cb-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="a10cb-134">Все пользователи в организации будут иметь лицензии на резервирование, но только те, которые включены в политику, могут создавать календари резервирования и иметь полный контроль над пользователями, имеющими доступ к создаваемым календарям.</span><span class="sxs-lookup"><span data-stu-id="a10cb-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="a10cb-135">Пользователи, включенные в эту политику, могут создавать новые календари резервирования и могут добавляться как сотрудники в любую мощность (включая роль администратора) к существующим календарям.</span><span class="sxs-lookup"><span data-stu-id="a10cb-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="a10cb-136">Пользователи, которые не включены в эту политику, не смогут создавать новые календари и получать сообщение об ошибке при попытке сделать это.</span><span class="sxs-lookup"><span data-stu-id="a10cb-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="a10cb-137">Вам потребуется выполнить следующие команды с помощью Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a10cb-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="a10cb-138">Дополнительные сведения о выполнении командлетов Exchange Online приведены [в статье подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a10cb-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a10cb-139">В приведенных ниже примерах предполагается, что в Организации не были созданы другие политики почтовых ящиков Outlook Web App (OWA).</span><span class="sxs-lookup"><span data-stu-id="a10cb-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="a10cb-140">Создайте новую политику почтовых ящиков для пользователей, которым необходимо разрешить создавать календари учета.</span><span class="sxs-lookup"><span data-stu-id="a10cb-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="a10cb-141">(По умолчанию новые политики почтовых ящиков по умолчанию разрешено создавать календари.)</span><span class="sxs-lookup"><span data-stu-id="a10cb-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="a10cb-142">Дополнительные сведения см. в статье [New – OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="a10cb-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="a10cb-143">Назначьте эту политику соответствующим пользователям, выполнив эту команду для каждого пользователя, которому необходимо предоставить разрешение на создание календарей учета.</span><span class="sxs-lookup"><span data-stu-id="a10cb-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="a10cb-144">Дополнительные сведения см. в статье [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="a10cb-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="a10cb-145">Необязательно: выполните эту команду, если вы хотите отключить резервирования для всех других пользователей в Организации.</span><span class="sxs-lookup"><span data-stu-id="a10cb-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="a10cb-146">Дополнительные сведения см. в статье [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="a10cb-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="a10cb-147">Для получения дополнительных сведений о политиках почтовых ящиков OWA ознакомьтесь со следующими статьями:</span><span class="sxs-lookup"><span data-stu-id="a10cb-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="a10cb-148">Создание Outlook в политике веб-почтовых ящиков в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a10cb-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="a10cb-149">Применение или удаление политики почтовых ящиков Outlook в Интернете для почтового ящика в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a10cb-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
