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
description: Как с помощью PowerShell заблокировать и разблокировать доступ к учетным записям Microsoft 365.
ms.openlocfilehash: c1a79d925965fafd796033182098e68e26a81473
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754684"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Блокировка учетных записей пользователей Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Если вы блокируете доступ к учетной записи Microsoft 365, вы блокируете использование этой учетной записи для доступа к службам и данным в организации Microsoft 365. С помощью PowerShell можно заблокировать доступ к отдельным или нескольким учетным записям пользователей.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
 
### <a name="block-access-to-individual-user-accounts"></a>Блокировка доступа к отдельным учетным записям пользователей

Используйте следующий синтаксис для блокировки отдельной учетной записи пользователя:
  
```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> Параметр *-ObjectID* в cmdlet **Set-AzureAD** принимает имя для регистрации учетной записи, также известное как имя пользователя-пользователя, или ИД объекта учетной записи.
  
В этом примере блокируется доступ к учетной записи *fabricec@litwareinc.com.*
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

Чтобы разблокировать эту учетную запись пользователя, выполните следующую команду:
  
```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

Чтобы отобразить имя upN учетной записи пользователя на основе отображаемой имени пользователя, используйте следующие команды:
  
```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

В этом примере отображается имя upN учетной записи пользователя *Caleb Sills.*
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Чтобы заблокировать учетную запись на основе отображаемой имени пользователя, используйте следующие команды:
  
```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

Чтобы проверить состояние блокировки учетной записи пользователя, используйте следующую команду:
  
```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>Блокировка нескольких учетных записей пользователей

Чтобы заблокировать доступ для нескольких учетных записей пользователей, создайте текстовый файл, содержащий одно имя для входов в каждую строку, например:
    
  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

В следующих командах пример текстового файла *C:\My Documents\Accounts.txt.* Замените это имя на путь и имя файла в текстовом файле.
  
Чтобы заблокировать доступ к учетным записям, перечисленным в текстовом файле, выполните следующую команду:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $false }
```

Чтобы разблокировать учетные записи, указанные в текстовом файле, запустите следующую команду:
    
```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-AzureADUSer -ObjectID $_ -AccountEnabled $true }
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
    
### <a name="block-individual-user-accounts"></a>Блокировка отдельных учетных записей пользователей

Используйте следующий синтаксис, чтобы заблокировать доступ для отдельной учетной записи пользователя:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты *с Msol* в их имени. Эти cmdlets необходимо запускать из Windows PowerShell.

В этом примере блокируется доступ к учетной записи *fabricec \@ litwareinc.com.*
  
```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

Чтобы разблокировать учетную запись пользователя, выполните следующую команду:
  
```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

Чтобы проверить состояние блокировки учетной записи пользователя, запустите следующую команду:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>Блокировка доступа для нескольких учетных записей пользователей

Сначала создайте текстовый файл, содержащий по одной учетной записи в каждой строке, как по этому:
    
```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

В следующих командах пример текстового файла *C:\My Documents\Accounts.txt.* Замените это имя на путь и имя файла в текстовом файле.
    
Чтобы заблокировать доступ к учетным записям, указанным в текстовом файле, запустите следующую команду:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $true }
  ```
Чтобы разблокировать учетные записи, перечисленные в текстовом файле, выполните следующую команду:
    
  ```powershell
  Get-Content "C:\My Documents\Accounts.txt" | ForEach { Set-MsolUser -UserPrincipalName $_ -BlockCredential $false }
  ```

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
