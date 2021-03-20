---
title: Назначение лицензий Microsoft 365 учетным записям пользователей с помощью PowerShell
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
description: В этой статье узнайте, как использовать PowerShell для назначения лицензии Microsoft 365 нелицензированным пользователям.
ms.openlocfilehash: 5fb5f9095d4f732b0bf23f26eebb22eff608b48c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905468"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="238f2-103">Назначение лицензий Microsoft 365 учетным записям пользователей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="238f2-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="238f2-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="238f2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="238f2-105">Пользователи не могут использовать какие-либо службы Microsoft 365 до тех пор, пока их учетной записи не будет назначена лицензия из плана лицензирования.</span><span class="sxs-lookup"><span data-stu-id="238f2-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="238f2-106">С помощью PowerShell можно быстро назначить лицензии нелицензируемой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="238f2-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

<span data-ttu-id="238f2-107">Учетным записям пользователей сначала должно быть назначено расположение.</span><span class="sxs-lookup"><span data-stu-id="238f2-107">User accounts must first be assigned a location.</span></span> <span data-ttu-id="238f2-108">Указание расположения является обязательной частью создания новой учетной записи пользователя в центре администрирования [Microsoft 365.](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="238f2-108">Specifying a location is a required part of creating a new user account in the [Microsoft 365 admin center](../admin/add-users/add-users.md).</span></span> 

<span data-ttu-id="238f2-109">Учетные записи, синхронизированные с локальной службой домена Active Directory, по умолчанию не имеют определенного расположения.</span><span class="sxs-lookup"><span data-stu-id="238f2-109">Accounts synchronized from your on-premises Active Directory Domain Services do not by default have a location specified.</span></span> <span data-ttu-id="238f2-110">Вы можете настроить расположение для этих учетных записей из:</span><span class="sxs-lookup"><span data-stu-id="238f2-110">You can configure a location for these accounts from:</span></span>

- <span data-ttu-id="238f2-111">Центр администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="238f2-111">The Microsoft 365 admin center</span></span>
 - [<span data-ttu-id="238f2-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="238f2-112">PowerShell</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
 - <span data-ttu-id="238f2-113">Портал [Azure](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) **(Пользователи active Directory**> учетной записи >  >   **контактные** данные профилей  >    >  **страны или региона).**</span><span class="sxs-lookup"><span data-stu-id="238f2-113">The [Azure portal](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) (**Active Directory** > **Users**  > user account > **Profile** > **Contact info** > **Country or region**).</span></span>

>[!Note]
><span data-ttu-id="238f2-114">[Узнайте, как назначать лицензии учетным](../admin/manage/assign-licenses-to-users.md) записям пользователей в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="238f2-114">[Learn how to assign licenses to user accounts](../admin/manage/assign-licenses-to-users.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="238f2-115">Список дополнительных ресурсов см. в списке [Управление пользователями и группами.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="238f2-115">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="238f2-116">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="238f2-116">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="238f2-117">[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="238f2-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="238f2-118">Далее перечислите планы лицензий для клиента с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="238f2-118">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="238f2-119">Далее получите имя входной записи, к которой нужно добавить лицензию, также именуемую главным именем пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="238f2-119">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="238f2-120">Далее убедитесь, что учетной записи пользователя назначено расположение использования.</span><span class="sxs-lookup"><span data-stu-id="238f2-120">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="238f2-121">Если не назначено расположение использования, можно назначить одну с помощью этих команд:</span><span class="sxs-lookup"><span data-stu-id="238f2-121">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="238f2-122">Наконец, укажите имя и имя плана плана регистрации пользователя и запустите эти команды.</span><span class="sxs-lookup"><span data-stu-id="238f2-122">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="238f2-123">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="238f2-123">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="238f2-124">[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="238f2-124">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="238f2-125">Запустите команду, чтобы просмотреть доступные планы лицензирования и количество доступных лицензий в каждом плане `Get-MsolAccountSku` в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="238f2-125">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="238f2-126">Количество доступных лицензий в каждом плане **— ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits.**</span><span class="sxs-lookup"><span data-stu-id="238f2-126">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="238f2-127">Дополнительные сведения о планах лицензирования, лицензиях и службах см. в обзоре лицензий и служб [в PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="238f2-127">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="238f2-128">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="238f2-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="238f2-129">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="238f2-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="238f2-130">Чтобы найти нелицензивные учетные записи в организации, запустите эту команду.</span><span class="sxs-lookup"><span data-stu-id="238f2-130">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="238f2-131">Лицензии можно назначать только учетным записям пользователей с свойством **UseLocation,** задаваемым допустимым кодом страны ISO 3166-1 alpha-2.</span><span class="sxs-lookup"><span data-stu-id="238f2-131">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="238f2-132">Важно указать это значение, так как некоторые службы O365_W14_2nd недоступны в определенных странах.</span><span class="sxs-lookup"><span data-stu-id="238f2-132">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="238f2-133">Некоторые службы Microsoft 365 недоступны в некоторых странах.</span><span class="sxs-lookup"><span data-stu-id="238f2-133">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="238f2-134">Дополнительные сведения см. [в дополнительных сведениях об ограничениях лицензии.](https://go.microsoft.com/fwlink/p/?LinkId=691730)</span><span class="sxs-lookup"><span data-stu-id="238f2-134">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="238f2-135">Чтобы найти учетные записи, которые не имеют **значения UseLocation,** запустите эту команду.</span><span class="sxs-lookup"><span data-stu-id="238f2-135">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="238f2-136">Чтобы установить значение **UseLocation** для учетной записи, запустите эту команду.</span><span class="sxs-lookup"><span data-stu-id="238f2-136">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="238f2-137">Например:</span><span class="sxs-lookup"><span data-stu-id="238f2-137">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="238f2-138">Если использовать командлет **Get-MsolUser** без параметра **-All**, возвращаются только первые 500 учетных записей.</span><span class="sxs-lookup"><span data-stu-id="238f2-138">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="238f2-139">Назначение лицензий учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="238f2-139">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="238f2-140">Чтобы назначить лицензию пользователю, используйте следующую команду в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="238f2-140">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="238f2-141">В этом примере лицензия из плана лицензирования **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) назначается нелицензионному пользователю **belindan \@ litwareinc.com:**</span><span class="sxs-lookup"><span data-stu-id="238f2-141">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="238f2-142">Чтобы назначить лицензию всем нелицензируемой пользователям, запустите эту команду.</span><span class="sxs-lookup"><span data-stu-id="238f2-142">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="238f2-143">Невозможно назначить пользователю несколько лицензий из одного плана лицензирования.</span><span class="sxs-lookup"><span data-stu-id="238f2-143">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="238f2-144">Если у вас нет достаточного количества доступных лицензий, они назначаются пользователям в порядке, в котором их возвращает командлет **Get-MsolUser**, пока не закончатся.</span><span class="sxs-lookup"><span data-stu-id="238f2-144">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="238f2-145">В этом примере всем нелицензионным пользователям присваиваются лицензии из плана лицензирования **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3):</span><span class="sxs-lookup"><span data-stu-id="238f2-145">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="238f2-146">В этом примере эти же лицензии назначаются нелицензированным пользователям в отделе продаж в США:</span><span class="sxs-lookup"><span data-stu-id="238f2-146">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="238f2-147">Перемещение пользователя в другую подписку (план лицензии) с помощью модуля Azure Active Directory PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="238f2-147">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="238f2-148">[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="238f2-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="238f2-149">Далее получите имя учетной записи пользователя, для которой нужны подписки на коммутаторы, также известные как основное имя пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="238f2-149">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="238f2-150">Далее перечислите подписки (планы лицензий) для клиента с этой командой.</span><span class="sxs-lookup"><span data-stu-id="238f2-150">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="238f2-151">Далее укай список подписок, которые в настоящее время есть у учетной записи пользователя с этими командами.</span><span class="sxs-lookup"><span data-stu-id="238f2-151">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="238f2-152">Определите подписку, на которую пользователь в настоящее время имеет (подписку FROM) и подписку на которую перемещается (подписка TO).</span><span class="sxs-lookup"><span data-stu-id="238f2-152">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="238f2-153">Наконец, укажите имена подписок TO и FROM (номера части SKU) и запустите эти команды.</span><span class="sxs-lookup"><span data-stu-id="238f2-153">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="238f2-154">Вы можете проверить изменение подписки на учетную запись пользователя с помощью этих команд.</span><span class="sxs-lookup"><span data-stu-id="238f2-154">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="238f2-155">См. также</span><span class="sxs-lookup"><span data-stu-id="238f2-155">See also</span></span>

[<span data-ttu-id="238f2-156">Управление учетными записями пользователей, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="238f2-156">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="238f2-157">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="238f2-157">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="238f2-158">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="238f2-158">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)