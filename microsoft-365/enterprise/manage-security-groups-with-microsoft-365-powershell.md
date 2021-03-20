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
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="f9615-103">Управление группами безопасности с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9615-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="f9615-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="f9615-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f9615-105">Для управления группами безопасности можно использовать PowerShell для Microsoft 365 в качестве альтернативы центру администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f9615-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="f9615-106">В этой статье описывается перечисление, создание, изменение параметров и удаление групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9615-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="f9615-107">Если для командного блока в этой статье требуется указать переменные значения, используйте эти действия.</span><span class="sxs-lookup"><span data-stu-id="f9615-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="f9615-108">Скопируйте командный блок в буфер обмена данными и вклеите его в блокнот или интегрированную среду скриптов PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="f9615-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="f9615-109">Заполните переменные значения и удалите символы "<" и ">".</span><span class="sxs-lookup"><span data-stu-id="f9615-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="f9615-110">Запустите команды в окне PowerShell или ISE PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9615-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="f9615-111">См. [в обзоре Сохранение членства в](maintain-group-membership-with-microsoft-365-powershell.md) группе безопасности для управления членством в группе с Помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9615-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f9615-112">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="f9615-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f9615-113">[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="f9615-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="f9615-114">Список групп</span><span class="sxs-lookup"><span data-stu-id="f9615-114">List your groups</span></span>

<span data-ttu-id="f9615-115">Используйте эту команду, чтобы перечислить все группы.</span><span class="sxs-lookup"><span data-stu-id="f9615-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="f9615-116">Используйте эти команды для отображения параметров определенной группы по ее имени.</span><span class="sxs-lookup"><span data-stu-id="f9615-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="f9615-117">Создание группы</span><span class="sxs-lookup"><span data-stu-id="f9615-117">Create a new group</span></span>

<span data-ttu-id="f9615-118">Используйте эту команду для создания новой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9615-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="f9615-119">Изменение параметров группы</span><span class="sxs-lookup"><span data-stu-id="f9615-119">Change the settings on a group</span></span>

<span data-ttu-id="f9615-120">Отображение параметров группы с помощью этих команд.</span><span class="sxs-lookup"><span data-stu-id="f9615-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="f9615-121">Затем используйте [статью Set-AzureADGroup,](/powershell/module/azuread/set-azureadgroup) чтобы определить, как изменить параметр.</span><span class="sxs-lookup"><span data-stu-id="f9615-121">Then, use the [Set-AzureADGroup](/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="f9615-122">Удаление группы безопасности</span><span class="sxs-lookup"><span data-stu-id="f9615-122">Remove a security group</span></span>

<span data-ttu-id="f9615-123">Используйте эти команды, чтобы удалить группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9615-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="f9615-124">Управление владельцами группы безопасности</span><span class="sxs-lookup"><span data-stu-id="f9615-124">Manage the owners of a security group</span></span>

<span data-ttu-id="f9615-125">Используйте эти команды для отображения текущих владельцев группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9615-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="f9615-126">Используйте эти команды, чтобы добавить учетную запись пользователя по ее основному имени **пользователя (UPN)** к текущим владельцам группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9615-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="f9615-127">Используйте эти команды, чтобы добавить учетную запись пользователя по ее **имени** к текущим владельцам группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9615-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="f9615-128">Используйте эти команды, чтобы удалить учетную запись пользователя с помощью **upN** для текущих владельцев группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9615-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="f9615-129">Используйте эти команды, чтобы удалить  учетную запись пользователя по ее имени для текущих владельцев группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9615-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f9615-130">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9615-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f9615-131">[Во-первых, подключите клиента Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="f9615-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="f9615-132">Список групп</span><span class="sxs-lookup"><span data-stu-id="f9615-132">List your groups</span></span>

<span data-ttu-id="f9615-133">Используйте эту команду, чтобы перечислить все группы.</span><span class="sxs-lookup"><span data-stu-id="f9615-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="f9615-134">Используйте эти команды для отображения параметров определенной группы по ее имени.</span><span class="sxs-lookup"><span data-stu-id="f9615-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="f9615-135">Создание группы</span><span class="sxs-lookup"><span data-stu-id="f9615-135">Create a new group</span></span>

<span data-ttu-id="f9615-136">Используйте эту команду для создания новой группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9615-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="f9615-137">Изменение параметров группы</span><span class="sxs-lookup"><span data-stu-id="f9615-137">Change the settings on a group</span></span>

<span data-ttu-id="f9615-138">Отображение параметров группы с помощью этих команд.</span><span class="sxs-lookup"><span data-stu-id="f9615-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="f9615-139">Затем используйте [статью Set-MsolGroup,](/powershell/module/msonline/set-msolgroup) чтобы определить, как изменить параметр.</span><span class="sxs-lookup"><span data-stu-id="f9615-139">Then, use the [Set-MsolGroup](/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="f9615-140">Удаление группы безопасности</span><span class="sxs-lookup"><span data-stu-id="f9615-140">Remove a security group</span></span>

<span data-ttu-id="f9615-141">Используйте эти команды, чтобы удалить группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9615-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="f9615-142">См. также</span><span class="sxs-lookup"><span data-stu-id="f9615-142">See also</span></span>

[<span data-ttu-id="f9615-143">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9615-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f9615-144">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9615-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f9615-145">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f9615-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)