---
title: Создание и удаление нескольких поисков содержимого, а также получение отчетов по ним
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Сведения об автоматизации задач поиска контента, таких как создание поисковых запросов и выполнение отчетов с помощью скриптов PowerShell в центре безопасности & соответствия требованиям в Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 389cc9e15bc661e967f7af769ac48c4ae6e27228
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817988"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="19ae5-103">Создание и удаление нескольких поисков содержимого, а также получение отчетов по ним</span><span class="sxs-lookup"><span data-stu-id="19ae5-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="19ae5-104">Быстрое создание и составление отчетов о поиске обнаружения часто является важным шагом при попытке получить сведения о базовых данных, а также полноту и качеству поиска.</span><span class="sxs-lookup"><span data-stu-id="19ae5-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="19ae5-105">Чтобы сделать это, в PowerShell центра безопасности & соответствия требованиям предлагается набор командлетов для автоматизации задач поиска контента.</span><span class="sxs-lookup"><span data-stu-id="19ae5-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="19ae5-106">Эти сценарии предоставляют быстрый и простой способ создания ряда операций поиска, а затем запускают отчеты по предполагаемым результатам поиска, которые могут помочь определить количество данных.</span><span class="sxs-lookup"><span data-stu-id="19ae5-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="19ae5-107">Кроме того, вы можете использовать сценарии для создания различных версий поиска для сравнения результатов, создаваемых каждой из них.</span><span class="sxs-lookup"><span data-stu-id="19ae5-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="19ae5-108">Эти сценарии позволяют быстро и эффективно определять и исключать данные.</span><span class="sxs-lookup"><span data-stu-id="19ae5-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span> 
  
## <a name="before-you-create-a-content-search"></a><span data-ttu-id="19ae5-109">Перед созданием поиска контента</span><span class="sxs-lookup"><span data-stu-id="19ae5-109">Before you create a Content Search</span></span>

- <span data-ttu-id="19ae5-110">Для запуска сценариев, описанных в этом разделе, необходимо быть членом группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="19ae5-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span> 
    
- <span data-ttu-id="19ae5-111">Чтобы собрать список URL-адресов сайтов OneDrive для бизнеса в Организации, которые можно добавить в CSV-файл на этапе 1, ознакомьтесь со статьей [Создание списка всех расположений OneDrive в Организации](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span><span class="sxs-lookup"><span data-stu-id="19ae5-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span> 
    
- <span data-ttu-id="19ae5-112">Обязательно сохраните все файлы, созданные в этом разделе, в одну и ту же папку.</span><span class="sxs-lookup"><span data-stu-id="19ae5-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="19ae5-113">Это позволит упростить выполнение сценариев.</span><span class="sxs-lookup"><span data-stu-id="19ae5-113">That will make it easier to run the scripts.</span></span>
    
- <span data-ttu-id="19ae5-114">Сценарии включают минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="19ae5-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="19ae5-115">Их основной целью является быстрое создание, составление отчетов и удаление нескольких поисков контента.</span><span class="sxs-lookup"><span data-stu-id="19ae5-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>
    
- <span data-ttu-id="19ae5-116">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span><span class="sxs-lookup"><span data-stu-id="19ae5-116">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="19ae5-117">The sample scripts are provided AS IS without warranty of any kind.</span><span class="sxs-lookup"><span data-stu-id="19ae5-117">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="19ae5-118">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span><span class="sxs-lookup"><span data-stu-id="19ae5-118">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="19ae5-119">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span><span class="sxs-lookup"><span data-stu-id="19ae5-119">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="19ae5-120">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span><span class="sxs-lookup"><span data-stu-id="19ae5-120">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="19ae5-121">Шаг 1: создание CSV-файла, содержащего сведения о искомых запросах</span><span class="sxs-lookup"><span data-stu-id="19ae5-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="19ae5-122">Файл значений с разделителями-запятыми (CSV), который вы создаете в этом шаге, содержит строку для каждого пользователя, для которого требуется выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="19ae5-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="19ae5-123">Можно выполнить поиск в почтовом ящике Exchange Online пользователя (который включает архивный почтовый ящик, если он включен) и на сайте OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="19ae5-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="19ae5-124">Вы также можете выполнить поиск только в почтовом ящике или на сайте OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="19ae5-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="19ae5-125">Кроме того, можно выполнять поиск на любом сайте в Организации SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="19ae5-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="19ae5-126">Сценарий, выполняемый на шаге 3, создаст отдельный поиск для каждой строки в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="19ae5-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span> 
  
1. <span data-ttu-id="19ae5-127">Скопируйте и вставьте приведенный ниже текст в текстовый файл с помощью блокнота.</span><span class="sxs-lookup"><span data-stu-id="19ae5-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="19ae5-128">Сохраните этот файл в папку на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="19ae5-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="19ae5-129">Кроме того, вы также сохраните другие сценарии в этой папке.</span><span class="sxs-lookup"><span data-stu-id="19ae5-129">You'll save the other scripts to this folder as well.</span></span>
    
    ```text
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    <span data-ttu-id="19ae5-130">В первой строке (строке заголовков) файла перечислены параметры, которые будут использоваться командлетом **New-ComplianceSearch** (в скрипте, указанном в шаге 3), чтобы создать новый поиск контента.</span><span class="sxs-lookup"><span data-stu-id="19ae5-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="19ae5-131">Имена параметров отделяются друг от друга запятыми.</span><span class="sxs-lookup"><span data-stu-id="19ae5-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="19ae5-132">Убедитесь, что в строке заголовков нет пробелов.</span><span class="sxs-lookup"><span data-stu-id="19ae5-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="19ae5-133">Каждая строка под строкой заголовков представляет значения параметров для каждого поиска.</span><span class="sxs-lookup"><span data-stu-id="19ae5-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="19ae5-134">Обязательно замените данные заполнителя в CSV-файле фактическими данными.</span><span class="sxs-lookup"><span data-stu-id="19ae5-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span> 
    
2. <span data-ttu-id="19ae5-135">Откройте txt файл в Excel, а затем воспользуйтесь сведениями из следующей таблицы, чтобы изменить файл, используя сведения для каждого поиска.</span><span class="sxs-lookup"><span data-stu-id="19ae5-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span> 
    
    |<span data-ttu-id="19ae5-136">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="19ae5-136">**Parameter**</span></span>|<span data-ttu-id="19ae5-137">**Описание**</span><span class="sxs-lookup"><span data-stu-id="19ae5-137">**Description**</span></span>|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |<span data-ttu-id="19ae5-138">SMTP-адрес почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="19ae5-138">The SMTP address of the user's mailbox.</span></span>  <br/> |
    | `SharePointLocation` <br/> |<span data-ttu-id="19ae5-139">URL-адрес сайта OneDrive для бизнеса пользователя или URL-адрес любого сайта в Организации.</span><span class="sxs-lookup"><span data-stu-id="19ae5-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="19ae5-140">В качестве URL-адреса для сайтов OneDrive для бизнеса используйте следующий формат: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` .</span><span class="sxs-lookup"><span data-stu-id="19ae5-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="19ae5-141">Пример: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span><span class="sxs-lookup"><span data-stu-id="19ae5-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>  <br/> |
    | `ContentMatchQuery` <br/> |<span data-ttu-id="19ae5-142">Поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="19ae5-142">The search query for the search.</span></span> <span data-ttu-id="19ae5-143">Дополнительные сведения о создании поискового запроса можно узнать в статье [запросы ключевых слов и условия поиска контента](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="19ae5-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>  <br/> |
    | `StartDate` <br/> |<span data-ttu-id="19ae5-144">Для электронной почты, дата или время получения сообщения получателем или отправлено отправителем.</span><span class="sxs-lookup"><span data-stu-id="19ae5-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="19ae5-145">Для документов на сайтах SharePoint или OneDrive для бизнеса Дата или время последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="19ae5-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>  <br/> |
    | `EndDate` <br/> |<span data-ttu-id="19ae5-146">Для электронной почты Дата или время до отправки сообщения отправлены пользователем, отправленным пользователем.</span><span class="sxs-lookup"><span data-stu-id="19ae5-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="19ae5-147">Для документов на сайтах SharePoint или OneDrive для бизнеса Дата или время последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="19ae5-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>  <br/> |
   
3. <span data-ttu-id="19ae5-148">Сохраните файл Excel в виде CSV-файла в папке на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="19ae5-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="19ae5-149">Скрипт, созданный на шаге 3, будет использовать сведения из этого CSV-файла для создания запросов поиска.</span><span class="sxs-lookup"><span data-stu-id="19ae5-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span> 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="19ae5-150">Шаг 2. Подключение к PowerShell в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="19ae5-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>
  
<span data-ttu-id="19ae5-151">Следующий шаг — подключение к PowerShell в Центре безопасности и соответствия требованиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="19ae5-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="19ae5-152">Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="19ae5-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="19ae5-153">Если ваша учетная запись Microsoft 365 использует многофакторную проверку подлинности (MFA) или федеративную проверку подлинности, вы не сможете использовать приведенные в предыдущем разделе инструкции по подключению к PowerShell в Центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="19ae5-153">If your Microsoft 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="19ae5-154">В таком случае см. инструкции в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям с использованием многофакторной проверки подлинности](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="19ae5-154">Instead, see the instructions in the topic [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="19ae5-155">Шаг 3: запуск скрипта для создания и запуска операций поиска</span><span class="sxs-lookup"><span data-stu-id="19ae5-155">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="19ae5-156">Сценарий на этом шаге создаст отдельный поиск контента для каждой строки в CSV-файле, созданном на этапе 1.</span><span class="sxs-lookup"><span data-stu-id="19ae5-156">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="19ae5-157">При выполнении этого сценария выводится приглашение указать два значения:</span><span class="sxs-lookup"><span data-stu-id="19ae5-157">When you run this script, you'll be prompted for two values:</span></span>
  
- <span data-ttu-id="19ae5-158">**Идентификатор группы поиска** — это имя обеспечивает простой способ упорядочения операций поиска, создаваемых из CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="19ae5-158">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="19ae5-159">Каждый созданный Поиск называется ИДЕНТИФИКАТОРом группы поиска, а затем к имени поиска добавляется номер.</span><span class="sxs-lookup"><span data-stu-id="19ae5-159">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="19ae5-160">Например, если ввести **контосокасе** для идентификатора группы поиска, поиск будет называться **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**и т. д.</span><span class="sxs-lookup"><span data-stu-id="19ae5-160">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="19ae5-161">Обратите внимание, что введенное имя задается с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="19ae5-161">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="19ae5-162">При использовании идентификатора группы поиска на этапе 4 и 5 необходимо использовать тот же сценарий, что и при его создании.</span><span class="sxs-lookup"><span data-stu-id="19ae5-162">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span> 
    
- <span data-ttu-id="19ae5-163">**CSV-файл** — имя CSV-файла, созданного в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="19ae5-163">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="19ae5-164">Обязательно укажите полное имя файла, включая расширение CSV-файла; Пример: `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="19ae5-164">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
<span data-ttu-id="19ae5-165">Чтобы запустить сценарий, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="19ae5-165">To run the script:</span></span>

1. <span data-ttu-id="19ae5-166">Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `CreateSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="19ae5-166">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="19ae5-167">Сохраните файл в той же папке, где были сохранены другие файлы.</span><span class="sxs-lookup"><span data-stu-id="19ae5-167">Save the file to the same folder where you saved the other files.</span></span>
    
  ```Powershell
  # Get the Search Group ID and the location of the CSV input file
  $searchGroup = Read-Host 'Search Group ID'
  $csvFile = Read-Host 'Source CSV file'
    
  # Do a quick check to make sure our group name will not collide with other searches
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
    }
    $searchCounter++
  }
    
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }
      
      # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
      $exchangeLocation = $null
      if ( $_.ExchangeLocation)
      {
           $exchangeLocation = $_.ExchangeLocation
      }
    
    # Create and run the search        
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query
    
    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
    }
    Write-Host ""
    
    $searchCounter++
  }
  ```

2. <span data-ttu-id="19ae5-168">В Windows PowerShell перейдите в папку, в которой сохранен сценарий на предыдущем шаге, а затем выполните сценарий. Например:</span><span class="sxs-lookup"><span data-stu-id="19ae5-168">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\CreateSearches.ps1
    ```

3. <span data-ttu-id="19ae5-169">В поле запрос **идентификатора группы поиска** введите имя группы поиска и нажмите клавишу **Ввод**; Пример: `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="19ae5-169">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="19ae5-170">Помните, что в этом имени учитывается регистр, поэтому в последующих шагах необходимо будет ввести его.</span><span class="sxs-lookup"><span data-stu-id="19ae5-170">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>
    
4. <span data-ttu-id="19ae5-171">В командной строки **ИСХОДНОГО CSV-файла** введите имя CSV-файла, включая расширение CSV-файла; Пример: `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="19ae5-171">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
5. <span data-ttu-id="19ae5-172">Нажмите клавишу **Ввод** , чтобы продолжить выполнение скрипта.</span><span class="sxs-lookup"><span data-stu-id="19ae5-172">Press **Enter** to continue running the script.</span></span> 
    
    <span data-ttu-id="19ae5-173">В этом сценарии отображается ход создания и выполнения операций поиска.</span><span class="sxs-lookup"><span data-stu-id="19ae5-173">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="19ae5-174">После завершения выполнения скрипта он возвращается в командную строку.</span><span class="sxs-lookup"><span data-stu-id="19ae5-174">When the script is complete, it returns to the prompt.</span></span> 
    
    ![Пример результата выполнения сценария для создания нескольких запросов на поиск соответствий требованиям](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="19ae5-176">Шаг 4: запуск скрипта для отчета о оценках поиска</span><span class="sxs-lookup"><span data-stu-id="19ae5-176">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="19ae5-177">После создания поискового запроса необходимо выполнить сценарий, в котором отображается простой отчет о количестве найденных совпадений для каждого поиска, созданного на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="19ae5-177">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="19ae5-178">Кроме того, отчет включает размер результатов для каждого поиска и общее количество совпадений и общий размер всех поисков.</span><span class="sxs-lookup"><span data-stu-id="19ae5-178">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="19ae5-179">При запуске скрипта отчетов вам будет предложено указать идентификатор группы поиска и имя CSV-файла, если вы хотите сохранить отчет в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="19ae5-179">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>
  
1. <span data-ttu-id="19ae5-180">Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `SearchReport.ps1` .</span><span class="sxs-lookup"><span data-stu-id="19ae5-180">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="19ae5-181">Сохраните файл в той же папке, где были сохранены другие файлы.</span><span class="sxs-lookup"><span data-stu-id="19ae5-181">Save the file to the same folder where you saved the other files.</span></span>
    
  ```Powershell
  $searchGroup = Read-Host 'Search Group ID'
  $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
  $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
  $allSearchStats = @()
  foreach ($partialObj in $searches)
  {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
  }
  # Calculate the totals
  $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
  # Convert the total size to MB and round to the nearst 100th
  $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
  $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
  # Get the total successful searches and total of all searches
  $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
  $allCount = $allSearchStats.Count
  $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
  # Totals Row
  $totalSearchStats = New-Object PSObject
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
  $allSearchStats += $totalSearchStats
  # Just get the columns we're interested in showing
  $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
  # Print the results to the screen
  $allSearchStatsPrime |ft -AutoSize -Wrap
  # Save the results to a CSV file
  if ($outputFile)
  {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
  }
  ```

2. <span data-ttu-id="19ae5-182">В Windows PowerShell перейдите в папку, в которой сохранен сценарий на предыдущем шаге, а затем выполните сценарий. Например:</span><span class="sxs-lookup"><span data-stu-id="19ae5-182">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\SearchReport.ps1
    ```

3. <span data-ttu-id="19ae5-183">В поле запрос **идентификатора группы поиска** введите имя группы поиска и нажмите клавишу **Ввод**; например `ContosoCase` :.</span><span class="sxs-lookup"><span data-stu-id="19ae5-183">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="19ae5-184">Помните, что в этом имени учитывается регистр, поэтому необходимо ввести его так же, как и при выполнении сценария на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="19ae5-184">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
4. <span data-ttu-id="19ae5-185">В разделе **путь к файлу для сохранения отчета в CSV-файл (оставьте пустым, чтобы просто отобразить отчет)** введите имя файла полного пути имени файла (в том числе CSV-файла), если вы хотите сохранить отчет в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="19ae5-185">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="19ae5-186">Имя CSV-файла, включая расширение CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="19ae5-186">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="19ae5-187">Например, вы можете `ContosoCaseReport.csv` сохранить его в текущем каталоге или ввести в `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` другую папку.</span><span class="sxs-lookup"><span data-stu-id="19ae5-187">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="19ae5-188">Кроме того, вы можете оставить поле приглашения пустым, чтобы отобразить отчет, но не сохранять его в файл.</span><span class="sxs-lookup"><span data-stu-id="19ae5-188">You can also leave the prompt blank to display the report but not save it to a file.</span></span> 
    
5. <span data-ttu-id="19ae5-189">Нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="19ae5-189">Press **Enter**.</span></span>
    
    <span data-ttu-id="19ae5-190">В этом сценарии отображается ход создания и выполнения операций поиска.</span><span class="sxs-lookup"><span data-stu-id="19ae5-190">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="19ae5-191">После завершения выполнения скрипта отображается отчет.</span><span class="sxs-lookup"><span data-stu-id="19ae5-191">When the script is complete, the report is displayed.</span></span> 
    
    ![Выполнение отчета о поиске для просмотра результатов для группы поиска](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> <span data-ttu-id="19ae5-193">Если один и тот же почтовый ящик или сайт указаны в качестве расположения контента в нескольких операциях поиска в группе поиска, то итоговая оценка итоговых результатов в отчете (как для количества элементов, так и для общего размера) может включать в себя результаты для одних и тех же элементов.</span><span class="sxs-lookup"><span data-stu-id="19ae5-193">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="19ae5-194">Это связано с тем, что одно и то же сообщение электронной почты или документ будет учитываться несколько раз, если он соответствует запросу для поиска в группе поиска.</span><span class="sxs-lookup"><span data-stu-id="19ae5-194">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span> 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="19ae5-195">Шаг 5: запуск скрипта для удаления операций поиска</span><span class="sxs-lookup"><span data-stu-id="19ae5-195">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="19ae5-196">Так как вы можете создать большое количество операций поиска, последний сценарий просто упрощает быстрое удаление операций поиска, созданных на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="19ae5-196">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="19ae5-197">Как и в случае с другими сценариями, здесь также запрашивается идентификатор группы поиска.</span><span class="sxs-lookup"><span data-stu-id="19ae5-197">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="19ae5-198">При выполнении этого сценария все операции поиска с ИДЕНТИФИКАТОРом группы поиска в имени поиска будут удалены.</span><span class="sxs-lookup"><span data-stu-id="19ae5-198">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span> 
  
1. <span data-ttu-id="19ae5-199">Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `DeleteSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="19ae5-199">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="19ae5-200">Сохраните файл в той же папке, где были сохранены другие файлы.</span><span class="sxs-lookup"><span data-stu-id="19ae5-200">Save the file to the same folder where you saved the other files.</span></span>
    
  ```Powershell
  # Delete all searches in a search group
  $searchGroup = Read-Host 'Search Group ID'
  Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
  }
  ```

2. <span data-ttu-id="19ae5-201">В Windows PowerShell перейдите в папку, в которой сохранен сценарий на предыдущем шаге, а затем выполните сценарий. Например:</span><span class="sxs-lookup"><span data-stu-id="19ae5-201">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```Powershell
    .\DeleteSearches.ps1
    ```

3. <span data-ttu-id="19ae5-202">В командной **строки введите имя группы поиска для** поиска, который требуется удалить, а затем нажмите клавишу **Ввод**. Пример: `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="19ae5-202">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="19ae5-203">Помните, что в этом имени учитывается регистр, поэтому необходимо ввести его так же, как и при выполнении сценария на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="19ae5-203">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
    <span data-ttu-id="19ae5-204">В этом сценарии отображается имя каждого удаленного поиска.</span><span class="sxs-lookup"><span data-stu-id="19ae5-204">The script displays the name of each search that's deleted.</span></span>
    
    ![Выполните сценарий для удаления поисковых запросов в группе поиска](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
