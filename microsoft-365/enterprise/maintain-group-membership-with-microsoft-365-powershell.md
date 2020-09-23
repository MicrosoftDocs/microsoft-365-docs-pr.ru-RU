---
title: Обслуживание членства в группах Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2020
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
ms.openlocfilehash: 464ebcebe87fcd7ce081de85e75acf76cd6d5a46
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235634"
---
# <a name="maintain-microsoft-365-group-membership-with-powershell"></a><span data-ttu-id="ec9ab-103">Обслуживание членства в группах Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec9ab-103">Maintain Microsoft 365 group membership with PowerShell</span></span>

<span data-ttu-id="ec9ab-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="ec9ab-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ec9ab-105">Вы можете использовать PowerShell для Microsoft 365 в качестве альтернативы центру администрирования Microsoft 365 для поддержки членства в группах в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to maintain group membership in Microsoft 365.</span></span> 

> [!TIP]
> <span data-ttu-id="ec9ab-106">Чтобы создать готовые команды PowerShell, указав имена учетных записей пользователей и групп, используйте эту [книгу для обслуживания групп Microsoft Excel](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx).</span><span class="sxs-lookup"><span data-stu-id="ec9ab-106">To generate ready-to-run PowerShell commands by specifying user account and group names, use this [group maintenance Microsoft Excel workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/media/maintain-group-membership-with-microsoft-365-powershell/GroupMaintPowerShellGenerator.xlsx).</span></span> 

>[!Note]
><span data-ttu-id="ec9ab-107">[Сведения о том, как поддерживать членство в группах microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) с помощью центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-107">[Learn how to maintain Microsoft 365 group membership](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="ec9ab-108">Список дополнительных ресурсов приведен в разделе [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="ec9ab-108">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ec9ab-109">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="ec9ab-109">Use the Azure Active Directory PowerShell for Graph module</span></span>
<span data-ttu-id="ec9ab-110">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="ec9ab-110">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="ec9ab-111">Добавление и удаление учетных записей пользователей в качестве участников группы</span><span class="sxs-lookup"><span data-stu-id="ec9ab-111">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="ec9ab-112">**Чтобы добавить учетную запись пользователя по имени участника**-пользователя, заполните имя участника-пользователя для учетной записи пользователя (например: belindan@contoso.com) и отображаемое имя группы, удалите символы "<" и ">", а затем выполните следующие команды в окне PowerShell или интегрированной среде сценариев POWERSHELL (ISE).</span><span class="sxs-lookup"><span data-stu-id="ec9ab-112">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="ec9ab-113">**Чтобы добавить учетную запись пользователя по отображаемому имени**, заполните отображаемое имя учетной записи пользователя (например, Светланы Коноваловой) и отображаемое имя группы, а затем выполните указанные ниже команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-113">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="ec9ab-114">**Чтобы удалить учетную запись пользователя по имени участника**-пользователя, введите имя участника-пользователя (например: belindan@contoso.com) и отображаемое имя группы, а затем выполните приведенные ниже команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-114">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="ec9ab-115">**Чтобы удалить учетную запись пользователя по отображаемому имени**, заполните отображаемое имя учетной записи пользователя (например, Светланы Коноваловой) и отображаемое имя группы, а затем выполните указанные ниже команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-115">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="ec9ab-116">Добавление и удаление групп в качестве участников группы</span><span class="sxs-lookup"><span data-stu-id="ec9ab-116">Add or remove groups as members of a group</span></span>

<span data-ttu-id="ec9ab-117">Группы безопасности могут содержать другие группы в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-117">Security groups can contain other groups as members.</span></span> <span data-ttu-id="ec9ab-118">Однако группы Microsoft 365 не могут.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-118">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="ec9ab-119">В этом разделе содержатся команды PowerShell для добавления или удаления групп только для группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-119">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="ec9ab-120">**Чтобы добавить группу по отображаемому имени**, укажите отображаемое имя добавляемой группы и отображаемое имя группы, которая будет содержать группу участников, и выполните следующие команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-120">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="ec9ab-121">**Чтобы удалить группу по отображаемому имени**, укажите отображаемое имя группы, которую нужно удалить, и отображаемое имя группы, которая будет содержать группу участников, и выполните следующие команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-121">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ec9ab-122">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec9ab-122">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ec9ab-123">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ec9ab-123">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>


### <a name="add-or-remove-user-accounts-as-members-of-a-group"></a><span data-ttu-id="ec9ab-124">Добавление и удаление учетных записей пользователей в качестве участников группы</span><span class="sxs-lookup"><span data-stu-id="ec9ab-124">Add or remove user accounts as members of a group</span></span>

<span data-ttu-id="ec9ab-125">**Чтобы добавить учетную запись пользователя по имени участника**-пользователя, заполните имя участника-пользователя для учетной записи пользователя (например: belindan@contoso.com) и отображаемое имя группы, удалите символы "<" и ">", а затем выполните следующие команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-125">**To add a user account by its UPN**, fill in the user account User Principal Name (UPN) (example: belindan@contoso.com) and the group display name, removing the “<” and “>” characters, and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="ec9ab-126">**Чтобы добавить учетную запись пользователя по отображаемому имени**, заполните отображаемое имя учетной записи пользователя (например, Светланы Коноваловой) и отображаемое имя группы, а затем выполните указанные ниже команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-126">**To add a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to add>"
$groupName="<display name of the group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="ec9ab-127">**Чтобы удалить учетную запись пользователя по имени участника**-пользователя, введите имя участника-пользователя (например: belindan@contoso.com) и отображаемое имя группы, а затем выполните приведенные ниже команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-127">**To remove a user account by its UPN**, fill in the user account UPN (example: belindan@contoso.com) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

<span data-ttu-id="ec9ab-128">**Чтобы удалить учетную запись пользователя по отображаемому имени**, заполните отображаемое имя учетной записи пользователя (например, Светланы Коноваловой) и отображаемое имя группы, а затем выполните указанные ниже команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-128">**To remove a user account by its display name**, fill in the user account display name (example: Belinda Newman) and the group display name and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$userName="<display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolUser | Where { $_.DisplayName -eq $userName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
```

### <a name="add-or-remove-groups-as-members-of-a-group"></a><span data-ttu-id="ec9ab-129">Добавление и удаление групп в качестве участников группы</span><span class="sxs-lookup"><span data-stu-id="ec9ab-129">Add or remove groups as members of a group</span></span>

<span data-ttu-id="ec9ab-130">Группы безопасности могут содержать другие группы в качестве участников.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-130">Security groups can contain other groups as members.</span></span> <span data-ttu-id="ec9ab-131">Однако группы Microsoft 365 не могут.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-131">Microsoft 365 groups, however, cannot.</span></span> <span data-ttu-id="ec9ab-132">В этом разделе содержатся команды PowerShell для добавления или удаления групп только для группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-132">This section contains PowerShell commands to add or remove groups only for a security group.</span></span>

<span data-ttu-id="ec9ab-133">**Чтобы добавить группу по отображаемому имени**, укажите отображаемое имя добавляемой группы и отображаемое имя группы, которая будет содержать группу участников, и выполните следующие команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-133">**To add a group by its display name**, fill in the display name of the group you’re going to add and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group that will contain the member group>"
Add-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

<span data-ttu-id="ec9ab-134">**Чтобы удалить группу по отображаемому имени**, укажите отображаемое имя группы, которую нужно удалить, и отображаемое имя группы, которая будет содержать группу участников, и выполните следующие команды в окне PowerShell или в интегрированной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ec9ab-134">**To remove a group by its display name**, fill in the display name of the group you’re going to remove and the display name of the group that will contain the member group and run these commands in the PowerShell window or the PowerShell ISE.</span></span>

```powershell
$groupMemberName="<display name of the group to add>"
$groupName="<display name of the group contains the member group>"
Remove-MsolGroupMember -GroupMemberObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $groupName }).ObjectID -GroupMemberType Group
```

## <a name="see-also"></a><span data-ttu-id="ec9ab-135">См. также</span><span class="sxs-lookup"><span data-stu-id="ec9ab-135">See also</span></span>

[<span data-ttu-id="ec9ab-136">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec9ab-136">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ec9ab-137">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec9ab-137">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ec9ab-138">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ec9ab-138">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

