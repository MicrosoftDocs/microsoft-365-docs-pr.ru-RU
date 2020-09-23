---
title: Удаление учетных записей пользователей Microsoft 365 с помощью PowerShell
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: В этой статье рассказывается, как использовать различные модули в PowerShell для удаления учетных записей пользователей Microsoft 365.
ms.openlocfilehash: 0c13b57c13fb3d01d648438a5d6973fea8b9db67
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235446"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Удаление учетных записей пользователей Microsoft 365 с помощью PowerShell

Для удаления и восстановления учетной записи пользователя можно использовать PowerShell для Microsoft 365.

>[!Note]
>[Узнайте, как восстановить учетную запись пользователя](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) с помощью центра администрирования Microsoft 365. Список дополнительных ресурсов приведен в разделе [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

После подключения используйте следующий синтаксис, чтобы удалить учетную запись пользователя:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

В этом примере удаляется учетная запись пользователя fabricec@litwareinc.com.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> Параметр **– ObjectID** в командлете **Remove – AzureADUser** принимает либо имя входа учетной записи, также называемое именем участника пользователя, либо идентификатор объекта учетной записи.
  
Чтобы отобразить имя учетной записи на основе имени пользователя, используйте следующие команды:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

В этом примере отображается имя учетной записи пользователя Caleb Sills.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Чтобы удалить учетную запись на основе отображаемого имени пользователя, используйте указанные ниже команды:
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Учетную запись пользователя, удаленную с помощью модуля Microsoft Azure Active Directory для Windows PowerShell, можно восстановить в течение 30 дней.

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Чтобы удалить учетную запись пользователя, используйте следующий синтаксис:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

В этом примере удаляется учетная запись пользователя BelindaN@litwareinc.com.
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Чтобы восстановить удаленную учетную запись пользователя в течение 30 дней, используйте следующий синтаксис:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

В этом примере восстанавливается удаленная учетная запись BelindaN@litwareinc.com.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

 **Примечания.**
  
- Чтобы просмотреть список удаленных пользователей, которых можно восстановить, выполните следующую команду:
    
  ```powershell
  Get-MsolUser -All -ReturnDeletedUsers
  ```

- Если исходное имя участника-пользователя используется другой учетной записью, замените _NewUserPrincipalName_ параметром _UserPrincipalName_, чтобы указать другое имя участника-пользователя при восстановлении учетной записи.


## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
