---
title: Назначение ролей учетным записям пользователей Microsoft 365 с помощью PowerShell
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
- O365ITProTrain
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: ede7598c-b5d5-4e3e-a488-195f02f26d93
description: В этой статье рассказывается, как быстро и легко использовать PowerShell для Microsoft 365, чтобы назначать роли учетным записям пользователей.
ms.openlocfilehash: 4726dcea109490ff28299002bc5263aa15dca949
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693000"
---
# <a name="assign-roles-to-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="56300-103">Назначение ролей учетным записям пользователей Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="56300-103">Assign roles to Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="56300-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="56300-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="56300-105">Вы можете быстро и легко назначать роли учетным записям пользователей с помощью PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56300-105">You can quickly and easily assign roles to user accounts using PowerShell for Microsoft 365.</span></span>

>[!Note]
><span data-ttu-id="56300-106">Чтобы назначить роли учетным записям пользователей с помощью центра администрирования Microsoft 365, ознакомьтесь с приведенными [ниже инструкциями](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="56300-106">To assign roles to user accounts with the Microsoft 365 admin center, see [these instructions](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="56300-107">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="56300-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="56300-108">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) , используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="56300-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) using a global administrator account.</span></span>
  
<span data-ttu-id="56300-p101">Затем определите имя входа для учетной записи пользователя, которую нужно добавить в роль (пример: fredsm@contoso.com). Оно также называется именем участника-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="56300-p101">Next, determine the sign-in name of the user account that you want to add to a role (example: fredsm@contoso.com). This is also known as the user principal name (UPN).</span></span>

<span data-ttu-id="56300-111">После этого определите имя роли.</span><span class="sxs-lookup"><span data-stu-id="56300-111">Next, determine the name of the role.</span></span> <span data-ttu-id="56300-112">Используйте [список разрешений роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="56300-112">Use this [list of administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

>[!Note]
><span data-ttu-id="56300-113">Обратите внимание на примечания в этой статье.</span><span class="sxs-lookup"><span data-stu-id="56300-113">Pay attention to the notes in this article.</span></span> <span data-ttu-id="56300-114">Некоторые имена ролей отличаются для Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56300-114">Some role names are different for Azure AD PowerShell.</span></span> <span data-ttu-id="56300-115">Например роль "Администратор SharePoint" в центре администрирования Microsoft 365 называется "Администратор службы SharePoint" для Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56300-115">For example, the "SharePoint Administrator" role in the Microsoft 365 admin center is named "SharePoint Service Administrator" for Azure AD PowerShell.</span></span>
>

<span data-ttu-id="56300-116">Затем укажите имена для входа и роли и выполните указанные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="56300-116">Next, fill in the sign-in and role names and run these commands.</span></span>
  
```powershell
$userName="<sign-in name of the account>"
$roleName="<role name>"
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
if ($role -eq $null) {
$roleTemplate = Get-AzureADDirectoryRoleTemplate | Where {$_.displayName -eq $roleName}
Enable-AzureADDirectoryRole -RoleTemplateId $roleTemplate.ObjectId
$role = Get-AzureADDirectoryRole | Where {$_.displayName -eq $roleName}
}
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId (Get-AzureADUser | Where {$_.UserPrincipalName -eq $userName}).ObjectID
```

<span data-ttu-id="56300-117">Ниже приведен пример завершенного набора команд, который назначает роль администратора службы SharePoint учетной записи belindan@contoso.com:</span><span class="sxs-lookup"><span data-stu-id="56300-117">Here is an example of a completed command set that assigns the SharePoint Service Administrator role to the belindan@contoso.com account:</span></span>
  
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

<span data-ttu-id="56300-118">Чтобы отобразить список имен пользователей для определенной роли, используйте указанные ниже команды.</span><span class="sxs-lookup"><span data-stu-id="56300-118">To display the list of user names for a specific role, use these commands.</span></span>

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="56300-119">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56300-119">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="56300-120">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) , используя учетную запись глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="56300-120">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell) using a global administrator account.</span></span>
  
### <a name="for-a-single-role-change"></a><span data-ttu-id="56300-121">Изменение одной роли</span><span class="sxs-lookup"><span data-stu-id="56300-121">For a single role change</span></span>

<span data-ttu-id="56300-122">Наиболее распространенные способы конкретной учетной записи пользователя с отображаемым именем или его адресом электронной почты, также известным именем для входа или именем участника-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="56300-122">The most common ways of specific user account is with its display name or its email name, also known its sign-in name or user principal name (UPN).</span></span>

#### <a name="display-names-of-user-accounts"></a><span data-ttu-id="56300-123">Отображение имен учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="56300-123">Display names of user accounts</span></span>

<span data-ttu-id="56300-124">Если вы используете для работы с отображаемыми именами учетных записей пользователей, определите следующее:</span><span class="sxs-lookup"><span data-stu-id="56300-124">If you are used to working with the display names of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="56300-125">Учетная запись пользователя, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="56300-125">The user account that you want to configure.</span></span>
    
    <span data-ttu-id="56300-p104">Чтобы указать учетную запись пользователя, необходимо определить ее отображаемое имя. Чтобы получить список учетных записей, используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="56300-p104">To specify the user account, you must determine its Display Name. To get a complete list accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="56300-p105">Эта команда выводит учетные записи пользователей, отсортированное по отображаемому имени, по одному экрану за раз. Вы можете отфильтровать список, используя командлет **Where**. Вот пример:</span><span class="sxs-lookup"><span data-stu-id="56300-p105">This command lists the Display Name of your user accounts, sorted by the Display Name, one screen at a time. You can filter the list to a smaller set by using the **Where** cmdlet. Here is an example:</span></span>

   >[!Note]
   ><span data-ttu-id="56300-131">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="56300-131">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="56300-132">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56300-132">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    <span data-ttu-id="56300-133">Эта команда выводит только учетные записи пользователей, отображаемое имя которых начинается со слова "John".</span><span class="sxs-lookup"><span data-stu-id="56300-133">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="56300-134">Роль, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="56300-134">The role you want to assign.</span></span>
    
    <span data-ttu-id="56300-135">Чтобы отобразить список доступных ролей, используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="56300-135">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="56300-136">После того как вы определили отображаемое имя учетной записи и имя роли, используйте эти команды, чтобы назначить роль учетной записи:</span><span class="sxs-lookup"><span data-stu-id="56300-136">Once you have determined the Display Name of the account and the Name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

<span data-ttu-id="56300-137">Скопируйте команды в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="56300-137">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="56300-138">Для переменных **$dispName** и **$roleName** замените текст описания их значениями, удалите \< and > символы и оставьте кавычки.</span><span class="sxs-lookup"><span data-stu-id="56300-138">For the **$dispName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="56300-139">Скопируйте измененные строки в окно модуля Windows Azure Active Directory для Windows PowerShell, чтобы запустить их.</span><span class="sxs-lookup"><span data-stu-id="56300-139">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="56300-140">Кроме того, можно использовать интегрированную среду сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56300-140">Alternately, you can use the Windows PowerShell Integrated Script Environment (ISE).</span></span>
  
<span data-ttu-id="56300-141">Вот пример полного набора команд:</span><span class="sxs-lookup"><span data-stu-id="56300-141">Here is an example of a completed command set:</span></span>
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a><span data-ttu-id="56300-142">Имена для входа учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="56300-142">Sign-in names of user accounts</span></span>

<span data-ttu-id="56300-143">Если вы используете учетные записи или имена участников для учетных записей пользователей, определите следующее:</span><span class="sxs-lookup"><span data-stu-id="56300-143">If you are used to working with the sign-in names or UPNs of user accounts, determine the following:</span></span>
  
- <span data-ttu-id="56300-144">Имя участника-пользователя для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="56300-144">The user account's UPN.</span></span>
    
    <span data-ttu-id="56300-145">Если вы еще не знаете имя участника-пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="56300-145">If you don't already know the UPN, use this command:</span></span>
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="56300-146">Эта команда перечисляет UPN учетных записей пользователей, отсортированных по имени участника-пользователя по одному экрану за раз.</span><span class="sxs-lookup"><span data-stu-id="56300-146">This command lists the UPN of your user accounts, sorted by the UPN, one screen at a time.</span></span> <span data-ttu-id="56300-147">Вы можете отфильтровать список, используя командлет **Where**.</span><span class="sxs-lookup"><span data-stu-id="56300-147">You can filter the list to a smaller set by using the **Where** cmdlet.</span></span> <span data-ttu-id="56300-148">Вот пример:</span><span class="sxs-lookup"><span data-stu-id="56300-148">Here is an example:</span></span>
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    <span data-ttu-id="56300-149">Эта команда выводит только учетные записи пользователей, отображаемое имя которых начинается со слова "John".</span><span class="sxs-lookup"><span data-stu-id="56300-149">This command lists only the user accounts for which the Display Name starts with "John".</span></span>
    
- <span data-ttu-id="56300-150">Роль, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="56300-150">The role you want to assign.</span></span>
    
    <span data-ttu-id="56300-151">Чтобы отобразить список доступных ролей, используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="56300-151">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="56300-152">После получения имени участника-пользователя для учетной записи и имени роли выполните следующие команды, чтобы назначить роль учетной записи:</span><span class="sxs-lookup"><span data-stu-id="56300-152">Once you have the UPN of the account and the name of the role, use these commands to assign the role to the account:</span></span>
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

<span data-ttu-id="56300-153">Скопируйте команды в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="56300-153">Copy the commands and paste them into Notepad.</span></span> <span data-ttu-id="56300-154">Для переменных **$upnName** и **$roleName** замените текст описания их значениями, удалите \< and > символы и оставьте кавычки.</span><span class="sxs-lookup"><span data-stu-id="56300-154">For the **$upnName** and **$roleName** variables, replace the description text with their values, remove the \< and > characters, and leave the quotes.</span></span> <span data-ttu-id="56300-155">Скопируйте измененные строки в окно модуля Windows Azure Active Directory для Windows PowerShell, чтобы запустить их.</span><span class="sxs-lookup"><span data-stu-id="56300-155">Copy the modified lines and paste them into your Windows Azure Active Directory Module for Windows PowerShell window to run them.</span></span> <span data-ttu-id="56300-156">Кроме того, вы можете использовать среду Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="56300-156">Alternately, you can use the Windows PowerShell ISE.</span></span>
  
<span data-ttu-id="56300-157">Вот пример полного набора команд:</span><span class="sxs-lookup"><span data-stu-id="56300-157">Here is an example of a completed command set:</span></span>
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a><span data-ttu-id="56300-158">Изменение нескольких ролей</span><span class="sxs-lookup"><span data-stu-id="56300-158">Multiple role changes</span></span>

<span data-ttu-id="56300-159">Для изменения нескольких ролей определите следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="56300-159">For multiple role changes, determine the following:</span></span>
  
- <span data-ttu-id="56300-160">Какие учетные записи пользователей вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="56300-160">Which user accounts that you want to configure.</span></span> <span data-ttu-id="56300-161">Методы, описанные в предыдущем разделе, можно использовать для сбора набора отображаемых имен или UPN.</span><span class="sxs-lookup"><span data-stu-id="56300-161">You can use the methods in the previous section to gather the set of display names or UPNs.</span></span>
    
- <span data-ttu-id="56300-162">Какие роли вы хотите назначить каждой учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="56300-162">Which roles you want to assign to each user account.</span></span>
    
    <span data-ttu-id="56300-163">Чтобы отобразить список доступных ролей, используйте эту команду:</span><span class="sxs-lookup"><span data-stu-id="56300-163">To display the list of available roles that you can assign to user accounts, use this command:</span></span>
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

<span data-ttu-id="56300-164">Затем создайте текстовый файл с разделителями-запятыми (CSV), в котором отображаются поля отображаемого имени или имени участника-пользователя и имени роли.</span><span class="sxs-lookup"><span data-stu-id="56300-164">Next, create a comma-separated value (CSV) text file that has the display name or UPN and role name fields.</span></span> <span data-ttu-id="56300-165">Вы можете легко сделать это с помощью Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="56300-165">You can do this easily with Microsoft Excel.</span></span>

<span data-ttu-id="56300-166">Ниже приведен пример для отображаемых имен:</span><span class="sxs-lookup"><span data-stu-id="56300-166">Here is an example for display names:</span></span>
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

<span data-ttu-id="56300-167">Затем укажите расположение CSV-файла и запустите получившиеся команды в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56300-167">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

<span data-ttu-id="56300-168">Ниже приведен пример для UPN:</span><span class="sxs-lookup"><span data-stu-id="56300-168">Here is an example for UPNs:</span></span>
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

<span data-ttu-id="56300-169">Затем укажите расположение CSV-файла и запустите получившиеся команды в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="56300-169">Next, fill in the location of the CSV file and run the resulting commands at the PowerShell command prompt.</span></span>
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a><span data-ttu-id="56300-170">См. также</span><span class="sxs-lookup"><span data-stu-id="56300-170">See also</span></span>

- [<span data-ttu-id="56300-171">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="56300-171">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [<span data-ttu-id="56300-172">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="56300-172">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="56300-173">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56300-173">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
