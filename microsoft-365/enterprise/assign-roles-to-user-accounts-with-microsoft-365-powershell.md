---
title: Назначение ролей учетным записям пользователей Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: В этой статье вы узнаете, как быстро и легко назначать роли администратора учетным записям пользователей с помощью PowerShell для Microsoft 365.
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754202"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="e3a88-103">Назначение ролей администратора учетным записям пользователей Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3a88-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="e3a88-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="e3a88-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e3a88-105">Вы можете легко назначать роли учетным записям пользователей с помощью PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3a88-105">You can easily assign roles to user accounts by using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="e3a88-106">Узнайте, как  [назначать роли администратора](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) учетным записям пользователей в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e3a88-106">Learn how to  [assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) to user accounts with the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="e3a88-107">Список дополнительных ресурсов см. в [подсети "Управление пользователями и группами".](https://docs.microsoft.com/microsoft-365/admin/add-users/)</span><span class="sxs-lookup"><span data-stu-id="e3a88-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e3a88-108">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="e3a88-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e3a88-109">Сначала используйте учетную запись глобального администратора [для подключения к вашему клиенту Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="e3a88-109">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="e3a88-110">Затем определите имя для входов учетной записи пользователя, которую нужно добавить в роль (пример: fredsm \@ contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e3a88-110">Next, identify the sign-in name of the user account that you want to add to a role (example: fredsm\@contoso.com).</span></span> <span data-ttu-id="e3a88-111">Это также называется именем основного пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="e3a88-111">This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="e3a88-112">После этого определите имя роли.</span><span class="sxs-lookup"><span data-stu-id="e3a88-112">Next, determine the name of the role.</span></span> <span data-ttu-id="e3a88-113">См. [разрешения роли администратора в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="e3a88-113">See [administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="e3a88-114">Обратите внимание на примечания в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e3a88-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="e3a88-115">Некоторые имена ролей отличаются для Azure Active Directory (Azure AD) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3a88-115">Some role names are different for Azure Active Directory (Azure AD) PowerShell.</span></span> <span data-ttu-id="e3a88-116">Например, роль администратора *SharePoint* в Центре администрирования Microsoft 365 — администратор *Службы SharePoint в* Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3a88-116">For example, the *SharePoint Administrator* role in the Microsoft 365 admin center is *SharePoint Service Administrator* in Azure AD PowerShell.</span></span>
>

<span data-ttu-id="e3a88-117">После этого заполните имена для входов и ролей и запустите следующие команды:</span><span class="sxs-lookup"><span data-stu-id="e3a88-117">Next, fill in the sign-in and role names and run these commands:</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<admin role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="e3a88-118">Вот пример завершенного набора команд, который назначает роль администратора SharePoint Service учетной записи пользователя *belindan \@ contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="e3a88-118">Here's an example of a completed command set that assigns the SharePoint Service Administrator role to the *belindan\@contoso.com* account:</span></span>
  
```powershell
$userName="belindan@contoso.com"
$roleName="SharePoint Service Administrator"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="e3a88-119">Чтобы отобразить список имен пользователей для определенной роли администратора, используйте эти команды.</span><span class="sxs-lookup"><span data-stu-id="e3a88-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e3a88-120">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3a88-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e3a88-121">Сначала используйте учетную запись глобального администратора [для подключения к вашему клиенту Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="e3a88-121">First, use a global administrator account to [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="e3a88-122">Изменение одной роли</span><span class="sxs-lookup"><span data-stu-id="e3a88-122">For a single role change</span></span>

<span data-ttu-id="e3a88-123">Чаще всего указать учетную запись пользователя можно с помощью отображаемого имени или имени электронной почты, которое также называется именем для регистрации или именем пользователя-пользователя .</span><span class="sxs-lookup"><span data-stu-id="e3a88-123">The most common ways to specify the user account is by using its display name or its email name, which also known as its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="e3a88-124">Отображение имен учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="e3a88-124">Display names of user accounts</span></span>

<span data-ttu-id="e3a88-125">Если вы привыкли работать с отображаемой информацией об учетных записях пользователей, определите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e3a88-125">If you're used to working with the display names of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="e3a88-126">Учетная запись пользователя, которую необходимо настроить</span><span class="sxs-lookup"><span data-stu-id="e3a88-126">The user account that you want to configure</span></span>
    
    <span data-ttu-id="e3a88-127">Чтобы указать учетную запись пользователя, необходимо определить ее отображаемое имя.</span><span class="sxs-lookup"><span data-stu-id="e3a88-127">To specify the user account, you must determine its Display Name.</span></span> <span data-ttu-id="e3a88-128">Чтобы получить полный список учетных записей, используйте команду:</span><span class="sxs-lookup"><span data-stu-id="e3a88-128">To get a complete list of accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="e3a88-129">Эта команда выводит учетные записи пользователей, отсортированное по отображаемому имени, по одному экрану за раз.</span><span class="sxs-lookup"><span data-stu-id="e3a88-129">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time.</span></span> <span data-ttu-id="e3a88-130">Вы можете отфильтровать список, используя командлет **Where**.</span><span class="sxs-lookup"><span data-stu-id="e3a88-130">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="e3a88-131">См. следующий пример.</span><span class="sxs-lookup"><span data-stu-id="e3a88-131">See the following example.</span></span>

   >[!Note]
   ><span data-ttu-id="e3a88-132">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*.</span><span class="sxs-lookup"><span data-stu-id="e3a88-132">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="e3a88-133">Эти командлеты требуется запускать из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3a88-133">Run these cmdlets from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="e3a88-134">Эта команда выводит только учетные записи пользователей, отображаемое имя которых начинается со слова "John".</span><span class="sxs-lookup"><span data-stu-id="e3a88-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="e3a88-135">Роль, которую вы хотите назначить</span><span class="sxs-lookup"><span data-stu-id="e3a88-135">The role you want to assign</span></span>
    
    <span data-ttu-id="e3a88-136">Чтобы отобразить список доступных ролей администратора, которые можно назначить учетным записям пользователей, используйте команду:</span><span class="sxs-lookup"><span data-stu-id="e3a88-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="e3a88-137">После определения отображаемого имени учетной записи и роли используйте эти команды, чтобы назначить роль учетной записи:</span><span class="sxs-lookup"><span data-stu-id="e3a88-137">After you determine the Display Name of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="e3a88-138">Paste the commands into Notepad.</span><span class="sxs-lookup"><span data-stu-id="e3a88-138">Paste the commands into Notepad.</span></span> <span data-ttu-id="e3a88-139">Для *переменных $dispName* *и $roleName* замените текст описания их значениями.</span><span class="sxs-lookup"><span data-stu-id="e3a88-139">For the *$dispName* and *$roleName* variables, replace the description text with their values.</span></span> <span data-ttu-id="e3a88-140">Удалите \< and > символы, но сохраняем кавычка.</span><span class="sxs-lookup"><span data-stu-id="e3a88-140">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="e3a88-141">В paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell to run them.</span><span class="sxs-lookup"><span data-stu-id="e3a88-141">Paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="e3a88-142">Кроме того, можно использовать интегрированную среду сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3a88-142">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="e3a88-143">Вот пример завершенного набора команд:</span><span class="sxs-lookup"><span data-stu-id="e3a88-143">Here's an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="e3a88-144">Имена учетных записей пользователей для входов</span><span class="sxs-lookup"><span data-stu-id="e3a88-144">Sign-in names of user accounts</span></span>

<span data-ttu-id="e3a88-145">Если вы привыкли работать с именами или именами пользователей для входов в учетные записи пользователей, определите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e3a88-145">If you're used to working with the sign-in names or UPNs of user accounts, determine the following information:</span></span>
  
- <span data-ttu-id="e3a88-146">UpN учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="e3a88-146">The user account's UPN</span></span>
    
    <span data-ttu-id="e3a88-147">Если вы не знаете upN, используйте команду:</span><span class="sxs-lookup"><span data-stu-id="e3a88-147">If you don't know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="e3a88-148">Эта команда перечисляет имя upn учетных записей пользователей, отсортировать их по одному экрану за раз.</span><span class="sxs-lookup"><span data-stu-id="e3a88-148">This command lists the UPN of your user accounts, sorted by UPN, one screen at a time.</span></span> <span data-ttu-id="e3a88-149">Для фильтрации **списка** можно использовать этот список с помощью cmdlet Where.</span><span class="sxs-lookup"><span data-stu-id="e3a88-149">You can use the **Where** cmdlet to filter the list.</span></span> <span data-ttu-id="e3a88-150">Пример:</span><span class="sxs-lookup"><span data-stu-id="e3a88-150">Here's an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="e3a88-151">Эта команда выводит только учетные записи пользователей, отображаемое имя которых начинается со слова "John".</span><span class="sxs-lookup"><span data-stu-id="e3a88-151">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="e3a88-152">Роль, которую вы хотите назначить</span><span class="sxs-lookup"><span data-stu-id="e3a88-152">The role you want to assign</span></span>
    
    <span data-ttu-id="e3a88-153">Чтобы отобразить список доступных ролей, используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="e3a88-153">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="e3a88-154">После присвоения имени имени пользователя учетной записи и имени роли используйте эти команды, чтобы назначить роль учетной записи:</span><span class="sxs-lookup"><span data-stu-id="e3a88-154">After you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="e3a88-155">Скопируйте команды в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="e3a88-155">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="e3a88-156">Для **$upnName** и **$roleName** переменных.</span><span class="sxs-lookup"><span data-stu-id="e3a88-156">For the **$upnName** and **$roleName** variables.</span></span> <span data-ttu-id="e3a88-157">Замените текст описания их значениями.</span><span class="sxs-lookup"><span data-stu-id="e3a88-157">Replace the description text with their values.</span></span> <span data-ttu-id="e3a88-158">Удалите \< and > символы, но сохраняем кавычка.</span><span class="sxs-lookup"><span data-stu-id="e3a88-158">Remove the \< and > characters but keep the quotation marks.</span></span> <span data-ttu-id="e3a88-159">В paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span><span class="sxs-lookup"><span data-stu-id="e3a88-159">Paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="e3a88-160">Кроме того, можно использовать Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="e3a88-160">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="e3a88-161">Вот пример завершенного набора команд:</span><span class="sxs-lookup"><span data-stu-id="e3a88-161">Here's an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="e3a88-162">Несколько изменений ролей</span><span class="sxs-lookup"><span data-stu-id="e3a88-162">Multiple role changes</span></span>

<span data-ttu-id="e3a88-163">Для нескольких изменений ролей определите следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e3a88-163">For multiple role changes, determine the following information:</span></span>
  
- <span data-ttu-id="e3a88-164">Какие учетные записи пользователей необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="e3a88-164">Which user accounts you want to configure.</span></span> <span data-ttu-id="e3a88-165">Вы можете использовать методы, показанные в предыдущем разделе, для сбора набора отображаемого имени или имен upNs.</span><span class="sxs-lookup"><span data-stu-id="e3a88-165">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="e3a88-166">Какие роли вы хотите назначить каждой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="e3a88-166">Which roles you want to assign to each user account.</span></span> <span data-ttu-id="e3a88-167">Чтобы отобразить список доступных ролей, используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="e3a88-167">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="e3a88-168">Затем создайте текстовый файл с разделиными запятой (CSV-файл), который имеет отображаемого имени или имени имени upn и поля имени роли.</span><span class="sxs-lookup"><span data-stu-id="e3a88-168">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="e3a88-169">Это легко сделать в Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="e3a88-169">You can do this easily in Microsoft Excel.</span></span>

<span data-ttu-id="e3a88-170">Вот пример отображаемой имена:</span><span class="sxs-lookup"><span data-stu-id="e3a88-170">Here's an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="e3a88-171">Затем укажите расположение CSV-файла и запустите получившиеся команды в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3a88-171">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="e3a88-172">Вот пример для upNs:</span><span class="sxs-lookup"><span data-stu-id="e3a88-172">Here's an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="e3a88-173">Затем укажите расположение CSV-файла и запустите получившиеся команды в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e3a88-173">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="e3a88-174">См. также</span><span class="sxs-lookup"><span data-stu-id="e3a88-174">See also</span></span>

- [<span data-ttu-id="e3a88-175">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3a88-175">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e3a88-176">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e3a88-176">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="e3a88-177">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e3a88-177">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
