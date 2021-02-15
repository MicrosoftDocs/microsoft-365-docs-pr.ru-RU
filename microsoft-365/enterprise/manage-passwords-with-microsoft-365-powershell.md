---
title: Управление паролями с помощью PowerShell
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
description: Узнайте, как использовать PowerShell для управления паролями.
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073216"
---
# <a name="manage-passwords-with-powershell"></a><span data-ttu-id="76f6e-103">Управление паролями с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="76f6e-103">Manage passwords with PowerShell</span></span>

<span data-ttu-id="76f6e-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="76f6e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="76f6e-105">Вы можете использовать PowerShell для Microsoft 365 в качестве альтернативы Центру администрирования Microsoft 365 для управления паролями в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76f6e-105">You can use PowerShell for Microsoft 365 as an alternative to the Microsoft 365 admin center to manage passwords in Microsoft 365.</span></span> 

<span data-ttu-id="76f6e-106">Если блоку команд в этой статье требуется указать значения переменных, используйте следующие действия.</span><span class="sxs-lookup"><span data-stu-id="76f6e-106">When a command block in this article requires that you specify variable values, use these steps.</span></span>

1. <span data-ttu-id="76f6e-107">Скопируйте блок команд в буфер обмена и в paste его в Блокнот или интегрированную среду сценариев PowerShell (ISE).</span><span class="sxs-lookup"><span data-stu-id="76f6e-107">Copy the command block to the clipboard and paste it into Notepad or the PowerShell Integrated Script Environment (ISE).</span></span>
2. <span data-ttu-id="76f6e-108">Заполните значения переменных и удалите символы "<" и ">".</span><span class="sxs-lookup"><span data-stu-id="76f6e-108">Fill in the variable values and remove the "<" and ">" characters.</span></span>
3. <span data-ttu-id="76f6e-109">Запустите команды в окне PowerShell или ВМЕ PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76f6e-109">Run the commands in the PowerShell window or the PowerShell ISE.</span></span>

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="76f6e-110">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="76f6e-110">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="76f6e-111">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="76f6e-111">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="76f6e-112">Настройка пароля</span><span class="sxs-lookup"><span data-stu-id="76f6e-112">Set a password</span></span>

<span data-ttu-id="76f6e-113">Используйте эти команды, чтобы указать пароль для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="76f6e-113">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="76f6e-114">Принудительное изменение пароля пользователем</span><span class="sxs-lookup"><span data-stu-id="76f6e-114">Force a user to change their password</span></span>

<span data-ttu-id="76f6e-115">Используйте эти команды, чтобы установить пароль и заставить пользователя изменить новый пароль.</span><span class="sxs-lookup"><span data-stu-id="76f6e-115">Use these commands to set a password and force a user to change their new password.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

<span data-ttu-id="76f6e-116">Используйте эти команды, чтобы установить пароль и заставить пользователя изменить новый пароль при следующем входе.</span><span class="sxs-lookup"><span data-stu-id="76f6e-116">Use these commands to set a password and force a user to change their new password the next time they sign in.</span></span>

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="76f6e-117">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="76f6e-117">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="76f6e-118">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="76f6e-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="set-a-password"></a><span data-ttu-id="76f6e-119">Настройка пароля</span><span class="sxs-lookup"><span data-stu-id="76f6e-119">Set a password</span></span>

<span data-ttu-id="76f6e-120">Используйте эти команды, чтобы указать пароль для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="76f6e-120">Use these commands to specify a password for a user account.</span></span>

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a><span data-ttu-id="76f6e-121">Принудительное изменение пароля пользователем</span><span class="sxs-lookup"><span data-stu-id="76f6e-121">Force a user to change their password</span></span>

<span data-ttu-id="76f6e-122">Используйте эти команды, чтобы заставить пользователя изменить пароль.</span><span class="sxs-lookup"><span data-stu-id="76f6e-122">Use these commands to force a user to change their password.</span></span>

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a><span data-ttu-id="76f6e-123">См. также</span><span class="sxs-lookup"><span data-stu-id="76f6e-123">See also</span></span>

[<span data-ttu-id="76f6e-124">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="76f6e-124">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="76f6e-125">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="76f6e-125">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="76f6e-126">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="76f6e-126">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

