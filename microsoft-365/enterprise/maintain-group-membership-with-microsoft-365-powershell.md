---
title: Обеспечение членства в группах безопасности с помощью PowerShell
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
ms.openlocfilehash: b47f501c9726e1d4dcb2e9d61108224db0408b8e
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073065"
---
# <a name="maintain-security-group-membership-with-powershell"></a>Обеспечение членства в группах безопасности с помощью PowerShell

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Вы можете использовать PowerShell для Microsoft 365 в качестве альтернативы Центру администрирования Microsoft 365 для поддержки членства в группах безопасности в Microsoft 365. 

>[!Note]
>Узнайте, как поддерживать членство в группах [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) в Центре администрирования Microsoft 365. Список дополнительных ресурсов см. в [подсети "Управление пользователями и группами".](https://docs.microsoft.com/microsoft-365/admin/add-users/)
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Использование модуля PowerShell Azure Active Directory для Graph
Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Добавление или удаление учетных записей пользователей в качестве членов группы

Чтобы добавить учетную запись пользователя по имени ее имени, в окне PowerShell или интегрированной среде сценариев PowerShell или интегрированной среде сценариев PowerShell в окне PowerShell или интегрированной среде сценариев PowerShell укажите символы "<" и ">". belindan@contoso.com

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Чтобы добавить учетную запись пользователя по ее отображаемой **имени,** в заполните отображаемое имя учетной записи пользователя (например, Belinda Newman) и отображаемое имя группы и запустите эти команды в окне PowerShell или ВМЕ PowerShell.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Чтобы удалить учетную запись пользователя по имени ее имени, в заполните имя upN учетной записи пользователя (например: belindan@contoso.com) и отображаемое имя группы и запустите эти команды в окне PowerShell или ВМЕ PowerShell.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Чтобы удалить учетную запись пользователя по ее отображаемой **имени,** в заполните отображаемое имя учетной записи пользователя (например, Belinda Newman) и отображаемое имя группы и запустите эти команды в окне PowerShell или ВМЕ PowerShell.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Добавление или удаление групп в качестве членов группы

Группы безопасности могут содержать другие группы в качестве членов. Однако группы Microsoft 365 не могут. В этом разделе содержатся команды PowerShell для добавления или удаления групп только для группы безопасности.

Чтобы добавить группу по отображаемой **имени,** в заполните отображаемое имя добавляемой группы и отображаемое имя группы, которая будет содержать группу членов, и запустите эти команды в окне PowerShell или ВМЕ PowerShell.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Чтобы удалить группу с помощью отображаемого **имени,** в заполните отображаемое имя удаляемой группы и отображаемое имя группы, которая будет содержать группу членов, и запустите эти команды в окне PowerShell или ВМЕ PowerShell.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Использование модуля Microsoft Azure Active Directory для Windows PowerShell

Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a>Добавление или удаление учетных записей пользователей в качестве членов группы

Чтобы добавить учетную запись пользователя по имени имени **пользователя,** в заполните имя пользователя-пользователя (например, belindan@contoso.com) и отображаемое имя группы, удалив символы "<" и ">" и выполнив эти команды в окне PowerShell или в isE PowerShell.

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Чтобы добавить учетную запись пользователя по ее отображаемой **имени,** в заполните отображаемое имя учетной записи пользователя (например, Belinda Newman) и отображаемое имя группы и запустите эти команды в окне PowerShell или ВМЕ PowerShell.

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Чтобы удалить учетную запись пользователя по имени ее имени, в заполните имя upN учетной записи пользователя (например: belindan@contoso.com) и отображаемое имя группы и запустите эти команды в окне PowerShell или ВМЕ PowerShell.

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

Чтобы удалить учетную запись пользователя по ее отображаемой **имени,** в заполните отображаемое имя учетной записи пользователя (например, Belinda Newman) и отображаемое имя группы и запустите эти команды в окне PowerShell или ВМЕ PowerShell.

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a>Добавление или удаление групп в качестве членов группы

Группы безопасности могут содержать другие группы в качестве членов. Однако группы Microsoft 365 не могут. В этом разделе содержатся команды PowerShell для добавления или удаления групп только для группы безопасности.

Чтобы добавить группу по отображаемой **имени,** в заполните отображаемое имя добавляемой группы и отображаемое имя группы, которая будет содержать группу членов, и запустите эти команды в окне PowerShell или ВМЕ PowerShell.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

Чтобы удалить группу с помощью отображаемого **имени,** в заполните отображаемое имя удаляемой группы и отображаемое имя группы, которая будет содержать группу членов, и запустите эти команды в окне PowerShell или ВМЕ PowerShell.

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a>См. также

[Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Управление Microsoft 365 с помощью PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Начало работы с PowerShell для Microsoft 365](getting-started-with-microsoft-365-powershell.md)

