---
title: Ведение членства в группе безопасности с помощью PowerShell
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
# <a name="maintain-security-group-membership-with-powershell"></a><span data-ttu-id="fd204-103">Ведение членства в группе безопасности с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd204-103">Maintain security group membership with PowerShell</span></span>

<span data-ttu-id="fd204-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="fd204-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="fd204-105">Вы можете использовать PowerShell для Microsoft 365 в качестве альтернативы центру администрирования Microsoft 365, чтобы управлять членством в группе безопасности в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd204-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain security group membership in Microsoft 365.</span></span> 

>[!Note]
><span data-ttu-id="fd204-106">[Сведения о том, как поддерживать членство в группах microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) с помощью центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fd204-106">[Learn how to maintain Microsoft 365 group membership](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="fd204-107">Список дополнительных ресурсов приведен в разделе [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="fd204-107">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="fd204-108">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="fd204-108">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="fd204-109">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="fd204-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="fd204-110">Добавление и удаление учетных записей пользователей в качестве участников группы</span><span class="sxs-lookup"><span data-stu-id="fd204-110">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="fd204-111">**Чтобы добавить учетную запись пользователя по имени участника** -пользователя, заполните имя участника-пользователя учетной записи пользователя (например: belindan@contoso.com) и отображаемое имя группы безопасности, удалите символы "<" и ">", а затем выполните следующие команды в окне PowerShell или интегрированной среде сценариев POWERSHELL (ISE).</span><span class="sxs-lookup"><span data-stu-id="fd204-111">**To add a user account by its UPN** , fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the security group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="fd204-112">**Чтобы добавить учетную запись пользователя по отображаемому имени** , заполните отображаемое имя учетной записи пользователя (например, Светланы Коноваловой) и отображаемое имя группы, а затем выполните указанные ниже команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd204-112">**To add a user account by its display name** , fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="fd204-113">**Чтобы удалить учетную запись пользователя по имени участника** -пользователя, введите имя участника-пользователя (например: belindan@contoso.com) и отображаемое имя группы, а затем выполните приведенные ниже команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd204-113">**To remove a user account by its UPN** , fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="fd204-114">**Чтобы удалить учетную запись пользователя по отображаемому имени** , заполните отображаемое имя учетной записи пользователя (например, Светланы Коноваловой) и отображаемое имя группы, а затем выполните указанные ниже команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd204-114">**To remove a user account by its display name** , fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="fd204-115">Добавление и удаление групп в качестве участников группы</span><span class="sxs-lookup"><span data-stu-id="fd204-115">Add or remove groups as members of a group</span></span>

<span data-ttu-id="fd204-116">Группы безопасности могут содержать другие группы в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="fd204-116">Security groups can contain other groups as members.</span></span> <span data-ttu-id="fd204-117">Однако группы Microsoft 365 не могут.</span><span class="sxs-lookup"><span data-stu-id="fd204-117">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="fd204-118">В этом разделе содержатся команды PowerShell для добавления или удаления групп только для группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="fd204-118">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="fd204-119">**Чтобы добавить группу по отображаемому имени** , укажите отображаемое имя добавляемой группы и отображаемое имя группы, которая будет содержать группу участников, и выполните следующие команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd204-119">**To add a group by its display name** , fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="fd204-120">**Чтобы удалить группу по отображаемому имени** , укажите отображаемое имя группы, которую нужно удалить, и отображаемое имя группы, которая будет содержать группу участников, и выполните следующие команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd204-120">**To remove a group by its display name** , fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="fd204-121">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd204-121">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="fd204-122">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="fd204-122">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="fd204-123">Добавление и удаление учетных записей пользователей в качестве участников группы</span><span class="sxs-lookup"><span data-stu-id="fd204-123">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="fd204-124">**Чтобы добавить учетную запись пользователя по имени участника** -пользователя, заполните имя участника-пользователя для учетной записи пользователя (например: belindan@contoso.com) и отображаемое имя группы, удалите символы "<" и ">", а затем выполните следующие команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd204-124">**To add a user account by its UPN** , fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="fd204-125">**Чтобы добавить учетную запись пользователя по отображаемому имени** , заполните отображаемое имя учетной записи пользователя (например, Светланы Коноваловой) и отображаемое имя группы, а затем выполните указанные ниже команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd204-125">**To add a user account by its display name** , fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="fd204-126">**Чтобы удалить учетную запись пользователя по имени участника** -пользователя, введите имя участника-пользователя (например: belindan@contoso.com) и отображаемое имя группы, а затем выполните приведенные ниже команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd204-126">**To remove a user account by its UPN** , fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="fd204-127">**Чтобы удалить учетную запись пользователя по отображаемому имени** , заполните отображаемое имя учетной записи пользователя (например, Светланы Коноваловой) и отображаемое имя группы, а затем выполните указанные ниже команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd204-127">**To remove a user account by its display name** , fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="fd204-128">Добавление и удаление групп в качестве участников группы</span><span class="sxs-lookup"><span data-stu-id="fd204-128">Add or remove groups as members of a group</span></span>

<span data-ttu-id="fd204-129">Группы безопасности могут содержать другие группы в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="fd204-129">Security groups can contain other groups as members.</span></span> <span data-ttu-id="fd204-130">Однако группы Microsoft 365 не могут.</span><span class="sxs-lookup"><span data-stu-id="fd204-130">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="fd204-131">В этом разделе содержатся команды PowerShell для добавления или удаления групп только для группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="fd204-131">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="fd204-132">**Чтобы добавить группу по отображаемому имени** , укажите отображаемое имя добавляемой группы и отображаемое имя группы, которая будет содержать группу участников, и выполните следующие команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd204-132">**To add a group by its display name** , fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="fd204-133">**Чтобы удалить группу по отображаемому имени** , укажите отображаемое имя группы, которую нужно удалить, и отображаемое имя группы, которая будет содержать группу участников, и выполните следующие команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd204-133">**To remove a group by its display name** , fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="fd204-134">См. также</span><span class="sxs-lookup"><span data-stu-id="fd204-134">See also</span></span>

[<span data-ttu-id="fd204-135">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd204-135">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fd204-136">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd204-136">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="fd204-137">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fd204-137">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

