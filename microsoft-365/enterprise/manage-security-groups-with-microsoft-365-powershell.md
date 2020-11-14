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
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073229"
---
# <a name="manage-security-groups-with-powershell"></a>Управление группами безопасности с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Вы можете использовать PowerShell для Microsoft 365 в качестве альтернативы центру администрирования Microsoft 365 для управления группами безопасности. 

В этой статье описывается листинг, создание, изменение параметров и удаление групп безопасности. 

Если в этой статье блок команд требует указать значения переменных, выполните указанные ниже действия.

1. Скопируйте блок команд в буфер обмена и вставьте его в Блокнот или интегрированную среду сценариев PowerShell (ISE).
2. Заполните значения переменных и удалите символы "<" и ">".
3. Выполните команды в окне PowerShell или в ИНТЕГРИРОВАНной среде выполнения PowerShell.

Чтобы управлять членством в группах с помощью PowerShell, ознакомьтесь со статьей управление [членством в группе безопасности](maintain-group-membership-with-microsoft-365-powershell.md) .

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).

### <a name="list-your-groups"></a>Список ваших групп

Используйте эту команду, чтобы получить список всех групп.

```powershell
Get-AzureADGroup
```
Используйте эти команды для отображения параметров определенной группы по отображаемому имени.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Создание группы

Используйте эту команду, чтобы создать новую группу безопасности.

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>Изменение параметров группы

Отображение параметров группы с помощью следующих команд.

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Затем используйте статью [Set – азуреадграуп](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) , чтобы определить, как изменить параметр.

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
Используйте эти команды для добавления учетной записи пользователя с помощью **имени участника-пользователя (UPN)** к текущим владельцам группы безопасности.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
Используйте эти команды, чтобы добавить учетную запись пользователя по **отображаемому имени** текущим владельцам группы безопасности.

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
Используйте эти команды, чтобы удалить учетную запись пользователя с помощью **имени участника** -пользователя для текущих владельцев группы безопасности.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

Используйте эти команды, чтобы удалить учетную запись пользователя по **отображаемому имени** текущим владельцам группы безопасности.

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="list-your-groups"></a>Список ваших групп

Используйте эту команду, чтобы получить список всех групп.

```powershell
Get-MsolGroup
```
Используйте эти команды для отображения параметров определенной группы по отображаемому имени.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>Создание группы

Используйте эту команду, чтобы создать новую группу безопасности.

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>Изменение параметров группы

Отображение параметров группы с помощью следующих команд.

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

Затем используйте статью [Set – мсолграуп](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) , чтобы определить, как изменить параметр.

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

