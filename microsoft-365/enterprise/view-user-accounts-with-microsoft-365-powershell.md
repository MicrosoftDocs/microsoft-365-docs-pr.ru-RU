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
description: Сведения о том, как просматривать, перечислить и отображать учетные записи пользователей Microsoft 365 различными способами с помощью PowerShell.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754076"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Просмотр учетных записей пользователей Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Вы можете использовать центр администрирования Microsoft 365 для просмотра учетных записей клиента Microsoft 365. PowerShell для Microsoft 365 включает это, но также предоставляет дополнительные функции.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
### <a name="view-all-accounts"></a>Просмотр всех учетных записей

Чтобы отобразить полный список учетных записей пользователей, выполните следующую команду:
  
```powershell
Get-AzureADUser
```

Необходимо получить сведения, аналогичные приведенным ниже.
  
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

Чтобы отобразить определенную учетную запись пользователя, выполните следующую команду. Введите имя учетной записи пользователя, которая также называется именем участника-пользователя (UPN). Удалите символы "<" и ">".
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Пример:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Просмотр дополнительных значений свойств для конкретной учетной записи

По умолчанию командлет **Get – AzureADUser** отображает свойства *ObjectID*, *DisplayName*и *userPrincipalName* для учетных записей.

Чтобы более избирательно выбирать свойства для отображения, используйте командлет **SELECT** в сочетании с командлетом **Get – AzureADUser** . Чтобы объединить два командлета, используйте символ "pipe" ("|"), который указывает Azure Active Directory PowerShell для Graph принимать результаты одной команды и отправлять ее в следующую команду. Ниже приведен пример команды, которая отображает *DisplayName*, *Department*и *UsageLocation* для каждой учетной записи пользователя:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
1. Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).
    
1.  Отображение только имени, отдела и места использования учетной записи пользователя (**выберите DisplayName, Department, UsageLocation**).
  
Чтобы просмотреть все свойства для конкретной учетной записи пользователя, используйте командлет **SELECT** и подстановочный знак (*). Пример:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

В качестве другого примера выполните следующую команду, чтобы проверить включенное состояние конкретной учетной записи пользователя:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Просмотр состояния синхронизации учетной записи

Учетные записи пользователей имеют два источника: 

- Windows Server Active Directory (AD), которая является учетными записями, которые синхронизируют локальную службу AD с облаком.

- Учетные записи Active Directory Azure Active Directory (Azure AD), которые создаются непосредственно в облаке.


Следующая команда предписывает PowerShell получить всех пользователей, у которых атрибут *дирсинценаблед* имеет значение *true*. Его можно использовать для поиска учетных записей, которые синхронизируются из локальной службы AD.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

Следующая команда предписывает PowerShell получить всех пользователей, у которых атрибут *дирсинценаблед* имеет значение *false*. С его помощью можно найти учетные записи только для облака.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Просмотр учетных записей на основе общего свойства

Чтобы сделать более избирательным список отображаемых учетных записей, можно использовать командлет **WHERE** в сочетании с командлетом **Get – AzureADUser** . Чтобы объединить два командлета, используйте символ "pipe" ("|"), который указывает Azure Active Directory PowerShell для Graph принимать результаты одной команды и отправлять ее в следующую команду. Ниже приведен пример команды, которая отображает только те учетные записи пользователей с незаданной областью использования:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Эта команда указывает Azure Active Directory PowerShell для Graph:
  
1. Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).
    
1. Найдите все учетные записи пользователей с незаданной областью использования (**где {$ \_ . UsageLocation-EQ $Null}**). В фигурных скобках команда предписывает PowerShell только искать набор учетных записей, для которых свойство учетной записи пользователя UsageLocation (** $ \_ . UsageLocation**) не указан (**-EQ $NULL**).
    
**UsageLocation** — лишь одно из многих свойств, связанных с учетной записью пользователя. Чтобы отобразить все свойства для конкретной учетной записи пользователя, используйте командлет **SELECT** и подстановочный знак (*). Пример:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Например, **City** — это имя свойства учетной записи пользователя. С помощью следующей команды можно получить список всех учетных записей пользователей, проживающих в Лондоне:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  В приведенных ниже примерах используется синтаксис для командлета **WHERE** **{$ \_ .** [имя свойства учетной записи пользователя] [оператор сравнения] оно **}**. > [оператор сравнения] имеет значение **-EQ** для Equals, **-Ne** для Not Equals, **-lt** для "меньше, чем", "-gt" для "больше чем", " **-gt** " и других.  [Value] как правило, это строка (последовательность букв, цифр и других знаков), числовое значение или **$null** не указано. Для получения дополнительных [сведений см.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="view-all-accounts"></a>Просмотр всех учетных записей

Чтобы отобразить полный список учетных записей пользователей, выполните следующую команду:
  
```powershell
Get-MsolUser
```

>[!Note]
>Среда PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для модуля Windows PowerShell и командлеты с *MSOL* в имени. Выполните эти командлеты в Windows PowerShell.
>

Необходимо получить сведения, аналогичные приведенным ниже.
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

У командлета **Get-MsolUser** также есть ряд параметров для фильтрации отображаемых учетных данных. Например, для списка нелицензированных пользователей (пользователей, которые были добавлены в Microsoft 365, но еще не лицензированы для использования каких-либо служб) выполните следующую команду:
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Необходимо получить сведения, аналогичные приведенным ниже.
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Дополнительные сведения о дополнительных параметрах для фильтрации отображаемого набора учетных записей пользователей приведены в статье [Get – MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Просмотр определенной учетной записи

Чтобы отобразить определенную учетную запись пользователя, выполните следующую команду. Введите имя для входа учетной записи пользователя, которое также называется именем участника-пользователя (UPN). Удалите символы "<" и ">".
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Просмотр учетных записей на основе общего свойства

Чтобы сделать более избирательным список отображаемых учетных записей, можно использовать командлет **WHERE** в сочетании с командлетом **Get – MsolUser** . Чтобы объединить два командлета, используйте символ "pipe" ("|"), который указывает PowerShell на получение результатов одной команды и их отправку в следующую команду. Ниже приведен пример, в котором отображаются только те учетные записи пользователей, для которых не указано неопределенное место использования:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
1. Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).
    
1. Поиск всех учетных записей пользователей с незаданной областью использования (**где {$ \_ . UsageLocation-EQ $Null}**). В фигурных скобках команда предписывает PowerShell найти только набор учетных записей, для которых свойство учетной записи пользователя UsageLocation (** $ \_ . UsageLocation**) не указан (**-EQ $NULL**).
    
Необходимо получить сведения, аналогичные приведенным ниже.
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

*UsageLocation* — лишь одно из многих свойств, связанных с учетной записью пользователя. Чтобы просмотреть все свойства учетных записей пользователей, используйте командлет **SELECT** и подстановочный знак (*), чтобы отображать их все для конкретной учетной записи пользователя. Пример:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Например, *City* — это имя свойства учетной записи пользователя. Вы можете использовать следующую команду, чтобы получить список всех учетных записей пользователей для пользователей, проживающих в Лондоне:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  В приведенных ниже примерах используется синтаксис для командлета **WHERE** **{$ \_ .** [имя свойства учетной записи пользователя] [оператор сравнения] оно **}**.  [оператор сравнения] имеет значение **-EQ** для Equals, **-Ne** для Not Equals, **-lt** для "больше чем", " **-gt** " для "больше чем", и других.  [Value] как правило, это строка (последовательность букв, цифр и других знаков), числовое значение или **$null** не указано. Для получения дополнительных [сведений см.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)
  
Чтобы проверить состояние блокировки учетной записи пользователя, выполните следующую команду:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Просмотр дополнительных значений свойств для учетных записей

По умолчанию командлет **Get – MsolUser** отображает следующие три свойства учетных записей пользователей:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Если требуются дополнительные свойства, например отдел, в котором работает пользователь, и страна или регион, где используются службы Microsoft 365, можно выполнить командлет **Get-MsolUser** в сочетании с командлетом **SELECT** , чтобы указать список свойств учетной записи пользователя. Пример:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
1. Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).
    
1. Отображение только имени, отдела и места использования учетной записи пользователя (**выберите DisplayName, Department, UsageLocation**).
    
Необходимо получить сведения, аналогичные приведенным ниже.
  
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

Командлет **SELECT** позволяет выбрать отображаемые свойства. Чтобы отобразить все свойства для конкретной учетной записи пользователя, используйте подстановочный знак (*). Пример:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Чтобы сделать более избирательным список учетных записей для отображения, можно также использовать командлет **WHERE** . Ниже приведен пример команды, которая отображает только те учетные записи пользователей с незаданной областью использования:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
1. Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).
    
1. Поиск всех учетных записей пользователей с незаданной областью использования (**где {$ \_ . UsageLocation-EQ $Null}**) и отправьте полученные сведения в следующую команду ( **|** ). В фигурных скобках команда предписывает PowerShell только искать набор учетных записей, для которых свойство учетной записи пользователя UsageLocation (** $ \_ . UsageLocation**) не указан (**-EQ $NULL**).
    
1. Отображение только имени, отдела и места использования учетной записи пользователя (**выберите DisplayName, Department, UsageLocation**).
    
Необходимо получить сведения, аналогичные приведенным ниже.
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Если вы используете синхронизацию службы каталогов для создания пользователей Microsoft 365 и управления ими, вы можете отобразить локальную учетную запись, из которой проецируется пользователь Microsoft 365. В следующем примере предполагается, что:

- Служба Azure AD Connect настроена на использование привязки источника по умолчанию ObjectGUID. (Дополнительные сведения о настройке привязки источника см. в статье [Azure AD Connect: концепция дизайна](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).
- Установлен модуль доменных служб Active Directory для PowerShell (см. [инструменты RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Дополнительные ресурсы:

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)
