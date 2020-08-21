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
# <a name="create-report-on-and-delete-multiple-content-searches"></a>Создание и удаление нескольких поисков содержимого, а также получение отчетов по ним

 Быстрое создание поисков с обнаружением и создание отчетов часто является важным шагом при обнаружении электронных данных и расследованиях при изучении базовых данных, полной функциональности и качестве ваших поисковых запросов. Для этого в PowerShell в Центре безопасности & соответствия требованиям предоставляется набор командлетов для автоматизации потребляемых времени задач на поиск контента. Эти скрипты позволяют быстро и легко создать ряд поисковых запросов и создавать отчеты предполагаемых результатов поиска, которые помогут определить количество требуемых данных. Кроме того, с помощью этих скриптов можно создавать различные версии поиска, чтобы сравнивать результаты каждого из результатов. Эти сценарии позволят быстро и эффективно определять и расти данные.

## <a name="before-you-create-a-content-search"></a>Подготовка к поиску контента

- Для запуска сценариев, описанных в этом разделе, вы должны быть членом группы ролей "Руководитель службы обнаружения электронных данных" в Центре соответствия требованиям &.

- Сведения о сборе списка URL-адресов сайтов OneDrive для бизнеса в организации, которые вы можете добавить к CSV-файлу на шаге 1, см. в статье ["Создание списка всех расположений OneDrive в организации".](https://docs.microsoft.com/onedrive/list-onedrive-urls)

- Все файлы, создаваемые в этом разделе, должны быть сохранены в одной папке. Это упрощает выполнение сценариев.

- Эти скрипты включают минимальную обработку ошибок. Основная задача — быстрое создание, отчетности и удаление нескольких операций поиска контента.

- Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>Шаг 1. Создайте CSV-файл со сведениями о запросах, которые необходимо выполнить

Файл данных с разделителями-запятыми (CSV),который вы создаете на этом шаге, содержит строку для каждого пользователя, для которого нужно выполнить поиск. Вы можете выполнять поиск в почтовом ящике Exchange Online пользователя (который включает в себя архивный почтовый ящик и его сайт OneDrive для бизнеса). Кроме того, вы можете выполнить поиск только в почтовом ящике или на сайте OneDrive для бизнеса. Вы также можете выполнять поиск на любом сайте в организации SharePoint Online. Сценарий, выполняемый на шаге 3, создает отдельный поиск по каждой строке в файле CSV.

1. Скопируйте и вставьте следующий текст в TXT-файл с помощью Блокнота. Сохраните этот файл в папку на локальном компьютере. Другие сценарии также сохраняются в этой папке.

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   В первой строке (строке заголовков) файла перечислены параметры, которые будут использоваться **командлетом New-ComplianceSearch** (в сценарии на шаге 3) для создания новых операций поиска контента. Имена параметров отделяются друг от друга запятыми. Убедитесь, что в строке заголовка нет пробелов. Каждая строка под строкой заголовков представляет значения параметров для каждой поисковой запрос. Не забудьте заменить заполнитель данных в CSV-файле фактическими данными.

2. Откройте TXT-файл в Excel и воспользуйтесь сведениями из следующей таблицы, чтобы отредактировать файл с данными для каждого поискового запроса.

   ****

   |Параметр|Описание|
   |---|---|
   |`ExchangeLocation`|SMTP-адрес почтового ящика пользователя.|
   |`SharePointLocation`|URL-адрес сайта OneDrive для бизнеса пользователя или URL-адрес любого сайта в организации. Для URL-адреса сайтов OneDrive для бизнеса используется следующий ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` формат: Пример: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.|
   |`ContentMatchQuery`|Поисковый запрос. Дополнительные сведения о создании поискового запроса см. в статье ["Запросы по ключевым словам" и условия поиска контента.](keyword-queries-and-search-conditions.md)|
   |`StartDate`|Для электронной почты: дата внедрения или после него сообщение отправлено отправителем или его после него. Дата последнего изменения документа на сайтах SharePoint или OneDrive для бизнеса.|
   |`EndDate`|Для электронной почты: дата отправки сообщения от пользователя или до того, как было отправлено ее. Дата последнего изменения документа на сайтах SharePoint или OneDrive для бизнеса.|
   |

3. Сохраните файл Excel в формате CSV в папку на локальном компьютере. Сценарий, создаваемый на шаге 3, использует сведения из этого CSV-файла для создания запросов.

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Шаг 2. Подключение к PowerShell в Центре безопасности и соответствия требованиям

Следующий шаг — подключение к PowerShell в Центре безопасности и соответствия требованиям вашей организации. Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>Шаг 3. Запуск сценария для создания и запуска поиска

Сценарий на этом этапе создает отдельный поиск контента для каждой строки в CSV-файле, созданном в действии 1. При выполнении этого сценария вам потребуется указать два значения:

- **Идентификатор группы поиска** — это имя позволяет легко организовать операции поиска, созданные из CSV-файла. При этом каждому создаваемому поиску присваивается имя с идентификатором группы поиска, после чего к имени поиска присваивается номер. Например, если ввести **ContosoCase** для идентификатора группы поиска, то поисковому приглушаются **ContosoCase_1** **ContosoCase_2ContosoCase_3** **и**т. д. Обратите внимание, что введенное имя вводится с учетом регистра. При использовании идентификатора группы поиска на шагах 4 и 5 необходимо использовать тот же регистр, что и при создании группы.

- **CSV-файл** — имя CSV-файла, созданного в действии 1. Не забудьте включить его полное имя. Используйте расширение CSV-файла. Например,  `ContosoCase.csv` .

Чтобы запустить сценарий, сделайте следующее:

1. Сохраните приведенный ниже текст в файле сценария Windows PowerShell, используя суффикс .ps1 в имени файла. Например, `CreateSearches.ps1` . Сохраните файл в той же папке, в которой сохранены другие файлы.

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

2. В Windows PowerShell перейдите к папке, где вы сохранили сценарий на предыдущем шаге, а затем запустите его. Например:

   ```Powershell
   .\CreateSearches.ps1
   ```

3. В запросе **идентификатора группы** поиска введите имя группы поиска и нажмите клавишу **ВВОД;** Например,  `ContosoCase` . Помните, что при вводе имени учитывается регистр, поэтому придется ввести его так же, как на последующих этапах.

4. В **командной строке исходного** CSV-файла введите имя CSV-файла, включая расширение CSV-файла; Например,  `ContosoCase.csv` .

5. Нажмите **клавишу ВВОД,** чтобы продолжить выполнение скрипта.

   Скрипт показывает ход создания и выполнения поисковых запросов. После завершения скрипта запрос возвращается в запрос.

   ![Пример результата выполнения сценария для создания нескольких запросов на поиск соответствий требованиям](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>Шаг 4. Запуск скрипта для отчета об оценке результатов поиска

После создания поисковых запросов необходимо запустить скрипт, отображающий простой отчет о количестве обращений к поиску для каждого запроса, созданного в шаге 3. Отчет также включает в себя размер результатов для каждого поискового запроса, а также общее число совбоев и общий размер всех поисковых запросов. При запуске сценария создания отчетов вам будет предложено введить идентификатор группы поиска и имя CSV-файла, если вы хотите сохранить отчет в CSV-файле.

1. Сохраните приведенный ниже текст в файле сценария Windows PowerShell, используя суффикс .ps1 в имени файла. Например, `SearchReport.ps1` . Сохраните файл в той же папке, в которой сохранены другие файлы.

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

2. В Windows PowerShell перейдите к папке, где вы сохранили сценарий на предыдущем шаге, а затем запустите его. Например:

   ```Powershell
   .\SearchReport.ps1
   ```

3. В запросе **идентификатора группы** поиска введите имя группы поиска и нажмите клавишу **ВВОД;** Например:  `ContosoCase` . Помните, что при запуске сценария на шаге 3 придется вводить его так же, как и при запуске.

4. В **пути к файлу, чтобы сохранить отчет в виде CSV-файла (оставьте поле пустым для отображения отчета)** в командной строке запроса, введите имя файла с полным именем (включая расширение CSV), если хотите сохранить отчет в CSV-файл. имя CSV-файла с расширением CSV. Например, можно ввести для  `ContosoCaseReport.csv` сохранения его в текущем каталоге или ввести  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` его сохранение в другой папке. Можно также оставить запрос пустым для отображения отчета, но не сохранять его в файле.

5. Нажмите клавишу **ВВОД**.

   Скрипт показывает ход создания и выполнения поисковых запросов. После завершения скрипта отобразится отчет.

   ![Выполнение отчета о поиске для просмотра результатов для группы поиска](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> Если один и тот же почтовый ящик или сайт указан как расположение содержимого в нескольких поисках в группе поиска, то общая оценка результатов в отчете (как для числа элементов, так и для общего размера) может включать результаты для одних и тех же элементов. Это вызвано тем, что одно и то же сообщение электронной почты или документ будут учитываться несколько раз, если они соответствуют запросу разных запросов поиска в группе поиска.

## <a name="step-5-run-the-script-to-delete-the-searches"></a>Шаг 5. Запуск сценария для удаления поисковых запросов

Так как вы создаете много поисковых запросов, то последний скрипт только что упрощает удаление поисковых запросов, созданных на шаге 3. Как и в случае с остальными сценариями, он также предлагает указать идентификатор группы поиска. При запуске сценария все поисковые запросы с идентификатором группы поиска в имени поиска будут удалены.

1. Сохраните приведенный ниже текст в файле сценария Windows PowerShell, используя суффикс .ps1 в имени файла. Например, `DeleteSearches.ps1` . Сохраните файл в той же папке, в которой сохранены другие файлы.

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

2. В Windows PowerShell перейдите к папке, где вы сохранили сценарий на предыдущем шаге, а затем запустите его. Например:

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. В **запросе на Ввод идентификатора группы** поиска введите имя группы поиска, чтобы найти результаты поиска, которые требуется удалить, и нажмите **клавишу ВВОД;** Например,  `ContosoCase` . Помните, что при запуске сценария на шаге 3 придется вводить его так же, как и при запуске.

   Скрипт отображает имя каждого удаленного поиска.

   ![Выполните сценарий для удаления поисковых запросов в группе поиска](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
