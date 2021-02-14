---
title: Отключение доступа к службам Microsoft 365 при назначении пользовательских лицензий
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: Узнайте, как назначать лицензии учетным записям пользователей и отключать определенные планы обслуживания одновременно с помощью PowerShell для Microsoft 365.
ms.openlocfilehash: b027c805638284a78d4e49f4c65518be02e60392
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693178"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a><span data-ttu-id="34dae-103">Отключение доступа к службам Microsoft 365 при назначении пользовательских лицензий</span><span class="sxs-lookup"><span data-stu-id="34dae-103">Disable access to Microsoft 365 services while assigning user licenses</span></span>

<span data-ttu-id="34dae-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="34dae-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="34dae-105">Подписки на Microsoft 365 приходят с планами обслуживания для отдельных служб.</span><span class="sxs-lookup"><span data-stu-id="34dae-105">Microsoft 365 subscriptions come with service plans for individual services.</span></span> <span data-ttu-id="34dae-106">Администраторам Microsoft 365 часто требуется отключить определенные планы при назначении лицензий пользователям.</span><span class="sxs-lookup"><span data-stu-id="34dae-106">Microsoft 365 administrators often need to disable certain plans when assigning licenses to users.</span></span> <span data-ttu-id="34dae-107">С помощью инструкций в этой статье вы можете назначить лицензию Microsoft 365, отключив определенные планы обслуживания с помощью PowerShell для отдельной учетной записи пользователя или нескольких учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="34dae-107">With the instructions in this article, you can assign a Microsoft 365 license while disabling specific service plans using PowerShell for an individual user account or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="34dae-108">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="34dae-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="34dae-109">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="34dae-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  

<span data-ttu-id="34dae-110">Затем перечислите планы лицензий для клиента с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="34dae-110">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="34dae-111">Затем получите имя для регистрации учетной записи, к которой вы хотите добавить лицензию, также известное как имя пользователя-пользователя(UPN).</span><span class="sxs-lookup"><span data-stu-id="34dae-111">Next, get the sign-in name of the account to which you want add a license, also known as the user principal name (UPN).</span></span>

<span data-ttu-id="34dae-112">Затем скомпилировать список служб, которые необходимо включить.</span><span class="sxs-lookup"><span data-stu-id="34dae-112">Next, compile a list of services to enable.</span></span> <span data-ttu-id="34dae-113">Полный список планов лицензирования (также известных как названия продуктов), включенных в них планов обслуживания и соответствующих названий см. в соответствующем списке названий продуктов и идентификаторов планов обслуживания для [лицензирования.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)</span><span class="sxs-lookup"><span data-stu-id="34dae-113">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="34dae-114">В приведенном ниже блоке команд в заполните имя пользователя-пользователя учетной записи пользователя, номер части SKU и список планов обслуживания, чтобы включить и удалить пояснительный текст и \< and > символы.</span><span class="sxs-lookup"><span data-stu-id="34dae-114">For the command block below, fill in the user principal name of the user account, the SKU part number, and the list of service plans to enable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="34dae-115">Затем выполните полученные команды в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34dae-115">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="34dae-116">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="34dae-116">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="34dae-117">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="34dae-117">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="34dae-118">Затем запустите следующую команду, чтобы увидеть текущие подписки:</span><span class="sxs-lookup"><span data-stu-id="34dae-118">Next, run this command to see your current subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="34dae-119">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="34dae-119">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="34dae-120">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34dae-120">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="34dae-121">Значение составляющих команды  `Get-MsolAccountSku`:</span><span class="sxs-lookup"><span data-stu-id="34dae-121">In the display of the  `Get-MsolAccountSku` command:</span></span>
  
- <span data-ttu-id="34dae-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span><span class="sxs-lookup"><span data-stu-id="34dae-122">**AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format.</span></span> <span data-ttu-id="34dae-123">Это \<OrganizationName> значение, которое вы предоставили при регистрации в Microsoft 365 и уникально для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="34dae-123">The \<OrganizationName> is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="34dae-124">The \<Subscription> value is for a specific subscription.</span><span class="sxs-lookup"><span data-stu-id="34dae-124">The \<Subscription> value is for a specific subscription.</span></span> <span data-ttu-id="34dae-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="34dae-125">For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).</span></span>
    
- <span data-ttu-id="34dae-126">**ActiveUnits** — количество лицензий, которые вы приобрели для подписки.</span><span class="sxs-lookup"><span data-stu-id="34dae-126">**ActiveUnits** is the number of licenses that you've purchased for the subscription.</span></span>
    
- <span data-ttu-id="34dae-127">**WarningUnits** — количество лицензий для не продленной подписки, срок действия которой истекает через 30 дней льготного периода.</span><span class="sxs-lookup"><span data-stu-id="34dae-127">**WarningUnits** is the number of licenses in a subscription that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="34dae-128">**ConsumedUnits** — количество лицензий, которые вы назначили пользователям для подписки.</span><span class="sxs-lookup"><span data-stu-id="34dae-128">**ConsumedUnits** is the number of licenses that you've assigned to users for the subscription.</span></span>
    
<span data-ttu-id="34dae-129">Обратите внимание на AccountSkuId для подписки на Microsoft 365, которая содержит пользователей, которые вы хотите лицензировать.</span><span class="sxs-lookup"><span data-stu-id="34dae-129">Note the AccountSkuId for your Microsoft 365 subscription that contains the users you want to license.</span></span> <span data-ttu-id="34dae-130">Убедитесь, что лицензий для назначения достаточно (отнимите **ConsumedUnits** от **ActiveUnits** ).</span><span class="sxs-lookup"><span data-stu-id="34dae-130">Also, ensure that there are enough licenses to assign (subtract **ConsumedUnits** from **ActiveUnits** ).</span></span>
  
<span data-ttu-id="34dae-131">Затем запустите эту команду, чтобы увидеть сведения о планах обслуживания Microsoft 365, доступных во всех подписках:</span><span class="sxs-lookup"><span data-stu-id="34dae-131">Next, run this command to see the details about the Microsoft 365 service plans that are available in all your subscriptions:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="34dae-132">Просмотрите результаты команды и определите, какие планы обслуживания нужно отключить при назначении лицензий пользователям.</span><span class="sxs-lookup"><span data-stu-id="34dae-132">From the display of this command, determine which service plans you would like to disable when you assign licenses to users.</span></span>
  
<span data-ttu-id="34dae-133">Вот неполный список планов обслуживания и соответствующих им служб Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34dae-133">Here is a partial list of service plans and their corresponding Microsoft 365 services.</span></span>

<span data-ttu-id="34dae-134">В следующей таблице показаны планы обслуживания Microsoft 365 и их названия для наиболее распространенных служб.</span><span class="sxs-lookup"><span data-stu-id="34dae-134">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="34dae-135">Ваш список планов обслуживания может отличаться.</span><span class="sxs-lookup"><span data-stu-id="34dae-135">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="34dae-136">**План обслуживания**</span><span class="sxs-lookup"><span data-stu-id="34dae-136">**Service plan**</span></span>|<span data-ttu-id="34dae-137">**Описание**</span><span class="sxs-lookup"><span data-stu-id="34dae-137">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="34dae-138">Sway</span><span class="sxs-lookup"><span data-stu-id="34dae-138">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="34dae-139">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="34dae-139">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="34dae-140">Yammer</span><span class="sxs-lookup"><span data-stu-id="34dae-140">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="34dae-141">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="34dae-141">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="34dae-142">Приложения Microsoft 365 для предприятий (ранее называлось *Office 365 профессиональныйplus)*</span><span class="sxs-lookup"><span data-stu-id="34dae-142">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="34dae-143">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="34dae-143">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="34dae-144">Office</span><span class="sxs-lookup"><span data-stu-id="34dae-144">Office</span></span>   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="34dae-145">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="34dae-145">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="34dae-146">Exchange Online (план 2)</span><span class="sxs-lookup"><span data-stu-id="34dae-146">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="34dae-147">Полный список планов лицензирования (также известных как названия продуктов), включенных в них планов обслуживания и соответствующих названий см. в соответствующем списке названий продуктов и идентификаторов планов обслуживания для [лицензирования.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)</span><span class="sxs-lookup"><span data-stu-id="34dae-147">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
   
<span data-ttu-id="34dae-148">Теперь, когда у вас есть AccountSkuId и планы обслуживания, которые нужно отключить, вы можете назначить лицензии для одного или нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="34dae-148">Now that you have the AccountSkuId and the service plans to disable, you can assign licenses for an individual user or for multiple users.</span></span>
  
### <a name="for-a-single-user"></a><span data-ttu-id="34dae-149">Для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="34dae-149">For a single user</span></span>

<span data-ttu-id="34dae-150">Для одного пользователя в заполните имя пользователя-пользователя учетной записи, AccountSkuId и список планов обслуживания, которые необходимо отключить, и удалите пояснительный текст и \< and > символы.</span><span class="sxs-lookup"><span data-stu-id="34dae-150">For a single user, fill in the user principal name of the user account, the AccountSkuId, and the list of service plans to disable and remove the explanatory text and the \< and > characters.</span></span> <span data-ttu-id="34dae-151">Затем выполните полученные команды в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34dae-151">Then, run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

<span data-ttu-id="34dae-152">Ниже приведен пример блока команд для учетной записи belindan@contoso.com. В этом случае указана лицензия contoso:ENTERPRISEPACK, а отключить нужно планы обслуживания RMS_S_ENTERPRISE, SWAY, INTUNE_O365 и YAMMER_ENTERPRISE.</span><span class="sxs-lookup"><span data-stu-id="34dae-152">Here is an example command block for the account named belindan@contoso.com, for the contoso:ENTERPRISEPACK license, and the service plans to disable are RMS_S_ENTERPRISE, SWAY, INTUNE_O365, and YAMMER_ENTERPRISE:</span></span>
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a><span data-ttu-id="34dae-153">Для нескольких пользователей</span><span class="sxs-lookup"><span data-stu-id="34dae-153">For multiple users</span></span>

<span data-ttu-id="34dae-p109">Чтобы выполнить эту задачу администрирования для нескольких пользователей, создайте текстовый файл с разделителями-запятыми (CSV-файл), содержащий поля UserPrincipalName и UsageLocation. Пример:</span><span class="sxs-lookup"><span data-stu-id="34dae-p109">To perform this administration task for multiple users, create a comma-separated value (CSV) text file that contains the UserPrincipalName and UsageLocation fields. Here is an example:</span></span>
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

<span data-ttu-id="34dae-156">После этого укажите расположение входного и выходного CSV-файлов, ИД SKU учетной записи и список планов обслуживания, которые нужно отключить. Затем выполните полученные команды в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="34dae-156">Next, fill in the location of the input and output CSV files, the account SKU ID, and the list of service plans to disable, and then run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

<span data-ttu-id="34dae-157">Что делает этот блок команд PowerShell:</span><span class="sxs-lookup"><span data-stu-id="34dae-157">This PowerShell command block:</span></span>
  
- <span data-ttu-id="34dae-158">Отображает имя участника-пользователя для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="34dae-158">Displays the user principal name of each user.</span></span>
    
- <span data-ttu-id="34dae-159">Назначает настраиваемые лицензии для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="34dae-159">Assigns customized licenses to each user.</span></span>
    
- <span data-ttu-id="34dae-160">Создает CSV-файл со всеми обработанными пользователями и отображает состояние их лицензий.</span><span class="sxs-lookup"><span data-stu-id="34dae-160">Creates a CSV file with all the users that were processed and shows their license status.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="34dae-161">См. также</span><span class="sxs-lookup"><span data-stu-id="34dae-161">See also</span></span>

[<span data-ttu-id="34dae-162">Отключение доступа к службам Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="34dae-162">Disable access to Microsoft 365 services with PowerShell</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="34dae-163">Отключение доступа к Sway с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="34dae-163">Disable access to Sway with PowerShell</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="34dae-164">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="34dae-164">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="34dae-165">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="34dae-165">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
