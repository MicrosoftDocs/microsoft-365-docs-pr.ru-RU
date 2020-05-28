---
title: Создание, изменение и удаление группы безопасности в центре администрирования Microsoft 365
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Узнайте, как создать, изменить или удалить группу безопасности.
ms.openlocfilehash: 283f1eca7500bfb1d8172657639bbc7cff76906f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400092"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="05d84-103">Создание, изменение и удаление группы безопасности в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="05d84-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="05d84-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="05d84-104">The admin center is changing.</span></span> <span data-ttu-id="05d84-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="05d84-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="05d84-106">На странице " **группы** Microsoft 365" можно создавать группы учетных записей пользователей, которые можно использовать для назначения одинаковых разрешений в SharePoint Online и CRM Online.</span><span class="sxs-lookup"><span data-stu-id="05d84-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="05d84-107">Например, администратор может создать группу безопасности, чтобы предоставить определенной группе людей доступ к сайту SharePoint.</span><span class="sxs-lookup"><span data-stu-id="05d84-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="05d84-108">Разрешения на создание, изменение и удаление групп безопасности имеют только администраторы глобального управления и управления пользователями; Дополнительные сведения о ролях администратора приведены в разделе [назначение ролей](../add-users/assign-admin-roles.md)администратора.</span><span class="sxs-lookup"><span data-stu-id="05d84-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="05d84-109">Существуют также [Группы в Exchange Online и SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), которые можно использовать для отправки электронной почты или назначения разрешений группе пользователей, и [Группы в Exchange Online и SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), с помощью которых можно предоставлять пользователям права и доступ к веб-сайтам и их семействам.</span><span class="sxs-lookup"><span data-stu-id="05d84-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="05d84-110">Планирование использования почтовых ящиков сайта</span><span class="sxs-lookup"><span data-stu-id="05d84-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="05d84-111">Все пользователи, которые добавляются на сайт SharePoint через группу безопасности, а не добавляются по отдельности, могут использовать только почтовый ящик сайта из SharePoint.</span><span class="sxs-lookup"><span data-stu-id="05d84-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="05d84-112">Эти пользователи не смогут получать доступ к почтовому ящику сайта из Outlook.</span><span class="sxs-lookup"><span data-stu-id="05d84-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="05d84-113">Дополнительные сведения см. в [статье Использование групп Microsoft 365 вместо почтовых ящиков сайта](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span><span class="sxs-lookup"><span data-stu-id="05d84-113">For more information, see [Use Microsoft 365 groups instead of Site Mailboxes](https://support.office.com/article/737d6b1f-67cc-41fe-8db8-f2d09dd1673b.aspx).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="05d84-114">Управление группами безопасности в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="05d84-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="05d84-115">Добавление группы безопасности</span><span class="sxs-lookup"><span data-stu-id="05d84-115">Add a security group</span></span>

1. <span data-ttu-id="05d84-116">В центре администрирования Microsoft 365 перейдите на **Groups**  >  страницу<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> группы.</span><span class="sxs-lookup"><span data-stu-id="05d84-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="05d84-117">На странице " **группы** " выберите команду **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="05d84-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="05d84-118">На странице **Выбор типа группы** выберите **Безопасность**.</span><span class="sxs-lookup"><span data-stu-id="05d84-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="05d84-119">Чтобы завершить создание группы, выполните действия, описанные в разделе.</span><span class="sxs-lookup"><span data-stu-id="05d84-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="05d84-120">Добавление участников в группу безопасности</span><span class="sxs-lookup"><span data-stu-id="05d84-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="05d84-121">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="05d84-121">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>
    
1. <span data-ttu-id="05d84-122">Выберите имя группы безопасности на странице " **группы** ", а затем на вкладке **Участники** выберите **Просмотр всех элементов и управление ими**.</span><span class="sxs-lookup"><span data-stu-id="05d84-122">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="05d84-123">В области Группа выберите **Добавить участников** и выберите пользователя из списка или введите имя пользователя, которого вы хотите добавить в поле **поиска** , а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="05d84-123">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="05d84-124">Чтобы удалить участников, нажмите X рядом с именем.</span><span class="sxs-lookup"><span data-stu-id="05d84-124">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="05d84-125">На странице **группы** выберите имя группы безопасности, а затем нажмите кнопку **изменить** **рядом с элементом**.</span><span class="sxs-lookup"><span data-stu-id="05d84-125">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="05d84-126">В области Группа выберите **Добавить участников** и выберите пользователя из списка или введите имя пользователя, которого вы хотите добавить в поле **поиска** , а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="05d84-126">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="05d84-127">Чтобы удалить участников, нажмите X рядом с именем.</span><span class="sxs-lookup"><span data-stu-id="05d84-127">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="05d84-128">На странице **группы** выберите имя группы безопасности, а затем нажмите кнопку **изменить** **рядом с элементом**.</span><span class="sxs-lookup"><span data-stu-id="05d84-128">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="05d84-129">В области Группа выберите **Добавить участников** и выберите пользователя из списка или введите имя пользователя, которого вы хотите добавить в поле **поиска** , а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="05d84-129">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="05d84-130">Чтобы удалить участников, нажмите X рядом с именем.</span><span class="sxs-lookup"><span data-stu-id="05d84-130">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="05d84-131">Изменение группы безопасности</span><span class="sxs-lookup"><span data-stu-id="05d84-131">Edit a security group</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="05d84-132">Если вы не используете новый Центр администрирования Microsoft 365, можно включить его с помощью переключателя **Попробовать новый Центр администрирования**, расположенного в верхней части главной страницы.</span><span class="sxs-lookup"><span data-stu-id="05d84-132">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="05d84-133">В центре администрирования перейдите на **Groups** \> страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> группы.</span><span class="sxs-lookup"><span data-stu-id="05d84-133">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="05d84-134">На странице **группы** выберите имя группы.</span><span class="sxs-lookup"><span data-stu-id="05d84-134">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="05d84-135">В области Параметры перейдите на вкладку **Общие** или **члены** , чтобы изменить сведения о группе или ее членах.</span><span class="sxs-lookup"><span data-stu-id="05d84-135">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="05d84-136">В центре администрирования перейдите на **Groups** \> страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> группы.</span><span class="sxs-lookup"><span data-stu-id="05d84-136">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="05d84-137">На странице **группы** выберите имя группы.</span><span class="sxs-lookup"><span data-stu-id="05d84-137">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="05d84-138">В области группа безопасности нажмите кнопку **изменить** рядом с вкладкой **имя** или **члены** , чтобы изменить сведения о группе или членах.</span><span class="sxs-lookup"><span data-stu-id="05d84-138">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="05d84-139">После внесения изменений нажмите кнопку **сохранить** \> **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="05d84-139">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="05d84-140">В центре администрирования перейдите на **Groups** \> страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> группы.</span><span class="sxs-lookup"><span data-stu-id="05d84-140">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="05d84-141">На странице **группы** выберите имя группы.</span><span class="sxs-lookup"><span data-stu-id="05d84-141">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="05d84-142">В области группа безопасности нажмите кнопку **изменить** рядом с вкладкой **имя** или **члены** , чтобы изменить сведения о группе или членах.</span><span class="sxs-lookup"><span data-stu-id="05d84-142">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="05d84-143">После внесения изменений нажмите кнопку **сохранить** > **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="05d84-143">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="05d84-144">Удаление группы безопасности</span><span class="sxs-lookup"><span data-stu-id="05d84-144">Delete a security group</span></span>

1. <span data-ttu-id="05d84-145">В центре администрирования перейдите на **Groups**  >  страницу<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> группы.</span><span class="sxs-lookup"><span data-stu-id="05d84-145">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="05d84-146">На странице **группы** выберите имя группы.</span><span class="sxs-lookup"><span data-stu-id="05d84-146">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="05d84-147">Выберите **Удалить группу** (значок васетбин), а затем подтвердите, нажав кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="05d84-147">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="05d84-148">После удаления группы нажмите кнопку **Закрыть** .</span><span class="sxs-lookup"><span data-stu-id="05d84-148">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="05d84-149">Группы в Exchange Online и SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="05d84-149">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="05d84-150">Если вы хотите создать группы пользователей, чтобы вы могли отправлять их всем пользователям одновременно, вы можете сделать это в центре администрирования Exchange, перейдя к разделу **Администрирование** \> **Exchange** \> **Recipients** \> **групп**получателей Exchange.</span><span class="sxs-lookup"><span data-stu-id="05d84-150">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="05d84-151">Затем выберите команду **создать** ![ Добавление ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) и выберите тип создаваемой группы:</span><span class="sxs-lookup"><span data-stu-id="05d84-151">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="05d84-152">**Группа рассылки**: используется для распространения сообщений группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="05d84-152">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="05d84-153">Она также называется *группой рассылки с включенной поддержкой почты*или *списком рассылки*.</span><span class="sxs-lookup"><span data-stu-id="05d84-153">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="05d84-154">Дополнительные сведения: [Manage рассылки Groups](https://technet.microsoft.com/library/bb124513.aspx).</span><span class="sxs-lookup"><span data-stu-id="05d84-154">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="05d84-155">**Группа безопасности**: может использоваться для распространения сообщений группе пользователей или предоставления разрешений на доступ к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="05d84-155">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="05d84-156">Эта группа также называется *группой безопасности с включенной поддержкой почты*.</span><span class="sxs-lookup"><span data-stu-id="05d84-156">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="05d84-157">Дополнительные сведения: [Управление группами безопасности с поддержкой электронной почты](https://technet.microsoft.com/library/bb123521.aspx).</span><span class="sxs-lookup"><span data-stu-id="05d84-157">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="05d84-158">**Динамическая группа рассылки**: тип группы рассылки, список получателей которых пересчитывается при каждой отправке сообщения на основе определяемых фильтров и условий.</span><span class="sxs-lookup"><span data-stu-id="05d84-158">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="05d84-159">Дополнительные [сведения см.](https://technet.microsoft.com/library/bb123722.aspx)</span><span class="sxs-lookup"><span data-stu-id="05d84-159">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="05d84-160">После создания групп рассылки и групп безопасности с включенной поддержкой почты в центре администрирования Exchange их имена и списки пользователей отобразятся на странице " **группы безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="05d84-160">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="05d84-161">Удалить эти группы можно в обоих местах, но изменить  только в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="05d84-161">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="05d84-162">Динамические группы рассылки не отображаются на странице " **группы безопасности** ".</span><span class="sxs-lookup"><span data-stu-id="05d84-162">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="05d84-163">Группы SharePoint создаются автоматически при создании семейства веб-сайтов.</span><span class="sxs-lookup"><span data-stu-id="05d84-163">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="05d84-164">Группы по умолчанию используют уровни разрешений по умолчанию в SharePoint, иногда называемые ролями SharePoint, чтобы предоставить пользователям права и доступ.</span><span class="sxs-lookup"><span data-stu-id="05d84-164">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="05d84-165">Дополнительные сведения см. [в разделе группы SharePoint по умолчанию в SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span><span class="sxs-lookup"><span data-stu-id="05d84-165">For more information, see [Default SharePoint groups in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="05d84-166">Чем отличается группа безопасности от групп безопасности, созданных в SharePoint?</span><span class="sxs-lookup"><span data-stu-id="05d84-166">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="05d84-167">Группы безопасности можно использовать с SharePoint, Exchange, MDM, Windows и т. д.</span><span class="sxs-lookup"><span data-stu-id="05d84-167">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="05d84-168">Группа безопасности, созданная в SharePoint, распознается только этим семейством веб-сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="05d84-168">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="05d84-169">Нужно ли использовать группы безопасности для защиты Организации?</span><span class="sxs-lookup"><span data-stu-id="05d84-169">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="05d84-p111">Нет. Это лишь один из способов управления безопасностью организации. Вы можете предоставлять разрешения и доступ к сайтам каждому пользователю по отдельности. Группы безопасности просто упрощают управление несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="05d84-p111">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="05d84-174">Можно ли отправлять электронную почту в группу безопасности?</span><span class="sxs-lookup"><span data-stu-id="05d84-174">Can I send email to a security group?</span></span>

<span data-ttu-id="05d84-175">Да.</span><span class="sxs-lookup"><span data-stu-id="05d84-175">Yes.</span></span> <span data-ttu-id="05d84-176">Но если вы хотите использовать группы для электронной почты и совместной работы, рекомендуем [создать группу Microsoft 365](../create-groups/create-groups.md) .</span><span class="sxs-lookup"><span data-stu-id="05d84-176">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
