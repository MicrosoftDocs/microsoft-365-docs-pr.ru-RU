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
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="d4aa0-103">Настройка свойств учетной записи пользователя Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4aa0-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="d4aa0-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="d4aa0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d4aa0-105">Вы можете использовать центр администрирования Microsoft 365 для настройки свойств учетных записей пользователей клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-105">You can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant.</span></span> <span data-ttu-id="d4aa0-106">В PowerShell можно также выполнить эту задачу, а также другие действия, которые невозможно выполнить в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-106">In PowerShell, you can also do this, plus some other things you can't do in the admin center.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="d4aa0-107">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="d4aa0-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="d4aa0-108">Чтобы настроить свойства учетных записей пользователей в модуле PowerShell Azure Active Directory для Graph, используйте командлет [**Set – AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) и укажите свойства, которые нужно задать или изменить.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-108">To configure properties for user accounts in the Azure Active Directory PowerShell for Graph module, use the [**Set-AzureADUser**](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="d4aa0-109">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-109">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="d4aa0-110">Изменение свойств учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="d4aa0-110">Change properties for a specific user account</span></span>

<span data-ttu-id="d4aa0-111">Вы идентифицируете учетную запись с помощью параметра *– ObjectID* , а также устанавливаете или изменяет определенные свойства с помощью дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-111">You identify the account with the *-ObjectID* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="d4aa0-112">Ниже перечислены наиболее распространенные параметры.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-112">Here's a list of the most common parameters:</span></span>
  
- <span data-ttu-id="d4aa0-113">-Department "<название отдела>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-113">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="d4aa0-114">-DisplayName "<полное имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-114">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="d4aa0-115">-FacsimilieTelephoneNumber "<номер факса>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-115">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="d4aa0-116">-GivenName "<имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-116">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="d4aa0-117">-Surname "<фамилия пользователя>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-117">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="d4aa0-118">-Mobile "<номер мобильного телефона>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-118">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="d4aa0-119">-JobTitle "<должность>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-119">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="d4aa0-120">-PreferredLanguage "<язык>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-120">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="d4aa0-121">-StreetAddress "<почтовый адрес>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-121">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="d4aa0-122">-City "<название города>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-122">-City "\<city name>"</span></span>
    
- <span data-ttu-id="d4aa0-123">-State "<название региона>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-123">-State "\<state name>"</span></span>
    
- <span data-ttu-id="d4aa0-124">-PostalCode "<почтовый индекс>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-124">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="d4aa0-125">-Country "<название страны>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-125">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="d4aa0-126">-TelephoneNumber "<номер рабочего телефона>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-126">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="d4aa0-127">— UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="d4aa0-127">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="d4aa0-128">Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-128">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="d4aa0-129">Дополнительные параметры можно найти в разделе [Set – AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span><span class="sxs-lookup"><span data-stu-id="d4aa0-129">For additional parameters, see [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) .</span></span>

>[!Note]
><span data-ttu-id="d4aa0-130">Перед назначением лицензий учетной записи пользователя необходимо назначить место использования.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-130">Before you can assign licenses to a user account, you must assign a usage location.</span></span>
>

<span data-ttu-id="d4aa0-131">Чтобы отобразить имя участника-пользователя для учетных записей пользователей, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-131">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="d4aa0-132">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-132">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="d4aa0-133">Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-133">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d4aa0-134">Сортировать список имен субъектов-пользователей в алфавитном порядке (**Сортировка userPrincipalName**) и отправлять их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-134">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d4aa0-135">Отобразите только свойство имени участника-пользователя для каждой учетной записи (**выберите userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-135">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

1. <span data-ttu-id="d4aa0-136">Отобразить их на одном экране (**More**).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-136">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="d4aa0-137">Чтобы отобразить имя участника-пользователя для учетной записи на основе его отображаемого имени (имя и фамилия), выполните следующие команды.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-137">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="d4aa0-138">Заполните переменную *$username* и удалите \< and > символы:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-138">Fill in the *$userName* variable, and remove the \< and > characters:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="d4aa0-139">В этом примере отображается имя участника пользователя для учетной записи пользователя с отображаемым именем *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-139">This example displays the User Principal Name for the user account that has the display name *Caleb Sills*.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="d4aa0-140">С помощью переменной *$upn* можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-140">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="d4aa0-141">Ниже приведен пример, в котором показано, как задать *Светланы Коноваловой*в качестве места использования для Франции.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-141">Here's an example that sets *Belinda Newman*'s usage location to France.</span></span> <span data-ttu-id="d4aa0-142">Но здесь указывается его отображаемое имя, а не имя участника пользователя:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-142">But it specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="d4aa0-143">Изменение свойств для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="d4aa0-143">Change properties for all user accounts</span></span>

<span data-ttu-id="d4aa0-144">Чтобы изменить свойства для всех пользователей, можно использовать сочетание командлетов **Get – AzureADUser** и **Set – AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="d4aa0-144">To change properties for all users, you can use a combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="d4aa0-145">В следующем примере показано, как изменить расположение использования для всех пользователей на *Франция*:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-145">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="d4aa0-146">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-146">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="d4aa0-147">Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-147">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d4aa0-148">Задайте для расположения пользователя значение Франция (**Set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-148">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="d4aa0-149">Изменение свойств для определенного набора учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="d4aa0-149">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="d4aa0-150">Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать сочетания командлетов **Get – AzureADUser**, **WHERE**и **Set — AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="d4aa0-150">To change properties for a specific set of user accounts, you can use a combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets.</span></span> <span data-ttu-id="d4aa0-151">В следующем примере показано, как изменить место использования для всех пользователей в отделе учета на *Франция*:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-151">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="d4aa0-152">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-152">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="d4aa0-153">Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-153">Get all the information on the user accounts (**Get-AzureADUser**), and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="d4aa0-154">Найдите все учетные записи пользователей, для которых для свойства *Department* задано значение "Accounting" (**where {$ _. Department-EQ "Accounting"}**) и отправьте полученные сведения в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-154">Find all the user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**), and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d4aa0-155">Задайте для расположения пользователя значение Франция (**Set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-155">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="d4aa0-156">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4aa0-156">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="d4aa0-157">Чтобы настроить свойства учетных записей пользователей с помощью модуля Microsoft Azure Active Directory для Windows PowerShell, используйте командлет **Set – MsolUser** и укажите свойства, которые нужно задать или изменить.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-157">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span>

<span data-ttu-id="d4aa0-158">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-158">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="d4aa0-159">Среда PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для модуля Windows PowerShell и командлеты с *MSOL* в имени.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-159">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="d4aa0-160">Выполните эти командлеты в Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-160">Run these cmdlets from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="d4aa0-161">Изменение свойств учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="d4aa0-161">Change properties for a specific user account</span></span>

<span data-ttu-id="d4aa0-162">Чтобы настроить свойства для конкретной учетной записи пользователя, используйте командлет [**Set – MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) и укажите свойства, которые нужно задать или изменить.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-162">To configure properties for a specific user account, use the [**Set-MsolUser**](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="d4aa0-163">Вы идентифицируете учетную запись с помощью параметра *– userPrincipalName* , а также устанавливаете или изменяет определенные свойства с помощью дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-163">You identify the account with the *-UserPrincipalName* parameter and set or change specific properties by using additional parameters.</span></span> <span data-ttu-id="d4aa0-164">Ниже перечислены наиболее распространенные параметры.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-164">Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="d4aa0-165">-City "<название города>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-165">-City "\<city name>"</span></span>
    
- <span data-ttu-id="d4aa0-166">-Country "<название страны>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-166">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="d4aa0-167">-Department "<название отдела>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-167">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="d4aa0-168">-DisplayName "<полное имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-168">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="d4aa0-169">-Fax "<номер факса>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-169">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="d4aa0-170">-FirstName "<имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-170">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="d4aa0-171">-LastName "<фамилия пользователя>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-171">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="d4aa0-172">-MobilePhone "<номер мобильного телефона>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-172">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="d4aa0-173">-Office "<расположение офиса>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-173">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="d4aa0-174">-PhoneNumber "<номер телефона офиса>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-174">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="d4aa0-175">-PostalCode "<почтовый индекс>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-175">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="d4aa0-176">-PreferredLanguage "<язык>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-176">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="d4aa0-177">-State "<название региона>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-177">-State "\<state name>"</span></span>
    
- <span data-ttu-id="d4aa0-178">-StreetAddress "<почтовый адрес>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-178">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="d4aa0-179">-Title "<должность>"</span><span class="sxs-lookup"><span data-stu-id="d4aa0-179">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="d4aa0-180">— UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="d4aa0-180">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="d4aa0-181">Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-181">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="d4aa0-182">Дополнительные параметры можно найти в разделе [Set – MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-182">For additional parameters, see [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span></span>

<span data-ttu-id="d4aa0-183">Чтобы просмотреть имена участников пользователя для всех пользователей, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-183">To see the User Principal Names of all your users, run the following command:</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="d4aa0-184">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-184">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="d4aa0-185">Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-185">Get all of information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d4aa0-186">Сортировать список имен субъектов-пользователей в алфавитном порядке (**Сортировка userPrincipalName**) и отправлять их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-186">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d4aa0-187">Отобразите только свойство имени участника-пользователя для каждой учетной записи (**выберите userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-187">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
1. <span data-ttu-id="d4aa0-188">Отобразить их на одном экране (**More**).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-188">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="d4aa0-189">Чтобы отобразить имя участника-пользователя для учетной записи на основе его отображаемого имени (имя и фамилия), выполните следующие команды.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-189">To display the User Principal Name for an account based on its display name (first and last name), run the following commands.</span></span> <span data-ttu-id="d4aa0-190">Заполните переменную *$username* и удалите \< and > символы.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-190">Fill in the *$userName* variable, and remove the \< and > characters.</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="d4aa0-191">В этом примере отображается имя участника пользователя с именем Caleb Sills:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-191">This example displays the User Principal Name for the user named Caleb Sills:</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="d4aa0-192">С помощью переменной *$upn* можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-192">By using a *$upn* variable, you can make changes to individual accounts based on their display name.</span></span> <span data-ttu-id="d4aa0-193">Ниже приведен пример, в котором показано, как настроить *Светланы Коноваловой*в качестве места использования для *Франции*, но указать его отображаемое имя вместо основного имени пользователя:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-193">Here's an example that sets *Belinda Newman*'s usage location to *France*, but specifies her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="d4aa0-194">Изменение свойств для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="d4aa0-194">Change properties for all user accounts</span></span>

<span data-ttu-id="d4aa0-195">Чтобы изменить свойства для всех пользователей, используйте сочетание командлетов **Get – MsolUser** и **Set – MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="d4aa0-195">To change properties for all users,  use a combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="d4aa0-196">В следующем примере показано, как изменить расположение использования для всех пользователей на *Франция*:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-196">The following example changes the usage location for all users to *France*:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="d4aa0-197">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-197">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="d4aa0-198">Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-198">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d4aa0-199">Задайте для расположения пользователя значение Франция (**Set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-199">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="d4aa0-200">Изменение свойств для определенного набора учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="d4aa0-200">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="d4aa0-201">Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать сочетания командлетов **Get – MsolUser**, **WHERE**и **Set — MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="d4aa0-201">To change properties for a specific set of user accounts, you can use a combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="d4aa0-202">В следующем примере показано, как изменить место использования для всех пользователей в отделе учета на *Франция*:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-202">The following example changes the usage location for all the users in the Accounting department to *France*:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="d4aa0-203">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-203">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="d4aa0-204">Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-204">Get all the information for the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d4aa0-205">Найдите все учетные записи пользователей, для которых для свойства *Department* задано значение "Accounting" (**where {$ _. Department-EQ "Accounting"}**) и отправьте полученные сведения в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-205">Find all user accounts that have their *Department* property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
1. <span data-ttu-id="d4aa0-206">Задайте для расположения пользователя значение Франция (**Set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="d4aa0-206">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4aa0-207">Дополнительные ресурсы:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-207">See also</span></span>

[<span data-ttu-id="d4aa0-208">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4aa0-208">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d4aa0-209">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4aa0-209">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="d4aa0-210">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d4aa0-210">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
