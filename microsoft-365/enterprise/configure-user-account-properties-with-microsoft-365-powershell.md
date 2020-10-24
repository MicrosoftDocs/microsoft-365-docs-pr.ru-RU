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

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Вы можете использовать центр администрирования Microsoft 365 для настройки свойств учетных записей пользователей клиента Microsoft 365. В PowerShell можно также выполнить эту задачу, а также другие действия, которые невозможно выполнить в центре администрирования.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Чтобы настроить свойства учетных записей пользователей в модуле PowerShell Azure Active Directory для Graph, используйте командлет [**Set – AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) и укажите свойства, которые нужно задать или изменить.

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
   
### <a name="change-properties-for-a-specific-user-account"></a>Изменение свойств учетной записи пользователя

Вы идентифицируете учетную запись с помощью параметра *– ObjectID* , а также устанавливаете или изменяет определенные свойства с помощью дополнительных параметров. Ниже перечислены наиболее распространенные параметры.
  
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
    
Дополнительные параметры можно найти в разделе [Set – AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .

>[!Note]
>Перед назначением лицензий учетной записи пользователя необходимо назначить место использования.
>

Чтобы отобразить имя участника-пользователя для учетных записей пользователей, выполните следующую команду.
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
1. Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).
    
1. Сортировать список имен субъектов-пользователей в алфавитном порядке (**Сортировка userPrincipalName**) и отправлять их в следующую команду ( **|** ).
    
1. Отобразите только свойство имени участника-пользователя для каждой учетной записи (**выберите userPrincipalName**).

1. Отобразить их на одном экране (**More**).
    
Чтобы отобразить имя участника-пользователя для учетной записи на основе его отображаемого имени (имя и фамилия), выполните следующие команды. Заполните переменную *$username* и удалите \< and > символы:
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

В этом примере отображается имя участника пользователя для учетной записи пользователя с отображаемым именем *Caleb Sills*.
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

С помощью переменной *$upn* можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен. Ниже приведен пример, в котором показано, как задать *Светланы Коноваловой*в качестве места использования для Франции. Но здесь указывается его отображаемое имя, а не имя участника пользователя:
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Изменение свойств для всех учетных записей пользователей

Чтобы изменить свойства для всех пользователей, можно использовать сочетание командлетов **Get – AzureADUser** и **Set – AzureADUser** . В следующем примере показано, как изменить расположение использования для всех пользователей на *Франция*:
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
1. Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).
    
1. Задайте для расположения пользователя значение Франция (**Set-AzureADUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Изменение свойств для определенного набора учетных записей пользователей

Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать сочетания командлетов **Get – AzureADUser**, **WHERE**и **Set — AzureADUser** . В следующем примере показано, как изменить место использования для всех пользователей в отделе учета на *Франция*:
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
1. Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).
    
1.  Найдите все учетные записи пользователей, для которых для свойства *Department* задано значение "Accounting" (**where {$ _. Department-EQ "Accounting"}**) и отправьте полученные сведения в следующую команду ( **|** ).
    
1. Задайте для расположения пользователя значение Франция (**Set-AzureADUser-UsageLocation "fr"**).
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Чтобы настроить свойства учетных записей пользователей с помощью модуля Microsoft Azure Active Directory для Windows PowerShell, используйте командлет **Set – MsolUser** и укажите свойства, которые нужно задать или изменить.

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
  
>[!Note]
>Среда PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для модуля Windows PowerShell и командлеты с *MSOL* в имени. Выполните эти командлеты в Windows PowerShell.
>

### <a name="change-properties-for-a-specific-user-account"></a>Изменение свойств учетной записи пользователя

Чтобы настроить свойства для конкретной учетной записи пользователя, используйте командлет [**Set – MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) и укажите свойства, которые нужно задать или изменить. 

Вы идентифицируете учетную запись с помощью параметра *– userPrincipalName* , а также устанавливаете или изменяет определенные свойства с помощью дополнительных параметров. Ниже перечислены наиболее распространенные параметры.
  
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
    
Дополнительные параметры можно найти в разделе [Set – MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).

Чтобы просмотреть имена участников пользователя для всех пользователей, выполните следующую команду:
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
1. Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).
    
1. Сортировать список имен субъектов-пользователей в алфавитном порядке (**Сортировка userPrincipalName**) и отправлять их в следующую команду ( **|** ).
    
1. Отобразите только свойство имени участника-пользователя для каждой учетной записи (**выберите userPrincipalName**).
    
1. Отобразить их на одном экране (**More**).
    
Чтобы отобразить имя участника-пользователя для учетной записи на основе его отображаемого имени (имя и фамилия), выполните следующие команды. Заполните переменную *$username* и удалите \< and > символы.
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

В этом примере отображается имя участника пользователя с именем Caleb Sills:
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

С помощью переменной *$upn* можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен. Ниже приведен пример, в котором показано, как настроить *Светланы Коноваловой*в качестве места использования для *Франции*, но указать его отображаемое имя вместо основного имени пользователя:
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a>Изменение свойств для всех учетных записей пользователей

Чтобы изменить свойства для всех пользователей, используйте сочетание командлетов **Get – MsolUser** и **Set – MsolUser** . В следующем примере показано, как изменить расположение использования для всех пользователей на *Франция*:
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
1. Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).
    
1. Задайте для расположения пользователя значение Франция (**Set-MsolUser-UsageLocation "fr"**).
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a>Изменение свойств для определенного набора учетных записей пользователей

Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать сочетания командлетов **Get – MsolUser**, **WHERE**и **Set — MsolUser** . В следующем примере показано, как изменить место использования для всех пользователей в отделе учета на *Франция*:
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
1. Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).
    
1. Найдите все учетные записи пользователей, для которых для свойства *Department* задано значение "Accounting" (**where {$ _. Department-EQ "Accounting"}**) и отправьте полученные сведения в следующую команду ( **|** ).
    
1. Задайте для расположения пользователя значение Франция (**Set-MsolUser-UsageLocation "fr"**).

## <a name="see-also"></a>Дополнительные ресурсы:

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
