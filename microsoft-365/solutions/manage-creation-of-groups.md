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
ms.openlocfilehash: 9c3edf335ce09f04e9b0b538e69fa607a9c34044
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929160"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="6d2ff-103">Управление разрешениями пользователей на создание групп Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d2ff-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="6d2ff-104">По умолчанию все пользователи могут создавать группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="6d2ff-105">Это рекомендуемый подход, так как он позволяет пользователям приступить к совместной совместной работу без необходимости оказания ИТ-помощи.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="6d2ff-106">Если для бизнеса требуется ограничить пользователей, которые могут создавать группы, можно ограничить создание группы Microsoft 365 членами определенной группы или группы безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-106">If your business requires that you restrict who can create groups, you can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span>

<span data-ttu-id="6d2ff-107">Если вы беспокоите пользователей, создав группы или группы, которые не соответствуют вашим бизнес-стандартам, подумайте о том, чтобы пользователи завершили учебный курс, а затем добавили их в группу разрешенных пользователей.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-107">If you're concerned about users creating teams or groups that don't comply with your business standards, consider requiring users to complete a training course and then adding them to the group of allowed users.</span></span>

<span data-ttu-id="6d2ff-108">Когда вы ограничиваете, кто может создать группу, это влияет на все службы, которые полагаются на группы для доступа, в том числе:</span><span class="sxs-lookup"><span data-stu-id="6d2ff-108">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="6d2ff-109">Outlook</span><span class="sxs-lookup"><span data-stu-id="6d2ff-109">Outlook</span></span>
- <span data-ttu-id="6d2ff-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="6d2ff-110">SharePoint</span></span>
- <span data-ttu-id="6d2ff-111">Yammer</span><span class="sxs-lookup"><span data-stu-id="6d2ff-111">Yammer</span></span>
- <span data-ttu-id="6d2ff-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d2ff-112">Microsoft Teams</span></span>
- <span data-ttu-id="6d2ff-113">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="6d2ff-113">Microsoft Stream</span></span>
- <span data-ttu-id="6d2ff-114">Планировщик</span><span class="sxs-lookup"><span data-stu-id="6d2ff-114">Planner</span></span>
- <span data-ttu-id="6d2ff-115">Power BI (классический)</span><span class="sxs-lookup"><span data-stu-id="6d2ff-115">Power BI (classic)</span></span>
- <span data-ttu-id="6d2ff-116">Project for the web / Roadmap</span><span class="sxs-lookup"><span data-stu-id="6d2ff-116">Project for the web / Roadmap</span></span>

<span data-ttu-id="6d2ff-117">Действия в этой статье не будут препятствовать созданию групп членами определенных ролей.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-117">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="6d2ff-118">Глобальные администраторы Office 365 могут создавать группы любыми средствами, такими как центр администрирования Microsoft 365, планировщик, teams, Exchange и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-118">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="6d2ff-119">Другие роли могут создавать группы с помощью ограниченных средств, перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-119">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="6d2ff-120">Администратор Exchange: Центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="6d2ff-120">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="6d2ff-121">Поддержка уровня 1 партнера: Центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="6d2ff-121">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="6d2ff-122">Поддержка уровня партнеров 2: Центр администрирования Microsoft 365, центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="6d2ff-122">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="6d2ff-123">Авторы каталогов: Azure AD</span><span class="sxs-lookup"><span data-stu-id="6d2ff-123">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="6d2ff-124">Администратор SharePoint: Центр администрирования SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="6d2ff-124">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="6d2ff-125">Администратор службы teams: Центр администрирования teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="6d2ff-125">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="6d2ff-126">Администратор пользователя: Центр администрирования Microsoft 365, Azure AD</span><span class="sxs-lookup"><span data-stu-id="6d2ff-126">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="6d2ff-127">Если вы входите в одну из этих ролей, вы можете создать Группы Microsoft 365 для пользователей с ограниченным доступом, а затем назначить пользователя владельцем группы.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-127">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="6d2ff-128">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="6d2ff-128">Licensing requirements</span></span>

<span data-ttu-id="6d2ff-129">Чтобы управлять созданием групп, следующим людям нужны лицензии Azure AD Premium или лицензии Azure AD Basic EDU, назначенные им:</span><span class="sxs-lookup"><span data-stu-id="6d2ff-129">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="6d2ff-130">Администратор, который настраивает эти параметры создания группы</span><span class="sxs-lookup"><span data-stu-id="6d2ff-130">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="6d2ff-131">Члены группы, которым разрешено создавать группы</span><span class="sxs-lookup"><span data-stu-id="6d2ff-131">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="6d2ff-132">Дополнительные сведения о назначении лицензий Azure см. в материале Назначение или удаление лицензий на [портале Azure Active Directory.](/azure/active-directory/fundamentals/license-users-groups)</span><span class="sxs-lookup"><span data-stu-id="6d2ff-132">See [Assign or remove licenses in the Azure Active Directory portal](/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="6d2ff-133">Следующие люди не нуждаются в лицензиях Azure AD Premium или Azure AD Basic EDU, которые им назначены:</span><span class="sxs-lookup"><span data-stu-id="6d2ff-133">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="6d2ff-134">Люди, которые являются членами групп Microsoft 365 и не имеют возможности создавать другие группы.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-134">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="6d2ff-135">Шаг 1. Создание группы для пользователей, которым необходимо создать группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d2ff-135">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="6d2ff-136">Только одна группа в вашей организации может использоваться для управления тем, кто может создавать группы.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-136">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="6d2ff-137">Но вы можете вложенные другие группы в качестве членов этой группы.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-137">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="6d2ff-138">Администраторы в перечисленных выше ролях не должны быть членами этой группы: они сохраняют возможность создавать группы.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-138">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="6d2ff-139">В центре администрирования перейдите на страницу [Группы](https://admin.microsoft.com/adminportal/home#/groups).</span><span class="sxs-lookup"><span data-stu-id="6d2ff-139">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="6d2ff-140">Нажмите **кнопку Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-140">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="6d2ff-141">Выберите нужный тип группы.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-141">Choose the group type you want.</span></span> <span data-ttu-id="6d2ff-142">Запомните имя группы.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-142">Remember the name of the group!</span></span> <span data-ttu-id="6d2ff-143">Он потребуется позже.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-143">You'll need it later.</span></span>

4. <span data-ttu-id="6d2ff-144">Завершите настройку группы, добавив людей или другие группы, которые вы хотите иметь возможность создавать группы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-144">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="6d2ff-145">Подробные инструкции см. в [публикации Create, edit или delete a security group in the Microsoft 365 admin center.](../admin/email/create-edit-or-delete-a-security-group.md)</span><span class="sxs-lookup"><span data-stu-id="6d2ff-145">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../admin/email/create-edit-or-delete-a-security-group.md).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="6d2ff-146">Шаг 2. Запуск команд PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d2ff-146">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="6d2ff-147">Чтобы изменить параметр гостевого доступа на групповом уровне, необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph (AzureAD) (имя](/powershell/azure/active-directory/install-adv2) модуля **AzureADPreview).**</span><span class="sxs-lookup"><span data-stu-id="6d2ff-147">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="6d2ff-148">Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) и следуйте инструкциям по установке общедоступной предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-148">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="6d2ff-149">Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-149">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="6d2ff-150">Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-150">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="6d2ff-151">Скопируйте сценарий ниже в текстовый редактор, например блокнот или [Windows PowerShell ISE.](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)</span><span class="sxs-lookup"><span data-stu-id="6d2ff-151">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="6d2ff-152">Замените *\<GroupName\>* имя созданной группы.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-152">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="6d2ff-153">Например:</span><span class="sxs-lookup"><span data-stu-id="6d2ff-153">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="6d2ff-154">Сохраните файл как GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-154">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="6d2ff-155">В окне PowerShell перейдите к расположению, в котором сохранен файл (тип <FileLocation> "CD").</span><span class="sxs-lookup"><span data-stu-id="6d2ff-155">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="6d2ff-156">Запустите сценарий, введя:</span><span class="sxs-lookup"><span data-stu-id="6d2ff-156">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="6d2ff-157">и [во входе в учетную запись администратора](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) при запросе.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-157">and [sign in with your administrator account](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="6d2ff-158">Последняя строка скрипта отображает обновленные параметры:</span><span class="sxs-lookup"><span data-stu-id="6d2ff-158">The last line of the script will display the updated settings:</span></span>

![Снимок экрана вывода скрипта PowerShell.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="6d2ff-160">Если в будущем необходимо изменить используемую группу, можно перезахоранить сценарий с именем новой группы.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-160">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="6d2ff-161">Если вы хотите отключить ограничение создания группы и снова разрешить всем пользователям создавать группы, установите $GroupName "" и $AllowGroupCreation "True" и перезапустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-161">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="6d2ff-162">Шаг 3. Проверка</span><span class="sxs-lookup"><span data-stu-id="6d2ff-162">Step 3: Verify that it works</span></span>

<span data-ttu-id="6d2ff-163">Для внесения изменений может занять 30 минут или более.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-163">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="6d2ff-164">Вы можете проверить новые параметры, делая следующие:</span><span class="sxs-lookup"><span data-stu-id="6d2ff-164">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="6d2ff-165">Вопишитесь в Microsoft 365 с учетной записью пользователя, у которого не должно быть возможности создавать группы.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-165">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="6d2ff-166">То есть они не являются членом созданной группы или администратором.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-166">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="6d2ff-167">Выберите **плитку Planner.**</span><span class="sxs-lookup"><span data-stu-id="6d2ff-167">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="6d2ff-168">В Планировщике выберите **Новый план** в левой навигации, чтобы создать план.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-168">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="6d2ff-169">Вы должны получить сообщение о том, что планирование и создание группы отключены.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-169">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="6d2ff-170">Попробуйте повторить ту же процедуру с участником группы.</span><span class="sxs-lookup"><span data-stu-id="6d2ff-170">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="6d2ff-171">Если члены группы не могут создавать группы, убедитесь, что они не заблокированы с помощью политики [почтовых ящиков OWA.](/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="6d2ff-171">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6d2ff-172">Родственные темы</span><span class="sxs-lookup"><span data-stu-id="6d2ff-172">Related topics</span></span>

[<span data-ttu-id="6d2ff-173">Пошаговая пошаговая работа по планированию управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="6d2ff-173">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="6d2ff-174">Создание плана управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="6d2ff-174">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="6d2ff-175">Начало работы с Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d2ff-175">Getting started with Office 365 PowerShell</span></span>](../enterprise/getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="6d2ff-176">Настройка управления группой самообслуживки в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6d2ff-176">Set up self-service group management in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-self-service-management)

<span data-ttu-id="6d2ff-177">[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy).</span><span class="sxs-lookup"><span data-stu-id="6d2ff-177">[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

[<span data-ttu-id="6d2ff-178">Командлеты Azure Active Directory для настройки параметров группы</span><span class="sxs-lookup"><span data-stu-id="6d2ff-178">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)