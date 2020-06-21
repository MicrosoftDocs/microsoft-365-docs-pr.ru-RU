---
title: Управление гостевым доступом в группах Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Узнайте, как добавлять гостей в группу Microsoft 365, просматривать гостевых пользователей и использовать PowerShell для управления гостевым доступом.
ms.openlocfilehash: fe72f5e831215730a1ac79bcce2296d53b969c9c
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761666"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="46d3f-103">Управление гостевым доступом в группах Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="46d3f-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="46d3f-104">По умолчанию для вашей организации включен гостевой доступ для групп Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="46d3f-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="46d3f-105">Администраторы могут контролировать, разрешено ли гостевой доступ к группам для всей организации или для отдельных групп.</span><span class="sxs-lookup"><span data-stu-id="46d3f-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="46d3f-106">Когда она включена, участники группы могут приглашать гостевых пользователей в группу Microsoft 365 с помощью Outlook в Интернете.</span><span class="sxs-lookup"><span data-stu-id="46d3f-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="46d3f-107">Приглашения отправляются владельцу группы для утверждения.</span><span class="sxs-lookup"><span data-stu-id="46d3f-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="46d3f-108">После утверждения пользователь-гость добавляется в каталог и группу.</span><span class="sxs-lookup"><span data-stu-id="46d3f-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="46d3f-109">Сети Yammer Enterprise, которые находятся в собственном режиме или в [географическом формате ЕС](https://go.microsoft.com/fwlink/?linkid=2107357) , не поддерживают гостевые сети.</span><span class="sxs-lookup"><span data-stu-id="46d3f-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="46d3f-110">Microsoft 365 подключенные группы Yammer в настоящее время не поддерживают гостевой доступ, но вы можете создавать неподключенные внешние группы в сети Yammer.</span><span class="sxs-lookup"><span data-stu-id="46d3f-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="46d3f-111">Инструкции по [созданию и управлению внешними группами в Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) .</span><span class="sxs-lookup"><span data-stu-id="46d3f-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="46d3f-112">Гостевой доступ в группах часто используется в составе более широкого сценария, включающего SharePoint или Teams.</span><span class="sxs-lookup"><span data-stu-id="46d3f-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="46d3f-113">Эти службы имеют собственные параметры общего доступа к гостям.</span><span class="sxs-lookup"><span data-stu-id="46d3f-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="46d3f-114">Для получения полных инструкций по настройке общего доступа к гостевым компьютерам в группах, SharePoint и Teams, ознакомьтесь со статьей:</span><span class="sxs-lookup"><span data-stu-id="46d3f-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="46d3f-115">Совместная работа с гостями на сайте</span><span class="sxs-lookup"><span data-stu-id="46d3f-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="46d3f-116">Совместная работа с гостями в команде</span><span class="sxs-lookup"><span data-stu-id="46d3f-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="46d3f-117">Управление группами гостевого доступа</span><span class="sxs-lookup"><span data-stu-id="46d3f-117">Manage groups guest access</span></span>

<span data-ttu-id="46d3f-118">Если вы хотите включить или отключить гостевой доступ в группах, это можно сделать в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="46d3f-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="46d3f-119">В центре администрирования перейдите к **Settings** \> **параметрам Организации** параметры и на вкладке **службы** выберите пункт **Microsoft 365 группы**.</span><span class="sxs-lookup"><span data-stu-id="46d3f-119">In the admin center, go to the **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="46d3f-120">На странице " **группы Microsoft 365** " выберите, следует ли разрешить пользователям, не входящим в организацию, получать доступ к ресурсам группы или разрешить владельцам групп добавлять людей вне Организации в группы.</span><span class="sxs-lookup"><span data-stu-id="46d3f-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="46d3f-121">Добавление гостей в группу Microsoft 365 из центра администрирования</span><span class="sxs-lookup"><span data-stu-id="46d3f-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="46d3f-122">Если гость уже существует в вашем каталоге, вы можете добавить их в свои группы из центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="46d3f-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="46d3f-123">В центре администрирования перейдите на **Groups**  >  страницу**группы** группы.</span><span class="sxs-lookup"><span data-stu-id="46d3f-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="46d3f-124">Щелкните группу, в которую требуется добавить гостя, и выберите **Просмотреть все и управлять участниками** на вкладке **Участники** .</span><span class="sxs-lookup"><span data-stu-id="46d3f-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="46d3f-125">Нажмите кнопку **Добавить участников**и выберите имя гостя, которого вы хотите добавить.</span><span class="sxs-lookup"><span data-stu-id="46d3f-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="46d3f-126">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="46d3f-126">Select **Save**.</span></span>

<span data-ttu-id="46d3f-127">Если вы хотите добавить гостя в каталог напрямую, вы можете [Добавить пользователей службы совместной работы Azure Active Directory на портале Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="46d3f-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="46d3f-128">Если вы хотите изменить любую информацию гостя, вы можете [Добавить или обновить сведения о профиле пользователя с помощью Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="46d3f-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="46d3f-129">Блокировка гостевых пользователей из определенной группы</span><span class="sxs-lookup"><span data-stu-id="46d3f-129">Block guest users from a specific group</span></span>

<span data-ttu-id="46d3f-130">Если вы хотите разрешить гостевой доступ к большинству групп, но если вы хотите запретить гостевой доступ, вы можете заблокировать гостевой доступ для отдельных групп с помощью Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46d3f-130">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="46d3f-131">Для изменения параметров гостевого доступа на уровне группы необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (имя модуля **AzureADPreview**):</span><span class="sxs-lookup"><span data-stu-id="46d3f-131">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="46d3f-132">Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) и следуйте инструкциям по установке общедоступной предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="46d3f-132">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="46d3f-133">Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="46d3f-133">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="46d3f-134">Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.</span><span class="sxs-lookup"><span data-stu-id="46d3f-134">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="46d3f-135">Для выполнения этих команд требуются права глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="46d3f-135">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="46d3f-136">Выполните следующий сценарий, указав */<GroupName/>* имя группы, в которую необходимо заблокировать гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="46d3f-136">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="46d3f-137">Чтобы проверить параметры, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="46d3f-137">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="46d3f-138">Проверка выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="46d3f-138">The verification looks like this:</span></span>
    
![Снимок экрана: Окно PowerShell, в котором показано, что для доступа к гостевой группе задано значение false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="46d3f-140">Разрешение или блокировка гостевого доступа в зависимости от их домена</span><span class="sxs-lookup"><span data-stu-id="46d3f-140">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="46d3f-141">Вы можете разрешить или заблокировать доступ для пользователей-гостей, почта которых отправляется с определенного домена.</span><span class="sxs-lookup"><span data-stu-id="46d3f-141">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="46d3f-142">Например, если ваша организация (Contoso) имеет связь с другим предприятием (Fabrikam), вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавить этих гостей в свои группы.</span><span class="sxs-lookup"><span data-stu-id="46d3f-142">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="46d3f-143">Дополнительную информацию можно узнать [в статье разрешение или блокировка приглашений для пользователей B2B из определенных организаций](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="46d3f-143">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="46d3f-144">Добавление гостей в глобальный список адресов</span><span class="sxs-lookup"><span data-stu-id="46d3f-144">Add guests to the global address list</span></span>

<span data-ttu-id="46d3f-145">По умолчанию гости не отображаются в глобальном списке адресов Exchange.</span><span class="sxs-lookup"><span data-stu-id="46d3f-145">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="46d3f-146">Выполните приведенные ниже действия, чтобы сделать гостей видимым в глобальном списке адресов.</span><span class="sxs-lookup"><span data-stu-id="46d3f-146">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="46d3f-147">Найдите ObjectID пользователя гостя, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="46d3f-147">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="46d3f-148">Затем выполните приведенные ниже значения с использованием соответствующих значений для ObjectID, GivenName, фамилия, DisplayName и TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="46d3f-148">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="46d3f-149">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="46d3f-149">Related articles</span></span>

[<span data-ttu-id="46d3f-150">Управление членством в группах в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="46d3f-150">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="46d3f-151">Проверка доступа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="46d3f-151">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="46d3f-152">Set — AzureADUser</span><span class="sxs-lookup"><span data-stu-id="46d3f-152">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
