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
# <a name="assign-admin-roles-to-microsoft-365-user-accounts-with-powershell"></a>Назначение ролей администратора учетным записям пользователей Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Вы можете легко назначать роли учетным записям пользователей с помощью PowerShell для Microsoft 365.

>[!Note]
>Узнайте, как  [назначать роли администратора](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) учетным записям пользователей в Центре администрирования Microsoft 365.
>
>Список дополнительных ресурсов см. в [подсети "Управление пользователями и группами".](https://docs.microsoft.com/microsoft-365/admin/add-users/)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала используйте учетную запись глобального администратора [для подключения к вашему клиенту Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Затем определите имя для входов учетной записи пользователя, которую нужно добавить в роль (пример: fredsm \@ contoso.com). Это также называется именем основного пользователя (UPN).

После этого определите имя роли. См. [разрешения роли администратора в Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)

>[!Note]
>Обратите внимание на примечания в этой статье. Некоторые имена ролей отличаются для Azure Active Directory (Azure AD) PowerShell. Например, роль администратора *SharePoint* в Центре администрирования Microsoft 365 — администратор *Службы SharePoint в* Azure AD PowerShell.
>

После этого заполните имена для входов и ролей и запустите следующие команды:
  
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

Вот пример завершенного набора команд, который назначает роль администратора SharePoint Service учетной записи пользователя *belindan \@ contoso.com.*
  
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

Чтобы отобразить список имен пользователей для определенной роли администратора, используйте эти команды.

```powershell
$roleName="<role name>"
Get-AzureADDirectoryRole | Where { $_.DisplayName -eq $roleName } | Get-AzureADDirectoryRoleMember | Ft DisplayName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала используйте учетную запись глобального администратора [для подключения к вашему клиенту Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
### <a name="for-a-single-role-change"></a>Изменение одной роли

Чаще всего указать учетную запись пользователя можно с помощью отображаемого имени или имени электронной почты, которое также называется именем для регистрации или именем пользователя-пользователя .

#### <a name="display-names-of-user-accounts"></a>Отображение имен учетных записей пользователей

Если вы привыкли работать с отображаемой информацией об учетных записях пользователей, определите следующие сведения:
  
- Учетная запись пользователя, которую необходимо настроить
    
    Чтобы указать учетную запись пользователя, необходимо определить ее отображаемое имя. Чтобы получить полный список учетных записей, используйте команду:
    
  ```powershell
  Get-MsolUser -All | Sort DisplayName | Select DisplayName | More
  ```

    Эта команда выводит учетные записи пользователей, отсортированное по отображаемому имени, по одному экрану за раз. Вы можете отфильтровать список, используя командлет **Where**. См. следующий пример.

   >[!Note]
   >В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*. Эти командлеты требуется запускать из Windows PowerShell.
   >
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort DisplayName | Select DisplayName | More
  ```

    Эта команда выводит только учетные записи пользователей, отображаемое имя которых начинается со слова "John".
    
- Роль, которую вы хотите назначить
    
    Чтобы отобразить список доступных ролей администратора, которые можно назначить учетным записям пользователей, используйте команду:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

После определения отображаемого имени учетной записи и роли используйте эти команды, чтобы назначить роль учетной записи:
  
```powershell
$dispName="<The Display Name of the account>"
$roleName="<The admin role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

Paste the commands into Notepad. Для *переменных $dispName* *и $roleName* замените текст описания их значениями. Удалите \< and > символы, но сохраняем кавычка. В paste the modified lines into the Microsoft Azure Active Directory Module for Windows PowerShell to run them. Кроме того, можно использовать интегрированную среду сценариев Windows PowerShell.
  
Вот пример завершенного набора команд:
  
```powershell
$dispName="Scott Wallace"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress (Get-MsolUser -All | Where DisplayName -eq $dispName).UserPrincipalName -RoleName $roleName
```

#### <a name="sign-in-names-of-user-accounts"></a>Имена учетных записей пользователей для входов

Если вы привыкли работать с именами или именами пользователей для входов в учетные записи пользователей, определите следующие сведения:
  
- UpN учетной записи пользователя
    
    Если вы не знаете upN, используйте команду:
    
  ```powershell
  Get-MsolUser -All | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Эта команда перечисляет имя upn учетных записей пользователей, отсортировать их по одному экрану за раз. Для фильтрации **списка** можно использовать этот список с помощью cmdlet Where. Пример:
    
  ```powershell
  Get-MsolUser -All | Where DisplayName -like "John*" | Sort UserPrincipalName | Select UserPrincipalName | More
  ```

    Эта команда выводит только учетные записи пользователей, отображаемое имя которых начинается со слова "John".
    
- Роль, которую вы хотите назначить
    
    Чтобы отобразить список доступных ролей, используйте эту команду:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

После присвоения имени имени пользователя учетной записи и имени роли используйте эти команды, чтобы назначить роль учетной записи:
  
```powershell
$upnName="<The UPN of the account>"
$roleName="<The role name you want to assign to the account>"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

Скопируйте команды в Блокнот. Для **$upnName** и **$roleName** переменных. Замените текст описания их значениями. Удалите \< and > символы, но сохраняем кавычка. В paste the modified lines into Microsoft Azure Active Directory Module for Windows PowerShell window to run them. Кроме того, можно использовать Windows PowerShell ISE.
  
Вот пример завершенного набора команд:
  
```powershell
$upnName="scottw@contoso.com"
$roleName="SharePoint Service Administrator"
Add-MsolRoleMember -RoleMemberEmailAddress $upnName -RoleName $roleName
```

### <a name="multiple-role-changes"></a>Несколько изменений ролей

Для нескольких изменений ролей определите следующие сведения:
  
- Какие учетные записи пользователей необходимо настроить. Вы можете использовать методы, показанные в предыдущем разделе, для сбора набора отображаемого имени или имен upNs.
    
- Какие роли вы хотите назначить каждой учетной записи пользователя. Чтобы отобразить список доступных ролей, используйте эту команду:
    
  ```powershell
  Get-MsolRole | Sort Name | Select Name,Description
  ```

Затем создайте текстовый файл с разделиными запятой (CSV-файл), который имеет отображаемого имени или имени имени upn и поля имени роли. Это легко сделать в Microsoft Excel.

Вот пример отображаемой имена:
  
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

Вот пример для upNs:
  
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
