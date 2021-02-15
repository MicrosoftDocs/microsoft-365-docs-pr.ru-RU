---
title: Создание, изменение или удаление группы безопасности в Центре администрирования Microsoft 365
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
ms.openlocfilehash: df3d8fde0c487663237b3858aa0bf049ba4db045
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114049"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6dade-103">Создание, изменение или удаление группы безопасности в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6dade-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6dade-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="6dade-104">The admin center is changing.</span></span> <span data-ttu-id="6dade-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="6dade-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="6dade-106">На странице "Группы  Microsoft 365" можно создать группы учетных записей пользователей, которые можно использовать для назначения одинаковых разрешений в SharePoint Online и CRM Online.</span><span class="sxs-lookup"><span data-stu-id="6dade-106">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="6dade-107">Например, администратор может создать группу безопасности, чтобы предоставить определенной группе людей доступ к сайту SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6dade-107">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="6dade-108">Разрешения на создание, изменение и удаление групп безопасности имеют только глобальные администраторы и администраторы управления пользователями; Дополнительные сведения о ролях администратора см. в [подназначе-ных ролях администратора.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="6dade-108">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="6dade-109">Существуют также [Группы в Exchange Online и SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), которые можно использовать для отправки электронной почты или назначения разрешений группе пользователей, и [Группы в Exchange Online и SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), с помощью которых можно предоставлять пользователям права и доступ к веб-сайтам и их семействам.</span><span class="sxs-lookup"><span data-stu-id="6dade-109">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="6dade-110">Планируете использовать почтовые ящики сайта?</span><span class="sxs-lookup"><span data-stu-id="6dade-110">Planning on using site mailboxes?</span></span> <span data-ttu-id="6dade-111">Все пользователи, которые добавляются на сайт SharePoint через группу безопасности, а не добавляются по отдельности, могут использовать только почтовый ящик сайта из SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6dade-111">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="6dade-112">Эти пользователи не смогут получить доступ к почтовому ящику сайта из Outlook.</span><span class="sxs-lookup"><span data-stu-id="6dade-112">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="6dade-113">Дополнительные сведения см. в теме ["Использование групп Microsoft 365 вместо почтовых ящиков сайта".](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)</span><span class="sxs-lookup"><span data-stu-id="6dade-113">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="6dade-114">Управление группами безопасности в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="6dade-114">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="6dade-115">Добавление группы безопасности</span><span class="sxs-lookup"><span data-stu-id="6dade-115">Add a security group</span></span>

1. <span data-ttu-id="6dade-116">В Центре администрирования Microsoft 365 перейдите на страницу **"Группы**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a> групп".</span><span class="sxs-lookup"><span data-stu-id="6dade-116">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="6dade-117">На странице **"Группы"** выберите **"Добавить группу".**</span><span class="sxs-lookup"><span data-stu-id="6dade-117">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="6dade-118">На странице **"Выбор типа группы"** выберите **"Безопасность".**</span><span class="sxs-lookup"><span data-stu-id="6dade-118">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="6dade-119">Выполните действия, чтобы завершить создание группы.</span><span class="sxs-lookup"><span data-stu-id="6dade-119">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="6dade-120">Добавление участников в группу безопасности</span><span class="sxs-lookup"><span data-stu-id="6dade-120">Add members to a security group</span></span>

::: moniker range="o365-worldwide"
    
1. <span data-ttu-id="6dade-121">Выберите имя группы безопасности на **странице** "Группы", а на вкладке "Участники" выберите "Просмотреть всех участников" **и "Управлять участниками".** </span><span class="sxs-lookup"><span data-stu-id="6dade-121">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="6dade-122">В области групп выберите  "Добавить участников" и выберите человека из списка или введите  имя нужного человека в поле поиска, а затем выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="6dade-122">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="6dade-123">Чтобы удалить участников, выберите X рядом с их именем.</span><span class="sxs-lookup"><span data-stu-id="6dade-123">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6dade-124">Выберите имя группы безопасности на странице **"Группы",** а затем **выберите** "Изменить рядом с **участниками".**</span><span class="sxs-lookup"><span data-stu-id="6dade-124">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="6dade-125">В области групп выберите  "Добавить участников" и выберите человека из списка или введите  имя нужного человека в поле поиска, а затем выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="6dade-125">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="6dade-126">Чтобы удалить участников, выберите X рядом с их именем.</span><span class="sxs-lookup"><span data-stu-id="6dade-126">To remove members, select the X next to their name.</span></span> 
  
::: moniker-end

::: moniker range="o365-21vianet"


1. <span data-ttu-id="6dade-127">Выберите имя группы безопасности на странице **"Группы",** а затем **выберите** "Изменить рядом с **участниками".**</span><span class="sxs-lookup"><span data-stu-id="6dade-127">Select the security group name on the **Groups** page, and then select **Edit** next to **Members**.</span></span> 
    
2. <span data-ttu-id="6dade-128">В области групп выберите  "Добавить участников" и выберите человека из списка или введите  имя нужного человека в поле поиска, а затем выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="6dade-128">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="6dade-129">Чтобы удалить участников, выберите X рядом с их именем.</span><span class="sxs-lookup"><span data-stu-id="6dade-129">To remove members, select the X next to their name.</span></span>

::: moniker-end

### <a name="edit-a-security-group"></a><span data-ttu-id="6dade-130">Изменение группы безопасности</span><span class="sxs-lookup"><span data-stu-id="6dade-130">Edit a security group</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6dade-131">В Центре администрирования перейдите на **страницу** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">"Группы групп".</a></span><span class="sxs-lookup"><span data-stu-id="6dade-131">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="6dade-132">На странице **"Группы"** выберите имя группы.</span><span class="sxs-lookup"><span data-stu-id="6dade-132">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="6dade-133">В области параметров выберите  вкладку "Общие" или **"Участники",** чтобы изменить сведения о группе или ее членах.</span><span class="sxs-lookup"><span data-stu-id="6dade-133">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6dade-134">В Центре <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">администрирования перейдите</a>на **страницу** \> **"Группы групп".**</span><span class="sxs-lookup"><span data-stu-id="6dade-134">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>  
  
2. <span data-ttu-id="6dade-135">На странице **"Группы"** выберите имя группы.</span><span class="sxs-lookup"><span data-stu-id="6dade-135">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="6dade-136">В области групп безопасности  выберите "Изменить"  рядом с вкладками **"Имя"** или "Участники", чтобы изменить сведения о группе или ее членах.</span><span class="sxs-lookup"><span data-stu-id="6dade-136">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="6dade-137">После внесения изменений выберите **"Сохранить** \> **закрыть".**</span><span class="sxs-lookup"><span data-stu-id="6dade-137">After you've made changes, select **Save** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6dade-138">В Центре <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">администрирования перейдите</a>на **страницу** \> **"Группы групп".**</span><span class="sxs-lookup"><span data-stu-id="6dade-138">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Groups** \> **Groups** page.</span></span>
  
2. <span data-ttu-id="6dade-139">На странице **"Группы"** выберите имя группы.</span><span class="sxs-lookup"><span data-stu-id="6dade-139">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="6dade-140">В области групп безопасности  выберите "Изменить"  рядом с вкладками **"Имя"** или "Участники", чтобы изменить сведения о группе или ее членах.</span><span class="sxs-lookup"><span data-stu-id="6dade-140">In the security group pane, select **Edit** next to either **Name** or **Members** tab to edit either group details or members.</span></span>
    
4. <span data-ttu-id="6dade-141">После внесения изменений выберите **"Сохранить** > **закрыть".**</span><span class="sxs-lookup"><span data-stu-id="6dade-141">After you've made changes, select **Save** > **Close**.</span></span>

::: moniker-end


### <a name="delete-a-security-group"></a><span data-ttu-id="6dade-142">Удаление группы безопасности</span><span class="sxs-lookup"><span data-stu-id="6dade-142">Delete a security group</span></span>

1. <span data-ttu-id="6dade-143">В Центре администрирования перейдите на **страницу**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">"Группы групп".</a></span><span class="sxs-lookup"><span data-stu-id="6dade-143">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="6dade-144">На странице **"Группы"** выберите имя группы.</span><span class="sxs-lookup"><span data-stu-id="6dade-144">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="6dade-145">Выберите **"Удалить группу"** (значок wasetbin), а затем подтвердите, выбрав **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="6dade-145">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="6dade-146">После **удаления** группы выберите "Закрыть".</span><span class="sxs-lookup"><span data-stu-id="6dade-146">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="6dade-147">Группы в Exchange Online и SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="6dade-147">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="6dade-148">Если вы хотите создать группы пользователей, чтобы отправлять им электронную почту одновременно, это можно сделать  в Центре администрирования Exchange, перенаправив их в группы получателей \> **Exchange** \>  \> **администрирования.**</span><span class="sxs-lookup"><span data-stu-id="6dade-148">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="6dade-149">Затем выберите **"Создать** добавить" и выберите тип ![ создаемой ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) группы:</span><span class="sxs-lookup"><span data-stu-id="6dade-149">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="6dade-150">**Группа рассылки:** используется для распространения сообщений группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="6dade-150">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="6dade-151">Она также называется группой рассылки с включенной поддержкой почты *или* *списком рассылки.*</span><span class="sxs-lookup"><span data-stu-id="6dade-151">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="6dade-152">Дополнительные сведения см. в под [управлением группами рассылки.](https://technet.microsoft.com/library/bb124513.aspx)</span><span class="sxs-lookup"><span data-stu-id="6dade-152">For more information, see [Manage distribution groups](https://technet.microsoft.com/library/bb124513.aspx).</span></span>
    
- <span data-ttu-id="6dade-153">**Группа безопасности:** может использоваться для распространения сообщений группе пользователей или предоставления разрешений на доступ к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="6dade-153">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="6dade-154">Эта группа также называется группой безопасности *с включенной поддержкой почты.*</span><span class="sxs-lookup"><span data-stu-id="6dade-154">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="6dade-155">Дополнительные сведения см. в под [управлением групп безопасности с включенной поддержкой почты.](https://technet.microsoft.com/library/bb123521.aspx)</span><span class="sxs-lookup"><span data-stu-id="6dade-155">For more information, see [Manage mail-enabled security groups](https://technet.microsoft.com/library/bb123521.aspx).</span></span>
    
- <span data-ttu-id="6dade-156">**Динамическая группа** рассылки : тип группы рассылки, список получателей которой пересчитываются при каждой отправке сообщения на основе определенных вами фильтров и условий.</span><span class="sxs-lookup"><span data-stu-id="6dade-156">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="6dade-157">Дополнительные сведения см. в под [управлением динамических групп рассылки.](https://technet.microsoft.com/library/bb123722.aspx)</span><span class="sxs-lookup"><span data-stu-id="6dade-157">For more information, see [Manage dynamic distribution groups](https://technet.microsoft.com/library/bb123722.aspx).</span></span>
    
<span data-ttu-id="6dade-158">После создания групп рассылки и групп безопасности с включенной поддержкой почты в Центре администрирования Exchange их имена и списки пользователей отображаются на странице "Группы **безопасности".**</span><span class="sxs-lookup"><span data-stu-id="6dade-158">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="6dade-159">Удалить эти группы можно в обоих местах, но изменить  только в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="6dade-159">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="6dade-160">Динамические группы рассылки не показываются на странице **"Группы безопасности".**</span><span class="sxs-lookup"><span data-stu-id="6dade-160">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="6dade-161">Группы SharePoint создаются автоматически при формировании коллекции сайтов.</span><span class="sxs-lookup"><span data-stu-id="6dade-161">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="6dade-162">Группы по умолчанию используют уровни разрешений по умолчанию в SharePoint (иногда называемые ролями SharePoint) для предоставления пользователям прав и доступа.</span><span class="sxs-lookup"><span data-stu-id="6dade-162">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="6dade-163">Дополнительные сведения [см. в стандартных группах SharePoint в SharePoint Online.](https://docs.microsoft.com/sharepoint/default-sharepoint-groups)</span><span class="sxs-lookup"><span data-stu-id="6dade-163">For more information, see [Default SharePoint groups in SharePoint Online](https://docs.microsoft.com/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="6dade-164">Чем группа безопасности отличается от групп безопасности, которые я создаю в SharePoint?</span><span class="sxs-lookup"><span data-stu-id="6dade-164">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="6dade-165">Группы безопасности можно использовать с SharePoint, Exchange, MDM, Windows и другими службами.</span><span class="sxs-lookup"><span data-stu-id="6dade-165">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="6dade-166">Группа безопасности, которую вы создаете в SharePoint, распознается только этим набором веб-сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6dade-166">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="6dade-167">Нужно ли использовать группы безопасности для обеспечения безопасности моей организации?</span><span class="sxs-lookup"><span data-stu-id="6dade-167">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="6dade-p111">Нет. Это лишь один из способов управления безопасностью организации. Вы можете предоставлять разрешения и доступ к сайтам каждому пользователю по отдельности. Группы безопасности просто упрощают управление несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="6dade-p111">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="6dade-172">Можно ли отправлять электронную почту группе безопасности?</span><span class="sxs-lookup"><span data-stu-id="6dade-172">Can I send email to a security group?</span></span>

<span data-ttu-id="6dade-173">Да.</span><span class="sxs-lookup"><span data-stu-id="6dade-173">Yes.</span></span> <span data-ttu-id="6dade-174">Но если вы хотите использовать группы для электронной почты и совместной работы, рекомендуем создать группу [Microsoft 365.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="6dade-174">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 
  
