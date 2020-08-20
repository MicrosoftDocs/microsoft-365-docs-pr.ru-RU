---
title: Использование поиска контента для целевых коллекций
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
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: Используйте веб-часть "Поиск контента" в Центре безопасности & соответствия требованиям для выполнения целевых коллекций, которые гарантирует, что элементы будут находиться в определенном почтовом ящике или папке сайта.
ms.openlocfilehash: aa311d0f9226330d9f2d881af6dabbdc6d0a15b5
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814541"
---
# <a name="use-content-search-for-targeted-collections"></a>Использование поиска контента для целевых коллекций

Функция поиска содержимого в Центре соответствия требованиям безопасности не позволяет искать в определенных папках на сайтах SharePoint или &amp; SharePoint и OneDrive для бизнеса на прямом режиме пользовательского интерфейса. Однако можно выполнять поиск в определенных папках (называемых *целевыми коллекциями),* указав свойство идентификатора папки для адреса электронной почты или пути (DocumentLink) для сайтов в синтаксисе запросов поиска. Использование средства "Поиск контента" для выполнения целевой коллекции полезно, если вы уверены, что элементы, отвечающие обращению или привилегированным элементам, находятся в конкретном почтовом ящике или в папке сайта. С помощью скрипта, представленного в этой статье, можно получить идентификатор папки для папок почтового ящика или путь (DocumentLink) для папок на сайте SharePoint и OneDrive для бизнеса. После этого вы можете использовать идентификатор или путь в поисковом запросе для возврата элементов, найденных в папке.

> [!NOTE]
> Чтобы вернуть контент, расположенный в папке на сайте SharePoint или OneDrive для бизнеса, в скрипте из этой статьи используется управляемое свойство DocumentLink вместо свойства Path. Свойство DocumentLink более надежно, чем свойство Path, поскольку оно возвращает все содержимое папки, в то время как свойство Path не возвращает некоторые файлы мультимедиа.

## <a name="before-you-use-content-search"></a>Перед использованием средства "Поиск контента"

- Для выполнения сценария на шаге 1 вы должны быть членом группы ролей "Руководитель службы обнаружения электронных данных" &amp; в Центре соответствия требованиям безопасности. Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).
    
    Кроме того, вам должна быть назначена роль получателей почты в организации Exchange Online. Это необходимо для выполнения командлета **Get-MailboxFolderStatistics,** входящего в состав сценария на шаге 1. Роль получателей почты по умолчанию назначается группам ролей "Управление организацией" и "Управление получателями" в Exchange Online. Дополнительные сведения о назначении разрешений в Exchange Online см. в статье ["Управление участниками группы ролей".](https://go.microsoft.com/fwlink/p/?linkid=692102) Также можно создать настраиваемую группу ролей, назначить ей роль получателей почты, а затем добавить членов, которым потребуется запускать сценарий на шаге 1. Дополнительные сведения см. в разделе ["Управление группами ролей".](https://go.microsoft.com/fwlink/p/?linkid=730688)
    
- При каждом запуске сценария на шаге 1 создается новый сеанс удаленной оболочки PowerShell. Поэтому вы могли использовать все доступные удаленные сеансы PowerShell. Чтобы предотвратить это, можно выполнить следующую команду для отключения активных сеансов PowerShell.
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Дополнительные сведения см. в статье [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- Этот скрипт включает минимальную обработку ошибок. Основная задача сценария — быстро показать идентификаторы папок почтового ящика или пути на сайте, которые можно использовать в синтаксисе запросов поиска контента для выполнения целевой коллекции.
    
- Пример скрипта, представленный в этой статье, не поддерживается ни одной из стандартных программ поддержки или служб Майкрософт. Образец сценария предоставляется "как есть", без каких-либо гарантий. Кроме того, корпорация Майкрософт отказывается от всех подразумеваемых гарантий, включая, но не ограничиваясь указанным, все подразумеваемые гарантии пригодности для продажи или определенной цели. Весь риск, испытывающих использование или производительность примера сценария и документации, возможно, вам также касается. Корпорация Майкрософт, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценариев, ни при каких обстоятельствах не несут ответственность за какой-либо ущерб (в том числе, ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или неспособностью использовать примеры сценариев и документацию, даже если корпорации Майкрософт известно о возможности нанесения такого ущерба.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Шаг 1. Запуск сценария, чтобы получить список папок для почтового ящика или сайта

Сценарий, запускаемый на этом первом шаге, возвратит список папок почтового ящика либо папок SharePoint и OneDrive для бизнеса, а также идентификатор соответствующей папки с идентификатором или путем для каждой папки. При выполнении этого сценария появится следующая информация.
  
- **Адрес электронной почты или URL-адрес сайта** Введите адрес электронной почты для копии, который возвращает список папок и идентификаторов папок почтового ящика Exchange. Если также можно указать URL-адрес сайта SharePoint или сайта OneDrive для бизнеса, чтобы возвращался список путей к указанному сайту. Ниже приводятся примеры: 
    
  - **Exchange** stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive для бизнеса** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **Учетные данные пользователя.** Сценарий будет использовать учетные данные для подключения к Exchange Online и Центра безопасности & соответствия требованиям с помощью удаленной оболочки PowerShell. Как было сказано выше, вам необходимо назначить соответствующие разрешения для успешного выполнения этого сценария.
    
Чтобы отобразить список папок почтового ящика или ссылок документа сайта, необходимо:
  
1. Сохраните приведенный ниже текст в файле сценария Windows PowerShell, используя суффикс .ps1 в имени файла. Например, `GetFolderSearchParameters.ps1` .
    
   ```powershell
   #########################################################################################################
   # This PowerShell script will prompt you for:                                #
   #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
   #      Online and who is an eDiscovery Manager in the Security & Compliance Center.            #
   # The script will then:                                            #
   #    * If an email address is supplied: list the folders for the target mailbox.            #
   #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
   #    * for the site.                                                                                    #
   #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)    #
   #      appended to the folder ID or documentlink to use in a Content Search.                #
   # Notes:                                                #
   #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the     #
   #      the current folder and all sub-folders are searched.                        #
   #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder    #
   #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
   #      each sub-folder that you want to search.                                #
   #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.        #
   #########################################################################################################
   # Collect the target email address or SharePoint Url
   $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
   # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
   if (!$credentials)
   {
      $credentials = Get-Credential
   }
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
   }
   elseif ($addressOrSite.IndexOf("http") -ige 0)
   {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Authenticate with the Security & Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "DocumentLink:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
   }
   else
   {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
   }
   ```

2. На локальном компьютере откройте Windows PowerShell и перейдите к папке, где сохранен сценарий.
    
3. Запустите сценарий. Например:
    
   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. Введите информацию, в которой сценарий предлагает ее.
    
    Скрипт отобразит список папок почтового ящика или папок сайта для указанного пользователя. Оставьте это окно открытым, чтобы можно было скопировать имя папки с идентификатором или документом, и вставьте его в поисковый запрос на шаге 2.
    
    > [!TIP]
    > Вместо отображения списка папок на экране компьютера можно перенаправить выходные данные сценария в текстовый файл. Этот файл будет сохранен в папке, где расположен сценарий. Например, чтобы перенаправить выходные данные сценария в текстовый файл, выполните следующую команду в действии 3: Затем вы можете скопировать идентификатор папки или ссылку на документы из файла  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` для использования в поисковом запросе.
  
### <a name="script-output-for-mailbox-folders"></a>Вывод сценариев для папок почтового ящика

При получении идентификаторов папок почтового ящика сценарий подключается к Exchange Online с помощью удаленной оболочки PowerShell, запускает **командлет Get-MailboxFolderStatisics** и выводит список папок из указанного почтового ящика. Для каждой папки в почтовом ящике в сценарии отображается имя папки в **столбце FolderPath** и идентификатор папки в **столбце FolderQuery.** Кроме того, сценарий добавляет префикс **folderId** (который представляет собой имя свойства почтового ящика) в идентификатор папки. Так как **свойство folderid является** свойством searchable, для поиска в этой папке будет использоваться  `folderid:<folderid>` поисковый запрос на шаге 2. Скрипт отображает не более 100 папок почтового ящика.

> [!IMPORTANT]
> Сценарий в этой статье содержит логику кодирования, которая преобразует значения идентификаторов 64-мепапок, возвращаемые **Get-MailboxFolderStatistics,** в 48-символьный формат, индексируемый для поиска. Если вы только что запустили **командлет Get-MailboxFolderStatistics** в PowerShell, чтобы получить идентификатор папки (вместо выполнения скрипта, представленного в этой статье), поисковый запрос с этим идентификатором будет выполняться ошибкой. Необходимо выполнить сценарий, чтобы получить правильно отформатированные идентификаторы папок, которые можно использовать при поиске контента.
  
Ниже приведен пример выходных данных, возвращаемых сценарием для папок почтовых ящиков.
  
![Пример списка папок почтового ящика и их идентификаторов, возвращаемых сценарием](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
В примере шага 2 показан запрос, используемый для поиска во вложенной папке "Очистка" в папке пользователя "Элементы с возможностью восстановления".
  
### <a name="script-output-for-site-folders"></a>Вывод скриптов для папок сайта

При получении пути к свойству **documentlink** с сайтов SharePoint или OneDrive для бизнеса сценарий подключается к Центру безопасности соответствия требованиям & с помощью удаленного сеанса PowerShell, создает новый поиск контента на сайте, чтобы найти папки на нем, а затем выводит список папок, расположенных на указанном сайте. Скрипт отображает имя каждой папки и добавляет префикс **documentlink** в URL-адрес папки. Так как **свойство documentlink** является свойством, поддерживающим поиск, в поисковом запросе в действии 2 выполняется поиск в `documentlink:<path>` этой папке. Скрипт отображает не более 200 папок сайта. Если папок сайта больше 200, отображаются новейшая из них.
  
Ниже приведен пример выходных данных, возвращаемых скриптом для папок сайта.
  
![Пример списка имен documentlink для папок сайта, возвращаемых скриптом](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Шаг 2. Использование идентификатора папки или ссылки на документы для выполнения целевой коллекции

После выполнения сценария для сбора списка идентификаторов папок или ссылок на документы для определенного пользователя следующее действие переходит в Центр безопасности & соответствия требованиям и создание нового запроса на поиск контента для поиска в определенной папке. Необходимо использовать пару `folderid:<folderid>` "or `documentlink:<path>` property:value" в поисковом запросе, которую вы настроите в поле ключевых слов поиска контента (или как значение *параметра ContentMatchQuery,* **если используется командлет New-ComplianceSearch).** Вы можете объединить  `folderid` или добавить свойство с  `documentlink` другими параметрами поиска или условиями поиска. Если включить в запрос  `folderid` только  `documentlink` свойство или свойство, то поиск возвращает все элементы, найденные в указанной папке. 
  
1. Перейдите по ссылке [https://protection.office.com](https://protection.office.com).
    
2. Войдите с использованием учетной записи и учетных данных, которые использовались для запуска сценария на шаге 1.
    
3. В левой области Центра безопасности & соответствия требованиям щелкните **"Поиск** \> **контента"** и нажмите значок **New** ![ "Добавить". ](../media/O365-MDM-CreatePolicy-AddIcon.gif)
    
4. На странице **Новый поиск** введите имя поиска контента. Это имя должно быть уникальным в пределах организации. 
    
5. В **разделе "Место поиска" выполните**одно из следующих действий в зависимости от того, выполняете ли вы поиск в папке почтового ящика или папке сайта:
    
    - Щелкните **"Выбрать определенные почтовые ящики** для поиска" и добавьте тот же почтовый ящик, который был указан при выполнении сценария на шаге 1. 
    
      ИЛИ
    
    - Щелкните **"Выбор определенных сайтов для поиска"** и добавьте URL-адрес, указанный при выполнении скрипта на шаге 1. 
    
6. Нажмите кнопку **Далее**.
    
7. В поле ключевых слов на **странице "Что вы хотите** искать" вставьте или  `folderid:<folderid>`  `documentlink:<path>` значение, возвращенное сценарием на шаге 1. 
    
    Например, запрос на следующем снимке экрана выполняет поиск любого элемента в подпапке "Очистка" в папке пользователя "Элементы с возможностью восстановления" (значение свойства для вложенной папки "Очистка" отображается на снимке экрана `folderid` на этапе 1) и:.
    
    ![Вставка значения folderid или documentlink в поле ключевого слова поискового запроса](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. Нажмите **кнопку** "Поиск", чтобы запустить целевой поиск в коллекции. 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>Примеры поисковых запросов для целевых коллекций

Ниже приведены некоторые примеры использования  `folderid` и  `documentlink` свойств в поисковом запросе для выполнения целевой коллекции. Обратите внимание, что для экономии места  `folderid:<folderid>` используются  `documentlink:<path>` заполнители. 
  
- В этом примере выполняется поиск в трех разных папках почтового ящика. Для поиска в скрытых папках, подключаемых пользователя, можно использовать сходный синтаксис запросов.
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- В этом примере в папке почтового ящика выполняется поиск элементов, содержащих точную фразу.
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- В этом примере в заголовке выполняется поиск документов, содержащих буквы NDA в заголовке, в папке сайта (и во всех вложенных папках).
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- В этом примере выполняется поиск документов, измененных в пределах диапазона дат, в папке сайта (и во всех вложенных папках).
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>Дополнительные сведения

При использовании скрипта, описанного в этой статье, следует учитывать следующие моменты.
  
- Сценарий не удаляет из результатов папки. Поэтому некоторые папки, перечисленные в результатах, могут быть невисимы (или возвращать нулевые элементы), так как они содержат созданный системой контент.
    
- Этот сценарий возвращает сведения о папке только для основного почтового ящика пользователя. Она не возвращает сведения о папках в архивном почтовом ящике пользователя.
    
- При поиске в папках почтового ящика поиск будет выполняться только в указанных папках (определяемой его  `folderid` свойством) и поиск по вложенным папкам. Для поиска вложенных папок необходимо использовать идентификатор вложенной папки, в которой нужно найти в ней идентификатор вложенной папки. 
    
- Поиск в папках сайта выполняется во всех папках (определяемых свойством) и  `documentlink` всеми вложенных папках. 
    
- При экспорте результатов поиска, в которых было указано только свойство в поисковом запросе, вы можете выбрать первый вариант экспорта "Все элементы, кроме неизвестных формата, зашифрованных или не индексированных по `folderid` другой причине". Все элементы в папке будут экспортироваться всегда независимо от их состояния индексирования, так как идентификатор папки всегда индексируется.
