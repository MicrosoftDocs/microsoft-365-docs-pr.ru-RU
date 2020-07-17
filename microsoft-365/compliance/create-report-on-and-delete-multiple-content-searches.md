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
# <a name="create-report-on-and-delete-multiple-content-searches"></a>Создание и удаление нескольких поисков содержимого, а также получение отчетов по ним

 Быстрое создание и составление отчетов о поиске обнаружения часто является важным шагом при попытке получить сведения о базовых данных, а также полноту и качеству поиска. Чтобы сделать это, в PowerShell центра безопасности & соответствия требованиям предлагается набор командлетов для автоматизации задач поиска контента. Эти сценарии предоставляют быстрый и простой способ создания ряда операций поиска, а затем запускают отчеты по предполагаемым результатам поиска, которые могут помочь определить количество данных. Кроме того, вы можете использовать сценарии для создания различных версий поиска для сравнения результатов, создаваемых каждой из них. Эти сценарии позволяют быстро и эффективно определять и исключать данные. 
  
## <a name="before-you-create-a-content-search"></a>Перед созданием поиска контента

- Для запуска сценариев, описанных в этом разделе, необходимо быть членом группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & соответствия требованиям. 
    
- Чтобы собрать список URL-адресов сайтов OneDrive для бизнеса в Организации, которые можно добавить в CSV-файл на этапе 1, ознакомьтесь со статьей [Создание списка всех расположений OneDrive в Организации](https://docs.microsoft.com/onedrive/list-onedrive-urls). 
    
- Обязательно сохраните все файлы, созданные в этом разделе, в одну и ту же папку. Это позволит упростить выполнение сценариев.
    
- Сценарии включают минимальную обработку ошибок. Их основной целью является быстрое создание, составление отчетов и удаление нескольких поисков контента.
    
- Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>Шаг 1: создание CSV-файла, содержащего сведения о искомых запросах

Файл значений с разделителями-запятыми (CSV), который вы создаете в этом шаге, содержит строку для каждого пользователя, для которого требуется выполнить поиск. Можно выполнить поиск в почтовом ящике Exchange Online пользователя (который включает архивный почтовый ящик, если он включен) и на сайте OneDrive для бизнеса. Вы также можете выполнить поиск только в почтовом ящике или на сайте OneDrive для бизнеса. Кроме того, можно выполнять поиск на любом сайте в Организации SharePoint Online. Сценарий, выполняемый на шаге 3, создаст отдельный поиск для каждой строки в CSV-файле. 
  
1. Скопируйте и вставьте приведенный ниже текст в текстовый файл с помощью блокнота. Сохраните этот файл в папку на локальном компьютере. Кроме того, вы также сохраните другие сценарии в этой папке.
    
    ```text
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    В первой строке (строке заголовков) файла перечислены параметры, которые будут использоваться командлетом **New-ComplianceSearch** (в скрипте, указанном в шаге 3), чтобы создать новый поиск контента. Имена параметров отделяются друг от друга запятыми. Убедитесь, что в строке заголовков нет пробелов. Каждая строка под строкой заголовков представляет значения параметров для каждого поиска. Обязательно замените данные заполнителя в CSV-файле фактическими данными. 
    
2. Откройте txt файл в Excel, а затем воспользуйтесь сведениями из следующей таблицы, чтобы изменить файл, используя сведения для каждого поиска. 
    
    |**Параметр**|**Описание**|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |SMTP-адрес почтового ящика пользователя.  <br/> |
    | `SharePointLocation` <br/> |URL-адрес сайта OneDrive для бизнеса пользователя или URL-адрес любого сайта в Организации. В качестве URL-адреса для сайтов OneDrive для бизнеса используйте следующий формат: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` . Пример: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.  <br/> |
    | `ContentMatchQuery` <br/> |Поисковый запрос. Дополнительные сведения о создании поискового запроса можно узнать в статье [запросы ключевых слов и условия поиска контента](keyword-queries-and-search-conditions.md).  <br/> |
    | `StartDate` <br/> |Для электронной почты, дата или время получения сообщения получателем или отправлено отправителем. Для документов на сайтах SharePoint или OneDrive для бизнеса Дата или время последнего изменения документа.  <br/> |
    | `EndDate` <br/> |Для электронной почты Дата или время до отправки сообщения отправлены пользователем, отправленным пользователем. Для документов на сайтах SharePoint или OneDrive для бизнеса Дата или время последнего изменения документа.  <br/> |
   
3. Сохраните файл Excel в виде CSV-файла в папке на локальном компьютере. Скрипт, созданный на шаге 3, будет использовать сведения из этого CSV-файла для создания запросов поиска. 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a>Шаг 2. Подключение к PowerShell в Центре безопасности и соответствия требованиям
  
Следующий шаг — подключение к PowerShell в Центре безопасности и соответствия требованиям вашей организации. Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
Если ваша учетная запись Microsoft 365 использует многофакторную проверку подлинности (MFA) или федеративную проверку подлинности, вы не сможете использовать приведенные в предыдущем разделе инструкции по подключению к PowerShell в Центре безопасности и соответствия требованиям. В таком случае см. инструкции в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям с использованием многофакторной проверки подлинности](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>Шаг 3: запуск скрипта для создания и запуска операций поиска

Сценарий на этом шаге создаст отдельный поиск контента для каждой строки в CSV-файле, созданном на этапе 1. При выполнении этого сценария выводится приглашение указать два значения:
  
- **Идентификатор группы поиска** — это имя обеспечивает простой способ упорядочения операций поиска, создаваемых из CSV-файла. Каждый созданный Поиск называется ИДЕНТИФИКАТОРом группы поиска, а затем к имени поиска добавляется номер. Например, если ввести **контосокасе** для идентификатора группы поиска, поиск будет называться **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**и т. д. Обратите внимание, что введенное имя задается с учетом регистра. При использовании идентификатора группы поиска на этапе 4 и 5 необходимо использовать тот же сценарий, что и при его создании. 
    
- **CSV-файл** — имя CSV-файла, созданного в шаге 1. Обязательно укажите полное имя файла, включая расширение CSV-файла; Пример: `ContosoCase.csv` .
    
Чтобы запустить сценарий, сделайте следующее:

1. Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `CreateSearches.ps1` . Сохраните файл в той же папке, где были сохранены другие файлы.
    
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

2. В Windows PowerShell перейдите в папку, в которой сохранен сценарий на предыдущем шаге, а затем выполните сценарий. Например:
    
    ```Powershell
    .\CreateSearches.ps1
    ```

3. В поле запрос **идентификатора группы поиска** введите имя группы поиска и нажмите клавишу **Ввод**; Пример: `ContosoCase` . Помните, что в этом имени учитывается регистр, поэтому в последующих шагах необходимо будет ввести его.
    
4. В командной строки **ИСХОДНОГО CSV-файла** введите имя CSV-файла, включая расширение CSV-файла; Пример: `ContosoCase.csv` .
    
5. Нажмите клавишу **Ввод** , чтобы продолжить выполнение скрипта. 
    
    В этом сценарии отображается ход создания и выполнения операций поиска. После завершения выполнения скрипта он возвращается в командную строку. 
    
    ![Пример результата выполнения сценария для создания нескольких запросов на поиск соответствий требованиям](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>Шаг 4: запуск скрипта для отчета о оценках поиска

После создания поискового запроса необходимо выполнить сценарий, в котором отображается простой отчет о количестве найденных совпадений для каждого поиска, созданного на шаге 3. Кроме того, отчет включает размер результатов для каждого поиска и общее количество совпадений и общий размер всех поисков. При запуске скрипта отчетов вам будет предложено указать идентификатор группы поиска и имя CSV-файла, если вы хотите сохранить отчет в CSV-файл.
  
1. Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `SearchReport.ps1` . Сохраните файл в той же папке, где были сохранены другие файлы.
    
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

2. В Windows PowerShell перейдите в папку, в которой сохранен сценарий на предыдущем шаге, а затем выполните сценарий. Например:
    
    ```Powershell
    .\SearchReport.ps1
    ```

3. В поле запрос **идентификатора группы поиска** введите имя группы поиска и нажмите клавишу **Ввод**; например `ContosoCase` :. Помните, что в этом имени учитывается регистр, поэтому необходимо ввести его так же, как и при выполнении сценария на шаге 3.
    
4. В разделе **путь к файлу для сохранения отчета в CSV-файл (оставьте пустым, чтобы просто отобразить отчет)** введите имя файла полного пути имени файла (в том числе CSV-файла), если вы хотите сохранить отчет в CSV-файл. Имя CSV-файла, включая расширение CSV-файла. Например, вы можете `ContosoCaseReport.csv` сохранить его в текущем каталоге или ввести в `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` другую папку. Кроме того, вы можете оставить поле приглашения пустым, чтобы отобразить отчет, но не сохранять его в файл. 
    
5. Нажмите клавишу **ВВОД**.
    
    В этом сценарии отображается ход создания и выполнения операций поиска. После завершения выполнения скрипта отображается отчет. 
    
    ![Выполнение отчета о поиске для просмотра результатов для группы поиска](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> Если один и тот же почтовый ящик или сайт указаны в качестве расположения контента в нескольких операциях поиска в группе поиска, то итоговая оценка итоговых результатов в отчете (как для количества элементов, так и для общего размера) может включать в себя результаты для одних и тех же элементов. Это связано с тем, что одно и то же сообщение электронной почты или документ будет учитываться несколько раз, если он соответствует запросу для поиска в группе поиска. 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a>Шаг 5: запуск скрипта для удаления операций поиска

Так как вы можете создать большое количество операций поиска, последний сценарий просто упрощает быстрое удаление операций поиска, созданных на шаге 3. Как и в случае с другими сценариями, здесь также запрашивается идентификатор группы поиска. При выполнении этого сценария все операции поиска с ИДЕНТИФИКАТОРом группы поиска в имени поиска будут удалены. 
  
1. Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `DeleteSearches.ps1` . Сохраните файл в той же папке, где были сохранены другие файлы.
    
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

2. В Windows PowerShell перейдите в папку, в которой сохранен сценарий на предыдущем шаге, а затем выполните сценарий. Например:
    
    ```Powershell
    .\DeleteSearches.ps1
    ```

3. В командной **строки введите имя группы поиска для** поиска, который требуется удалить, а затем нажмите клавишу **Ввод**. Пример: `ContosoCase` . Помните, что в этом имени учитывается регистр, поэтому необходимо ввести его так же, как и при выполнении сценария на шаге 3.
    
    В этом сценарии отображается имя каждого удаленного поиска.
    
    ![Выполните сценарий для удаления поисковых запросов в группе поиска](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
