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
description: Узнайте, как автоматизировать задачи поиска контента, такие как создание поиска и запуск отчетов с помощью скриптов PowerShell в Центре & соответствия требованиям в Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6155a0bf411cc83fd58291efe7797e7f68370708
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994966"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>Создание и удаление нескольких поисков содержимого, а также получение отчетов по ним

 Быстрое создание и поиск обнаружения отчетов часто является важным шагом в области обнаружения электронных данных и расследований, когда вы пытаетесь узнать о данных, а также о богатстве и качестве поиска. Чтобы помочь вам в этом, Центр & обеспечения соответствия требованиям PowerShell предлагает набор cmdlets для автоматизации трудоемких задач поиска контента. Эти скрипты предоставляют быстрый и простой способ создания нескольких поисковых запросов, а затем запускают отчеты о предполагаемых результатах поиска, которые помогут определить количество данных, о чем идет речь. Вы также можете использовать скрипты для создания различных версий поиска для сравнения результатов, которые каждый из них производит. Эти скрипты помогут вам быстро и эффективно идентифицировать и отоиметь данные.

## <a name="before-you-create-a-content-search"></a>Перед созданием поиска контента

- Для выполнения сценариев, описанных в этой теме, необходимо быть членом группы ролей диспетчера электронных данных в Центре & безопасности.

- Чтобы собрать список URL-адресов для сайтов OneDrive для бизнеса организации, которые можно добавить в CSV-файл в шаге 1, см. в статью Создание списка всех OneDrive расположения в [организации.](/onedrive/list-onedrive-urls)

- Обязательно сохраните все файлы, которые вы создаете в этой теме, в одной папке. Это облегчит запуск скриптов.

- Сценарии включают минимальную обработку ошибок. Их основная цель — быстрое создание, отчет и удаление нескольких поисков контента.

- Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>Шаг 1. Создание CSV-файла, который содержит сведения об поисковых запросах, которые необходимо выполнить

Файл разделенного значения запятой (CSV), который вы создаете на этом шаге, содержит строку для каждого пользователя, который хочет искать. Вы можете искать почтовый ящик Exchange Online пользователя (который включает почтовый ящик архива, если он включен) и OneDrive для бизнеса сайт. Или вы можете искать только почтовый ящик или OneDrive для бизнеса сайт. Вы также можете искать любой сайт в организации SharePoint Online. Сценарий, который вы запустите в шаге 3, создаст отдельный поиск для каждой строки в CSV-файле.

1. Скопируйте и вклейте следующий текст в .txt с помощью NotePad. Сохраните этот файл в папке на локальном компьютере. В этой папке также будут сохраняться другие скрипты.

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   В первой строке или строке заглавной строки файла перечислены параметры, которые будут использоваться в **cmdlet New-ComplianceSearch** (в скрипте в шаге 3) для создания нового поиска контента. Имена параметров отделяются друг от друга запятыми. Убедитесь, что в строке заглавной строки нет пробелов. Каждая строка в строке заглавной строки представляет значения параметров для каждого поиска. Не забудьте заменить данные о месте в CSV-файле фактическими данными.

2. Откройте файл .txt в Excel, а затем используйте сведения в следующей таблице, чтобы изменить файл с информацией для каждого поиска.

   ****

   |Параметр|Описание|
   |---|---|
   |`ExchangeLocation`|SMTP-адрес почтового ящика пользователя.|
   |`SharePointLocation`|URL-адрес для веб-OneDrive для бизнеса пользователя или URL-адрес для любого сайта в организации. Для URL-адреса для OneDrive для бизнеса сайтов используйте этот формат: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` . Пример: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.|
   |`ContentMatchQuery`|Поисковый запрос для поиска. Дополнительные сведения о создании запроса поиска см. в статье Ключевые запросы и условия [поиска для поиска контента.](keyword-queries-and-search-conditions.md)|
   |`StartDate`|Для электронной почты датой или после того, как сообщение было получено получателем или отправлено отправителю. Для документов на SharePoint или OneDrive для бизнеса веб-сайтов дата последнего изменения документа или после нее.|
   |`EndDate`|Для электронной почты дата отправки или до отправки сообщения пользователем. Для документов на SharePoint или OneDrive для бизнеса веб-сайтов дата последнего изменения документа или до нее.|
   |

3. Сохраните Excel как CSV-файл в папку на локальном компьютере. Сценарий, который вы создаете в шаге 3, будет использовать сведения в этом CSV-файле для создания поиска.

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Шаг 2. Подключение к PowerShell в Центре безопасности и соответствия требованиям

Следующий шаг — подключение к PowerShell в Центре безопасности и соответствия требованиям вашей организации. Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell).

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>Шаг 3. Запустите сценарий для создания и запуска поиска

Скрипт на этом шаге создаст отдельный поиск контента для каждой строки в CSV-файле, созданном в шаге 1. При запуске этого сценария вам будет предложено два значения:

- **ID группы** поиска — это имя позволяет легко организовать поиск, созданный из CSV-файла. Каждый созданный поиск называется с ИД группы поиска, а затем к имени поиска примыкает номер. Например, если вы вводите **ContosoCase** для ID группы поиска, поиски именуются **ContosoCase_1,** **ContosoCase_2,** **ContosoCase_3** и т. д. Обратите внимание, что имя, которое вы введите, является чувствительным к делу. При использовании ID группы поиска в шаге 4 и шаге 5 необходимо использовать тот же случай, что и при его создания.

- **CSV-файл** — имя файла CSV, созданного в шаге 1. Обязательно включай полное имя файла, включай расширение .csv; например,  `ContosoCase.csv` .

Чтобы запустить сценарий, сделайте следующее:

1. Сохраните следующий текст в Windows PowerShell скрипта с помощью суффикса .ps1; например, `CreateSearches.ps1` . Сохраните файл в той же папке, в которой сохранены другие файлы.

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

3. В **запросе ID группы поиска** введите имя группы поиска и нажмите **кнопку Ввод;** например,  `ContosoCase` . Помните, что это имя является чувствительным к делу, поэтому на последующих действиях необходимо ввести его таким же образом.

4. В **запросе файла Source CSV** введите имя файла CSV, включая расширение .csv; например,  `ContosoCase.csv` .

5. Нажмите **кнопку Ввод,** чтобы продолжить запуск скрипта.

   Сценарий отображает ход создания и выполнения поиска. После завершения сценария он возвращается к запросу.

   ![Пример результата выполнения сценария для создания нескольких запросов на поиск соответствий требованиям](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>Шаг 4. Запустите скрипт, чтобы сообщить о сметах поиска

После создания поиска следующим шагом является запуск скрипта, отображаемого в простом отчете о количестве просмотров для каждого поиска, созданного в шаге 3. В отчете также содержится размер результатов для каждого поиска, а также общее количество просмотров и общий размер всех поисков. При запуске сценария отчетов вам будет предложено имя группы поиска и имя файла CSV, если вы хотите сохранить отчет в CSV-файл.

1. Сохраните следующий текст в Windows PowerShell скрипта с помощью суффикса .ps1; например, `SearchReport.ps1` . Сохраните файл в той же папке, в которой сохранены другие файлы.

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

3. В **запросе ID группы поиска** введите имя группы поиска и нажмите **кнопку Ввод;** например  `ContosoCase` . Помните, что это имя является чувствительным к делу, поэтому его необходимо ввести так же, как и при 3-м этапе сценария.

4. Чтобы сохранить отчет в **CSV-файле (оставьте** пустым только для отображения отчета) запрос, введите имя файла полного пути имя файла (в том числе расширение .csv файла), если вы хотите сохранить отчет в CSV-файл. имя CSV-файла, включая расширение .csv файла. Например, можно ввести, чтобы сохранить его в текущем каталоге, или ввести, чтобы сохранить его  `ContosoCaseReport.csv`  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` в другой папке. Вы также можете оставить запрос пустым, чтобы отобразить отчет, но не сохранить его в файле.

5. Нажмите клавишу **ВВОД**.

   Сценарий отображает ход создания и выполнения поиска. Когда сценарий завершен, отчет отображается.

   ![Выполнение отчета о поиске для просмотра результатов для группы поиска](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> Если один и тот же почтовый ящик или сайт указан в качестве расположения контента в нескольких поисковых группах, общая оценка результатов в отчете (как по количеству элементов, так и по общему размеру) может включать результаты для тех же элементов. Это потому, что одно и то же сообщение электронной почты или документ будут пересчитываться несколько раз, если он совпадает с запросом для различных поисков в группе поиска.

## <a name="step-5-run-the-script-to-delete-the-searches"></a>Шаг 5. Запустите сценарий для удаления поиска

Так как вы создаете много поисковых запросов, этот последний скрипт просто упрощает быстрое удаление поисковых запросов, созданных в шаге 3. Как и другие скрипты, этот также подсказок для ИД группы поиска. Все поиски с ИД группы поиска в имени поиска будут удалены при запуске этого скрипта.

1. Сохраните следующий текст в Windows PowerShell скрипта с помощью суффикса .ps1; например, `DeleteSearches.ps1` . Сохраните файл в той же папке, в которой сохранены другие файлы.

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

3. В **запросе ID группы** поиска введите имя группы поиска для поисков, которые необходимо удалить, а затем нажмите **кнопку Ввод;** например,  `ContosoCase` . Помните, что это имя является чувствительным к делу, поэтому его необходимо ввести так же, как и при 3-м этапе сценария.

   Сценарий отображает имя каждого удаленного поиска.

   ![Выполните сценарий для удаления поисковых запросов в группе поиска](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
