---
title: Создание, редактирование или удаление группы безопасности в Центр администрирования Microsoft 365
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Научитесь создавать, редактировать или удалять группу безопасности.
ms.openlocfilehash: 525acc45b293563f58bb9aa12c40bec1438cb055
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393959"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a884e-103">Создание, редактирование или удаление группы безопасности в Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a884e-103">Create, edit, or delete a security group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="a884e-104">На странице Microsoft 365 **Группы** можно создать группы учетных записей пользователей, которые можно использовать для назначения тех же разрешений в SharePoint Online и CRM Online.</span><span class="sxs-lookup"><span data-stu-id="a884e-104">On the Microsoft 365 **Groups** page, you can create groups of user accounts that you can use to assign the same permissions to in SharePoint Online and CRM Online.</span></span> <span data-ttu-id="a884e-105">Например, администратор может создать группу безопасности, чтобы предоставить определенной группе людей доступ к SharePoint сайту.</span><span class="sxs-lookup"><span data-stu-id="a884e-105">For example, an administrator can create a security group to grant a certain group of people access to a SharePoint site.</span></span> <span data-ttu-id="a884e-106">Только администраторы глобального и управления пользователями имеют разрешения на создание, редактирование или удаление групп безопасности; Дополнительные сведения о ролях администратора см. в [дополнительных сведениях о назначении ролей администратора.](../add-users/assign-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="a884e-106">Only global and user management administrators have permissions to create, edit, or delete security groups; for more information about administrator roles, see [Assigning admin roles](../add-users/assign-admin-roles.md).</span></span> 
  
<span data-ttu-id="a884e-107">Существуют также [Группы в Exchange Online и SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), которые можно использовать для отправки электронной почты или назначения разрешений группе пользователей, и [Группы в Exchange Online и SharePoint Online](#groups-in-exchange-online-and-sharepoint-online), с помощью которых можно предоставлять пользователям права и доступ к веб-сайтам и их семействам.</span><span class="sxs-lookup"><span data-stu-id="a884e-107">There are also [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that you can use to send email or assign permissions to a group of users, and [Groups in Exchange Online and SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) that grant users rights and access to sites and site collections.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="a884e-108">Планирование использования почтовых ящиков сайтов?</span><span class="sxs-lookup"><span data-stu-id="a884e-108">Planning on using site mailboxes?</span></span> <span data-ttu-id="a884e-109">Все пользователи, добавленные на веб-SharePoint через группу безопасности, а не добавляться по отдельности, могут использовать только почтовый ящик сайта из SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a884e-109">All the users that are added to a SharePoint site via a security group rather than being added individually can use only the site mailbox from SharePoint.</span></span> <span data-ttu-id="a884e-110">Эти пользователи не смогут получить доступ к почтовому ящику сайта из Outlook.</span><span class="sxs-lookup"><span data-stu-id="a884e-110">These users won't be able to access the site mailbox from Outlook.</span></span> <span data-ttu-id="a884e-111">Дополнительные сведения см. в [Microsoft 365 группы, а не почтовые ящики сайтов.](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b)</span><span class="sxs-lookup"><span data-stu-id="a884e-111">For more information, see [Use Microsoft 365 Groups instead of Site Mailboxes](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b).</span></span> 
  
## <a name="manage-security-groups-in-the-admin-center"></a><span data-ttu-id="a884e-112">Управление группами безопасности в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="a884e-112">Manage security groups in the admin center</span></span>

### <a name="add-a-security-group"></a><span data-ttu-id="a884e-113">Добавление группы безопасности</span><span class="sxs-lookup"><span data-stu-id="a884e-113">Add a security group</span></span>

1. <span data-ttu-id="a884e-114">В Центр администрирования Microsoft 365 перейдите на страницу **Группы**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">групп.</a></span><span class="sxs-lookup"><span data-stu-id="a884e-114">In the Microsoft 365 admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="a884e-115">На странице **Группы** выберите **Добавить группу.**</span><span class="sxs-lookup"><span data-stu-id="a884e-115">On the **Groups** page, select **Add a group**.</span></span>
    
3. <span data-ttu-id="a884e-116">На странице **Выберите тип группы** выберите **безопасность.**</span><span class="sxs-lookup"><span data-stu-id="a884e-116">On the **Choose a group type** page, choose **Security**.</span></span> 
    
4. <span data-ttu-id="a884e-117">Выполните действия по завершению создания группы.</span><span class="sxs-lookup"><span data-stu-id="a884e-117">Follow the steps to complete creation of the group.</span></span> 
 
### <a name="add-members-to-a-security-group"></a><span data-ttu-id="a884e-118">Добавление участников в группу безопасности</span><span class="sxs-lookup"><span data-stu-id="a884e-118">Add members to a security group</span></span>
    
1. <span data-ttu-id="a884e-119">Выберите имя группы безопасности на странице **Группы** и на вкладке **Члены,** выберите Просмотр всех и **управление участниками.**</span><span class="sxs-lookup"><span data-stu-id="a884e-119">Select the security group name on the **Groups** page, and on the **Members** tab, select **View all and manage members**.</span></span> 
    
2. <span data-ttu-id="a884e-120">В области группы выберите  Добавить участников и выберите человека из списка или введите имя  человека, которого вы хотите добавить в поле Поиск, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a884e-120">In the group pane, select **Add members** and choose the person from the list or type the name of the person you want to add in the **Search** box, and then select **Save**.</span></span>
    
    <span data-ttu-id="a884e-121">Чтобы удалить участников, выберите X рядом с их именем.</span><span class="sxs-lookup"><span data-stu-id="a884e-121">To remove members, select the X next to their name.</span></span> 
  
### <a name="edit-a-security-group"></a><span data-ttu-id="a884e-122">Изменение группы безопасности</span><span class="sxs-lookup"><span data-stu-id="a884e-122">Edit a security group</span></span>

1. <span data-ttu-id="a884e-123">В центре администрирования перейдите на страницу **Группы** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">групп.</a></span><span class="sxs-lookup"><span data-stu-id="a884e-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="a884e-124">На странице **Группы** выберите имя группы.</span><span class="sxs-lookup"><span data-stu-id="a884e-124">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="a884e-125">В области параметров выберите вкладку **General** или вкладку **Members,** чтобы изменить сведения о группе или членах.</span><span class="sxs-lookup"><span data-stu-id="a884e-125">In the settings pane, select the **General** tab or the **Members** tab to edit either group details or members.</span></span>

### <a name="delete-a-security-group"></a><span data-ttu-id="a884e-126">Удаление группы безопасности</span><span class="sxs-lookup"><span data-stu-id="a884e-126">Delete a security group</span></span>

1. <span data-ttu-id="a884e-127">В центре администрирования перейдите на страницу **Группы**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">групп.</a></span><span class="sxs-lookup"><span data-stu-id="a884e-127">In the admin center, go to the **Groups** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
    
2. <span data-ttu-id="a884e-128">На странице **Группы** выберите имя группы.</span><span class="sxs-lookup"><span data-stu-id="a884e-128">On the **Groups** page, select the group's name.</span></span> 
    
3. <span data-ttu-id="a884e-129">Выберите **группу Delete** (значок wasetbin), а затем подтвердите, выбрав **Delete**.</span><span class="sxs-lookup"><span data-stu-id="a884e-129">Select **Delete group** (wasetbin icon), and then confirm by selecting **Delete**.</span></span>
    
    <span data-ttu-id="a884e-130">Выберите **Закрыть** после удаления группы.</span><span class="sxs-lookup"><span data-stu-id="a884e-130">Select **Close** once the group is deleted.</span></span> 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a><span data-ttu-id="a884e-131">Группы в Exchange Online и SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a884e-131">Groups in Exchange Online and SharePoint Online</span></span>

<span data-ttu-id="a884e-132">Если вы хотите создать группы пользователей, чтобы вы могли отправлять им электронную почту одновременно, вы можете сделать  это в центре администрирования Exchange, отправив групп получателей администратора Exchange. \>  \>  \> </span><span class="sxs-lookup"><span data-stu-id="a884e-132">If you want to create groups of users so you can send email to them all at the same time, you can do that in the Exchange admin center by going to **Admin** \> **Exchange** \> **Recipients** \> **Groups**.</span></span> <span data-ttu-id="a884e-133">Далее выберите **New** ![ Add и выберите группу, которая будет ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) создаваться:</span><span class="sxs-lookup"><span data-stu-id="a884e-133">Next, select **New**![Add](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png), and select the kind of group you want to create:</span></span> 
  
- <span data-ttu-id="a884e-134">**Группа рассылки.** Используется для распространения сообщений для группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="a884e-134">**Distribution group**: Used to distribute messages to a group of users.</span></span> <span data-ttu-id="a884e-135">Она также называется группой *рассылки* с поддержкой почты или *списком рассылки.*</span><span class="sxs-lookup"><span data-stu-id="a884e-135">It's also called a  *mail-enabled distribution group*, or, a  *distribution list*.</span></span> <span data-ttu-id="a884e-136">Дополнительные сведения см. в ["Управление группами рассылки".](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)</span><span class="sxs-lookup"><span data-stu-id="a884e-136">For more information, see [Manage distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).</span></span>
    
- <span data-ttu-id="a884e-137">**Группа безопасности.** Можно использовать для распространения сообщений для группы пользователей или предоставления разрешений на доступ к ресурсам.</span><span class="sxs-lookup"><span data-stu-id="a884e-137">**Security group**: Can be used to distribute messages to a group of users, or to grant access permissions to resources.</span></span> <span data-ttu-id="a884e-138">Эта группа также называется группой безопасности с поддержкой *почты.*</span><span class="sxs-lookup"><span data-stu-id="a884e-138">This group is also called a *mail-enabled security group*.</span></span> <span data-ttu-id="a884e-139">Дополнительные сведения см. в [сообщении Управление группами](/Exchange/recipients/mail-enabled-security-groups)безопасности с поддержкой почты.</span><span class="sxs-lookup"><span data-stu-id="a884e-139">For more information, see [Manage mail-enabled security groups](/Exchange/recipients/mail-enabled-security-groups).</span></span>
    
- <span data-ttu-id="a884e-140">**Динамическая группа** рассылки: тип группы рассылки, список получателей которой пересчитываются при каждом отправке сообщения на основе фильтров и условий, которые вы определяете.</span><span class="sxs-lookup"><span data-stu-id="a884e-140">**Dynamic distribution group**: A type of distribution group whose list of recipients is recalculated every time you send a message based on filters and conditions that you define.</span></span> <span data-ttu-id="a884e-141">Дополнительные сведения см. в [см. в "Управление динамическими группами рассылки".](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups)</span><span class="sxs-lookup"><span data-stu-id="a884e-141">For more information, see [Manage dynamic distribution groups](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).</span></span>
    
<span data-ttu-id="a884e-142">После создания групп рассылки и групп безопасности с включенной почтой в центре администрирования Exchange их имена и списки пользователей отображаются на странице **Группы** безопасности.</span><span class="sxs-lookup"><span data-stu-id="a884e-142">After you create distribution groups and mail-enabled security groups in the Exchange admin center, their names and user lists appear on the **Security groups** page.</span></span> <span data-ttu-id="a884e-143">Удалить эти группы можно в обоих местах, но изменить  только в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="a884e-143">You can delete these groups in both locations, but you can edit them only in the Exchange admin center.</span></span> <span data-ttu-id="a884e-144">Динамические группы рассылки не показываются на странице **Группы** безопасности.</span><span class="sxs-lookup"><span data-stu-id="a884e-144">Dynamic distribution groups don't show up on the **Security groups** page.</span></span> 
  
 <span data-ttu-id="a884e-145">SharePoint группы создаются автоматически при формировании коллекции сайтов.</span><span class="sxs-lookup"><span data-stu-id="a884e-145">SharePoint groups are created automatically when you make a site collection.</span></span> <span data-ttu-id="a884e-146">Группы по умолчанию используют уровни разрешений по умолчанию в SharePoint иногда SharePoint ролей, чтобы предоставить пользователям права и доступ.</span><span class="sxs-lookup"><span data-stu-id="a884e-146">The default groups use the default permission levels in SharePoint—sometimes called SharePoint roles—to grant users rights and access.</span></span> <span data-ttu-id="a884e-147">Дополнительные сведения см. в SharePoint группах по умолчанию [в SharePoint Online.](/sharepoint/default-sharepoint-groups)</span><span class="sxs-lookup"><span data-stu-id="a884e-147">For more information, see [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).</span></span>
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a><span data-ttu-id="a884e-148">Чем группа безопасности отличается от групп безопасности, которые я создаю в SharePoint?</span><span class="sxs-lookup"><span data-stu-id="a884e-148">How is a security group different from security groups I create in SharePoint?</span></span>

<span data-ttu-id="a884e-149">Группы безопасности можно использовать с SharePoint, Exchange, MDM, Windows и другими.</span><span class="sxs-lookup"><span data-stu-id="a884e-149">Security groups can be used with SharePoint, Exchange, MDM, Windows, and more.</span></span> <span data-ttu-id="a884e-150">Группа безопасности, которую вы создаете в SharePoint, распознается только этой SharePoint сайта.</span><span class="sxs-lookup"><span data-stu-id="a884e-150">A security group you create in SharePoint is only recognized by that SharePoint site collection.</span></span>
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a><span data-ttu-id="a884e-151">Нужно ли использовать группы безопасности для обеспечения безопасности организации?</span><span class="sxs-lookup"><span data-stu-id="a884e-151">Do I have to use security groups for my organization to be secure?</span></span>

<span data-ttu-id="a884e-p110">Нет. Это лишь один из способов управления безопасностью организации. Вы можете предоставлять разрешения и доступ к сайтам каждому пользователю по отдельности. Группы безопасности просто упрощают управление несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="a884e-p110">No. This is just one more way you can manage security for your organization. You can always grant user permissions and access to sites individually. But with security groups, you can easily manage larger groups of users.</span></span>
  
## <a name="can-i-send-email-to-a-security-group"></a><span data-ttu-id="a884e-156">Могу ли я отправить электронную почту группе безопасности?</span><span class="sxs-lookup"><span data-stu-id="a884e-156">Can I send email to a security group?</span></span>

<span data-ttu-id="a884e-157">Да.</span><span class="sxs-lookup"><span data-stu-id="a884e-157">Yes.</span></span> <span data-ttu-id="a884e-158">Но если вы хотите использовать группы для электронной почты и совместной работы, рекомендуется создать Microsoft 365 [группу.](../create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="a884e-158">But if you want to use groups for email and collaboration, we recommend that you [create a Microsoft 365 group](../create-groups/create-groups.md) instead.</span></span> 

## <a name="related-content"></a><span data-ttu-id="a884e-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="a884e-159">Related content</span></span>

<span data-ttu-id="a884e-160">[Создание группы в Центр администрирования Microsoft 365](../create-groups/create-groups.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="a884e-160">[Create a group in the Microsoft 365 admin center](../create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="a884e-161">[Объяснение групп Microsoft 365 пользователям](../create-groups/explain-groups-knowledge-worker.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="a884e-161">[Explaining Microsoft 365 Groups to your users](../create-groups/explain-groups-knowledge-worker.md) (article)</span></span>\
<span data-ttu-id="a884e-162">[Управление группой в Центр администрирования Microsoft 365](../create-groups/manage-groups.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="a884e-162">[Manage a group in the Microsoft 365 admin center](../create-groups/manage-groups.md) (article)</span></span>