---
title: Просмотр сведений о лицензии и службе учетной записи Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- PowerShell
- Ent_Office_Other
- LIL_Placement
ms.assetid: ace07d8a-15ca-4b89-87f0-abbce809b519
description: Объясняется, как использовать PowerShell для определения служб Microsoft 365, которые были назначены пользователям.
ms.openlocfilehash: 163a92ec31f700aa6157e58b49e23a1cec587815
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693549"
---
# <a name="view-microsoft-365-account-license-and-service-details-with-powershell"></a><span data-ttu-id="10376-103">Просмотр сведений о лицензии и службе учетной записи Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="10376-103">View Microsoft 365 account license and service details with PowerShell</span></span>

<span data-ttu-id="10376-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="10376-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="10376-105">В Microsoft 365 лицензии из планов лицензирования (также называемые планами SKUs или Microsoft 365) дают пользователям доступ к службам Microsoft 365, определенным для этих планов.</span><span class="sxs-lookup"><span data-stu-id="10376-105">In Microsoft 365, licenses from licensing plans (also called SKUs or Microsoft 365 plans) give users access to the Microsoft 365 services that are defined for those plans.</span></span> <span data-ttu-id="10376-106">Однако у пользователя может не быть доступа ко всем службам, доступным в лицензии, которая им назначена в данный момент.</span><span class="sxs-lookup"><span data-stu-id="10376-106">However, a user might not have access to all the services that are available in a license that's currently assigned to them.</span></span> <span data-ttu-id="10376-107">С помощью PowerShell для Microsoft 365 можно просматривать состояние служб в учетных записях пользователей.</span><span class="sxs-lookup"><span data-stu-id="10376-107">You can use PowerShell for Microsoft 365 to view the status of services on user accounts.</span></span> 

<span data-ttu-id="10376-108">Дополнительные сведения о планах лицензирования, лицензиях и службах см. в сведениях о лицензировании и службах [с помощью PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="10376-108">For more information about licensing plans, license, and services, see [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="10376-109">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="10376-109">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="10376-110">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="10376-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="10376-111">Затем перечислите планы лицензий для клиента с помощью этой команды.</span><span class="sxs-lookup"><span data-stu-id="10376-111">Next, list the license plans for your tenant with this command.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="10376-112">Используйте эти команды для получения списка служб, доступных в каждом плане лицензирования.</span><span class="sxs-lookup"><span data-stu-id="10376-112">Use these commands to list the services that are available in each licensing plan.</span></span>

```powershell
$allSKUs=Get-AzureADSubscribedSku
$licArray = @()
for($i = 0; $i -lt $allSKUs.Count; $i++)
{
$licArray += "Service Plan: " + $allSKUs[$i].SkuPartNumber
$licArray +=  Get-AzureADSubscribedSku -ObjectID $allSKUs[$i].ObjectID | Select -ExpandProperty ServicePlans
$licArray +=  ""
}
$licArray
```

<span data-ttu-id="10376-113">Используйте эти команды для получения списка лицензий, которые назначены учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="10376-113">Use these commands to list the licenses that are assigned to a user account.</span></span>

```powershell
$userUPN="<user account UPN, such as belindan@contoso.com>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="10376-114">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="10376-114">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="10376-115">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="10376-115">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="10376-116">Затем запустите эту команду, чтобы получить список планов лицензирования, доступных в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="10376-116">Next, run this command to list the licensing plans that are available in your organization.</span></span> 

```powershell
Get-MsolAccountSku
```
>[!Note]
><span data-ttu-id="10376-117">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="10376-117">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="10376-118">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10376-118">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="10376-119">Затем запустите следующую команду, чтобы получить список служб, доступных в каждом плане лицензирования, а также порядок их перечисления (номер индекса).</span><span class="sxs-lookup"><span data-stu-id="10376-119">Next, run this command to list the services that are available in each licensing plan, and the order in which they are listed (the index number).</span></span>

```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```
  
<span data-ttu-id="10376-120">Используйте эту команду, чтобы получить список лицензий, которые назначены пользователю, и порядок их перечисления (номер индекса).</span><span class="sxs-lookup"><span data-stu-id="10376-120">Use this command to list the licenses that are assigned to a user, and the order in which they are listed (the index number).</span></span>

```powershell
Get-MsolUser -UserPrincipalName <user account UPN> | Format-List DisplayName,Licenses
```

### <a name="to-view-services-for-a-user-account"></a><span data-ttu-id="10376-121">Просмотр служб для учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="10376-121">To view services for a user account</span></span>

<span data-ttu-id="10376-122">Чтобы просмотреть все службы Microsoft 365, к которые пользователь имеет доступ, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="10376-122">To view all the Microsoft 365 services that a user has access to, use the following syntax:</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName <user account UPN>).Licenses[<LicenseIndexNumber>].ServiceStatus
```

<span data-ttu-id="10376-123">В этом примере показаны службы, к которым у BelindaN@litwareinc.com есть доступ.</span><span class="sxs-lookup"><span data-stu-id="10376-123">This example shows the services to which the user BelindaN@litwareinc.com has access.</span></span> <span data-ttu-id="10376-124">Этот код показывает службы, связанные со всеми лицензиями, назначенными ее учетной записи.</span><span class="sxs-lookup"><span data-stu-id="10376-124">This shows the services that are associated with all licenses that are assigned to her account.</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses.ServiceStatus
```

<span data-ttu-id="10376-125">Этот код показывает службы, к которым у пользователя BelindaN@litwareinc.com есть доступ по первой назначенной ей лицензии (индекс 0).</span><span class="sxs-lookup"><span data-stu-id="10376-125">This example shows the services that user BelindaN@litwareinc.com has access to from the first license that's assigned to her account (the index number is 0).</span></span>
  
```powershell
(Get-MsolUser -UserPrincipalName belindan@litwareinc.com).Licenses[0].ServiceStatus
```

<span data-ttu-id="10376-126">Чтобы просмотреть все службы для пользователя, которому назначено несколько лицензий, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="10376-126">To view all the services for a user who has been assigned *multiple licenses*, use the following syntax:</span></span>

```powershell
$userUPN="<user account UPN>"
$AllLicenses=(Get-MsolUser -UserPrincipalName $userUPN).Licenses
$licArray = @()
for($i = 0; $i -lt $AllLicenses.Count; $i++)
{
$licArray += "License: " + $AllLicenses[$i].AccountSkuId
$licArray +=  $AllLicenses[$i].ServiceStatus
$licArray +=  ""
}
$licArray
```
 
## <a name="see-also"></a><span data-ttu-id="10376-127">См. также</span><span class="sxs-lookup"><span data-stu-id="10376-127">See also</span></span>

[<span data-ttu-id="10376-128">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="10376-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="10376-129">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="10376-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="10376-130">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="10376-130">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
