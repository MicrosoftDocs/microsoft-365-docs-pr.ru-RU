---
title: Управление разрешениями пользователей на создание групп Office 365
f1.keywords:
- NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Узнайте, как управлять тем, какие пользователи могут создавать группы Office 365.
ms.openlocfilehash: 1f0d3109d1102c740a9be0b670e618eac982e6e2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245465"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="a109b-103">Управление разрешениями пользователей на создание групп Office 365</span><span class="sxs-lookup"><span data-stu-id="a109b-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="a109b-104">Благодаря тому, что пользователи могут легко создавать группы Office 365, вам не будет приходиться это делать.</span><span class="sxs-lookup"><span data-stu-id="a109b-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="a109b-105">Однако вам может потребоваться ограничивать права на создание групп или предоставлять их.</span><span class="sxs-lookup"><span data-stu-id="a109b-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="a109b-106">В этой статье приведены инструкции по отключению возможности создавать группы **во всех службах Office 365, где они используются**:</span><span class="sxs-lookup"><span data-stu-id="a109b-106">This article explains how to disable the ability to create groups **in all Office 365 services that use groups**:</span></span> 
  
- <span data-ttu-id="a109b-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="a109b-107">Outlook</span></span>
    
- <span data-ttu-id="a109b-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="a109b-108">SharePoint</span></span>
    
- <span data-ttu-id="a109b-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="a109b-109">Yammer</span></span>
    
- <span data-ttu-id="a109b-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a109b-110">Microsoft Teams</span></span>

- <span data-ttu-id="a109b-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="a109b-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="a109b-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="a109b-112">StaffHub</span></span>
    
- <span data-ttu-id="a109b-113">Планировщик</span><span class="sxs-lookup"><span data-stu-id="a109b-113">Planner</span></span>
    
- <span data-ttu-id="a109b-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="a109b-114">PowerBI</span></span>

- <span data-ttu-id="a109b-115">План</span><span class="sxs-lookup"><span data-stu-id="a109b-115">Roadmap</span></span>
    
<span data-ttu-id="a109b-116">Можно ограничить создание групп Office 365 членами определенной группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="a109b-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="a109b-117">Чтобы настроить это, используйте Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a109b-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="a109b-118">В этой статье рассказывается о необходимых действиях.</span><span class="sxs-lookup"><span data-stu-id="a109b-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="a109b-119">Действия, описанные в этой статье, не позволят членам определенных ролей создавать группы.</span><span class="sxs-lookup"><span data-stu-id="a109b-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="a109b-120">Глобальные администраторы Office 365 могут создавать группы с помощью любых средств, таких как центр администрирования Майкрософт 365, планировщик, Teams, Exchange и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="a109b-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="a109b-121">Другие роли могут создавать группы с помощью ограниченных средств, перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="a109b-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="a109b-122">Администратор Exchange: центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="a109b-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="a109b-123">Поддержка уровня партнеров 1: центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="a109b-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="a109b-124">Поддержка уровня партнеров 2: центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="a109b-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="a109b-125">Записи в каталогах: Azure AD</span><span class="sxs-lookup"><span data-stu-id="a109b-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="a109b-126">Администратор SharePoint: центр администрирования SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="a109b-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="a109b-127">Администратор службы teams: центр администрирования Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="a109b-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="a109b-128">Администратор управления пользователями: центр администрирования Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="a109b-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="a109b-129">Если вы входите в одну из этих ролей, вы можете создать Группы Office 365 для пользователей с ограниченными правами, а затем назначить пользователя владельцем группы.</span><span class="sxs-lookup"><span data-stu-id="a109b-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="a109b-130">Пользователи с этой ролью могут создавать подключенные группы в Yammer независимо от параметров PowerShell, которые могут препятствовать созданию.</span><span class="sxs-lookup"><span data-stu-id="a109b-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="a109b-131">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="a109b-131">Licensing requirements</span></span>

<span data-ttu-id="a109b-132">Для управления разрешениями групп для следующих людей требуются лицензии Azure AD Premium или Azure AD Basic EDU, назначенные им:</span><span class="sxs-lookup"><span data-stu-id="a109b-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="a109b-133">Администратор, который настраивает эти параметры создания групп</span><span class="sxs-lookup"><span data-stu-id="a109b-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="a109b-134">Члены группы безопасности, которым разрешено создавать группы</span><span class="sxs-lookup"><span data-stu-id="a109b-134">The members of the security group who are allowed to create Groups</span></span>

<span data-ttu-id="a109b-135">Следующим пользователям не нужны лицензии Azure AD Premium или Azure AD Basic EDU:</span><span class="sxs-lookup"><span data-stu-id="a109b-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="a109b-136">Пользователи, являющиеся членами групп Office 365 и у которых нет возможности создавать другие группы.</span><span class="sxs-lookup"><span data-stu-id="a109b-136">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="a109b-137">Шаг 1. Создание группы безопасности для пользователей, которые должны создавать Группы Office 365</span><span class="sxs-lookup"><span data-stu-id="a109b-137">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="a109b-138">Для контроля того, кто может создавать группы, можно использовать только одну группу безопасности в Организации.</span><span class="sxs-lookup"><span data-stu-id="a109b-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="a109b-139">Но вы можете вложить в нее другие группы безопасности как участников.</span><span class="sxs-lookup"><span data-stu-id="a109b-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="a109b-140">Например, группой безопасности может быть группа Allow Group Creation, участниками которой являются группы Microsoft Planner Users и Exchange Online Users.</span><span class="sxs-lookup"><span data-stu-id="a109b-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="a109b-141">Администраторы из перечисленных выше ролей не должны быть членами этой группы: они сохраняют возможность создавать группы.</span><span class="sxs-lookup"><span data-stu-id="a109b-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a109b-142">Обязательно используйте **группу безопасности** , чтобы ограничить круг пользователей, которые могут создавать группы.</span><span class="sxs-lookup"><span data-stu-id="a109b-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="a109b-143">Ее участники не смогут создать группу из SharePoint, так как SharePoint проверяет наличие группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="a109b-143">If you try to use an Office 365 Group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="a109b-144">В центре администрирования перейдите на страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> **группы** \> .</span><span class="sxs-lookup"><span data-stu-id="a109b-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="a109b-145">Нажмите кнопку **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="a109b-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="a109b-146">Выберите пункт **Безопасность** в качестве типа группы.</span><span class="sxs-lookup"><span data-stu-id="a109b-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="a109b-147">Запомните имя группы.</span><span class="sxs-lookup"><span data-stu-id="a109b-147">Remember the name of the group!</span></span> <span data-ttu-id="a109b-148">Он потребуется позже.</span><span class="sxs-lookup"><span data-stu-id="a109b-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="a109b-149">Завершите настройку группы безопасности, Добавление пользователей или других групп безопасности, которые будут иметь возможность создавать группы в Организации.</span><span class="sxs-lookup"><span data-stu-id="a109b-149">Finish setting up the security group, adding people or other security groups who you want to be able to create Groups in your org.</span></span>
    
<span data-ttu-id="a109b-150">Подробные инструкции приведены в разделе [Создание, изменение и удаление группы безопасности в центре администрирования Microsoft 365](../email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="a109b-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
  
## <a name="step-2-install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="a109b-151">Шаг 2: Установка ознакомительной версии Azure Active Directory PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="a109b-151">Step 2: Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

<span data-ttu-id="a109b-152">Для выполнения этих процедур требуется предварительная версия Azure Active Directory PowerShell для Graph.</span><span class="sxs-lookup"><span data-stu-id="a109b-152">These procedures require the preview version of the Azure Active Directory PowerShell for Graph.</span></span> <span data-ttu-id="a109b-153">Эта версия не будет работать.</span><span class="sxs-lookup"><span data-stu-id="a109b-153">The GA version will not work.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a109b-154">Вы не можете одновременно установить версии Preview и GA на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="a109b-154">You cannot install both the preview and GA versions on the same computer at the same time.</span></span> <span data-ttu-id="a109b-155">Вы можете установить модуль в Windows 10, Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="a109b-155">You can install the module on Windows 10, Windows Server 2016.</span></span>

  
<span data-ttu-id="a109b-156">Рекомендуется  *всегда*  следить за актуальностью компонентов: удалите старую версию AzureADPreview или AzureAD и установите последнюю.</span><span class="sxs-lookup"><span data-stu-id="a109b-156">As a best practice, we recommend  *always*  staying current: uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
1. <span data-ttu-id="a109b-157">В строке поиска введите Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a109b-157">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="a109b-158">Щелкните программу **Windows PowerShell** правой кнопкой мыши и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="a109b-158">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
    
    ![Откройте PowerShell с помощью команды "Запуск от имени администратора".](../media/52517af8-c7b0-4c8f-b2f3-0f82f9d5ace1.png)
  
2. <span data-ttu-id="a109b-160">Проверьте установленный модуль:</span><span class="sxs-lookup"><span data-stu-id="a109b-160">Check installed module:</span></span>
    
    ```
    Get-InstalledModule -Name "AzureAD*"
    ```

3. <span data-ttu-id="a109b-161">Чтобы удалить предыдущую версию AzureADPreview или AzureAD, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a109b-161">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
    ```
    Uninstall-Module AzureADPreview
    ```

    <span data-ttu-id="a109b-162">или</span><span class="sxs-lookup"><span data-stu-id="a109b-162">or</span></span>
  
    ```
    Uninstall-Module AzureAD
    ```

4. <span data-ttu-id="a109b-163">To install the latest version of AzureADPreview, run this command:</span><span class="sxs-lookup"><span data-stu-id="a109b-163">To install the latest version of AzureADPreview, run this command:</span></span>
  
    ```
    Install-Module AzureADPreview
    ```

    <span data-ttu-id="a109b-164">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. </span><span class="sxs-lookup"><span data-stu-id="a109b-164">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>

<span data-ttu-id="a109b-165">Оставьте окно PowerShell открытым для шага 3 ниже.</span><span class="sxs-lookup"><span data-stu-id="a109b-165">Leave the PowerShell window open for Step 3, below.</span></span>
  
## <a name="step-3-run-powershell-commands"></a><span data-ttu-id="a109b-166">Шаг 3: выполнение команд PowerShell</span><span class="sxs-lookup"><span data-stu-id="a109b-166">Step 3: Run PowerShell commands</span></span>

<span data-ttu-id="a109b-167">Скопируйте приведенный ниже скрипт в текстовый редактор, например "Блокнот" или [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="a109b-167">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="a109b-168">Замените \* \<секуритиграупнаме\> \* именем группы безопасности, которую вы создали.</span><span class="sxs-lookup"><span data-stu-id="a109b-168">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="a109b-169">Пример:</span><span class="sxs-lookup"><span data-stu-id="a109b-169">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="a109b-170">Сохраните файл как Граупкреаторс. ps1.</span><span class="sxs-lookup"><span data-stu-id="a109b-170">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="a109b-171">В окне PowerShell перейдите к папке, в которую был сохранен файл (введите "CD <FileLocation>").</span><span class="sxs-lookup"><span data-stu-id="a109b-171">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="a109b-172">Выполните сценарий, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a109b-172">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="a109b-173">После появления соответствующего запроса [Войдите в систему с учетной записью администратора](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) .</span><span class="sxs-lookup"><span data-stu-id="a109b-173">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="a109b-174">В последней строке сценария отобразятся обновленные параметры:</span><span class="sxs-lookup"><span data-stu-id="a109b-174">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="a109b-176">Если в будущем требуется изменить группу безопасности, можно повторно запустить скрипт с именем новой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="a109b-176">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="a109b-177">Если вы хотите отключить ограничение на создание групп и снова разрешить всем пользователям создавать группы, задайте для параметра $GroupName значение "" и $AllowGroupCreation значение true, а затем повторно запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="a109b-177">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="a109b-178">Шаг 4: Убедитесь, что он работает</span><span class="sxs-lookup"><span data-stu-id="a109b-178">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="a109b-179">Войдите в Office 365 с учетной записью пользователя, у которого нет возможности создавать группы.</span><span class="sxs-lookup"><span data-stu-id="a109b-179">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="a109b-180">То есть они не являются участниками группы безопасности, созданной или администратором.</span><span class="sxs-lookup"><span data-stu-id="a109b-180">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="a109b-181">Выберите плитку **планировщика** .</span><span class="sxs-lookup"><span data-stu-id="a109b-181">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="a109b-182">В планировщике выберите **новый план** в левой области навигации, чтобы создать план.</span><span class="sxs-lookup"><span data-stu-id="a109b-182">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="a109b-183">Следует получить сообщение о том, что планирование и создание групп отключены.</span><span class="sxs-lookup"><span data-stu-id="a109b-183">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="a109b-184">Повторите ту же процедуру с членом группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="a109b-184">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="a109b-185">Если участники группы безопасности не могут создавать группы, убедитесь, что они не блокируются с помощью [политики почтовых ящиков OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="a109b-185">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="a109b-186">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="a109b-186">Related articles</span></span>

[<span data-ttu-id="a109b-187">Начало работы с Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a109b-187">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="a109b-188">Настройка управления группами самостоятельных служб в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a109b-188">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

<span data-ttu-id="a109b-189">[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span><span class="sxs-lookup"><span data-stu-id="a109b-189">[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

[<span data-ttu-id="a109b-190">Командлеты Azure Active Directory для настройки параметров группы</span><span class="sxs-lookup"><span data-stu-id="a109b-190">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
