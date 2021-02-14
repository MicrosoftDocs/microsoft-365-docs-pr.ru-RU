---
title: Отключение доступа к службам Microsoft 365 при назначении пользовательских лицензий
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/24/2020
audience: Admin
ms.topic: article
ms.collection: Ent_O365
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
ms.assetid: bb003bdb-3c22-4141-ae3b-f0656fc23b9c
description: Узнайте, как назначать лицензии учетным записям пользователей и отключать определенные планы обслуживания одновременно с помощью PowerShell для Microsoft 365.
ms.openlocfilehash: b027c805638284a78d4e49f4c65518be02e60392
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693178"
---
# <a name="disable-access-to-microsoft-365-services-while-assigning-user-licenses"></a>Отключение доступа к службам Microsoft 365 при назначении пользовательских лицензий

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Подписки на Microsoft 365 приходят с планами обслуживания для отдельных служб. Администраторам Microsoft 365 часто требуется отключить определенные планы при назначении лицензий пользователям. С помощью инструкций в этой статье вы можете назначить лицензию Microsoft 365, отключив определенные планы обслуживания с помощью PowerShell для отдельной учетной записи пользователя или нескольких учетных записей пользователей.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  

Затем перечислите планы лицензий для клиента с помощью этой команды.

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

Затем получите имя для регистрации учетной записи, к которой вы хотите добавить лицензию, также известное как имя пользователя-пользователя(UPN).

Затем скомпилировать список служб, которые необходимо включить. Полный список планов лицензирования (также известных как названия продуктов), включенных в них планов обслуживания и соответствующих названий см. в соответствующем списке названий продуктов и идентификаторов планов обслуживания для [лицензирования.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)

В приведенном ниже блоке команд в заполните имя пользователя-пользователя учетной записи пользователя, номер части SKU и список планов обслуживания, чтобы включить и удалить пояснительный текст и \< and > символы. Затем выполните полученные команды в командной строке PowerShell.
  
```powershell
$userUPN="<user account UPN>"
$skuPart="<SKU part number>"
$serviceList=<double-quoted enclosed, comma-separated list of enabled services>
$user = Get-AzureADUser -ObjectID $userUPN
$skuID= (Get-AzureADSubscribedSku  | Where {$_.SkuPartNumber -eq $skuPart}).SkuID
$SkuFeaturesToEnable = @($serviceList)
$StandardLicense = Get-AzureADSubscribedSku | Where {$_.SkuId -eq $skuID}
$SkuFeaturesToDisable = $StandardLicense.ServicePlans | ForEach-Object { $_ | Where {$_.ServicePlanName -notin $SkuFeaturesToEnable }}
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = $StandardLicense.SkuId
$License.DisabledPlans = $SkuFeaturesToDisable.ServicePlanId
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $user.ObjectId -AssignedLicenses $LicensesToAssign
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

Затем запустите следующую команду, чтобы увидеть текущие подписки:
  
```powershell
Get-MsolAccountSku
```

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

Значение составляющих команды  `Get-MsolAccountSku`:
  
- **AccountSkuId** is a subscription for your organization in \<OrganizationName>:\<Subscription> format. Это \<OrganizationName> значение, которое вы предоставили при регистрации в Microsoft 365 и уникально для вашей организации. The \<Subscription> value is for a specific subscription. For example, for litwareinc:ENTERPRISEPACK, the organization name is litwareinc, and the subscription name is ENTERPRISEPACK (Office 365 Enterprise E3).
    
- **ActiveUnits** — количество лицензий, которые вы приобрели для подписки.
    
- **WarningUnits** — количество лицензий для не продленной подписки, срок действия которой истекает через 30 дней льготного периода.
    
- **ConsumedUnits** — количество лицензий, которые вы назначили пользователям для подписки.
    
Обратите внимание на AccountSkuId для подписки на Microsoft 365, которая содержит пользователей, которые вы хотите лицензировать. Убедитесь, что лицензий для назначения достаточно (отнимите **ConsumedUnits** от **ActiveUnits** ).
  
Затем запустите эту команду, чтобы увидеть сведения о планах обслуживания Microsoft 365, доступных во всех подписках:
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

Просмотрите результаты команды и определите, какие планы обслуживания нужно отключить при назначении лицензий пользователям.
  
Вот неполный список планов обслуживания и соответствующих им служб Microsoft 365.

В следующей таблице показаны планы обслуживания Microsoft 365 и их названия для наиболее распространенных служб. Ваш список планов обслуживания может отличаться. 
  
|**План обслуживания**|**Описание**|
|:-----|:-----|
| `SWAY` <br/> |Sway  <br/> |
| `TEAMS1` <br/> |Microsoft Teams  <br/> |
| `YAMMER_ENTERPRISE` <br/> |Yammer  <br/> |
| `RMS_S_ENTERPRISE` <br/> |Azure Rights Management (RMS)  <br/> |
| `OFFICESUBSCRIPTION` <br/> |Приложения Microsoft 365 для предприятий (ранее называлось *Office 365 профессиональныйplus)*  <br/> |
| `MCOSTANDARD` <br/> |Skype для бизнеса Online  <br/> |
| `SHAREPOINTWAC` <br/> |Office   <br/> |
| `SHAREPOINTENTERPRISE` <br/> |SharePoint Online  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |Exchange Online (план 2)  <br/> |
   
Полный список планов лицензирования (также известных как названия продуктов), включенных в них планов обслуживания и соответствующих названий см. в соответствующем списке названий продуктов и идентификаторов планов обслуживания для [лицензирования.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
   
Теперь, когда у вас есть AccountSkuId и планы обслуживания, которые нужно отключить, вы можете назначить лицензии для одного или нескольких пользователей.
  
### <a name="for-a-single-user"></a>Для одного пользователя

Для одного пользователя в заполните имя пользователя-пользователя учетной записи, AccountSkuId и список планов обслуживания, которые необходимо отключить, и удалите пояснительный текст и \< and > символы. Затем выполните полученные команды в командной строке PowerShell.
  
```powershell
$userUPN="<the user's account name in email format>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the service plans to disable> )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

Ниже приведен пример блока команд для учетной записи belindan@contoso.com. В этом случае указана лицензия contoso:ENTERPRISEPACK, а отключить нужно планы обслуживания RMS_S_ENTERPRISE, SWAY, INTUNE_O365 и YAMMER_ENTERPRISE.
  
```powershell
$userUPN="belindan@contoso.com"
$accountSkuId="contoso:ENTERPRISEPACK"
$planList=@( "RMS_S_ENTERPRISE","SWAY","INTUNE_O365","YAMMER_ENTERPRISE" )
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
Set-MsolUserLicense -UserPrincipalName $userUpn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
Sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $userUpn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
```

### <a name="for-multiple-users"></a>Для нескольких пользователей

Чтобы выполнить эту задачу администрирования для нескольких пользователей, создайте текстовый файл с разделителями-запятыми (CSV-файл), содержащий поля UserPrincipalName и UsageLocation. Пример:
  
```powershell
UserPrincipalName,UsageLocation
ClaudeL@contoso.onmicrosoft.com,FR
LynneB@contoso.onmicrosoft.com,US
ShawnM@contoso.onmicrosoft.com,US
```

После этого укажите расположение входного и выходного CSV-файлов, ИД SKU учетной записи и список планов обслуживания, которые нужно отключить. Затем выполните полученные команды в командной строке PowerShell.
  
```powershell
$inFileName="<path and file name of the input CSV file that contains the users, example: C:\admin\Users2License.CSV>"
$outFileName="<path and file name of the output CSV file that records the results, example: C:\admin\Users2License-Done.CSV>"
$accountSkuId="<the AccountSkuId from the Get-MsolAccountSku command>"
$planList=@( <comma-separated, double-quote enclosed list of the plans to disable> )
$users=Import-Csv $inFileName
$licenseOptions=New-MsolLicenseOptions -AccountSkuId $accountSkuId -DisabledPlans $planList
ForEach ($user in $users)
{
$user.Userprincipalname
$upn=$user.UserPrincipalName
Set-MsolUserLicense -UserPrincipalName $upn -AddLicenses $accountSkuId -ErrorAction SilentlyContinue
sleep -Seconds 5
Set-MsolUserLicense -UserPrincipalName $upn -LicenseOptions $licenseOptions -ErrorAction SilentlyContinue
$users | Get-MsolUser | Select UserPrincipalName, Islicensed,Usagelocation | Export-Csv $outFileName
}
```

Что делает этот блок команд PowerShell:
  
- Отображает имя участника-пользователя для каждого пользователя.
    
- Назначает настраиваемые лицензии для каждого пользователя.
    
- Создает CSV-файл со всеми обработанными пользователями и отображает состояние их лицензий.
    
## <a name="see-also"></a>См. также

[Отключение доступа к службам Microsoft 365 с помощью PowerShell](disable-access-to-services-with-microsoft-365-powershell.md)
  
[Отключение доступа к Sway с помощью PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md)
  
[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
