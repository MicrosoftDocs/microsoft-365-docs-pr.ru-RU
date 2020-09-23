---
title: Назначение лицензий Microsoft 365 для учетных записей пользователей с помощью PowerShell
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
description: В этой статье рассказывается, как использовать PowerShell для назначения лицензии Microsoft 365 нелицензированным пользователям.
ms.openlocfilehash: f042f8109bf9ac9b634bc66509c60a5181fb1af6
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235622"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Назначение лицензий Microsoft 365 для учетных записей пользователей с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Пользователи не могут использовать службы Microsoft 365, пока их учетной записи не назначена лицензия из плана лицензирования. С помощью PowerShell можно быстро назначить лицензии нелицензированным учетным записям. 

>[!Note]
>Учетным записям пользователей должно быть назначено расположение. Это можно сделать в свойствах учетной записи пользователя в центре администрирования Microsoft 365 или PowerShell.
>

>[!Note]
>[Узнайте, как назначать лицензии учетным записям пользователей](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) с помощью центра администрирования Microsoft 365. Список дополнительных ресурсов приведен в разделе [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  

Затем перечислите план лицензирования для клиента с помощью этой команды.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Затем получите имя для входа учетной записи, к которой требуется добавить лицензию, также называемую именем участника-пользователя (UPN).

Затем убедитесь, что для учетной записи пользователя назначено место использования.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Если местоположение использования не назначено, вы можете назначить его с помощью следующих команд:

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Наконец, укажите имя пользователя для входа и имя плана лицензирования и выполните указанные ниже команды.

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

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Выполните `Get-MsolAccountSku` команду, чтобы просмотреть доступные планы лицензирования и число доступных лицензий в каждом плане в Организации. Число доступных лицензий в каждом плане — **ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits**. Для получения дополнительных сведений о планах лицензирования, лицензиях и службах ознакомьтесь со статьей [Просмотр лицензий и служб с помощью PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

Чтобы найти нелицензированные учетные записи в Организации, выполните указанную ниже команду.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Вы можете назначать лицензии только тем пользователям, у которых для свойства **UsageLocation** задан действительный код страны ISO 3166-1 Alpha-2. Важно указать это значение, так как некоторые службы O365_W14_2nd недоступны в определенных странах. Некоторые службы Microsoft 365 недоступны в некоторых странах. Более подробную информацию можно узнать в статье [ограничения лицензирования](https://go.microsoft.com/fwlink/p/?LinkId=691730).
    
Чтобы найти учетные записи, для которых не задано значение **UsageLocation** , выполните указанную ниже команду.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Чтобы задать значение **UsageLocation** для учетной записи, выполните указанную ниже команду.

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

В этом примере назначается лицензия из плана лицензирования **litwareinc: ENTERPRISEPACK** (Office 365 корпоративный E3) для нелицензированного пользователя **белиндан \@ litwareinc.com**:
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Чтобы назначить лицензию для всех нелицензированных пользователей, выполните указанную ниже команду.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>Невозможно назначить пользователю несколько лицензий из одного плана лицензирования. Если у вас нет достаточного количества доступных лицензий, они назначаются пользователям в порядке, в котором их возвращает командлет **Get-MsolUser**, пока не закончатся.
>

В этом примере назначаются лицензии из плана лицензирования **litwareinc: ENTERPRISEPACK** (Office 365 корпоративный E3) для всех нелицензированных пользователей:
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

В этом примере для нелицензированных пользователей назначаются те же лицензии в отделе продаж в США.
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Перемещение пользователя в другую подписку (план лицензирования) с помощью модуля Azure Active Directory PowerShell для Graph

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Затем получите имя для входа учетной записи пользователя, для которой требуется сменить подписку, также называемую именем участника-пользователя (UPN).

Затем перечислите подписки (планы лицензирования) для вашего клиента с помощью этой команды.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Затем перечислите подписку на текущую учетную запись пользователя с помощью этих команд.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Определите подписку пользователя (из подписки) и подписку, на которую пользователь перемещается (в подписку).

Наконец, укажите имена подписок "Кому" и "от" (номера деталей SKU) и выполните приведенные ниже команды.

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

Вы можете проверить изменение подписки для учетной записи пользователя с помощью этих команд.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
