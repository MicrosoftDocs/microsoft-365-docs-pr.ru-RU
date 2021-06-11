---
title: Назначение Microsoft 365 для учетных записей пользователей с помощью PowerShell
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
description: В этой статье узнайте, как использовать PowerShell для назначения лицензии Microsoft 365 нелицензионных пользователей.
ms.openlocfilehash: 6d7e005aff018394810082de57c68ea289057f8e
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572625"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts-with-powershell"></a>Назначение Microsoft 365 для учетных записей пользователей с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Пользователи не могут использовать какие-либо Microsoft 365 до тех пор, пока их учетной записи не будет назначена лицензия из плана лицензирования. С помощью PowerShell можно быстро назначить лицензии нелицензируемой учетной записи. 

Учетным записям пользователей сначала должно быть назначено расположение. Указание расположения является обязательной частью создания новой учетной записи пользователя в [центре администрирования Microsoft 365.](../admin/add-users/add-users.md) 

Учетные записи, синхронизированные с локальной службой домена Active Directory, по умолчанию не имеют определенного расположения. Вы можете настроить расположение для этих учетных записей из:

- Центр администрирования Microsoft 365
 - [PowerShell](configure-user-account-properties-with-microsoft-365-powershell.md)
 - Портал [Azure](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal) **(Пользователи active Directory**> учетной записи >  >   **контактные** данные профилей  >    >  **страны или региона).**

>[!Note]
>[Узнайте, как назначать лицензии учетным](../admin/manage/assign-licenses-to-users.md) записям пользователей в центре Microsoft 365 администрирования. Список дополнительных ресурсов см. в списке [Управление пользователями и группами.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  

Далее перечислите планы лицензий для клиента с помощью этой команды.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Далее получите имя входной записи, к которой нужно добавить лицензию, также именуемую главным именем пользователя (UPN).

Далее убедитесь, что учетной записи пользователя назначено расположение использования.

```powershell
Get-AzureADUser -ObjectID <user sign-in name (UPN)> | Select DisplayName, UsageLocation
```

Если не назначено расположение использования, можно назначить одну с помощью этих команд:

```powershell
$userUPN="<user sign-in name (UPN)>"
$userLoc="<ISO 3166-1 alpha-2 country code>"
Set-AzureADUser -ObjectID $userUPN -UsageLocation $userLoc
```

Наконец, укажите имя и имя плана плана регистрации пользователя и запустите эти команды.

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

Обратите внимание, что мы начнем обесценить этот модуль, когда функциональность этого модуля будет доступна в новом Azure Active Directory [PowerShell для Graph](/powershell/azuread/v2/azureactivedirectory) модуля. Мы советуем пользователям, создав новые скрипты PowerShell, использовать новый модуль вместо этого модуля.

[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Запустите команду, чтобы просмотреть доступные планы лицензирования и количество доступных лицензий в каждом плане `Get-MsolAccountSku` в вашей организации. Количество доступных лицензий в каждом плане **— ActiveUnits**  -  **WarningUnits**  -  **ConsumedUnits.** Дополнительные сведения о планах лицензирования, лицензиях и службах см. в обзоре лицензий и служб [в PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

Чтобы найти нелицензивные учетные записи в организации, запустите эту команду.

```powershell
Get-MsolUser -All -UnlicensedUsersOnly
```

Лицензии можно назначать только учетным записям пользователей с свойством **UseLocation,** задаваемым допустимым кодом страны ISO 3166-1 alpha-2. Важно указать это значение, так как некоторые службы O365_W14_2nd недоступны в определенных странах. Некоторые Microsoft 365 службы недоступны в некоторых странах. Дополнительные сведения см. [в дополнительных сведениях об ограничениях лицензии.](https://go.microsoft.com/fwlink/p/?LinkId=691730)
    
Чтобы найти учетные записи, которые не имеют **значения UseLocation,** запустите эту команду.

```powershell
Get-MsolUser -All | where {$_.UsageLocation -eq $null}
```

Чтобы установить значение **UseLocation** для учетной записи, запустите эту команду.

```powershell
Set-MsolUser -UserPrincipalName "<Account>" -UsageLocation <CountryCode>
```

Пример.

```powershell
Set-MsolUser -UserPrincipalName "belindan@litwareinc.com" -UsageLocation US
```
    
Если использовать командлет **Get-MsolUser** без параметра **-All**, возвращаются только первые 500 учетных записей.

### <a name="assigning-licenses-to-user-accounts"></a>Назначение лицензий учетным записям пользователей
    
Чтобы назначить лицензию пользователю, используйте следующую команду в PowerShell.
  
```powershell
Set-MsolUserLicense -UserPrincipalName "<Account>" -AddLicenses "<AccountSkuId>"
```

В этом примере лицензия из плана лицензирования **litwareinc:ENTERPRISEPACK** (Office 365 корпоративный E3) назначается нелицензионному пользователю **\@ belindan litwareinc.com:**
  
```powershell
Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"
```

Чтобы назначить лицензию всем нелицензируемой пользователям, запустите эту команду.
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly [<FilterableAttributes>] | Set-MsolUserLicense -AddLicenses "<AccountSkuId>"
```
  
>[!Note]
>Невозможно назначить пользователю несколько лицензий из одного плана лицензирования. Если у вас нет достаточного количества доступных лицензий, они назначаются пользователям в порядке, в котором их возвращает командлет **Get-MsolUser**, пока не закончатся.
>

В этом примере всем нелицензионным пользователям присваиваются лицензии из плана лицензирования **litwareinc:ENTERPRISEPACK** (Office 365 корпоративный E3):
  
```powershell
Get-MsolUser -All -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```

В этом примере эти же лицензии назначаются нелицензированным пользователям в отделе продаж в США:
  
```powershell
Get-MsolUser -All -Department "Sales" -UsageLocation "US" -UnlicensedUsersOnly | Set-MsolUserLicense -AddLicenses "litwareinc:ENTERPRISEPACK"
```
  
## <a name="move-a-user-to-a-different-subscription-license-plan-with-the-azure-active-directory-powershell-for-graph-module"></a>Перемещение пользователя в другую подписку (лицензионный план) с Azure Active Directory PowerShell для Graph модуля

[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
Далее получите имя учетной записи пользователя, для которой нужны подписки на коммутаторы, также известные как основное имя пользователя (UPN).

Далее перечислите подписки (планы лицензий) для клиента с этой командой.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Далее укай список подписок, которые в настоящее время есть у учетной записи пользователя с этими командами.

```powershell
$userUPN="<user account UPN>"
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

Определите подписку, на которую пользователь в настоящее время имеет (подписку FROM) и подписку на которую перемещается (подписка TO).

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

Вы можете проверить изменение подписки на учетную запись пользователя с помощью этих команд.

```powershell
$licensePlanList = Get-AzureADSubscribedSku
$userList = Get-AzureADUser -ObjectID $userUPN | Select -ExpandProperty AssignedLicenses | Select SkuID 
$userList | ForEach { $sku=$_.SkuId ; $licensePlanList | ForEach { If ( $sku -eq $_.ObjectId.substring($_.ObjectId.length - 36, 36) ) { Write-Host $_.SkuPartNumber } } }
```

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
