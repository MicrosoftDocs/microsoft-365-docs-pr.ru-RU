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
description: Узнайте, как использовать PowerShell для поддержания членства в Microsoft 365 группах.
ms.openlocfilehash: 9696c9093ae6f24a2edaf544e80794bde45d18d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909578"
---
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="4dc2b-103">Сохранение членства в группе безопасности с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4dc2b-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="4dc2b-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="4dc2b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4dc2b-105">Вы можете использовать PowerShell для Microsoft 365 в качестве альтернативы центру администрирования Microsoft 365 для поддержания членства группы безопасности в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="4dc2b-106">[Узнайте, как поддерживать Microsoft 365 в](../admin/create-groups/add-or-remove-members-from-groups.md) центре администрирования Microsoft 365 группы.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-106">[Learn how to maintain Microsoft 365 group membership](../admin/create-groups/add-or-remove-members-from-groups.md) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="4dc2b-107">Список дополнительных ресурсов см. в списке [Управление пользователями и группами.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="4dc2b-107">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="4dc2b-108">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="4dc2b-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="4dc2b-109">[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="4dc2b-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="4dc2b-110">Добавление или удаление учетных записей пользователей в составе группы</span><span class="sxs-lookup"><span data-stu-id="4dc2b-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="4dc2b-111">Чтобы добавить учетную запись пользователя по своей учетной записи, заполните учетную запись пользователя Имя пользователя (UPN) (пример: belindan@contoso.com) и имя отображения группы безопасности, удалив символы "<" и ">" и запустите эти команды в окне PowerShell или в среде интегрированных скриптов PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="4dc2b-111">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4dc2b-112">**Чтобы** добавить учетную запись пользователя по имени отображения, заполните имя отображения учетной записи пользователя (пример: Белинда Ньюман) и имя отображения группы и запустите эти команды в окне PowerShell или ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-112">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4dc2b-113">Чтобы удалить учетную запись пользователя с помощью **upN,** заполните учетную запись пользователя UPN (пример: belindan@contoso.com) и имя отображения группы и запустите эти команды в окне PowerShell или ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-113">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4dc2b-114">**Чтобы удалить** учетную запись пользователя по имени отображения, заполните имя отображения учетной записи пользователя (пример: Белинда Ньюман) и имя отображения группы и запустите эти команды в окне PowerShell или ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-114">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="4dc2b-115">Добавление или удаление групп в качестве членов группы</span><span class="sxs-lookup"><span data-stu-id="4dc2b-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="4dc2b-116">Группы безопасности могут содержать другие группы в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="4dc2b-117">Microsoft 365 группы, однако, не могут.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="4dc2b-118">В этом разделе содержатся команды PowerShell по добавлению или удалению групп только для группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="4dc2b-119">**Чтобы** добавить группу по имени отображения, заполните отображаемое имя группы, которую вы собираетесь добавить, и имя отображения группы, которая будет содержать группу членов и запустит эти команды в окне PowerShell или ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-119">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4dc2b-120">**Чтобы** удалить группу по имени отображения, заполните отображаемое имя группы, которую вы собираетесь удалить, и отображаемое имя группы, которая будет содержать группу членов и запустит эти команды в окне PowerShell или ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-120">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="4dc2b-121">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4dc2b-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="4dc2b-122">[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="4dc2b-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="4dc2b-123">Добавление или удаление учетных записей пользователей в составе группы</span><span class="sxs-lookup"><span data-stu-id="4dc2b-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="4dc2b-124">Чтобы добавить учетную запись пользователя по своей учетной записи, заполните в учетной записи пользователя имя пользователя (UPN) (пример: belindan@contoso.com) и имя отображения группы, удалив символы "<" и ">" и запустите эти команды в окне PowerShell или ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-124">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4dc2b-125">**Чтобы** добавить учетную запись пользователя по имени отображения, заполните имя отображения учетной записи пользователя (пример: Белинда Ньюман) и имя отображения группы и запустите эти команды в окне PowerShell или ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-125">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4dc2b-126">Чтобы удалить учетную запись пользователя с помощью **upN,** заполните учетную запись пользователя UPN (пример: belindan@contoso.com) и имя отображения группы и запустите эти команды в окне PowerShell или ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-126">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="4dc2b-127">**Чтобы удалить** учетную запись пользователя по имени отображения, заполните имя отображения учетной записи пользователя (пример: Белинда Ньюман) и имя отображения группы и запустите эти команды в окне PowerShell или ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-127">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="4dc2b-128">Добавление или удаление групп в качестве членов группы</span><span class="sxs-lookup"><span data-stu-id="4dc2b-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="4dc2b-129">Группы безопасности могут содержать другие группы в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="4dc2b-130">Microsoft 365 группы, однако, не могут.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="4dc2b-131">В этом разделе содержатся команды PowerShell по добавлению или удалению групп только для группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="4dc2b-132">**Чтобы** добавить группу по имени отображения, заполните отображаемое имя группы, которую вы собираетесь добавить, и имя отображения группы, которая будет содержать группу членов и запустит эти команды в окне PowerShell или ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-132">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="4dc2b-133">**Чтобы** удалить группу по имени отображения, заполните отображаемое имя группы, которую вы собираетесь удалить, и отображаемое имя группы, которая будет содержать группу членов и запустит эти команды в окне PowerShell или ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4dc2b-133">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="4dc2b-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4dc2b-134">See also</span></span>

[<span data-ttu-id="4dc2b-135">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4dc2b-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4dc2b-136">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4dc2b-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4dc2b-137">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4dc2b-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)