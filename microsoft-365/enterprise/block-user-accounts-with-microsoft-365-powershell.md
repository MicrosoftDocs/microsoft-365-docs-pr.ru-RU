---
title: Блокировка Microsoft 365 учетных записей пользователей с помощью PowerShell
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
description: Использование PowerShell для блокировки и разблокирования доступа к Microsoft 365 учетным записям.
ms.openlocfilehash: 90d712cdb6eb34d0588fc262e3a02673accfbd9e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287225"
---
# <a name="block-microsoft-365-user-accounts-with-powershell"></a>Блокировка Microsoft 365 учетных записей пользователей с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Если вы блокируете доступ к Microsoft 365 учетной записи, вы не позволяете кому-либо использовать учетную запись для регистрации и доступа к службам и данным в Microsoft 365 организации. С помощью PowerShell можно заблокировать доступ к отдельным или нескольким учетным записям пользователей.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="block-access-to-individual-user-accounts"></a>Блокировка доступа к отдельным учетным записям пользователей

Чтобы заблокировать индивидуальную учетную запись пользователя, используйте следующий синтаксис:

```powershell
Set-AzureADUser -ObjectID <sign-in name of the user account> -AccountEnabled $false
```

> [!NOTE]
> Параметр *-ObjectID* в **комлете Set-AzureAD** принимает либо имя регистрации учетной записи, также известное как основное имя пользователя, либо код объекта учетной записи.

В этом примере блокируется доступ к учетной *записи fabricec@litwareinc.com.*

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $false
```

Чтобы разблокировать эту учетную запись пользователя, выполните следующую команду:

```powershell
Set-AzureADUser -ObjectID fabricec@litwareinc.com -AccountEnabled $true
```

Чтобы отобразить учетную запись пользователя UPN на основе имени отображения пользователя, используйте следующие команды:

```powershell
$userName="<display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName

```

В этом примере отображается учетная запись пользователя UPN для пользователя  *Caleb Sills*.

```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Чтобы заблокировать учетную запись на основе имени отображения пользователя, используйте следующие команды:

```powershell
$userName="<display name>"
Set-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName -AccountEnabled $false

```

Чтобы проверить заблокированный статус учетной записи пользователя, используйте следующую команду:

```powershell
Get-AzureADUser -UserPrincipalName <UPN of user account> | Select DisplayName,AccountEnabled
```

### <a name="block-multiple-user-accounts"></a>Блокировка нескольких учетных записей пользователей

Чтобы заблокировать доступ к нескольким учетным записям пользователей, создайте текстовый файл, содержащий одно имя входной записи в каждой строке:

  ```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
  ```

В следующих командах в примере текстовый файл *C:\My Documents\Accounts.txt.* Замените это имя файла путем и именем файла в текстовом файле.

Чтобы заблокировать доступ к учетным записям, перечисленным в текстовом файле, выполните следующую команду:

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $false}
```

Чтобы разблокировать учетные записи, перечисленные в текстовом файле, запустите следующую команду:

```powershell
Get-Content "C:\My Documents\Accounts.txt" | ForEach {Set-AzureADUser -ObjectID $_ -AccountEnabled $true}
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="block-individual-user-accounts"></a>Блокировка отдельных учетных записей пользователей

Чтобы заблокировать доступ к отдельной учетной записи пользователя, используйте следующий синтаксис:

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $true
```

>[!Note]
>PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для Windows PowerShell и командлетов с *Msol* в их имени. Вы должны запустить эти комлеты из Windows PowerShell.

В этом примере блокируется доступ к *fabricec \@ учетной записи пользователя litwareinc.com.*

```powershell
Set-MsolUser -UserPrincipalName fabricec@litwareinc.com -BlockCredential $true
```

Чтобы разблокировать учетную запись пользователя, выполните следующую команду:

```powershell
Set-MsolUser -UserPrincipalName <sign-in name of user account>  -BlockCredential $false
```

Чтобы проверить заблокированный статус учетной записи пользователя, запустите следующую команду:

```powershell
Get-MsolUser -UserPrincipalName <sign-in name of user account> | Select DisplayName,BlockCredential
```

### <a name="block-access-for-multiple-user-accounts"></a>Блокировка доступа для нескольких учетных записей пользователей

Сначала создайте текстовый файл, содержащий одну учетную запись в каждой строке, например:

```powershell
akol@contoso.com
tjohnston@contoso.com
kakers@contoso.com
```

В следующих командах в примере текстовый файл *C:\My Documents\Accounts.txt.* Замените это имя файла путем и именем файла в текстовом файле.

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
