---
title: Запретить добавление гостей в определенную группу
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Узнайте, как запретить гостям добавляться в определенную группу
ms.openlocfilehash: 8bee26bf5ec323536ca1ac6f25ce96927634cee7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660052"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="90945-103">Запретить гостям добавляться в определенную группу Microsoft 365 или команду Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90945-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="90945-104">Если вы хотите разрешить гостевой доступ для большинства групп и команд, но хотите запретить гостевой доступ, вы можете заблокировать гостевой доступ для отдельных групп и команд.</span><span class="sxs-lookup"><span data-stu-id="90945-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="90945-105">(Блокировка гостевого доступа к команде делается путем блокирования гостевого доступа к связанной группе.) Это предотвращает добавление новых гостей, но не удаляет гостей, которые уже находятся в группе или команде.</span><span class="sxs-lookup"><span data-stu-id="90945-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="90945-106">Если в вашей организации используются метки конфиденциальности, мы рекомендуем использовать их для управления гостевим доступом по группе.</span><span class="sxs-lookup"><span data-stu-id="90945-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="90945-107">Сведения о том, как это сделать, можно получить с помощью меток конфиденциальности для защиты контента в Microsoft Teams, группах [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)и на сайтах SharePoint.</span><span class="sxs-lookup"><span data-stu-id="90945-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="90945-108">Это рекомендуемый подход.</span><span class="sxs-lookup"><span data-stu-id="90945-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="90945-109">Изменение параметров группы с помощью Microsoft PowerShell</span><span class="sxs-lookup"><span data-stu-id="90945-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="90945-110">Вы также можете запретить добавление новых гостей в отдельные группы с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90945-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="90945-111">(Помните, что связанный с командой сайт SharePoint имеет отдельные [элементы управления гостевых общий доступ.)](https://docs.microsoft.com/sharepoint/change-external-sharing-site)</span><span class="sxs-lookup"><span data-stu-id="90945-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](https://docs.microsoft.com/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="90945-112">Чтобы изменить параметр гостевого доступа на уровне группы, необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (имя модуля **AzureADPreview):**</span><span class="sxs-lookup"><span data-stu-id="90945-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="90945-113">Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) и следуйте инструкциям по установке общедоступной предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="90945-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="90945-114">Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="90945-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="90945-115">Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.</span><span class="sxs-lookup"><span data-stu-id="90945-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="90945-116">Для запуска этих команд необходимо иметь права глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="90945-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="90945-117">Запустите следующий сценарий, заменив имя группы, в которой необходимо */<GroupName/>* заблокировать гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="90945-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="90945-118">Чтобы проверить параметры, запустите команду:</span><span class="sxs-lookup"><span data-stu-id="90945-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="90945-119">Проверка выглядит так:</span><span class="sxs-lookup"><span data-stu-id="90945-119">The verification looks like this:</span></span>
    
![Screenshot of PowerShell window showing that guest group access has been set to false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="90945-121">Разрешение или блокировка гостевого доступа на основе домена</span><span class="sxs-lookup"><span data-stu-id="90945-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="90945-122">Вы можете разрешить или заблокировать гостей, использующих определенный домен.</span><span class="sxs-lookup"><span data-stu-id="90945-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="90945-123">Например, если ваш бизнес (Contoso) имеет партнерство с другим предприятием (Fabrikam), вы можете добавить Fabrikam в список "Разрешить", чтобы пользователи могли добавлять этих гостей в свои группы.</span><span class="sxs-lookup"><span data-stu-id="90945-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="90945-124">Дополнительные сведения см. в сведениях о том, как разрешить или заблокировать приглашения пользователям [B2B из определенных организаций.](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)</span><span class="sxs-lookup"><span data-stu-id="90945-124">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="90945-125">Добавление гостей в глобальный список адресов</span><span class="sxs-lookup"><span data-stu-id="90945-125">Add guests to the global address list</span></span>

<span data-ttu-id="90945-126">По умолчанию гости не видны в глобальном списке адресов Exchange.</span><span class="sxs-lookup"><span data-stu-id="90945-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="90945-127">С помощью указанных ниже действий можно сделать гостевых гостей видимыми в глобальном списке адресов.</span><span class="sxs-lookup"><span data-stu-id="90945-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="90945-128">Найдите ObjectID гостя, выдав:</span><span class="sxs-lookup"><span data-stu-id="90945-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="90945-129">Затем запустите следующее, используя соответствующие значения для ObjectID, GivenName, Surname, DisplayName и TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="90945-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="90945-130">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="90945-130">Related topics</span></span>

[<span data-ttu-id="90945-131">Пошаговая пошаговая работа по планированию управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="90945-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="90945-132">Создание плана управления совместной работой</span><span class="sxs-lookup"><span data-stu-id="90945-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="90945-133">Управление членством в группах в Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="90945-133">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="90945-134">Проверки доступа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="90945-134">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="90945-135">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="90945-135">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
