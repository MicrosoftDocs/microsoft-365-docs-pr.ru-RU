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
ms.openlocfilehash: ea631d12a95ca813ebf9da3286e36d724d51a2f7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696521"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Просмотр учетных записей пользователей Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Несмотря на то, что вы можете использовать центр администрирования Microsoft 365 для просмотра учетных записей клиента Microsoft 365, вы также можете использовать PowerShell для Microsoft 365 и выполнять некоторые действия, которые не могут находиться в центре администрирования.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
### <a name="view-all-accounts"></a>Просмотр всех учетных записей

Чтобы отобразить полный список учетных записей пользователей, выполните следующую команду:
  
```powershell
Get-AzureADUser
```

Выходные данные должны выглядеть примерно следующим образом:
  
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

Чтобы отобразить определенную учетную запись пользователя, введите имя учетной записи пользователя, также называемое именем участника-пользователя (UPN), удалите символы "<" и ">", а затем выполните следующую команду:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Вот пример:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Просмотр дополнительных значений свойств для конкретной учетной записи

По умолчанию командлет **Get – AzureADUser** отображает свойства ObjectID, DisplayName и userPrincipalName для учетных записей.

Чтобы сделать более избирательным список отображаемых свойств, можно использовать командлет **SELECT** в сочетании с командлетом **Get – AzureADUser** . Чтобы объединить два командлета, мы используем символ ' ' pipe ' ' | ", который сообщает PowerShell Active Directory PowerShell для Graph, чтобы получить результаты одной команды и отправить ее следующей команде. Ниже приведен пример команды, которая отображает DisplayName, Department и UsageLocation для каждой учетной записи пользователя:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
- Получить всю информацию об учетных записях пользователей (**Get-AzureADUser**) и отправить их следующей команде (**|**).
    
- Отображение только имени, отдела и места использования учетной записи пользователя ( **выберите DisplayName, Department, UsageLocation** ).
  
Чтобы просмотреть все свойства учетных записей пользователей, используйте командлет **SELECT** и подстановочный знак (*), чтобы отображать их все для конкретной учетной записи пользователя. Вот пример:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

В качестве другого примера можно проверить включенное состояние конкретной учетной записи пользователя с помощью следующей команды:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-some-accounts-based-on-a-common-property"></a>Просмотр некоторых учетных записей на основе общего свойства

Чтобы сделать более избирательным список отображаемых учетных записей, можно использовать командлет **WHERE** в сочетании с командлетом **Get – AzureADUser** . Чтобы объединить два командлета, мы используем символ ' ' pipe ' ' | ", который сообщает PowerShell Active Directory PowerShell для Graph, чтобы получить результаты одной команды и отправить ее следующей команде. Ниже приведен пример команды, которая выводит только учетные записи, для которых не указано место использования:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Эта команда указывает Azure Active Directory PowerShell для Graph:
  
- Получить всю информацию об учетных записях пользователей (**Get-AzureADUser**) и отправить их следующей команде (**|**).
    
- Найдите все учетные записи пользователей с незаданной областью использования ( **где {$ \_ . UsageLocation-EQ $Null}** ). В фигурных скобках команда предписывает PowerShell только искать набор учетных записей, в которых свойство учетной записи пользователя UsageLocation ( ** $ \_ . UsageLocation** ) не указан ( **-EQ $NULL** ).
    
**UsageLocation** — лишь одно из многих свойств, связанных с учетной записью пользователя. Чтобы просмотреть все свойства учетных записей пользователей, используйте командлет **SELECT** и подстановочный знак (*), чтобы отображать их все для конкретной учетной записи пользователя. Пример:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Например, **City** для этого списка — имя свойства, принадлежащего учетной записи пользователя. Это значит, что перечислить все учетные записи пользователей, проживающих в Лондоне, можно с помощью такой команды:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  В приведенных ниже примерах используется синтаксис для командлета **WHERE** **{$ \_ .** [имя свойства учетной записи пользователя] [оператор сравнения] оно **}**. > [оператор сравнения] имеет значение **-EQ** для Equals, **-Ne** для Not Equals, **-lt** для "меньше, чем", "-gt" для "больше чем", " **-gt** " и других.  [Value] как правило, это строка (последовательность букв, цифр и других знаков), числовое значение или **$null** для незаданных> узнать, [где](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) можно получить дополнительные сведения.
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="view-all-accounts"></a>Просмотр всех учетных записей

Чтобы отобразить полный список учетных записей пользователей, выполните следующую команду:
  
```powershell
Get-MsolUser
```

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

Выходные данные должны выглядеть примерно следующим образом:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

У командлета **Get-MsolUser** также есть ряд параметров для фильтрации отображаемых учетных данных. Например, чтобы получить список нелицензированных пользователей (пользователей, добавленных в Microsoft 365, но еще не лицензированных для использования каких-либо служб), выполните указанную ниже команду.
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Выходные данные должны выглядеть примерно следующим образом:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Дополнительные сведения о дополнительных параметрах для фильтрации отображаемого набора учетных записей пользователей приведены в статье [Get – MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Просмотр определенной учетной записи

Чтобы отобразить определенную учетную запись пользователя, введите учетную запись пользователя учетной записи пользователя, которая также называется именем участника-пользователя (UPN), удалите символы "<" и ">", а затем выполните следующую команду:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a>Просмотр некоторых учетных записей на основе общего свойства

Чтобы сделать более избирательным список отображаемых учетных записей, можно использовать командлет **WHERE** в сочетании с командлетом **Get – MsolUser** . Чтобы объединить два командлета, мы используем символ ' ' pipe ' ' | ", который указывает PowerShell на получение результатов одной команды и их отправку в следующую команду. Ниже приведен пример команды, которая выводит только учетные записи, для которых не указано место использования:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
- Получить всю информацию об учетных записях пользователей (**Get-MsolUser**) и передать их в следующую команду (**|**).
    
- Найдите все учетные записи пользователей с незаданной областью использования ( **где {$ \_ . UsageLocation-EQ $Null}** ). В фигурных скобках команда предписывает PowerShell только искать набор учетных записей, в которых свойство учетной записи пользователя UsageLocation ( ** $ \_ . UsageLocation** ) не указан ( **-EQ $NULL** ).
    
Выходные данные должны выглядеть примерно следующим образом:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

**UsageLocation** — лишь одно из многих свойств, связанных с учетной записью пользователя. Чтобы просмотреть все свойства учетных записей пользователей, используйте командлет **SELECT** и подстановочный знак (*), чтобы отображать их все для конкретной учетной записи пользователя. Пример:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Например, **City** для этого списка — имя свойства, принадлежащего учетной записи пользователя. Это значит, что перечислить все учетные записи пользователей, проживающих в Лондоне, можно с помощью такой команды:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  В приведенных ниже примерах используется синтаксис для командлета **WHERE** **{$ \_ .** [имя свойства учетной записи пользователя] [оператор сравнения] оно **}**.  [оператор сравнения] имеет значение **-EQ** для Equals, **-Ne** для Not Equals, **-lt** для "больше чем", " **-gt** " для "больше чем", и других.  [Value] как правило, это строка (последовательность букв, цифр и других знаков), числовое значение или **$null** не указано. Дополнительные [сведения см.](https://technet.microsoft.com/library/hh849715.aspx)
  
Вы можете проверить состояние блокировки учетной записи пользователя с помощью следующей команды:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Просмотр дополнительных значений свойств для учетных записей

Командлет **Get – MsolUser** по умолчанию отображает три свойства учетных записей пользователей:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Если требуются дополнительные свойства, такие как отдел, с которым работает пользователь, и страна или регион, где пользователь использует службы Microsoft 365, можно выполнить командлет **Get-MsolUser** в сочетании с командлетом **SELECT** , чтобы указать список свойств учетной записи пользователя. Вот пример:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
- Получить всю информацию об учетных записях пользователей (**Get-MsolUser**) и передать их в следующую команду (**|**).
    
- Отображение только имени, отдела и места использования учетной записи пользователя ( **выберите DisplayName, Department, UsageLocation** ).
    
Выходные данные должны выглядеть примерно следующим образом:
  
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

Командлет **SELECT** позволяет выбрать свойства, которые должна отображать команда. Чтобы просмотреть все свойства учетных записей пользователей, используйте подстановочный знак (*), чтобы отображать их все для конкретной учетной записи пользователя. Вот пример:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Чтобы сделать более избирательным список учетных записей для отображения, можно также использовать командлет **WHERE** . Ниже приведен пример команды, которая выводит только учетные записи, для которых не указано место использования:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Эта команда предписывает PowerShell выполнить следующие действия:
  
- Получить всю информацию об учетных записях пользователей (**Get-MsolUser**) и передать их в следующую команду (**|**).
    
- Найдите все учетные записи пользователей с незаданной областью использования ( **где {$ \_ . UsageLocation-EQ $Null}** ) и отправьте полученные сведения в следующую команду ( **|** ). В фигурных скобках команда задает PowerShell только для поиска набора учетных записей, в которых свойство учетной записи пользователя UsageLocation ( ** $ \_ . UsageLocation** ) не указан ( **-EQ $NULL** ).
    
- Отображение только имени, отдела и места использования учетной записи пользователя ( **выберите DisplayName, Department, UsageLocation** ).
    
Выходные данные должны выглядеть примерно следующим образом:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Если вы используете синхронизацию службы каталогов для создания пользователей Microsoft 365 и управления ими, вы можете отобразить локальную учетную запись, из которой проецируется пользователь Microsoft 365. В следующем примере предполагается, что служба Azure AD Connect настроена на использование привязки источника по умолчанию ObjectGUID (Дополнительные сведения о настройке привязки источника см. в статье [Azure AD Connect: концепция дизайна](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) и предполагается, что установлен модуль доменных служб Active Directory для PowerShell (см. [инструменты RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)

