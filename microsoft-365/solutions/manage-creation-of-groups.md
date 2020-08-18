---
title: Управление пользователями, которые могут создавать группы Microsoft 365
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Узнайте, как определять, какие пользователи могут создавать группы Microsoft 365.
ms.openlocfilehash: f2b2837a762398bb065d36c7f849b2fdcbbb5816
ms.sourcegitcommit: 6fb2a1c404ea3c3573b0f7803bf17459a9387891
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788888"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="4b37c-103">Управление пользователями, которые могут создавать группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4b37c-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="4b37c-104">По умолчанию все пользователи могут создавать группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b37c-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="4b37c-105">Это рекомендуемый подход, так как он позволяет пользователям начать работать без необходимости помощи.</span><span class="sxs-lookup"><span data-stu-id="4b37c-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="4b37c-106">Если для вашей организации требуется ограничить круг пользователей, которые могут создавать группы, выполните действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4b37c-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="4b37c-107">При ограничении прав на создание группы она влияет на все службы, зависящие от групп, в том числе:</span><span class="sxs-lookup"><span data-stu-id="4b37c-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="4b37c-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="4b37c-108">Outlook</span></span>
    
- <span data-ttu-id="4b37c-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="4b37c-109">SharePoint</span></span>
    
- <span data-ttu-id="4b37c-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="4b37c-110">Yammer</span></span>
    
- <span data-ttu-id="4b37c-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b37c-111">Microsoft Teams</span></span>

- <span data-ttu-id="4b37c-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="4b37c-112">Microsoft Stream</span></span>

- <span data-ttu-id="4b37c-113">Планировщик</span><span class="sxs-lookup"><span data-stu-id="4b37c-113">Planner</span></span>
    
- <span data-ttu-id="4b37c-114">PowerBI (классический)</span><span class="sxs-lookup"><span data-stu-id="4b37c-114">PowerBI (classic)</span></span>
    
- <span data-ttu-id="4b37c-115">Проект для веб-сайта или плана</span><span class="sxs-lookup"><span data-stu-id="4b37c-115">Project for the web / Roadmap</span></span>
    
<span data-ttu-id="4b37c-116">Вы можете ограничить создание групп Microsoft 365 членами определенной группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="4b37c-116">You can restrict Microsoft 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="4b37c-117">Чтобы настроить это, используйте Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b37c-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="4b37c-118">В этой статье рассказывается о необходимых действиях.</span><span class="sxs-lookup"><span data-stu-id="4b37c-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="4b37c-119">Действия, описанные в этой статье, не позволят членам определенных ролей создавать группы.</span><span class="sxs-lookup"><span data-stu-id="4b37c-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="4b37c-120">Глобальные администраторы Office 365 могут создавать группы с помощью любых средств, таких как центр администрирования Майкрософт 365, планировщик, Teams, Exchange и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4b37c-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="4b37c-121">Другие роли могут создавать группы с помощью ограниченных средств, перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="4b37c-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="4b37c-122">Администратор Exchange: центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4b37c-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="4b37c-123">Поддержка уровня партнеров 1: центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4b37c-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="4b37c-124">Поддержка уровня партнеров 2: центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4b37c-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="4b37c-125">Записи в каталогах: Azure AD</span><span class="sxs-lookup"><span data-stu-id="4b37c-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="4b37c-126">Администратор SharePoint: центр администрирования SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4b37c-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="4b37c-127">Администратор службы teams: центр администрирования Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4b37c-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="4b37c-128">Администратор управления пользователями: центр администрирования Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="4b37c-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="4b37c-129">Если вы являетесь участником одной из этих ролей, вы можете создать группы Microsoft 365 для пользователей с ограниченным доступом, а затем назначить пользователя владельцем группы.</span><span class="sxs-lookup"><span data-stu-id="4b37c-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="4b37c-130">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="4b37c-130">Licensing requirements</span></span>

<span data-ttu-id="4b37c-131">Для управления разрешениями групп для следующих людей требуются лицензии Azure AD Premium или Azure AD Basic EDU, назначенные им:</span><span class="sxs-lookup"><span data-stu-id="4b37c-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="4b37c-132">Администратор, который настраивает эти параметры создания групп</span><span class="sxs-lookup"><span data-stu-id="4b37c-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="4b37c-133">Члены группы безопасности, которым разрешено создавать группы</span><span class="sxs-lookup"><span data-stu-id="4b37c-133">The members of the security group who are allowed to create groups</span></span>
 
> [!NOTE]
> <span data-ttu-id="4b37c-134">Дополнительные сведения о назначении лицензий Azure можно найти [в статье назначение и удаление лицензий на портале Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) .</span><span class="sxs-lookup"><span data-stu-id="4b37c-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="4b37c-135">Следующим пользователям не нужны лицензии Azure AD Premium или Azure AD Basic EDU:</span><span class="sxs-lookup"><span data-stu-id="4b37c-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="4b37c-136">Пользователи, являющиеся членами групп Microsoft 365 и у которых нет возможности создавать другие группы.</span><span class="sxs-lookup"><span data-stu-id="4b37c-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="4b37c-137">Шаг 1: создание группы безопасности для пользователей, которым требуется создавать группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4b37c-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="4b37c-138">Для контроля того, кто может создавать группы, можно использовать только одну группу безопасности в Организации.</span><span class="sxs-lookup"><span data-stu-id="4b37c-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="4b37c-139">Но вы можете вложить в нее другие группы безопасности как участников.</span><span class="sxs-lookup"><span data-stu-id="4b37c-139">But, you can nest other security groups as members of this group.</span></span>

<span data-ttu-id="4b37c-140">Администраторы из перечисленных выше ролей не должны быть членами этой группы: они сохраняют возможность создавать группы.</span><span class="sxs-lookup"><span data-stu-id="4b37c-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b37c-141">Обязательно используйте **группу безопасности** , чтобы ограничить круг пользователей, которые могут создавать группы.</span><span class="sxs-lookup"><span data-stu-id="4b37c-141">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="4b37c-142">Использование группы Microsoft 365 не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4b37c-142">Using a Microsoft 365 group is not supported.</span></span> 
    
1. <span data-ttu-id="4b37c-143">В центре администрирования перейдите на [страницу группы](https://admin.microsoft.com/adminportal/home#/groups).</span><span class="sxs-lookup"><span data-stu-id="4b37c-143">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="4b37c-144">Нажмите кнопку **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="4b37c-144">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="4b37c-145">Выберите пункт **Безопасность** в качестве типа группы.</span><span class="sxs-lookup"><span data-stu-id="4b37c-145">Choose **Security** as the group type.</span></span> <span data-ttu-id="4b37c-146">Запомните имя группы.</span><span class="sxs-lookup"><span data-stu-id="4b37c-146">Remember the name of the group!</span></span> <span data-ttu-id="4b37c-147">Он потребуется позже.</span><span class="sxs-lookup"><span data-stu-id="4b37c-147">You'll need it later.</span></span>
  
4. <span data-ttu-id="4b37c-148">Завершите настройку группы безопасности, Добавление пользователей или других групп безопасности, которые будут иметь возможность создавать группы в Организации.</span><span class="sxs-lookup"><span data-stu-id="4b37c-148">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="4b37c-149">Подробные инструкции приведены в разделе [Создание, изменение и удаление группы безопасности в центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span><span class="sxs-lookup"><span data-stu-id="4b37c-149">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="4b37c-150">Шаг 2. Запуск команд PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b37c-150">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="4b37c-151">Для изменения параметров гостевого доступа на уровне группы необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (имя модуля **AzureADPreview**):</span><span class="sxs-lookup"><span data-stu-id="4b37c-151">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="4b37c-152">Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) и следуйте инструкциям по установке общедоступной предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="4b37c-152">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="4b37c-153">Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="4b37c-153">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="4b37c-154">Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.</span><span class="sxs-lookup"><span data-stu-id="4b37c-154">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="4b37c-155">Скопируйте приведенный ниже скрипт в текстовый редактор, например "Блокнот" или [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span><span class="sxs-lookup"><span data-stu-id="4b37c-155">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="4b37c-156">Замените *\<SecurityGroupName\>* именем группы безопасности, которую вы создали.</span><span class="sxs-lookup"><span data-stu-id="4b37c-156">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="4b37c-157">Например:</span><span class="sxs-lookup"><span data-stu-id="4b37c-157">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="4b37c-158">Сохраните файл как GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="4b37c-158">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="4b37c-159">В окне PowerShell перейдите к папке, в которую был сохранен файл (введите "CD <FileLocation> ").</span><span class="sxs-lookup"><span data-stu-id="4b37c-159">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="4b37c-160">Выполните сценарий, введя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4b37c-160">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="4b37c-161">После появления соответствующего запроса [Войдите в систему с учетной записью администратора](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) .</span><span class="sxs-lookup"><span data-stu-id="4b37c-161">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="4b37c-162">В последней строке сценария отобразятся обновленные параметры:</span><span class="sxs-lookup"><span data-stu-id="4b37c-162">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="4b37c-164">Если в будущем требуется изменить группу безопасности, можно повторно запустить скрипт с именем новой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="4b37c-164">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="4b37c-165">Если вы хотите отключить ограничение на создание групп и снова разрешить всем пользователям создавать группы, задайте для параметра $GroupName значение "" и $AllowGroupCreation значение true, а затем повторно запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="4b37c-165">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="4b37c-166">Шаг 3. Проверка</span><span class="sxs-lookup"><span data-stu-id="4b37c-166">Step 3: Verify that it works</span></span>

<span data-ttu-id="4b37c-167">Для вступления изменений в силу может потребоваться 30 минут или более.</span><span class="sxs-lookup"><span data-stu-id="4b37c-167">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="4b37c-168">Вы можете проверить новые параметры, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4b37c-168">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="4b37c-169">Войдите в Microsoft 365 с учетной записью пользователя, у которого нет возможности создавать группы.</span><span class="sxs-lookup"><span data-stu-id="4b37c-169">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="4b37c-170">То есть они не являются участниками группы безопасности, созданной или администратором.</span><span class="sxs-lookup"><span data-stu-id="4b37c-170">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="4b37c-171">Выберите плитку **планировщика** .</span><span class="sxs-lookup"><span data-stu-id="4b37c-171">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="4b37c-172">В планировщике выберите **новый план** в левой области навигации, чтобы создать план.</span><span class="sxs-lookup"><span data-stu-id="4b37c-172">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="4b37c-173">Следует получить сообщение о том, что планирование и создание групп отключены.</span><span class="sxs-lookup"><span data-stu-id="4b37c-173">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="4b37c-174">Повторите ту же процедуру с членом группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="4b37c-174">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="4b37c-175">Если участники группы безопасности не могут создавать группы, убедитесь, что они не блокируются с помощью [политики почтовых ящиков OWA](https://go.microsoft.com/fwlink/?linkid=852135).</span><span class="sxs-lookup"><span data-stu-id="4b37c-175">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="4b37c-176">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4b37c-176">Related articles</span></span>

[<span data-ttu-id="4b37c-177">Начало работы с Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4b37c-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="4b37c-178">Настройка управления группами самостоятельных служб в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4b37c-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

<span data-ttu-id="4b37c-179">[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span><span class="sxs-lookup"><span data-stu-id="4b37c-179">[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

[<span data-ttu-id="4b37c-180">Командлеты Azure Active Directory для настройки параметров группы</span><span class="sxs-lookup"><span data-stu-id="4b37c-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
