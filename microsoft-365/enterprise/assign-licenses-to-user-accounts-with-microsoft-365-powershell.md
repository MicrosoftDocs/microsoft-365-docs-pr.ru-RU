---
title: Назначение лицензий Microsoft 365 учетным записям пользователей с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- LIL_Placement
- PowerShell
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: ba235f4f-e640-4360-81ea-04507a3a70be
search.appverid:
- MET150
description: В этой статье вы узнаете, как с помощью PowerShell назначить лицензию Microsoft 365 пользователям без лицензий.
ms.openlocfilehash: 8c3165b99477afa14e6d2b0da927b5f64c416ef1
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580944"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Назначение лицензий Microsoft 365 учетным записям пользователей с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Пользователи не смогут использовать какие-либо службы Microsoft 365, пока их учетной записи не будет назначена лицензия из плана лицензирования. С помощью PowerShell можно быстро назначать лицензии учетным записям без лицензий. 

Учетным записям пользователей сначала необходимо на назначенное расположение. Указание расположения является обязательной частью создания новой учетной записи пользователя в Центре администрирования [Microsoft 365.](../admin/add-users/add-users.md) 

Для учетных записей, синхронизированных из локальной доменной службы Active Directory, по умолчанию не указано расположение. Расположение для этих учетных записей можно настроить с помощью:

- Центр администрирования Microsoft 365
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - Портал [Azure](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) **(пользователи Active Directory**> учетной записи >  >   **контактной** информации профиля  >    >  **страны или региона).**

>[!Note]
>[Узнайте, как назначать лицензии учетным записям](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) пользователей в Центре администрирования Microsoft 365. Список дополнительных ресурсов см. в [подсети "Управление пользователями и группами".](https://docs.microsoft.com/microsoft-365/admin/add-users/)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  

Затем перечислите планы лицензий для клиента с помощью этой команды.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Затем получите имя для регистрации учетной записи, к которой вы хотите добавить лицензию, также известное как имя пользователя-пользователя(UPN).

Затем убедитесь, что учетной записи пользователя назначено расположение использования.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Если место использования не назначено, его можно назначить с помощью указанных команд.

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Наконец, укажите имя для входов пользователя и имя плана лицензирования и запустите эти команды.

```powershell
$userUPN="<user sign-in name (UPN)>"
$planName="<license plan name from the list of license plans>"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $planName -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Запустите команду, чтобы просмотреть доступные планы лицензирования и количество доступных лицензий в каждом `Get-MsolAccountSku` плане в организации. Количество доступных лицензий в каждом плане — **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits.** Дополнительные сведения о планах лицензирования, лицензиях и службах см. в сведениях о лицензировании и службах [с помощью PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

Чтобы найти учетные записи без лицензий в организации, запустите эту команду.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Лицензии можно назначать только учетным записям пользователей, для свойства **UsageLocation** задаваемого допустимого кода страны ПО ISO 3166-1 alpha-2. Важно указать это значение, так как некоторые службы O365_W14_2nd недоступны в определенных странах. Некоторые службы Microsoft 365 недоступны в некоторых странах. Дополнительные сведения см. [в сведениях об ограничениях лицензий.](https://go.microsoft.com/fwlink/p/?LinkId=691730)
    
Чтобы найти учетные записи без значения **UsageLocation,** запустите эту команду.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Чтобы установить значение **UsageLocation** для учетной записи, запустите эту команду.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Пример:

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Если использовать командлет **Get-MsolUser** без параметра **-All**, возвращаются только первые 500 учетных записей.

### <a name="assigning-licenses-to-user-accounts"></a>Назначение лицензий учетным записям пользователей
    
Чтобы назначить лицензию пользователю, используйте следующую команду в PowerShell.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

В этом примере пользователю без лицензии назначается лицензия из плана лицензирования **litwareinc:ENTERPRISEPACK** (Office 365 корпоративный **\@ E3)** для пользователя без лицензии, litwareinc.com:
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Чтобы назначить лицензию всем пользователям без лицензий, запустите эту команду.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>Невозможно назначить пользователю несколько лицензий из одного плана лицензирования. Если у вас нет достаточного количества доступных лицензий, они назначаются пользователям в порядке, в котором их возвращает командлет **Get-MsolUser**, пока не закончатся.
>

В этом примере всем пользователям без лицензий назначаются лицензии из плана лицензирования **litwareinc:ENTERPRISEPACK** (Office 365 корпоративный E3):
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

В этом примере эти же лицензии назначаются пользователям без лицензий в отделе продаж в США:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Перемещение пользователя на другую подписку (план лицензирования) с помощью модуля Azure Active Directory PowerShell для Graph

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Затем получите имя для регистрации учетной записи пользователя, для которой нужно переключить подписки, также известное как имя пользователя-пользователя (UPN).

Затем перечислите подписки (планы лицензирования) для клиента с помощью этой команды.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Затем перечислим подписки, которые в данный момент есть у учетной записи пользователя с этими командами.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Определите подписку, которая у пользователя в данный момент есть (подписка FROM), и подписку, в которую перемещается пользователь (подписка НА).

Наконец, укажите имена подписок TO и FROM (номера части SKU) и запустите эти команды.

```powershell
$subscriptionFrom="<SKU part number of the current subscription>"
$subscriptionTo="<SKU part number of the new subscription>"
# Unassign
$license = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
$licenses.AddLicenses = $license
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
$licenses.AddLicenses = @()
$licenses.RemoveLicenses =  (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionFrom -EQ).SkuID
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
# Assign
$license.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $subscriptionTo -EQ).SkuID
$licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$licenses.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $licenses
```

С помощью этих команд можно проверить изменение подписки для учетной записи пользователя.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
