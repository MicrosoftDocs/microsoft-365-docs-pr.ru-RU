---
title: Использование поиска контента для целевых коллекций
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
- M365-security-compliance
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
ms.custom: seo-marvel-apr2020
description: Используйте поиск контента в центре соответствия требованиям Microsoft 365, чтобы выполнять целевые коллекции, которые обеспечивают расположение элементов в определенном почтовом ящике или папке сайта.
ms.openlocfilehash: 0908b8262942e7a1c4d80bc511d4b8cbcc6dc646
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376596"
---
# <a name="use-content-search-for-targeted-collections"></a>Использование поиска контента для целевых коллекций

Функция поиска контента в центре соответствия требованиям Microsoft 365 не предоставляет прямой способ для поиска определенных папок в почтовых ящиках Exchange, а также на сайтах SharePoint и OneDrive для бизнеса. Тем не менее, можно выполнять поиск по определенным папкам (называемым *целевой коллекцией*), УКАЗАВ свойство ID папки для свойства email или Path (документлинк) для сайтов в фактическом синтаксисе поискового запроса. Использование функции поиска контента для выполнения целевой коллекции полезно, если вы уверены, что элементы, реагирующие на обращение или привилегированные элементы, расположены в определенном почтовом ящике или папке сайта. С помощью сценария, описанного в этой статье, можно получить идентификатор папки для папок почтовых ящиков или путь (Документлинк) для папок на сайте SharePoint и OneDrive для бизнеса. Затем вы можете использовать идентификатор или путь к папке в запросе поиска, чтобы вернуть элементы, расположенные в папке.

> [!NOTE]
> Чтобы получить контент, расположенный в папке на сайте SharePoint или OneDrive для бизнеса, сценарий в этом разделе использует управляемое свойство Документлинк вместо свойства Path. Свойство Документлинк является более надежным, чем свойство Path, так как оно возвращает весь контент в папке, а свойство Path не возвращает некоторые файлы мультимедиа.

## <a name="before-you-run-a-targeted-collection"></a>Перед запуском целевой коллекции

- Вы должны быть участником группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & соответствия требованиям для запуска скрипта на шаге 1. Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).

    Кроме того, необходимо назначить роль получателей почты в организации Exchange Online. Это необходимо для запуска командлета **Get-MailboxFolderStatistics** , включенного в сценарий. По умолчанию роль получателей почты назначается группам ролей "Управление организацией" и "Управление получателями" в Exchange Online. Дополнительные сведения о назначении разрешений в Exchange Online содержатся в разделе [Управление участниками группы ролей](https://go.microsoft.com/fwlink/p/?linkid=692102). Вы также можете создать настраиваемую группу ролей, назначить ей роль получателей почты, а затем добавить участников, которым требуется запустить сценарий, на шаге 1. Дополнительные сведения можно найти в разделе [Manage Role Groups](https://go.microsoft.com/fwlink/p/?linkid=730688).

- Сценарий, описанный в этой статье, поддерживает современная проверка подлинности. Вы можете использовать сценарий как есть, если вы используете Microsoft 365 или Microsoft 365 GCC. Если вы являетесь организацией Office 365 Германия, высокоорганизационной организацией Microsoft 365 или Microsoft 365 DoD, вам потребуется изменить сценарий, чтобы успешно запустить его. В частности, необходимо изменить строку `Connect-ExchangeOnline` и использовать параметр *ексчанжеенвиронментнаме* (и соответствующее значение для типа организации) для подключения к Exchange Online PowerShell.  Кроме того, необходимо изменить строку `Connect-IPPSSession` и использовать параметры *ConnectionURI* и *азуреадаусоризатионендпоинтури* (и соответствующие значения для типа организации), чтобы подключиться к PowerShell центра безопасности & соответствия требованиям. Для получения дополнительных сведений ознакомьтесь с примерами, приведенными в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) , и [подключитесь к серверу безопасности & панели управления соответствия требованиям PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).

- Каждый раз при запуске скрипта создается новый удаленный сеанс PowerShell. Это означает, что вы можете использовать все удаленные сеансы PowerShell, доступные вам. Чтобы избежать этого, выполните следующую команду, чтобы отключить активные сеансы удаленной среды PowerShell.

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Дополнительные сведения см. в статье [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

- Сценарий включает в себя минимальную обработку ошибок. Основной целью сценария является быстрое отображение списка идентификаторов папок почтовых ящиков или путей сайтов, которые можно использовать в синтаксисе запроса поиска контента для выполнения целевой коллекции.

- Пример сценария, представленный в этом разделе, не поддерживается ни в одной из стандартных программ или услуг поддержки Майкрософт. Пример сценария предоставляется без каких-либо гарантий. Кроме того, корпорация Майкрософт отказывается от всех подразумеваемых гарантий, включая, но не ограничиваясь указанным, все подразумеваемые гарантии пригодности для продажи или определенной цели. Весь риск, возникающий из примера использования или производительности примера сценария и документации, остается без вас. Корпорация Майкрософт, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценариев, ни при каких обстоятельствах не несут ответственность за какой-либо ущерб (в том числе, ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или неспособностью использовать примеры сценариев и документацию, даже если корпорации Майкрософт известно о возможности нанесения такого ущерба.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Шаг 1: запуск скрипта для получения списка папок для почтового ящика или сайта

Скрипт, выполняемый на первом шаге, вернет список папок почтовых ящиков или папок SharePoint и OneDrive для бизнеса, а также соответствующий идентификатор или путь к папке. При выполнении этого сценария будет предложено ввести следующие сведения.
  
- **Адрес электронной почты или URL-адрес сайта**: введите адрес электронной почты хранитель, чтобы получить список папок почтовых ящиков Exchange и идентификаторов папок. Или введите URL-адрес сайта SharePoint или сайта OneDrive для бизнеса, чтобы получить список путей для указанного сайта. Ниже приводятся примеры:

  - **Exchange**: stacig@contoso. onmicrosoft <spam> <spam> . com

  - **SharePoint**: HTTPS <span>://</span>contoso.SharePoint.com/sites/Marketing 

  - **OneDrive для бизнеса**: HTTPS <span>://</span>Contoso-My.SharePoint.com/Personal/stacig_contoso_onmicrosoft_com 

- **Ваши учетные данные пользователя**: сценарий будет использовать ваши учетные данные для подключения к Exchange Online PowerShell или центр безопасности & безопасности PowerShell с помощью современной проверки подлинности. Как было сказано ранее, вам необходимо назначить соответствующие разрешения для успешного выполнения этого сценария.

Чтобы отобразить список папок почтовых ящиков или документлинк (путей) сайта, выполните следующие действия:
  
1. Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `GetFolderSearchParameters.ps1` .

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
   if ($addressOrSite.IndexOf("@") -ige 0)
   {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Connect to Exchange Online PowerShell
      if (!$ExoSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-ExchangeOnline
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
      # Connect to Security & Compliance Center PowerShell
      if (!$SccSession)
      {
          Import-Module ExchangeOnlineManagement
          Connect-IPPSSession
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

    В этом сценарии отображается список папок или папок почтового ящика для указанного пользователя. Оставьте это окно открытым, чтобы можно было скопировать идентификатор папки или имя документлинк и вставить его в поисковый запрос на шаге 2.

    > [!TIP]
    > Вместо того чтобы отображать список папок на экране компьютера, можно повторно перенаправить выходные данные сценария в текстовый файл. Этот файл будет сохранен в папке, в которой расположен сценарий. Например, чтобы перенаправить выходные данные сценария в текстовый файл, выполните следующую команду на шаге 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` затем вы можете скопировать идентификатор папки или документлинк из файла для использования в поисковый запрос.
  
### <a name="script-output-for-mailbox-folders"></a>Вывод сценариев для папок почтовых ящиков

Если вы получаете идентификаторы папок почтовых ящиков, сценарий подключается к Exchange Online PowerShell, запускает командлет **Get-маилбоксфолдерстатисикс** , а затем отображает список папок из указанного почтового ящика. Для каждой папки в почтовом ящике сценарий отображает имя папки в столбце **FolderPath** и идентификатор папки в столбце **фолдеркуери** . Кроме того, скрипт добавляет префикс **FolderId** (имя свойства почтового ящика) к идентификатору папки. Так как свойство **FolderId** является свойством для поиска, вы будете использовать поисковую  `folderid:<folderid>` папку в запросе поиска на шаге 2. В этом сценарии отображается не более 100 папок почтовых ящиков.

> [!IMPORTANT]
> Сценарий, описанный в этой статье, включает логику кодирования, преобразующую значения идентификаторов папок 64-character, которые возвращаются командой **Get-MailboxFolderStatistics** , в тот же формат 48 символов, который индексируется для поиска. Если вы просто выполняете командлет **Get-MailboxFolderStatistics** в PowerShell, чтобы получить идентификатор папки (вместо того, чтобы выполнять сценарий в этой статье), поисковый запрос, в котором используется значение идентификатора этой папки, завершится с ошибками. Для получения правильно отформатированных идентификаторов папок, которые можно использовать при поиске контента, необходимо выполнить сценарий.
  
Ниже приведен пример выходных данных, возвращаемых сценарием для папок почтовых ящиков.
  
![Пример списка папок и идентификаторов папок почтовых ящиков, возвращенных сценарием](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
В примере на шаге 2 показан запрос, используемый для поиска вложенной папки "очистки" в папке "элементы с возможностью восстановления".
  
### <a name="script-output-for-site-folders"></a>Выходные данные сценариев для папок сайта

Если вы получаете путь к свойству **документлинк** из сайтов SharePoint или OneDrive для бизнеса, сценарий подключается к системе безопасности & соответствии с оболочкой PowerShell, создает новый поиск контента, который ищет папки на сайте, а затем отображает список папок, расположенных на указанном сайте. В этом сценарии отображается имя каждой папки и добавляется префикс **документлинк** к URL-адресу папки. Так как свойство **документлинк** является свойством, `documentlink:<path>` поддерживающим Поиск, для поиска в этой папке используется значение "свойство: значение" в поисковом запросе на шаге 2. В этом сценарии отображается не более 200 папок сайта. Если количество папок сайта превышает 200, отображаются последние из них.
  
Ниже приведен пример выходных данных, возвращаемых сценарием для папок сайта.
  
![Пример списка имен документлинк для папок сайта, возвращаемых сценарием](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Шаг 2: использование идентификатора папки или документлинк для выполнения целевой коллекции

После выполнения сценария для сбора списка идентификаторов папок или ссылок на документы для определенного пользователя необходимо перейти в центр соответствия требованиям Microsoft 365 и создать новый поиск контента для поиска в определенной папке. В  `folderid:<folderid>`  `documentlink:<path>` поле ключевое слово поиска контента (или в качестве значения параметра  *контентматчкуери*  при использовании командлета **New-ComplianceSearch** ) будет использоваться значение "свойство: значение" в запросе поиска, которое вы настроили. Можно сочетать  `folderid`  `documentlink` свойство или с другими параметрами поиска или условиями поиска. Если вы включаете  `folderid`  `documentlink` в запрос только свойство или, то поиск вернет все элементы, расположенные в указанной папке.
  
1. Перейдите на страницу [https://compliance.microsoft.com](https://compliance.microsoft.com) и войдите, используя учетную запись и учетные данные, которые использовались для запуска скрипта на шаге 1.

2. В левой области центра соответствия требованиям щелкните **Показать**  >  **Поиск всего контента**, а затем нажмите кнопку **создать поиск**.

3. В поле **Ключевые слова** вставьте `folderid:<folderid>`  `documentlink:<path>` значение или значение, возвращенное сценарием на шаге 1.

    Например, запрос на следующем снимке экрана будет искать любой элемент в подпапке "очистки" в папке "элементы с возможностью восстановления" (значение `folderid` свойства для вложенной папки "очистки" отображается на снимке экрана на шаге 1):

    ![Вставьте FolderId или документлинк в поле ключевое слово поискового запроса.](../media/FolderIDSearchQuery.png)

4. В разделе **расположения** выберите **определенные расположения** и нажмите кнопку **изменить**.

5. Выполните одно из следующих действий в зависимости от того, выполняется ли поиск в папке почтового ящика или в папке сайта:

    - Рядом с пунктом **Электронная почта Exchange** нажмите кнопку **выбрать пользователей, группы или Teams** , а затем добавьте тот же почтовый ящик, который вы указали при выполнении сценария на шаге 1.

      или

    - Рядом с пунктом **сайты SharePoint** нажмите кнопку **выбрать сайты** , а затем добавьте тот же URL-адрес сайта, который вы указали при выполнении сценария, описанного в шаге 1.

6. После сохранения расположения контента для поиска нажмите кнопку **сохранить & выполнить**, введите имя для поиска контента, а затем нажмите кнопку **сохранить** , чтобы запустить поиск целевой коллекции. 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>Примеры запросов поиска для целевых коллекций

Ниже приведено несколько примеров использования  `folderid` свойств и  `documentlink` в запросе поиска для выполнения целевой коллекции. Заполнители используются для  `folderid:<folderid>` хранения и  `documentlink:<path>` экономии места. 
  
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
  
- Сценарий не удаляет папки из результатов. Поэтому некоторые папки, перечисленные в результатах, могут быть недоступными (или возвращать нулевые элементы), так как они содержат содержимое, созданное системой, или они содержат только вложенные папки, а не элементы почтового ящика.

- Этот сценарий возвращает только сведения о папке для основного почтового ящика пользователя. Он не возвращает сведения о папках в архивном почтовом ящике пользователя. Чтобы получить сведения о папках в архивном почтовом ящике пользователя, можно изменить сценарий. Для этого измените строку, `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` а затем сохраните и запустите измененный скрипт. Это изменение вернет идентификаторы папок и вложенных папок в архивном почтовом ящике пользователя. Чтобы выполнить поиск по всему архивному почтовому ящику, можно подключить все пары свойств идентификатора папки: значение с `OR` оператором в запросе поиска.

- При поиске в папках почтового ящика Поиск будет выполняться только в указанной папке (определяется `folderid` свойством); вложенные папки не будут выполнять поиск. Чтобы найти вложенные папки, необходимо использовать идентификатор папки для вложенной папки, в которой требуется выполнить поиск.

- При поиске в папках сайта папка (определенная ее `documentlink` свойствами) и все вложенные папки будут искаться. 

- При экспорте результатов поиска, в которых вы указали только `folderid` свойство в поисковом запросе, вы можете выбрать первый вариант экспорта, "все элементы, кроме тех, которые имеют неизвестный формат, шифруются или не индексируются по другим причинам". Все элементы в папке всегда будут экспортироваться независимо от состояния их индексирования, так как идентификатор папки всегда индексируется.
