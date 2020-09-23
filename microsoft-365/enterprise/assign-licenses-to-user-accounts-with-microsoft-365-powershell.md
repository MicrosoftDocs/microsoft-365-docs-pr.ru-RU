---
title: Назначение лицензий Microsoft 365 для учетных записей пользователей с помощью PowerShell
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
description: В этой статье рассказывается, как использовать PowerShell для назначения лицензии Microsoft 365 нелицензированным пользователям.
ms.openlocfilehash: f042f8109bf9ac9b634bc66509c60a5181fb1af6
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235622"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a><span data-ttu-id="1bf9f-103">Назначение лицензий Microsoft 365 для учетных записей пользователей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bf9f-103">Assign Microsoft 365 licenses to user accounts with PowerShell</span></span>

<span data-ttu-id="1bf9f-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="1bf9f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1bf9f-105">Пользователи не могут использовать службы Microsoft 365, пока их учетной записи не назначена лицензия из плана лицензирования.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-105">Users can't use any Microsoft 365 services until their account has been assigned a license from a licensing plan.</span></span> <span data-ttu-id="1bf9f-106">С помощью PowerShell можно быстро назначить лицензии нелицензированным учетным записям.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-106">You can use PowerShell to quickly assign licenses to unlicensed accounts.</span></span> 

>[!Note]
><span data-ttu-id="1bf9f-107">Учетным записям пользователей должно быть назначено расположение.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-107">User accounts must be assigned a location.</span></span> <span data-ttu-id="1bf9f-108">Это можно сделать в свойствах учетной записи пользователя в центре администрирования Microsoft 365 или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-108">You can do this from the properties of a user account in the Microsoft 365 admin center or from PowerShell.</span></span>
>

>[!Note]
><span data-ttu-id="1bf9f-109">[Узнайте, как назначать лицензии учетным записям пользователей](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) с помощью центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-109">[Learn how to assign licenses to user accounts](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="1bf9f-110">Список дополнительных ресурсов приведен в разделе [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="1bf9f-110">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1bf9f-111">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="1bf9f-111">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1bf9f-112">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="1bf9f-112">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="1bf9f-113">Затем перечислите план лицензирования для клиента с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-113">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="1bf9f-114">Затем получите имя для входа учетной записи, к которой требуется добавить лицензию, также называемую именем участника-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="1bf9f-114">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="1bf9f-115">Затем убедитесь, что для учетной записи пользователя назначено место использования.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-115">Next, ensure that the user account has a usage location assigned.</span></span>

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

<span data-ttu-id="1bf9f-116">Если местоположение использования не назначено, вы можете назначить его с помощью следующих команд:</span><span class="sxs-lookup"><span data-stu-id="1bf9f-116">If there is no usage location assigned, you can assign one with these commands:</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

<span data-ttu-id="1bf9f-117">Наконец, укажите имя пользователя для входа и имя плана лицензирования и выполните указанные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-117">Finally, specify the user sign-in name and license plan name and run these commands.</span></span>

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1bf9f-118">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bf9f-118">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="1bf9f-119">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1bf9f-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="1bf9f-120">Выполните `Get-MsolAccountSku` команду, чтобы просмотреть доступные планы лицензирования и число доступных лицензий в каждом плане в Организации.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-120">Run the `Get-MsolAccountSku` command to view the available licensing plans and the number of available licenses in each plan in your organization.</span></span> <span data-ttu-id="1bf9f-121">Число доступных лицензий в каждом плане — **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-121">The number of available licenses in each plan is **ActiveUnits** - **WarningUnits** - **ConsumedUnits**.</span></span> <span data-ttu-id="1bf9f-122">Для получения дополнительных сведений о планах лицензирования, лицензиях и службах ознакомьтесь со статьей [Просмотр лицензий и служб с помощью PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1bf9f-122">For more information about licensing plans, licenses, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

>[!Note]
><span data-ttu-id="1bf9f-123">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-123">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="1bf9f-124">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-124">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="1bf9f-125">Чтобы найти нелицензированные учетные записи в Организации, выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-125">To find the unlicensed accounts in your organization, run this command.</span></span>

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="1bf9f-126">Вы можете назначать лицензии только тем пользователям, у которых для свойства **UsageLocation** задан действительный код страны ISO 3166-1 Alpha-2.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-126">You can only assign licenses to user accounts that have the **UsageLocation** property set to a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="1bf9f-127">Важно указать это значение, так как некоторые службы O365_W14_2nd недоступны в определенных странах.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-127">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="1bf9f-128">Некоторые службы Microsoft 365 недоступны в некоторых странах.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-128">Some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="1bf9f-129">Более подробную информацию можно узнать в статье [ограничения лицензирования](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="1bf9f-129">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>
    
<span data-ttu-id="1bf9f-130">Чтобы найти учетные записи, для которых не задано значение **UsageLocation** , выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-130">To find accounts that don't have a **UsageLocation** value, run this command.</span></span>

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

<span data-ttu-id="1bf9f-131">Чтобы задать значение **UsageLocation** для учетной записи, выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-131">To set the **UsageLocation** value on an account, run this command.</span></span>

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

<span data-ttu-id="1bf9f-132">Пример:</span><span class="sxs-lookup"><span data-stu-id="1bf9f-132">For example:</span></span>

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
<span data-ttu-id="1bf9f-133">Если использовать командлет **Get-MsolUser** без параметра **-All**, возвращаются только первые 500 учетных записей.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-133">If you use the **Get-MsolUser** cmdlet without using the **-All** parameter, only the first 500 accounts are returned.</span></span>

### <a name="assigning-licenses-to-user-accounts"></a><span data-ttu-id="1bf9f-134">Назначение лицензий учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="1bf9f-134">Assigning licenses to user accounts</span></span>
    
<span data-ttu-id="1bf9f-135">Чтобы назначить лицензию пользователю, используйте следующую команду в PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-135">To assign a license to a user, use the following command in PowerShell.</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

<span data-ttu-id="1bf9f-136">В этом примере назначается лицензия из плана лицензирования **litwareinc: ENTERPRISEPACK** (Office 365 корпоративный E3) для нелицензированного пользователя **белиндан \@ litwareinc.com**:</span><span class="sxs-lookup"><span data-stu-id="1bf9f-136">This example assigns a license from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to the unlicensed user **belindan\@litwareinc.com**:</span></span>
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="1bf9f-137">Чтобы назначить лицензию для всех нелицензированных пользователей, выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-137">To assign a license to all unlicensed users, run this command.</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
><span data-ttu-id="1bf9f-138">Невозможно назначить пользователю несколько лицензий из одного плана лицензирования.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-138">You can't assign multiple licenses to a user from the same licensing plan.</span></span> <span data-ttu-id="1bf9f-139">Если у вас нет достаточного количества доступных лицензий, они назначаются пользователям в порядке, в котором их возвращает командлет **Get-MsolUser**, пока не закончатся.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-139">If you don't have enough available licenses, the licenses are assigned to users in the order that they're returned by the **Get-MsolUser** cmdlet until the available licenses run out.</span></span>
>

<span data-ttu-id="1bf9f-140">В этом примере назначаются лицензии из плана лицензирования **litwareinc: ENTERPRISEPACK** (Office 365 корпоративный E3) для всех нелицензированных пользователей:</span><span class="sxs-lookup"><span data-stu-id="1bf9f-140">This example assigns licenses from the **litwareinc:ENTERPRISEPACK** (Office 365 Enterprise E3) licensing plan to all unlicensed users:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

<span data-ttu-id="1bf9f-141">В этом примере для нелицензированных пользователей назначаются те же лицензии в отделе продаж в США.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-141">This example assigns those same licenses to unlicensed users in the Sales department in the United States:</span></span>
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1bf9f-142">Перемещение пользователя в другую подписку (план лицензирования) с помощью модуля Azure Active Directory PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="1bf9f-142">Move a user to a different subscription (license plan) with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1bf9f-143">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="1bf9f-143">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="1bf9f-144">Затем получите имя для входа учетной записи пользователя, для которой требуется сменить подписку, также называемую именем участника-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="1bf9f-144">Next, get the sign-in name of the user account for which you want switch subscriptions, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="1bf9f-145">Затем перечислите подписки (планы лицензирования) для вашего клиента с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-145">Next, list the subscriptions (license plans) for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="1bf9f-146">Затем перечислите подписку на текущую учетную запись пользователя с помощью этих команд.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-146">Next, list the subscriptions that the user account currently has with these commands.</span></span>

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

<span data-ttu-id="1bf9f-147">Определите подписку пользователя (из подписки) и подписку, на которую пользователь перемещается (в подписку).</span><span class="sxs-lookup"><span data-stu-id="1bf9f-147">Identify the subscription the user currently has (the FROM subscription) and the subscription to which the user is moving (the TO subscription).</span></span>

<span data-ttu-id="1bf9f-148">Наконец, укажите имена подписок "Кому" и "от" (номера деталей SKU) и выполните приведенные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-148">Finally, specify the TO and FROM subscription names (SKU part numbers) and run these commands.</span></span>

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

<span data-ttu-id="1bf9f-149">Вы можете проверить изменение подписки для учетной записи пользователя с помощью этих команд.</span><span class="sxs-lookup"><span data-stu-id="1bf9f-149">You can verify the change in subscription for the user account with these commands.</span></span>

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a><span data-ttu-id="1bf9f-150">См. также</span><span class="sxs-lookup"><span data-stu-id="1bf9f-150">See also</span></span>

[<span data-ttu-id="1bf9f-151">Управление учетными записями пользователей, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bf9f-151">Manage user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1bf9f-152">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bf9f-152">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1bf9f-153">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1bf9f-153">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
