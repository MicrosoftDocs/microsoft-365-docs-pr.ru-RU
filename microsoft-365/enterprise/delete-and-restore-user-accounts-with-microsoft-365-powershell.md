---
title: Удаление Microsoft 365 учетных записей пользователей с помощью PowerShell
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
description: Узнайте, как использовать различные модули в PowerShell для удаления Microsoft 365 учетных записей пользователей.
ms.openlocfilehash: 32081d1ce0cbc7aac89b337cf8b5d08bc8e43dfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919144"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a>Удаление Microsoft 365 учетных записей пользователей с помощью PowerShell

Вы можете использовать PowerShell для Microsoft 365 для удаления и восстановления учетных записей пользователей.

>[!Note]
>Узнайте, как [восстановить учетную запись пользователя](../admin/add-users/restore-user.md) с помощью Microsoft 365 центра администрирования.
>
>Список дополнительных ресурсов см. в списке [Управление пользователями и группами.](../admin/add-users/index.yml)
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

После подключения используйте следующий синтаксис для удаления отдельной учетной записи пользователя:
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

В этом примере удаляется *fabricec \@ учетной записи пользователя litwareinc.com*.
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> Параметр *-ObjectID* в комлете **Remove-AzureADUser** принимает либо имя входной записи учетной записи, также известное как имя пользователя, так и объектный ИД учетной записи.
  
Чтобы отобразить имя учетной записи на основе имени пользователя, используйте следующие команды:
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

В этом примере отображается имя учетной записи пользователя *Caleb Sills*.
  
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

При удалении учетной записи пользователя через Microsoft Azure Active Directory модуль для Windows PowerShell, учетная запись не удаляется окончательно. Удаленную учетную запись пользователя можно восстановить в течение 30 дней.

[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Чтобы удалить учетную запись пользователя, используйте следующий синтаксис:
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*. Эти командлеты требуется запускать из Windows PowerShell.
>

В этом примере удаляется *учетная запись BelindaN@litwareinc.com*.
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

Чтобы восстановить удаленную учетную запись пользователя в течение 30 дней, используйте следующий синтаксис:
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

В этом примере восстанавливается удаленная учетная запись *BelindaN \@ litwareinc.com*.
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> Чтобы просмотреть список удаленных пользователей, которых можно восстановить, выполните следующую команду:
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> Если исходное имя участника-пользователя используется другой учетной записью, замените _NewUserPrincipalName_ параметром _UserPrincipalName_, чтобы указать другое имя участника-пользователя при восстановлении учетной записи.


## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)