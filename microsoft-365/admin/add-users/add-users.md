---
title: Добавление пользователей по отдельности или в пакетном режиме
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: Узнайте, как добавлять пользователей в Microsoft 365 один раз в один раз или нескольких пользователей из CSV-файла.
ms.openlocfilehash: 6d7a9d97d4cca25bac6579ea4427136351110658
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049475"
---
# <a name="add-users-individually-or-in-bulk"></a><span data-ttu-id="8c0ad-103">Добавление пользователей по отдельности или в пакетном режиме</span><span class="sxs-lookup"><span data-stu-id="8c0ad-103">Add users individually or in bulk</span></span>

<span data-ttu-id="8c0ad-104">Пользователям в вашей группе требуется учетная запись пользователя, прежде чем она сможет войти в систему и получить доступ к [Microsoft 365 для бизнеса](https://go.microsoft.com/fwlink/?LinkID=519395).</span><span class="sxs-lookup"><span data-stu-id="8c0ad-104">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="8c0ad-105">Самый простой способ добавить учетные записи пользователей — добавить их по одной в центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8c0ad-106">После выполнения этого действия пользователям будут назначены лицензии Microsoft 365, учетные данные входа и почтовые ящики Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-106">After you do this step, your users will have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="8c0ad-107">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="8c0ad-108">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="8c0ad-109">Перейдите к разделу **Активные пользователи** **пользователей** > и выберите **Добавить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-109">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="8c0ad-110">В области **Настройка основных** сведений введите следующие сведения, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-110">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="8c0ad-111">**Name (имя** ) Заполните поля имя, фамилия, отображаемое имя и имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-111">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="8c0ad-112">**Domain (домен** ) Например, если имя пользователя пользователя — Жакоб, а его домен — contoso.com, он выполнит вход, введя jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-112">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="8c0ad-113">**Параметры паролей** Выберите параметр использовать автоматически созданный пароль или создайте для пользователя свой надежный пароль.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-113">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="8c0ad-114">Пользователю необходимо будет сменить пароль через 90 дней.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-114">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="8c0ad-115">Кроме того, вы можете указать, что **этот пользователь должен изменить пароль при первом входе в систему**.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-115">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="8c0ad-116">Укажите, хотите ли вы отправить пароль в сообщении электронной почты после добавления пользователя.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-116">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="8c0ad-117">В области **Назначение лицензий на продукты** выберите расположение и соответствующую лицензию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-117">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="8c0ad-118">Если у вас нет доступных лицензий, вы по-прежнему можете добавить пользователя и приобрести дополнительные лицензии.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-118">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="8c0ad-119">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-119">Select **Next**.</span></span>

5. <span data-ttu-id="8c0ad-120">На странице **необязательные параметры** разверните узел **роли** , если вы хотите сделать этого пользователя администратором, и раскройте **сведения о профиле** , если хотите добавить дополнительные сведения о пользователе.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-120">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="8c0ad-121">Нажмите кнопку **Далее**, просмотрите параметры нового пользователя, внесите изменения, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-121">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="8c0ad-122">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-122">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="8c0ad-123">Перейдите к разделу **Активные пользователи** **пользователей** > и выберите **Добавить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-123">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="8c0ad-124">В области **Новый пользователь** заполните указанные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-124">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="8c0ad-125">Нажмите кнопку **Добавить** , когда закончите.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-125">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="8c0ad-126">**Имя.** Введите имя и фамилию, отображаемое имя и имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-126">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="8c0ad-127">**Domain (домен** ) Например, если имя пользователя пользователя — Жакоб, а его домен — contoso.com, он выполнит вход, введя jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-127">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="8c0ad-128">**Контактные данные.** Разверните этот раздел, чтобы указать мобильный телефон, адрес и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-128">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="8c0ad-129">**Пароль.** Используйте автоматически созданный пароль или разверните этот раздел, чтобы ввести надежный пароль для пользователя.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-129">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="8c0ad-p105">Пользователю необходимо будет сменить пароль через 90 дней. Кроме того, вы можете **потребовать смену пароля при первом входе пользователя**.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-p105">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="8c0ad-132">**Роли.** Разверните этот раздел, если пользователя нужно назначить администратором.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-132">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="8c0ad-p106">**Лицензии продуктов.** Разверните этот раздел и выберите нужную лицензию. Даже если у вас нет доступных лицензий, вы можете добавить пользователя и купить дополнительные лицензии.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-p106">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="8c0ad-135">Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-135">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="8c0ad-136">Перейдите к разделу **Активные пользователи** **пользователей** > и выберите **Добавить пользователя**.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-136">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="8c0ad-137">В области **Новый пользователь** заполните указанные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-137">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="8c0ad-138">Нажмите кнопку **Добавить** , когда закончите.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-138">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="8c0ad-139">**Имя.** Введите имя и фамилию, отображаемое имя и имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-139">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="8c0ad-140">**Domain (домен** ) Например, если имя пользователя пользователя — Жакоб, а его домен — contoso.com, он выполнит вход, введя jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-140">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="8c0ad-141">**Контактные данные.** Разверните этот раздел, чтобы указать мобильный телефон, адрес и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-141">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="8c0ad-142">**Пароль.** Используйте автоматически созданный пароль или разверните этот раздел, чтобы ввести надежный пароль для пользователя.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-142">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="8c0ad-p108">Пользователю необходимо будет сменить пароль через 90 дней. Кроме того, вы можете **потребовать смену пароля при первом входе пользователя**.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-p108">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="8c0ad-145">**Роли.** Разверните этот раздел, если пользователя нужно назначить администратором.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-145">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="8c0ad-p109">**Лицензии продуктов.** Разверните этот раздел и выберите нужную лицензию. Даже если у вас нет доступных лицензий, вы можете добавить пользователя и купить дополнительные лицензии.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="8c0ad-148">После добавления пользователя вы получите сообщение электронной почты от группы Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-148">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="8c0ad-149">Сообщение электронной почты будет содержать идентификатор пользователя и пароль, чтобы пользователи могли входить в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-149">The email will contain the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="8c0ad-150">Вы должны сообщить новому пользователю о входе в систему Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-150">You need to tell your new user about their Microsoft 365 sign in information.</span></span> <span data-ttu-id="8c0ad-151">Для этого следуйте стандартной процедуре передачи паролей.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-151">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="8c0ad-152">Если вы создаете пользователей с помощью переноса почтовых ящиков, вам потребуется активировать учетные записи пользователей, назначая лицензии.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-152">If you create users by migrating mail boxes, you will need to activate user accounts by assigning licenses.</span></span> <span data-ttu-id="8c0ad-153">Если вы не назначите лицензию пользователю, их почтовые ящики будут отключены по истечении 30 дней.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-153">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="8c0ad-154">Узнайте, как [назначать лицензии пользователям](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) с помощью центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-154">See how to [assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="8c0ad-155">Видео: Добавление пользователей в центр администрирования и управление ими</span><span class="sxs-lookup"><span data-stu-id="8c0ad-155">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="8c0ad-156">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="8c0ad-156">Next steps</span></span>

<span data-ttu-id="8c0ad-157">Поделитесь [кратким руководством сотрудника](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) с новыми пользователями, чтобы они могли настроить, например, [набор Office на компьютере с Windows или Mac OS](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) или [мобильные приложения Office](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span><span class="sxs-lookup"><span data-stu-id="8c0ad-157">Share the [Employee quick start guide](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) with your new users to set things up, like [Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) and [Office mobile apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="8c0ad-158">Нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="8c0ad-158">Need help?</span></span>

<span data-ttu-id="8c0ad-159">[Обратитесь в службу поддержки Microsoft 365 для бизнеса](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="8c0ad-159">[Contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="8c0ad-160">Вам нужно добавить сотни или тысячи пользователей?</span><span class="sxs-lookup"><span data-stu-id="8c0ad-160">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="8c0ad-161">Чтобы одновременно добавить столько человек, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-161">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="8c0ad-162">**Использование электронной таблицы для массового добавления пользователей.**</span><span class="sxs-lookup"><span data-stu-id="8c0ad-162">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="8c0ad-163">Ознакомьтесь [со статьей Добавление нескольких пользователей одновременно](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span><span class="sxs-lookup"><span data-stu-id="8c0ad-163">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="8c0ad-164">**Автоматизация добавления учетных записей и назначения лицензий.**</span><span class="sxs-lookup"><span data-stu-id="8c0ad-164">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="8c0ad-165">[В разделе Создание учетных записей пользователей с помощью Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="8c0ad-165">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="8c0ad-166">Выберите этот метод, если вы уже знакомы с использованием командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-166">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="8c0ad-167">**Использование ActiveDirectory**</span><span class="sxs-lookup"><span data-stu-id="8c0ad-167">**Using ActiveDirectory?**</span></span> <span data-ttu-id="8c0ad-168">[Настройка синхронизации каталогов для Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="8c0ad-168">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="8c0ad-169">С его помощью вы можете проводить репликацию учетных записей пользователей (а также других объектов Active Directory) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-169">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="8c0ad-170">При синхронизации добавляются только учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-170">The sync only adds the user accounts.</span></span> <span data-ttu-id="8c0ad-171">Чтобы синхронизированные пользователи смогли получать доступ к электронной почте и другим приложениям Office, вам потребуется назначить им лицензии.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-171">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="8c0ad-172">**Миграция с Exchange**</span><span class="sxs-lookup"><span data-stu-id="8c0ad-172">**Migrating from Exchange?**</span></span> <span data-ttu-id="8c0ad-173">[Способы переноса нескольких учетных записей электронной почты в Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="8c0ad-173">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="8c0ad-174">При переносе нескольких почтовых ящиков в Microsoft 365 с помощью прямой, поэтапной или гибридной среды Exchange пользователи будут добавлены автоматически в рамках миграции.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-174">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="8c0ad-175">При миграции добавляются только учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-175">The migration only adds the user accounts.</span></span> <span data-ttu-id="8c0ad-176">Чтобы пользователи смогли получать доступ к электронной почте и другим приложениям Office, вам потребуется назначить им лицензии.</span><span class="sxs-lookup"><span data-stu-id="8c0ad-176">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8c0ad-177">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="8c0ad-177">Related articles</span></span>

[<span data-ttu-id="8c0ad-178">Добавление нового сотрудника в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c0ad-178">Add a new employee to Microsoft 365</span></span>](add-new-employee.md)

[<span data-ttu-id="8c0ad-179">Удаление пользователя из Организации</span><span class="sxs-lookup"><span data-stu-id="8c0ad-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="8c0ad-180">Восстановление пользователя в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c0ad-180">Restore a user in Microsoft 365</span></span>](restore-user.md)

[<span data-ttu-id="8c0ad-181">Одновременное добавление нескольких пользователей в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c0ad-181">Add several users at the same time to Microsoft 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)

