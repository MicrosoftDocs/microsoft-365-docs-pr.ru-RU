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
description: В этой статье рассказывается, как быстро и легко использовать PowerShell для Microsoft 365, чтобы назначить роли администратора учетным записям пользователей.
ms.openlocfilehash: 1486c86172cd34e6e88f8cd02d003967518bcdb7
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655951"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="82663-103">Назначение ролей администратора учетным записям пользователей Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="82663-103">Assign admin roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="82663-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="82663-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="82663-105">Вы можете быстро и легко назначать роли администратора учетным записям пользователей с помощью PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="82663-105">You can quickly and easily assign admin roles to user accounts using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="82663-106">[Узнайте, как назначать роли администратора учетным записям пользователей](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) с помощью центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="82663-106">[Learn how to assign admin roles to user accounts](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="82663-107">Список дополнительных ресурсов приведен в разделе [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="82663-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="82663-108">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="82663-108">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="82663-109">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) , используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="82663-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) using a global administrator account.</span></span>
  
<span data-ttu-id="82663-p102">Затем определите имя входа для учетной записи пользователя, которую нужно добавить в роль (пример: fredsm@contoso.com). Оно также называется именем участника-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="82663-p102">Next, determine the sign-in name of the user account that you want to add to a role (example: fredsm@contoso.com). This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="82663-112">Затем определите имя роли администратора.</span><span class="sxs-lookup"><span data-stu-id="82663-112">Next, determine the name of the admin role.</span></span> <span data-ttu-id="82663-113">Используйте [список разрешений роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="82663-113">Use this [list of administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="82663-114">Обратите внимание на примечания в этой статье.</span><span class="sxs-lookup"><span data-stu-id="82663-114">Pay attention to the notes in this article.</span></span> <span data-ttu-id="82663-115">Некоторые имена ролей отличаются для Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82663-115">Some role names are different for Azure AD PowerShell.</span></span> <span data-ttu-id="82663-116">Например роль "Администратор SharePoint" в центре администрирования Microsoft 365 называется "Администратор службы SharePoint" для Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82663-116">For example, the "SharePoint Administrator" role in the Microsoft 365 admin center is named "SharePoint Service Administrator" for Azure AD PowerShell.</span></span>
>

<span data-ttu-id="82663-117">Затем укажите имена для входа и роли и выполните указанные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="82663-117">Next, fill in the sign-in and role names and run these commands.</span></span>
  
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

<span data-ttu-id="82663-118">Ниже приведен пример завершенного набора команд, который назначает роль администратора службы SharePoint для учетной записи belindan@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="82663-118">Here is an example of a completed command set that assigns the SharePoint Service Administrator admin role to the belindan@contoso.com account:</span></span>
  
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

<span data-ttu-id="82663-119">Чтобы отобразить список имен пользователей для определенной роли администратора, используйте следующие команды.</span><span class="sxs-lookup"><span data-stu-id="82663-119">To display the list of user names for a specific admin role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="82663-120">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="82663-120">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="82663-121">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) , используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="82663-121">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) using a global administrator account.</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="82663-122">Изменение одной роли</span><span class="sxs-lookup"><span data-stu-id="82663-122">For a single role change</span></span>

<span data-ttu-id="82663-123">Наиболее распространенные способы конкретной учетной записи пользователя с отображаемым именем или его адресом электронной почты, также известным именем для входа или именем участника-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="82663-123">The most common ways of specific user account is with its display name or its email name, also known its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="82663-124">Отображение имен учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="82663-124">Display names of user accounts</span></span>

<span data-ttu-id="82663-125">Если вы используете для работы с отображаемыми именами учетных записей пользователей, определите следующее:</span><span class="sxs-lookup"><span data-stu-id="82663-125">If you are used to working with the display names of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="82663-126">Учетная запись пользователя, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="82663-126">The user account that you want to configure.</span></span>
    
    <span data-ttu-id="82663-p105">Чтобы указать учетную запись пользователя, необходимо определить ее отображаемое имя. Чтобы получить список учетных записей, используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="82663-p105">To specify the user account, you must determine its Display Name. To get a complete list accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="82663-p106">Эта команда выводит учетные записи пользователей, отсортированное по отображаемому имени, по одному экрану за раз. Вы можете отфильтровать список, используя командлет **Where**. Вот пример:</span><span class="sxs-lookup"><span data-stu-id="82663-p106">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time. You can filter the list to a smaller set by using the **Where** cmdlet. Here is an example:</span></span>

   >[!Note]
   ><span data-ttu-id="82663-132">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="82663-132">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="82663-133">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82663-133">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="82663-134">Эта команда выводит только учетные записи пользователей, отображаемое имя которых начинается со слова "John".</span><span class="sxs-lookup"><span data-stu-id="82663-134">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="82663-135">Роль, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="82663-135">The role you want to assign.</span></span>
    
    <span data-ttu-id="82663-136">Чтобы отобразить список доступных ролей администратора, которые можно назначить учетным записям пользователей, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="82663-136">To display the list of available admin roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="82663-137">После определения отображаемого имени учетной записи и имени роли администратора, используйте следующие команды, чтобы назначить роль учетной записи:</span><span class="sxs-lookup"><span data-stu-id="82663-137">Once you have determined the Display Name of the account and the Name of the admin role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="82663-138">Скопируйте команды в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="82663-138">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="82663-139">Для переменных **$dispName** и **$roleName** замените текст описания их значениями, удалите \< and > символы и оставьте кавычки.</span><span class="sxs-lookup"><span data-stu-id="82663-139">For the **$dispName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="82663-140">Скопируйте измененные строки в окно модуля Windows Azure Active Directory для Windows PowerShell, чтобы запустить их.</span><span class="sxs-lookup"><span data-stu-id="82663-140">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="82663-141">Кроме того, можно использовать интегрированную среду сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82663-141">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="82663-142">Вот пример полного набора команд:</span><span class="sxs-lookup"><span data-stu-id="82663-142">Here is an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="82663-143">Имена для входа учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="82663-143">Sign-in names of user accounts</span></span>

<span data-ttu-id="82663-144">Если вы используете учетные записи или имена участников для учетных записей пользователей, определите следующее:</span><span class="sxs-lookup"><span data-stu-id="82663-144">If you are used to working with the sign-in names or UPNs of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="82663-145">Имя участника-пользователя для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="82663-145">The user account's UPN.</span></span>
    
    <span data-ttu-id="82663-146">Если вы еще не знаете имя участника-пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="82663-146">If you don't already know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="82663-147">Эта команда перечисляет UPN учетных записей пользователей, отсортированных по имени участника-пользователя по одному экрану за раз.</span><span class="sxs-lookup"><span data-stu-id="82663-147">This command lists the UPN of your user accounts, sorted by the UPN, one screen at a time.</span></span> <span data-ttu-id="82663-148">Вы можете отфильтровать список, используя командлет **Where**.</span><span class="sxs-lookup"><span data-stu-id="82663-148">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="82663-149">Вот пример:</span><span class="sxs-lookup"><span data-stu-id="82663-149">Here is an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="82663-150">Эта команда выводит только учетные записи пользователей, отображаемое имя которых начинается со слова "John".</span><span class="sxs-lookup"><span data-stu-id="82663-150">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="82663-151">Роль, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="82663-151">The role you want to assign.</span></span>
    
    <span data-ttu-id="82663-152">Чтобы отобразить список доступных ролей, используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="82663-152">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="82663-153">После получения имени участника-пользователя для учетной записи и имени роли выполните следующие команды, чтобы назначить роль учетной записи:</span><span class="sxs-lookup"><span data-stu-id="82663-153">Once you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="82663-154">Скопируйте команды в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="82663-154">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="82663-155">Для переменных **$upnName** и **$roleName** замените текст описания их значениями, удалите \< and > символы и оставьте кавычки.</span><span class="sxs-lookup"><span data-stu-id="82663-155">For the **$upnName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="82663-156">Скопируйте измененные строки в окно модуля Windows Azure Active Directory для Windows PowerShell, чтобы запустить их.</span><span class="sxs-lookup"><span data-stu-id="82663-156">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="82663-157">Кроме того, вы можете использовать среду Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="82663-157">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="82663-158">Вот пример полного набора команд:</span><span class="sxs-lookup"><span data-stu-id="82663-158">Here is an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="82663-159">Изменение нескольких ролей</span><span class="sxs-lookup"><span data-stu-id="82663-159">Multiple role changes</span></span>

<span data-ttu-id="82663-160">Для изменения нескольких ролей определите следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="82663-160">For multiple role changes, determine the following:</span></span>
  
- <span data-ttu-id="82663-161">Какие учетные записи пользователей вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="82663-161">Which user accounts that you want to configure.</span></span> <span data-ttu-id="82663-162">Методы, описанные в предыдущем разделе, можно использовать для сбора набора отображаемых имен или UPN.</span><span class="sxs-lookup"><span data-stu-id="82663-162">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="82663-163">Какие роли вы хотите назначить каждой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="82663-163">Which roles you want to assign to each user account.</span></span>
    
    <span data-ttu-id="82663-164">Чтобы отобразить список доступных ролей, используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="82663-164">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="82663-165">Затем создайте текстовый файл с разделителями-запятыми (CSV), в котором отображаются поля отображаемого имени или имени участника-пользователя и имени роли.</span><span class="sxs-lookup"><span data-stu-id="82663-165">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="82663-166">Вы можете легко сделать это с помощью Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="82663-166">You can do this easily with Microsoft Excel.</span></span>

<span data-ttu-id="82663-167">Ниже приведен пример для отображаемых имен:</span><span class="sxs-lookup"><span data-stu-id="82663-167">Here is an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="82663-168">Затем укажите расположение CSV-файла и запустите получившиеся команды в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82663-168">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="82663-169">Ниже приведен пример для UPN:</span><span class="sxs-lookup"><span data-stu-id="82663-169">Here is an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="82663-170">Затем укажите расположение CSV-файла и запустите получившиеся команды в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82663-170">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="82663-171">См. также</span><span class="sxs-lookup"><span data-stu-id="82663-171">See also</span></span>

- [<span data-ttu-id="82663-172">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="82663-172">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="82663-173">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="82663-173">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="82663-174">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="82663-174">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
