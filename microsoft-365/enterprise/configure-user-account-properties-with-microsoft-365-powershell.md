---
title: Настройка свойств учетной записи microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Используйте PowerShell для Microsoft 365 для настройки свойств отдельных или нескольких учетных записей пользователей в клиенте Microsoft 365.
ms.openlocfilehash: 6b674641842f89fd8c8e22dc26350cdd53734b9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911088"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Настройка свойств учетной записи microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Центр администрирования Microsoft 365 можно использовать для настройки свойств для учетных записей пользователей клиента Microsoft 365. В PowerShell вы также можете сделать это, а также некоторые другие вещи, которые вы не можете сделать в центре администрирования.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Чтобы настроить свойства для учетных записей пользователей в модуле Azure Active Directory PowerShell для Graph, используйте командлет [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) и укажите свойства для настройки или изменения.

[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   
### <a name="change-properties-for-a-specific-user-account"></a>Изменение свойств учетной записи пользователя

Вы определяете учетную запись с *параметром -ObjectID* и задаете или измените конкретные свойства с помощью дополнительных параметров. Вот список наиболее распространенных параметров:
  
- -Department "<название отдела>"
    
- -DisplayName "<полное имя пользователя>"
    
- -FacsimilieTelephoneNumber "<номер факса>"
    
- -GivenName "<имя пользователя>"
    
- -Surname "<фамилия пользователя>"
    
- -Mobile "<номер мобильного телефона>"
    
- -JobTitle "<должность>"
    
- -PreferredLanguage "<язык>"
    
- -StreetAddress "<почтовый адрес>"
    
- -City "<название города>"
    
- -State "<название региона>"
    
- -PostalCode "<почтовый индекс>"
    
- -Country "<название страны>"
    
- -TelephoneNumber "<номер рабочего телефона>"
    
- -UseLocation \<2-character country or region code> " "
    
    Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).
    
Дополнительные параметры см. [в видеоролике Set-AzureADUser.](/powershell/module/azuread/set-azureaduser?view=azureadps-2.0)

>[!Note]
>Прежде чем назначить лицензии учетной записи пользователя, необходимо назначить расположение использования.
>

Чтобы отобразить имя участника-пользователя для учетных записей пользователей, выполните следующую команду.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Эта команда предписывает PowerShell:
  
1. Получите всю информацию о учетных записях пользователей **(Get-AzureADUser)** и отправьте ее в следующую команду ( **|** ).
    
1. Сортировать список имен основных пользователей в алфавитном порядке **(Sort UserPrincipalName)** и отправить его в следующую команду ( **|** ).
    
1. Отобразить только свойство Имя пользователя для каждой учетной записи **(Выберите UserPrincipalName).**

1. Отобразить их на одном экране (**More**).
    
Чтобы отобразить имя пользователя для учетной записи на основе ее имени отображения (имя и фамилия), запустите следующие команды. Заполните *переменную $userName* и удалите \< and > символы:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

В этом примере отображается основное имя пользователя для учетной записи пользователя с отображаемой именем *Caleb Sills.*
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

С помощью переменной *$upn* можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен. Вот пример, который задает расположение использования *Белинда Ньюман* во Францию. Но в нем указывается ее имя отображения, а не ее имя пользователя:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Изменение свойств для всех учетных записей пользователей

Чтобы изменить свойства для всех пользователей, можно использовать комбинацию комбинирований **Get-AzureADUser** и **Set-AzureADUser.** В следующем примере изменяется расположение использования для всех пользователей во *Франции:*
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell:
  
1. Получите всю информацию об учетных записях пользователей **(Get-AzureADUser)** и отправьте ее в следующую команду ( **|** ).
    
1. Установите расположение пользователя во Франции **(Set-AzureADUser-UseLocation "FR").**
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Изменение свойств для определенного набора учетных записей пользователей

Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать комбинацию комбинеатов **Get-AzureADUser**, **Where** и **Set-AzureADUser.** В следующем примере изменяется расположение использования для всех пользователей в отделе бухгалтерского учета *во Францию:*
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell:
  
1. Получите всю информацию о учетных записях пользователей **(Get-AzureADUser)** и отправьте ее в следующую команду ( **|** ).
    
1.  Найдите все учетные записи пользователей, которые имеют свойство *Department* с набором "Учет"**(Where {$_). Department -eq "Accounting"}** и отправьте в следующую команду **|** ().
    
1. Установите расположение пользователя во Франции **(Set-AzureADUser-UseLocation "FR").**
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Чтобы настроить свойства для учетных записей пользователей с помощью модуля Microsoft Azure Active Directory для Windows PowerShell, используйте командлет **Set-MsolUser** и укажите свойства для настройки или изменения.

[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*. Эти командлеты требуется запускать из Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Изменение свойств учетной записи пользователя

Чтобы настроить свойства для определенной учетной записи пользователя, используйте комлет [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) и укажите свойства для настройки или изменения. 

Вы определяете учетную запись с параметром *-UserPrincipalName* и задате или измените конкретные свойства с помощью дополнительных параметров. Вот список наиболее распространенных параметров.
  
- -City "<название города>"
    
- -Country "<название страны>"
    
- -Department "<название отдела>"
    
- -DisplayName "<полное имя пользователя>"
    
- -Fax "<номер факса>"
    
- -FirstName "<имя пользователя>"
    
- -LastName "<фамилия пользователя>"
    
- -MobilePhone "<номер мобильного телефона>"
    
- -Office "<расположение офиса>"
    
- -PhoneNumber "<номер телефона офиса>"
    
- -PostalCode "<почтовый индекс>"
    
- -PreferredLanguage "<язык>"
    
- -State "<название региона>"
    
- -StreetAddress "<почтовый адрес>"
    
- -Title "<должность>"
    
- -UseLocation \<2-character country or region code> " "
    
    Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).
    
Дополнительные параметры см. [в рублях Set-MsolUser.](/previous-versions/azure/dn194136(v=azure.100))

Чтобы увидеть главные имена пользователей всех пользователей, запустите следующую команду:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Эта команда предписывает PowerShell:
  
1. Получите всю информацию для учетных записей пользователей **(Get-MsolUser)** и отправьте ее в следующую команду ( **|** ).
    
1. Сортировать список имен основных пользователей в алфавитном порядке **(Sort UserPrincipalName)** и отправить его в следующую команду ( **|** ).
    
1. Отобразить только свойство Имя пользователя для каждой учетной записи **(Выберите UserPrincipalName).**
    
1. Отобразить их на одном экране (**More**).
    
Чтобы отобразить имя пользователя для учетной записи на основе ее имени отображения (имя и фамилия), запустите следующие команды. Заполните *переменную $userName* и удалите \< and > символы.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

В этом примере отображается имя пользователя с именем Caleb Sills:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

С помощью переменной *$upn* можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен. Вот пример, который задает расположение использования Белинда Ньюман во Францию, но указывает ее имя отображения, а не ее имя пользователя:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Изменение свойств для всех учетных записей пользователей

Чтобы изменить свойства для всех пользователей, используйте комбинацию комбинирований **Get-MsolUser** и **Set-MsolUser.** В следующем примере изменяется расположение использования для всех пользователей во *Франции:*
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell:
  
1. Получите всю информацию для учетных записей пользователей **(Get-MsolUser)** и отправьте ее в следующую команду ( **|** ).
    
1. Установите расположение пользователя во Франции **(Set-MsolUser-UseLocation "FR").**
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Изменение свойств для определенного набора учетных записей пользователей

Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать комбинацию cmdlets **Get-MsolUser**, **Where** и **Set-MsolUser.** В следующем примере изменяется расположение использования для всех пользователей в отделе бухгалтерского учета *во Францию:*
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell:
  
1. Получите всю информацию для учетных записей пользователей **(Get-MsolUser)** и отправьте ее в следующую команду ( **|** ).
    
1. Найдите все учетные записи пользователей, которые имеют свойство *Department* с набором "Учет"**(Where {$_). Department -eq "Accounting"}** и отправьте выдаваемую информацию в следующую команду ( **|** ).
    
1. Установите расположение пользователя во Франции **(Set-MsolUser-UseLocation "FR").**

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)