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
description: Узнайте, как просматривать, перечислять или отображать учетные записи пользователей Microsoft 365 различными способами с помощью PowerShell.
ms.openlocfilehash: de91195afeb8480bf231d9536e4b3a94502a6da1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924652"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Просмотр учетных записей пользователей Microsoft 365 с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Вы можете использовать центр администрирования Microsoft 365 для просмотра учетных записей клиента Microsoft 365. PowerShell для Microsoft 365 включает это, но также предоставляет дополнительные функции.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  
### <a name="view-all-accounts"></a>Просмотр всех учетных записей

Чтобы отобразить полный список учетных записей пользователей, запустите эту команду:
  
```powershell
Get-AzureADUser
```

Вы должны получать сведения, аналогичные этому:
  
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

Чтобы отобразить определенную учетную запись пользователя, запустите следующую команду. Заполните имя учетной записи пользователя, которая также называется главным именем пользователя (UPN). Удалите символы "<" и ">".
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Пример:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Просмотр дополнительных значений свойств для определенной учетной записи

По умолчанию в **кодлете Get-AzureADUser** отображаются только свойства учетных записей *ObjectID,* *DisplayName* и *UserPrincipalName.*

Чтобы быть более выборочными в отображаемом свойстве, используйте комлет **Select** в сочетании с комдлетом **Get-AzureADUser.** Чтобы объединить два командлета, используйте символ "pipe" ("|"), который сообщает Azure Active Directory PowerShell для Graph, чтобы получить результаты одной команды и отправить ее в следующую команду. Вот пример команды, которая отображает *DisplayName,* *Department* и *UseLocation* для каждой учетной записи пользователя:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Эта команда предписывает PowerShell:
  
1. Получите всю информацию о учетных записях пользователей **(Get-AzureADUser)** и отправьте ее в следующую команду ( **|** ).
    
1.  Отображение только имени учетной записи пользователя, расположения отдела и использования **(Выберите DisplayName, Department, UseLocation).**
  
Чтобы увидеть все свойства для определенной учетной записи пользователя, используйте **кодлет Select** и символ под диктовки (*). Пример:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

В другом примере запустите следующую команду, чтобы проверить состояние включенной учетной записи пользователя:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Просмотр состояния синхронизации учетных записей

Учетные записи пользователей имеют два источника: 

- Windows Server Active Directory (AD), это учетные записи, синхронизируются с локальной AD в облако.

- Учетные записи Azure Active Directory (Azure AD), созданные непосредственно в облаке.


Следующая команда предписывает PowerShell получить всех пользователей с атрибутом *DirSyncEnabled* для *True*. Его можно использовать для поиска учетных записей, синхронизируются с локальной AD.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

Следующая команда предписывает PowerShell получить всех пользователей, у которых есть набор *атрибута DirSyncEnabled* к *False*. Его можно использовать для поиска учетных записей только для облачных вычислений.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Просмотр учетных записей на основе общего свойства

Чтобы быть более выборочным в списке отображаемой учетной записи, вы можете использовать комлет **Where** в сочетании с комдлетом **Get-AzureADUser.** Чтобы объединить два командлета, используйте символ "pipe" ("|"), который сообщает Azure Active Directory PowerShell для Graph, чтобы получить результаты одной команды и отправить ее в следующую команду. Вот пример команды, которая отображает только те учетные записи пользователей, которые имеют неустановленное расположение использования:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Эта команда предписывает Azure Active Directory PowerShell для Graph:
  
1. Получите всю информацию о учетных записях пользователей **(Get-AzureADUser)** и отправьте ее в следующую команду ( **|** ).
    
1. Найдите все учетные записи пользователей с неустановленным расположением использования **(Where {$ \_ . UseLocation -eq $Null}**). В скобки команда предписывает PowerShell находить только набор учетных записей, для которых свойству учетной записи пользователя UseLocation (**$ \_ . UseLocation**) не указывается **(-eq $Null).**
    
**UsageLocation** — лишь одно из многих свойств, связанных с учетной записью пользователя. Чтобы отобразить все свойства для определенной учетной записи пользователя, используйте символ **Select** и символ под диктовки (*). Пример:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Например, **City** — это имя свойства учетной записи пользователя. Вы можете использовать следующую команду, чтобы перечислить все учетные записи пользователей, которые живут в Лондоне:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Синтаксис для cmdlet **Where** в этих примерах — **Where {$ \_ .** [имя свойства учетной записи пользователя] [оператор сравнения] [значение] **}**.> [оператор сравнения] — **это -eq** для равных, **-ne** для не равного, **-lt** для меньшего, **-gt** для большей, чем и другие.  [значение], как правило, строка (последовательность букв, чисел и других  символов), числовые значения или $Null для неустановленного. Дополнительные сведения см. в [дополнительных сведениях.](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="view-all-accounts"></a>Просмотр всех учетных записей

Чтобы отобразить полный список учетных записей пользователей, запустите эту команду:
  
```powershell
Get-MsolUser
```

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*. Эти командлеты требуется запускать из Windows PowerShell.
>

Вы должны получать сведения, аналогичные этому:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

У командлета **Get-MsolUser** также есть ряд параметров для фильтрации отображаемых учетных данных. Например, для списка нелицензионных пользователей (пользователей, которые были добавлены в Microsoft 365, но еще не были лицензированы на использование каких-либо служб), запустите эту команду:
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Вы должны получать сведения, аналогичные этому:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Сведения о дополнительных параметрах для фильтрации отображаемого набора учетных записей пользователей см. в [get-MsolUser.](/previous-versions/azure/dn194133(v=azure.100))
  
### <a name="view-a-specific-account"></a>Просмотр определенной учетной записи

Чтобы отобразить определенную учетную запись пользователя, запустите следующую команду. Заполните имя входной записи пользователя, которая также называется главным именем пользователя (UPN). Удалите символы "<" и ">".
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Просмотр учетных записей на основе общего свойства

Чтобы быть более выборочным в списке отображаемой учетной записи, можно использовать cmdlet **Where** in combination with the **Get-MsolUser** cmdlet. Чтобы объединить два командлета, используйте символ "pipe" ("|"), который сообщает PowerShell взять результаты одной команды и отправить ее в следующую команду. Вот пример, в который отображаются только те учетные записи пользователей, которые имеют неустановленное расположение использования:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Эта команда предписывает PowerShell:
  
1. Получите всю информацию о учетных записях пользователей **(Get-MsolUser)** и отправьте ее в следующую команду ( **|** ).
    
1. Найдите все учетные записи пользователей с неустановленным расположением использования **(Where \_ {$. UseLocation -eq $Null}**). В скобки команда предписывает PowerShell находить только набор учетных записей, для которых свойству учетной записи useLocation (**$ \_ . UseLocation**) не указывается **(-eq $Null).**
    
Вы должны получать сведения, аналогичные этому:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

*UsageLocation* — лишь одно из многих свойств, связанных с учетной записью пользователя. Чтобы увидеть все свойства учетных записей пользователей, используйте комлет **Select** и символ под диктовки (*), чтобы отобразить их все для определенной учетной записи пользователя. Пример:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Например, *City* — это имя свойства учетной записи пользователя. Вы можете использовать следующую команду, чтобы перечислить все учетные записи пользователей, которые живут в Лондоне:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Синтаксис для cmdlet **Where** в этих примерах — **Where {$ \_ .** [имя свойства учетной записи пользователя] [оператор сравнения] [значение] **}**.  [оператор сравнения] **— eq** для равных, **-ne** для не равного, **-lt** для меньшего, **-gt** для большей, чем и другие.  [значение], как правило, строка (последовательность букв, чисел и других  символов), числовые значения или $Null для неустановленного. Дополнительные сведения см. в [дополнительных сведениях.](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)
  
Чтобы проверить заблокированный статус учетной записи пользователя, используйте следующую команду:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Просмотр дополнительных значений свойств для учетных записей

По умолчанию в **комлете Get-MsolUser** отображаются три свойства учетных записей пользователей:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Если вам нужны дополнительные свойства, такие как отдел, в котором работает пользователь, и страна/регион, где они используют службы Microsoft 365, вы можете запустить **Get-MsolUser** в сочетании с cmdlet **Select,** чтобы указать список свойств учетных записей пользователей. Пример:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Эта команда предписывает PowerShell:
  
1. Получите все сведения о учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).
    
1. Отображение только имени учетной записи пользователя, расположения отдела и использования **(Выберите DisplayName, Department, UseLocation).**
    
Вы должны получать сведения, аналогичные этому:
  
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

В **cmdlet Select** вы можете выбрать, какие свойства отобразить. Чтобы отобразить все свойства для определенной учетной записи пользователя, используйте символ под диктовки (*). Пример:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Чтобы более избирательно использовать список отображаемой учетной записи, можно также использовать cmdlet **Where.** Вот пример команды, которая отображает только те учетные записи пользователей, которые имеют неустановленное расположение использования:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Эта команда предписывает PowerShell:
  
1. Получите все сведения о учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).
    
1. Найдите все учетные записи пользователей с неустановленным расположением использования **(Where \_ {$. UseLocation -eq $Null}** и отправка результатов в следующую команду ( **|** ). В скобки команда предписывает PowerShell находить только набор учетных записей, для которых свойству учетной записи пользователя UseLocation (**$ \_ . UseLocation**) не указывается **(-eq $Null).**
    
1. Отображение только имени учетной записи пользователя, расположения отдела и использования **(Выберите DisplayName, Department, UseLocation).**
    
Вы должны получать сведения, аналогичные этому:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Если для создания и управления пользователями Microsoft 365 используется синхронизация каталогов, можно отобразить локализованную учетную запись, с которой был проецируемый пользователь Microsoft 365. В следующем примере предполагается, что:

- Azure AD Connect настроен для использования якоря источника objectGUID по умолчанию. (Дополнительные сведения о настройке источника якоря см. в [странице Azure AD Connect: Design concepts).](/azure/active-directory/hybrid/plan-connect-design-concepts)
- Установлен модуль служб домена Active Directory для PowerShell (см. [инструменты RSAT).](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)