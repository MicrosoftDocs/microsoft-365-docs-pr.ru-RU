---
title: Создание и удаление нескольких поисков содержимого, а также получение отчетов по ним
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
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
description: Узнайте, как автоматизировать задачи поиска контента, такие как создание поиска и запуск отчетов с помощью сценариев PowerShell в Центре безопасности & соответствия требованиям в Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d748e12942fa2d634f27c04de37ccf5b3ec19297
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845901"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="db18d-103">Создание и удаление нескольких поисков содержимого, а также получение отчетов по ним</span><span class="sxs-lookup"><span data-stu-id="db18d-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="db18d-104">Быстрое создание поисков с обнаружением и создание отчетов часто является важным шагом при обнаружении электронных данных и расследованиях при изучении базовых данных, полной функциональности и качестве ваших поисковых запросов.</span><span class="sxs-lookup"><span data-stu-id="db18d-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="db18d-105">Для этого в PowerShell в Центре безопасности & соответствия требованиям предоставляется набор командлетов для автоматизации потребляемых времени задач на поиск контента.</span><span class="sxs-lookup"><span data-stu-id="db18d-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="db18d-106">Эти скрипты позволяют быстро и легко создать ряд поисковых запросов и создавать отчеты предполагаемых результатов поиска, которые помогут определить количество требуемых данных.</span><span class="sxs-lookup"><span data-stu-id="db18d-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="db18d-107">Кроме того, с помощью этих скриптов можно создавать различные версии поиска, чтобы сравнивать результаты каждого из результатов.</span><span class="sxs-lookup"><span data-stu-id="db18d-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="db18d-108">Эти сценарии позволят быстро и эффективно определять и расти данные.</span><span class="sxs-lookup"><span data-stu-id="db18d-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span>

## <a name="before-you-create-a-content-search"></a><span data-ttu-id="db18d-109">Подготовка к поиску контента</span><span class="sxs-lookup"><span data-stu-id="db18d-109">Before you create a Content Search</span></span>

- <span data-ttu-id="db18d-110">Для запуска сценариев, описанных в этом разделе, вы должны быть членом группы ролей "Руководитель службы обнаружения электронных данных" в Центре соответствия требованиям &.</span><span class="sxs-lookup"><span data-stu-id="db18d-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span>

- <span data-ttu-id="db18d-111">Сведения о сборе списка URL-адресов сайтов OneDrive для бизнеса в организации, которые вы можете добавить к CSV-файлу на шаге 1, см. в статье ["Создание списка всех расположений OneDrive в организации".](https://docs.microsoft.com/onedrive/list-onedrive-urls)</span><span class="sxs-lookup"><span data-stu-id="db18d-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

- <span data-ttu-id="db18d-112">Все файлы, создаваемые в этом разделе, должны быть сохранены в одной папке.</span><span class="sxs-lookup"><span data-stu-id="db18d-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="db18d-113">Это упрощает выполнение сценариев.</span><span class="sxs-lookup"><span data-stu-id="db18d-113">That will make it easier to run the scripts.</span></span>

- <span data-ttu-id="db18d-114">Эти скрипты включают минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="db18d-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="db18d-115">Основная задача — быстрое создание, отчетности и удаление нескольких операций поиска контента.</span><span class="sxs-lookup"><span data-stu-id="db18d-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>

- <span data-ttu-id="db18d-p104">Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="db18d-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="db18d-121">Шаг 1. Создайте CSV-файл со сведениями о запросах, которые необходимо выполнить</span><span class="sxs-lookup"><span data-stu-id="db18d-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="db18d-122">Файл данных с разделителями-запятыми (CSV),который вы создаете на этом шаге, содержит строку для каждого пользователя, для которого нужно выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="db18d-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="db18d-123">Вы можете выполнять поиск в почтовом ящике Exchange Online пользователя (который включает в себя архивный почтовый ящик и его сайт OneDrive для бизнеса).</span><span class="sxs-lookup"><span data-stu-id="db18d-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="db18d-124">Кроме того, вы можете выполнить поиск только в почтовом ящике или на сайте OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="db18d-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="db18d-125">Вы также можете выполнять поиск на любом сайте в организации SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="db18d-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="db18d-126">Сценарий, выполняемый на шаге 3, создает отдельный поиск по каждой строке в файле CSV.</span><span class="sxs-lookup"><span data-stu-id="db18d-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span>

1. <span data-ttu-id="db18d-127">Скопируйте и вставьте следующий текст в TXT-файл с помощью Блокнота.</span><span class="sxs-lookup"><span data-stu-id="db18d-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="db18d-128">Сохраните этот файл в папку на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="db18d-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="db18d-129">Другие сценарии также сохраняются в этой папке.</span><span class="sxs-lookup"><span data-stu-id="db18d-129">You'll save the other scripts to this folder as well.</span></span>

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   <span data-ttu-id="db18d-130">В первой строке (строке заголовков) файла перечислены параметры, которые будут использоваться **командлетом New-ComplianceSearch** (в сценарии на шаге 3) для создания новых операций поиска контента.</span><span class="sxs-lookup"><span data-stu-id="db18d-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="db18d-131">Имена параметров отделяются друг от друга запятыми.</span><span class="sxs-lookup"><span data-stu-id="db18d-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="db18d-132">Убедитесь, что в строке заголовка нет пробелов.</span><span class="sxs-lookup"><span data-stu-id="db18d-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="db18d-133">Каждая строка под строкой заголовков представляет значения параметров для каждой поисковой запрос.</span><span class="sxs-lookup"><span data-stu-id="db18d-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="db18d-134">Не забудьте заменить заполнитель данных в CSV-файле фактическими данными.</span><span class="sxs-lookup"><span data-stu-id="db18d-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span>

2. <span data-ttu-id="db18d-135">Откройте TXT-файл в Excel и воспользуйтесь сведениями из следующей таблицы, чтобы отредактировать файл с данными для каждого поискового запроса.</span><span class="sxs-lookup"><span data-stu-id="db18d-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span>

   ****

   |<span data-ttu-id="db18d-136">Параметр</span><span class="sxs-lookup"><span data-stu-id="db18d-136">Parameter</span></span>|<span data-ttu-id="db18d-137">Описание</span><span class="sxs-lookup"><span data-stu-id="db18d-137">Description</span></span>|
   |---|---|
   |`ExchangeLocation`|<span data-ttu-id="db18d-138">SMTP-адрес почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="db18d-138">The SMTP address of the user's mailbox.</span></span>|
   |`SharePointLocation`|<span data-ttu-id="db18d-139">URL-адрес сайта OneDrive для бизнеса пользователя или URL-адрес любого сайта в организации.</span><span class="sxs-lookup"><span data-stu-id="db18d-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="db18d-140">Для URL-адреса сайтов OneDrive для бизнеса используется следующий ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` формат:</span><span class="sxs-lookup"><span data-stu-id="db18d-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="db18d-141">Пример: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span><span class="sxs-lookup"><span data-stu-id="db18d-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>|
   |`ContentMatchQuery`|<span data-ttu-id="db18d-142">Поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="db18d-142">The search query for the search.</span></span> <span data-ttu-id="db18d-143">Дополнительные сведения о создании поискового запроса см. в статье ["Запросы по ключевым словам" и условия поиска контента.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="db18d-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>|
   |`StartDate`|<span data-ttu-id="db18d-144">Для электронной почты: дата внедрения или после него сообщение отправлено отправителем или его после него.</span><span class="sxs-lookup"><span data-stu-id="db18d-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="db18d-145">Дата последнего изменения документа на сайтах SharePoint или OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="db18d-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>|
   |`EndDate`|<span data-ttu-id="db18d-146">Для электронной почты: дата отправки сообщения от пользователя или до того, как было отправлено ее.</span><span class="sxs-lookup"><span data-stu-id="db18d-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="db18d-147">Дата последнего изменения документа на сайтах SharePoint или OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="db18d-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>|
   |

3. <span data-ttu-id="db18d-148">Сохраните файл Excel в формате CSV в папку на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="db18d-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="db18d-149">Сценарий, создаваемый на шаге 3, использует сведения из этого CSV-файла для создания запросов.</span><span class="sxs-lookup"><span data-stu-id="db18d-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span>

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="db18d-150">Шаг 2. Подключение к PowerShell в Центре безопасности и соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="db18d-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="db18d-151">Следующий шаг — подключение к PowerShell в Центре безопасности и соответствия требованиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="db18d-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="db18d-152">Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="db18d-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="db18d-153">Шаг 3. Запуск сценария для создания и запуска поиска</span><span class="sxs-lookup"><span data-stu-id="db18d-153">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="db18d-154">Сценарий на этом этапе создает отдельный поиск контента для каждой строки в CSV-файле, созданном в действии 1.</span><span class="sxs-lookup"><span data-stu-id="db18d-154">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="db18d-155">При выполнении этого сценария вам потребуется указать два значения:</span><span class="sxs-lookup"><span data-stu-id="db18d-155">When you run this script, you'll be prompted for two values:</span></span>

- <span data-ttu-id="db18d-156">**Идентификатор группы поиска** — это имя позволяет легко организовать операции поиска, созданные из CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="db18d-156">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="db18d-157">При этом каждому создаваемому поиску присваивается имя с идентификатором группы поиска, после чего к имени поиска присваивается номер.</span><span class="sxs-lookup"><span data-stu-id="db18d-157">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="db18d-158">Например, если ввести **ContosoCase** для идентификатора группы поиска, то поисковому приглушаются **ContosoCase_1** **ContosoCase_2ContosoCase_3** **и**т. д.</span><span class="sxs-lookup"><span data-stu-id="db18d-158">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="db18d-159">Обратите внимание, что введенное имя вводится с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="db18d-159">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="db18d-160">При использовании идентификатора группы поиска на шагах 4 и 5 необходимо использовать тот же регистр, что и при создании группы.</span><span class="sxs-lookup"><span data-stu-id="db18d-160">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span>

- <span data-ttu-id="db18d-161">**CSV-файл** — имя CSV-файла, созданного в действии 1.</span><span class="sxs-lookup"><span data-stu-id="db18d-161">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="db18d-162">Не забудьте включить его полное имя. Используйте расширение CSV-файла. Например,  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="db18d-162">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

<span data-ttu-id="db18d-163">Чтобы запустить сценарий, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="db18d-163">To run the script:</span></span>

1. <span data-ttu-id="db18d-164">Сохраните приведенный ниже текст в файле сценария Windows PowerShell, используя суффикс .ps1 в имени файла. Например, `CreateSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="db18d-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="db18d-165">Сохраните файл в той же папке, в которой сохранены другие файлы.</span><span class="sxs-lookup"><span data-stu-id="db18d-165">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="db18d-166">В Windows PowerShell перейдите к папке, где вы сохранили сценарий на предыдущем шаге, а затем запустите его. Например:</span><span class="sxs-lookup"><span data-stu-id="db18d-166">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\CreateSearches.ps1
   ```

3. <span data-ttu-id="db18d-167">В запросе **идентификатора группы** поиска введите имя группы поиска и нажмите клавишу **ВВОД;** Например,  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="db18d-167">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="db18d-168">Помните, что при вводе имени учитывается регистр, поэтому придется ввести его так же, как на последующих этапах.</span><span class="sxs-lookup"><span data-stu-id="db18d-168">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>

4. <span data-ttu-id="db18d-169">В **командной строке исходного** CSV-файла введите имя CSV-файла, включая расширение CSV-файла; Например,  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="db18d-169">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

5. <span data-ttu-id="db18d-170">Нажмите **клавишу ВВОД,** чтобы продолжить выполнение скрипта.</span><span class="sxs-lookup"><span data-stu-id="db18d-170">Press **Enter** to continue running the script.</span></span>

   <span data-ttu-id="db18d-171">Скрипт показывает ход создания и выполнения поисковых запросов.</span><span class="sxs-lookup"><span data-stu-id="db18d-171">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="db18d-172">После завершения скрипта запрос возвращается в запрос.</span><span class="sxs-lookup"><span data-stu-id="db18d-172">When the script is complete, it returns to the prompt.</span></span>

   ![Пример результата выполнения сценария для создания нескольких запросов на поиск соответствий требованиям](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="db18d-174">Шаг 4. Запуск скрипта для отчета об оценке результатов поиска</span><span class="sxs-lookup"><span data-stu-id="db18d-174">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="db18d-175">После создания поисковых запросов необходимо запустить скрипт, отображающий простой отчет о количестве обращений к поиску для каждого запроса, созданного в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="db18d-175">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="db18d-176">Отчет также включает в себя размер результатов для каждого поискового запроса, а также общее число совбоев и общий размер всех поисковых запросов.</span><span class="sxs-lookup"><span data-stu-id="db18d-176">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="db18d-177">При запуске сценария создания отчетов вам будет предложено введить идентификатор группы поиска и имя CSV-файла, если вы хотите сохранить отчет в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="db18d-177">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>

1. <span data-ttu-id="db18d-178">Сохраните приведенный ниже текст в файле сценария Windows PowerShell, используя суффикс .ps1 в имени файла. Например, `SearchReport.ps1` .</span><span class="sxs-lookup"><span data-stu-id="db18d-178">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="db18d-179">Сохраните файл в той же папке, в которой сохранены другие файлы.</span><span class="sxs-lookup"><span data-stu-id="db18d-179">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="db18d-180">В Windows PowerShell перейдите к папке, где вы сохранили сценарий на предыдущем шаге, а затем запустите его. Например:</span><span class="sxs-lookup"><span data-stu-id="db18d-180">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\SearchReport.ps1
   ```

3. <span data-ttu-id="db18d-181">В запросе **идентификатора группы** поиска введите имя группы поиска и нажмите клавишу **ВВОД;** Например:  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="db18d-181">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="db18d-182">Помните, что при запуске сценария на шаге 3 придется вводить его так же, как и при запуске.</span><span class="sxs-lookup"><span data-stu-id="db18d-182">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

4. <span data-ttu-id="db18d-183">В **пути к файлу, чтобы сохранить отчет в виде CSV-файла (оставьте поле пустым для отображения отчета)** в командной строке запроса, введите имя файла с полным именем (включая расширение CSV), если хотите сохранить отчет в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="db18d-183">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="db18d-184">имя CSV-файла с расширением CSV.</span><span class="sxs-lookup"><span data-stu-id="db18d-184">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="db18d-185">Например, можно ввести для  `ContosoCaseReport.csv` сохранения его в текущем каталоге или ввести  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` его сохранение в другой папке.</span><span class="sxs-lookup"><span data-stu-id="db18d-185">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="db18d-186">Можно также оставить запрос пустым для отображения отчета, но не сохранять его в файле.</span><span class="sxs-lookup"><span data-stu-id="db18d-186">You can also leave the prompt blank to display the report but not save it to a file.</span></span>

5. <span data-ttu-id="db18d-187">Нажмите клавишу **ВВОД**.</span><span class="sxs-lookup"><span data-stu-id="db18d-187">Press **Enter**.</span></span>

   <span data-ttu-id="db18d-188">Скрипт показывает ход создания и выполнения поисковых запросов.</span><span class="sxs-lookup"><span data-stu-id="db18d-188">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="db18d-189">После завершения скрипта отобразится отчет.</span><span class="sxs-lookup"><span data-stu-id="db18d-189">When the script is complete, the report is displayed.</span></span>

   ![Выполнение отчета о поиске для просмотра результатов для группы поиска](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> <span data-ttu-id="db18d-191">Если один и тот же почтовый ящик или сайт указан как расположение содержимого в нескольких поисках в группе поиска, то общая оценка результатов в отчете (как для числа элементов, так и для общего размера) может включать результаты для одних и тех же элементов.</span><span class="sxs-lookup"><span data-stu-id="db18d-191">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="db18d-192">Это вызвано тем, что одно и то же сообщение электронной почты или документ будут учитываться несколько раз, если они соответствуют запросу разных запросов поиска в группе поиска.</span><span class="sxs-lookup"><span data-stu-id="db18d-192">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span>

## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="db18d-193">Шаг 5. Запуск сценария для удаления поисковых запросов</span><span class="sxs-lookup"><span data-stu-id="db18d-193">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="db18d-194">Так как вы создаете много поисковых запросов, то последний скрипт только что упрощает удаление поисковых запросов, созданных на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="db18d-194">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="db18d-195">Как и в случае с остальными сценариями, он также предлагает указать идентификатор группы поиска.</span><span class="sxs-lookup"><span data-stu-id="db18d-195">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="db18d-196">При запуске сценария все поисковые запросы с идентификатором группы поиска в имени поиска будут удалены.</span><span class="sxs-lookup"><span data-stu-id="db18d-196">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span>

1. <span data-ttu-id="db18d-197">Сохраните приведенный ниже текст в файле сценария Windows PowerShell, используя суффикс .ps1 в имени файла. Например, `DeleteSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="db18d-197">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="db18d-198">Сохраните файл в той же папке, в которой сохранены другие файлы.</span><span class="sxs-lookup"><span data-stu-id="db18d-198">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="db18d-199">В Windows PowerShell перейдите к папке, где вы сохранили сценарий на предыдущем шаге, а затем запустите его. Например:</span><span class="sxs-lookup"><span data-stu-id="db18d-199">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. <span data-ttu-id="db18d-200">В **запросе на Ввод идентификатора группы** поиска введите имя группы поиска, чтобы найти результаты поиска, которые требуется удалить, и нажмите **клавишу ВВОД;** Например,  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="db18d-200">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="db18d-201">Помните, что при запуске сценария на шаге 3 придется вводить его так же, как и при запуске.</span><span class="sxs-lookup"><span data-stu-id="db18d-201">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

   <span data-ttu-id="db18d-202">Скрипт отображает имя каждого удаленного поиска.</span><span class="sxs-lookup"><span data-stu-id="db18d-202">The script displays the name of each search that's deleted.</span></span>

   ![Выполните сценарий для удаления поисковых запросов в группе поиска](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
