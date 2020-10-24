---
title: Просмотр учетных записей пользователей Microsoft 365 с помощью PowerShell
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
description: Сведения о том, как просматривать, перечислить и отображать учетные записи пользователей Microsoft 365 различными способами с помощью PowerShell.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754076"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="f995d-103">Просмотр учетных записей пользователей Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f995d-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="f995d-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="f995d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f995d-105">Вы можете использовать центр администрирования Microsoft 365 для просмотра учетных записей клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f995d-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="f995d-106">PowerShell для Microsoft 365 включает это, но также предоставляет дополнительные функции.</span><span class="sxs-lookup"><span data-stu-id="f995d-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f995d-107">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="f995d-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f995d-108">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="f995d-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="f995d-109">Просмотр всех учетных записей</span><span class="sxs-lookup"><span data-stu-id="f995d-109">View all accounts</span></span>

<span data-ttu-id="f995d-110">Чтобы отобразить полный список учетных записей пользователей, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f995d-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="f995d-111">Необходимо получить сведения, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="f995d-111">You should get information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="f995d-112">Просмотр определенной учетной записи</span><span class="sxs-lookup"><span data-stu-id="f995d-112">View a specific account</span></span>

<span data-ttu-id="f995d-113">Чтобы отобразить определенную учетную запись пользователя, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="f995d-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="f995d-114">Введите имя учетной записи пользователя, которая также называется именем участника-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="f995d-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="f995d-115">Удалите символы "<" и ">".</span><span class="sxs-lookup"><span data-stu-id="f995d-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="f995d-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="f995d-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="f995d-117">Просмотр дополнительных значений свойств для конкретной учетной записи</span><span class="sxs-lookup"><span data-stu-id="f995d-117">View additional property values for a specific account</span></span>

<span data-ttu-id="f995d-118">По умолчанию командлет **Get – AzureADUser** отображает свойства *ObjectID*, *DisplayName*и *userPrincipalName* для учетных записей.</span><span class="sxs-lookup"><span data-stu-id="f995d-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="f995d-119">Чтобы более избирательно выбирать свойства для отображения, используйте командлет **SELECT** в сочетании с командлетом **Get – AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="f995d-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="f995d-120">Чтобы объединить два командлета, используйте символ "pipe" ("|"), который указывает Azure Active Directory PowerShell для Graph принимать результаты одной команды и отправлять ее в следующую команду.</span><span class="sxs-lookup"><span data-stu-id="f995d-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="f995d-121">Ниже приведен пример команды, которая отображает *DisplayName*, *Department*и *UsageLocation* для каждой учетной записи пользователя:</span><span class="sxs-lookup"><span data-stu-id="f995d-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="f995d-122">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f995d-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="f995d-123">Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f995d-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="f995d-124">Отображение только имени, отдела и места использования учетной записи пользователя (**выберите DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="f995d-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="f995d-125">Чтобы просмотреть все свойства для конкретной учетной записи пользователя, используйте командлет **SELECT** и подстановочный знак (\*).</span><span class="sxs-lookup"><span data-stu-id="f995d-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="f995d-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="f995d-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="f995d-127">В качестве другого примера выполните следующую команду, чтобы проверить включенное состояние конкретной учетной записи пользователя:</span><span class="sxs-lookup"><span data-stu-id="f995d-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="f995d-128">Просмотр состояния синхронизации учетной записи</span><span class="sxs-lookup"><span data-stu-id="f995d-128">View account synchronization status</span></span>

<span data-ttu-id="f995d-129">Учетные записи пользователей имеют два источника:</span><span class="sxs-lookup"><span data-stu-id="f995d-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="f995d-130">Windows Server Active Directory (AD), которая является учетными записями, которые синхронизируют локальную службу AD с облаком.</span><span class="sxs-lookup"><span data-stu-id="f995d-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="f995d-131">Учетные записи Active Directory Azure Active Directory (Azure AD), которые создаются непосредственно в облаке.</span><span class="sxs-lookup"><span data-stu-id="f995d-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="f995d-132">Следующая команда предписывает PowerShell получить всех пользователей, у которых атрибут *дирсинценаблед* имеет значение *true*.</span><span class="sxs-lookup"><span data-stu-id="f995d-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="f995d-133">Его можно использовать для поиска учетных записей, которые синхронизируются из локальной службы AD.</span><span class="sxs-lookup"><span data-stu-id="f995d-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="f995d-134">Следующая команда предписывает PowerShell получить всех пользователей, у которых атрибут *дирсинценаблед* имеет значение *false*.</span><span class="sxs-lookup"><span data-stu-id="f995d-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="f995d-135">С его помощью можно найти учетные записи только для облака.</span><span class="sxs-lookup"><span data-stu-id="f995d-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="f995d-136">Просмотр учетных записей на основе общего свойства</span><span class="sxs-lookup"><span data-stu-id="f995d-136">View accounts based on a common property</span></span>

<span data-ttu-id="f995d-137">Чтобы сделать более избирательным список отображаемых учетных записей, можно использовать командлет **WHERE** в сочетании с командлетом **Get – AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="f995d-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="f995d-138">Чтобы объединить два командлета, используйте символ "pipe" ("|"), который указывает Azure Active Directory PowerShell для Graph принимать результаты одной команды и отправлять ее в следующую команду.</span><span class="sxs-lookup"><span data-stu-id="f995d-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="f995d-139">Ниже приведен пример команды, которая отображает только те учетные записи пользователей с незаданной областью использования:</span><span class="sxs-lookup"><span data-stu-id="f995d-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="f995d-140">Эта команда указывает Azure Active Directory PowerShell для Graph:</span><span class="sxs-lookup"><span data-stu-id="f995d-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="f995d-141">Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f995d-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="f995d-142">Найдите все учетные записи пользователей с незаданной областью использования (**где {$ \_ . UsageLocation-EQ $Null}**).</span><span class="sxs-lookup"><span data-stu-id="f995d-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="f995d-143">В фигурных скобках команда предписывает PowerShell только искать набор учетных записей, для которых свойство учетной записи пользователя UsageLocation (\*\* $ \_ . UsageLocation**) не указан (**-EQ $NULL\*\*).</span><span class="sxs-lookup"><span data-stu-id="f995d-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="f995d-144">**UsageLocation** — лишь одно из многих свойств, связанных с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="f995d-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="f995d-145">Чтобы отобразить все свойства для конкретной учетной записи пользователя, используйте командлет **SELECT** и подстановочный знак (\*).</span><span class="sxs-lookup"><span data-stu-id="f995d-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="f995d-146">Пример:</span><span class="sxs-lookup"><span data-stu-id="f995d-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="f995d-147">Например, **City** — это имя свойства учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="f995d-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="f995d-148">С помощью следующей команды можно получить список всех учетных записей пользователей, проживающих в Лондоне:</span><span class="sxs-lookup"><span data-stu-id="f995d-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="f995d-149">В приведенных ниже примерах используется синтаксис для командлета **WHERE** **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="f995d-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="f995d-150">[имя свойства учетной записи пользователя] [оператор сравнения] оно **}**. > [оператор сравнения] имеет значение **-EQ** для Equals, **-Ne** для Not Equals, **-lt** для "меньше, чем", "-gt" для "больше чем", " **-gt** " и других.</span><span class="sxs-lookup"><span data-stu-id="f995d-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="f995d-151">[Value] как правило, это строка (последовательность букв, цифр и других знаков), числовое значение или **$null** не указано.</span><span class="sxs-lookup"><span data-stu-id="f995d-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="f995d-152">Для получения дополнительных [сведений см.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="f995d-152">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f995d-153">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f995d-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f995d-154">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f995d-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="f995d-155">Просмотр всех учетных записей</span><span class="sxs-lookup"><span data-stu-id="f995d-155">View all accounts</span></span>

<span data-ttu-id="f995d-156">Чтобы отобразить полный список учетных записей пользователей, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f995d-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="f995d-157">Среда PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для модуля Windows PowerShell и командлеты с *MSOL* в имени.</span><span class="sxs-lookup"><span data-stu-id="f995d-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="f995d-158">Выполните эти командлеты в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f995d-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="f995d-159">Необходимо получить сведения, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="f995d-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="f995d-160">У командлета **Get-MsolUser** также есть ряд параметров для фильтрации отображаемых учетных данных.</span><span class="sxs-lookup"><span data-stu-id="f995d-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="f995d-161">Например, для списка нелицензированных пользователей (пользователей, которые были добавлены в Microsoft 365, но еще не лицензированы для использования каких-либо служб) выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f995d-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="f995d-162">Необходимо получить сведения, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="f995d-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="f995d-163">Дополнительные сведения о дополнительных параметрах для фильтрации отображаемого набора учетных записей пользователей приведены в статье [Get – MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="f995d-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="f995d-164">Просмотр определенной учетной записи</span><span class="sxs-lookup"><span data-stu-id="f995d-164">View a specific account</span></span>

<span data-ttu-id="f995d-165">Чтобы отобразить определенную учетную запись пользователя, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="f995d-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="f995d-166">Введите имя для входа учетной записи пользователя, которое также называется именем участника-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="f995d-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="f995d-167">Удалите символы "<" и ">".</span><span class="sxs-lookup"><span data-stu-id="f995d-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="f995d-168">Просмотр учетных записей на основе общего свойства</span><span class="sxs-lookup"><span data-stu-id="f995d-168">View accounts based on a common property</span></span>

<span data-ttu-id="f995d-169">Чтобы сделать более избирательным список отображаемых учетных записей, можно использовать командлет **WHERE** в сочетании с командлетом **Get – MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="f995d-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="f995d-170">Чтобы объединить два командлета, используйте символ "pipe" ("|"), который указывает PowerShell на получение результатов одной команды и их отправку в следующую команду.</span><span class="sxs-lookup"><span data-stu-id="f995d-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="f995d-171">Ниже приведен пример, в котором отображаются только те учетные записи пользователей, для которых не указано неопределенное место использования:</span><span class="sxs-lookup"><span data-stu-id="f995d-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="f995d-172">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f995d-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="f995d-173">Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f995d-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="f995d-174">Поиск всех учетных записей пользователей с незаданной областью использования (**где {$ \_ . UsageLocation-EQ $Null}**).</span><span class="sxs-lookup"><span data-stu-id="f995d-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="f995d-175">В фигурных скобках команда предписывает PowerShell найти только набор учетных записей, для которых свойство учетной записи пользователя UsageLocation (\*\* $ \_ . UsageLocation**) не указан (**-EQ $NULL\*\*).</span><span class="sxs-lookup"><span data-stu-id="f995d-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="f995d-176">Необходимо получить сведения, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="f995d-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="f995d-177">*UsageLocation* — лишь одно из многих свойств, связанных с учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="f995d-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="f995d-178">Чтобы просмотреть все свойства учетных записей пользователей, используйте командлет **SELECT** и подстановочный знак (\*), чтобы отображать их все для конкретной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="f995d-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="f995d-179">Пример:</span><span class="sxs-lookup"><span data-stu-id="f995d-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="f995d-180">Например, *City* — это имя свойства учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="f995d-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="f995d-181">Вы можете использовать следующую команду, чтобы получить список всех учетных записей пользователей для пользователей, проживающих в Лондоне:</span><span class="sxs-lookup"><span data-stu-id="f995d-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="f995d-182">В приведенных ниже примерах используется синтаксис для командлета **WHERE** **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="f995d-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="f995d-183">[имя свойства учетной записи пользователя] [оператор сравнения] оно **}**.</span><span class="sxs-lookup"><span data-stu-id="f995d-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="f995d-184">[оператор сравнения] имеет значение **-EQ** для Equals, **-Ne** для Not Equals, **-lt** для "больше чем", " **-gt** " для "больше чем", и других.</span><span class="sxs-lookup"><span data-stu-id="f995d-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="f995d-185">[Value] как правило, это строка (последовательность букв, цифр и других знаков), числовое значение или **$null** не указано.</span><span class="sxs-lookup"><span data-stu-id="f995d-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="f995d-186">Для получения дополнительных [сведений см.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7)</span><span class="sxs-lookup"><span data-stu-id="f995d-186">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="f995d-187">Чтобы проверить состояние блокировки учетной записи пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f995d-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="f995d-188">Просмотр дополнительных значений свойств для учетных записей</span><span class="sxs-lookup"><span data-stu-id="f995d-188">View additional property values for accounts</span></span>

<span data-ttu-id="f995d-189">По умолчанию командлет **Get – MsolUser** отображает следующие три свойства учетных записей пользователей:</span><span class="sxs-lookup"><span data-stu-id="f995d-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="f995d-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="f995d-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="f995d-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f995d-191">DisplayName</span></span>
    
- <span data-ttu-id="f995d-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="f995d-192">isLicensed</span></span>
    
<span data-ttu-id="f995d-193">Если требуются дополнительные свойства, например отдел, в котором работает пользователь, и страна или регион, где используются службы Microsoft 365, можно выполнить командлет **Get-MsolUser** в сочетании с командлетом **SELECT** , чтобы указать список свойств учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="f995d-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="f995d-194">Пример:</span><span class="sxs-lookup"><span data-stu-id="f995d-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="f995d-195">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f995d-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="f995d-196">Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f995d-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="f995d-197">Отображение только имени, отдела и места использования учетной записи пользователя (**выберите DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="f995d-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="f995d-198">Необходимо получить сведения, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="f995d-198">You should get information similar to this:</span></span>
  
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

<span data-ttu-id="f995d-199">Командлет **SELECT** позволяет выбрать отображаемые свойства.</span><span class="sxs-lookup"><span data-stu-id="f995d-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="f995d-200">Чтобы отобразить все свойства для конкретной учетной записи пользователя, используйте подстановочный знак (\*).</span><span class="sxs-lookup"><span data-stu-id="f995d-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="f995d-201">Пример:</span><span class="sxs-lookup"><span data-stu-id="f995d-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="f995d-202">Чтобы сделать более избирательным список учетных записей для отображения, можно также использовать командлет **WHERE** .</span><span class="sxs-lookup"><span data-stu-id="f995d-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="f995d-203">Ниже приведен пример команды, которая отображает только те учетные записи пользователей с незаданной областью использования:</span><span class="sxs-lookup"><span data-stu-id="f995d-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="f995d-204">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f995d-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="f995d-205">Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f995d-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="f995d-206">Поиск всех учетных записей пользователей с незаданной областью использования (**где {$ \_ . UsageLocation-EQ $Null}**) и отправьте полученные сведения в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="f995d-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="f995d-207">В фигурных скобках команда предписывает PowerShell только искать набор учетных записей, для которых свойство учетной записи пользователя UsageLocation (\*\* $ \_ . UsageLocation**) не указан (**-EQ $NULL\*\*).</span><span class="sxs-lookup"><span data-stu-id="f995d-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="f995d-208">Отображение только имени, отдела и места использования учетной записи пользователя (**выберите DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="f995d-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="f995d-209">Необходимо получить сведения, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="f995d-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="f995d-210">Если вы используете синхронизацию службы каталогов для создания пользователей Microsoft 365 и управления ими, вы можете отобразить локальную учетную запись, из которой проецируется пользователь Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f995d-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="f995d-211">В следующем примере предполагается, что:</span><span class="sxs-lookup"><span data-stu-id="f995d-211">The following example assumes that:</span></span>

- <span data-ttu-id="f995d-212">Служба Azure AD Connect настроена на использование привязки источника по умолчанию ObjectGUID.</span><span class="sxs-lookup"><span data-stu-id="f995d-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="f995d-213">(Дополнительные сведения о настройке привязки источника см. в статье [Azure AD Connect: концепция дизайна](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span><span class="sxs-lookup"><span data-stu-id="f995d-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="f995d-214">Установлен модуль доменных служб Active Directory для PowerShell (см. [инструменты RSAT](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span><span class="sxs-lookup"><span data-stu-id="f995d-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="f995d-215">Дополнительные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="f995d-215">See also</span></span>

[<span data-ttu-id="f995d-216">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f995d-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f995d-217">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f995d-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f995d-218">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f995d-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
