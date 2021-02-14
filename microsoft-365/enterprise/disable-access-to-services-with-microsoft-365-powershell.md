---
title: Отключение доступа к службам Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- PowerShell
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: В этой статье вы узнаете, как использовать PowerShell для отключения доступа к службам Microsoft 365 для пользователей.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693180"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a><span data-ttu-id="fc8b8-103">Отключение доступа к службам Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc8b8-103">Disable access to Microsoft 365 services with PowerShell</span></span>

<span data-ttu-id="fc8b8-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="fc8b8-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fc8b8-105">Когда учетной записи Microsoft 365 назначена лицензия из плана лицензирования, службы Microsoft 365 будут доступны пользователю из этой лицензии.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-105">When a Microsoft 365 account is assigned a license from a licensing plan, Microsoft 365 services are made available to the user from that license.</span></span> <span data-ttu-id="fc8b8-106">Однако вы можете управлять службами Microsoft 365, к которые пользователь может получить доступ.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-106">However, you can control the Microsoft 365 services that the user can access.</span></span> <span data-ttu-id="fc8b8-107">Например, хотя лицензия разрешает доступ к службе SharePoint Online, вы можете отключить доступ к ней.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-107">For example, even though the license allows access to the SharePoint Online service, you can disable access to it.</span></span> <span data-ttu-id="fc8b8-108">С помощью PowerShell можно отключить доступ к любому количеству служб для определенного плана лицензирования для:</span><span class="sxs-lookup"><span data-stu-id="fc8b8-108">You can use PowerShell to disable access to any number of services for a specific licensing plan for:</span></span>

- <span data-ttu-id="fc8b8-109">отдельная учетная запись;</span><span class="sxs-lookup"><span data-stu-id="fc8b8-109">An individual account.</span></span>
- <span data-ttu-id="fc8b8-110">группа учетных записей;</span><span class="sxs-lookup"><span data-stu-id="fc8b8-110">A group of accounts.</span></span>
- <span data-ttu-id="fc8b8-111">все учетные записи в организации.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-111">All accounts in your organization.</span></span>

>[!Note]
><span data-ttu-id="fc8b8-112">Существуют зависимости служб Microsoft 365, которые могут препятствовать отключению указанной службы, если от нее зависят другие службы.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-112">There are Microsoft 365 service dependencies that can prevent you from disabling a specified service when other services depend on it.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="fc8b8-113">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc8b8-113">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="fc8b8-114">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="fc8b8-114">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="fc8b8-115">Затем используйте эту команду для просмотра доступных планов лицензирования, также известных как AccountSkuIds:</span><span class="sxs-lookup"><span data-stu-id="fc8b8-115">Next, use this command to view your available licensing plans, also known as AccountSkuIds:</span></span>

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
><span data-ttu-id="fc8b8-116">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-116">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="fc8b8-117">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-117">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="fc8b8-118">Дополнительные сведения см. в сведениях о просмотре лицензий и [служб с помощью PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="fc8b8-118">For more information, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="fc8b8-119">Сведения о том, как просмотреть сведения о лицензии учетной записи и службе с помощью [PowerShell,](view-account-license-and-service-details-with-microsoft-365-powershell.md)см. до и после результатов процедур, рассматриваемой в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-119">To see the before and after results of the procedures in this topic, see [View account license and service details with PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="fc8b8-120">Кроме того, вы можете воспользоваться сценарием PowerShell, который автоматизирует выполнение процедур, описанных в этой статье.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-120">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="fc8b8-121">В частности, этот сценарий позволяет просматривать и отключать службы в организации Microsoft 365, включая Sway.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-121">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="fc8b8-122">Дополнительные сведения см. в [подключе "Отключение доступа к Sway с помощью PowerShell".](disable-access-to-sway-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="fc8b8-122">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a><span data-ttu-id="fc8b8-123">Отключение определенных служб Microsoft 365 для определенных пользователей для определенного плана лицензирования</span><span class="sxs-lookup"><span data-stu-id="fc8b8-123">Disable specific Microsoft 365 services for specific users for a specific licensing plan</span></span>
  
<span data-ttu-id="fc8b8-124">Чтобы отключить определенный набор служб Microsoft 365 для пользователей для определенного плана лицензирования, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-124">To disable a specific set of Microsoft 365 services for users for a specific licensing plan, perform the following steps:</span></span>
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a><span data-ttu-id="fc8b8-125">Шаг 1. Определите нежелательные службы в плане лицензирования, используя следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="fc8b8-125">Step 1: Identify the undesirable services in the licensing plan by using the following syntax:</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

<span data-ttu-id="fc8b8-126">В следующем примере создается объект **LicenseOptions,** который отключает службы Office и SharePoint Online в плане лицензирования с именем `litwareinc:ENTERPRISEPACK` (Office 365 корпоративный E3).</span><span class="sxs-lookup"><span data-stu-id="fc8b8-126">The following example creates a **LicenseOptions** object that disables the Office and SharePoint Online services in the licensing plan named `litwareinc:ENTERPRISEPACK` (Office 365 Enterprise E3).</span></span>
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a><span data-ttu-id="fc8b8-127">Шаг 2. Использование объекта **LicenseOptions** из шага 1 для одного или более пользователей.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-127">Step 2: Use the **LicenseOptions** object from Step 1 on one or more users.</span></span>
    
<span data-ttu-id="fc8b8-128">Чтобы создать учетную запись, для которой отключены службы, используйте указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-128">To create a new account that has the services disabled, use the following syntax:</span></span>
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

<span data-ttu-id="fc8b8-129">В следующем примере создается новая учетная запись для Пользователя Allie Bellew, которая назначает лицензию и отключает службы, описанные в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-129">The following example creates a new account for Allie Bellew that assigns the license and disables the services described in Step 1.</span></span>
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

<span data-ttu-id="fc8b8-130">Дополнительные сведения о создании учетных записей пользователей в PowerShell для Microsoft 365 см. в этой [теме.](create-user-accounts-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="fc8b8-130">For more information about creating user accounts in PowerShell for Microsoft 365, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md).</span></span>
    
<span data-ttu-id="fc8b8-131">Чтобы отключить службы для существующего лицензированного пользователя, выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-131">To disable the services for an existing licensed user, use the following syntax:</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

<span data-ttu-id="fc8b8-132">В этом примере показано, как отключить службы для пользователя BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-132">This example disables the services for the user BelindaN@litwareinc.com.</span></span>
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

<span data-ttu-id="fc8b8-133">Чтобы отключить службы, описанные в шаге 1, для всех имеющихся лицензированных пользователей, укажите имя плана Microsoft 365 из отображения командлета **Get-MsolAccountSku** **(например, litwareinc:ENTERPRISEPACK),** а затем запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="fc8b8-133">To disable the services described in Step 1 for all existing licensed users, specify the name of your Microsoft 365 plan from the display of the **Get-MsolAccountSku** cmdlet (such as **litwareinc:ENTERPRISEPACK**), and then run the following commands:</span></span>
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 <span data-ttu-id="fc8b8-134">Если вы используете **cmdlet Get-MsolUser** без параметра _All,_ возвращаются только первые 500 учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-134">If you use the **Get-MsolUser** cmdlet without using the _All_ parameter, only the first 500 user accounts are returned.</span></span>

<span data-ttu-id="fc8b8-135">Чтобы отключить службы для группы существующих пользователей, воспользуйтесь одним из указанных ниже методов для идентификации пользователей.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-135">To disable the services for a group of existing users, use either of the following methods to identify the users:</span></span>
    
<span data-ttu-id="fc8b8-136">**Метод 1. Фильтрация учетных записей на основе существующего атрибута учетной записи**</span><span class="sxs-lookup"><span data-stu-id="fc8b8-136">**Method 1. Filter the accounts based on an existing account attribute**</span></span> 

<span data-ttu-id="fc8b8-137">Для этого используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="fc8b8-137">To do this, use the following syntax:</span></span>
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="fc8b8-138">В следующем примере отключались службы для пользователей отдела продаж в США.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-138">The following example disables the services for users in the Sales department in the United States.</span></span>
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

<span data-ttu-id="fc8b8-139">**Метод 2. Использование списка определенных учетных записей**</span><span class="sxs-lookup"><span data-stu-id="fc8b8-139">**Method 2: Use a list of specific accounts**</span></span> 

<span data-ttu-id="fc8b8-140">Для этого выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-140">To do this, perform the following steps:</span></span>
    
1. <span data-ttu-id="fc8b8-141">Создайте текстовый файл, в котором в каждой строке будет по одной учетной записи, как в примере ниже.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-141">Create a text file that contains one account on each line like this:</span></span>
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   <span data-ttu-id="fc8b8-142">В этом примере текстовый файл C: \\ My Documents \\Accounts.txt.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-142">In this example, the text file is C:\\My Documents\\Accounts.txt.</span></span>
    
2. <span data-ttu-id="fc8b8-143">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fc8b8-143">Run the following command:</span></span>
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

<span data-ttu-id="fc8b8-144">Если вы хотите отключить доступ к службам для нескольких планов лицензирования, повторите вышеперечисленные инструкции для каждого плана лицензирования, убедившись, что:</span><span class="sxs-lookup"><span data-stu-id="fc8b8-144">If you want to disable access to services for multiple licensing plans, repeat the above instructions for each licensing plan, ensuring that:</span></span>

- <span data-ttu-id="fc8b8-145">Учетным записям пользователей назначен план лицензирования.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-145">The user accounts have been assigned the licensing plan.</span></span>
- <span data-ttu-id="fc8b8-146">Службы, которые необходимо отключить, доступны в плане лицензирования.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-146">The services to disable are available in the licensing plan.</span></span>

<span data-ttu-id="fc8b8-147">Чтобы отключить службы Microsoft 365 для пользователей при назначении им плана лицензирования, см. "Отключение доступа к службам при назначении пользовательских [лицензий".](disable-access-to-services-while-assigning-user-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="fc8b8-147">To disable Microsoft 365 services for users while you are assigning them to a licensing plan, see [Disable access to services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</span></span>

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a><span data-ttu-id="fc8b8-148">Назначение всех служб в плане лицензирования учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="fc8b8-148">Assign all services in a licensing plan to a user account</span></span>

<span data-ttu-id="fc8b8-149">Для учетных записей пользователей с отключенными службами можно включить все службы для определенного плана лицензирования с помощью указанных здесь команд.</span><span class="sxs-lookup"><span data-stu-id="fc8b8-149">For user accounts that have had services disabled, you can enable all services for a specific licensing plan with these commands:</span></span>

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a><span data-ttu-id="fc8b8-150">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="fc8b8-150">Related topic</span></span>

[<span data-ttu-id="fc8b8-151">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc8b8-151">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fc8b8-152">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc8b8-152">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fc8b8-153">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc8b8-153">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
