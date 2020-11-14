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
# <a name="manage-security-groups-with-powershell"></a><span data-ttu-id="b7548-103">Управление группами безопасности с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7548-103">Manage security groups with PowerShell</span></span>

<span data-ttu-id="b7548-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="b7548-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b7548-105">Вы можете использовать PowerShell для Microsoft 365 в качестве альтернативы центру администрирования Microsoft 365 для управления группами безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7548-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage security groups.</span></span> 

<span data-ttu-id="b7548-106">В этой статье описывается листинг, создание, изменение параметров и удаление групп безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7548-106">This article describes listing, creating, changing settings, and removing security groups.</span></span> 

<span data-ttu-id="b7548-107">Если в этой статье блок команд требует указать значения переменных, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b7548-107">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="b7548-108">Скопируйте блок команд в буфер обмена и вставьте его в Блокнот или интегрированную среду сценариев PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="b7548-108">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="b7548-109">Заполните значения переменных и удалите символы "<" и ">".</span><span class="sxs-lookup"><span data-stu-id="b7548-109">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="b7548-110">Выполните команды в окне PowerShell или в ИНТЕГРИРОВАНной среде выполнения PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7548-110">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

<span data-ttu-id="b7548-111">Чтобы управлять членством в группах с помощью PowerShell, ознакомьтесь со статьей управление [членством в группе безопасности](maintain-group-membership-with-microsoft-365-powershell.md) .</span><span class="sxs-lookup"><span data-stu-id="b7548-111">See [Maintain security group membership](maintain-group-membership-with-microsoft-365-powershell.md) to manage group membership with PowerShell.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b7548-112">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="b7548-112">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="b7548-113">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="b7548-113">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="b7548-114">Список ваших групп</span><span class="sxs-lookup"><span data-stu-id="b7548-114">List your groups</span></span>

<span data-ttu-id="b7548-115">Используйте эту команду, чтобы получить список всех групп.</span><span class="sxs-lookup"><span data-stu-id="b7548-115">Use this command to list all of your groups.</span></span>

```powershell
Get-AzureADGroup
```
<span data-ttu-id="b7548-116">Используйте эти команды для отображения параметров определенной группы по отображаемому имени.</span><span class="sxs-lookup"><span data-stu-id="b7548-116">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="b7548-117">Создание группы</span><span class="sxs-lookup"><span data-stu-id="b7548-117">Create a new group</span></span>

<span data-ttu-id="b7548-118">Используйте эту команду, чтобы создать новую группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7548-118">Use this command to create a new security group.</span></span>

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="b7548-119">Изменение параметров группы</span><span class="sxs-lookup"><span data-stu-id="b7548-119">Change the settings on a group</span></span>

<span data-ttu-id="b7548-120">Отображение параметров группы с помощью следующих команд.</span><span class="sxs-lookup"><span data-stu-id="b7548-120">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="b7548-121">Затем используйте статью [Set – азуреадграуп](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) , чтобы определить, как изменить параметр.</span><span class="sxs-lookup"><span data-stu-id="b7548-121">Then, use the [Set-AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="b7548-122">Удаление группы безопасности</span><span class="sxs-lookup"><span data-stu-id="b7548-122">Remove a security group</span></span>

<span data-ttu-id="b7548-123">Используйте эти команды, чтобы удалить группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7548-123">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a><span data-ttu-id="b7548-124">Управление владельцами группы безопасности</span><span class="sxs-lookup"><span data-stu-id="b7548-124">Manage the owners of a security group</span></span>

<span data-ttu-id="b7548-125">Используйте эти команды для отображения текущих владельцев группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7548-125">Use these commands to display the current owners of a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
<span data-ttu-id="b7548-126">Используйте эти команды для добавления учетной записи пользователя с помощью **имени участника-пользователя (UPN)** к текущим владельцам группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7548-126">Use these commands to add a user account by its **user principal name (UPN)** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
<span data-ttu-id="b7548-127">Используйте эти команды, чтобы добавить учетную запись пользователя по **отображаемому имени** текущим владельцам группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7548-127">Use these commands to add a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
<span data-ttu-id="b7548-128">Используйте эти команды, чтобы удалить учетную запись пользователя с помощью **имени участника** -пользователя для текущих владельцев группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7548-128">Use these commands to remove a user account by its **UPN** to the current owners of a security group.</span></span>

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

<span data-ttu-id="b7548-129">Используйте эти команды, чтобы удалить учетную запись пользователя по **отображаемому имени** текущим владельцам группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7548-129">Use these commands to remove a user account by its **display name** to the current owners of a security group.</span></span>

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="b7548-130">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7548-130">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="b7548-131">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b7548-131">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="list-your-groups"></a><span data-ttu-id="b7548-132">Список ваших групп</span><span class="sxs-lookup"><span data-stu-id="b7548-132">List your groups</span></span>

<span data-ttu-id="b7548-133">Используйте эту команду, чтобы получить список всех групп.</span><span class="sxs-lookup"><span data-stu-id="b7548-133">Use this command to list all of your groups.</span></span>

```powershell
Get-MsolGroup
```
<span data-ttu-id="b7548-134">Используйте эти команды для отображения параметров определенной группы по отображаемому имени.</span><span class="sxs-lookup"><span data-stu-id="b7548-134">Use these commands to display the settings of a specific group by its display name.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a><span data-ttu-id="b7548-135">Создание группы</span><span class="sxs-lookup"><span data-stu-id="b7548-135">Create a new group</span></span>

<span data-ttu-id="b7548-136">Используйте эту команду, чтобы создать новую группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7548-136">Use this command to create a new security group.</span></span>

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a><span data-ttu-id="b7548-137">Изменение параметров группы</span><span class="sxs-lookup"><span data-stu-id="b7548-137">Change the settings on a group</span></span>

<span data-ttu-id="b7548-138">Отображение параметров группы с помощью следующих команд.</span><span class="sxs-lookup"><span data-stu-id="b7548-138">Display the settings of the group with these commands.</span></span>

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

<span data-ttu-id="b7548-139">Затем используйте статью [Set – мсолграуп](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) , чтобы определить, как изменить параметр.</span><span class="sxs-lookup"><span data-stu-id="b7548-139">Then, use the [Set-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) article to determine how to change a setting.</span></span>

### <a name="remove-a-security-group"></a><span data-ttu-id="b7548-140">Удаление группы безопасности</span><span class="sxs-lookup"><span data-stu-id="b7548-140">Remove a security group</span></span>

<span data-ttu-id="b7548-141">Используйте эти команды, чтобы удалить группу безопасности.</span><span class="sxs-lookup"><span data-stu-id="b7548-141">Use these commands to remove a security group.</span></span>

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a><span data-ttu-id="b7548-142">См. также</span><span class="sxs-lookup"><span data-stu-id="b7548-142">See also</span></span>

[<span data-ttu-id="b7548-143">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7548-143">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b7548-144">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7548-144">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b7548-145">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7548-145">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

