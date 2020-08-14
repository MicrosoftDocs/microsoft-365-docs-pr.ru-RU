---
title: Блокировка гостевых пользователей из определенной группы
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Блокировка гостевых пользователей из определенной группы
ms.openlocfilehash: 923a9e5cd09d232f377f55fd6a9f499f8f536a84
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662787"
---
# <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="cc4b1-103">Блокировка гостевых пользователей из определенной группы</span><span class="sxs-lookup"><span data-stu-id="cc4b1-103">Block guest users from a specific group</span></span>

<span data-ttu-id="cc4b1-104">Если вы хотите разрешить гостевой доступ к большинству групп, но если вы хотите запретить гостевой доступ, вы можете заблокировать гостевой доступ для отдельных групп.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-104">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups.</span></span>

<span data-ttu-id="cc4b1-105">Если вы используете метки чувствительности в Организации, рекомендуем использовать их для управления гостевым доступом для отдельных групп.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-105">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="cc4b1-106">Для получения сведений о том, как это сделать, [используйте метки чувствительности для защиты содержимого в Microsoft Teams, microsoft 365 Groups и сайтов SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="cc4b1-106">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="cc4b1-107">Это рекомендуемый подход.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-107">This is the recommended approach.</span></span>

<span data-ttu-id="cc4b1-108">Вы также можете заблокировать гостевой доступ к отдельным группам с помощью Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-108">You can also block guest access to individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="cc4b1-109">Для изменения параметров гостевого доступа на уровне группы необходимо использовать предварительную версию [Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (имя модуля **AzureADPreview**):</span><span class="sxs-lookup"><span data-stu-id="cc4b1-109">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="cc4b1-110">Если вы еще не установили ни одной версии модуля Azure AD PowerShell, см. раздел [Установка модуля Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) и следуйте инструкциям по установке общедоступной предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-110">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="cc4b1-111">Если у вас установлена общедоступная версия 2.0 модуля Azure AD PowerShell (AzureAD), вам требуется удалить ее, выполнив команду `Uninstall-Module AzureAD` в сеансе PowerShell, а затем установить предварительную версию, выполнив команду `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-111">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="cc4b1-112">Если вы уже установили предварительную версию, выполните команду `Install-Module AzureADPreview`, чтобы убедиться, что это последняя версия модуля.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-112">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="cc4b1-113">Для выполнения этих команд требуются права глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-113">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="cc4b1-114">Выполните следующий сценарий, указав */<GroupName/>* имя группы, в которую необходимо заблокировать гостевой доступ.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-114">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="cc4b1-115">Чтобы проверить параметры, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="cc4b1-115">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="cc4b1-116">Проверка выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cc4b1-116">The verification looks like this:</span></span>
    
![Снимок экрана: Окно PowerShell, в котором показано, что для доступа к гостевой группе задано значение false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="cc4b1-118">Разрешение или блокировка гостевого доступа в зависимости от их домена</span><span class="sxs-lookup"><span data-stu-id="cc4b1-118">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="cc4b1-119">Вы можете разрешить или заблокировать доступ для пользователей-гостей, почта которых отправляется с определенного домена.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-119">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="cc4b1-120">Например, если ваша организация (Contoso) имеет связь с другим предприятием (Fabrikam), вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавить этих гостей в свои группы.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-120">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="cc4b1-121">Дополнительную информацию можно узнать [в статье разрешение или блокировка приглашений для пользователей B2B из определенных организаций](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="cc4b1-121">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="cc4b1-122">Добавление гостей в глобальный список адресов</span><span class="sxs-lookup"><span data-stu-id="cc4b1-122">Add guests to the global address list</span></span>

<span data-ttu-id="cc4b1-123">По умолчанию гости не отображаются в глобальном списке адресов Exchange.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-123">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="cc4b1-124">Выполните приведенные ниже действия, чтобы сделать гостей видимым в глобальном списке адресов.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-124">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="cc4b1-125">Найдите ObjectID пользователя гостя, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="cc4b1-125">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="cc4b1-126">Затем выполните приведенные ниже значения с использованием соответствующих значений для ObjectID, GivenName, фамилия, DisplayName и TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="cc4b1-126">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="cc4b1-127">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cc4b1-127">Related articles</span></span>

[<span data-ttu-id="cc4b1-128">Управление членством в группах в центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc4b1-128">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="cc4b1-129">Проверка доступа Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cc4b1-129">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="cc4b1-130">Set — AzureADUser</span><span class="sxs-lookup"><span data-stu-id="cc4b1-130">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)