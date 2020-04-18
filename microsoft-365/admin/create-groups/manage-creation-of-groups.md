---
title: Управление разрешениями пользователей на создание групп Office 365
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
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
ms.openlocfilehash: d31690cb6438c6563b01e0597f7f2b1ff96e3b9a
ms.sourcegitcommit: 0da80ba7b504841c502ab06fea659a985c06fe8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/17/2020
ms.locfileid: "43547590"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="68142-103">Управление разрешениями пользователей на создание групп Office 365</span><span class="sxs-lookup"><span data-stu-id="68142-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="68142-104">Благодаря тому, что пользователи могут легко создавать группы Office 365, вам не будет приходиться это делать.</span><span class="sxs-lookup"><span data-stu-id="68142-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="68142-105">Однако вам может потребоваться ограничивать права на создание групп или предоставлять их.</span><span class="sxs-lookup"><span data-stu-id="68142-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="68142-106">В этой статье объясняется, как отключить возможность создания групп во всех службах Office 365, использующих группы, в том числе:</span><span class="sxs-lookup"><span data-stu-id="68142-106">This article explains how to disable the ability to create groups in all Office 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="68142-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="68142-107">Outlook</span></span>
    
- <span data-ttu-id="68142-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="68142-108">SharePoint</span></span>
    
- <span data-ttu-id="68142-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="68142-109">Yammer</span></span>
    
- <span data-ttu-id="68142-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="68142-110">Microsoft Teams</span></span>

- <span data-ttu-id="68142-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="68142-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="68142-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="68142-112">StaffHub</span></span>
    
- <span data-ttu-id="68142-113">Планировщик</span><span class="sxs-lookup"><span data-stu-id="68142-113">Planner</span></span>
    
- <span data-ttu-id="68142-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="68142-114">PowerBI</span></span>

- <span data-ttu-id="68142-115">План</span><span class="sxs-lookup"><span data-stu-id="68142-115">Roadmap</span></span>
    
<span data-ttu-id="68142-116">Можно ограничить создание групп Office 365 членами определенной группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="68142-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="68142-117">Чтобы настроить это, используйте Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68142-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="68142-118">В этой статье рассказывается о необходимых действиях.</span><span class="sxs-lookup"><span data-stu-id="68142-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="68142-119">Действия, описанные в этой статье, не позволят членам определенных ролей создавать группы.</span><span class="sxs-lookup"><span data-stu-id="68142-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="68142-120">Глобальные администраторы Office 365 могут создавать группы с помощью любых средств, таких как центр администрирования Майкрософт 365, планировщик, Teams, Exchange и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="68142-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="68142-121">Другие роли могут создавать группы с помощью ограниченных средств, перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="68142-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="68142-122">Администратор Exchange: центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="68142-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="68142-123">Поддержка уровня партнеров 1: центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="68142-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="68142-124">Поддержка уровня партнеров 2: центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="68142-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="68142-125">Записи в каталогах: Azure AD</span><span class="sxs-lookup"><span data-stu-id="68142-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="68142-126">Администратор SharePoint: центр администрирования SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="68142-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="68142-127">Администратор службы teams: центр администрирования Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="68142-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="68142-128">Администратор управления пользователями: центр администрирования Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="68142-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="68142-129">Если вы входите в одну из этих ролей, вы можете создать Группы Office 365 для пользователей с ограниченными правами, а затем назначить пользователя владельцем группы.</span><span class="sxs-lookup"><span data-stu-id="68142-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="68142-130">Пользователи с этой ролью могут создавать подключенные группы в Yammer независимо от параметров PowerShell, которые могут препятствовать созданию.</span><span class="sxs-lookup"><span data-stu-id="68142-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="68142-131">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="68142-131">Licensing requirements</span></span>

<span data-ttu-id="68142-132">Для управления разрешениями групп для следующих людей требуются лицензии Azure AD Premium или Azure AD Basic EDU, назначенные им:</span><span class="sxs-lookup"><span data-stu-id="68142-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="68142-133">Администратор, который настраивает эти параметры создания групп</span><span class="sxs-lookup"><span data-stu-id="68142-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="68142-134">Члены группы безопасности, которым разрешено создавать группы</span><span class="sxs-lookup"><span data-stu-id="68142-134">The members of the security group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="68142-135">Дополнительные сведения о назначении лицензий Azure можно найти [в статье назначение и удаление лицензий на портале Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) .</span><span class="sxs-lookup"><span data-stu-id="68142-135">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="68142-136">Следующим пользователям не нужны лицензии Azure AD Premium или Azure AD Basic EDU:</span><span class="sxs-lookup"><span data-stu-id="68142-136">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="68142-137">Пользователи, являющиеся членами групп Office 365 и у которых нет возможности создавать другие группы.</span><span class="sxs-lookup"><span data-stu-id="68142-137">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="68142-138">Шаг 1. Создание группы безопасности для пользователей, которые должны создавать Группы Office 365</span><span class="sxs-lookup"><span data-stu-id="68142-138">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="68142-139">Для контроля того, кто может создавать группы, можно использовать только одну группу безопасности в Организации.</span><span class="sxs-lookup"><span data-stu-id="68142-139">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="68142-140">Но вы можете вложить в нее другие группы безопасности как участников.</span><span class="sxs-lookup"><span data-stu-id="68142-140">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="68142-141">Например, группой безопасности может быть группа Allow Group Creation, участниками которой являются группы Microsoft Planner Users и Exchange Online Users.</span><span class="sxs-lookup"><span data-stu-id="68142-141">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="68142-142">Администраторы из перечисленных выше ролей не должны быть членами этой группы: они сохраняют возможность создавать группы.</span><span class="sxs-lookup"><span data-stu-id="68142-142">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68142-143">Обязательно используйте **группу безопасности** , чтобы ограничить круг пользователей, которые могут создавать группы.</span><span class="sxs-lookup"><span data-stu-id="68142-143">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="68142-144">Если вы попытаетесь использовать группу Office 365, участники не смогут создать группу из SharePoint, так как она проверяет группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="68142-144">If you try to use an Office 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="68142-145">В центре администрирования перейдите на страницу <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">группы</a> **группы** \> .</span><span class="sxs-lookup"><span data-stu-id="68142-145">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="68142-146">Нажмите кнопку **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="68142-146">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="68142-147">Выберите пункт **Безопасность** в качестве типа группы.</span><span class="sxs-lookup"><span data-stu-id="68142-147">Choose **Security** as the group type.</span></span> <span data-ttu-id="68142-148">Запомните имя группы.</span><span class="sxs-lookup"><span data-stu-id="68142-148">Remember the name of the group!</span></span> <span data-ttu-id="68142-149">Он потребуется позже.</span><span class="sxs-lookup"><span data-stu-id="68142-149">You'll need it later.</span></span>
  
4. <span data-ttu-id="68142-150">Завершите настройку группы безопасности, Добавление пользователей или других групп безопасности, которые будут иметь возможность создавать группы в Организации.</span><span class="sxs-lookup"><span data-stu-id="68142-150">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="68142-151">Подробные инструкции приведены в разделе [Создание, изменение и удаление группы безопасности в центре администрирования Microsoft 365](../email/create-edit-or-delete-a-security-group.md).</span><span class="sxs-lookup"><span data-stu-id="68142-151">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="68142-152">Шаг 2. Запуск команд PowerShell</span><span class="sxs-lookup"><span data-stu-id="68142-152">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="68142-153">Для изменения параметров гостевого доступа на уровне группы необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (имя модуля **AzureADPreview**):</span><span class="sxs-lookup"><span data-stu-id="68142-153">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="68142-154">Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) и следуйте инструкциям по установке общедоступной предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="68142-154">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="68142-155">Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="68142-155">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="68142-156">Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.</span><span class="sxs-lookup"><span data-stu-id="68142-156">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="68142-157">Скопируйте приведенный ниже скрипт в текстовый редактор, например "Блокнот" или [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="68142-157">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="68142-158">Замените \* \<секуритиграупнаме\> \* именем группы безопасности, которую вы создали.</span><span class="sxs-lookup"><span data-stu-id="68142-158">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="68142-159">Например,</span><span class="sxs-lookup"><span data-stu-id="68142-159">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="68142-160">Сохраните файл как Граупкреаторс. ps1.</span><span class="sxs-lookup"><span data-stu-id="68142-160">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="68142-161">В окне PowerShell перейдите к папке, в которую был сохранен файл (введите "CD <FileLocation>").</span><span class="sxs-lookup"><span data-stu-id="68142-161">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="68142-162">Выполните сценарий, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68142-162">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="68142-163">После появления соответствующего запроса [Войдите в систему с учетной записью администратора](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) .</span><span class="sxs-lookup"><span data-stu-id="68142-163">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="68142-164">В последней строке сценария отобразятся обновленные параметры:</span><span class="sxs-lookup"><span data-stu-id="68142-164">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="68142-166">Если в будущем требуется изменить группу безопасности, можно повторно запустить скрипт с именем новой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="68142-166">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="68142-167">Если вы хотите отключить ограничение на создание групп и снова разрешить всем пользователям создавать группы, задайте для параметра $GroupName значение "" и $AllowGroupCreation значение true, а затем повторно запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="68142-167">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="68142-168">Шаг 4: Убедитесь, что он работает</span><span class="sxs-lookup"><span data-stu-id="68142-168">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="68142-169">Войдите в Office 365 с учетной записью пользователя, у которого нет возможности создавать группы.</span><span class="sxs-lookup"><span data-stu-id="68142-169">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="68142-170">То есть они не являются участниками группы безопасности, созданной или администратором.</span><span class="sxs-lookup"><span data-stu-id="68142-170">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="68142-171">Выберите плитку **планировщика** .</span><span class="sxs-lookup"><span data-stu-id="68142-171">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="68142-172">В планировщике выберите **новый план** в левой области навигации, чтобы создать план.</span><span class="sxs-lookup"><span data-stu-id="68142-172">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="68142-173">Следует получить сообщение о том, что планирование и создание групп отключены.</span><span class="sxs-lookup"><span data-stu-id="68142-173">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="68142-174">Повторите ту же процедуру с членом группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="68142-174">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="68142-175">Если участники группы безопасности не могут создавать группы, убедитесь, что они не блокируются с помощью [политики почтовых ящиков OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="68142-175">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="68142-176">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="68142-176">Related articles</span></span>

[<span data-ttu-id="68142-177">Начало работы с Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="68142-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="68142-178">Настройка управления группами самостоятельных служб в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="68142-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

<span data-ttu-id="68142-179">[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span><span class="sxs-lookup"><span data-stu-id="68142-179">[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

[<span data-ttu-id="68142-180">Командлеты Azure Active Directory для настройки параметров группы</span><span class="sxs-lookup"><span data-stu-id="68142-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
