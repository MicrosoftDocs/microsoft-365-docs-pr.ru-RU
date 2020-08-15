---
title: Настройка свойств учетной записи пользователя Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
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
description: 'Сводка: использование PowerShell для Microsoft 365 для настройки свойств отдельных или нескольких учетных записей пользователей в клиенте Microsoft 365.'
ms.openlocfilehash: 6a435b3981efa8d8c2be7f6d983a1d062237f0db
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692920"
---
# <a name="configure-microsoft-365-user-account-properties-with-powershell"></a><span data-ttu-id="4eea5-103">Настройка свойств учетной записи пользователя Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4eea5-103">Configure Microsoft 365 user account properties with PowerShell</span></span>

<span data-ttu-id="4eea5-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="4eea5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4eea5-105">Несмотря на то, что вы можете использовать центр администрирования Microsoft 365 для настройки свойств учетных записей пользователей клиента Microsoft 365, вы также можете использовать PowerShell и выполнить некоторые действия, которые не могут находиться в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4eea5-105">Although you can use the Microsoft 365 admin center to configure properties for the user accounts of your Microsoft 365 tenant, you can also use PowerShell and do some things that the Microsoft 365 admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="4eea5-106">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="4eea5-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="4eea5-107">Чтобы настроить свойства учетных записей пользователей с помощью модуля PowerShell Azure Active Directory для Graph, используйте командлет [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0), указав свойства, которые нужно задать или изменить.</span><span class="sxs-lookup"><span data-stu-id="4eea5-107">To configure properties for user accounts with the Azure Active Directory PowerShell for Graph module, you use the [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="4eea5-108">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="4eea5-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
   
### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="4eea5-109">Изменение свойств учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="4eea5-109">Change properties for a specific user account</span></span>

<span data-ttu-id="4eea5-p101">Параметр **-ObjectID** указывает учетную запись, а ее свойства можно задать или изменить с помощью дополнительных параметров. Ниже перечислены наиболее распространенные.</span><span class="sxs-lookup"><span data-stu-id="4eea5-p101">You identify the account with the **-ObjectID** parameter and set or change specific properties with additional parameters. Here's a list of the most common parameters.</span></span>
  
- <span data-ttu-id="4eea5-112">-Department "<название отдела>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-112">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="4eea5-113">-DisplayName "<полное имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-113">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="4eea5-114">-FacsimilieTelephoneNumber "<номер факса>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-114">-FacsimilieTelephoneNumber "\<fax number>"</span></span>
    
- <span data-ttu-id="4eea5-115">-GivenName "<имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-115">-GivenName "\<user first name>"</span></span>
    
- <span data-ttu-id="4eea5-116">-Surname "<фамилия пользователя>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-116">-Surname "\<user last name>"</span></span>
    
- <span data-ttu-id="4eea5-117">-Mobile "<номер мобильного телефона>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-117">-Mobile "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="4eea5-118">-JobTitle "<должность>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-118">-JobTitle "\<job title>"</span></span>
    
- <span data-ttu-id="4eea5-119">-PreferredLanguage "<язык>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-119">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="4eea5-120">-StreetAddress "<почтовый адрес>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-120">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="4eea5-121">-City "<название города>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-121">-City "\<city name>"</span></span>
    
- <span data-ttu-id="4eea5-122">-State "<название региона>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-122">-State "\<state name>"</span></span>
    
- <span data-ttu-id="4eea5-123">-PostalCode "<почтовый индекс>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-123">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="4eea5-124">-Country "<название страны>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-124">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="4eea5-125">-TelephoneNumber "<номер рабочего телефона>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-125">-TelephoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="4eea5-126">— UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="4eea5-126">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="4eea5-127">Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="4eea5-127">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="4eea5-128">Сведения о дополнительных параметрах см. в статье [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0).</span><span class="sxs-lookup"><span data-stu-id="4eea5-128">See [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser?view=azureadps-2.0) for additional parameters.</span></span>


<span data-ttu-id="4eea5-129">Чтобы отобразить имя участника-пользователя для учетных записей пользователей, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="4eea5-129">To display the User Principal Name for your user accounts, run the following command.</span></span>
  
```powershell
Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="4eea5-130">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4eea5-130">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="4eea5-131">Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4eea5-131">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4eea5-132">Сортировать список имен субъектов-пользователей в алфавитном порядке (**Сортировка userPrincipalName**) и отправлять их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4eea5-132">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4eea5-133">Отобразите только свойство имени участника-пользователя для каждой учетной записи (**выберите userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="4eea5-133">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>

- <span data-ttu-id="4eea5-134">Отобразить их на одном экране (**More**).</span><span class="sxs-lookup"><span data-stu-id="4eea5-134">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="4eea5-135">Эта команда перечислит все учетные записи.</span><span class="sxs-lookup"><span data-stu-id="4eea5-135">This command will list all of your accounts.</span></span> <span data-ttu-id="4eea5-136">Если вы хотите отобразить имя участника-пользователя для учетной записи на основе отображаемого имени (имя и фамилия), заполните приведенную ниже переменную **$username** (удалив \< and > символы), а затем выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="4eea5-136">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="4eea5-137">В этом примере выводится имя участника-пользователя для учетной записи пользователя с отображаемым именем Caleb Sills.</span><span class="sxs-lookup"><span data-stu-id="4eea5-137">This example displays the User Principal Name for the user account with the display name of Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="4eea5-p103">С помощью переменной **$upn** можно вносить изменения в учетные записи, указывая их отображаемые имена. В этом примере показано, как заменить текущее место работы пользователя Belinda Newman на Францию, указав при этом соответствующее отображаемое имя, а не имя участника-пользователя:</span><span class="sxs-lookup"><span data-stu-id="4eea5-p103">By using a **$upn** variable, you can make changes to individual accounts based on their display name. Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="Belinda Newman"
$upn=(Get-AzureADUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-AzureADUser -ObjectID $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="4eea5-140">Изменение свойств для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="4eea5-140">Change properties for all user accounts</span></span>

<span data-ttu-id="4eea5-p104">Чтобы изменить свойства для всех пользователей, примените сочетание командлетов **Get-AzureADUser** и **Set-AzureADUser**. Следующий пример заменяет текущее расположение использования для всех пользователей на Францию:</span><span class="sxs-lookup"><span data-stu-id="4eea5-p104">To change properties for all users, you can use the combination of the **Get-AzureADUser** and **Set-AzureADUser** cmdlets. The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-AzureADUser | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="4eea5-143">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4eea5-143">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="4eea5-144">Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4eea5-144">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4eea5-145">Задайте для расположения пользователя значение Франция (**Set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="4eea5-145">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="4eea5-146">Изменение свойств определенной части учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="4eea5-146">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="4eea5-p105">Сочетание командлетов **Get-AzureADUser**, **Where** и **Set-AzureADUser** позволит изменить свойства определенной части учетных записей пользователей. Следующая команда заменяет расположение всех пользователей в отделе Accounting на Францию:</span><span class="sxs-lookup"><span data-stu-id="4eea5-p105">To change properties for a specific set of user account, you can use the combination of the **Get-AzureADUser**, **Where**, and **Set-AzureADUser** cmdlets. The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.Department -eq "Accounting"} | Set-AzureADUser -UsageLocation "FR"
```

<span data-ttu-id="4eea5-149">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4eea5-149">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="4eea5-150">Получите все сведения об учетных записях пользователей (**Get-AzureADUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4eea5-150">Get all of the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4eea5-151">Найдите все учетные записи пользователей, для которых в свойстве Department задано значение "Accounting" (**где {$ _. Department-EQ "Accounting"}**) и отправьте полученные сведения в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4eea5-151">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="4eea5-152">Задайте для расположения пользователя значение Франция (**Set-AzureADUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="4eea5-152">Set the user location to France (**Set-AzureADUser -UsageLocation "FR"**).</span></span>
    
## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="4eea5-153">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4eea5-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="4eea5-154">Чтобы настроить свойства учетных записей пользователей с помощью модуля Microsoft Azure Active Directory для Windows PowerShell, используйте командлет **Set – MsolUser** и укажите свойства, которые нужно задать или изменить.</span><span class="sxs-lookup"><span data-stu-id="4eea5-154">To configure properties for user accounts with the Microsoft Azure Active Directory Module for Windows PowerShell, you use the **Set-MsolUser** cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="4eea5-155">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4eea5-155">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
  
>[!Note]
><span data-ttu-id="4eea5-156">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="4eea5-156">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="4eea5-157">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4eea5-157">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="change-properties-for-a-specific-user-account"></a><span data-ttu-id="4eea5-158">Изменение свойств учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="4eea5-158">Change properties for a specific user account</span></span>

<span data-ttu-id="4eea5-159">Чтобы настроить свойства учетной записи пользователя, используйте командлет [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) и укажите свойства, которые нужно задать или изменить.</span><span class="sxs-lookup"><span data-stu-id="4eea5-159">To configure properties for a specific user account, you use the [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) cmdlet and specify the properties to set or change.</span></span> 

<span data-ttu-id="4eea5-p107">Параметр **-UserPrincipalName** указывает учетную запись, а ее свойства можно задать или изменить с помощью дополнительных параметров. Ниже перечислены наиболее распространенные.</span><span class="sxs-lookup"><span data-stu-id="4eea5-p107">You identify the account with the **-UserPrincipalName** parameter and set or change specific properties with additional parameters. Here is a list of the most common parameters.</span></span>
  
- <span data-ttu-id="4eea5-162">-City "<название города>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-162">-City "\<city name>"</span></span>
    
- <span data-ttu-id="4eea5-163">-Country "<название страны>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-163">-Country "\<country name>"</span></span>
    
- <span data-ttu-id="4eea5-164">-Department "<название отдела>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-164">-Department "\<department name>"</span></span>
    
- <span data-ttu-id="4eea5-165">-DisplayName "<полное имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-165">-DisplayName "\<full user name>"</span></span>
    
- <span data-ttu-id="4eea5-166">-Fax "<номер факса>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-166">-Fax "\<fax number>"</span></span>
    
- <span data-ttu-id="4eea5-167">-FirstName "<имя пользователя>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-167">-FirstName "\<user first name>"</span></span>
    
- <span data-ttu-id="4eea5-168">-LastName "<фамилия пользователя>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-168">-LastName "\<user last name>"</span></span>
    
- <span data-ttu-id="4eea5-169">-MobilePhone "<номер мобильного телефона>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-169">-MobilePhone "\<mobile phone number>"</span></span>
    
- <span data-ttu-id="4eea5-170">-Office "<расположение офиса>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-170">-Office "\<office location>"</span></span>
    
- <span data-ttu-id="4eea5-171">-PhoneNumber "<номер телефона офиса>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-171">-PhoneNumber "\<office phone number>"</span></span>
    
- <span data-ttu-id="4eea5-172">-PostalCode "<почтовый индекс>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-172">-PostalCode "\<postal code>"</span></span>
    
- <span data-ttu-id="4eea5-173">-PreferredLanguage "<язык>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-173">-PreferredLanguage "\<language>"</span></span>
    
- <span data-ttu-id="4eea5-174">-State "<название региона>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-174">-State "\<state name>"</span></span>
    
- <span data-ttu-id="4eea5-175">-StreetAddress "<почтовый адрес>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-175">-StreetAddress "\<street address>"</span></span>
    
- <span data-ttu-id="4eea5-176">-Title "<должность>"</span><span class="sxs-lookup"><span data-stu-id="4eea5-176">-Title "\<title name>"</span></span>
    
- <span data-ttu-id="4eea5-177">— UsageLocation " \<2-character country or region code> "</span><span class="sxs-lookup"><span data-stu-id="4eea5-177">-UsageLocation "\<2-character country or region code>"</span></span>
    
    <span data-ttu-id="4eea5-178">Это двухбуквенный код страны или региона согласно ISO 3166-1 alpha-2 (A2).</span><span class="sxs-lookup"><span data-stu-id="4eea5-178">This is the ISO 3166-1 alpha-2 (A2) two-letter country or region code.</span></span>
    
<span data-ttu-id="4eea5-179">Сведения о дополнительных параметрах см. в статье [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="4eea5-179">See [Set-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194136(v=azure.100)) for additional parameters.</span></span>

<span data-ttu-id="4eea5-180">Чтобы просмотреть имя участника-пользователя для каждого из пользователей, выполните приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="4eea5-180">To see the User Principal Names of all your users, run the following command.</span></span>
  
```powershell
Get-MSolUser | Sort UserPrincipalName | Select UserPrincipalName | More
```

<span data-ttu-id="4eea5-181">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4eea5-181">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="4eea5-182">Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4eea5-182">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4eea5-183">Сортировать список имен субъектов-пользователей в алфавитном порядке (**Сортировка userPrincipalName**) и отправлять их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4eea5-183">Sort the list of User Principal Names alphabetically (**Sort UserPrincipalName**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4eea5-184">Отобразите только свойство имени участника-пользователя для каждой учетной записи (**выберите userPrincipalName**).</span><span class="sxs-lookup"><span data-stu-id="4eea5-184">Display just the User Principal Name property for each account (**Select UserPrincipalName**).</span></span>
    
- <span data-ttu-id="4eea5-185">Отобразить их на одном экране (**More**).</span><span class="sxs-lookup"><span data-stu-id="4eea5-185">Display them one screen at a time (**More**).</span></span>
    
<span data-ttu-id="4eea5-186">Эта команда перечислит все учетные записи.</span><span class="sxs-lookup"><span data-stu-id="4eea5-186">This command will list all of your accounts.</span></span> <span data-ttu-id="4eea5-187">Если вы хотите отобразить имя участника-пользователя для учетной записи на основе отображаемого имени (имя и фамилия), заполните приведенную ниже переменную **$username** (удалив \< and > символы), а затем выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="4eea5-187">If you want to display the User Principal Name for an account based on its display name (first and last name), fill in the **$userName** variable below (removing the \< and > characters), and then run the following commands:</span></span>
  
```powershell
$userName="<Display name>"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="4eea5-188">Этот пример отображает имя участника-пользователя для пользователя Caleb Sills.</span><span class="sxs-lookup"><span data-stu-id="4eea5-188">This example displays the User Principal Name for the user named Caleb Sills.</span></span>
  
```powershell
$userName="Caleb Sills"
Write-Host (Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
```

<span data-ttu-id="4eea5-p109">С помощью переменной **$upn** можно вносить изменения в отдельные учетные записи с учетом их отображаемых имен. Данный пример показывает, как заменить текущее расположение использования для пользователя Belinda Newman на Францию, указав при этом соответствующее отображаемое имя, а не имя участника-пользователя:</span><span class="sxs-lookup"><span data-stu-id="4eea5-p109">By using a **$upn** variable, you can make changes to individual accounts based on their display name. Here is an example of setting Belinda Newman's usage location to France, but specifying her display name rather than her User Principal Name:</span></span>
  
```powershell
$userName="<display name>"
$upn=(Get-MsolUser | where {$_.DisplayName -eq $userName}).UserPrincipalName
Set-MsolUser -UserPrincipalName $upn -UsageLocation "FR"
```

### <a name="change-properties-for-all-user-accounts"></a><span data-ttu-id="4eea5-191">Изменение свойств для всех учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="4eea5-191">Change properties for all user accounts</span></span>

<span data-ttu-id="4eea5-p110">Чтобы изменить свойства для всех пользователей, можно использовать сочетание командлетов **Get-MsolUser** и **Set-MsolUser**. В следующем примере место работы всех пользователей меняется на Францию:</span><span class="sxs-lookup"><span data-stu-id="4eea5-p110">To change properties for all users, you can use the combination of the **Get-MsolUser** and **Set-MsolUser** cmdlets. The following example changes the usage location for all users to France:</span></span>
  
```powershell
Get-MsolUser | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="4eea5-194">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4eea5-194">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="4eea5-195">Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4eea5-195">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4eea5-196">Задайте для расположения пользователя значение Франция (**Set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="4eea5-196">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    
### <a name="change-properties-for-a-specific-set-of-user-accounts"></a><span data-ttu-id="4eea5-197">Изменение свойств для определенного набора учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="4eea5-197">Change properties for a specific set of user accounts</span></span>

<span data-ttu-id="4eea5-198">Чтобы изменить свойства для определенного набора учетных записей пользователей, можно использовать сочетание командлетов **Get – MsolUser**, **WHERE**и **Set — MsolUser** .</span><span class="sxs-lookup"><span data-stu-id="4eea5-198">To change properties for a specific set of user account, you can use the combination of the **Get-MsolUser**, **Where**, and **Set-MsolUser** cmdlets.</span></span> <span data-ttu-id="4eea5-199">Пример кода, приведенный ниже, заменяет текущее расположение использования для всех пользователей в отделе Accounting (бухгалтерского учета) на Францию.</span><span class="sxs-lookup"><span data-stu-id="4eea5-199">The following example changes the usage location for all the users in the Accounting department to France:</span></span>
  
```powershell
Get-MsolUser | Where {$_.Department -eq "Accounting"} | Set-MsolUser -UsageLocation "FR"
```

<span data-ttu-id="4eea5-200">Эта команда предписывает PowerShell выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4eea5-200">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="4eea5-201">Получите все сведения об учетных записях пользователей (**Get-MsolUser**) и отправьте их в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4eea5-201">Get all of the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
- <span data-ttu-id="4eea5-202">Найдите все учетные записи пользователей, для которых в свойстве Department задано значение "Accounting" (**где {$ _. Department-EQ "Accounting"}**) и отправьте полученные сведения в следующую команду ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="4eea5-202">Find all of the user accounts that have their Department property set to "Accounting" (**Where {$_.Department -eq "Accounting"}**) and send the resulting information to the next command (**|**).</span></span>
    
- <span data-ttu-id="4eea5-203">Задайте для расположения пользователя значение Франция (**Set-MsolUser-UsageLocation "fr"**).</span><span class="sxs-lookup"><span data-stu-id="4eea5-203">Set the user location to France (**Set-MsolUser -UsageLocation "FR"**).</span></span>
    

## <a name="see-also"></a><span data-ttu-id="4eea5-204">См. также</span><span class="sxs-lookup"><span data-stu-id="4eea5-204">See also</span></span>

[<span data-ttu-id="4eea5-205">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4eea5-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4eea5-206">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4eea5-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="4eea5-207">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4eea5-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
