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
description: Используйте поиск контента в Центре соответствия требованиям Microsoft 365 для выполнения целевых коллекций, которые гарантируют, что элементы находятся в определенном почтовом ящике или папке сайта.
ms.openlocfilehash: 0908b8262942e7a1c4d80bc511d4b8cbcc6dc646
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376596"
---
# <a name="use-content-search-for-targeted-collections"></a>Использование поиска контента для целевых коллекций

Функция "Поиск контента" в Центре соответствия требованиям Microsoft 365 не предоставляет прямой путь в пользовательском интерфейсе для поиска определенных папок в почтовых ящиках Exchange, а также на сайтах SharePoint и OneDrive для бизнеса. Однако можно искать определенные папки (называемые целевой коллекцией), указав свойство ID папки для электронной почты или пути (DocumentLink) для сайтов в фактическом синтаксис запроса поиска. Использование поиска контента для выполнения целевой коллекции полезно, если вы уверены, что элементы, реагирующие на дела или привилегированные элементы, находятся в определенном почтовом ящике или папке сайта. С помощью сценария в этой статье можно получить ИД папки почтовых ящиков или путь (DocumentLink) для папок на сайте SharePoint и OneDrive для бизнеса. Затем можно использовать ИД папки или путь в поисковом запросе, чтобы вернуть элементы, расположенные в папке.

> [!NOTE]
> Для возврата контента, расположенного в папке на сайте SharePoint или OneDrive для бизнеса, сценарий в этом разделе использует управляемое свойство DocumentLink вместо свойства Path. Свойство DocumentLink является более надежным, чем свойство Path, так как оно возвращает все содержимое папки, тогда как свойство Path не возвращает некоторые файлы мультимедиа.

## <a name="before-you-run-a-targeted-collection"></a>Перед запуском целевой коллекции

- Чтобы запустить сценарий на шаге 1, необходимо быть членом группы ролей "Менеджер по обнаружению электронных данных" в Центре безопасности & соответствия требованиям. Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).

    Кроме того, вам должна быть назначена роль получателей почты в организации Exchange Online. Это необходимо для запуска включаемого в сценарий cmdlet **Get-MailboxFolderStatistics.** По умолчанию роль получателей почты назначена группам ролей "Управление организацией" и "Управление получателями" в Exchange Online. Дополнительные сведения о назначении разрешений в Exchange Online см. в под [управлением участников группы ролей.](https://go.microsoft.com/fwlink/p/?linkid=692102) Вы также можете создать настраиваемую группу ролей, назначить для нее роль получателей почты, а затем добавить участников, которым необходимо выполнить сценарий на шаге 1. Дополнительные сведения см. в [под управлением групп ролей.](https://go.microsoft.com/fwlink/p/?linkid=730688)

- Сценарий в этой статье поддерживает современную проверку подлинности. Вы можете использовать сценарий как есть, если вы — microsoft 365 или организация Microsoft 365 GCC. Если вы — организация Office 365 Germany, Microsoft 365 GCC High или Microsoft 365 DoD, вам придется изменить сценарий, чтобы успешно запустить его. В частности, необходимо изменить строку и использовать параметр `Connect-ExchangeOnline` *ExchangeEnvironmentName* (и соответствующее значение для типа организации) для подключения к Exchange Online PowerShell.  Кроме того, необходимо изменить строку и использовать параметры ConnectionUri и `Connect-IPPSSession` *AzureADAuthorizationEndpointUri* (и соответствующие значения для типа организации) для подключения к *PowerShell* Центра безопасности & соответствия требованиям. Дополнительные сведения см. в примерах в [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) Connect to Exchange Online [и Connect to Security & Compliance Center PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)

- При каждом запуске сценария создается новый удаленный сеанс PowerShell. Это означает, что вы можете использовать все доступные удаленные сеансы PowerShell. Чтобы предотвратить это, запустите следующую команду, чтобы отключить активные удаленные сеансы PowerShell.

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Дополнительные сведения см. в статье [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

- Сценарий включает минимальную обработку ошибок. Основная цель сценария — быстрое отображение списка ИД папок почтовых ящиков или путей к сайту, которые можно использовать в синтаксисах поисковых запросов поиска контента для выполнения целевой коллекции.

- Пример сценария, предоставленный в этом разделе, не поддерживается ни в одной стандартной программе или службе поддержки Майкрософт. Пример сценария приводится в виде "как есть", без каких-либо гарантий. Кроме того, корпорация Microsoft отказывается от всех подразумеваемых гарантий, включая в том числе все подразумеваемые гарантии пригодности для продажи или определенной цели. Все риски, возникающие в результате использования примера сценария и документации, берет на себя пользователь. Корпорация Майкрософт, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценариев, ни при каких обстоятельствах не несут ответственность за какой-либо ущерб (в том числе, ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или неспособностью использовать примеры сценариев и документацию, даже если корпорации Майкрософт известно о возможности нанесения такого ущерба.
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Шаг 1. Запуск сценария для получения списка папок для почтового ящика или сайта

Сценарий, который вы запустите на этом первом этапе, возвращает список папок почтовых ящиков или папок SharePoint и OneDrive для бизнеса, а также соответствующий ид папки или путь для каждой папки. При запуске этого сценария вам будут предложены следующие сведения.
  
- **Адрес электронной почты или URL-адрес** сайта: введите адрес электронной почты хранителя, чтобы получить список папок и папок почтовых ящиков Exchange. Или введите URL-адрес сайта SharePoint или сайта OneDrive для бизнеса, чтобы получить список путей для указанного сайта. Ниже приводятся примеры:

  - **Exchange**: stacig@contoso.onmicrosoft <spam> <spam> .com

  - **SharePoint**: https <span>://</span>contoso.sharepoint.com/sites/marketing 

  - **OneDrive для бизнеса**: https <span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 

- **Учетные** данные пользователя: сценарий будет использовать ваши учетные данные для подключения к Exchange Online PowerShell или PowerShell Центра безопасности и & соответствия требованиям с использованием современной проверки подлинности. Как объяснялось ранее, для успешного запуска этого сценария вам должны быть назначены соответствующие разрешения.

Чтобы отобразить список папок почтовых ящиков или имен документов сайта (пути):
  
1. Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, `GetFolderSearchParameters.ps1` .

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

2. На локальном компьютере откройте Windows PowerShell и перейдите в папку, в которой сохранен сценарий.

3. Запустите сценарий; Например:

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. Введите сведения, которые вам будет предложено ввести в сценарии.

    Сценарий отображает список папок почтовых ящиков или папок сайта для указанного пользователя. Оставьте это окно открытым, чтобы вы могли скопировать ИД папки или имя ссылки на документ и вставьте его в поисковый запрос на шаге 2.

    > [!TIP]
    > Вместо отображения списка папок на экране компьютера можно перенаправить выходные данные сценария в текстовый файл. Этот файл будет сохранен в папке, в которой находится сценарий. Например, чтобы перенаправить выходные данные сценария в текстовый файл, запустите следующую команду на шаге 3. Затем можно скопировать из файла ИД папки или ссылку на документ для использования в поисковом  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` запросе.
  
### <a name="script-output-for-mailbox-folders"></a>Выходные данные скрипта для папок почтовых ящиков

Если вы получаете коды папок почтовых ящиков, сценарий подключается к Exchange Online PowerShell, запускается cmdlet **Get-MailboxFolderStatisics,** а затем отображается список папок из указанного почтового ящика. Для каждой папки в почтовом ящике сценарий отображает имя папки в столбце **FolderPath** и ее ИД в столбце **FolderQuery.** Кроме того, сценарий добавляет префикс **folderId** (который является именем свойства почтового ящика) в ИД папки. Так как **свойство folderid** является свойством, которое можно найти, вы будете использовать в поисковом запросе на  `folderid:<folderid>` шаге 2 для поиска в этой папке. Сценарий отображает не более 100 папок почтовых ящиков.

> [!IMPORTANT]
> Сценарий в этой статье содержит логику кодиации, которая преобразует 64-символьные значения кодов папок, которые возвращаются **Get-MailboxFolderStatistics,** в 48-символьный формат, индексируемый для поиска. Если вы только что запустите в PowerShell с помощью **get-MailboxFolderStatistics,** чтобы получить ИД папки (а не запускать сценарий в этой статье), поисковый запрос, использующий это значение, не будет работать. Чтобы получить правильно отформатированные ИД папок, которые можно использовать в поиске контента, необходимо запустить сценарий.
  
Вот пример выходных данных, возвращаемого сценарием для папок почтовых ящиков.
  
![Пример списка папок и папок почтовых ящиков, возвращаемого сценарием](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
В примере на шаге 2 показан запрос, используемый для поиска вложенной папки "Очистка" в папке пользователя "Элементы с возможностью восстановления".
  
### <a name="script-output-for-site-folders"></a>Выходные данные скрипта для папок сайта

Если вы получаете путь к свойству **documentlink** с сайтов SharePoint или OneDrive для бизнеса, сценарий подключается к PowerShell для обеспечения соответствия требованиям безопасности &, создает новый поиск контента, который выполняет поиск папок на сайте, а затем отображает список папок, расположенных на указанном сайте. Сценарий отображает имя каждой папки и добавляет префикс **documentlink** в URL-адрес папки. Так как **свойство documentlink** является свойством, которое можно найти, вы будете использовать пару property:value в поисковом запросе на шаге 2 для поиска `documentlink:<path>` в этой папке. Сценарий отображает не более 200 папок сайта. Если имеется более 200 папок сайта, отображаются самые новые папки.
  
Вот пример выходных данных, возвращаемого сценарием для папок сайта.
  
![Пример списка имен ссылок на документы для папок сайта, возвращаемого сценарием](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Шаг 2. Использование ИД папки или ссылки на документ для выполнения целевой коллекции

После выполнения сценария для сбора списка папок или ссылок на документы для определенного пользователя необходимо перейти в Центр соответствия требованиям Microsoft 365 и создать новый поиск контента для поиска в определенной папке. В поисковом запросе, настроенном в поле ключевых слов "Поиск контента" (или в качестве значения параметра  `folderid:<folderid>`  `documentlink:<path>`  *ContentMatchQuery,*  если используется cmdlet **New-ComplianceSearch),** используется пара "свойство-значение". Свойство или свойство можно  `folderid` объединить  `documentlink` с другими параметрами поиска или условиями поиска. Если в запрос включено только свойство или свойство, поиск возвращает все элементы, расположенные  `folderid`  `documentlink` в указанной папке.
  
1. Войдите в учетную запись и учетные данные, которые использовались для запуска сценария на [https://compliance.microsoft.com](https://compliance.microsoft.com) шаге 1.

2. В левой области Центра соответствия требованиям щелкните **"Показать все** поиск контента" и выберите  >   **"Новый поиск".**

3. В поле **"Ключевые** слова" в paste the `folderid:<folderid>` or value that was  `documentlink:<path>` returned by the script in Step 1.

    Например, запрос на следующем снимке экрана будет искать любой элемент во вложенной папке "Очистка" в папке "Элементы с восстановления" пользователя (значение свойства вложенной папки "Очистка" показано на снимке экрана на шаге `folderid` 1):

    ![Вложите папку или ссылку на документ в поле ключевого слова поискового запроса](../media/FolderIDSearchQuery.png)

4. В **области "Расположения"** выберите **"Определенные расположения"** и нажмите кнопку **"Изменить".**

5. В зависимости от того, где вы ищете папку почтового ящика или сайта, сделайте одно из следующих:

    - Рядом с **электронной почтой Exchange** щелкните "Выбрать пользователей, группы или команды", а затем добавьте тот же почтовый **ящик,** который вы указали при сценарии на шаге 1.

      или

    - Рядом с **сайтами SharePoint** щелкните "Выбрать сайты", а затем добавьте тот же URL-адрес сайта, который был указан при сценарии на шаге 1. 

6. После сохранения расположения контента для поиска нажмите кнопку "Сохранить & **выполнить",** введите имя для поиска контента, а затем нажмите кнопку "Сохранить", чтобы запустить поиск в целевой коллекции.  
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>Примеры поисковых запросов для целевых коллекций

Вот несколько примеров использования свойств и свойств в поисковом запросе  `folderid`  `documentlink` для выполнения целевой коллекции. Для и экономии места используются заметики. `folderid:<folderid>` `documentlink:<path>` 
  
- В этом примере выполняется поиск в трех различных папках почтовых ящиков. Для поиска скрытых папок в папке "Элементы с возможностью восстановления" пользователя можно использовать аналогичный синтаксис запроса.

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- В этом примере выполняется поиск элементов, содержащих точную фразу, в папке почтового ящика.

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- В этом примере выполняется поиск в папке сайта (и всех вложенных папок) документов, содержащих буквы "NDA" в заголовке.

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- В этом примере выполняется поиск документов, которые были изменены в пределах диапазона дат, в папке сайта (и в любой вложенной папке).

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>Дополнительные сведения

При использовании скрипта, написанного в этой статье, для выполнения целевых коллекций следует иметь в виду следующее.
  
- Сценарий не удаляет папки из результатов. Поэтому некоторые папки, перечисленные в результатах, могут быть недоступны для поиска (или возвращать элементы без возврата), так как они содержат контент, созданный системой, или содержат только вложенные папки, а не элементы почтового ящика.

- Этот сценарий возвращает только сведения о папке для основного почтового ящика пользователя. Он не возвращает сведения о папках в архивном почтовом ящике пользователя. Чтобы получить сведения о папках в архивном почтовом ящике пользователя, можно изменить сценарий. Для этого измените строку на строку, а затем сохраните и `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` запустите измененный сценарий. Это изменение возвратит ИД папок и вложенных папок в архивном почтовом ящике пользователя. Чтобы найти весь архивный почтовый ящик, можно подключить все пары "свойство-значение" и "свойство-значение" к оператору `OR` в поисковом запросе.

- При поиске в папках почтовых ящиков будет искаться только указанная папка (указанная по ее свойству), а вложенные папки не будут `folderid` искаться. Для поиска вложенных папок необходимо использовать ИД папки для вложенной папки, которую требуется найти.

- При поиске в папках сайта будет искаться папка (по ее свойству) и все `documentlink` вложенные папки. 

- При экспорте результатов поиска, в которых указано только свойство в поисковом запросе, можно выбрать первый вариант экспорта: "Все элементы, кроме элементов, которые имеют неизвестный формат, шифруются или не индексируются по другим `folderid` причинам". Все элементы в папке всегда будут экспортироваться независимо от их состояния индексации, так как ИД папки всегда индексируется.
