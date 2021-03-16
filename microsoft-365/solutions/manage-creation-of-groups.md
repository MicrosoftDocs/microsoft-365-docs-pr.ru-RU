---
title: Управление разрешениями пользователей на создание групп Microsoft 365
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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Узнайте, как управлять, какие пользователи могут создавать группы Microsoft 365.
ms.openlocfilehash: f2d1a2062d43af750a84984aab66329ed6a4db22
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819706"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="50ce1-103">Управление разрешениями пользователей на создание групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="50ce1-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="50ce1-104">По умолчанию все пользователи могут создавать группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="50ce1-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="50ce1-105">Это рекомендуемый подход, так как он позволяет пользователям приступить к совместной совместной работу без необходимости оказания ИТ-помощи.</span><span class="sxs-lookup"><span data-stu-id="50ce1-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="50ce1-106">Если вашему бизнесу требуется ограничить, кто может создавать группы, вы можете сделать это, следуя процедурам в этой статье.</span><span class="sxs-lookup"><span data-stu-id="50ce1-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="50ce1-107">Когда вы ограничиваете, кто может создать группу, это влияет на все службы, которые полагаются на группы для доступа, в том числе:</span><span class="sxs-lookup"><span data-stu-id="50ce1-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="50ce1-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="50ce1-108">Outlook</span></span>
- <span data-ttu-id="50ce1-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="50ce1-109">SharePoint</span></span>
- <span data-ttu-id="50ce1-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="50ce1-110">Yammer</span></span>
- <span data-ttu-id="50ce1-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="50ce1-111">Microsoft Teams</span></span>
- <span data-ttu-id="50ce1-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="50ce1-112">Microsoft Stream</span></span>
- <span data-ttu-id="50ce1-113">Планировщик</span><span class="sxs-lookup"><span data-stu-id="50ce1-113">Planner</span></span>
- <span data-ttu-id="50ce1-114">Power BI (классический)</span><span class="sxs-lookup"><span data-stu-id="50ce1-114">Power BI (classic)</span></span>
- <span data-ttu-id="50ce1-115">Project for the web / Roadmap</span><span class="sxs-lookup"><span data-stu-id="50ce1-115">Project for the web / Roadmap</span></span>

<span data-ttu-id="50ce1-116">Можно ограничить создание Группы Microsoft 365 членами определенной группы Или группы безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="50ce1-116">You can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span> <span data-ttu-id="50ce1-117">Для настройки этого используется Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50ce1-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="50ce1-118">В этой статье вы можете пройти необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="50ce1-118">This article walks you through the needed steps.</span></span>

<span data-ttu-id="50ce1-119">Действия в этой статье не будут препятствовать созданию групп членами определенных ролей.</span><span class="sxs-lookup"><span data-stu-id="50ce1-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="50ce1-120">Глобальные администраторы Office 365 могут создавать группы любыми средствами, такими как центр администрирования Microsoft 365, планировщик, teams, Exchange и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="50ce1-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="50ce1-121">Другие роли могут создавать группы с помощью ограниченных средств, перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="50ce1-121">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="50ce1-122">Администратор Exchange: Центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="50ce1-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="50ce1-123">Поддержка уровня 1 партнера: Центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="50ce1-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="50ce1-124">Поддержка уровня партнеров 2: Центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="50ce1-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="50ce1-125">Авторы каталогов: Azure AD</span><span class="sxs-lookup"><span data-stu-id="50ce1-125">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="50ce1-126">Администратор SharePoint: Центр администрирования SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="50ce1-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="50ce1-127">Администратор службы teams: Центр администрирования teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="50ce1-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="50ce1-128">Администратор пользователя: Центр администрирования Microsoft 365, Azure AD</span><span class="sxs-lookup"><span data-stu-id="50ce1-128">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="50ce1-129">Если вы входите в одну из этих ролей, вы можете создать Группы Microsoft 365 для пользователей с ограниченным доступом, а затем назначить пользователя владельцем группы.</span><span class="sxs-lookup"><span data-stu-id="50ce1-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="50ce1-130">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="50ce1-130">Licensing requirements</span></span>

<span data-ttu-id="50ce1-131">Чтобы управлять созданием групп, следующим людям нужны лицензии Azure AD Premium или лицензии Azure AD Basic EDU, назначенные им:</span><span class="sxs-lookup"><span data-stu-id="50ce1-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="50ce1-132">Администратор, который настраивает эти параметры создания группы</span><span class="sxs-lookup"><span data-stu-id="50ce1-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="50ce1-133">Члены группы, которым разрешено создавать группы</span><span class="sxs-lookup"><span data-stu-id="50ce1-133">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="50ce1-134">Дополнительные сведения о назначении лицензий Azure см. в материале Назначение или удаление лицензий на [портале Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)</span><span class="sxs-lookup"><span data-stu-id="50ce1-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="50ce1-135">Следующие люди не нуждаются в лицензиях Azure AD Premium или Azure AD Basic EDU, которые им назначены:</span><span class="sxs-lookup"><span data-stu-id="50ce1-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="50ce1-136">Люди, которые являются членами групп Microsoft 365 и не имеют возможности создавать другие группы.</span><span class="sxs-lookup"><span data-stu-id="50ce1-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="50ce1-137">Шаг 1. Создание группы для пользователей, которым необходимо создать группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="50ce1-137">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="50ce1-138">Только одна группа в вашей организации может использоваться для управления тем, кто может создавать группы.</span><span class="sxs-lookup"><span data-stu-id="50ce1-138">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="50ce1-139">Но вы можете вложенные другие группы в качестве членов этой группы.</span><span class="sxs-lookup"><span data-stu-id="50ce1-139">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="50ce1-140">Администраторы в перечисленных выше ролях не должны быть членами этой группы: они сохраняют возможность создавать группы.</span><span class="sxs-lookup"><span data-stu-id="50ce1-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="50ce1-141">В центре администрирования перейдите на страницу [Группы](https://admin.microsoft.com/adminportal/home#/groups).</span><span class="sxs-lookup"><span data-stu-id="50ce1-141">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="50ce1-142">Нажмите **кнопку Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="50ce1-142">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="50ce1-143">Выберите нужный тип группы.</span><span class="sxs-lookup"><span data-stu-id="50ce1-143">Choose the group type you want.</span></span> <span data-ttu-id="50ce1-144">Запомните имя группы.</span><span class="sxs-lookup"><span data-stu-id="50ce1-144">Remember the name of the group!</span></span> <span data-ttu-id="50ce1-145">Он потребуется позже.</span><span class="sxs-lookup"><span data-stu-id="50ce1-145">You'll need it later.</span></span>

4. <span data-ttu-id="50ce1-146">Завершите настройку группы, добавив людей или другие группы, которые вы хотите иметь возможность создавать группы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="50ce1-146">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="50ce1-147">Подробные инструкции см. в [публикации Create, edit или delete a security group in the Microsoft 365 admin center.](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)</span><span class="sxs-lookup"><span data-stu-id="50ce1-147">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="50ce1-148">Шаг 2. Запуск команд PowerShell</span><span class="sxs-lookup"><span data-stu-id="50ce1-148">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="50ce1-149">Чтобы изменить параметр гостевого доступа на групповом уровне, необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph (AzureAD) (имя](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) модуля **AzureADPreview).**</span><span class="sxs-lookup"><span data-stu-id="50ce1-149">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="50ce1-150">Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) и следуйте инструкциям по установке общедоступной предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="50ce1-150">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="50ce1-151">Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="50ce1-151">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="50ce1-152">Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.</span><span class="sxs-lookup"><span data-stu-id="50ce1-152">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="50ce1-153">Скопируйте сценарий ниже в текстовый редактор, например блокнот или [Windows PowerShell ISE.](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)</span><span class="sxs-lookup"><span data-stu-id="50ce1-153">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="50ce1-154">Замените *\<GroupName\>* имя созданной группы.</span><span class="sxs-lookup"><span data-stu-id="50ce1-154">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="50ce1-155">Например:</span><span class="sxs-lookup"><span data-stu-id="50ce1-155">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="50ce1-156">Сохраните файл как GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="50ce1-156">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="50ce1-157">В окне PowerShell перейдите к расположению, в котором сохранен файл (тип <FileLocation> "CD").</span><span class="sxs-lookup"><span data-stu-id="50ce1-157">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="50ce1-158">Запустите сценарий, введя:</span><span class="sxs-lookup"><span data-stu-id="50ce1-158">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="50ce1-159">и [во входе в учетную запись администратора](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) при запросе.</span><span class="sxs-lookup"><span data-stu-id="50ce1-159">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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

<span data-ttu-id="50ce1-160">Последняя строка скрипта отображает обновленные параметры:</span><span class="sxs-lookup"><span data-stu-id="50ce1-160">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="50ce1-162">Если в будущем необходимо изменить используемую группу, можно перезахоранить сценарий с именем новой группы.</span><span class="sxs-lookup"><span data-stu-id="50ce1-162">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="50ce1-163">Если вы хотите отключить ограничение создания группы и снова разрешить всем пользователям создавать группы, установите $GroupName "" и $AllowGroupCreation "True" и перезапустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="50ce1-163">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="50ce1-164">Шаг 3. Проверка</span><span class="sxs-lookup"><span data-stu-id="50ce1-164">Step 3: Verify that it works</span></span>

<span data-ttu-id="50ce1-165">Для внесения изменений может занять 30 минут или более.</span><span class="sxs-lookup"><span data-stu-id="50ce1-165">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="50ce1-166">Вы можете проверить новые параметры, делая следующие:</span><span class="sxs-lookup"><span data-stu-id="50ce1-166">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="50ce1-167">Вопишитесь в Microsoft 365 с учетной записью пользователя, у которого не должно быть возможности создавать группы.</span><span class="sxs-lookup"><span data-stu-id="50ce1-167">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="50ce1-168">То есть они не являются членом созданной группы или администратором.</span><span class="sxs-lookup"><span data-stu-id="50ce1-168">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="50ce1-169">Выберите **плитку Planner.**</span><span class="sxs-lookup"><span data-stu-id="50ce1-169">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="50ce1-170">В Планировщике выберите **Новый план** в левой навигации, чтобы создать план.</span><span class="sxs-lookup"><span data-stu-id="50ce1-170">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="50ce1-171">Вы должны получить сообщение о том, что планирование и создание группы отключены.</span><span class="sxs-lookup"><span data-stu-id="50ce1-171">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="50ce1-172">Попробуйте повторить ту же процедуру с участником группы.</span><span class="sxs-lookup"><span data-stu-id="50ce1-172">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="50ce1-173">Если члены группы не могут создавать группы, убедитесь, что они не заблокированы с помощью политики [почтовых ящиков OWA.](https://go.microsoft.com/fwlink/?linkid=852135)</span><span class="sxs-lookup"><span data-stu-id="50ce1-173">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>

## <a name="related-topics"></a><span data-ttu-id="50ce1-174">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="50ce1-174">Related topics</span></span>

[<span data-ttu-id="50ce1-175">Пошаговая пошаговая работа по планированию управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="50ce1-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="50ce1-176">Создание плана управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="50ce1-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="50ce1-177">Начало работы с Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="50ce1-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="50ce1-178">Настройка управления группой самообслуживки в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="50ce1-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="50ce1-179">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="50ce1-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="50ce1-180">Командлеты Azure Active Directory для настройки параметров группы</span><span class="sxs-lookup"><span data-stu-id="50ce1-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
