---
title: Управление тем, кто может создавать группы Microsoft 365
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
description: Узнайте, как управлять тем, какие пользователи могут создавать группы Microsoft 365.
ms.openlocfilehash: 3fa430e44c272e5ababbfb0e4befba707c72c1ba
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122388"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="35ff8-103">Управление тем, кто может создавать группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="35ff8-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="35ff8-104">По умолчанию все пользователи могут создавать группы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35ff8-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="35ff8-105">Это рекомендуемый подход, так как он позволяет пользователям начать совместную работу без помощи ИТ-сотрудников.</span><span class="sxs-lookup"><span data-stu-id="35ff8-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="35ff8-106">Если в вашей организации требуется ограничить пользователей, которые могут создавать группы, это можно сделать, вы следуя процедурам, которые данной статьи.</span><span class="sxs-lookup"><span data-stu-id="35ff8-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="35ff8-107">Когда вы ограничиваете пользователей, которые могут создавать группы, это влияет на все службы, которые используют группы для доступа, в том числе:</span><span class="sxs-lookup"><span data-stu-id="35ff8-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="35ff8-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="35ff8-108">Outlook</span></span>
- <span data-ttu-id="35ff8-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="35ff8-109">SharePoint</span></span>
- <span data-ttu-id="35ff8-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="35ff8-110">Yammer</span></span>
- <span data-ttu-id="35ff8-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="35ff8-111">Microsoft Teams</span></span>
- <span data-ttu-id="35ff8-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="35ff8-112">Microsoft Stream</span></span>
- <span data-ttu-id="35ff8-113">Планировщик</span><span class="sxs-lookup"><span data-stu-id="35ff8-113">Planner</span></span>
- <span data-ttu-id="35ff8-114">Power BI (классическая)</span><span class="sxs-lookup"><span data-stu-id="35ff8-114">Power BI (classic)</span></span>
- <span data-ttu-id="35ff8-115">Проект в Интернете / План</span><span class="sxs-lookup"><span data-stu-id="35ff8-115">Project for the web / Roadmap</span></span>

<span data-ttu-id="35ff8-116">Создание группы Microsoft 365 можно ограничить только членами определенной группы Microsoft 365 или группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="35ff8-116">You can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span> <span data-ttu-id="35ff8-117">Чтобы настроить его, используйте Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35ff8-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="35ff8-118">В этой статье данная статья посвящена всем необходимым этапам.</span><span class="sxs-lookup"><span data-stu-id="35ff8-118">This article walks you through the needed steps.</span></span>

<span data-ttu-id="35ff8-119">Действия, которые необходимо предпринять в этой статье, не препятствуют созданию групп участниками определенных ролей.</span><span class="sxs-lookup"><span data-stu-id="35ff8-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="35ff8-120">Глобальные администраторы Office 365 могут создавать группы любыми способами, такими как Центр администрирования Microsoft 365, Планировщик, Teams, Exchange и SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="35ff8-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="35ff8-121">Другие роли могут создавать группы с помощью ограниченных средств, перечисленных ниже.</span><span class="sxs-lookup"><span data-stu-id="35ff8-121">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="35ff8-122">Администратор Exchange: Центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="35ff8-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="35ff8-123">Поддержка уровня 1 для партнеров: Центр администрирования Microsoft 365, Центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="35ff8-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="35ff8-124">Поддержка уровня 2 для партнеров: Центр администрирования Microsoft 365, Центр администрирования Exchange, Azure AD</span><span class="sxs-lookup"><span data-stu-id="35ff8-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="35ff8-125">Авторы каталогов: Azure AD</span><span class="sxs-lookup"><span data-stu-id="35ff8-125">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="35ff8-126">Администратор SharePoint: Центр администрирования SharePoint, Azure AD</span><span class="sxs-lookup"><span data-stu-id="35ff8-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="35ff8-127">Администратор служб Teams: Центр администрирования Teams, Azure AD</span><span class="sxs-lookup"><span data-stu-id="35ff8-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="35ff8-128">Администратор управления пользователями: Центр администрирования Microsoft 365, Yammer, Azure AD</span><span class="sxs-lookup"><span data-stu-id="35ff8-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>

<span data-ttu-id="35ff8-129">Если вы входите в одну из этих ролей, вы можете создать группы Microsoft 365 для пользователей с ограниченным доступом, а затем назначить пользователя владельцем группы.</span><span class="sxs-lookup"><span data-stu-id="35ff8-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="35ff8-130">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="35ff8-130">Licensing requirements</span></span>

<span data-ttu-id="35ff8-131">Чтобы управлять созданием групп, следующие люди нуждаются в лицензиях Azure AD Premium или назначенной им лицензиях azure AD Basic EDU:</span><span class="sxs-lookup"><span data-stu-id="35ff8-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="35ff8-132">Администратор, который настраивает эти параметры создания группы</span><span class="sxs-lookup"><span data-stu-id="35ff8-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="35ff8-133">Члены группы, которым разрешено создавать группы</span><span class="sxs-lookup"><span data-stu-id="35ff8-133">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="35ff8-134">Дополнительные сведения о назначении лицензий Azure см. на портале [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)</span><span class="sxs-lookup"><span data-stu-id="35ff8-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="35ff8-135">Следующие люди не нуждаются в лицензиях Azure AD Premium или Azure AD Basic EDU, которые им назначены:</span><span class="sxs-lookup"><span data-stu-id="35ff8-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="35ff8-136">Пользователи, которые являются членами групп Microsoft 365 и не могут создавать другие группы.</span><span class="sxs-lookup"><span data-stu-id="35ff8-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="35ff8-137">Шаг 1. Создание группы для пользователей, которым необходимо создать группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="35ff8-137">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="35ff8-138">Для управления тем, кто может создавать группы, можно использовать только одну группу в организации.</span><span class="sxs-lookup"><span data-stu-id="35ff8-138">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="35ff8-139">Но вы можете вложенные другие группы в качестве членов этой группы.</span><span class="sxs-lookup"><span data-stu-id="35ff8-139">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="35ff8-140">Администраторы в перечисленных выше ролях не должны быть членами этой группы: они сохраняют возможность создавать группы.</span><span class="sxs-lookup"><span data-stu-id="35ff8-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="35ff8-141">В Центре администрирования перейдите на [страницу "Группы".](https://admin.microsoft.com/adminportal/home#/groups)</span><span class="sxs-lookup"><span data-stu-id="35ff8-141">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="35ff8-142">Нажмите **кнопку "Добавить группу".**</span><span class="sxs-lookup"><span data-stu-id="35ff8-142">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="35ff8-143">Выберите нужный тип группы.</span><span class="sxs-lookup"><span data-stu-id="35ff8-143">Choose the group type you want.</span></span> <span data-ttu-id="35ff8-144">Запомните имя группы.</span><span class="sxs-lookup"><span data-stu-id="35ff8-144">Remember the name of the group!</span></span> <span data-ttu-id="35ff8-145">Он потребуется позже.</span><span class="sxs-lookup"><span data-stu-id="35ff8-145">You'll need it later.</span></span>

4. <span data-ttu-id="35ff8-146">Завершите настройку группы, добавив пользователей или другие группы, которым вы хотите иметь возможность создавать группы в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="35ff8-146">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="35ff8-147">Подробные инструкции см. в описании создания, изменения или удаления группы безопасности в Центре администрирования [Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)</span><span class="sxs-lookup"><span data-stu-id="35ff8-147">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="35ff8-148">Шаг 2. Запуск команд PowerShell</span><span class="sxs-lookup"><span data-stu-id="35ff8-148">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="35ff8-149">Чтобы изменить параметр гостевого доступа на уровне группы, необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (имя модуля **AzureADPreview):**</span><span class="sxs-lookup"><span data-stu-id="35ff8-149">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="35ff8-150">Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) и следуйте инструкциям по установке общедоступной предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="35ff8-150">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="35ff8-151">Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="35ff8-151">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="35ff8-152">Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.</span><span class="sxs-lookup"><span data-stu-id="35ff8-152">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="35ff8-153">Скопируйте сценарий ниже в текстовый редактор, например Блокнот или [Windows PowerShell ISE.](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)</span><span class="sxs-lookup"><span data-stu-id="35ff8-153">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="35ff8-154">Замените *\<GroupName\>* имя созданной группы.</span><span class="sxs-lookup"><span data-stu-id="35ff8-154">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="35ff8-155">Пример:</span><span class="sxs-lookup"><span data-stu-id="35ff8-155">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="35ff8-156">Сохраните файл как GroupCreators.ps1.</span><span class="sxs-lookup"><span data-stu-id="35ff8-156">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="35ff8-157">В окне PowerShell перейдите к расположению, в котором сохранен файл (введите <FileLocation> "CD").</span><span class="sxs-lookup"><span data-stu-id="35ff8-157">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="35ff8-158">Запустите сценарий, введя:</span><span class="sxs-lookup"><span data-stu-id="35ff8-158">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="35ff8-159">и [во входе с помощью учетной записи администратора](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) при запросе.</span><span class="sxs-lookup"><span data-stu-id="35ff8-159">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="35ff8-160">В последней строке сценария отобразятся обновленные параметры:</span><span class="sxs-lookup"><span data-stu-id="35ff8-160">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="35ff8-162">Если в будущем вы захотите изменить используемую группу, можно повторно использовать сценарий с именем новой группы.</span><span class="sxs-lookup"><span data-stu-id="35ff8-162">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="35ff8-163">Если вы хотите отключить ограничение на создание группы и снова разрешить всем пользователям создавать группы, установите для $GroupName "" $AllowGroupCreation "True" и повторно перезапустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="35ff8-163">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="35ff8-164">Шаг 3. Проверка</span><span class="sxs-lookup"><span data-stu-id="35ff8-164">Step 3: Verify that it works</span></span>

<span data-ttu-id="35ff8-165">Чтобы изменения вступили в силу, может занять 30 минут или больше.</span><span class="sxs-lookup"><span data-stu-id="35ff8-165">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="35ff8-166">Чтобы проверить новые параметры, с помощью следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="35ff8-166">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="35ff8-167">Во sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span><span class="sxs-lookup"><span data-stu-id="35ff8-167">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="35ff8-168">То есть они не являются членами группы, которую вы создали, или администратором.</span><span class="sxs-lookup"><span data-stu-id="35ff8-168">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="35ff8-169">Выберите **плитку Планировщика.**</span><span class="sxs-lookup"><span data-stu-id="35ff8-169">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="35ff8-170">В Планировщике выберите **"Новый план"** в области навигации слева, чтобы создать план.</span><span class="sxs-lookup"><span data-stu-id="35ff8-170">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="35ff8-171">Должно отключать планирование и создание групп.</span><span class="sxs-lookup"><span data-stu-id="35ff8-171">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="35ff8-172">Попробуйте эту же процедуру еще раз с участником группы.</span><span class="sxs-lookup"><span data-stu-id="35ff8-172">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="35ff8-173">Если члены группы не могут создавать группы, убедитесь, что они не заблокированы с помощью политики почтовых ящиков [OWA.](https://go.microsoft.com/fwlink/?linkid=852135)</span><span class="sxs-lookup"><span data-stu-id="35ff8-173">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>

## <a name="related-topics"></a><span data-ttu-id="35ff8-174">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="35ff8-174">Related topics</span></span>

[<span data-ttu-id="35ff8-175">Пошаговая пошаговая работа по планированию управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="35ff8-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="35ff8-176">Создание плана управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="35ff8-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="35ff8-177">Начало работы с Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="35ff8-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="35ff8-178">Настройка управления самостоятельной группой в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="35ff8-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

<span data-ttu-id="35ff8-179">[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span><span class="sxs-lookup"><span data-stu-id="35ff8-179">[Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)</span></span>

[<span data-ttu-id="35ff8-180">Командлеты Azure Active Directory для настройки параметров группы</span><span class="sxs-lookup"><span data-stu-id="35ff8-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
