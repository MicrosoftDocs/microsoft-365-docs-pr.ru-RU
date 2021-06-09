---
title: Создание Microsoft 365 учетных записей пользователей с помощью PowerShell
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
description: Использование PowerShell для создания отдельных или нескольких Microsoft 365 учетных записей пользователей.
ms.openlocfilehash: c3676acdec3bbba328809ee1528206bbc44f94f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907568"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="6be6a-103">Создание Microsoft 365 учетных записей пользователей с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6be6a-103">Create Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="6be6a-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="6be6a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6be6a-105">Вы можете использовать PowerShell для Microsoft 365 для эффективного создания учетных записей пользователей, в том числе нескольких учетных записей.</span><span class="sxs-lookup"><span data-stu-id="6be6a-105">You can use PowerShell for Microsoft 365 to efficiently create user accounts, including multiple accounts.</span></span>

<span data-ttu-id="6be6a-106">При создании учетных записей пользователей в PowerShell всегда требуются определенные свойства учетных записей.</span><span class="sxs-lookup"><span data-stu-id="6be6a-106">When you create user accounts in PowerShell, certain account properties are always required.</span></span> <span data-ttu-id="6be6a-107">Другие свойства не требуются, но важны.</span><span class="sxs-lookup"><span data-stu-id="6be6a-107">Other properties aren't required but are important.</span></span> <span data-ttu-id="6be6a-108">См. следующую таблицу.</span><span class="sxs-lookup"><span data-stu-id="6be6a-108">See the following table.</span></span>
  
|<span data-ttu-id="6be6a-109">**Имя свойства**</span><span class="sxs-lookup"><span data-stu-id="6be6a-109">**Property name**</span></span>|<span data-ttu-id="6be6a-110">**Обязательный?**</span><span class="sxs-lookup"><span data-stu-id="6be6a-110">**Required?**</span></span>|<span data-ttu-id="6be6a-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6be6a-111">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6be6a-112">**DisplayName**</span><span class="sxs-lookup"><span data-stu-id="6be6a-112">**DisplayName**</span></span> <br/> |<span data-ttu-id="6be6a-113">Да</span><span class="sxs-lookup"><span data-stu-id="6be6a-113">Yes</span></span>  <br/> |<span data-ttu-id="6be6a-114">Это имя отображения, которое используется в Microsoft 365 службах.</span><span class="sxs-lookup"><span data-stu-id="6be6a-114">This is the display name that's used in Microsoft 365 services.</span></span> <span data-ttu-id="6be6a-115">Например, *Caleb Sills*.</span><span class="sxs-lookup"><span data-stu-id="6be6a-115">For example, *Caleb Sills*.</span></span> <br/> |
|<span data-ttu-id="6be6a-116">**UserPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="6be6a-116">**UserPrincipalName**</span></span> <br/> |<span data-ttu-id="6be6a-117">Да</span><span class="sxs-lookup"><span data-stu-id="6be6a-117">Yes</span></span>  <br/> |<span data-ttu-id="6be6a-118">Это имя учетной записи, используемой для регистрации Microsoft 365 служб.</span><span class="sxs-lookup"><span data-stu-id="6be6a-118">This is the account name that's used to sign in to Microsoft 365 services.</span></span> <span data-ttu-id="6be6a-119">Например, *CalebS \@ contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="6be6a-119">For example, *CalebS\@contoso.onmicrosoft.com*.</span></span>  <br/> |
|<span data-ttu-id="6be6a-120">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="6be6a-120">**FirstName**</span></span> <br/> |<span data-ttu-id="6be6a-121">Нет</span><span class="sxs-lookup"><span data-stu-id="6be6a-121">No</span></span>  <br/> ||
|<span data-ttu-id="6be6a-122">**LastName**</span><span class="sxs-lookup"><span data-stu-id="6be6a-122">**LastName**</span></span> <br/> |<span data-ttu-id="6be6a-123">Нет</span><span class="sxs-lookup"><span data-stu-id="6be6a-123">No</span></span>  <br/> ||
|<span data-ttu-id="6be6a-124">**LicenseAssignment**</span><span class="sxs-lookup"><span data-stu-id="6be6a-124">**LicenseAssignment**</span></span> <br/> |<span data-ttu-id="6be6a-125">Нет</span><span class="sxs-lookup"><span data-stu-id="6be6a-125">No</span></span>  <br/> |<span data-ttu-id="6be6a-126">Это план лицензирования (также известный как план лицензии или SKU), из которого доступная лицензия назначена учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="6be6a-126">This is the licensing plan (also known as the license plan or SKU) from which an available license is assigned to the user account.</span></span> <span data-ttu-id="6be6a-127">Лицензия определяет Microsoft 365 службы, доступные для учетной записи.</span><span class="sxs-lookup"><span data-stu-id="6be6a-127">The license defines the Microsoft 365 services that are available to the account.</span></span> <span data-ttu-id="6be6a-128">При создании учетной записи пользователю не нужно назначать лицензию, но у учетной записи должна быть лицензия на доступ к Microsoft 365 службам.</span><span class="sxs-lookup"><span data-stu-id="6be6a-128">You don't have to assign a license to a user when you create the account, but the account must have a license to access Microsoft 365 services.</span></span> <span data-ttu-id="6be6a-129">Лицензию требуется добавить в течение 30 дней после создания учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="6be6a-129">You have 30 days to license the user account after you create it.</span></span> |
|<span data-ttu-id="6be6a-130">**Password**</span><span class="sxs-lookup"><span data-stu-id="6be6a-130">**Password**</span></span> <br/> |<span data-ttu-id="6be6a-131">Нет</span><span class="sxs-lookup"><span data-stu-id="6be6a-131">No</span></span>  <br/> | <span data-ttu-id="6be6a-132">Если пароль не указан, случайный пароль назначен учетной записи пользователя, и пароль отображается в результатах команды.</span><span class="sxs-lookup"><span data-stu-id="6be6a-132">If you don't specify a password, a random password is assigned to the user account, and the password is visible in the results of the command.</span></span> <span data-ttu-id="6be6a-133">Если указать пароль, он должен быть от 8 до 16 текстовых символов ASCII следующих типов: буквы нижнего регистра, верхние буквы, цифры и символы.</span><span class="sxs-lookup"><span data-stu-id="6be6a-133">If you specify a password, it needs to be 8 to 16 ASCII text characters of the following types: lowercase letters, uppercase letters, numbers, and symbols.</span></span><br/> |
|<span data-ttu-id="6be6a-134">**UsageLocation**</span><span class="sxs-lookup"><span data-stu-id="6be6a-134">**UsageLocation**</span></span> <br/> |<span data-ttu-id="6be6a-135">Нет</span><span class="sxs-lookup"><span data-stu-id="6be6a-135">No</span></span>  <br/> |<span data-ttu-id="6be6a-136">Это допустимый код страны согласно ISO 3166-1 alpha-2 (например, US для США и FR для Франции).</span><span class="sxs-lookup"><span data-stu-id="6be6a-136">This is a valid ISO 3166-1 alpha-2 country code.</span></span> <span data-ttu-id="6be6a-137">Например, *США* для США и *FR* для Франции.</span><span class="sxs-lookup"><span data-stu-id="6be6a-137">For example, *US* for the United States, and *FR* for France.</span></span> <span data-ttu-id="6be6a-138">Важно предоставить это значение, так как некоторые Microsoft 365 службы недоступны в некоторых странах.</span><span class="sxs-lookup"><span data-stu-id="6be6a-138">It's important to provide this value, because some Microsoft 365 services aren't available in certain countries.</span></span> <span data-ttu-id="6be6a-139">Вы не можете назначить лицензию учетной записи пользователя, если эта учетная запись не настроена.</span><span class="sxs-lookup"><span data-stu-id="6be6a-139">You can't assign a license to a user account unless the account has this value configured.</span></span> <span data-ttu-id="6be6a-140">Дополнительные сведения см. [в дополнительных сведениях об ограничениях лицензии.](https://go.microsoft.com/fwlink/p/?LinkId=691730)</span><span class="sxs-lookup"><span data-stu-id="6be6a-140">For more information, see [About license restrictions](https://go.microsoft.com/fwlink/p/?LinkId=691730).</span></span><br/> |

>[!Note]
><span data-ttu-id="6be6a-141">[Узнайте, как создавать учетные записи пользователей](../admin/add-users/add-users.md) с помощью Microsoft 365 центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="6be6a-141">[Learn how to create user accounts](../admin/add-users/add-users.md) by using the Microsoft 365 admin center.</span></span>
> 
> <span data-ttu-id="6be6a-142">Список дополнительных ресурсов см. в списке [Управление пользователями и группами.](../admin/add-users/index.yml)</span><span class="sxs-lookup"><span data-stu-id="6be6a-142">For a list of additional resources, see [Manage users and groups](../admin/add-users/index.yml).</span></span>
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="6be6a-143">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="6be6a-143">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="6be6a-144">[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="6be6a-144">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="6be6a-145">После подключения используйте следующий синтаксис для создания отдельной учетной записи:</span><span class="sxs-lookup"><span data-stu-id="6be6a-145">After you connect, use the following syntax to create an individual account:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

<span data-ttu-id="6be6a-146">В этом примере создается учетная запись для американского пользователя *Caleb Sills:*</span><span class="sxs-lookup"><span data-stu-id="6be6a-146">This example creates an account for the US user *Caleb Sills*:</span></span>
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="6be6a-147">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6be6a-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="6be6a-148">[Во-первых, подключите Microsoft 365 клиента.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="6be6a-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="create-an-individual-user-account"></a><span data-ttu-id="6be6a-149">Создание одной учетной записи пользователя</span><span class="sxs-lookup"><span data-stu-id="6be6a-149">Create an individual user account</span></span>

<span data-ttu-id="6be6a-150">Чтобы создать одну учетную запись, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="6be6a-150">To create an individual account, use the following syntax:</span></span>
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
><span data-ttu-id="6be6a-151">PowerShell Core не поддерживает модуль Microsoft Azure Active Directory для Windows PowerShell и командлетов с *Msol* в их имени.</span><span class="sxs-lookup"><span data-stu-id="6be6a-151">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets that have *Msol* in their name.</span></span> <span data-ttu-id="6be6a-152">Эти командлеты требуется запускать из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6be6a-152">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="6be6a-153">Чтобы предоставить список доступных имен плана лицензирования, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6be6a-153">To list the available licensing plan names, use this command:</span></span>

````powershell
Get-MsolAccountSku
````

<span data-ttu-id="6be6a-154">В этом примере создается учетная запись для американского пользователя *Caleb Sills* и назначается лицензия из плана лицензирования `contoso:ENTERPRISEPACK` (Office 365 корпоративный E3).</span><span class="sxs-lookup"><span data-stu-id="6be6a-154">This example creates an account for the US user *Caleb Sills*, and assigns a license from the `contoso:ENTERPRISEPACK` (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a><span data-ttu-id="6be6a-155">Создание нескольких учетных записей пользователей</span><span class="sxs-lookup"><span data-stu-id="6be6a-155">Create multiple user accounts</span></span>

1. <span data-ttu-id="6be6a-p108">Создайте CSV-файл, который содержит обязательные сведения об учетных записях пользователей. Пример:</span><span class="sxs-lookup"><span data-stu-id="6be6a-p108">Create a comma-separated value (CSV) file that contains the required user account information. For example:</span></span>

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   ><span data-ttu-id="6be6a-158">Имена столбцов и их порядок в первом ряду CSV-файла являются произвольными.</span><span class="sxs-lookup"><span data-stu-id="6be6a-158">The column names and their order in the first row of the CSV file are arbitrary.</span></span> <span data-ttu-id="6be6a-159">Но убедитесь, что порядок данных в остальном файле соответствует порядку имен столбцов.</span><span class="sxs-lookup"><span data-stu-id="6be6a-159">But make sure the order of the data in the rest of the file matches the order of the column names.</span></span> <span data-ttu-id="6be6a-160">И используйте имена столбцов для значений параметров в PowerShell для Microsoft 365 команды.</span><span class="sxs-lookup"><span data-stu-id="6be6a-160">And use the column names for the parameter values in the PowerShell for Microsoft 365 command.</span></span>
    
2. <span data-ttu-id="6be6a-161">Используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="6be6a-161">Use the following syntax:</span></span>
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   <span data-ttu-id="6be6a-162">В этом примере создаются учетные записи пользователей из файла *C:\My Documents\NewAccounts.csv* и журналы результатов в файле *C:\My Documents\NewAccountResults.csv.*</span><span class="sxs-lookup"><span data-stu-id="6be6a-162">This example creates user accounts from the file *C:\My Documents\NewAccounts.csv* and logs the results in a file named *C:\My Documents\NewAccountResults.csv*.</span></span>
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. <span data-ttu-id="6be6a-163">Результаты можно просмотреть в выходном файле.</span><span class="sxs-lookup"><span data-stu-id="6be6a-163">Review the output file to see the results.</span></span> <span data-ttu-id="6be6a-164">Мы не указали пароли, поэтому случайные пароли, Microsoft 365 созданные, видны в файле вывода.</span><span class="sxs-lookup"><span data-stu-id="6be6a-164">We didn't specify passwords, so the random passwords that Microsoft 365 generated are visible in the output file.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6be6a-165">См. также</span><span class="sxs-lookup"><span data-stu-id="6be6a-165">See also</span></span>

[<span data-ttu-id="6be6a-166">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6be6a-166">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6be6a-167">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="6be6a-167">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="6be6a-168">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6be6a-168">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)