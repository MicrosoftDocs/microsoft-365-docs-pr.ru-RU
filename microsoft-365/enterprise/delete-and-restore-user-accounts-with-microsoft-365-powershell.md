---
title: Удаление учетных записей пользователей Microsoft 365 с помощью PowerShell
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
- seo-marvel-apr2020
ms.assetid: 209c9868-448c-49bc-baae-11e28b923a39
description: Узнайте, как использовать различные модули в PowerShell для удаления учетных записей пользователей Microsoft 365.
ms.openlocfilehash: 39bf57fe7e7aad1bdc9915e503107ad799515030
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754544"
---
# <a name="delete-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="e1f51-103">Удаление учетных записей пользователей Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1f51-103">Delete Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="e1f51-104">Для удаления и восстановления учетных записей пользователей можно использовать PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1f51-104">You can use PowerShell for Microsoft 365 to delete and restore user accounts.</span></span>

>[!Note]
><span data-ttu-id="e1f51-105">Узнайте, как [восстановить учетную запись пользователя](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) с помощью Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e1f51-105">Learn how to [restore a user account](https://docs.microsoft.com/microsoft-365/admin/add-users/restore-user) by using the Microsoft 365 admin center.</span></span>
>
><span data-ttu-id="e1f51-106">Список дополнительных ресурсов см. в [подсети "Управление пользователями и группами".](https://docs.microsoft.com/microsoft-365/admin/add-users/)</span><span class="sxs-lookup"><span data-stu-id="e1f51-106">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   
   
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e1f51-107">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="e1f51-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e1f51-108">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="e1f51-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="e1f51-109">После подключения используйте следующий синтаксис для удаления отдельной учетной записи пользователя:</span><span class="sxs-lookup"><span data-stu-id="e1f51-109">After you connect, use the following syntax to remove an individual user account:</span></span>
  
```powershell
Remove-AzureADUser -ObjectID <sign-in name>
```

<span data-ttu-id="e1f51-110">В этом примере удаляется имя *fabricec \@ учетной записи litwareinc.com.*</span><span class="sxs-lookup"><span data-stu-id="e1f51-110">This example removes the user account *fabricec\@litwareinc.com*.</span></span>
  
```powershell
Remove-AzureADUser -ObjectID fabricec@litwareinc.com
```

> [!NOTE]
> <span data-ttu-id="e1f51-111">Параметр *-ObjectID* в cmdlet **Remove-AzureADUser** принимает имя для регистрации учетной записи, также известное как имя пользователя или ИД объекта учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e1f51-111">The *-ObjectID* parameter in the **Remove-AzureADUser** cmdlet accepts either the account's sign-in name, also known as the User Principal Name or the account's object ID.</span></span>
  
<span data-ttu-id="e1f51-112">Чтобы отобразить имя учетной записи на основе имени пользователя, используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="e1f51-112">To display the account name based on the user's name, use the following commands:</span></span>
  
```powershell
$userName="<User name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="e1f51-113">В этом примере отображается имя учетной записи пользователя *Caleb Sills.*</span><span class="sxs-lookup"><span data-stu-id="e1f51-113">This example displays the account name for the user *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="e1f51-114">Чтобы удалить учетную запись на основе отображаемого имени пользователя, используйте указанные ниже команды:</span><span class="sxs-lookup"><span data-stu-id="e1f51-114">To remove an account based on the user's display name, use the following commands:</span></span>
  
```powershell
$userName="<display name>"
Remove-AzureADUser -ObjectID (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e1f51-115">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1f51-115">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e1f51-116">При удалении учетной записи пользователя с помощью модуля Microsoft Azure Active Directory для Windows PowerShell она не удаляется окончательно.</span><span class="sxs-lookup"><span data-stu-id="e1f51-116">When you delete a user account through the Microsoft Azure Active Directory Module for Windows PowerShell, the account isn't permanently deleted.</span></span> <span data-ttu-id="e1f51-117">Удаленную учетную запись пользователя можно восстановить в течение 30 дней.</span><span class="sxs-lookup"><span data-stu-id="e1f51-117">You can restore the deleted user account within 30 days.</span></span>

<span data-ttu-id="e1f51-118">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="e1f51-118">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

<span data-ttu-id="e1f51-119">Чтобы удалить учетную запись пользователя, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e1f51-119">To delete a user account, use the following syntax:</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName <sign-in name>
```

>[!Note]
><span data-ttu-id="e1f51-120">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*.</span><span class="sxs-lookup"><span data-stu-id="e1f51-120">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="e1f51-121">Эти командлеты требуется запускать из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1f51-121">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="e1f51-122">В этом примере удаляется учетная *запись BelindaN@litwareinc.com.*</span><span class="sxs-lookup"><span data-stu-id="e1f51-122">This example deletes the user account *BelindaN@litwareinc.com*.</span></span>
  
```powershell
Remove-MsolUser -UserPrincipalName belindan@litwareinc.com
```

<span data-ttu-id="e1f51-123">Чтобы восстановить удаленную учетную запись пользователя в течение 30 дней, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="e1f51-123">To restore a deleted user account within the 30-day grace period, use the following syntax:</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName <sign-in name>
```

<span data-ttu-id="e1f51-124">В этом примере восстанавливается удаленная учетная *запись BelindaN \@ litwareinc.com*.</span><span class="sxs-lookup"><span data-stu-id="e1f51-124">This example restores the deleted account *BelindaN\@litwareinc.com*.</span></span>
  
```powershell
Restore-MsolUser -UserPrincipalName BelindaN@litwareinc.com
```

>[!Note]
> <span data-ttu-id="e1f51-125">Чтобы просмотреть список удаленных пользователей, которых можно восстановить, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e1f51-125">To see the list of deleted users that can be restored, run the following command:</span></span>
>    
> ```powershell
> Get-MsolUser -All -ReturnDeletedUsers
> ```
>
> <span data-ttu-id="e1f51-126">Если исходное имя участника-пользователя используется другой учетной записью, замените _NewUserPrincipalName_ параметром _UserPrincipalName_, чтобы указать другое имя участника-пользователя при восстановлении учетной записи.</span><span class="sxs-lookup"><span data-stu-id="e1f51-126">If the user account's original user principal name is used by another account, use the _NewUserPrincipalName_ parameter instead of _UserPrincipalName_ to specify a different user principal name when you restore the user account.</span></span>


## <a name="see-also"></a><span data-ttu-id="e1f51-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e1f51-127">See also</span></span>

[<span data-ttu-id="e1f51-128">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1f51-128">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e1f51-129">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1f51-129">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e1f51-130">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e1f51-130">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
