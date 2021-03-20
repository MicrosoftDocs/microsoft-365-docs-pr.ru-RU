---
title: Сохранение членства в группе безопасности с помощью PowerShell
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
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Узнайте, как использовать PowerShell для поддержания членства в группах Microsoft 365.
ms.openlocfilehash: 9696c9093ae6f24a2edaf544e80794bde45d18d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909578"
---
# <a name="maintain-security-group-membership-with-powershell"></a>Сохранение членства в группе безопасности с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Вы можете использовать PowerShell для Microsoft 365 в качестве альтернативы центру администрирования Microsoft 365 для поддержания членства группы безопасности в Microsoft 365. 

>[!Note]
>[Узнайте, как поддерживать членство в группе Microsoft 365](../admin/create-groups/add-or-remove-members-from-groups.md) в центре администрирования Microsoft 365. Список дополнительных ресурсов см. в списке [Управление пользователями и группами.](../admin/add-users/index.yml)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph
[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Добавление или удаление учетных записей пользователей в составе группы

Чтобы добавить учетную запись пользователя по своей учетной записи, заполните учетную запись пользователя Имя пользователя (UPN) (пример: belindan@contoso.com) и имя отображения группы безопасности, удалив символы "<" и ">" и запустите эти команды в окне PowerShell или в среде интегрированных скриптов PowerShell (ISE).

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Чтобы** добавить учетную запись пользователя по имени отображения, заполните имя отображения учетной записи пользователя (пример: Белинда Ньюман) и имя отображения группы и запустите эти команды в окне PowerShell или ISE PowerShell.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Чтобы удалить учетную запись пользователя с помощью **upN,** заполните учетную запись пользователя UPN (пример: belindan@contoso.com) и имя отображения группы и запустите эти команды в окне PowerShell или ISE PowerShell.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Чтобы удалить** учетную запись пользователя по имени отображения, заполните имя отображения учетной записи пользователя (пример: Белинда Ньюман) и имя отображения группы и запустите эти команды в окне PowerShell или ISE PowerShell.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Добавление или удаление групп в качестве членов группы

Группы безопасности могут содержать другие группы в качестве участников. Однако группы Microsoft 365 не могут. В этом разделе содержатся команды PowerShell по добавлению или удалению групп только для группы безопасности.

**Чтобы** добавить группу по имени отображения, заполните отображаемое имя группы, которую вы собираетесь добавить, и имя отображения группы, которая будет содержать группу членов и запустит эти команды в окне PowerShell или ISE PowerShell.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Чтобы** удалить группу по имени отображения, заполните отображаемое имя группы, которую вы собираетесь удалить, и отображаемое имя группы, которая будет содержать группу членов и запустит эти команды в окне PowerShell или ISE PowerShell.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Добавление или удаление учетных записей пользователей в составе группы

Чтобы добавить учетную запись пользователя по своей учетной записи, заполните в учетной записи пользователя имя пользователя (UPN) (пример: belindan@contoso.com) и имя отображения группы, удалив символы "<" и ">" и запустите эти команды в окне PowerShell или ISE PowerShell.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Чтобы** добавить учетную запись пользователя по имени отображения, заполните имя отображения учетной записи пользователя (пример: Белинда Ньюман) и имя отображения группы и запустите эти команды в окне PowerShell или ISE PowerShell.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Чтобы удалить учетную запись пользователя с помощью **upN,** заполните учетную запись пользователя UPN (пример: belindan@contoso.com) и имя отображения группы и запустите эти команды в окне PowerShell или ISE PowerShell.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

**Чтобы удалить** учетную запись пользователя по имени отображения, заполните имя отображения учетной записи пользователя (пример: Белинда Ньюман) и имя отображения группы и запустите эти команды в окне PowerShell или ISE PowerShell.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Добавление или удаление групп в качестве членов группы

Группы безопасности могут содержать другие группы в качестве участников. Однако группы Microsoft 365 не могут. В этом разделе содержатся команды PowerShell по добавлению или удалению групп только для группы безопасности.

**Чтобы** добавить группу по имени отображения, заполните отображаемое имя группы, которую вы собираетесь добавить, и имя отображения группы, которая будет содержать группу членов и запустит эти команды в окне PowerShell или ISE PowerShell.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

**Чтобы** удалить группу по имени отображения, заполните отображаемое имя группы, которую вы собираетесь удалить, и отображаемое имя группы, которая будет содержать группу членов и запустит эти команды в окне PowerShell или ISE PowerShell.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)