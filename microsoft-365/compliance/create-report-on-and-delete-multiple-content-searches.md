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
# <a name="create-report-on-and-delete-multiple-content-searches"></a>Создание и удаление нескольких поисков содержимого, а также получение отчетов по ним

 Быстрое создание и создание отчетов об обнаружении часто является важным этапом обнаружения электронных данных и расследований, когда вы пытаетесь узнать о данных, а также о его насыщенности и качестве. Для этого PowerShell Центра & безопасности и соответствия требованиям предлагает набор cmdlets для автоматизации задач по поиску контента, отнимающих много времени. Эти сценарии предоставляют быстрый и простой способ создания количества поисковых запросов, а затем запускают отчеты о предполагаемых результатах поиска, которые помогут определить количество данных, о чем идет речь. Вы также можете использовать сценарии для создания различных версий поиска, чтобы сравнить результаты, которые дает каждая из них. Эти сценарии помогут быстро и эффективно идентифицировать и отлаготировать данные.

## <a name="before-you-create-a-content-search"></a>Перед созданием поиска контента

- Для запуска сценариев, описанных в этом разделе, необходимо быть членом группы ролей "Руководитель службы eDiscovery" в Центре безопасности & соответствия требованиям.

- Чтобы получить список URL-адресов сайтов OneDrive для бизнеса в организации, которые можно добавить в CSV-файл на шаге 1, см. статью "Создание списка всех местоположений [OneDrive](https://docs.microsoft.com/onedrive/list-onedrive-urls)в организации".

- Не забудьте сохранить все файлы, которые вы создали в этом разделе, в одной папке. Это упростит запуск сценариев.

- Сценарии включают минимальную обработку ошибок. Их основная цель — быстрое создание, создание отчетов и удаление нескольких поисков контента.

- Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>Шаг 1. Создайте CSV-файл, содержащий сведения о поиске, который нужно выполнить

CSV-файл, который создается на этом шаге, содержит строку для каждого пользователя, который хочет найти. Вы можете искать в почтовом ящике пользователя Exchange Online (который включает архивный почтовый ящик, если он включен) и на сайте OneDrive для бизнеса. Вы также можете искать только в почтовом ящике или на сайте OneDrive для бизнеса. Вы также можете искать любой сайт в организации SharePoint Online. Сценарий, который вы запустите в шаге 3, создаст отдельный поиск для каждой строки в CSV-файле.

1. Скопируйте и в paste следующий текст в TXT-файл с помощью Блокнота. Сохраните этот файл в папке на локальном компьютере. Остальные сценарии также будут сохраняться в этой папке.

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   В первой строке файла (строке загона) перечислены параметры, которые будут использоваться с помощью cmdlet **New-ComplianceSearch** (в сценарии на шаге 3) для создания нового запроса на поиск контента. Имена параметров отделяются друг от друга запятыми. Убедитесь, что в строке header нет пробелов. Каждая строка под строкой header представляет значения параметров для каждого поиска. Не забудьте заменить данные-замещатель в CSV-файле фактическими данными.

2. Откройте TXT-файл в Excel и воспользуйтесь сведениями из следующей таблицы, чтобы изменить файл с информацией для каждого поиска.

   ****

   |Параметр|Описание|
   |---|---|
   |`ExchangeLocation`|SMTP-адрес почтового ящика пользователя.|
   |`SharePointLocation`|URL-адрес сайта OneDrive для бизнеса пользователя или URL-адрес любого сайта в организации. Для URL-адреса сайтов OneDrive для бизнеса используйте такой ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` формат: Пример: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.|
   |`ContentMatchQuery`|Поисковый запрос для поиска. Дополнительные сведения о создании поискового запроса см. в статье "Запросы по ключевым словам и условия поиска [контента".](keyword-queries-and-search-conditions.md)|
   |`StartDate`|Для электронной почты дата или дата, когда сообщение было получено получателем или отправлено отправищиком. Для документов на сайтах SharePoint или OneDrive для бизнеса дата последнего изменения документа.|
   |`EndDate`|Для электронной почты дата отправки сообщения пользователем или до нее. Для документов на сайтах SharePoint или OneDrive для бизнеса дата последнего изменения документа.|
   |

3. Сохраните файл Excel в CSV-файле в папку на локальном компьютере. Сценарий, который вы создали на шаге 3, будет использовать сведения из этого CSV-файла для создания поисковых запросов.

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Шаг 2. Подключение к PowerShell в Центре безопасности и соответствия требованиям

Следующий шаг — подключение к PowerShell в Центре безопасности и соответствия требованиям вашей организации. Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>Шаг 3. Запуск скрипта для создания и запуска поиска

Сценарий на этом шаге создаст отдельный поиск контента для каждой строки в CSV-файле, созданном на шаге 1. При запуске этого сценария вам будет предложено в двух значениях:

- **ИД группы поиска** — это имя позволяет легко организовать поиск, созданный из CSV-файла. Каждый созданный поиск имеет имя с ИД группы поиска, а затем к имени поиска будет придан номер. Например, если ввести **ContosoCase** для ИД группы поиска, поиск будет называться **ContosoCase_1,** **ContosoCase_2,** **ContosoCase_3** и т. д. Обратите внимание, что введите имя с чувствительностью к делу. При использовании ИД группы поиска в шагах 4 и 5 необходимо использовать тот же случай, что и при его создания.

- **CSV-файл** — имя CSV-файла, созданного на шаге 1. Не забудьте включить использование полного имени файла, включив расширение CSV-файла; например,  `ContosoCase.csv` .

Чтобы запустить сценарий, сделайте следующее:

1. Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, `CreateSearches.ps1` . Сохраните файл в той же папке, в которой сохранены другие файлы.

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

2. В Windows PowerShell перейдите в папку, в которой вы сохранили сценарий на предыдущем шаге, а затем запустите сценарий; Например:

   ```Powershell
   .\CreateSearches.ps1
   ```

3. В **запросе "ИД группы** поиска" введите имя группы поиска и нажмите **ввод;** например,  `ContosoCase` . Помните, что это имя с чувствительностью к делу, поэтому его необходимо ввести так же, как и на последующих шагах.

4. В **запросе на исходный CSV-файл** введите имя CSV-файла, включая расширение CSV-файла; например,  `ContosoCase.csv` .

5. Нажмите **ввод,** чтобы продолжить запуск сценария.

   Сценарий отображает ход создания и выполнения поисковых запросов. После выполнения скрипта он возвращается в запрос.

   ![Пример результата выполнения сценария для создания нескольких запросов на поиск соответствий требованиям](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>Шаг 4. Запуск скрипта для создания отчетов о оценках поиска

После создания поисковых запросов необходимо запустить сценарий, который отображает простой отчет о количестве результатов поиска для каждого поиска, созданного на шаге 3. Отчет также включает размер результатов для каждого поиска, а также общее количество попаданий и общий размер всех поисковых запросов. При запуске сценария создания отчетов вам будет предложено ввести ИД группы поиска и имя CSV-файла, если вы хотите сохранить отчет в CSV-файл.

1. Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, `SearchReport.ps1` . Сохраните файл в той же папке, в которой сохранены другие файлы.

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

2. В Windows PowerShell перейдите в папку, в которой вы сохранили сценарий на предыдущем шаге, а затем запустите сценарий; Например:

   ```Powershell
   .\SearchReport.ps1
   ```

3. В **запросе "ИД группы** поиска" введите имя группы поиска и нажмите **ввод;** например. `ContosoCase` Помните, что это имя с чувствительностью к делу, поэтому вам придется ввести его так же, как при написании сценария на шаге 3.

4. В пути к файлу для сохранения отчета в **CSV-файл (оставьте** пустым, чтобы просто отобразить отчет) введите полное имя файла (включая расширение CSV-файла), если вы хотите сохранить отчет в CSV-файл. имя CSV-файла, включая расширение CSV-файла. Например, можно ввести, чтобы сохранить его в текущем каталоге, или сохранить в  `ContosoCaseReport.csv`  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` другой папке. Вы также можете оставить запрос пустым, чтобы отобразить отчет, но не сохранить его в файл.

5. Нажмите клавишу **ВВОД**.

   Сценарий отображает ход создания и выполнения поисковых запросов. После выполнения скрипта отобразится отчет.

   ![Выполнение отчета о поиске для просмотра результатов для группы поиска](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> Если один и тот же почтовый ящик или сайт указан в качестве расположения контента в нескольких поисковых запросах в группе поиска, итоговая оценка результатов в отчете (как для количества элементов, так и для общего размера) может включать результаты для тех же элементов. Это необходимо, так как одно и то же сообщение электронной почты или документ будут учитываться несколько раз, если оно соответствует запросу на поиск в группе поиска.

## <a name="step-5-run-the-script-to-delete-the-searches"></a>Шаг 5. Запуск сценария для удаления поисковых запросов

Так как вы создаете много поисковых запросов, последний сценарий просто упрощает быстрое удаление поисковых запросов, созданных на шаге 3. Как и другие сценарии, этот сценарий также запросит у вас ид группы поиска. При запуске этого сценария все поиски с ИД группы поиска в имени поиска будут удалены.

1. Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, `DeleteSearches.ps1` . Сохраните файл в той же папке, в которой сохранены другие файлы.

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

2. В Windows PowerShell перейдите в папку, в которой вы сохранили сценарий на предыдущем шаге, а затем запустите сценарий; Например:

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. В **запросе "ИД группы** поиска" введите имя группы поиска для поисковых запросов, которые нужно удалить, а затем **нажмите** ввод; например,  `ContosoCase` . Помните, что это имя с чувствительностью к делу, поэтому вам придется ввести его так же, как при написании сценария на шаге 3.

   Сценарий отображает имя каждого удаленного поиска.

   ![Выполните сценарий для удаления поисковых запросов в группе поиска](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
