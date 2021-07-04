---
title: Просмотр Microsoft 365 учетных записей пользователей с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: Узнайте, как просматривать, перечислять или отображать учетные записи Microsoft 365 различными способами с помощью PowerShell.
ms.openlocfilehash: 77219fb89430ed257ef2a68a7b24bf9ebac715b2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290175"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="5711f-103">Просмотр Microsoft 365 учетных записей пользователей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5711f-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="5711f-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="5711f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5711f-105">Вы можете использовать Центр администрирования Microsoft 365 для просмотра учетных записей для Microsoft 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="5711f-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="5711f-106">PowerShell для Microsoft 365 это позволяет, но также предоставляет дополнительные функции.</span><span class="sxs-lookup"><span data-stu-id="5711f-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="5711f-107">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="5711f-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="5711f-108">[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="5711f-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="5711f-109">Просмотр всех учетных записей</span><span class="sxs-lookup"><span data-stu-id="5711f-109">View all accounts</span></span>

<span data-ttu-id="5711f-110">Чтобы отобразить полный список учетных записей пользователей, запустите эту команду:</span><span class="sxs-lookup"><span data-stu-id="5711f-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="5711f-111">Вы должны получать сведения, аналогичные этому:</span><span class="sxs-lookup"><span data-stu-id="5711f-111">You should get information similar to this:</span></span>
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a><span data-ttu-id="5711f-112">Просмотр определенной учетной записи</span><span class="sxs-lookup"><span data-stu-id="5711f-112">View a specific account</span></span>

<span data-ttu-id="5711f-113">Чтобы отобразить определенную учетную запись пользователя, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="5711f-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="5711f-114">Заполните имя учетной записи пользователя, которая также называется главным именем пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="5711f-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="5711f-115">Удалите символы "<" и ">".</span><span class="sxs-lookup"><span data-stu-id="5711f-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="5711f-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="5711f-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="5711f-117">Просмотр дополнительных значений свойств для определенной учетной записи</span><span class="sxs-lookup"><span data-stu-id="5711f-117">View additional property values for a specific account</span></span>

<span data-ttu-id="5711f-118">По умолчанию в **кодлете Get-AzureADUser** отображаются только свойства учетных записей *ObjectID,* *DisplayName* и *UserPrincipalName.*</span><span class="sxs-lookup"><span data-stu-id="5711f-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="5711f-119">Чтобы быть более выборочными в отображаемом свойстве, используйте комлет **Select** в сочетании с комдлетом **Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="5711f-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="5711f-120">Чтобы объединить два командлета, используйте символ "pipe" ("|"), который сообщает Azure Active Directory PowerShell для Graph, чтобы взять результаты одной команды и отправить ее в следующую команду.</span><span class="sxs-lookup"><span data-stu-id="5711f-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="5711f-121">Вот пример команды, которая отображает *DisplayName,* *Department* и *UseLocation* для каждой учетной записи пользователя:</span><span class="sxs-lookup"><span data-stu-id="5711f-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="5711f-122">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5711f-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="5711f-123">Получите всю информацию о учетных записях пользователей **(Get-AzureADUser)** и отправьте ее в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5711f-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="5711f-124">Отображение только имени учетной записи пользователя, расположения отдела и использования **(Выберите DisplayName, Department, UseLocation).**</span><span class="sxs-lookup"><span data-stu-id="5711f-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="5711f-125">Чтобы увидеть все свойства для определенной учетной записи пользователя, используйте **кодлет Select** и символ под диктовки (\*).</span><span class="sxs-lookup"><span data-stu-id="5711f-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="5711f-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="5711f-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="5711f-127">В другом примере запустите следующую команду, чтобы проверить состояние включенной учетной записи пользователя:</span><span class="sxs-lookup"><span data-stu-id="5711f-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="5711f-128">Просмотр состояния синхронизации учетных записей</span><span class="sxs-lookup"><span data-stu-id="5711f-128">View account synchronization status</span></span>

<span data-ttu-id="5711f-129">Учетные записи пользователей имеют два источника:</span><span class="sxs-lookup"><span data-stu-id="5711f-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="5711f-130">Windows Server Active Directory (AD), которые являются учетные записи, синхронизируются с локальной AD в облако.</span><span class="sxs-lookup"><span data-stu-id="5711f-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="5711f-131">Azure Active Directory (Azure AD) AD-учетные записи, созданные непосредственно в облаке.</span><span class="sxs-lookup"><span data-stu-id="5711f-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="5711f-132">Следующая команда предписывает PowerShell получить всех пользователей с атрибутом *DirSyncEnabled* для *True*.</span><span class="sxs-lookup"><span data-stu-id="5711f-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="5711f-133">Его можно использовать для поиска учетных записей, синхронизируются с локальной AD.</span><span class="sxs-lookup"><span data-stu-id="5711f-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="5711f-134">Следующая команда предписывает PowerShell получить всех пользователей, у которых есть набор *атрибута DirSyncEnabled* к *False*.</span><span class="sxs-lookup"><span data-stu-id="5711f-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="5711f-135">Его можно использовать для поиска учетных записей только для облачных вычислений.</span><span class="sxs-lookup"><span data-stu-id="5711f-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="5711f-136">Просмотр учетных записей на основе общего свойства</span><span class="sxs-lookup"><span data-stu-id="5711f-136">View accounts based on a common property</span></span>

<span data-ttu-id="5711f-137">Чтобы быть более выборочным в списке отображаемой учетной записи, вы можете использовать комлет **Where** в сочетании с комдлетом **Get-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="5711f-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="5711f-138">Чтобы объединить два командлета, используйте символ "pipe" ("|"), который сообщает Azure Active Directory PowerShell для Graph, чтобы взять результаты одной команды и отправить ее в следующую команду.</span><span class="sxs-lookup"><span data-stu-id="5711f-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="5711f-139">Вот пример команды, которая отображает только те учетные записи пользователей, которые имеют неустановленное расположение использования:</span><span class="sxs-lookup"><span data-stu-id="5711f-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="5711f-140">Эта команда Azure Active Directory PowerShell для Graph:</span><span class="sxs-lookup"><span data-stu-id="5711f-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="5711f-141">Получите всю информацию о учетных записях пользователей **(Get-AzureADUser)** и отправьте ее в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5711f-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="5711f-142">Найдите все учетные записи пользователей с неустановленным расположением использования **(Where {$ \_ . UseLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="5711f-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="5711f-143">В скобки команда предписывает PowerShell находить только набор учетных записей, для которых свойству учетной записи пользователя UseLocation (**$ \_ . UseLocation**) не указывается **(-eq $Null).**</span><span class="sxs-lookup"><span data-stu-id="5711f-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="5711f-144">**UsageLocation** — лишь одно из многих свойств, связанных с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="5711f-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="5711f-145">Чтобы отобразить все свойства для определенной учетной записи пользователя, используйте символ **Select** и символ под диктовки (\*).</span><span class="sxs-lookup"><span data-stu-id="5711f-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="5711f-146">Пример:</span><span class="sxs-lookup"><span data-stu-id="5711f-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="5711f-147">Например, **City** — это имя свойства учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="5711f-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="5711f-148">Вы можете использовать следующую команду, чтобы перечислить все учетные записи пользователей, которые живут в Лондоне:</span><span class="sxs-lookup"><span data-stu-id="5711f-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
> <span data-ttu-id="5711f-149">Синтаксис для cmdlet **Where** в этих примерах — **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="5711f-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="5711f-150">[имя свойства учетной записи пользователя] [оператор сравнения] [значение] **}**.> [оператор сравнения] — **это -eq** для равных, **-ne** для не равного, **-lt** для меньшего, **-gt** для большей, чем и другие.</span><span class="sxs-lookup"><span data-stu-id="5711f-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="5711f-151">[значение], как правило, строка (последовательность букв, чисел и других  символов), числовые значения или $Null для неустановленного.</span><span class="sxs-lookup"><span data-stu-id="5711f-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="5711f-152">Дополнительные сведения см. в [дополнительных сведениях.](/powershell/module/microsoft.powershell.core/where-object)</span><span class="sxs-lookup"><span data-stu-id="5711f-152">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="5711f-153">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5711f-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="5711f-154">[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="5711f-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="5711f-155">Просмотр всех учетных записей</span><span class="sxs-lookup"><span data-stu-id="5711f-155">View all accounts</span></span>

<span data-ttu-id="5711f-156">Чтобы отобразить полный список учетных записей пользователей, запустите эту команду:</span><span class="sxs-lookup"><span data-stu-id="5711f-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="5711f-157">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*.</span><span class="sxs-lookup"><span data-stu-id="5711f-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="5711f-158">Эти командлеты требуется запускать из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5711f-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="5711f-159">Вы должны получать сведения, аналогичные этому:</span><span class="sxs-lookup"><span data-stu-id="5711f-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="5711f-160">У командлета **Get-MsolUser** также есть ряд параметров для фильтрации отображаемых учетных данных.</span><span class="sxs-lookup"><span data-stu-id="5711f-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="5711f-161">Например, для списка нелицензионных пользователей (пользователей, которые были добавлены в Microsoft 365, но еще не были лицензированы на использование каких-либо служб), запустите эту команду:</span><span class="sxs-lookup"><span data-stu-id="5711f-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="5711f-162">Вы должны получать сведения, аналогичные этому:</span><span class="sxs-lookup"><span data-stu-id="5711f-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="5711f-163">Сведения о дополнительных параметрах для фильтрации отображаемого набора учетных записей пользователей см. в [get-MsolUser.](/previous-versions/azure/dn194133(v=azure.100))</span><span class="sxs-lookup"><span data-stu-id="5711f-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="5711f-164">Просмотр определенной учетной записи</span><span class="sxs-lookup"><span data-stu-id="5711f-164">View a specific account</span></span>

<span data-ttu-id="5711f-165">Чтобы отобразить определенную учетную запись пользователя, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="5711f-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="5711f-166">Заполните имя входной записи пользователя, которая также называется главным именем пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="5711f-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="5711f-167">Удалите символы "<" и ">".</span><span class="sxs-lookup"><span data-stu-id="5711f-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="5711f-168">Просмотр учетных записей на основе общего свойства</span><span class="sxs-lookup"><span data-stu-id="5711f-168">View accounts based on a common property</span></span>

<span data-ttu-id="5711f-169">Чтобы быть более выборочным в списке отображаемой учетной записи, можно использовать cmdlet **Where** in combination with the **Get-MsolUser** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5711f-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="5711f-170">Чтобы объединить два командлета, используйте символ "pipe" ("|"), который сообщает PowerShell взять результаты одной команды и отправить ее в следующую команду.</span><span class="sxs-lookup"><span data-stu-id="5711f-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="5711f-171">Вот пример, в который отображаются только те учетные записи пользователей, которые имеют неустановленное расположение использования:</span><span class="sxs-lookup"><span data-stu-id="5711f-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="5711f-172">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5711f-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="5711f-173">Получите всю информацию о учетных записях пользователей **(Get-MsolUser)** и отправьте ее в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5711f-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="5711f-174">Найдите все учетные записи пользователей с неустановленным расположением использования **(Where \_ {$. UseLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="5711f-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="5711f-175">В скобки команда предписывает PowerShell находить только набор учетных записей, для которых свойству учетной записи useLocation (**$ \_ . UseLocation**) не указывается **(-eq $Null).**</span><span class="sxs-lookup"><span data-stu-id="5711f-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="5711f-176">Вы должны получать сведения, аналогичные этому:</span><span class="sxs-lookup"><span data-stu-id="5711f-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="5711f-177">*UsageLocation* — лишь одно из многих свойств, связанных с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="5711f-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="5711f-178">Чтобы увидеть все свойства учетных записей пользователей, используйте комлет **Select** и символ под диктовки (\*), чтобы отобразить их все для определенной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="5711f-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="5711f-179">Пример:</span><span class="sxs-lookup"><span data-stu-id="5711f-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="5711f-180">Например, *City* — это имя свойства учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="5711f-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="5711f-181">Вы можете использовать следующую команду, чтобы перечислить все учетные записи пользователей, которые живут в Лондоне:</span><span class="sxs-lookup"><span data-stu-id="5711f-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
> <span data-ttu-id="5711f-182">Синтаксис для cmdlet **Where** в этих примерах — **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="5711f-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="5711f-183">[имя свойства учетной записи пользователя] [оператор сравнения] [значение] **}**.</span><span class="sxs-lookup"><span data-stu-id="5711f-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="5711f-184">[оператор сравнения] **— eq** для равных, **-ne** для не равного, **-lt** для меньшего, **-gt** для большей, чем и другие.</span><span class="sxs-lookup"><span data-stu-id="5711f-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="5711f-185">[значение], как правило, строка (последовательность букв, чисел и других  символов), числовые значения или $Null для неустановленного.</span><span class="sxs-lookup"><span data-stu-id="5711f-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="5711f-186">Дополнительные сведения см. в [дополнительных сведениях.](/powershell/module/microsoft.powershell.core/where-object)</span><span class="sxs-lookup"><span data-stu-id="5711f-186">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object).</span></span>
  
<span data-ttu-id="5711f-187">Чтобы проверить заблокированный статус учетной записи пользователя, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5711f-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="5711f-188">Просмотр дополнительных значений свойств для учетных записей</span><span class="sxs-lookup"><span data-stu-id="5711f-188">View additional property values for accounts</span></span>

<span data-ttu-id="5711f-189">По умолчанию в **комлете Get-MsolUser** отображаются три свойства учетных записей пользователей:</span><span class="sxs-lookup"><span data-stu-id="5711f-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="5711f-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="5711f-190">UserPrincipalName</span></span>

- <span data-ttu-id="5711f-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5711f-191">DisplayName</span></span>

- <span data-ttu-id="5711f-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="5711f-192">isLicensed</span></span>

<span data-ttu-id="5711f-193">Если вам нужны дополнительные свойства, такие как отдел, в котором работает пользователь, и страна/регион, в котором они используют Microsoft 365 службы, можно запустить **Get-MsolUser** в сочетании с помощью cmdlet **Select,** чтобы указать список свойств учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="5711f-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="5711f-194">Пример:</span><span class="sxs-lookup"><span data-stu-id="5711f-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="5711f-195">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5711f-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="5711f-196">Получите все сведения о учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5711f-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="5711f-197">Отображение только имени учетной записи пользователя, расположения отдела и использования **(Выберите DisplayName, Department, UseLocation).**</span><span class="sxs-lookup"><span data-stu-id="5711f-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="5711f-198">Вы должны получать сведения, аналогичные этому:</span><span class="sxs-lookup"><span data-stu-id="5711f-198">You should get information similar to this:</span></span>
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

<span data-ttu-id="5711f-199">В **cmdlet Select** вы можете выбрать, какие свойства отобразить.</span><span class="sxs-lookup"><span data-stu-id="5711f-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="5711f-200">Чтобы отобразить все свойства для определенной учетной записи пользователя, используйте символ под диктовки (\*).</span><span class="sxs-lookup"><span data-stu-id="5711f-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="5711f-201">Пример:</span><span class="sxs-lookup"><span data-stu-id="5711f-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="5711f-202">Чтобы более избирательно использовать список отображаемой учетной записи, можно также использовать cmdlet **Where.**</span><span class="sxs-lookup"><span data-stu-id="5711f-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="5711f-203">Вот пример команды, которая отображает только те учетные записи пользователей, которые имеют неустановленное расположение использования:</span><span class="sxs-lookup"><span data-stu-id="5711f-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="5711f-204">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5711f-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="5711f-205">Получите все сведения о учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5711f-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="5711f-206">Найдите все учетные записи пользователей с неустановленным расположением использования **(Where \_ {$. UseLocation -eq $Null}** и отправка результатов в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="5711f-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="5711f-207">В скобки команда предписывает PowerShell находить только набор учетных записей, для которых свойству учетной записи пользователя UseLocation (**$ \_ . UseLocation**) не указывается **(-eq $Null).**</span><span class="sxs-lookup"><span data-stu-id="5711f-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="5711f-208">Отображение только имени учетной записи пользователя, расположения отдела и использования **(Выберите DisplayName, Department, UseLocation).**</span><span class="sxs-lookup"><span data-stu-id="5711f-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="5711f-209">Вы должны получать сведения, аналогичные этому:</span><span class="sxs-lookup"><span data-stu-id="5711f-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="5711f-210">Если используется синхронизация каталогов для создания и управления Microsoft 365 пользователями, можно отобразить локализованную учетную запись, из которой Microsoft 365 был проецируемый пользователь.</span><span class="sxs-lookup"><span data-stu-id="5711f-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="5711f-211">В следующем примере предполагается, что:</span><span class="sxs-lookup"><span data-stu-id="5711f-211">The following example assumes that:</span></span>

- <span data-ttu-id="5711f-212">Azure AD Подключение настраивается для использования источника по умолчанию якоря ObjectGUID.</span><span class="sxs-lookup"><span data-stu-id="5711f-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="5711f-213">Дополнительные сведения о настройке якоря исходных источников см. в Подключение [Azure AD: Design concepts).](/azure/active-directory/hybrid/plan-connect-design-concepts)</span><span class="sxs-lookup"><span data-stu-id="5711f-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="5711f-214">Установлен модуль служб домена Active Directory для PowerShell (см. [инструменты RSAT).](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)</span><span class="sxs-lookup"><span data-stu-id="5711f-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="5711f-215">См. также</span><span class="sxs-lookup"><span data-stu-id="5711f-215">See also</span></span>

[<span data-ttu-id="5711f-216">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5711f-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5711f-217">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5711f-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5711f-218">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5711f-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)