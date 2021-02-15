---
title: Просмотр учетных записей пользователей Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: Узнайте, как просматривать, перечислять и отображать учетные записи пользователей Microsoft 365 различными способами с помощью PowerShell.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754076"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Просмотр учетных записей пользователей Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Для просмотра учетных записей клиента Microsoft 365 можно использовать Центр администрирования Microsoft 365. PowerShell для Microsoft 365 обеспечивает эту возможность, но также предоставляет дополнительные функции.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
### <a name="view-all-accounts"></a>Просмотр всех учетных записей

Чтобы отобразить полный список учетных записей пользователей, запустите команду:
  
```powershell
Get-AzureADUser
```

Вы должны получить сведения, похожие на эти:
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a>Просмотр определенной учетной записи

Чтобы отобразить определенную учетную запись пользователя, запустите следующую команду. Уполномочете имя учетной записи для регистрации, которое также называется именем основного пользователя (UPN). Удалите символы "<" и ">".
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Пример:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Просмотр дополнительных значений свойств для определенной учетной записи

По умолчанию для отображения свойств ObjectID, *DisplayName* и UserPrincipalName учетных записей в **get-AzureADUser** отображаются только свойства *ObjectID,* *DisplayName и UserPrincipalName.*

Чтобы более выборочно отобразить  свойства, используйте его в сочетании с **get-AzureADUser.** Чтобы объединить два командлета, используйте символ "pipe" ("|"), который сообщает Azure Active Directory PowerShell для Graph о том, что необходимо получить результаты одной команды и отправить их в следующую команду. Вот пример команды, которая отображает *displayName,* *Department* и *UsageLocation* для каждой учетной записи пользователя:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Эта команда предписывает PowerShell:
  
1. Получите все сведения об учетных записях пользователей **(Get-AzureADUser)** и отправьте их в следующую команду ( **|** ).
    
1.  Отображает только имя учетной записи пользователя, отдел и расположение использования (**Select DisplayName, Department, UsageLocation).**
  
Чтобы увидеть все свойства для определенной учетной записи пользователя, используйте с помощью cmdlet **Select** и поддиакалон (*). Пример:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

В качестве другого примера запустите следующую команду, чтобы проверить состояние включения определенной учетной записи пользователя:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Просмотр состояния синхронизации учетной записи

Учетные записи пользователей имеют два источника: 

- Windows Server Active Directory (AD) — это учетные записи, которые синхронизируются с облаком из локальной службы AD.

- Учетные записи Azure Active Directory (Azure AD) AD, которые создаются непосредственно в облаке.


Следующая команда предписывает PowerShell получить всех пользователей, для которых для атрибута *DirSyncEnabled* задано *true.* Его можно использовать для поиска учетных записей, которые синхронизируются из локальной AD.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

Следующая команда предписывает PowerShell получить всех пользователей, для которых для атрибута *DirSyncEnabled* задано *false.* Его можно использовать для поиска облачных учетных записей.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Просмотр учетных записей на основе общего свойства

Чтобы более выборочно отобразить список отображаемой учетной записи, можно использовать в сочетании с этим с помощью cmdlet **Get-AzureADUser.**  Чтобы объединить два командлета, используйте символ "pipe" ("|"), который сообщает Azure Active Directory PowerShell для Graph о том, что необходимо получить результаты одной команды и отправить их в следующую команду. Ниже показан пример команды, которая отображает только те учетные записи пользователей, которые имеют неустановленное расположение использования:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Эта команда дает указание Azure Active Directory PowerShell для Graph:
  
1. Получите все сведения об учетных записях пользователей **(Get-AzureADUser)** и отправьте их в следующую команду ( **|** ).
    
1. Найдите все учетные записи пользователей с неопределенным расположением использования **(где {$ \_ . UsageLocation -eq $Null}**). Внутри скобок команда дает powerShell указание найти только набор учетных записей, для которых свойство usageLocation учетной записи пользователя (**$ \_ . UsageLocation**) не указан (**-eq $Null**).
    
**UsageLocation** — лишь одно из многих свойств, связанных с учетной записью пользователя. Чтобы отобразить все свойства для определенной учетной записи пользователя, используйте с поддиамлетом **Select** и поддиансового знака (*). Пример:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Например, **City** — это имя свойства учетной записи пользователя. Чтобы получить список всех учетных записей пользователей в Лондоне, можно использовать следующую команду:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Синтаксис для cmdlet **Where** в этих примерах : **Where {$ \_ .** [имя свойства учетной записи пользователя] [оператор сравнения] [value] **}**.> [оператор сравнения] — **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.  [value] — это, как правило, строка (последовательность букв, чисел и других символов), числовые значения **или** $Null для неопределенных значений. Дополнительные сведения см. в [этой теме.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="view-all-accounts"></a>Просмотр всех учетных записей

Чтобы отобразить полный список учетных записей пользователей, запустите команду:
  
```powershell
Get-MsolUser
```

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*. Эти командлеты требуется запускать из Windows PowerShell.
>

Вы должны получить сведения, похожие на эти:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

У командлета **Get-MsolUser** также есть ряд параметров для фильтрации отображаемых учетных данных. Например, чтобы получить список пользователей без лицензий (пользователей, которые были добавлены в Microsoft 365, но еще не имеют лицензии на использование какой-либо из служб), запустите команду:
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Вы должны получить сведения, похожие на эти:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Дополнительные сведения о дополнительных параметрах для фильтрации отображаемого набора учетных записей пользователей см. в записи [Get-MsolUser.](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100))
  
### <a name="view-a-specific-account"></a>Просмотр определенной учетной записи

Чтобы отобразить определенную учетную запись пользователя, запустите следующую команду. Впишите имя для регистрации учетной записи пользователя, которое также называется именем пользователя-пользователя (UPN). Удалите символы "<" и ">".
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Просмотр учетных записей на основе общего свойства

Чтобы более выборочно отобразить список отображаемой учетной записи, можно использовать в сочетании с этим с помощью cmdlet **Get-MsolUser.**  Чтобы объединить два командлета, используйте символ "pipe" ("|"), который сообщает PowerShell о том, что необходимо получить результаты одной команды и отправить их в следующую команду. Ниже показан пример, в который отображаются только учетные записи пользователей с неопределенным расположением использования.
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Эта команда предписывает PowerShell:
  
1. Получите все сведения об учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).
    
1. Найдите все учетные записи пользователей с неопределенным расположением использования **(где {$ \_ . UsageLocation -eq $Null}**). Внутри скобок команда дает powerShell указание найти только набор учетных записей, для которых свойство usageLocation учетной записи пользователя (**$ \_ . UsageLocation**) не указан (**-eq $Null**).
    
Вы должны получить сведения, похожие на эти:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

*UsageLocation* — лишь одно из многих свойств, связанных с учетной записью пользователя. Чтобы увидеть все свойства учетных записей пользователей, используйте для отображения всех свойств для определенной учетной записи пользователя с помощью cmdlet **Select** и под wildcard character (*). Пример:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Например, *City* — это имя свойства учетной записи пользователя. Чтобы получить список всех учетных записей пользователей в Лондоне, можно использовать следующую команду:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Синтаксис для cmdlet **Where** в этих примерах : **Where {$ \_ .** [имя свойства учетной записи пользователя] [оператор сравнения] [value] **}**.  [оператор сравнения] — **это -eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.  [value] — это, как правило, строка (последовательность букв, чисел и других символов), числовые значения **или** $Null для неопределенных значений. Дополнительные сведения см. в [этой теме.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)
  
Чтобы проверить состояние блокировки учетной записи пользователя, используйте следующую команду:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Просмотр дополнительных значений свойств для учетных записей

По умолчанию в cmdlet **Get-MsolUser** отображаются три свойства учетных записей пользователей:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Если вам нужны дополнительные свойства, такие как отдел, в котором работает пользователь, и страна или регион, где они используют службы Microsoft 365, вы можете запустить **Get-MsolUser** в сочетании с помощью cmdlet **Select,** чтобы указать список свойств учетной записи пользователя. Пример:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Эта команда предписывает PowerShell:
  
1. Получите все сведения об учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).
    
1. Отображает только имя учетной записи пользователя, отдел и расположение использования (**Select DisplayName, Department, UsageLocation).**
    
Вы должны получить сведения, похожие на эти:
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

С **помощью** cmdlet Select вы можете выбрать, какие свойства необходимо отобразить. Чтобы отобразить все свойства определенной учетной записи пользователя, используйте под wildcard character (*). Пример:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Чтобы более выборочно отобразить список отображаемой учетной записи, можно также использовать cmdlet **Where.** Ниже показан пример команды, которая отображает только те учетные записи пользователей, которые имеют неустановленное расположение использования:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Эта команда предписывает PowerShell:
  
1. Получите все сведения об учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).
    
1. Найдите все учетные записи пользователей с неопределенным расположением использования **(где {$ \_ . UsageLocation -eq $Null}**) и отправьте итоговые сведения в следующую команду ( **|** ). Внутри скобок команда дает powerShell указание найти только набор учетных записей, для которых свойство usageLocation учетной записи пользователя (**$ \_ . UsageLocation**) не указан (**-eq $Null**).
    
1. Отображает только имя учетной записи пользователя, отдел и расположение использования (**Select DisplayName, Department, UsageLocation).**
    
Вы должны получить сведения, похожие на эти:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Если вы используете синхронизацию службы каталогов для создания пользователей Microsoft 365 и управления ими, вы можете отобразить локализованную учетную запись, из которой был проецируемый пользователь Microsoft 365. В следующем примере предполагается, что:

- Azure AD Connect настроен на использование привязки источника objectGUID по умолчанию. (Дополнительные сведения о настройке привязки источника см. в [подключении к Azure AD Connect: концепции проектирования).](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)
- Установлен модуль доменных служб Active Directory для PowerShell (см. средства [RSAT).](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
