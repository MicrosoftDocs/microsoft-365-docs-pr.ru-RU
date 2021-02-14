---
title: Создание и удаление нескольких поисков содержимого, а также получение отчетов по ним
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Узнайте, как автоматизировать такие задачи поиска контента, как создание поиска и запуск отчетов с помощью скриптов PowerShell в Центре безопасности & соответствия требованиям в Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c467b8ebc5ad3171347b23cad47f563b3634ee29
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546865"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="bc645-103">Создание и удаление нескольких поисков содержимого, а также получение отчетов по ним</span><span class="sxs-lookup"><span data-stu-id="bc645-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="bc645-104">Быстрое создание и создание отчетов об обнаружении часто является важным этапом обнаружения электронных данных и расследований, когда вы пытаетесь узнать о данных, а также о его насыщенности и качестве.</span><span class="sxs-lookup"><span data-stu-id="bc645-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="bc645-105">Для этого PowerShell Центра & безопасности и соответствия требованиям предлагает набор cmdlets для автоматизации задач по поиску контента, отнимающих много времени.</span><span class="sxs-lookup"><span data-stu-id="bc645-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="bc645-106">Эти сценарии предоставляют быстрый и простой способ создания количества поисковых запросов, а затем запускают отчеты о предполагаемых результатах поиска, которые помогут определить количество данных, о чем идет речь.</span><span class="sxs-lookup"><span data-stu-id="bc645-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="bc645-107">Вы также можете использовать сценарии для создания различных версий поиска, чтобы сравнить результаты, которые дает каждая из них.</span><span class="sxs-lookup"><span data-stu-id="bc645-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="bc645-108">Эти сценарии помогут быстро и эффективно идентифицировать и отлаготировать данные.</span><span class="sxs-lookup"><span data-stu-id="bc645-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span>

## <a name="before-you-create-a-content-search"></a><span data-ttu-id="bc645-109">Перед созданием поиска контента</span><span class="sxs-lookup"><span data-stu-id="bc645-109">Before you create a Content Search</span></span>

- <span data-ttu-id="bc645-110">Для запуска сценариев, описанных в этом разделе, необходимо быть членом группы ролей "Руководитель службы eDiscovery" в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="bc645-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span>

- <span data-ttu-id="bc645-111">Чтобы получить список URL-адресов сайтов OneDrive для бизнеса в организации, которые можно добавить в CSV-файл на шаге 1, см. статью "Создание списка всех местоположений [OneDrive](https://docs.microsoft.com/onedrive/list-onedrive-urls)в организации".</span><span class="sxs-lookup"><span data-stu-id="bc645-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

- <span data-ttu-id="bc645-112">Не забудьте сохранить все файлы, которые вы создали в этом разделе, в одной папке.</span><span class="sxs-lookup"><span data-stu-id="bc645-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="bc645-113">Это упростит запуск сценариев.</span><span class="sxs-lookup"><span data-stu-id="bc645-113">That will make it easier to run the scripts.</span></span>

- <span data-ttu-id="bc645-114">Сценарии включают минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="bc645-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="bc645-115">Их основная цель — быстрое создание, создание отчетов и удаление нескольких поисков контента.</span><span class="sxs-lookup"><span data-stu-id="bc645-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>

- <span data-ttu-id="bc645-p104">Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="bc645-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="bc645-121">Шаг 1. Создайте CSV-файл, содержащий сведения о поиске, который нужно выполнить</span><span class="sxs-lookup"><span data-stu-id="bc645-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="bc645-122">CSV-файл, который создается на этом шаге, содержит строку для каждого пользователя, который хочет найти.</span><span class="sxs-lookup"><span data-stu-id="bc645-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="bc645-123">Вы можете искать в почтовом ящике пользователя Exchange Online (который включает архивный почтовый ящик, если он включен) и на сайте OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="bc645-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="bc645-124">Вы также можете искать только в почтовом ящике или на сайте OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="bc645-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="bc645-125">Вы также можете искать любой сайт в организации SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bc645-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="bc645-126">Сценарий, который вы запустите в шаге 3, создаст отдельный поиск для каждой строки в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="bc645-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span>

1. <span data-ttu-id="bc645-127">Скопируйте и в paste следующий текст в TXT-файл с помощью Блокнота.</span><span class="sxs-lookup"><span data-stu-id="bc645-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="bc645-128">Сохраните этот файл в папке на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bc645-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="bc645-129">Остальные сценарии также будут сохраняться в этой папке.</span><span class="sxs-lookup"><span data-stu-id="bc645-129">You'll save the other scripts to this folder as well.</span></span>

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   <span data-ttu-id="bc645-130">В первой строке файла (строке загона) перечислены параметры, которые будут использоваться с помощью cmdlet **New-ComplianceSearch** (в сценарии на шаге 3) для создания нового запроса на поиск контента.</span><span class="sxs-lookup"><span data-stu-id="bc645-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="bc645-131">Имена параметров отделяются друг от друга запятыми.</span><span class="sxs-lookup"><span data-stu-id="bc645-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="bc645-132">Убедитесь, что в строке header нет пробелов.</span><span class="sxs-lookup"><span data-stu-id="bc645-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="bc645-133">Каждая строка под строкой header представляет значения параметров для каждого поиска.</span><span class="sxs-lookup"><span data-stu-id="bc645-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="bc645-134">Не забудьте заменить данные-замещатель в CSV-файле фактическими данными.</span><span class="sxs-lookup"><span data-stu-id="bc645-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span>

2. <span data-ttu-id="bc645-135">Откройте TXT-файл в Excel и воспользуйтесь сведениями из следующей таблицы, чтобы изменить файл с информацией для каждого поиска.</span><span class="sxs-lookup"><span data-stu-id="bc645-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span>

   ****

   |<span data-ttu-id="bc645-136">Параметр</span><span class="sxs-lookup"><span data-stu-id="bc645-136">Parameter</span></span>|<span data-ttu-id="bc645-137">Описание</span><span class="sxs-lookup"><span data-stu-id="bc645-137">Description</span></span>|
   |---|---|
   |`ExchangeLocation`|<span data-ttu-id="bc645-138">SMTP-адрес почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="bc645-138">The SMTP address of the user's mailbox.</span></span>|
   |`SharePointLocation`|<span data-ttu-id="bc645-139">URL-адрес сайта OneDrive для бизнеса пользователя или URL-адрес любого сайта в организации.</span><span class="sxs-lookup"><span data-stu-id="bc645-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="bc645-140">Для URL-адреса сайтов OneDrive для бизнеса используйте такой ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` формат:</span><span class="sxs-lookup"><span data-stu-id="bc645-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="bc645-141">Пример: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span><span class="sxs-lookup"><span data-stu-id="bc645-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>|
   |`ContentMatchQuery`|<span data-ttu-id="bc645-142">Поисковый запрос для поиска.</span><span class="sxs-lookup"><span data-stu-id="bc645-142">The search query for the search.</span></span> <span data-ttu-id="bc645-143">Дополнительные сведения о создании поискового запроса см. в статье "Запросы по ключевым словам и условия поиска [контента".](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="bc645-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>|
   |`StartDate`|<span data-ttu-id="bc645-144">Для электронной почты дата или дата, когда сообщение было получено получателем или отправлено отправищиком.</span><span class="sxs-lookup"><span data-stu-id="bc645-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="bc645-145">Для документов на сайтах SharePoint или OneDrive для бизнеса дата последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="bc645-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>|
   |`EndDate`|<span data-ttu-id="bc645-146">Для электронной почты дата отправки сообщения пользователем или до нее.</span><span class="sxs-lookup"><span data-stu-id="bc645-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="bc645-147">Для документов на сайтах SharePoint или OneDrive для бизнеса дата последнего изменения документа.</span><span class="sxs-lookup"><span data-stu-id="bc645-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>|
   |

3. <span data-ttu-id="bc645-148">Сохраните файл Excel в CSV-файле в папку на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bc645-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="bc645-149">Сценарий, который вы создали на шаге 3, будет использовать сведения из этого CSV-файла для создания поисковых запросов.</span><span class="sxs-lookup"><span data-stu-id="bc645-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span>

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="bc645-150">Шаг 2. Подключение к PowerShell в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="bc645-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="bc645-151">Следующий шаг — подключение к PowerShell в Центре безопасности и соответствия требованиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bc645-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="bc645-152">Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="bc645-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="bc645-153">Шаг 3. Запуск скрипта для создания и запуска поиска</span><span class="sxs-lookup"><span data-stu-id="bc645-153">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="bc645-154">Сценарий на этом шаге создаст отдельный поиск контента для каждой строки в CSV-файле, созданном на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="bc645-154">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="bc645-155">При запуске этого сценария вам будет предложено в двух значениях:</span><span class="sxs-lookup"><span data-stu-id="bc645-155">When you run this script, you'll be prompted for two values:</span></span>

- <span data-ttu-id="bc645-156">**ИД группы поиска** — это имя позволяет легко организовать поиск, созданный из CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="bc645-156">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="bc645-157">Каждый созданный поиск имеет имя с ИД группы поиска, а затем к имени поиска будет придан номер.</span><span class="sxs-lookup"><span data-stu-id="bc645-157">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="bc645-158">Например, если ввести **ContosoCase** для ИД группы поиска, поиск будет называться **ContosoCase_1,** **ContosoCase_2,** **ContosoCase_3** и т. д.</span><span class="sxs-lookup"><span data-stu-id="bc645-158">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="bc645-159">Обратите внимание, что введите имя с чувствительностью к делу.</span><span class="sxs-lookup"><span data-stu-id="bc645-159">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="bc645-160">При использовании ИД группы поиска в шагах 4 и 5 необходимо использовать тот же случай, что и при его создания.</span><span class="sxs-lookup"><span data-stu-id="bc645-160">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span>

- <span data-ttu-id="bc645-161">**CSV-файл** — имя CSV-файла, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="bc645-161">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="bc645-162">Не забудьте включить использование полного имени файла, включив расширение CSV-файла; например,  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="bc645-162">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

<span data-ttu-id="bc645-163">Чтобы запустить сценарий, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="bc645-163">To run the script:</span></span>

1. <span data-ttu-id="bc645-164">Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, `CreateSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="bc645-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="bc645-165">Сохраните файл в той же папке, в которой сохранены другие файлы.</span><span class="sxs-lookup"><span data-stu-id="bc645-165">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="bc645-166">В Windows PowerShell перейдите в папку, в которой вы сохранили сценарий на предыдущем шаге, а затем запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="bc645-166">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\CreateSearches.ps1
   ```

3. <span data-ttu-id="bc645-167">В **запросе "ИД группы** поиска" введите имя группы поиска и нажмите **ввод;** например,  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="bc645-167">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="bc645-168">Помните, что это имя с чувствительностью к делу, поэтому его необходимо ввести так же, как и на последующих шагах.</span><span class="sxs-lookup"><span data-stu-id="bc645-168">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>

4. <span data-ttu-id="bc645-169">В **запросе на исходный CSV-файл** введите имя CSV-файла, включая расширение CSV-файла; например,  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="bc645-169">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

5. <span data-ttu-id="bc645-170">Нажмите **ввод,** чтобы продолжить запуск сценария.</span><span class="sxs-lookup"><span data-stu-id="bc645-170">Press **Enter** to continue running the script.</span></span>

   <span data-ttu-id="bc645-171">Сценарий отображает ход создания и выполнения поисковых запросов.</span><span class="sxs-lookup"><span data-stu-id="bc645-171">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="bc645-172">После выполнения скрипта он возвращается в запрос.</span><span class="sxs-lookup"><span data-stu-id="bc645-172">When the script is complete, it returns to the prompt.</span></span>

   ![Пример результата выполнения сценария для создания нескольких запросов на поиск соответствий требованиям](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="bc645-174">Шаг 4. Запуск скрипта для создания отчетов о оценках поиска</span><span class="sxs-lookup"><span data-stu-id="bc645-174">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="bc645-175">После создания поисковых запросов необходимо запустить сценарий, который отображает простой отчет о количестве результатов поиска для каждого поиска, созданного на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="bc645-175">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="bc645-176">Отчет также включает размер результатов для каждого поиска, а также общее количество попаданий и общий размер всех поисковых запросов.</span><span class="sxs-lookup"><span data-stu-id="bc645-176">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="bc645-177">При запуске сценария создания отчетов вам будет предложено ввести ИД группы поиска и имя CSV-файла, если вы хотите сохранить отчет в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="bc645-177">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>

1. <span data-ttu-id="bc645-178">Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, `SearchReport.ps1` .</span><span class="sxs-lookup"><span data-stu-id="bc645-178">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="bc645-179">Сохраните файл в той же папке, в которой сохранены другие файлы.</span><span class="sxs-lookup"><span data-stu-id="bc645-179">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="bc645-180">В Windows PowerShell перейдите в папку, в которой вы сохранили сценарий на предыдущем шаге, а затем запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="bc645-180">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\SearchReport.ps1
   ```

3. <span data-ttu-id="bc645-181">В **запросе "ИД группы** поиска" введите имя группы поиска и нажмите **ввод;** например. `ContosoCase`</span><span class="sxs-lookup"><span data-stu-id="bc645-181">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="bc645-182">Помните, что это имя с чувствительностью к делу, поэтому вам придется ввести его так же, как при написании сценария на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="bc645-182">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

4. <span data-ttu-id="bc645-183">В пути к файлу для сохранения отчета в **CSV-файл (оставьте** пустым, чтобы просто отобразить отчет) введите полное имя файла (включая расширение CSV-файла), если вы хотите сохранить отчет в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="bc645-183">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="bc645-184">имя CSV-файла, включая расширение CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="bc645-184">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="bc645-185">Например, можно ввести, чтобы сохранить его в текущем каталоге, или сохранить в  `ContosoCaseReport.csv`  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` другой папке.</span><span class="sxs-lookup"><span data-stu-id="bc645-185">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="bc645-186">Вы также можете оставить запрос пустым, чтобы отобразить отчет, но не сохранить его в файл.</span><span class="sxs-lookup"><span data-stu-id="bc645-186">You can also leave the prompt blank to display the report but not save it to a file.</span></span>

5. <span data-ttu-id="bc645-187">Нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="bc645-187">Press **Enter**.</span></span>

   <span data-ttu-id="bc645-188">Сценарий отображает ход создания и выполнения поисковых запросов.</span><span class="sxs-lookup"><span data-stu-id="bc645-188">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="bc645-189">После выполнения скрипта отобразится отчет.</span><span class="sxs-lookup"><span data-stu-id="bc645-189">When the script is complete, the report is displayed.</span></span>

   ![Выполнение отчета о поиске для просмотра результатов для группы поиска](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> <span data-ttu-id="bc645-191">Если один и тот же почтовый ящик или сайт указан в качестве расположения контента в нескольких поисковых запросах в группе поиска, итоговая оценка результатов в отчете (как для количества элементов, так и для общего размера) может включать результаты для тех же элементов.</span><span class="sxs-lookup"><span data-stu-id="bc645-191">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="bc645-192">Это необходимо, так как одно и то же сообщение электронной почты или документ будут учитываться несколько раз, если оно соответствует запросу на поиск в группе поиска.</span><span class="sxs-lookup"><span data-stu-id="bc645-192">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span>

## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="bc645-193">Шаг 5. Запуск сценария для удаления поисковых запросов</span><span class="sxs-lookup"><span data-stu-id="bc645-193">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="bc645-194">Так как вы создаете много поисковых запросов, последний сценарий просто упрощает быстрое удаление поисковых запросов, созданных на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="bc645-194">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="bc645-195">Как и другие сценарии, этот сценарий также запросит у вас ид группы поиска.</span><span class="sxs-lookup"><span data-stu-id="bc645-195">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="bc645-196">При запуске этого сценария все поиски с ИД группы поиска в имени поиска будут удалены.</span><span class="sxs-lookup"><span data-stu-id="bc645-196">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span>

1. <span data-ttu-id="bc645-197">Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, `DeleteSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="bc645-197">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="bc645-198">Сохраните файл в той же папке, в которой сохранены другие файлы.</span><span class="sxs-lookup"><span data-stu-id="bc645-198">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="bc645-199">В Windows PowerShell перейдите в папку, в которой вы сохранили сценарий на предыдущем шаге, а затем запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="bc645-199">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. <span data-ttu-id="bc645-200">В **запросе "ИД группы** поиска" введите имя группы поиска для поисковых запросов, которые нужно удалить, а затем **нажмите** ввод; например,  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="bc645-200">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="bc645-201">Помните, что это имя с чувствительностью к делу, поэтому вам придется ввести его так же, как при написании сценария на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="bc645-201">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

   <span data-ttu-id="bc645-202">Сценарий отображает имя каждого удаленного поиска.</span><span class="sxs-lookup"><span data-stu-id="bc645-202">The script displays the name of each search that's deleted.</span></span>

   ![Выполните сценарий для удаления поисковых запросов в группе поиска](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
