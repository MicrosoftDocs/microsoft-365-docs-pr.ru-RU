---
title: Управление изолированным сайтом группы SharePoint Online
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Управлять изолированным сайтом группы SharePoint Online, добавлять новых пользователей и группы, удалять пользователей и группы, а также создавать вложенную папку документов с пользовательскими разрешениями.
ms.openlocfilehash: 43329aa72b3729200007441ce73838a7d6a60f55
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755382"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="994fa-103">Управление изолированным сайтом группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="994fa-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="994fa-104">**Сводка.** Управляйте изолированным сайтом группы SharePoint Online с помощью этих процедур.</span><span class="sxs-lookup"><span data-stu-id="994fa-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="994fa-105">В этой статье описаны основные операции по управлению изолированным сайтом группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="994fa-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="994fa-106">Добавление нового пользователя</span><span class="sxs-lookup"><span data-stu-id="994fa-106">Add a new user</span></span>

<span data-ttu-id="994fa-107">Когда к сайту присоединяется новый участник, необходимо определить его роль.</span><span class="sxs-lookup"><span data-stu-id="994fa-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="994fa-108">Администрирование: добавьте новую учетную запись пользователя в группу доступа "Администраторы сайта".</span><span class="sxs-lookup"><span data-stu-id="994fa-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="994fa-109">Активная совместная работа: добавьте учетную запись пользователя в группу доступа "Участники сайта".</span><span class="sxs-lookup"><span data-stu-id="994fa-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="994fa-110">Просмотр: добавьте учетную запись пользователя в группу доступа "Посетители сайта".</span><span class="sxs-lookup"><span data-stu-id="994fa-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="994fa-111">Если вы управляете учетными записями и группами пользователей с помощью доменных служб Active Directory (AD DS), добавьте соответствующих пользователей в соответствующие группы доступа, используя обычные процедуры управления пользователями и группами AD DS, и дождитесь синхронизации с подпиской.</span><span class="sxs-lookup"><span data-stu-id="994fa-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="994fa-112">Если вы управляете учетными записями и группами пользователей с помощью Microsoft 365, вы можете использовать центр администрирования Microsoft 365 или Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="994fa-112">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="994fa-113">Для центра администрирования Microsoft 365 войдите с помощью учетной записи пользователя, которой назначена роль администратора учетной записи пользователя или администратора организации, и используйте группы, чтобы добавить соответствующих пользователей в соответствующие группы доступа.</span><span class="sxs-lookup"><span data-stu-id="994fa-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="994fa-114">Для PowerShell сначала [подключитесь к модулю PowerShell Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="994fa-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="994fa-115">Чтобы добавить учетную запись пользователя в группу доступа по имени участника-пользователя (UPN), используйте следующий блок команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="994fa-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="994fa-116">Чтобы добавить учетную запись пользователя в группу доступа по отображаемому имени, используйте следующий блок команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="994fa-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="994fa-117">Добавление новой группы</span><span class="sxs-lookup"><span data-stu-id="994fa-117">Add a new group</span></span>

<span data-ttu-id="994fa-118">Чтобы добавить доступ для всей группы, необходимо определить роль всех членов группы на сайте:</span><span class="sxs-lookup"><span data-stu-id="994fa-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="994fa-119">Администрирование: добавьте группу в группу доступа "Администраторы сайта".</span><span class="sxs-lookup"><span data-stu-id="994fa-119">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="994fa-120">Активная совместная работа: добавьте группу в группу доступа "Участники сайта".</span><span class="sxs-lookup"><span data-stu-id="994fa-120">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="994fa-121">Просмотр: добавьте группу в группу доступа "Посетители сайта".</span><span class="sxs-lookup"><span data-stu-id="994fa-121">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="994fa-122">Если вы управляете учетными записями и группами пользователей с помощью доменных служб Active Directory, добавьте соответствующие группы в соответствующие группы, используя обычные процедуры управления пользователями и группами AD DS, и дождитесь синхронизации с подпиской.</span><span class="sxs-lookup"><span data-stu-id="994fa-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="994fa-123">Если вы управляете учетными записями и группами пользователей с помощью Office 365, вы можете использовать центр администрирования Microsoft 365 или PowerShell:</span><span class="sxs-lookup"><span data-stu-id="994fa-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="994fa-124">Для центра администрирования Microsoft 365 войдите в систему, используя учетную запись пользователя, которой назначена роль администратора учетных записей или администратора организации, и используйте группы для добавления соответствующих групп в соответствующие группы доступа.</span><span class="sxs-lookup"><span data-stu-id="994fa-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="994fa-125">Для PowerShell сначала [подключитесь к модулю PowerShell Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="994fa-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="994fa-126">Затем используйте следующие команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="994fa-126">Then, use the following PowerShell commands:</span></span>
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="994fa-127">Удаление пользователя</span><span class="sxs-lookup"><span data-stu-id="994fa-127">Remove a user</span></span>

<span data-ttu-id="994fa-128">Чтобы закрыть доступ к сайту для пользователя, удалите его из группы доступа, в которой он в данный момент состоит.</span><span class="sxs-lookup"><span data-stu-id="994fa-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="994fa-129">Администрирование: удалите учетную запись пользователя из группы доступа "Администраторы сайта".</span><span class="sxs-lookup"><span data-stu-id="994fa-129">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="994fa-130">Активная совместная работа: удалите учетную запись пользователя из группы доступа "Участники сайта".</span><span class="sxs-lookup"><span data-stu-id="994fa-130">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="994fa-131">Просмотр: удалите учетную запись пользователя из группы доступа "Посетители сайта".</span><span class="sxs-lookup"><span data-stu-id="994fa-131">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="994fa-132">Если вы управляете учетными записями и группами пользователей с помощью доменных служб Active Directory, удалите соответствующих пользователей из соответствующих групп доступа, используя обычные процедуры управления пользователями и группами AD DS, и дождитесь синхронизации с подпиской.</span><span class="sxs-lookup"><span data-stu-id="994fa-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="994fa-133">Если вы управляете учетными записями и группами пользователей с помощью Office 365, вы можете использовать центр администрирования Microsoft 365 или PowerShell:</span><span class="sxs-lookup"><span data-stu-id="994fa-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="994fa-134">Для центра администрирования Microsoft 365 войдите с помощью учетной записи пользователя, которой назначена роль администратора учетной записи пользователя или администратора организации, и используйте группы для удаления соответствующих пользователей из соответствующих групп доступа.</span><span class="sxs-lookup"><span data-stu-id="994fa-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="994fa-135">Для PowerShell сначала [подключитесь к модулю PowerShell Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="994fa-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="994fa-136">Чтобы удалить учетную запись пользователя из группы доступа по имени участника-пользователя, используйте следующий блок команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="994fa-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="994fa-137">Чтобы удалить учетную запись пользователя из группы доступа по отображаемому имени, используйте следующий блок команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="994fa-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="994fa-138">Удаление группы</span><span class="sxs-lookup"><span data-stu-id="994fa-138">Remove a group</span></span>

<span data-ttu-id="994fa-139">Чтобы закрыть доступ для всей группы, удалите ее из группы доступа, в которой она в данный момент состоит:</span><span class="sxs-lookup"><span data-stu-id="994fa-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="994fa-140">Администрирование: удалите группу из группы доступа "Администраторы сайта".</span><span class="sxs-lookup"><span data-stu-id="994fa-140">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="994fa-141">Активная совместная работа: удалите группу из группы доступа "Участники сайта".</span><span class="sxs-lookup"><span data-stu-id="994fa-141">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="994fa-142">Просмотр: удалите группу из группы доступа "Посетители сайта".</span><span class="sxs-lookup"><span data-stu-id="994fa-142">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="994fa-143">Если вы управляете учетными записями и группами пользователей с помощью Windows Server Active Directory, удалите соответствующие группы из соответствующих групп доступа, используя обычные процедуры управления пользователями и группами AD DS, и дождитесь синхронизации с подпиской.</span><span class="sxs-lookup"><span data-stu-id="994fa-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="994fa-144">Если вы управляете учетными записями и группами пользователей с помощью Office 365, вы можете использовать центр администрирования Microsoft 365 или PowerShell:</span><span class="sxs-lookup"><span data-stu-id="994fa-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="994fa-145">Для центра администрирования Microsoft 365 войдите с помощью учетной записи пользователя, которой назначена роль администратора учетной записи пользователя или администратора организации, и используйте группы для удаления соответствующих групп из соответствующих групп доступа.</span><span class="sxs-lookup"><span data-stu-id="994fa-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="994fa-146">Для PowerShell сначала [подключитесь к модулю PowerShell Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="994fa-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="994fa-147">Чтобы удалить группу из группы доступа по отображаемому имени, используйте следующий блок команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="994fa-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="994fa-148">Создание вложенной папки документов с настраиваемыми разрешениями</span><span class="sxs-lookup"><span data-stu-id="994fa-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="994fa-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span><span class="sxs-lookup"><span data-stu-id="994fa-149">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="994fa-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span><span class="sxs-lookup"><span data-stu-id="994fa-150">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="994fa-151">Those without permissions will not see the subfolder.</span><span class="sxs-lookup"><span data-stu-id="994fa-151">Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="994fa-152">Чтобы создать вложенную папку документов с настраиваемыми разрешениями, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="994fa-152">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="994fa-153">Войдите в учетную запись, которая является членом группы доступа "Администраторы" для сайта.</span><span class="sxs-lookup"><span data-stu-id="994fa-153">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="994fa-154">Справку см. в статье [Вход в Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="994fa-154">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="994fa-155">Перейдите к изолированному сайту группы и нажмите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="994fa-155">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="994fa-156">В папке "Документы" перейдите к нужной папке, создайте вложенную папку для настраиваемых разрешений и откройте ее.</span><span class="sxs-lookup"><span data-stu-id="994fa-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="994fa-157">Щелкните **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="994fa-157">Click **Share**.</span></span>
    
5. <span data-ttu-id="994fa-158">Нажмите **Доступ > Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="994fa-158">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="994fa-159">Нажмите **Прекратить наследование разрешений**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="994fa-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="994fa-160">Щелкните **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="994fa-160">Click **Share**.</span></span>
    
8. <span data-ttu-id="994fa-161">Нажмите **Доступ > Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="994fa-161">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="994fa-162">Нажмите **Предоставить разрешения > Доступ > Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="994fa-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="994fa-163">On the permissions page, click **\<site name> Members in the list**.</span><span class="sxs-lookup"><span data-stu-id="994fa-163">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="994fa-164">На странице \*\* \<site name> Участники\*\* установите флажок рядом с группой доступ участников сайта, щелкните **действия**, выберите **удалить пользователей из группы**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="994fa-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="994fa-165">Чтобы добавить участников в эту вложенную папку, нажмите **Создать > Добавить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="994fa-165">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="994fa-166">В диалоговом окне **Общий доступ** введите имена учетных записей пользователей, которые могут совместно работать над файлами в папке, и нажмите кнопку **Поделиться**.</span><span class="sxs-lookup"><span data-stu-id="994fa-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="994fa-167">Обновите веб-страницу, чтобы увидеть новые результаты.</span><span class="sxs-lookup"><span data-stu-id="994fa-167">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="994fa-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span><span class="sxs-lookup"><span data-stu-id="994fa-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="994fa-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span><span class="sxs-lookup"><span data-stu-id="994fa-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="994fa-170">Закройте вкладку **Пользователи и группы** в браузере.</span><span class="sxs-lookup"><span data-stu-id="994fa-170">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="994fa-171">См. также</span><span class="sxs-lookup"><span data-stu-id="994fa-171">See Also</span></span>

[<span data-ttu-id="994fa-172">Изолированные сайты групп SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="994fa-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="994fa-173">Разработка изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="994fa-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="994fa-174">Развертывание изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="994fa-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



