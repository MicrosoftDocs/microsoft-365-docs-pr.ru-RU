---
title: Настройка свойств учетной записи пользователя Microsoft 365 с помощью PowerShell
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
description: Используйте PowerShell для Microsoft 365, чтобы настроить свойства отдельных или нескольких учетных записей пользователей в клиенте Microsoft 365.
ms.openlocfilehash: 830cede93a6c14db2dcc5626d41d0dd296b9ac29
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754332"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="29ecc-103">Настройка свойств учетной записи пользователя Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="29ecc-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="29ecc-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="29ecc-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="29ecc-105">Центр администрирования Microsoft 365 можно использовать для настройки свойств учетных записей пользователей клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="29ecc-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="29ecc-106">В PowerShell это также можно сделать, а также некоторые другие вещи, которые нельзя сделать в Центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="29ecc-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="29ecc-107">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="29ecc-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="29ecc-108">Чтобы настроить свойства учетных записей пользователей в модуле Azure Active Directory PowerShell для Graph, используйте командлет [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) и укажите свойства, которые необходимо задать или изменить.</span><span class="sxs-lookup"><span data-stu-id="29ecc-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="29ecc-109">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="29ecc-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="29ecc-110">Изменение свойств учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="29ecc-110">Change properties for a specific user account</span></span>

<span data-ttu-id="29ecc-111">Учетная запись идентифицируется с помощью параметра *-ObjectID* и заданы или изменяются определенные свойства с помощью дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="29ecc-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="29ecc-112">Вот список наиболее распространенных параметров:</span><span class="sxs-lookup"><span data-stu-id="29ecc-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="29ecc-113">-Department "<название отдела>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="29ecc-114">-DisplayName "<полное имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="29ecc-115">-FacsimilieTelephoneNumber "<номер факса>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="29ecc-116">-GivenName "<имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="29ecc-117">-Surname "<фамилия пользователя>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="29ecc-118">-Mobile "<номер мобильного телефона>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="29ecc-119">-JobTitle "<должность>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="29ecc-120">-PreferredLanguage "<язык>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="29ecc-121">-StreetAddress "<почтовый адрес>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="29ecc-122">-City "<название города>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="29ecc-123">-State "<название региона>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="29ecc-124">-PostalCode "<почтовый индекс>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="29ecc-125">-Country "<название страны>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="29ecc-126">-TelephoneNumber "<номер рабочего телефона>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="29ecc-127">-UsageLocation \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="29ecc-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="29ecc-128">Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="29ecc-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="29ecc-129">Дополнительные параметры [см. в подстройке Set-AzureADUser.](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="29ecc-129">For additional parameters, see [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="29ecc-130">Прежде чем назначать лицензии учетной записи пользователя, необходимо назначить место использования.</span><span class="sxs-lookup"><span data-stu-id="29ecc-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="29ecc-131">Чтобы отобразить имя участника-пользователя для учетных записей пользователей, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="29ecc-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="29ecc-132">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="29ecc-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="29ecc-133">Получите все сведения об учетных записях пользователей **(Get-AzureADUser)** и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="29ecc-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="29ecc-134">Сортировка списка имен участников-пользователей в алфавитном порядке (**Sort UserPrincipalName)** и отправка его в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="29ecc-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="29ecc-135">Отображает только свойство user Principal Name для каждой учетной записи (**Select UserPrincipalName).**</span><span class="sxs-lookup"><span data-stu-id="29ecc-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="29ecc-136">Отобразить их на одном экране (**More**).</span><span class="sxs-lookup"><span data-stu-id="29ecc-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="29ecc-137">Чтобы отобразить имя основного пользователя для учетной записи на основе ее отображаемой имени (имени и фамилии), запустите следующие команды.</span><span class="sxs-lookup"><span data-stu-id="29ecc-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="29ecc-138">Заполните *переменную $userName* и удалите \< and > символы:</span><span class="sxs-lookup"><span data-stu-id="29ecc-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="29ecc-139">В этом примере отображается имя пользователя-пользователя для учетной записи пользователя с отображаемой именем *Caleb Sills.*</span><span class="sxs-lookup"><span data-stu-id="29ecc-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="29ecc-140">С помощью переменной *$upn* можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен.</span><span class="sxs-lookup"><span data-stu-id="29ecc-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="29ecc-141">Вот пример, в качестве расположения использования для *Belinda Newman* задав францию.</span><span class="sxs-lookup"><span data-stu-id="29ecc-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="29ecc-142">Но в нем указывается ее отображаемая имя, а не имя основного пользователя:</span><span class="sxs-lookup"><span data-stu-id="29ecc-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="29ecc-143">Изменение свойств для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="29ecc-143">Change properties for all user accounts</span></span>

<span data-ttu-id="29ecc-144">Чтобы изменить свойства для всех пользователей, можно использовать сочетание **get-AzureADUser** и **set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="29ecc-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="29ecc-145">В следующем примере расположение использования для всех пользователей изменяется на *Францию:*</span><span class="sxs-lookup"><span data-stu-id="29ecc-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="29ecc-146">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="29ecc-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="29ecc-147">Получите все сведения об учетных записях пользователей **(Get-AzureADUser)** и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="29ecc-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="29ecc-148">Установите расположение пользователя для Франции (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="29ecc-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="29ecc-149">Изменение свойств для определенного набора учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="29ecc-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="29ecc-150">Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать сочетание с помощью cmdlets **Get-AzureADUser**, **Where** и **Set-AzureADUser.**</span><span class="sxs-lookup"><span data-stu-id="29ecc-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="29ecc-151">В следующем примере расположение использования для всех пользователей в бухгалтерии изменяется на *Францию:*</span><span class="sxs-lookup"><span data-stu-id="29ecc-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="29ecc-152">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="29ecc-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="29ecc-153">Получите все сведения об учетных записях пользователей **(Get-AzureADUser)** и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="29ecc-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="29ecc-154">Найдите все учетные записи пользователей, свойство *Department* которых имеет свойство Accounting **(Где {$_). Department -eq "Accounting"}**) и отправьте итоговые сведения в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="29ecc-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="29ecc-155">Установите расположение пользователя для Франции (**Set-AzureADUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="29ecc-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="29ecc-156">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29ecc-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="29ecc-157">Чтобы настроить свойства учетных записей пользователей с помощью модуля Microsoft Azure Active Directory для Windows PowerShell, используйте командлет **Set-MsolUser** и укажите свойства, которые необходимо задать или изменить.</span><span class="sxs-lookup"><span data-stu-id="29ecc-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="29ecc-158">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="29ecc-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="29ecc-159">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*.</span><span class="sxs-lookup"><span data-stu-id="29ecc-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="29ecc-160">Эти командлеты требуется запускать из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ecc-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="29ecc-161">Изменение свойств учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="29ecc-161">Change properties for a specific user account</span></span>

<span data-ttu-id="29ecc-162">Чтобы настроить свойства для определенной учетной записи пользователя, используйте cmdlet [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) и укажите свойства, которые необходимо задать или изменить.</span><span class="sxs-lookup"><span data-stu-id="29ecc-162">To configure properties for a specific user account, use the [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="29ecc-163">Учетная запись идентифицируется с помощью параметра *-UserPrincipalName* и заданы или изменяются определенные свойства с помощью дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="29ecc-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="29ecc-164">Вот список наиболее распространенных параметров.</span><span class="sxs-lookup"><span data-stu-id="29ecc-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="29ecc-165">-City "<название города>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="29ecc-166">-Country "<название страны>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="29ecc-167">-Department "<название отдела>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="29ecc-168">-DisplayName "<полное имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="29ecc-169">-Fax "<номер факса>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="29ecc-170">-FirstName "<имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="29ecc-171">-LastName "<фамилия пользователя>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="29ecc-172">-MobilePhone "<номер мобильного телефона>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="29ecc-173">-Office "<расположение офиса>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="29ecc-174">-PhoneNumber "<номер телефона офиса>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="29ecc-175">-PostalCode "<почтовый индекс>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="29ecc-176">-PreferredLanguage "<язык>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="29ecc-177">-State "<название региона>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="29ecc-178">-StreetAddress "<почтовый адрес>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="29ecc-179">-Title "<должность>"</span><span class="sxs-lookup"><span data-stu-id="29ecc-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="29ecc-180">-UsageLocation \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="29ecc-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="29ecc-181">Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="29ecc-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="29ecc-182">Дополнительные параметры [см. в подстроке Set-MsolUser.](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100))</span><span class="sxs-lookup"><span data-stu-id="29ecc-182">For additional parameters, see [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="29ecc-183">Чтобы увидеть имена участников-пользователей всех пользователей, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="29ecc-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="29ecc-184">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="29ecc-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="29ecc-185">Получите все сведения об учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="29ecc-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="29ecc-186">Сортировка списка имен участников-пользователей в алфавитном порядке (**Sort UserPrincipalName)** и отправка его в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="29ecc-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="29ecc-187">Отображает только свойство user Principal Name для каждой учетной записи (**Select UserPrincipalName).**</span><span class="sxs-lookup"><span data-stu-id="29ecc-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="29ecc-188">Отобразить их на одном экране (**More**).</span><span class="sxs-lookup"><span data-stu-id="29ecc-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="29ecc-189">Чтобы отобразить имя основного пользователя для учетной записи на основе ее отображаемой имени (имени и фамилии), запустите следующие команды.</span><span class="sxs-lookup"><span data-stu-id="29ecc-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="29ecc-190">Заполните *переменную $userName* и удалите \< and > символы.</span><span class="sxs-lookup"><span data-stu-id="29ecc-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="29ecc-191">В этом примере отображается имя пользователя с именем Caleb Sills:</span><span class="sxs-lookup"><span data-stu-id="29ecc-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="29ecc-192">С помощью переменной *$upn* можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен.</span><span class="sxs-lookup"><span data-stu-id="29ecc-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="29ecc-193">Вот пример, в который для пользователя *Belinda Newman* задано расположение использования для *Франции,* но указывается ее отображаемая имя, а не ее имя-пользователя.</span><span class="sxs-lookup"><span data-stu-id="29ecc-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="29ecc-194">Изменение свойств для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="29ecc-194">Change properties for all user accounts</span></span>

<span data-ttu-id="29ecc-195">Чтобы изменить свойства для всех пользователей, используйте комбинацию с помощью **get-MsolUser** и **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="29ecc-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="29ecc-196">В следующем примере расположение использования для всех пользователей изменяется на *Францию:*</span><span class="sxs-lookup"><span data-stu-id="29ecc-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="29ecc-197">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="29ecc-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="29ecc-198">Получите все сведения об учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="29ecc-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="29ecc-199">Установите расположение пользователя для Франции (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="29ecc-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="29ecc-200">Изменение свойств для определенного набора учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="29ecc-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="29ecc-201">Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать сочетание с помощью **get-MsolUser,** **Where** и **Set-MsolUser.**</span><span class="sxs-lookup"><span data-stu-id="29ecc-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="29ecc-202">В следующем примере расположение использования для всех пользователей в бухгалтерии изменяется на *Францию:*</span><span class="sxs-lookup"><span data-stu-id="29ecc-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="29ecc-203">Эта команда предписывает PowerShell:</span><span class="sxs-lookup"><span data-stu-id="29ecc-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="29ecc-204">Получите все сведения об учетных записях пользователей **(Get-MsolUser)** и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="29ecc-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="29ecc-205">Найдите все учетные записи пользователей, свойство *Department* которых имеет свойство Accounting **(Где {$_). Department -eq "Accounting"}**) и отправьте итоговые сведения в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="29ecc-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="29ecc-206">Установите расположение пользователя для Франции (**Set-MsolUser -UsageLocation "FR"**).</span><span class="sxs-lookup"><span data-stu-id="29ecc-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="29ecc-207">См. также</span><span class="sxs-lookup"><span data-stu-id="29ecc-207">See also</span></span>

[<span data-ttu-id="29ecc-208">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="29ecc-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="29ecc-209">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="29ecc-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="29ecc-210">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29ecc-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
