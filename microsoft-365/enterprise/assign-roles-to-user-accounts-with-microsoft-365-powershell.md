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
ms.openlocfilehash: 7e3292ab26924384beb8d0c7450b7665dccd48fa
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754202"
---
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>Назначение ролей администратора учетным записям пользователей Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Вы можете легко назначать роли учетным записям пользователей с помощью PowerShell для Microsoft 365.

>[!Note]
>Узнайте, как  [назначать роли администратора](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) учетным записям пользователей с помощью центра администрирования Microsoft 365.
>
>Список дополнительных ресурсов приведен в разделе [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала используйте учетную запись глобального администратора, чтобы [подключиться к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Затем определите имя для входа учетной записи пользователя, которую вы хотите добавить к роли (например: фредсм \@ contoso.com). Это также называется именем участника-пользователя (UPN).

После этого определите имя роли. Просмотр [разрешений роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).

>[!Note]
>Обратите внимание на примечания в этой статье. Некоторые имена ролей для PowerShell Azure Active Directory (Azure AD) отличаются. Например, роль *администратора SharePoint* в центре администрирования Microsoft 365 является *администратором службы SharePoint* в Azure AD PowerShell.
>

Затем заполните имена входа и ролей и выполните следующие команды:
  
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

Ниже приведен пример завершенного набора команд, который назначает роль администратора службы SharePoint учетной записи *белиндан \@ contoso.com* :
  
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

Чтобы отобразить список имен пользователей для определенной роли администратора, используйте следующие команды.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала используйте учетную запись глобального администратора, чтобы [подключиться к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
### <a name="for-a-single-role-change"></a>Изменение одной роли

Наиболее распространенные способы указания учетной записи пользователя с помощью отображаемого имени или его имени электронной почты, которое также называется именем для входа или именем участника-пользователя (UPN).

#### <a name="display-names-of-user-accounts"></a>Отображение имен учетных записей пользователей

Если вы используете для работы с отображаемыми именами учетных записей пользователей, определите следующие сведения:
  
- Учетная запись пользователя, которую требуется настроить
    
    Чтобы указать учетную запись пользователя, необходимо определить ее отображаемое имя. Чтобы получить полный список учетных записей, используйте следующую команду:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Эта команда выводит учетные записи пользователей, отсортированное по отображаемому имени, по одному экрану за раз. Вы можете отфильтровать список, используя командлет **Where**. Ниже приведен пример.

   >[!Note]
   >Среда PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для модуля Windows PowerShell и командлеты с *MSOL* в имени. Выполните эти командлеты в Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Эта команда выводит только учетные записи пользователей, отображаемое имя которых начинается со слова "John".
    
- Роль, которую необходимо назначить
    
    Чтобы отобразить список доступных ролей администратора, которые можно назначить учетным записям пользователей, используйте следующую команду:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

После определения отображаемого имени учетной записи и имени роли выполните следующие команды, чтобы назначить роль учетной записи:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Вставьте команды в Блокнот. Для переменных *$dispName* и *$roleName* замените текст описания их значениями. Удалите \< and > символы, не заключая в кавычки. Вставьте измененные строки в окно Microsoft Azure Active Directory Module для Windows PowerShell, чтобы запустить их. Кроме того, можно использовать интегрированную среду сценариев Windows PowerShell.
  
Ниже приведен пример завершенного набора команд:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Имена для входа учетных записей пользователей

Если вы используете учетные записи или имена участников для учетных записей пользователей, определите следующие сведения:
  
- Имя участника-пользователя для учетной записи пользователя
    
    Если вы не знаете имя участника-пользователя, выполните следующую команду:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Эта команда выводит имя участника-пользователя для учетных записей пользователей, отсортированных по имени участника-пользователя, по одному экрану за раз. С помощью командлета **WHERE** можно отфильтровать список. Пример:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Эта команда выводит только учетные записи пользователей, отображаемое имя которых начинается со слова "John".
    
- Роль, которую необходимо назначить
    
    Чтобы отобразить список доступных ролей, используйте эту команду:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

После создания имени участника-пользователя для учетной записи и имени роли выполните следующие команды, чтобы назначить роль учетной записи:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Скопируйте команды в Блокнот. Для переменных **$upnName** и **$roleName** . Замените текст описания их значениями. Удалите \< and > символы, не заключая в кавычки. Вставьте измененные строки в окно Microsoft Azure Active Directory модуль для Windows PowerShell, чтобы запустить его. Кроме того, вы можете использовать среду Windows PowerShell ISE.
  
Ниже приведен пример завершенного набора команд:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Изменение нескольких ролей

Для изменения нескольких ролей определите следующие сведения:
  
- Какие учетные записи пользователей вы хотите настроить. Методы, описанные в предыдущем разделе, можно использовать для сбора набора отображаемых имен или UPN.
    
- Какие роли вы хотите назначить каждой учетной записи пользователя. Чтобы отобразить список доступных ролей, используйте эту команду:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Затем создайте текстовый файл с разделителями-запятыми (CSV), в котором отображаются поля отображаемого имени или имени участника-пользователя и имени роли. Это можно сделать с легкостью в Microsoft Excel.

Ниже приведен пример для отображаемых имен:
  
```powershell
DisplayName,RoleName
"Belinda Newman","Billing Administrator"
"Scott Wallace","SharePoint Service Administrator"
```

Затем укажите расположение CSV-файла и запустите получившиеся команды в командной строке PowerShell.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach {Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser | Where DisplayName -eq $_.DisplayName).UserPrincipalName -RoleName $_.RoleName }

```

Ниже приведен пример для UPN:
  
```powershell
UserPrincipalName,RoleName
"belindan@contoso.com","Billing Administrator"
"scottw@contoso.com","SharePoint Service Administrator"
```

Затем укажите расположение CSV-файла и запустите получившиеся команды в командной строке PowerShell.
  
```powershell
$fileName="<path and file name of the input CSV file that has the role changes, example: C:\admin\RoleUpdates.CSV>"
$roleChanges=Import-Csv $fileName | ForEach { Add-MsolRoleMember -RoleMemberEmailAddress $_.UserPrincipalName -RoleName $_.RoleName }

```

## <a name="see-also"></a>См. также

- [Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
- [Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
