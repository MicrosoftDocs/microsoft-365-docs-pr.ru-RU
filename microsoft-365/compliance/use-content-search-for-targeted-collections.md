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
description: Используйте поиск контента в центре Microsoft 365 для выполнения целевых коллекций, которые гарантируют, что элементы находятся в определенном почтовом ящике или папке сайта.
ms.openlocfilehash: ea01386b7e52c05f8116caacddd6dec7baf12272
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994766"
---
# <a name="use-content-search-for-targeted-collections"></a>Использование поиска контента для целевых коллекций

Функция поиска контента в центре Microsoft 365 соответствия требованиям не обеспечивает прямой путь в пользовательском интерфейсе для поиска определенных папок в Exchange почтовых ящиках или SharePoint и OneDrive для бизнеса сайтах. Однако можно искать определенные папки (называемые целевой коллекцией), указав свойство ID папок для свойства электронной почты или пути (DocumentLink) для сайтов в синтаксис запроса поиска. Использование поиска контента для выполнения целевой коллекции полезно, если вы уверены, что элементы, реагирующие на конкретный случай или привилегированные элементы, находятся в определенном почтовом ящике или папке сайта. Сценарий в этой статье можно использовать для получения ID папок для папок почтовых ящиков или пути (DocumentLink) для папок на SharePoint и OneDrive для бизнеса сайте. Затем вы можете использовать папку ID или путь в запросе поиска для возврата элементов, расположенных в папке.

> [!NOTE]
> Чтобы вернуть содержимое, расположенное в папке на сайте SharePoint или OneDrive для бизнеса, сценарий в этом разделе использует управляемое свойство DocumentLink вместо свойства Path. Свойство DocumentLink является более надежным, чем свойство Path, так как возвращает все содержимое в папке, в то время как свойство Path не возвращает некоторые файлы мультимедиа.

## <a name="before-you-run-a-targeted-collection"></a>Перед запуском целевой коллекции

- Чтобы запустить сценарий в шаге 1, необходимо быть членом группы ролей диспетчера электронных данных в Центре & безопасности. Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).

    Кроме того, вам должна быть назначена роль получателей почты в Exchange Online организации. Это необходимо для запуска **комлета Get-MailboxFolderStatistics,** который входит в сценарий. По умолчанию роль получателей почты назначена группам ролей управления организацией и управления получателями в Exchange Online. Дополнительные сведения о назначении разрешений в Exchange Online см. в Exchange Online [Управление участниками группы ролей.](/exchange/manage-role-group-members-exchange-2013-help) Можно также создать настраиваемую группу ролей, назначить ему роль получателей почты, а затем добавить участников, которым необходимо выполнить сценарий в шаге 1. Дополнительные сведения см. в [см. в "Управление группами ролей".](/Exchange/permissions-exo/role-groups)

- Сценарий в этой статье поддерживает современную проверку подлинности. Сценарий можно использовать как есть, если вы Microsoft 365 или Microsoft 365 GCC организации. Если вы — Office 365, Microsoft 365 GCC или организация Microsoft 365 DoD, вам придется изменить сценарий, чтобы успешно запустить его. В частности, для подключения к Exchange Online PowerShell необходимо изменить строку и использовать параметр `Connect-ExchangeOnline` *ExchangeEnvironmentName* (и соответствующее значение для типа организации).  Кроме того, необходимо изменить строку и использовать параметры `Connect-IPPSSession` *ConnectionUri* и *AzureADAuthorizationEndpointUri* (и соответствующие значения для типа организации) для подключения к Центру & соответствия требованиям PowerShell. Дополнительные сведения см. в примерах Подключение в [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) и Подключение безопасности & [PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)центра соответствия требованиям.

- При каждом запуске сценария создается новая удаленная сессия PowerShell. Это означает, что вы можете использовать все доступные удаленные сеансы PowerShell. Чтобы этого не произошло, запустите следующую команду, чтобы отключить активные удаленные сеансы PowerShell.

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    Дополнительные сведения см. в статье [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Сценарий включает минимальную обработку ошибок. Основная цель сценария — быстрое отображение списка ID-адресов папок почтовых ящиков или путей сайта, которые можно использовать в синтаксисе поисковых запросов поиска контента для выполнения целевой коллекции.

- Пример сценария, представленного в этом разделе, не поддерживается ни в рамках стандартной программы поддержки Майкрософт, ни в службе. Пример сценария приводится в виде "как есть", без каких-либо гарантий. Кроме того, корпорация Microsoft отказывается от всех подразумеваемых гарантий, включая в том числе все подразумеваемые гарантии пригодности для продажи или определенной цели. Все риски, возникающие в результате использования примера сценария и документации, берет на себя пользователь. Корпорация Майкрософт, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценариев, ни при каких обстоятельствах не несут ответственность за какой-либо ущерб (в том числе, ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или неспособностью использовать примеры сценариев и документацию, даже если корпорации Майкрософт известно о возможности нанесения такого ущерба.

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>Шаг 1. Запустите скрипт, чтобы получить список папок для почтового ящика или сайта

Сценарий, который вы запустите на этом первом шаге, возвращает список папок почтовых ящиков или SharePoint и OneDrive для бизнеса, а также соответствующий ID или путь папки для каждой папки. При запуске этого скрипта вы сможете получить следующие сведения.

- **Адрес электронной** почты или URL-адрес сайта: введите адрес электронной почты хранителя, чтобы вернуть список Exchange почтовых ящиков и ИД папок. Или введите URL SharePoint или OneDrive для бизнеса, чтобы вернуть список путей для указанного сайта. Ниже приводятся примеры:

  - **Exchange**: stacig@contoso.onmicrosoft <spam> <spam> .com

  - **SharePoint**: https <span>://</span>contoso.sharepoint.com/sites/marketing

  - **OneDrive для бизнеса**: https <span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com

- **Учетные** данные пользователей. Скрипт будет использовать учетные данные для подключения к Exchange Online PowerShell или службе безопасности & PowerShell с помощью современной проверки подлинности. Как объяснялось ранее, для успешного запуска этого сценария необходимо получить соответствующие разрешения.

Отображение списка папок почтовых ящиков или имен ссылки на документы сайта (пути):

1. Сохраните следующий текст в Windows PowerShell скрипта с помощью суффикса .ps1; например, `GetFolderSearchParameters.ps1` .

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

4. Введите сведения, которые вам подсказывует скрипт.

    Скрипт отображает список папок почтовых ящиков или папок сайта для указанного пользователя. Оставьте это окно открытым, чтобы можно было скопировать ИД папки или имя documentlink и вставьте его в поисковый запрос в шаге 2.

    > [!TIP]
    > Вместо отображения списка папок на экране компьютера можно перенаправить выход скрипта в текстовый файл. Этот файл будет сохранен в папке, в которой находится сценарий. Например, чтобы перенаправить выход скрипта в текстовый файл, запустите следующую команду в шаге 3. Затем вы можете скопировать ИД папки или документообнаправление из файла для использования в поисковом  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` запросе.

### <a name="script-output-for-mailbox-folders"></a>Выход скрипта для папок почтовых ящиков

Если вы получаете ID-коды папок почтовых ящиков, сценарий подключается к Exchange Online PowerShell, запускает комлет **Get-MailboxFolderStatisics,** а затем отображает список папок из указанного почтового ящика. Для каждой папки в почтовом ящике скрипт отображает имя папки в столбце **FolderPath** и ИД папки в столбце **FolderQuery.** Кроме того, скрипт добавляет префикс **папкиId** (это имя свойства почтового ящика) в папку ID. Так как свойство **папки** является свойством, которое можно найти, вы будете использовать в запросе поиска в шаге 2 для поиска  `folderid:<folderid>` этой папки. Скрипт отображает не более 100 папок почтовых ящиков.

> [!IMPORTANT]
> Сценарий в этой статье включает логику кодиротворяния, которая преобразует значения Id папки с 64 символами, которые возвращаются **Get-MailboxFolderStatistics** в тот же формат с 48-символами, индексируемый для поиска. Если вы только что запустите комлет **Get-MailboxFolderStatistics** в PowerShell, чтобы получить код папки (вместо запуска скрипта в этой статье), поисковый запрос, использующий это значение папки, не удастся. Чтобы получить правильно отформатированные папки, которые можно использовать в поиске контента, необходимо запустить сценарий.

Вот пример вывода, возвращаемого скриптом для папок почтовых ящиков.

![Пример списка папок почтовых ящиков и ИД папок, возвращенных скриптом](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

В примере на шаге 2 показан запрос, используемый для поиска подмостков purges в папке "Извлекаемые элементы" пользователя.

### <a name="script-output-for-site-folders"></a>Выход скрипта для папок сайта

Если вы получаете путь свойства **documentlink** с сайтов SharePoint или OneDrive для бизнеса, скрипт подключается к PowerShell & безопасности, создает новый поиск контента, который ищет сайт для папок, а затем отображает список папок, расположенных на указанном сайте. Скрипт отображает имя каждой папки и добавляет префикс **ссылки** на документы в URL-адрес папки. Так как **свойство documentlink** — это свойство, которое можно найти, для поиска в этой папке используется пара свойства:значение в запросе поиска на `documentlink:<path>` шаге 2. Скрипт отображает не более 200 папок сайта. Если на сайте более 200 папок, отображаются самые новые.

Вот пример вывода, возвращаемого скриптом для папок сайта.

![Пример списка имен documentlink для папок сайтов, возвращенных скриптом](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>Шаг 2. Используйте ID папки или документополулка для выполнения целевой коллекции

После выполнения скрипта для сбора списка папок или ссылок на документы для определенного пользователя следующий шаг должен перейти в центр соответствия требованиям Microsoft 365 и создать новый поиск контента для поиска определенной папки. В поисковом запросе, настраиваемом в поле ключевого слова "Поиск контента" (или в качестве значения для параметра  `folderid:<folderid>`  `documentlink:<path>`  *ContentMatchQuery,*  если используется кодлет **New-ComplianceSearch,** используется пара свойств или значений). Вы можете объединить свойство  `folderid`  `documentlink` или свойство с другими параметрами поиска или условиями поиска. Если в запрос включено только свойство или свойство, поиск возвращает все элементы, расположенные  `folderid`  `documentlink` в указанной папке.

1. Перейдите к учетной записи и учетным данным, которые использовались для запуска сценария в <https://compliance.microsoft.com> шаге 1.

2. В левой области центра соответствия щелкните **Показать** весь поиск контента  >  и нажмите **кнопку Новый поиск.**

3. В поле **"Ключевые** слова" вклеить значение или значение, возвращенные сценарием `folderid:<folderid>` в  `documentlink:<path>` шаге 1.

    Например, запрос на следующем скриншоте будет искать любой элемент в подмастере Purges в папке "Извлекаемые элементы" пользователя (значение свойства подмостков Purges показано на скриншоте на `folderid` шаге 1):

    ![Вложите папку или ссылку на документ в поле ключевого слова запроса поиска](../media/FolderIDSearchQuery.png)

4. В **соответствии с положениями** выберите **конкретные расположения** и нажмите кнопку **Изменить**.

5. Сделайте одно из следующих сообщений, основываясь на том, ищете ли вы папку почтовых ящиков или папку сайта:

    - Рядом с **Exchange** нажмите кнопку **Выберите пользователей,** групп или групп, а затем добавьте тот же почтовый ящик, который был указан при 1-м этапе.

      Или

    - Рядом с **SharePoint сайтами** щелкните **Выберите** сайты и добавьте тот же URL-адрес сайта, который был указан при 1-м этапе.

6. После сохранения расположения контента для поиска нажмите кнопку Сохранить **&** запустить, введите имя для поиска контента, а затем нажмите сохранить, чтобы начать целевой поиск коллекции. 

### <a name="examples-of-search-queries-for-targeted-collections"></a>Примеры поисковых запросов для целевых коллекций

Вот несколько примеров использования свойств и свойств в запросе поиска для  `folderid`  `documentlink` выполнения целевой коллекции. Держатели используются для  `folderid:<folderid>` и  `documentlink:<path>` для сохранения пространства.

- В этом примере выполняется поиск трех разных папок почтовых ящиков. Аналогичный синтаксис запроса можно использовать для поиска скрытых папок в папке "Извлекаемые элементы" пользователя.

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- В этом примере выполняется поиск папки почтовых ящиков для элементов, содержащих точную фразу.

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- В этом примере выполняется поиск папки сайта (и любых подвещений) для документов, содержащих буквы "NDA" в заголовке.

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- В этом примере выполняется поиск папки сайта (и любых подвещений) для документов, которые были изменены в диапазоне дат.

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a>Дополнительные сведения

Следует помнить о следующих вещах при использовании сценария в этой статье для выполнения целевых коллекций.

- Скрипт не удаляет папки из результатов. Так что некоторые папки, перечисленные в результатах, могут быть неотвечены (или возвращают нулевые элементы), так как содержат контент, созданный системой, или потому, что они содержат только подмостки, а не элементы почтовых ящиков.

- Этот скрипт возвращает только данные папок для основного почтового ящика пользователя. Он не возвращает сведения о папках в архивном почтовом ящике пользователя. Чтобы вернуть сведения о папках в архивном почтовом ящике пользователя, можно изменить сценарий. Для этого измените строку, а затем сохраните и `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` запустите отредактированную скрипт. Это изменение возвращает папки для папок и подмостков в архивном почтовом ящике пользователя. Чтобы найти весь архивный почтовый ящик, можно подключить все свойство ID папки: пары значений с оператором `OR` в запросе поиска.

- При поиске папок почтовых ящиков будет искаться только указанная папка (определенная ее свойством), подмостки не будут `folderid` искаться. Чтобы найти подмостки, необходимо использовать папку ID для подмостка, которую необходимо искать.

- При поиске папок сайта будет искаться папка (определенная ее свойством) и все `documentlink` подмостки.

- При экспорте результатов поиска, в котором вы только указали свойство в запросе поиска, можно выбрать первый вариант экспорта: "Все элементы, за исключением элементов, не указанных в неузнаваемом формате, шифруются или не индексируются по другим `folderid` причинам". Все элементы в папке всегда будут экспортироваться независимо от состояния индексации, так как ID папки всегда индексируется.
