---
title: Использование поиска контента в Office 365 для целевых коллекций
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
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: Используйте поиск контента в центре безопасности & соответствия требованиям для выполнения целевых коллекций. Целевая коллекция означает, что вы уверены, что элементы, реагирующие на обращение или привилегированные элементы, расположены в определенном почтовом ящике или папке сайта. Используйте сценарий, описанный в этой статье, чтобы получить идентификатор или путь к определенному почтовому ящику или папкам сайтов, в которых требуется выполнить поиск.
ms.openlocfilehash: 02cd78f9ebb02f7c41e0703ba4ddb78bfd184000
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38687561"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a>Использование поиска контента в Office 365 для целевых коллекций

Функция поиска контента в центре безопасности &amp; Office 365 не предоставляет прямой способ для поиска определенных папок в почтовых ящиках Exchange, а также на сайтах SharePoint и OneDrive для бизнеса. Тем не менее, можно выполнять поиск по определенным папкам (называемым *целевой коллекцией*), УКАЗАВ свойство ID папки для свойства email или Path (документлинк) для сайтов в фактическом синтаксисе поискового запроса. Использование функции поиска контента для выполнения целевой коллекции полезно, если вы уверены, что элементы, реагирующие на обращение или привилегированные элементы, расположены в определенном почтовом ящике или папке сайта. С помощью сценария, описанного в этой статье, можно получить идентификатор папки для папок почтовых ящиков или путь (Документлинк) для папок на сайте SharePoint и OneDrive для бизнеса. Затем вы можете использовать идентификатор или путь к папке в запросе поиска, чтобы вернуть элементы, расположенные в папке.

> [!NOTE]
> Чтобы получить контент, расположенный в папке на сайте SharePoint или OneDrive для бизнеса, сценарий в этом разделе использует управляемое свойство Документлинк вместо свойства Path. Свойство Документлинк является более надежным, чем свойство Path, так как оно возвращает весь контент в папке, а свойство Path не возвращает некоторые файлы мультимедиа.

## <a name="before-you-begin"></a>Перед началом работы

- Вы должны быть участником группы ролей "Диспетчер обнаружения электронных данных" в центре &amp; соответствия требованиям безопасности, чтобы запустить сценарий на шаге 1. Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).
    
    Кроме того, необходимо назначить роль получателей почты в организации Exchange Online. Это необходимо для запуска командлета **Get-MailboxFolderStatistics** , который включен в сценарий, описанный в шаге 1. По умолчанию роль получателей почты назначается группам ролей "Управление организацией" и "Управление получателями" в Exchange Online. Дополнительные сведения о назначении разрешений в Exchange Online содержатся в разделе [Управление участниками группы ролей](https://go.microsoft.com/fwlink/p/?linkid=692102). Вы также можете создать настраиваемую группу ролей, назначить ей роль получателей почты, а затем добавить участников, которым требуется запустить сценарий, на шаге 1. Дополнительные сведения можно найти в разделе [Manage Role Groups](https://go.microsoft.com/fwlink/p/?linkid=730688).
    
- Каждый раз при запуске скрипта на этапе 1 создается новый удаленный сеанс PowerShell. Поэтому можно использовать все удаленные сеансы PowerShell. Чтобы избежать этого, можно выполнить следующую команду, чтобы отключить активные сеансы удаленной оболочки PowerShell.
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Дополнительные сведения см. в статье [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
- Сценарий включает в себя минимальную обработку ошибок. Основной целью сценария является быстрое отображение списка идентификаторов папок почтовых ящиков или путей сайтов, которые можно использовать в синтаксисе запроса поиска контента для выполнения целевой коллекции.
    
- Пример сценария, представленный в этом разделе, не поддерживается ни в одной из стандартных программ или услуг поддержки Майкрософт. Пример сценария предоставляется без каких-либо гарантий. Кроме того, корпорация Майкрософт отказывается от всех косвенных гарантий товарного качества. Весь риск, возникающий из примера использования или производительности примера сценария и документации, остается без вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации сценариев, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров сценариев или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Шаг 1: запуск скрипта для получения списка папок для почтового ящика или сайта

Скрипт, выполняемый на первом шаге, вернет список папок почтовых ящиков или папок SharePoint и OneDrive для бизнеса, а также соответствующий идентификатор или путь к папке. При выполнении этого сценария будет предложено ввести следующие сведения.
  
- **Адрес электронной почты или URL-адрес сайта** Введите адрес электронной почты хранитель, чтобы получить список папок почтовых ящиков Exchange и идентификаторов папок. Или введите URL-адрес сайта SharePoint или сайта OneDrive для бизнеса, чтобы получить список путей для указанного сайта. Ниже приводятся примеры: 
    
  - **Exchange** — stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive для бизнеса** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **Ваши учетные данные пользователя** : сценарий будет использовать ваши учетные данные для подключения к Exchange Online и центра безопасности & соответствия требованиям с помощью удаленной оболочки PowerShell. Как было сказано выше, для успешного выполнения этого сценария необходимо назначить соответствующие разрешения.
    
Чтобы отобразить список папок почтовых ящиков или документлинк (путей) сайта, выполните следующие действия:
  
1. Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `GetFolderSearchParameters.ps1`.
    
  ```powershell
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security & Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
  #    * for the site.                                                                                  #
  #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)  #
  #      appended to the folder ID or documentlink to use in a Content Search.              #
  # Notes:                                              #
  #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the   #
  #      the current folder and all sub-folders are searched.                       #
  #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder #
  #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
  #      each sub-folder that you want to search.                               #
  #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.       #
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

2. На локальном компьютере откройте Windows PowerShell и перейдите к папке, в которой был сохранен сценарий.
    
3. Запуск скрипта; Например:
    
      ```powershell
      .\GetFolderSearchParameters.ps1
      ```

4. Введите сведения, которые будут запрашиваться сценарием.
    
    В этом сценарии отображается список папок или папок почтового ящика для указанного пользователя. Разрешите это окно, чтобы можно было скопировать идентификатор папки или имя документлинк и вставить его в поисковый запрос на шаге 2.
    
    > [!TIP]
    > Вместо того чтобы отображать список папок на экране компьютера, можно повторно перенаправить выходные данные сценария в текстовый файл. Этот файл будет сохранен в папке, в которой расположен сценарий. Например, чтобы перенаправить выходные данные сценария в текстовый файл, выполните следующую команду на шаге 3: `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` затем вы можете скопировать идентификатор папки или документлинк из файла для использования в поисковый запрос.
  
### <a name="script-output-for-mailbox-folders"></a>Вывод сценариев для папок почтовых ящиков

Если вы получаете идентификаторы папок почтовых ящиков, сценарий подключается к Exchange Online с помощью удаленной оболочки PowerShell, запускает командлет **Get-маилбоксфолдерстатисикс** , а затем отображает список папок из указанного почтового ящика. Для каждой папки в почтовом ящике сценарий отображает имя папки в столбце **FolderPath** и идентификатор папки в столбце **фолдеркуери** . Кроме того, скрипт добавляет префикс **FolderId** (имя свойства почтового ящика) к идентификатору папки. Так как свойство **FolderId** является свойством для поиска, вы будете использовать `folderid:<folderid>` поисковую папку в запросе поиска на шаге 2. В этом сценарии отображается не более 100 папок почтовых ящиков.

> [!IMPORTANT]
> Сценарий, описанный в этой статье, включает логику кодирования, преобразующую значения идентификаторов папок 64-character, которые возвращаются командой **Get-MailboxFolderStatistics** , в тот же формат 48 символов, который индексируется для поиска. Если вы просто выполняете командлет **Get-MailboxFolderStatistics** в PowerShell, чтобы получить идентификатор папки (вместо того, чтобы выполнять сценарий в этой статье), поисковый запрос, в котором используется значение идентификатора этой папки, завершится с ошибками. Для получения правильно отформатированных идентификаторов папок, которые можно использовать при поиске контента, необходимо выполнить сценарий.
  
Ниже приведен пример выходных данных, возвращаемых сценарием для папок почтовых ящиков.
  
![Пример списка папок и идентификаторов папок почтовых ящиков, возвращенных сценарием](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
В примере на шаге 2 показан запрос, используемый для поиска вложенной папки "очистки" в папке "элементы с возможностью восстановления".
  
### <a name="script-output-for-site-folders"></a>Выходные данные сценариев для папок сайта

Если вы получаете путь к свойству **документлинк** из сайтов SharePoint или OneDrive для бизнеса, сценарий подключается к центру безопасности & соответствия требованиям с помощью удаленной оболочки PowerShell, создает новый поиск контента, который выполняет поиск в сайтах для папок, а затем отображает список папок, расположенных на указанном сайте. В этом сценарии отображается имя каждой папки и добавляется префикс **документлинк** к URL-адресу папки. Так как свойство **документлинк** является свойством, поддерживающим Поиск, для `documentlink:<path>` поиска в этой папке используется значение "свойство: значение" в поисковом запросе на шаге 2. В этом сценарии отображается не более 200 папок сайта. Если количество папок сайта превышает 200, отображаются последние из них.
  
Ниже приведен пример выходных данных, возвращаемых сценарием для папок сайта.
  
![Пример списка имен документлинк для папок сайта, возвращаемых сценарием](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Шаг 2: использование идентификатора папки или документлинк для выполнения целевой коллекции

После выполнения сценария для сбора списка идентификаторов папок или документлинкс для определенного пользователя необходимо перейти в центр безопасности & соответствия требованиям и создать новый поиск контента для поиска в определенной папке. В поле ключевое `folderid:<folderid>` слово `documentlink:<path>` поиска контента (или в качестве значения параметра *Контентматчкуери* при использовании командлета **New-ComplianceSearch** ) будет использоваться значение "свойство: значение" в запросе поиска, которое вы настроили. Можно сочетать свойство `folderid` или `documentlink` с другими параметрами поиска или условиями поиска. Если вы включаете в `folderid` запрос `documentlink` только свойство или, то поиск вернет все элементы, расположенные в указанной папке. 
  
1. Перейдите по ссылке [https://protection.office.com](https://protection.office.com).
    
2. Войдите в Office 365, используя учетную запись и учетные данные, которые использовались для запуска скрипта на шаге 1.
    
3. В левой области центра безопасности & соответствия **требованиям выберите** \> поиск **контента**поиска и нажмите **создать** ![значок](media/O365-MDM-CreatePolicy-AddIcon.gif)добавления.
    
4. На странице **Новый поиск** введите имя поиска контента. Это имя должно быть уникальным в пределах организации. 
    
5. В разделе **где вы хотите посмотреть**, выполните одно из следующих действий в зависимости от того, выполняется ли поиск в папке почтовых ящиков или в папке сайта:
    
    - Щелкните **выбрать конкретные почтовые ящики для поиска** , а затем добавьте тот же почтовый ящик, который вы указали при выполнении сценария, описанного в шаге 1. 
    
      или
    
    - Щелкните **выбрать конкретные сайты для поиска** , а затем добавьте тот же URL-адрес сайта, который вы указали при выполнении сценария, описанного в шаге 1. 
    
6. Нажмите кнопку **Далее**.
    
7. В поле ключевое слово на странице **что вы хотите искать** на странице, вставьте значение `folderid:<folderid>` или `documentlink:<path>` значение, возвращенное сценарием на шаге 1. 
    
    Например, запрос на следующем снимке экрана будет искать любой элемент в подпапке "очистки" в папке "элементы с возможностью восстановления" (значение `folderid` свойства для вложенной папки "очистки" отображается на снимке экрана на шаге 1):
    
    ![Вставьте FolderId или документлинк в поле ключевое слово поискового запроса.](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. Нажмите кнопку **Поиск** , чтобы начать поиск целевой коллекции. 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>Примеры запросов поиска для целевых коллекций

Ниже приведено несколько примеров использования свойств `folderid` и `documentlink` в запросе поиска для выполнения целевой коллекции. Обратите внимание, что заполнители `folderid:<folderid>` используются `documentlink:<path>` для хранения и экономии места. 
  
- В этом примере выполняется поиск трех разных папок почтовых ящиков. Аналогичный синтаксис запроса можно использовать для поиска в скрытых папках в папке "элементы с возможностью восстановления".
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- В этом примере выполняется поиск элементов, содержащих точную фразу, в папке почтовых ящиков.
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- В этом примере выполняется поиск в папке сайта (и всех вложенных папках) для документов, содержащих буквы "нда" в заголовке.
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- В этом примере выполняется поиск в папке сайта (и любой вложенной папке) для документов, которые были изменены в пределах диапазона дат.
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>Дополнительные сведения

При использовании сценария, описанного в этой статье, следует учитывать следующие моменты для выполнения целевых коллекций.
  
- Сценарий не удаляет папки из результатов. Поэтому некоторые папки, перечисленные в результатах, могут быть недоступными (или возвращать нулевые элементы), так как они содержат содержимое, созданное системой.
    
- Этот сценарий возвращает только сведения о папке для основного почтового ящика пользователя. Он не возвращает сведения о папках в архивном почтовом ящике пользователя.
    
- При поиске в папках почтового ящика Поиск будет выполняться только `folderid` в указанной папке (определяется свойством). Поиск во вложенных папках выполняться не будет. Чтобы выполнить поиск в вложенных папках, необходимо использовать идентификатор папки для вложенной папки, в которой требуется выполнить поиск. 
    
- При поиске в папках сайта папка (определенная ее `documentlink` свойствами) и все вложенные папки будут искаться. 
    
- При экспорте результатов поиска, в которых вы указали только `folderid` свойство в поисковом запросе, вы можете выбрать первый вариант экспорта, "все элементы, кроме тех, которые имеют неизвестный формат, шифруются или не индексируются по другим причинам". Все элементы в папке всегда будут экспортироваться независимо от состояния их индексирования, так как идентификатор папки всегда индексируется.
