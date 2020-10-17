---
title: Создание учетных записей пользователей Microsoft 365 с помощью PowerShell
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
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: В этой статье рассказывается, как использовать PowerShell для создания учетных записей пользователей или нескольких учетных записей пользователей Microsoft 365.
ms.openlocfilehash: aedcc4adba6171a63a5ddaeb87b20150e72b2a76
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580956"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="b938f-103">Создание учетных записей пользователей Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b938f-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="b938f-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="b938f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b938f-105">С помощью PowerShell для Microsoft 365 можно эффективно создавать учетные записи пользователей, особенно несколько учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="b938f-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, especially multiple user accounts.</span></span> <span data-ttu-id="b938f-106">При создании учетных записей пользователей в PowerShell некоторые свойства учетной записи всегда являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="b938f-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="b938f-107">Для создания учетной записи другие свойства не требуются, но в ином случае важен.</span><span class="sxs-lookup"><span data-stu-id="b938f-107">Other properties aren't required to create the account, but are otherwise important.</span></span> <span data-ttu-id="b938f-108">Эти свойства описаны в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="b938f-108">These properties are described in the following table:</span></span>
  
|<span data-ttu-id="b938f-109">**Имя свойства**</span><span class="sxs-lookup"><span data-stu-id="b938f-109">**Property name**</span></span>|<span data-ttu-id="b938f-110">**Обязательный?**</span><span class="sxs-lookup"><span data-stu-id="b938f-110">**Required?**</span></span>|<span data-ttu-id="b938f-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b938f-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b938f-112">**DisplayName**</span><span class="sxs-lookup"><span data-stu-id="b938f-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="b938f-113">Да</span><span class="sxs-lookup"><span data-stu-id="b938f-113">Yes</span></span>  <br/> |<span data-ttu-id="b938f-114">Это отображаемое имя, используемое в службах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b938f-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="b938f-115">Например, Caleb Sills.</span><span class="sxs-lookup"><span data-stu-id="b938f-115">For example, Caleb Sills.</span></span>  <br/> |
|<span data-ttu-id="b938f-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="b938f-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="b938f-117">Да</span><span class="sxs-lookup"><span data-stu-id="b938f-117">Yes</span></span>  <br/> |<span data-ttu-id="b938f-118">Это имя учетной записи, используемой для входа в службы Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b938f-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="b938f-119">Например, CalebS@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="b938f-119">For example, CalebS@contoso.onmicrosoft.com.</span></span>  <br/> |
|<span data-ttu-id="b938f-120">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="b938f-120">**FirstName**</span></span> <br/> |<span data-ttu-id="b938f-121">Нет</span><span class="sxs-lookup"><span data-stu-id="b938f-121">No</span></span>  <br/> ||
|<span data-ttu-id="b938f-122">**LastName**</span><span class="sxs-lookup"><span data-stu-id="b938f-122">**LastName**</span></span> <br/> |<span data-ttu-id="b938f-123">Нет</span><span class="sxs-lookup"><span data-stu-id="b938f-123">No</span></span>  <br/> ||
|<span data-ttu-id="b938f-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="b938f-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="b938f-125">Нет</span><span class="sxs-lookup"><span data-stu-id="b938f-125">No</span></span>  <br/> |<span data-ttu-id="b938f-126">Это план лицензирования (который также называется планом лицензирования или SKU), от которого учетной записи пользователя назначена доступная лицензия.</span><span class="sxs-lookup"><span data-stu-id="b938f-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="b938f-127">Лицензия определяет службы Microsoft 365, доступные для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="b938f-127">The license defines the Microsoft 365 services that are available to account.</span></span> <span data-ttu-id="b938f-128">Вам не нужно назначать лицензию пользователю при создании учетной записи, но для этой учетной записи требуется лицензия на доступ к службам Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b938f-128">You don't have to assign a license to a user when you create the account, but the account requires a license to access Microsoft 365 services.</span></span> <span data-ttu-id="b938f-129">Лицензию требуется добавить в течение 30 дней после создания учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="b938f-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="b938f-130">**Password**</span><span class="sxs-lookup"><span data-stu-id="b938f-130">**Password**</span></span> <br/> |<span data-ttu-id="b938f-131">Нет</span><span class="sxs-lookup"><span data-stu-id="b938f-131">No</span></span>  <br/> | <span data-ttu-id="b938f-p105">Если не задать пароль, для учетной записи пользователя назначается случайный пароль, отображающийся в результатах выполнения команды. Если вы решили задать пароль самостоятельно, он должен содержать от 8 до 16 текстовых знаков ASCII любых трех типов из указанных далее: строчные буквы, прописные буквы, числа и символы.</span><span class="sxs-lookup"><span data-stu-id="b938f-p105">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command. If you specify a password, it needs to be 8 to 16 ASCII text characters from any three of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span> <br/> |
|<span data-ttu-id="b938f-134">**UsageLocation**</span><span class="sxs-lookup"><span data-stu-id="b938f-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="b938f-135">Нет</span><span class="sxs-lookup"><span data-stu-id="b938f-135">No</span></span>  <br/> |<span data-ttu-id="b938f-136">Это допустимый код страны согласно ISO 3166-1 alpha-2 (например, US для США и FR для Франции).</span><span class="sxs-lookup"><span data-stu-id="b938f-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="b938f-137">Важно указать это значение, так как некоторые службы O365_W14_2nd недоступны в определенных странах.</span><span class="sxs-lookup"><span data-stu-id="b938f-137">For example, US for the United States, and FR for France.</span></span> <span data-ttu-id="b938f-138">**Так как некоторые службы Microsoft 365 недоступны в некоторых странах, вы не можете назначить лицензию учетной записи пользователя, если для этой учетной записи не задано это значение.**</span><span class="sxs-lookup"><span data-stu-id="b938f-138">**Because some Microsoft 365 services aren't available in certain countries, you can't assign a license to a user account unless the account has this value configured.**</span></span> <span data-ttu-id="b938f-139">Более подробную информацию можно узнать в статье [ограничения лицензирования](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span><span class="sxs-lookup"><span data-stu-id="b938f-139">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span>  <br/> |

>[!Note]
><span data-ttu-id="b938f-140">[Узнайте, как создавать учетные записи пользователей](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) с помощью центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b938f-140">[Learn how to create user accounts](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) with the Microsoft 365 admin center.</span></span> <span data-ttu-id="b938f-141">Список дополнительных ресурсов приведен в разделе [Manage Users and Groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span><span class="sxs-lookup"><span data-stu-id="b938f-141">For a list of additional resources, see [Manage users and groups](https://docs.microsoft.com/microsoft-365/admin/add-users/).</span></span>
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="b938f-142">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="b938f-142">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="b938f-143">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="b938f-143">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="b938f-144">После подключения используйте следующий синтаксис, чтобы создать учетную запись:</span><span class="sxs-lookup"><span data-stu-id="b938f-144">After you have connected, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="b938f-145">В этом примере создается учетная запись пользователя Caleb Sills из Соединенных Штатов:</span><span class="sxs-lookup"><span data-stu-id="b938f-145">This example creates an account for the United States user named Caleb Sills:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="b938f-146">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b938f-146">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="b938f-147">Сначала [подключитесь к клиенту Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b938f-147">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="b938f-148">Создание одной учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="b938f-148">Create an individual user account</span></span>

<span data-ttu-id="b938f-149">Чтобы создать одну учетную запись, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b938f-149">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="b938f-150">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="b938f-150">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="b938f-151">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b938f-151">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="b938f-152">Чтобы предоставить список доступных имен плана лицензирования, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b938f-152">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="b938f-153">Этот пример кода создает учетную запись для пользователя в США с именем Caleb Sills и назначает для него лицензию согласно плану лицензирования `contoso:ENTERPRISEPACK` (Office 365 корпоративный E3).</span><span class="sxs-lookup"><span data-stu-id="b938f-153">This example creates an account for the United States user named Caleb Sills, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="b938f-154">Создание нескольких учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="b938f-154">Create multiple user accounts</span></span>

1. <span data-ttu-id="b938f-p109">Создайте CSV-файл, который содержит обязательные сведения об учетных записях пользователей. Пример:</span><span class="sxs-lookup"><span data-stu-id="b938f-p109">Create a comma-separated value (CSV) file that contains the required user account information. For example:</span></span>
    
  ```powershell
  UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
  ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
  LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
  ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
  ```

 > [!NOTE]
><span data-ttu-id="b938f-157">Имена столбцов и их порядок в первой строке CSV-файла являются произвольными, но убедитесь, что данные в остальном файле соответствуют порядку имен столбцов, и используйте имена столбцов для значений параметров в команде PowerShell для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b938f-157">The column names and their order in the first row of the CSV file are arbitrary, but make sure the data in the rest of the file matches the order of the column names, and use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="b938f-158">Используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="b938f-158">Use the following syntax:</span></span>
    
  ```powershell
  Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
  ```

<span data-ttu-id="b938f-159">Этот пример кода создает учетные записи пользователей на основе файла NewAccounts.csv (C:\My Documents\NewAccounts.csv) и записывает результаты в файл NewAccountResults.csv (C:\My Documents\NewAccountResults.csv).</span><span class="sxs-lookup"><span data-stu-id="b938f-159">This example creates the user accounts from the file named C:\My Documents\NewAccounts.csv, and logs the results in the file named C:\My Documents\NewAccountResults.csv</span></span>
    
  ```powershell
  Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
  ```

3. <span data-ttu-id="b938f-160">Результаты можно просмотреть в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="b938f-160">Review the output file to see the results.</span></span> <span data-ttu-id="b938f-161">Мы не указали пароли, поэтому случайные пароли, созданные Microsoft 365, отображаются в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="b938f-161">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b938f-162">См. также</span><span class="sxs-lookup"><span data-stu-id="b938f-162">See also</span></span>

[<span data-ttu-id="b938f-163">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b938f-163">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b938f-164">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="b938f-164">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="b938f-165">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b938f-165">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
