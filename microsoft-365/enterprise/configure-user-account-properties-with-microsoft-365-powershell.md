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
description: 'Сводка: использование PowerShell для Microsoft 365 для настройки свойств отдельных или нескольких учетных записей пользователей в клиенте Microsoft 365.'
ms.openlocfilehash: ae797d67b47c637dc95176b92fad8090f8a7ab37
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580932"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a>Настройка свойств учетной записи пользователя Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Несмотря на то, что вы можете использовать центр администрирования Microsoft 365 для настройки свойств учетных записей пользователей клиента Microsoft 365, вы также можете использовать PowerShell и выполнить некоторые действия, которые не могут находиться в центре администрирования Microsoft 365.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Чтобы настроить свойства учетных записей пользователей с помощью модуля PowerShell Azure Active Directory для Graph, используйте командлет [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser), указав свойства, которые нужно задать или изменить. 

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
   
### <a name="change-properties-for-a-specific-user-account"></a>Изменение свойств учетной записи пользователя

Параметр **-ObjectID** указывает учетную запись, а ее свойства можно задать или изменить с помощью дополнительных параметров. Ниже перечислены наиболее распространенные.
  
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
    
- — UsageLocation " \<2-character country or region code> "
    
    Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).
    
Сведения о дополнительных параметрах см. в статье [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser).

>[!Note]
>Перед назначением лицензий учетной записи пользователя необходимо назначить место использования.
>

Чтобы отобразить имя участника-пользователя для учетных записей пользователей, выполните следующую команду.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
- Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).
    
- Сортировать список имен субъектов-пользователей в алфавитном порядке (**Сортировка userPrincipalName**) и отправлять их в следующую команду ( **|** ).
    
- Отобразите только свойство имени участника-пользователя для каждой учетной записи (**выберите userPrincipalName**).

- Отобразить их на одном экране (**More**).
    
Эта команда перечислит все учетные записи. Если вы хотите отобразить имя участника-пользователя для учетной записи на основе отображаемого имени (имя и фамилия), заполните приведенную ниже переменную **$username** (удалив \< and > символы), а затем выполните следующие команды:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

В этом примере выводится имя участника-пользователя для учетной записи пользователя с отображаемым именем Caleb Sills.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

С помощью переменной **$upn** можно вносить изменения в учетные записи, указывая их отображаемые имена. В этом примере показано, как заменить текущее место работы пользователя Belinda Newman на Францию, указав при этом соответствующее отображаемое имя, а не имя участника-пользователя:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Изменение свойств для всех учетных записей пользователей

Чтобы изменить свойства для всех пользователей, примените сочетание командлетов **Get-AzureADUser** и **Set-AzureADUser**. Следующий пример заменяет текущее расположение использования для всех пользователей на Францию:
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
- Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).
    
- Задайте для расположения пользователя значение Франция (**Set-AzureADUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Изменение свойств определенной части учетных записей пользователей

Сочетание командлетов **Get-AzureADUser**, **Where** и **Set-AzureADUser** позволит изменить свойства определенной части учетных записей пользователей. Следующая команда заменяет расположение всех пользователей в отделе Accounting на Францию:
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
- Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).
    
- Найдите все учетные записи пользователей, для которых в свойстве Department задано значение "Accounting" (**где {$ _. Department-EQ "Accounting"}**) и отправьте полученные сведения в следующую команду ( **|** ).
    
- Задайте для расположения пользователя значение Франция (**Set-AzureADUser-UsageLocation "fr"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Чтобы настроить свойства учетных записей пользователей с помощью модуля Microsoft Azure Active Directory для Windows PowerShell, используйте командлет **Set – MsolUser** и укажите свойства, которые нужно задать или изменить. 

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Изменение свойств учетной записи пользователя

Чтобы настроить свойства учетной записи пользователя, используйте командлет [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) и укажите свойства, которые нужно задать или изменить. 

Параметр **-UserPrincipalName** указывает учетную запись, а ее свойства можно задать или изменить с помощью дополнительных параметров. Ниже перечислены наиболее распространенные.
  
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
    
- — UsageLocation " \<2-character country or region code> "
    
    Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).
    
Сведения о дополнительных параметрах см. в статье [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).

Чтобы просмотреть имя участника-пользователя для каждого из пользователей, выполните приведенную ниже команду.
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
- Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).
    
- Сортировать список имен субъектов-пользователей в алфавитном порядке (**Сортировка userPrincipalName**) и отправлять их в следующую команду ( **|** ).
    
- Отобразите только свойство имени участника-пользователя для каждой учетной записи (**выберите userPrincipalName**).
    
- Отобразить их на одном экране (**More**).
    
Эта команда перечислит все учетные записи. Если вы хотите отобразить имя участника-пользователя для учетной записи на основе отображаемого имени (имя и фамилия), заполните приведенную ниже переменную **$username** (удалив \< and > символы), а затем выполните следующие команды:
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

Этот пример отображает имя участника-пользователя для пользователя Caleb Sills.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

С помощью переменной **$upn** можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен. Данный пример показывает, как заменить текущее расположение использования для пользователя Belinda Newman на Францию, указав при этом соответствующее отображаемое имя, а не имя участника-пользователя:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Изменение свойств для всех учетных записей пользователей

Чтобы изменить свойства для всех пользователей, можно использовать сочетание командлетов **Get-MsolUser** и **Set-MsolUser**. В следующем примере место работы всех пользователей меняется на Францию:
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
- Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).
    
- Задайте для расположения пользователя значение Франция (**Set-MsolUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Изменение свойств для определенного набора учетных записей пользователей

Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать сочетание командлетов **Get – MsolUser**, **WHERE**и **Set — MsolUser** . Пример кода, приведенный ниже, заменяет текущее расположение использования для всех пользователей в отделе Accounting (бухгалтерского учета) на Францию.
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
- Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).
    
- Найдите все учетные записи пользователей, для которых в свойстве Department задано значение "Accounting" (**где {$ _. Department-EQ "Accounting"}**) и отправьте полученные сведения в следующую команду ( **|** ).
    
- Задайте для расположения пользователя значение Франция (**Set-MsolUser-UsageLocation "fr"**).


## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
