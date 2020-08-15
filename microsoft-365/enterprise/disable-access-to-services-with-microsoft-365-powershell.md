---
title: Отключение доступа к службам Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/27/2020
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
- LIL_Placement
- seo-marvel-apr2020
ms.assetid: 264f4f0d-e2cd-44da-a9d9-23bef250a720
description: В этой статье рассказывается, как использовать PowerShell для отключения доступа к службам Microsoft 365 для пользователей.
ms.openlocfilehash: 292bda3b380b9ce3947b2427288da4f16198bb51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693180"
---
# <a name="disable-access-to-microsoft-365-services-with-powershell"></a>Отключение доступа к службам Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Когда учетной записи Microsoft 365 назначена лицензия из плана лицензирования, службы Microsoft 365 предоставляются пользователю из этой лицензии. Тем не менее, вы можете управлять службами Microsoft 365, к которым у пользователя есть доступ. Например, несмотря на то, что лицензия разрешает доступ к службе SharePoint Online, вы можете отключить доступ к ней. С помощью PowerShell можно отключить доступ к любому числу служб для определенного плана лицензирования:

- отдельная учетная запись;
- группа учетных записей;
- все учетные записи в организации.

>[!Note]
>Существует зависимость от службы Microsoft 365, которая может препятствовать отключению указанной службы, когда от нее зависят другие службы.
>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

Затем используйте эту команду для просмотра доступных планов лицензирования, известных также как Аккаунтскуидс:

```powershell
Get-MsolAccountSku | Select AccountSkuId | Sort AccountSkuId
```

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

Для получения дополнительных сведений ознакомьтесь [со статьей Просмотр лицензий и служб с помощью PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).
    
Чтобы просмотреть результаты процедуры, описанные в этом разделе, в статье [Просмотр сведений о лицензиях и службах для учетной записи с помощью PowerShell](view-account-license-and-service-details-with-microsoft-365-powershell.md).
    
Кроме того, вы можете воспользоваться сценарием PowerShell, который автоматизирует выполнение процедур, описанных в этой статье. В частности, скрипт позволяет просматривать и отключать службы в организации Microsoft 365, в том числе Sway. Дополнительные сведения см. [в статье Отключение доступа к Sway с помощью PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).
    
    
### <a name="disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan"></a>Отключение определенных служб Microsoft 365 для определенных пользователей по определенному плану лицензирования
  
Чтобы отключить определенный набор служб Microsoft 365 для пользователей по определенному плану лицензирования, выполните указанные ниже действия.
  
#### <a name="step-1-identify-the-undesirable-services-in-the-licensing-plan-by-using-the-following-syntax"></a>Шаг 1: определение нежелательных служб в плане лицензирования с помощью следующего синтаксиса:
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId <AccountSkuId> -DisabledPlans "<UndesirableService1>", "<UndesirableService2>"...
```

В следующем примере создается объект **LicenseOptions** , который отключает службы Office и SharePoint Online в плане лицензирования под названием `litwareinc:ENTERPRISEPACK` (Office 365 корпоративный E3).
    
```powershell
$LO = New-MsolLicenseOptions -AccountSkuId "litwareinc:ENTERPRISEPACK" -DisabledPlans "SHAREPOINTWAC", "SHAREPOINTENTERPRISE"
```

#### <a name="step-2-use-the-licenseoptions-object-from-step-1-on-one-or-more-users"></a>Шаг 2: используйте объект **LicenseOptions** из шага 1 для одного или нескольких пользователей.
    
Чтобы создать учетную запись, для которой отключены службы, используйте указанную ниже команду.
    
```powershell
New-MsolUser -UserPrincipalName <Account> -DisplayName <DisplayName> -FirstName <FirstName> -LastName <LastName> -LicenseAssignment <AccountSkuId> -LicenseOptions $LO -UsageLocation <CountryCode>
```

В следующем примере создается новая учетная запись для (Allie bellew), которая назначает лицензию и отключает службы, описанные в шаге 1.
    
```powershell
New-MsolUser -UserPrincipalName allieb@litwareinc.com -DisplayName "Allie Bellew" -FirstName Allie -LastName Bellew -LicenseAssignment litwareinc:ENTERPRISEPACK -LicenseOptions $LO -UsageLocation US
```

Для получения дополнительных сведений о создании учетных записей пользователей в PowerShell для Microsoft 365, ознакомьтесь со статьей [Создание учетных записей пользователей с помощью PowerShell](create-user-accounts-with-microsoft-365-powershell.md).
    
Чтобы отключить службы для существующего лицензированного пользователя, выполните указанную ниже команду.
    
```powershell
Set-MsolUserLicense -UserPrincipalName <Account> -LicenseOptions $LO
```

В этом примере показано, как отключить службы для пользователя BelindaN@litwareinc.com.
    
```powershell
Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -LicenseOptions $LO
```

Чтобы отключить службы, описанные в шаге 1, для всех существующих лицензированных пользователей, укажите имя плана Microsoft 365 на экране командлета **Get-MsolAccountSku** (например, **litwareinc: ENTERPRISEPACK**), а затем выполните следующие команды:
    
```powershell
$acctSKU="<AccountSkuId>"
$AllLicensed = Get-MsolUser -All | Where {$_.isLicensed -eq $true -and $_.licenses.AccountSku.SkuPartNumber -contains ($acctSKU).Substring($acctSKU.IndexOf(":")+1, $acctSKU.Length-$acctSKU.IndexOf(":")-1)}
$AllLicensed | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

 Если вы используете командлет **Get – MsolUser** без параметра _ALL_ , возвращаются только первые 500 учетных записей пользователей.

Чтобы отключить службы для группы существующих пользователей, воспользуйтесь одним из указанных ниже методов для идентификации пользователей.
    
**Способ 1. Фильтрация учетных записей на основе существующего атрибута учетной записи** 

Для этого используйте следующий синтаксис:
    
```powershell
$x = Get-MsolUser -All <FilterableAttributes>
$x | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

В следующем примере отключаются службы для пользователей в отделе продаж в США.
    
```powershell
$USSales = Get-MsolUser -All -Department "Sales" -UsageLocation "US"
$USSales | ForEach {Set-MsolUserLicense -UserPrincipalName $_.UserPrincipalName -LicenseOptions $LO}
```

**Способ 2: использование списка определенных учетных записей** 

Для этого выполните указанные ниже действия.
    
1. Создайте текстовый файл, в котором в каждой строке будет по одной учетной записи, как в примере ниже.
    
   ```powershell
   akol@contoso.com
   tjohnston@contoso.com
   kakers@contoso.com
   ```

   В этом примере текстовый файл — C: \\ Мои документы \\Accounts.txt.
    
2. Выполните следующую команду:
    
   ```powershell
   Get-Content "C:\My Documents\Accounts.txt" | foreach {Set-MsolUserLicense -UserPrincipalName $_ -LicenseOptions $LO}
   ```

Если вы хотите отключить доступ к службам для нескольких планов лицензирования, повторите указанные выше инструкции для каждого плана лицензирования, убедившись в том, что:

- Учетным записям пользователей назначен план лицензирования.
- Службы, которые необходимо отключить, доступны в плане лицензирования.

Чтобы отключить службы Microsoft 365 для пользователей при назначении их плану лицензирования, ознакомьтесь со статьей [Отключение доступа к службам при назначении пользовательских лицензий](disable-access-to-services-while-assigning-user-licenses.md).

### <a name="assign-all-services-in-a-licensing-plan-to-a-user-account"></a>Назначить учетной записи пользователя все службы в плане лицензирования

Для учетных записей пользователей, для которых отключены службы, можно включить все службы для определенного плана лицензирования с помощью следующих команд:

```powershell
$userUPN="<user account UPN>"
$acctSKU="<AccountSkuId>"
$LO = New-MsolLicenseOptions -AccountSkuId $acctSKU
Set-MsolUserLicense -UserPrincipalName $userUPN -LicenseOptions $LO
```

## <a name="related-topic"></a>Связанная тема

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
