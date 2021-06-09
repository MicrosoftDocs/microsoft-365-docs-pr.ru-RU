---
title: Просмотр лицензированных и нелицензионных Microsoft 365 с Помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/21/2020
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
- seo-marvel-apr2020
ms.assetid: e4ee53ed-ed36-4993-89f4-5bec11031435
description: В этой статье рассказывается, как использовать PowerShell для просмотра лицензированных и нелицензионных учетных записей Microsoft 365 пользователей.
ms.openlocfilehash: b38ee7674abaea6b63d0661ba79a9814f8c54229
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651388"
---
# <a name="view-licensed-and-unlicensed-microsoft-365-users-with-powershell"></a><span data-ttu-id="1b724-103">Просмотр лицензированных и нелицензионных Microsoft 365 с Помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b724-103">View licensed and unlicensed Microsoft 365 users with PowerShell</span></span>

<span data-ttu-id="1b724-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="1b724-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1b724-105">Учетные записи пользователей в Microsoft 365 организации могут иметь некоторые, все или ни одной из доступных лицензий, присвоенных им из планов лицензирования, доступных в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1b724-105">User accounts in your Microsoft 365 organization may have some, all, or none of the available licenses assigned to them from the licensing plans that are available in your organization.</span></span> <span data-ttu-id="1b724-106">Вы можете использовать PowerShell для Microsoft 365, чтобы быстро найти лицензированных и нелицензионных пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1b724-106">You can use PowerShell for Microsoft 365 to quickly find the licensed and unlicensed users in your organization.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1b724-107">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="1b724-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1b724-108">[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="1b724-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
<span data-ttu-id="1b724-109">Чтобы просмотреть список всех учетных записей пользователей в организации, которые не были назначены ни одной из ваших планов лицензирования (нелицензионных пользователей), запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1b724-109">To view the list of all user accounts in your organization that have NOT been assigned any of your licensing plans (unlicensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach{ $licensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $false) { Write-Host $_.UserPrincipalName} }
```

<span data-ttu-id="1b724-110">Чтобы просмотреть список всех учетных записей пользователей в организации, которые были назначены любым из ваших планов лицензирования (лицензированных пользователей), запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1b724-110">To view the list of all user accounts in your organization that have been assigned any of your licensing plans (licensed users), run the following command:</span></span>
  
```powershell
Get-AzureAdUser | ForEach { $licensed=$True ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If( [string]::IsNullOrEmpty(  $_.AssignedLicenses[$i].SkuId ) -ne $True) { $licensed=$true } } ; If( $licensed -eq $true) { Write-Host $_.UserPrincipalName} }
```

>[!Note]
><span data-ttu-id="1b724-111">Чтобы перечислить всех пользователей подписки, используйте `Get-AzureAdUser -All $true` команду.</span><span class="sxs-lookup"><span data-stu-id="1b724-111">To list all of the users in your subscription, use the `Get-AzureAdUser -All $true` command.</span></span>
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1b724-112">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b724-112">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="1b724-113">[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="1b724-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="1b724-114">Чтобы просмотреть список всех учетных записей пользователей и их состояние лицензирования в организации, запустите следующую команду в PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1b724-114">To view the list of all user accounts and their licensing status in your organization, run the following command in PowerShell:</span></span>
  
```powershell
Get-MsolUser -All
```

>[!Note]
><span data-ttu-id="1b724-115">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="1b724-115">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="1b724-116">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b724-116">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="1b724-117">Чтобы отобразить список всех учетных записей пользователей без лицензий в вашей организации, выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="1b724-117">To view the list of all unlicensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

<span data-ttu-id="1b724-118">Чтобы отобразить список всех учетных записей пользователей с лицензиями в вашей организации, выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="1b724-118">To view the list of all licensed user accounts in your organization, run the following command:</span></span>
  
```powershell
Get-MsolUser -All | where {$_.isLicensed -eq $true}
```

## <a name="see-also"></a><span data-ttu-id="1b724-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1b724-119">See also</span></span>

[<span data-ttu-id="1b724-120">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b724-120">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1b724-121">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="1b724-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1b724-122">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1b724-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
