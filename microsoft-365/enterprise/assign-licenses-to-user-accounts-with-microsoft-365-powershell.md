---
title: Назначение Microsoft 365 для учетных записей пользователей с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: В этой статье узнайте, как использовать PowerShell для назначения Microsoft 365 лицензии нелицензированным пользователям.
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572625"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="9a1cd-103">Назначение Microsoft 365 для учетных записей пользователей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a1cd-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="9a1cd-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="9a1cd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9a1cd-105">Пользователи не могут использовать какие-либо Microsoft 365 службы до тех пор, пока их учетная запись не будет назначена лицензия из плана лицензирования.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="9a1cd-106">Вы можете использовать PowerShell для быстрого назначения лицензий нелицензированным учетным записям.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="9a1cd-107">Учетные записи пользователей должны быть сначала назначены местоположение.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="9a1cd-108">Определение местоположения является необходимой частью создания новой учетной записи пользователя в [Microsoft 365 администратора.](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="9a1cd-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="9a1cd-109">Учетные записи, синхронизированные с вашими службами active Directory Domain Services, по умолчанию не имеют указанного местоположения.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="9a1cd-110">Вы можете настроить местоположение для этих учетных записей из:</span><span class="sxs-lookup"><span data-stu-id="9a1cd-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="9a1cd-111">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9a1cd-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="9a1cd-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a1cd-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="9a1cd-113">Портал [Azure (Активные](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) **пользователи**  >  **каталога >** учетную запись >   >  **контактную информацию профиля** Страна или  >  **регион).**</span><span class="sxs-lookup"><span data-stu-id="9a1cd-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="9a1cd-114">[Узнайте, как присвоить лицензии учетным](../admin/manage/assign-licenses-to-users.md) записям пользователей с помощью Microsoft 365-центра.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="9a1cd-115">Список дополнительных ресурсов можно посмотреть с [пользователями и группами Управления.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="9a1cd-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="9a1cd-116">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="9a1cd-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="9a1cd-117">[Во-первых, подключись к Microsoft 365 арендатору.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="9a1cd-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="9a1cd-118">Далее перечислите планы лицензий для вашего арендатора с этой командой.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="9a1cd-119">Затем получите имя учетной записи, к которой вы хотите добавить лицензию, также известную как главное имя пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="9a1cd-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="9a1cd-120">Далее убедитесь, что учетная запись пользователя имеет местоположение использования назначено.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="9a1cd-121">Если место использования не назначено, можно назначить одну с этими командами:</span><span class="sxs-lookup"><span data-stu-id="9a1cd-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="9a1cd-122">Наконец, укажите имя пользователя и имя плана лицензии и запустите эти команды.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="9a1cd-123">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a1cd-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="9a1cd-124">Пожалуйста, обратите внимание, что мы начнем о амортизации этого модуля, когда функциональность этого модуля доступна [в Azure Active Directory PowerShell для Graph](/powershell/azuread/v2/azureactivedirectory) модуля.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-124">Please note that we will begin to deprecate this module when the functionality of this module is available in the newer [Azure Active Directory PowerShell for Graph](/powershell/azuread/v2/azureactivedirectory) module.</span></span> <span data-ttu-id="9a1cd-125">Мы советуем клиентам, создающих новые скрипты PowerShell, использовать новый модуль вместо этого модуля.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-125">We advise customers who are creating new PowerShell scripts to use the newer module instead of this module.</span></span>

<span data-ttu-id="9a1cd-126">[Во-первых, подключись к Microsoft 365 арендатору.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="9a1cd-126">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="9a1cd-127">Запустите `Get-MsolAccountSku` команду для просмотра доступных планов лицензирования и количества доступных лицензий в каждом плане в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-127">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="9a1cd-128">Количество доступных лицензий в каждом плане **ActiveUnits**  -  **WarningUnits**  -  **ПотребляемыеUnits**.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-128">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="9a1cd-129">Для получения дополнительной информации о планах лицензирования, лицензиях и услугах [см.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="9a1cd-129">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="9a1cd-130">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-130">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="9a1cd-131">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-131">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="9a1cd-132">Чтобы найти нелицензированные учетные записи в вашей организации, запустите эту команду.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-132">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="9a1cd-133">Лицензии могут присваиваться только учетным записям пользователей, которые **имеют свойство UsageLocation,** настроенное на действительный код страны ISO 3166-1 alpha-2.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-133">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="9a1cd-134">Важно указать это значение, так как некоторые службы O365_W14_2nd недоступны в определенных странах.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-134">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="9a1cd-135">Некоторые Microsoft 365 услуги не доступны в некоторых странах.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-135">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="9a1cd-136">Для получения дополнительной информации [см.](https://go.microsoft.com/fwlink/p/?LinkId=691730)</span><span class="sxs-lookup"><span data-stu-id="9a1cd-136">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="9a1cd-137">Чтобы найти учетные записи, не которые не имеют **значения использования,** запустите эту команду.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-137">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="9a1cd-138">Чтобы установить значение **Распределения использования в** учетной записи, запустите эту команду.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-138">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="9a1cd-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="9a1cd-139">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="9a1cd-140">Если использовать командлет **Get-MsolUser** без параметра **-All**, возвращаются только первые 500 учетных записей.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-140">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="9a1cd-141">Назначение лицензий учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="9a1cd-141">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="9a1cd-142">Чтобы назначить лицензию пользователю, в PowerShell используйте следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-142">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="9a1cd-143">Этот пример присваивает лицензию от **litwareinc:ENTERPRISEPACK** (Office 365 корпоративный E3) план лицензирования нелицензированного пользователя **belindan \@ litwareinc.com:**</span><span class="sxs-lookup"><span data-stu-id="9a1cd-143">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="9a1cd-144">Чтобы назначить лицензию всем нелицензированным пользователям, запустите эту команду.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-144">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="9a1cd-145">Невозможно назначить пользователю несколько лицензий из одного плана лицензирования.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-145">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="9a1cd-146">Если у вас нет достаточного количества доступных лицензий, они назначаются пользователям в порядке, в котором их возвращает командлет **Get-MsolUser**, пока не закончатся.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-146">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="9a1cd-147">Этот пример присваивает лицензии **из плана лицензирования litwareinc:ENTERPRISEPACK** (Office 365 корпоративный E3) всем нелицензированным пользователям:</span><span class="sxs-lookup"><span data-stu-id="9a1cd-147">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="9a1cd-148">Этот пример присваивает те же лицензии нелицензированным пользователям в отделе продаж в США:</span><span class="sxs-lookup"><span data-stu-id="9a1cd-148">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="9a1cd-149">Перемещение пользователя в другую подписку (лицензионный план) с Azure Active Directory PowerShell для Graph модуля</span><span class="sxs-lookup"><span data-stu-id="9a1cd-149">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="9a1cd-150">[Во-первых, подключись к Microsoft 365 арендатору.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="9a1cd-150">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="9a1cd-151">Далее, получить имя входят в учетную запись пользователя, для которой вы хотите переключить подписки, также известный как основное имя пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="9a1cd-151">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="9a1cd-152">Далее перечислите подписки (планы лицензий) для вашего клиента с этой командой.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-152">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="9a1cd-153">Далее перечислите подписки, которые пользовательская учетная запись в настоящее время имеет с этими командами.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-153">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="9a1cd-154">Определите подписку, которую пользователь в настоящее время имеет (подписку FROM) и подписку, к которой переезжает пользователь (подписка TO).</span><span class="sxs-lookup"><span data-stu-id="9a1cd-154">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="9a1cd-155">Наконец, укажите имена подписки TO и FROM (номера части SKU) и запустите эти команды.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-155">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

<span data-ttu-id="9a1cd-156">Вы можете проверить изменение подписки на учетную запись пользователя с помощью этих команд.</span><span class="sxs-lookup"><span data-stu-id="9a1cd-156">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="9a1cd-157">См. также</span><span class="sxs-lookup"><span data-stu-id="9a1cd-157">See also</span></span>

[<span data-ttu-id="9a1cd-158">Управление учетными записями пользователей, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a1cd-158">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9a1cd-159">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9a1cd-159">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="9a1cd-160">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9a1cd-160">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
