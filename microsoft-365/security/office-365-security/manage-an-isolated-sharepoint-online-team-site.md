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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Управляйте изолированным сайтом группы SharePoint Online, добавляйте новых пользователей и группы, удаляйте пользователей и группы, а также создавайте в подкадровку документов с пользовательскими разрешениями.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e354de77b70ea69d69e201bd3b1d40ea32cc5b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289525"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="1ad70-103">Управление изолированным сайтом группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1ad70-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1ad70-104">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="1ad70-104">**Applies to**</span></span>
- [<span data-ttu-id="1ad70-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1ad70-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="1ad70-106">Microsoft Defender для Office 365 (план 1)</span><span class="sxs-lookup"><span data-stu-id="1ad70-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="1ad70-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1ad70-107">SharePoint Online</span></span> 

 <span data-ttu-id="1ad70-108">**Сводка.** Управляйте изолированным сайтом группы SharePoint Online с помощью этих процедур.</span><span class="sxs-lookup"><span data-stu-id="1ad70-108">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>

<span data-ttu-id="1ad70-109">В этой статье описаны основные операции по управлению изолированным сайтом группы SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1ad70-109">This article describes common management operations for an isolated SharePoint Online team site.</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="1ad70-110">Добавление нового пользователя</span><span class="sxs-lookup"><span data-stu-id="1ad70-110">Add a new user</span></span>

<span data-ttu-id="1ad70-111">Когда к сайту присоединяется новый участник, необходимо определить его роль.</span><span class="sxs-lookup"><span data-stu-id="1ad70-111">When someone new joins the site, you must decide their level of participation in the site:</span></span>

- <span data-ttu-id="1ad70-112">Администрирование: добавьте новую учетную запись пользователя в группу доступа "Администраторы сайта".</span><span class="sxs-lookup"><span data-stu-id="1ad70-112">Administration: Add the new user account to the site admins access group</span></span>

- <span data-ttu-id="1ad70-113">Активная совместная работа: добавьте учетную запись пользователя в группу доступа "Участники сайта".</span><span class="sxs-lookup"><span data-stu-id="1ad70-113">Active collaboration: Add the user account to the site members access group</span></span>

- <span data-ttu-id="1ad70-114">Просмотр: добавьте учетную запись пользователя в группу доступа "Посетители сайта".</span><span class="sxs-lookup"><span data-stu-id="1ad70-114">Viewing: Add the user account to the site viewers access group</span></span>

<span data-ttu-id="1ad70-115">Если вы управляете учетными записями пользователей и группами с помощью доменных служб Active Directory (AD DS), добавьте соответствующих пользователей в соответствующие группы доступа с помощью обычных процедур управления пользователями и группами AD DS и дождись синхронизации с подпиской.</span><span class="sxs-lookup"><span data-stu-id="1ad70-115">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="1ad70-116">Если вы управляете учетной записью пользователя и группами с помощью Microsoft 365, вы можете использовать Центр администрирования Microsoft 365 или Microsoft PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1ad70-116">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>

- <span data-ttu-id="1ad70-117">В Центре администрирования Microsoft 365 во sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span><span class="sxs-lookup"><span data-stu-id="1ad70-117">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>

- <span data-ttu-id="1ad70-118">Для PowerShell сначала подключите [модуль Azure Active Directory PowerShell для Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="1ad70-118">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="1ad70-119">Чтобы добавить учетную запись пользователя в группу доступа по имени участника-пользователя (UPN), используйте следующий блок команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1ad70-119">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="1ad70-120">Чтобы добавить учетную запись пользователя в группу доступа по отображаемому имени, используйте следующий блок команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1ad70-120">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="1ad70-121">Добавление новой группы</span><span class="sxs-lookup"><span data-stu-id="1ad70-121">Add a new group</span></span>

<span data-ttu-id="1ad70-122">Чтобы добавить доступ для всей группы, необходимо определить роль всех членов группы на сайте:</span><span class="sxs-lookup"><span data-stu-id="1ad70-122">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>

- <span data-ttu-id="1ad70-123">Администрирование: добавьте группу в группу доступа "Администраторы сайта".</span><span class="sxs-lookup"><span data-stu-id="1ad70-123">Administration: Add the group to the site admins access group</span></span>

- <span data-ttu-id="1ad70-124">Активная совместная работа: добавьте группу в группу доступа "Участники сайта".</span><span class="sxs-lookup"><span data-stu-id="1ad70-124">Active collaboration: Add the group to the site members access group</span></span>

- <span data-ttu-id="1ad70-125">Просмотр: добавьте группу в группу доступа "Посетители сайта".</span><span class="sxs-lookup"><span data-stu-id="1ad70-125">Viewing: Add the group to the site viewers access group</span></span>

<span data-ttu-id="1ad70-126">Если вы управляете учетными записями и группами пользователей с помощью AD DS, добавьте соответствующие группы в соответствующие группы с помощью обычных процедур управления пользователями и группами AD DS и дождись синхронизации с подпиской.</span><span class="sxs-lookup"><span data-stu-id="1ad70-126">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="1ad70-127">Если вы управляете учетной записью и группами пользователей с помощью Office 365, вы можете использовать Центр администрирования Microsoft 365 или PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1ad70-127">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="1ad70-128">В Центре администрирования Microsoft 365 во sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span><span class="sxs-lookup"><span data-stu-id="1ad70-128">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>

- <span data-ttu-id="1ad70-129">Для PowerShell сначала подключите [модуль Azure Active Directory PowerShell для Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="1ad70-129">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="1ad70-130">Затем используйте следующие команды PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1ad70-130">Then, use the following PowerShell commands:</span></span>

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="1ad70-131">Удаление пользователя</span><span class="sxs-lookup"><span data-stu-id="1ad70-131">Remove a user</span></span>

<span data-ttu-id="1ad70-132">Чтобы закрыть доступ к сайту для пользователя, удалите его из группы доступа, в которой он в данный момент состоит.</span><span class="sxs-lookup"><span data-stu-id="1ad70-132">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="1ad70-133">Администрирование: удалите учетную запись пользователя из группы доступа "Администраторы сайта".</span><span class="sxs-lookup"><span data-stu-id="1ad70-133">Administration: Remove the user account from the site admins access group</span></span>

- <span data-ttu-id="1ad70-134">Активная совместная работа: удалите учетную запись пользователя из группы доступа "Участники сайта".</span><span class="sxs-lookup"><span data-stu-id="1ad70-134">Active collaboration: Remove the user account from the site members access group</span></span>

- <span data-ttu-id="1ad70-135">Просмотр: удалите учетную запись пользователя из группы доступа "Посетители сайта".</span><span class="sxs-lookup"><span data-stu-id="1ad70-135">Viewing: Remove the user account from the site viewers access group</span></span>

<span data-ttu-id="1ad70-136">Если вы управляете учетными записями и группами пользователей с помощью AD DS, удалите соответствующих пользователей из соответствующих групп доступа с помощью обычных процедур управления пользователями и группами AD DS и дождись синхронизации с подпиской.</span><span class="sxs-lookup"><span data-stu-id="1ad70-136">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="1ad70-137">Если вы управляете учетной записью и группами пользователей с помощью Office 365, вы можете использовать Центр администрирования Microsoft 365 или PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1ad70-137">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="1ad70-138">В Центре администрирования Microsoft 365 во sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span><span class="sxs-lookup"><span data-stu-id="1ad70-138">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>

- <span data-ttu-id="1ad70-139">Для PowerShell сначала подключите [модуль Azure Active Directory PowerShell для Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="1ad70-139">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="1ad70-140">Чтобы удалить учетную запись пользователя из группы доступа по имени участника-пользователя, используйте следующий блок команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1ad70-140">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="1ad70-141">Чтобы удалить учетную запись пользователя из группы доступа по отображаемому имени, используйте следующий блок команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1ad70-141">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="1ad70-142">Удаление группы</span><span class="sxs-lookup"><span data-stu-id="1ad70-142">Remove a group</span></span>

<span data-ttu-id="1ad70-143">Чтобы закрыть доступ для всей группы, удалите ее из группы доступа, в которой она в данный момент состоит:</span><span class="sxs-lookup"><span data-stu-id="1ad70-143">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="1ad70-144">Администрирование: удалите группу из группы доступа "Администраторы сайта".</span><span class="sxs-lookup"><span data-stu-id="1ad70-144">Administration: Remove the group from the site admins access group</span></span>

- <span data-ttu-id="1ad70-145">Активная совместная работа: удалите группу из группы доступа "Участники сайта".</span><span class="sxs-lookup"><span data-stu-id="1ad70-145">Active collaboration: Remove the group from the site members access group</span></span>

- <span data-ttu-id="1ad70-146">Просмотр: удалите группу из группы доступа "Посетители сайта".</span><span class="sxs-lookup"><span data-stu-id="1ad70-146">Viewing: Remove the group from the site viewers access group</span></span>

<span data-ttu-id="1ad70-147">Если вы управляете учетными записями и группами пользователей с помощью Windows Server Active Directory, удалите соответствующие группы из соответствующих групп доступа с помощью обычных процедур управления пользователями и группами AD DS и дождись синхронизации с подпиской.</span><span class="sxs-lookup"><span data-stu-id="1ad70-147">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="1ad70-148">Если вы управляете учетной записью и группами пользователей с помощью Office 365, вы можете использовать Центр администрирования Microsoft 365 или PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1ad70-148">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="1ad70-149">В Центре администрирования Microsoft 365 во sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span><span class="sxs-lookup"><span data-stu-id="1ad70-149">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>

- <span data-ttu-id="1ad70-150">Для PowerShell сначала подключите [модуль Azure Active Directory PowerShell для Graph.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="1ad70-150">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="1ad70-151">Чтобы удалить группу из группы доступа по отображаемому имени, используйте следующий блок команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1ad70-151">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="1ad70-152">Создание вложенной папки документов с настраиваемыми разрешениями</span><span class="sxs-lookup"><span data-stu-id="1ad70-152">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="1ad70-p105">Группе людей, работающих на изолированном сайте, может потребоваться закрытое место для совместной работы. В SharePoint Online вы можете создать вложенную папку в папке сайта "Документы" и назначить ей особые разрешения. Пользователи без разрешений не увидят эту папку.</span><span class="sxs-lookup"><span data-stu-id="1ad70-p105">In some cases, a subset of the people working within the isolated site need a more private place to collaborate. For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions. Those without permissions will not see the subfolder.</span></span>

<span data-ttu-id="1ad70-156">Чтобы создать вложенную папку документов с настраиваемыми разрешениями, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="1ad70-156">To create a documents subfolder with custom permissions, do the following:</span></span>

1. <span data-ttu-id="1ad70-157">Во sign in to an account that is a member of the admins access group for the site.</span><span class="sxs-lookup"><span data-stu-id="1ad70-157">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="1ad70-158">Справку см. в статье [Вход в Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="1ad70-158">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="1ad70-159">Перейдите к изолированному сайту группы и нажмите **Документы**.</span><span class="sxs-lookup"><span data-stu-id="1ad70-159">Go to the isolated team site and click **Documents**.</span></span>

3. <span data-ttu-id="1ad70-160">В папке "Документы" перейдите к нужной папке, создайте вложенную папку для настраиваемых разрешений и откройте ее.</span><span class="sxs-lookup"><span data-stu-id="1ad70-160">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>

4. <span data-ttu-id="1ad70-161">Щелкните **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="1ad70-161">Click **Share**.</span></span>

5. <span data-ttu-id="1ad70-162">Нажмите **Доступ > Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="1ad70-162">Click **Shared with > Advanced**.</span></span>

6. <span data-ttu-id="1ad70-163">Нажмите **Прекратить наследование разрешений**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1ad70-163">Click **Stop inheriting permissions**, and then click **OK**.</span></span>

7. <span data-ttu-id="1ad70-164">Щелкните **Общий доступ**.</span><span class="sxs-lookup"><span data-stu-id="1ad70-164">Click **Share**.</span></span>

8. <span data-ttu-id="1ad70-165">Нажмите **Доступ > Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="1ad70-165">Click **Shared with > Advanced**.</span></span>

9. <span data-ttu-id="1ad70-166">Нажмите **Предоставить разрешения > Доступ > Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="1ad70-166">Click **Grant Permissions > Shared with > Advanced**.</span></span>

10. <span data-ttu-id="1ad70-167">On the permissions page, click **\<site name> Members in the list**.</span><span class="sxs-lookup"><span data-stu-id="1ad70-167">On the permissions page, click **\<site name> Members in the list**.</span></span>

11. <span data-ttu-id="1ad70-168">На странице **\<site name> "Участники"** выберите контрольный знак рядом с группой доступа "Участники сайта", щелкните "Действия", "Удалить пользователей из группы" и нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="1ad70-168">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>

12. <span data-ttu-id="1ad70-169">Чтобы добавить участников в эту вложенную папку, нажмите **Создать > Добавить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="1ad70-169">To add specific members to this subfolder, click **New > Add users**.</span></span>

13. <span data-ttu-id="1ad70-170">В диалоговом окне **Общий доступ** введите имена учетных записей пользователей, которые могут совместно работать над файлами в папке, и нажмите кнопку **Поделиться**.</span><span class="sxs-lookup"><span data-stu-id="1ad70-170">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>

14. <span data-ttu-id="1ad70-171">Обновите веб-страницу, чтобы увидеть новые результаты.</span><span class="sxs-lookup"><span data-stu-id="1ad70-171">Refresh the web page to see the new results.</span></span>

15. <span data-ttu-id="1ad70-172">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span><span class="sxs-lookup"><span data-stu-id="1ad70-172">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>

16. <span data-ttu-id="1ad70-173">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span><span class="sxs-lookup"><span data-stu-id="1ad70-173">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>

17. <span data-ttu-id="1ad70-174">Закройте вкладку **Пользователи и группы** в браузере.</span><span class="sxs-lookup"><span data-stu-id="1ad70-174">Close the **People and Groups** tab in your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ad70-175">См. также</span><span class="sxs-lookup"><span data-stu-id="1ad70-175">See Also</span></span>

[<span data-ttu-id="1ad70-176">Изолированные сайты групп SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1ad70-176">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="1ad70-177">Разработка изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1ad70-177">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="1ad70-178">Развертывание изолированного сайта группы SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1ad70-178">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
