---
title: Блокировка учетных записей пользователей Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
- seo-marvel-apr2020
ms.assetid: 04e58c2a-400b-496a-acd4-8ec5d37236dc
description: В этой статье объясняется, как заблокировать и разблокировать доступ к учетным записям Microsoft 365 с помощью PowerShell.
ms.openlocfilehash: a9ade2f41fb601da00ca1c2d1905ca0cb003dcb3
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693199"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="6ef79-103">Блокировка учетных записей пользователей Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ef79-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="6ef79-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="6ef79-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6ef79-105">Блокировка доступа к учетной записи Microsoft 365 запрещает всем пользователям использовать эту учетную запись для входа и доступа к службам и данным в организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ef79-105">Blocking access to a Microsoft 365 account prevents anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="6ef79-106">С помощью PowerShell можно блокировать доступ к отдельным и нескольким учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="6ef79-106">You can use PowerShell to block access to individual and multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6ef79-107">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="6ef79-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6ef79-108">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6ef79-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="6ef79-109">Блокировка доступа к отдельным учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="6ef79-109">Block access to individual user accounts</span></span>

<span data-ttu-id="6ef79-110">Используйте следующий синтаксис, чтобы заблокировать отдельную учетную запись пользователя:</span><span class="sxs-lookup"><span data-stu-id="6ef79-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="6ef79-111">Параметр – ObjectID в командлете Set – AzureAD принимает либо имя входа учетной записи, также называемое именем участника пользователя, либо идентификатор объекта учетной записи.</span><span class="sxs-lookup"><span data-stu-id="6ef79-111">The -ObjectID parameter in the Set-AzureAD cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span> 
  
<span data-ttu-id="6ef79-112">В этом примере блокируется доступ к учетной записи пользователя fabricec@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="6ef79-112">This example blocks access to the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="6ef79-113">Чтобы разблокировать эту учетную запись пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6ef79-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="6ef79-114">Чтобы отобразить учетную запись участника-пользователя на основе отображаемого имени пользователя, используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="6ef79-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="6ef79-115">В этом примере отображается имя участника-пользователя для учетной записи пользователя с именем Caleb Sills.</span><span class="sxs-lookup"><span data-stu-id="6ef79-115">This example displays the user account UPN for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="6ef79-116">Чтобы заблокировать учетную запись на основе отображаемого имени пользователя, используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="6ef79-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="6ef79-117">В любое время вы можете проверить состояние блокировки учетной записи пользователя с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="6ef79-117">At any time, you can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-access-to-multiple-user-accounts"></a><span data-ttu-id="6ef79-118">Блокировка доступа к нескольким учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="6ef79-118">Block access to multiple user accounts</span></span>

<span data-ttu-id="6ef79-119">Чтобы заблокировать доступ к нескольким учетным записям пользователей, создайте текстовый файл с одним именем входа учетной записи в каждой строке, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="6ef79-119">To block access to multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="6ef79-120">В приведенных ниже командах пример текстового файла — "мой Documents\Accounts.txt".</span><span class="sxs-lookup"><span data-stu-id="6ef79-120">In the following commands, the example text file is C:\My Documents\Accounts.txt.</span></span> <span data-ttu-id="6ef79-121">Замените путь и имя файла для текстового файла.</span><span class="sxs-lookup"><span data-stu-id="6ef79-121">Replace this with the path and file name of your text file.</span></span>
  
<span data-ttu-id="6ef79-122">Чтобы заблокировать доступ к учетным записям, перечисленным в текстовом файле, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6ef79-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="6ef79-123">Чтобы разблокировать учетные записи, перечисленные в текстовом файле, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6ef79-123">To unblock the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6ef79-124">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ef79-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6ef79-125">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="6ef79-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="6ef79-126">Блокировка доступа к отдельным учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="6ef79-126">Block access to individual user accounts</span></span>

<span data-ttu-id="6ef79-127">Используйте следующий синтаксис, чтобы заблокировать доступ к отдельной учетной записи пользователя:</span><span class="sxs-lookup"><span data-stu-id="6ef79-127">Use the following syntax to block access to an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="6ef79-128">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="6ef79-128">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="6ef79-129">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ef79-129">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="6ef79-130">В этом примере блокируется доступ к учетной записи пользователя fabricec@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="6ef79-130">This example blocks access to the user account fabricec@litwareinc.com.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="6ef79-131">Чтобы разблокировать учетную запись пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6ef79-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="6ef79-132">В любое время вы можете проверить состояние блокировки учетной записи пользователя с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="6ef79-132">At any time, you can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-to-multiple-user-accounts"></a><span data-ttu-id="6ef79-133">Блокировка доступа к нескольким учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="6ef79-133">Block access to multiple user accounts</span></span>

<span data-ttu-id="6ef79-134">Сначала создайте текстовый файл, который содержит одну учетную запись в каждой строке, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="6ef79-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="6ef79-135">В приведенных ниже командах пример текстового файла — "мой Documents\Accounts.txt".</span><span class="sxs-lookup"><span data-stu-id="6ef79-135">In the following commands, the example text file is C:\My Documents\Accounts.txt.</span></span> <span data-ttu-id="6ef79-136">Замените путь и имя файла для текстового файла.</span><span class="sxs-lookup"><span data-stu-id="6ef79-136">Replace this with the path and file name of your text file.</span></span>
    
<span data-ttu-id="6ef79-137">Чтобы заблокировать доступ к учетным записям, перечисленным в текстовом файле, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6ef79-137">To block access to the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="6ef79-138">Чтобы разблокировать учетные записи, перечисленные в текстовом файле, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6ef79-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="6ef79-139">См. также</span><span class="sxs-lookup"><span data-stu-id="6ef79-139">See also</span></span>

[<span data-ttu-id="6ef79-140">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ef79-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6ef79-141">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ef79-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6ef79-142">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6ef79-142">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
