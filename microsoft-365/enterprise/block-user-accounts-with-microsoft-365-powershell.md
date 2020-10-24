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
description: Использование PowerShell для блокировки и разблокирования доступа к учетным записям Microsoft 365.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754684"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="924c4-103">Блокировка учетных записей пользователей Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="924c4-103">Block Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="924c4-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="924c4-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="924c4-105">Заблокируя доступ к учетной записи Microsoft 365, вы не сможете использовать эту учетную запись для входа и доступа к службам и данным в вашей организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="924c4-105">When you block access to a Microsoft 365 account, you prevent anyone from using the account to sign in and access the services and data in your Microsoft 365 organization.</span></span> <span data-ttu-id="924c4-106">С помощью PowerShell можно заблокировать доступ к отдельным или нескольким учетным записям пользователей.</span><span class="sxs-lookup"><span data-stu-id="924c4-106">You can use PowerShell to block access to individual or multiple user accounts.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="924c4-107">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="924c4-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="924c4-108">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="924c4-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 
### <a name="block-access-to-individual-user-accounts"></a><span data-ttu-id="924c4-109">Блокировка доступа к отдельным учетным записям пользователей</span><span class="sxs-lookup"><span data-stu-id="924c4-109">Block access to individual user accounts</span></span>

<span data-ttu-id="924c4-110">Используйте следующий синтаксис, чтобы заблокировать отдельную учетную запись пользователя:</span><span class="sxs-lookup"><span data-stu-id="924c4-110">Use the following syntax to block an individual user account:</span></span>
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> <span data-ttu-id="924c4-111">Параметр *– ObjectID* в командлете **Set – AzureAD** принимает либо имя входа учетной записи, также называемое именем участника пользователя, либо идентификатор объекта учетной записи.</span><span class="sxs-lookup"><span data-stu-id="924c4-111">The *-ObjectID* parameter in the **Set-AzureAD** cmdlet accepts either the account sign-in name, also known as the User Principal Name, or the account's object ID.</span></span>
  
<span data-ttu-id="924c4-112">В этом примере блокируется доступ к учетной записи пользователя *fabricec@litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="924c4-112">This example blocks access to the user account *fabricec@litwareinc.com*.</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

<span data-ttu-id="924c4-113">Чтобы разблокировать эту учетную запись пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="924c4-113">To unblock this user account, run the following command:</span></span>
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

<span data-ttu-id="924c4-114">Чтобы отобразить учетную запись участника-пользователя на основе отображаемого имени пользователя, используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="924c4-114">To display the user account UPN based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

<span data-ttu-id="924c4-115">В этом примере отображается имя участника-пользователя для учетной записи пользователя  *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="924c4-115">This example displays the user account UPN for the user  *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="924c4-116">Чтобы заблокировать учетную запись на основе отображаемого имени пользователя, используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="924c4-116">To block an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

<span data-ttu-id="924c4-117">Чтобы проверить состояние блокировки учетной записи пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="924c4-117">To check the blocked status of a user account use the following command:</span></span>
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a><span data-ttu-id="924c4-118">Блокировка нескольких учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="924c4-118">Block multiple user accounts</span></span>

<span data-ttu-id="924c4-119">Чтобы заблокировать доступ к нескольким учетным записям пользователей, создайте текстовый файл, содержащий одно имя учетной записи в каждой строке, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="924c4-119">To block access for multiple user accounts, create a text file that contains one account sign-in name on each line like this:</span></span>
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

<span data-ttu-id="924c4-120">В приведенных ниже командах пример текстового файла — "мой *Documents\Accounts.txt*".</span><span class="sxs-lookup"><span data-stu-id="924c4-120">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="924c4-121">Замените имя этого файла на путь и имя файла текстового файла.</span><span class="sxs-lookup"><span data-stu-id="924c4-121">Replace this file name with the path and file name of your text file.</span></span>
  
<span data-ttu-id="924c4-122">Чтобы заблокировать доступ к учетным записям, перечисленным в текстовом файле, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="924c4-122">To block access to the accounts listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

<span data-ttu-id="924c4-123">Чтобы разблокировать учетные записи, перечисленные в текстовом файле, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="924c4-123">To unblock the accounts that are listed in the text file, run the following command:</span></span>
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="924c4-124">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="924c4-124">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="924c4-125">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="924c4-125">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
### <a name="block-individual-user-accounts"></a><span data-ttu-id="924c4-126">Блокировка отдельных учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="924c4-126">Block individual user accounts</span></span>

<span data-ttu-id="924c4-127">Чтобы заблокировать доступ для отдельной учетной записи пользователя, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="924c4-127">Use the following syntax to block access for an individual user account:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
><span data-ttu-id="924c4-128">PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для модулей Windows PowerShell и командлетов, в именах которых *MSOL* .</span><span class="sxs-lookup"><span data-stu-id="924c4-128">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="924c4-129">Эти командлеты необходимо запускать в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="924c4-129">You have to run these cmdlets from Windows PowerShell.</span></span>

<span data-ttu-id="924c4-130">В этом примере блокируется доступ к учетной записи пользователя *фабрицек \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="924c4-130">This example blocks access to the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

<span data-ttu-id="924c4-131">Чтобы разблокировать учетную запись пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="924c4-131">To unblock the user account, run the following command:</span></span>
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

<span data-ttu-id="924c4-132">Чтобы проверить состояние блокировки учетной записи пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="924c4-132">To check the blocked status of a user account run the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a><span data-ttu-id="924c4-133">Блокировка доступа для нескольких учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="924c4-133">Block access for multiple user accounts</span></span>

<span data-ttu-id="924c4-134">Сначала создайте текстовый файл, который содержит одну учетную запись в каждой строке, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="924c4-134">First, create a text file that contains one account on each line like this:</span></span>
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

<span data-ttu-id="924c4-135">В приведенных ниже командах пример текстового файла — "мой *Documents\Accounts.txt*".</span><span class="sxs-lookup"><span data-stu-id="924c4-135">In the following commands, the example text file is *C:\My Documents\Accounts.txt*.</span></span> <span data-ttu-id="924c4-136">Замените имя этого файла на путь и имя файла текстового файла.</span><span class="sxs-lookup"><span data-stu-id="924c4-136">Replace this file name with the path and file name of your text file.</span></span>
    
<span data-ttu-id="924c4-137">Чтобы заблокировать доступ к учетным записям, перечисленным в текстовом файле, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="924c4-137">To block access for the accounts that are listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
<span data-ttu-id="924c4-138">Чтобы разблокировать учетные записи, перечисленные в текстовом файле, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="924c4-138">To unblock the accounts listed in the text file, run the following command:</span></span>
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a><span data-ttu-id="924c4-139">См. также</span><span class="sxs-lookup"><span data-stu-id="924c4-139">See also</span></span>

[<span data-ttu-id="924c4-140">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="924c4-140">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="924c4-141">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="924c4-141">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="924c4-142">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="924c4-142">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
