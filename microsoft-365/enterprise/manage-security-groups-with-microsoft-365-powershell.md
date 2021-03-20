---
title: Управление группами безопасности с помощью PowerShell
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
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: Узнайте, как использовать PowerShell для управления группами безопасности.
ms.openlocfilehash: 64a02a1472fdeb0d61cfb4f380cbe61dd7b557b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909506"
---
# <a name="manage-security-groups-with-powershell"></a>Управление группами безопасности с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Для управления группами безопасности можно использовать PowerShell для Microsoft 365 в качестве альтернативы центру администрирования Microsoft 365. 

В этой статье описывается перечисление, создание, изменение параметров и удаление групп безопасности. 

Если для командного блока в этой статье требуется указать переменные значения, используйте эти действия.

1. Скопируйте командный блок в буфер обмена данными и вклеите его в блокнот или интегрированную среду скриптов PowerShell (ISE).
2. Заполните переменные значения и удалите символы "<" и ">".
3. Запустите команды в окне PowerShell или ISE PowerShell.

См. [в обзоре Сохранение членства в](maintain-group-membership-with-microsoft-365-powershell.md) группе безопасности для управления членством в группе с Помощью PowerShell.

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="list-your-groups"></a>Список групп

Используйте эту команду, чтобы перечислить все группы.

```powershell
Get-AzureADGroup
```
Используйте эти команды для отображения параметров определенной группы по ее имени.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Создание группы

Используйте эту команду для создания новой группы безопасности.

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>Изменение параметров группы

Отображение параметров группы с помощью этих команд.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Затем используйте [статью Set-AzureADGroup,](/powershell/module/azuread/set-azureadgroup) чтобы определить, как изменить параметр.

### <a name="remove-a-security-group"></a>Удаление группы безопасности

Используйте эти команды, чтобы удалить группу безопасности.

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>Управление владельцами группы безопасности

Используйте эти команды для отображения текущих владельцев группы безопасности.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
Используйте эти команды, чтобы добавить учетную запись пользователя по ее основному имени **пользователя (UPN)** к текущим владельцам группы безопасности.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
Используйте эти команды, чтобы добавить учетную запись пользователя по ее **имени** к текущим владельцам группы безопасности.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
Используйте эти команды, чтобы удалить учетную запись пользователя с помощью **upN** для текущих владельцев группы безопасности.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

Используйте эти команды, чтобы удалить  учетную запись пользователя по ее имени для текущих владельцев группы безопасности.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="list-your-groups"></a>Список групп

Используйте эту команду, чтобы перечислить все группы.

```powershell
Get-MsolGroup
```
Используйте эти команды для отображения параметров определенной группы по ее имени.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Создание группы

Используйте эту команду для создания новой группы безопасности.

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>Изменение параметров группы

Отображение параметров группы с помощью этих команд.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Затем используйте [статью Set-MsolGroup,](/powershell/module/msonline/set-msolgroup) чтобы определить, как изменить параметр.

### <a name="remove-a-security-group"></a>Удаление группы безопасности

Используйте эти команды, чтобы удалить группу безопасности.

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)