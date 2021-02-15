---
title: Настройка свойств учетной записи пользователя Microsoft 365 с помощью PowerShell
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
description: Используйте PowerShell для Microsoft 365, чтобы настроить свойства отдельных или нескольких учетных записей пользователей в клиенте Microsoft 365.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754332"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Настройка свойств учетной записи пользователя Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Центр администрирования Microsoft 365 можно использовать для настройки свойств учетных записей пользователей клиента Microsoft 365. В PowerShell это также можно сделать, а также некоторые другие вещи, которые нельзя сделать в Центре администрирования.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Чтобы настроить свойства учетных записей пользователей в модуле Azure Active Directory PowerShell для Graph, используйте командлет [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) и укажите свойства, которые необходимо задать или изменить.

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
   
### <a name="change-properties-for-a-specific-user-account"></a>Изменение свойств учетной записи пользователя

Учетная запись идентифицируется с помощью параметра *-ObjectID* и заданы или изменяются определенные свойства с помощью дополнительных параметров. Вот список наиболее распространенных параметров:
  
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
    
- -UsageLocation \<2-character country or region code> "
    
    Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).
    
Дополнительные параметры [см. в подстройке Set-AzureADUser.](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0)

>[!Note]
>Прежде чем назначать лицензии учетной записи пользователя, необходимо назначить место использования.
>

Чтобы отобразить имя участника-пользователя для учетных записей пользователей, выполните следующую команду.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Эта команда предписывает PowerShell:
  
1. Получите все сведения об учетных записях пользователей **(Get-AzureADUser)** и отправьте их в следующую команду ( **|** ).
    
1. Сортировка списка имен участников-пользователей в алфавитном порядке (**Sort UserPrincipalName)** и отправка его в следующую команду ( **|** ).
    
1. Отображает только свойство user Principal Name для каждой учетной записи (**Select UserPrincipalName).**

1. Отобразить их на одном экране (**More**).
    
Чтобы отобразить имя основного пользователя для учетной записи на основе ее отображаемой имени (имени и фамилии), запустите следующие команды. Заполните *переменную $userName* и удалите \< and > символы:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

В этом примере отображается имя пользователя-пользователя для учетной записи пользователя с отображаемой именем *Caleb Sills.*
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

С помощью переменной *$upn* можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен. Вот пример, в качестве расположения использования для *Belinda Newman* задав францию. Но в нем указывается ее отображаемая имя, а не имя основного пользователя:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Изменение свойств для всех учетных записей пользователей

Чтобы изменить свойства для всех пользователей, можно использовать сочетание **get-AzureADUser** и **set-AzureADUser.** В следующем примере расположение использования для всех пользователей изменяется на *Францию:*
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell:
  
1. Получите все сведения об учетных записях пользователей **(Get-AzureADUser)** и отправьте их в следующую команду ( **|** ).
    
1. Установите расположение пользователя для Франции (**Set-AzureADUser -UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Изменение свойств для определенного набора учетных записей пользователей

Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать сочетание с помощью cmdlets **Get-AzureADUser**, **Where** и **Set-AzureADUser.** В следующем примере расположение использования для всех пользователей в бухгалтерии изменяется на *Францию:*
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell:
  
1. Получите все сведения об учетных записях пользователей **(Get-AzureADUser)** и отправьте их в следующую команду ( **|** ).
    
1.  Найдите все учетные записи пользователей, свойство *Department* которых имеет свойство Accounting **(Где {$_). Department -eq "Accounting"}**) и отправьте итоговые сведения в следующую команду ( **|** ).
    
1. Установите расположение пользователя для Франции (**Set-AzureADUser -UsageLocation "FR"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Чтобы настроить свойства учетных записей пользователей с помощью модуля Microsoft Azure Active Directory для Windows PowerShell, используйте командлет **Set-MsolUser** и укажите свойства, которые необходимо задать или изменить.

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)
  
>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*. Эти командлеты требуется запускать из Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Изменение свойств учетной записи пользователя

Чтобы настроить свойства для определенной учетной записи пользователя, используйте cmdlet [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) и укажите свойства, которые необходимо задать или изменить. 

Учетная запись идентифицируется с помощью параметра *-UserPrincipalName* и заданы или изменяются определенные свойства с помощью дополнительных параметров. Вот список наиболее распространенных параметров.
  
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
    
- -UsageLocation \<2-character country or region code> "
    
    Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).
    
Дополнительные параметры [см. в подстроке Set-MsolUser.](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))

Чтобы увидеть имена участников-пользователей всех пользователей, запустите следующую команду:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Эта команда предписывает PowerShell:
  
1. Получите все сведения об учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).
    
1. Сортировка списка имен участников-пользователей в алфавитном порядке (**Sort UserPrincipalName)** и отправка его в следующую команду ( **|** ).
    
1. Отображает только свойство user Principal Name для каждой учетной записи (**Select UserPrincipalName).**
    
1. Отобразить их на одном экране (**More**).
    
Чтобы отобразить имя основного пользователя для учетной записи на основе ее отображаемой имени (имени и фамилии), запустите следующие команды. Заполните *переменную $userName* и удалите \< and > символы.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

В этом примере отображается имя пользователя с именем Caleb Sills:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

С помощью переменной *$upn* можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен. Вот пример, в который для пользователя *Belinda Newman* задано расположение использования для *Франции,* но указывается ее отображаемая имя, а не ее имя-пользователя.
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Изменение свойств для всех учетных записей пользователей

Чтобы изменить свойства для всех пользователей, используйте комбинацию с помощью **get-MsolUser** и **Set-MsolUser.** В следующем примере расположение использования для всех пользователей изменяется на *Францию:*
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell:
  
1. Получите все сведения об учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).
    
1. Установите расположение пользователя для Франции (**Set-MsolUser -UsageLocation "FR"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Изменение свойств для определенного набора учетных записей пользователей

Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать сочетание с помощью **get-MsolUser,** **Where** и **Set-MsolUser.** В следующем примере расположение использования для всех пользователей в бухгалтерии изменяется на *Францию:*
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell:
  
1. Получите все сведения об учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).
    
1. Найдите все учетные записи пользователей, свойство *Department* которых имеет свойство Accounting **(Где {$_). Department -eq "Accounting"}**) и отправьте итоговые сведения в следующую команду ( **|** ).
    
1. Установите расположение пользователя для Франции (**Set-MsolUser -UsageLocation "FR"**).

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
