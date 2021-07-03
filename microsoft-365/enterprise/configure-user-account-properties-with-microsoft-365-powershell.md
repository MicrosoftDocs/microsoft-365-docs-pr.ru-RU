---
title: Настройка свойств Microsoft 365 учетных записей пользователей с помощью PowerShell
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
- O365ITProTrain
- Ent_Office_Other
- PowerShell
ms.assetid: 30813f8d-b08d-444b-98c1-53df7c29b4d7
description: Используйте PowerShell для Microsoft 365 для настройки свойств отдельных или нескольких учетных записей пользователей в Microsoft 365 клиента.
ms.openlocfilehash: aeb9b586c42a0bdfb8d69b8d297998fedc1124e6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286013"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="c51e1-103">Настройка свойств Microsoft 365 учетных записей пользователей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c51e1-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="c51e1-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="c51e1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c51e1-105">Вы можете использовать Центр администрирования Microsoft 365 для настройки свойств для учетных записей пользователей Microsoft 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="c51e1-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="c51e1-106">В PowerShell вы также можете сделать это, а также некоторые другие вещи, которые вы не можете сделать в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="c51e1-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c51e1-107">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="c51e1-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c51e1-108">Чтобы настроить свойства для учетных записей пользователей в Azure Active Directory PowerShell для Graph модуля, используйте командлет [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser) и укажите свойства для настройки или изменения.</span><span class="sxs-lookup"><span data-stu-id="c51e1-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](/powershell/module/azuread/set-azureaduser) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="c51e1-109">[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="c51e1-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="c51e1-110">Изменение свойств учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="c51e1-110">Change properties for a specific user account</span></span>

<span data-ttu-id="c51e1-111">Вы определяете учетную запись с *параметром -ObjectID* и задаете или измените конкретные свойства с помощью дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="c51e1-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="c51e1-112">Вот список наиболее распространенных параметров:</span><span class="sxs-lookup"><span data-stu-id="c51e1-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="c51e1-113">-Department "<название отдела>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-113">-Department "\<department name>"</span></span>

- <span data-ttu-id="c51e1-114">-DisplayName "<полное имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-114">-DisplayName "\<full user name>"</span></span>

- <span data-ttu-id="c51e1-115">-FacsimilieTelephoneNumber "<номер факса>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>

- <span data-ttu-id="c51e1-116">-GivenName "<имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-116">-GivenName "\<user first name>"</span></span>

- <span data-ttu-id="c51e1-117">-Surname "<фамилия пользователя>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-117">-Surname "\<user last name>"</span></span>

- <span data-ttu-id="c51e1-118">-Mobile "<номер мобильного телефона>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-118">-Mobile "\<mobile phone number>"</span></span>

- <span data-ttu-id="c51e1-119">-JobTitle "<должность>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-119">-JobTitle "\<job title>"</span></span>

- <span data-ttu-id="c51e1-120">-PreferredLanguage "<язык>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-120">-PreferredLanguage "\<language>"</span></span>

- <span data-ttu-id="c51e1-121">-StreetAddress "<почтовый адрес>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-121">-StreetAddress "\<street address>"</span></span>

- <span data-ttu-id="c51e1-122">-City "<название города>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-122">-City "\<city name>"</span></span>

- <span data-ttu-id="c51e1-123">-State "<название региона>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-123">-State "\<state name>"</span></span>

- <span data-ttu-id="c51e1-124">-PostalCode "<почтовый индекс>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-124">-PostalCode "\<postal code>"</span></span>

- <span data-ttu-id="c51e1-125">-Country "<название страны>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-125">-Country "\<country name>"</span></span>

- <span data-ttu-id="c51e1-126">-TelephoneNumber "<номер рабочего телефона>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-126">-TelephoneNumber "\<office phone number>"</span></span>

- <span data-ttu-id="c51e1-127">-UseLocation \<2-character country or region code> " "</span><span class="sxs-lookup"><span data-stu-id="c51e1-127">-UsageLocation "\<2-character country or region code>"</span></span>

    <span data-ttu-id="c51e1-128">Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="c51e1-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>

<span data-ttu-id="c51e1-129">Дополнительные параметры см. [в видеоролике Set-AzureADUser.](/powershell/module/azuread/set-azureaduser)</span><span class="sxs-lookup"><span data-stu-id="c51e1-129">For additional parameters, see [Set-AzureADUser](/powershell/module/azuread/set-azureaduser).</span></span>

> [!NOTE]
> <span data-ttu-id="c51e1-130">Прежде чем назначить лицензии учетной записи пользователя, необходимо назначить расположение использования.</span><span class="sxs-lookup"><span data-stu-id="c51e1-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>

<span data-ttu-id="c51e1-131">Чтобы отобразить имя участника-пользователя для учетных записей пользователей, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="c51e1-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="c51e1-132">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c51e1-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="c51e1-133">Получите всю информацию о учетных записях пользователей **(Get-AzureADUser)** и отправьте ее в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="c51e1-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="c51e1-134">Сортировать список имен основных пользователей в алфавитном порядке **(Sort UserPrincipalName)** и отправить его в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="c51e1-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="c51e1-135">Отобразить только свойство Имя пользователя для каждой учетной записи **(Выберите UserPrincipalName).**</span><span class="sxs-lookup"><span data-stu-id="c51e1-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="c51e1-136">Отобразить их на одном экране (**More**).</span><span class="sxs-lookup"><span data-stu-id="c51e1-136">Display them one screen at a time (**More**).</span></span>

<span data-ttu-id="c51e1-137">Чтобы отобразить имя пользователя для учетной записи на основе ее имени отображения (имя и фамилия), запустите следующие команды.</span><span class="sxs-lookup"><span data-stu-id="c51e1-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="c51e1-138">Заполните *переменную $userName* и удалите \< and > символы:</span><span class="sxs-lookup"><span data-stu-id="c51e1-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="c51e1-139">В этом примере отображается основное имя пользователя для учетной записи пользователя с отображаемой именем *Caleb Sills.*</span><span class="sxs-lookup"><span data-stu-id="c51e1-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="c51e1-140">С помощью переменной *$upn* можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен.</span><span class="sxs-lookup"><span data-stu-id="c51e1-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="c51e1-141">Вот пример, который задает расположение использования *Белинда Ньюман* во Францию.</span><span class="sxs-lookup"><span data-stu-id="c51e1-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="c51e1-142">Но в нем указывается ее имя отображения, а не ее имя пользователя:</span><span class="sxs-lookup"><span data-stu-id="c51e1-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="c51e1-143">Изменение свойств для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="c51e1-143">Change properties for all user accounts</span></span>

<span data-ttu-id="c51e1-144">Чтобы изменить свойства для всех пользователей, можно использовать комбинацию комбинирований **Get-AzureADUser** и **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="c51e1-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="c51e1-145">В следующем примере изменяется расположение использования для всех пользователей во *Франции:*</span><span class="sxs-lookup"><span data-stu-id="c51e1-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="c51e1-146">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c51e1-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="c51e1-147">Получите всю информацию об учетных записях пользователей **(Get-AzureADUser)** и отправьте ее в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="c51e1-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="c51e1-148">Установите расположение пользователя во Франции **(Set-AzureADUser-UseLocation "FR").**</span><span class="sxs-lookup"><span data-stu-id="c51e1-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="c51e1-149">Изменение свойств для определенного набора учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="c51e1-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="c51e1-150">Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать комбинацию комбинеатов **Get-AzureADUser**, **Where** и **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="c51e1-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="c51e1-151">В следующем примере изменяется расположение использования для всех пользователей в отделе бухгалтерского учета *во Францию:*</span><span class="sxs-lookup"><span data-stu-id="c51e1-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="c51e1-152">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c51e1-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="c51e1-153">Получите всю информацию о учетных записях пользователей **(Get-AzureADUser)** и отправьте ее в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="c51e1-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>

1.  <span data-ttu-id="c51e1-154">Найдите все учетные записи пользователей, которые имеют свойство *Department* с набором "Учет"**(Where {$_). Department -eq "Accounting"}** и отправьте в следующую команду **|** ().</span><span class="sxs-lookup"><span data-stu-id="c51e1-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>

1. <span data-ttu-id="c51e1-155">Установите расположение пользователя во Франции **(Set-AzureADUser-UseLocation "FR").**</span><span class="sxs-lookup"><span data-stu-id="c51e1-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="c51e1-156">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c51e1-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="c51e1-157">Чтобы настроить свойства для учетных записей пользователей с помощью модуля Microsoft Azure Active Directory для Windows PowerShell, используйте командлет **Set-MsolUser** и укажите свойства для настройки или изменения.</span><span class="sxs-lookup"><span data-stu-id="c51e1-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="c51e1-158">[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="c51e1-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c51e1-159">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*.</span><span class="sxs-lookup"><span data-stu-id="c51e1-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="c51e1-160">Эти командлеты требуется запускать из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c51e1-160">Run these cmdlets from Windows PowerShell.</span></span>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="c51e1-161">Изменение свойств учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="c51e1-161">Change properties for a specific user account</span></span>

<span data-ttu-id="c51e1-162">Чтобы настроить свойства для определенной учетной записи пользователя, используйте комлет [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) и укажите свойства для настройки или изменения.</span><span class="sxs-lookup"><span data-stu-id="c51e1-162">To configure properties for a specific user account, use the [**Set-MsolUser**](/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="c51e1-163">Вы определяете учетную запись с параметром *-UserPrincipalName* и задате или измените конкретные свойства с помощью дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="c51e1-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="c51e1-164">Вот список наиболее распространенных параметров.</span><span class="sxs-lookup"><span data-stu-id="c51e1-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="c51e1-165">-City "<название города>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-165">-City "\<city name>"</span></span>

- <span data-ttu-id="c51e1-166">-Country "<название страны>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-166">-Country "\<country name>"</span></span>

- <span data-ttu-id="c51e1-167">-Department "<название отдела>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-167">-Department "\<department name>"</span></span>

- <span data-ttu-id="c51e1-168">-DisplayName "<полное имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-168">-DisplayName "\<full user name>"</span></span>

- <span data-ttu-id="c51e1-169">-Fax "<номер факса>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-169">-Fax "\<fax number>"</span></span>

- <span data-ttu-id="c51e1-170">-FirstName "<имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-170">-FirstName "\<user first name>"</span></span>

- <span data-ttu-id="c51e1-171">-LastName "<фамилия пользователя>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-171">-LastName "\<user last name>"</span></span>

- <span data-ttu-id="c51e1-172">-MobilePhone "<номер мобильного телефона>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-172">-MobilePhone "\<mobile phone number>"</span></span>

- <span data-ttu-id="c51e1-173">-Office "<расположение офиса>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-173">-Office "\<office location>"</span></span>

- <span data-ttu-id="c51e1-174">-PhoneNumber "<номер телефона офиса>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-174">-PhoneNumber "\<office phone number>"</span></span>

- <span data-ttu-id="c51e1-175">-PostalCode "<почтовый индекс>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-175">-PostalCode "\<postal code>"</span></span>

- <span data-ttu-id="c51e1-176">-PreferredLanguage "<язык>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-176">-PreferredLanguage "\<language>"</span></span>

- <span data-ttu-id="c51e1-177">-State "<название региона>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-177">-State "\<state name>"</span></span>

- <span data-ttu-id="c51e1-178">-StreetAddress "<почтовый адрес>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-178">-StreetAddress "\<street address>"</span></span>

- <span data-ttu-id="c51e1-179">-Title "<должность>"</span><span class="sxs-lookup"><span data-stu-id="c51e1-179">-Title "\<title name>"</span></span>

- <span data-ttu-id="c51e1-180">-UseLocation \<2-character country or region code> " "</span><span class="sxs-lookup"><span data-stu-id="c51e1-180">-UsageLocation "\<2-character country or region code>"</span></span>

    <span data-ttu-id="c51e1-181">Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="c51e1-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>

<span data-ttu-id="c51e1-182">Дополнительные параметры см. [в рублях Set-MsolUser.](/previous-versions/azure/dn194136(v=azure.100))</span><span class="sxs-lookup"><span data-stu-id="c51e1-182">For additional parameters, see [Set-MsolUser](/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="c51e1-183">Чтобы увидеть главные имена пользователей всех пользователей, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c51e1-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="c51e1-184">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c51e1-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="c51e1-185">Получите всю информацию для учетных записей пользователей **(Get-MsolUser)** и отправьте ее в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="c51e1-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="c51e1-186">Сортировать список имен основных пользователей в алфавитном порядке **(Sort UserPrincipalName)** и отправить его в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="c51e1-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="c51e1-187">Отобразить только свойство Имя пользователя для каждой учетной записи **(Выберите UserPrincipalName).**</span><span class="sxs-lookup"><span data-stu-id="c51e1-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="c51e1-188">Отобразить их на одном экране (**More**).</span><span class="sxs-lookup"><span data-stu-id="c51e1-188">Display them one screen at a time (**More**).</span></span>

<span data-ttu-id="c51e1-189">Чтобы отобразить имя пользователя для учетной записи на основе ее имени отображения (имя и фамилия), запустите следующие команды.</span><span class="sxs-lookup"><span data-stu-id="c51e1-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="c51e1-190">Заполните *переменную $userName* и удалите \< and > символы.</span><span class="sxs-lookup"><span data-stu-id="c51e1-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="c51e1-191">В этом примере отображается имя пользователя с именем Caleb Sills:</span><span class="sxs-lookup"><span data-stu-id="c51e1-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="c51e1-192">С помощью переменной *$upn* можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен.</span><span class="sxs-lookup"><span data-stu-id="c51e1-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="c51e1-193">Вот пример, который задает расположение использования Белинда Ньюман во Францию, но указывает ее имя отображения, а не ее имя пользователя:</span><span class="sxs-lookup"><span data-stu-id="c51e1-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="c51e1-194">Изменение свойств для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="c51e1-194">Change properties for all user accounts</span></span>

<span data-ttu-id="c51e1-195">Чтобы изменить свойства для всех пользователей, используйте комбинацию комбинирований **Get-MsolUser** и **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="c51e1-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="c51e1-196">В следующем примере изменяется расположение использования для всех пользователей во *Франции:*</span><span class="sxs-lookup"><span data-stu-id="c51e1-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="c51e1-197">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c51e1-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="c51e1-198">Получите всю информацию для учетных записей пользователей **(Get-MsolUser)** и отправьте ее в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="c51e1-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="c51e1-199">Установите расположение пользователя во Франции **(Set-MsolUser-UseLocation "FR").**</span><span class="sxs-lookup"><span data-stu-id="c51e1-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="c51e1-200">Изменение свойств для определенного набора учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="c51e1-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="c51e1-201">Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать комбинацию cmdlets **Get-MsolUser**, **Where** и **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="c51e1-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="c51e1-202">В следующем примере изменяется расположение использования для всех пользователей в отделе бухгалтерского учета *во Францию:*</span><span class="sxs-lookup"><span data-stu-id="c51e1-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="c51e1-203">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c51e1-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="c51e1-204">Получите всю информацию для учетных записей пользователей **(Get-MsolUser)** и отправьте ее в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="c51e1-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>

1. <span data-ttu-id="c51e1-205">Найдите все учетные записи пользователей, которые имеют свойство *Department* с набором "Учет"**(Where {$_). Department -eq "Accounting"}** и отправьте выдаваемую информацию в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="c51e1-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>

1. <span data-ttu-id="c51e1-206">Установите расположение пользователя во Франции **(Set-MsolUser-UseLocation "FR").**</span><span class="sxs-lookup"><span data-stu-id="c51e1-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="c51e1-207">См. также</span><span class="sxs-lookup"><span data-stu-id="c51e1-207">See also</span></span>

[<span data-ttu-id="c51e1-208">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c51e1-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c51e1-209">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c51e1-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="c51e1-210">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c51e1-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
