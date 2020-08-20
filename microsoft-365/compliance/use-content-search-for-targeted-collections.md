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
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="96ff1-103">Использование поиска контента для целевых коллекций</span><span class="sxs-lookup"><span data-stu-id="96ff1-103">Use Content Search for targeted collections</span></span>

<span data-ttu-id="96ff1-104">Функция поиска содержимого в Центре соответствия требованиям безопасности не позволяет искать в определенных папках на сайтах SharePoint или &amp; SharePoint и OneDrive для бизнеса на прямом режиме пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="96ff1-104">The Content Search feature in the Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="96ff1-105">Однако можно выполнять поиск в определенных папках (называемых *целевыми коллекциями),* указав свойство идентификатора папки для адреса электронной почты или пути (DocumentLink) для сайтов в синтаксисе запросов поиска.</span><span class="sxs-lookup"><span data-stu-id="96ff1-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="96ff1-106">Использование средства "Поиск контента" для выполнения целевой коллекции полезно, если вы уверены, что элементы, отвечающие обращению или привилегированным элементам, находятся в конкретном почтовом ящике или в папке сайта.</span><span class="sxs-lookup"><span data-stu-id="96ff1-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="96ff1-107">С помощью скрипта, представленного в этой статье, можно получить идентификатор папки для папок почтового ящика или путь (DocumentLink) для папок на сайте SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="96ff1-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="96ff1-108">После этого вы можете использовать идентификатор или путь в поисковом запросе для возврата элементов, найденных в папке.</span><span class="sxs-lookup"><span data-stu-id="96ff1-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="96ff1-109">Чтобы вернуть контент, расположенный в папке на сайте SharePoint или OneDrive для бизнеса, в скрипте из этой статьи используется управляемое свойство DocumentLink вместо свойства Path.</span><span class="sxs-lookup"><span data-stu-id="96ff1-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="96ff1-110">Свойство DocumentLink более надежно, чем свойство Path, поскольку оно возвращает все содержимое папки, в то время как свойство Path не возвращает некоторые файлы мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="96ff1-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-use-content-search"></a><span data-ttu-id="96ff1-111">Перед использованием средства "Поиск контента"</span><span class="sxs-lookup"><span data-stu-id="96ff1-111">Before you use Content Search</span></span>

- <span data-ttu-id="96ff1-112">Для выполнения сценария на шаге 1 вы должны быть членом группы ролей "Руководитель службы обнаружения электронных данных" &amp; в Центре соответствия требованиям безопасности.</span><span class="sxs-lookup"><span data-stu-id="96ff1-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="96ff1-113">Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="96ff1-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="96ff1-114">Кроме того, вам должна быть назначена роль получателей почты в организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="96ff1-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="96ff1-115">Это необходимо для выполнения командлета **Get-MailboxFolderStatistics,** входящего в состав сценария на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="96ff1-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1.</span></span> <span data-ttu-id="96ff1-116">Роль получателей почты по умолчанию назначается группам ролей "Управление организацией" и "Управление получателями" в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="96ff1-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="96ff1-117">Дополнительные сведения о назначении разрешений в Exchange Online см. в статье ["Управление участниками группы ролей".](https://go.microsoft.com/fwlink/p/?linkid=692102)</span><span class="sxs-lookup"><span data-stu-id="96ff1-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="96ff1-118">Также можно создать настраиваемую группу ролей, назначить ей роль получателей почты, а затем добавить членов, которым потребуется запускать сценарий на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="96ff1-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="96ff1-119">Дополнительные сведения см. в разделе ["Управление группами ролей".](https://go.microsoft.com/fwlink/p/?linkid=730688)</span><span class="sxs-lookup"><span data-stu-id="96ff1-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="96ff1-120">При каждом запуске сценария на шаге 1 создается новый сеанс удаленной оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96ff1-120">Each time you run the script in Step 1, a new remote PowerShell session is created.</span></span> <span data-ttu-id="96ff1-121">Поэтому вы могли использовать все доступные удаленные сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96ff1-121">So you could use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="96ff1-122">Чтобы предотвратить это, можно выполнить следующую команду для отключения активных сеансов PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96ff1-122">To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="96ff1-123">Дополнительные сведения см. в статье [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="96ff1-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="96ff1-124">Этот скрипт включает минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="96ff1-124">The script includes minimal error handling.</span></span> <span data-ttu-id="96ff1-125">Основная задача сценария — быстро показать идентификаторы папок почтового ящика или пути на сайте, которые можно использовать в синтаксисе запросов поиска контента для выполнения целевой коллекции.</span><span class="sxs-lookup"><span data-stu-id="96ff1-125">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="96ff1-126">Пример скрипта, представленный в этой статье, не поддерживается ни одной из стандартных программ поддержки или служб Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="96ff1-126">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="96ff1-127">Образец сценария предоставляется "как есть", без каких-либо гарантий.</span><span class="sxs-lookup"><span data-stu-id="96ff1-127">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="96ff1-128">Кроме того, корпорация Майкрософт отказывается от всех подразумеваемых гарантий, включая, но не ограничиваясь указанным, все подразумеваемые гарантии пригодности для продажи или определенной цели.</span><span class="sxs-lookup"><span data-stu-id="96ff1-128">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="96ff1-129">Весь риск, испытывающих использование или производительность примера сценария и документации, возможно, вам также касается.</span><span class="sxs-lookup"><span data-stu-id="96ff1-129">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="96ff1-130">Корпорация Майкрософт, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценариев, ни при каких обстоятельствах не несут ответственность за какой-либо ущерб (в том числе, ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или неспособностью использовать примеры сценариев и документацию, даже если корпорации Майкрософт известно о возможности нанесения такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="96ff1-130">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="96ff1-131">Шаг 1. Запуск сценария, чтобы получить список папок для почтового ящика или сайта</span><span class="sxs-lookup"><span data-stu-id="96ff1-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="96ff1-132">Сценарий, запускаемый на этом первом шаге, возвратит список папок почтового ящика либо папок SharePoint и OneDrive для бизнеса, а также идентификатор соответствующей папки с идентификатором или путем для каждой папки.</span><span class="sxs-lookup"><span data-stu-id="96ff1-132">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="96ff1-133">При выполнении этого сценария появится следующая информация.</span><span class="sxs-lookup"><span data-stu-id="96ff1-133">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="96ff1-134">**Адрес электронной почты или URL-адрес сайта** Введите адрес электронной почты для копии, который возвращает список папок и идентификаторов папок почтового ящика Exchange.</span><span class="sxs-lookup"><span data-stu-id="96ff1-134">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="96ff1-135">Если также можно указать URL-адрес сайта SharePoint или сайта OneDrive для бизнеса, чтобы возвращался список путей к указанному сайту.</span><span class="sxs-lookup"><span data-stu-id="96ff1-135">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="96ff1-136">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="96ff1-136">Here are some examples:</span></span> 
    
  - <span data-ttu-id="96ff1-137">**Exchange** stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="96ff1-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="96ff1-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="96ff1-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="96ff1-139">**OneDrive для бизнеса** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="96ff1-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="96ff1-140">**Учетные данные пользователя.** Сценарий будет использовать учетные данные для подключения к Exchange Online и Центра безопасности & соответствия требованиям с помощью удаленной оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="96ff1-140">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="96ff1-141">Как было сказано выше, вам необходимо назначить соответствующие разрешения для успешного выполнения этого сценария.</span><span class="sxs-lookup"><span data-stu-id="96ff1-141">As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="96ff1-142">Чтобы отобразить список папок почтового ящика или ссылок документа сайта, необходимо:</span><span class="sxs-lookup"><span data-stu-id="96ff1-142">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="96ff1-143">Сохраните приведенный ниже текст в файле сценария Windows PowerShell, используя суффикс .ps1 в имени файла. Например, `GetFolderSearchParameters.ps1` .</span><span class="sxs-lookup"><span data-stu-id="96ff1-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
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

2. <span data-ttu-id="96ff1-144">На локальном компьютере откройте Windows PowerShell и перейдите к папке, где сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="96ff1-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="96ff1-145">Запустите сценарий. Например:</span><span class="sxs-lookup"><span data-stu-id="96ff1-145">Run the script; for example:</span></span>
    
   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="96ff1-146">Введите информацию, в которой сценарий предлагает ее.</span><span class="sxs-lookup"><span data-stu-id="96ff1-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="96ff1-147">Скрипт отобразит список папок почтового ящика или папок сайта для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="96ff1-147">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="96ff1-148">Оставьте это окно открытым, чтобы можно было скопировать имя папки с идентификатором или документом, и вставьте его в поисковый запрос на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="96ff1-148">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="96ff1-149">Вместо отображения списка папок на экране компьютера можно перенаправить выходные данные сценария в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="96ff1-149">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="96ff1-150">Этот файл будет сохранен в папке, где расположен сценарий.</span><span class="sxs-lookup"><span data-stu-id="96ff1-150">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="96ff1-151">Например, чтобы перенаправить выходные данные сценария в текстовый файл, выполните следующую команду в действии 3: Затем вы можете скопировать идентификатор папки или ссылку на документы из файла  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` для использования в поисковом запросе.</span><span class="sxs-lookup"><span data-stu-id="96ff1-151">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="96ff1-152">Вывод сценариев для папок почтового ящика</span><span class="sxs-lookup"><span data-stu-id="96ff1-152">Script output for mailbox folders</span></span>

<span data-ttu-id="96ff1-153">При получении идентификаторов папок почтового ящика сценарий подключается к Exchange Online с помощью удаленной оболочки PowerShell, запускает **командлет Get-MailboxFolderStatisics** и выводит список папок из указанного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="96ff1-153">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="96ff1-154">Для каждой папки в почтовом ящике в сценарии отображается имя папки в **столбце FolderPath** и идентификатор папки в **столбце FolderQuery.**</span><span class="sxs-lookup"><span data-stu-id="96ff1-154">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="96ff1-155">Кроме того, сценарий добавляет префикс **folderId** (который представляет собой имя свойства почтового ящика) в идентификатор папки.</span><span class="sxs-lookup"><span data-stu-id="96ff1-155">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="96ff1-156">Так как **свойство folderid является** свойством searchable, для поиска в этой папке будет использоваться  `folderid:<folderid>` поисковый запрос на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="96ff1-156">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="96ff1-157">Скрипт отображает не более 100 папок почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="96ff1-157">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96ff1-158">Сценарий в этой статье содержит логику кодирования, которая преобразует значения идентификаторов 64-мепапок, возвращаемые **Get-MailboxFolderStatistics,** в 48-символьный формат, индексируемый для поиска.</span><span class="sxs-lookup"><span data-stu-id="96ff1-158">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="96ff1-159">Если вы только что запустили **командлет Get-MailboxFolderStatistics** в PowerShell, чтобы получить идентификатор папки (вместо выполнения скрипта, представленного в этой статье), поисковый запрос с этим идентификатором будет выполняться ошибкой.</span><span class="sxs-lookup"><span data-stu-id="96ff1-159">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="96ff1-160">Необходимо выполнить сценарий, чтобы получить правильно отформатированные идентификаторы папок, которые можно использовать при поиске контента.</span><span class="sxs-lookup"><span data-stu-id="96ff1-160">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="96ff1-161">Ниже приведен пример выходных данных, возвращаемых сценарием для папок почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="96ff1-161">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![Пример списка папок почтового ящика и их идентификаторов, возвращаемых сценарием](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="96ff1-163">В примере шага 2 показан запрос, используемый для поиска во вложенной папке "Очистка" в папке пользователя "Элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="96ff1-163">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="96ff1-164">Вывод скриптов для папок сайта</span><span class="sxs-lookup"><span data-stu-id="96ff1-164">Script output for site folders</span></span>

<span data-ttu-id="96ff1-165">При получении пути к свойству **documentlink** с сайтов SharePoint или OneDrive для бизнеса сценарий подключается к Центру безопасности соответствия требованиям & с помощью удаленного сеанса PowerShell, создает новый поиск контента на сайте, чтобы найти папки на нем, а затем выводит список папок, расположенных на указанном сайте.</span><span class="sxs-lookup"><span data-stu-id="96ff1-165">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to the Security & Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="96ff1-166">Скрипт отображает имя каждой папки и добавляет префикс **documentlink** в URL-адрес папки.</span><span class="sxs-lookup"><span data-stu-id="96ff1-166">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="96ff1-167">Так как **свойство documentlink** является свойством, поддерживающим поиск, в поисковом запросе в действии 2 выполняется поиск в `documentlink:<path>` этой папке.</span><span class="sxs-lookup"><span data-stu-id="96ff1-167">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="96ff1-168">Скрипт отображает не более 200 папок сайта.</span><span class="sxs-lookup"><span data-stu-id="96ff1-168">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="96ff1-169">Если папок сайта больше 200, отображаются новейшая из них.</span><span class="sxs-lookup"><span data-stu-id="96ff1-169">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="96ff1-170">Ниже приведен пример выходных данных, возвращаемых скриптом для папок сайта.</span><span class="sxs-lookup"><span data-stu-id="96ff1-170">Here's an example of the output returned by the script for site folders.</span></span>
  
![Пример списка имен documentlink для папок сайта, возвращаемых скриптом](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="96ff1-172">Шаг 2. Использование идентификатора папки или ссылки на документы для выполнения целевой коллекции</span><span class="sxs-lookup"><span data-stu-id="96ff1-172">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="96ff1-173">После выполнения сценария для сбора списка идентификаторов папок или ссылок на документы для определенного пользователя следующее действие переходит в Центр безопасности & соответствия требованиям и создание нового запроса на поиск контента для поиска в определенной папке.</span><span class="sxs-lookup"><span data-stu-id="96ff1-173">After you've run the script to collect a list of folder IDs or documentlinks for a specific user, the next step to go to the Security & Compliance Center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="96ff1-174">Необходимо использовать пару `folderid:<folderid>` "or `documentlink:<path>` property:value" в поисковом запросе, которую вы настроите в поле ключевых слов поиска контента (или как значение *параметра ContentMatchQuery,* **если используется командлет New-ComplianceSearch).**</span><span class="sxs-lookup"><span data-stu-id="96ff1-174">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="96ff1-175">Вы можете объединить  `folderid` или добавить свойство с  `documentlink` другими параметрами поиска или условиями поиска.</span><span class="sxs-lookup"><span data-stu-id="96ff1-175">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="96ff1-176">Если включить в запрос  `folderid` только  `documentlink` свойство или свойство, то поиск возвращает все элементы, найденные в указанной папке.</span><span class="sxs-lookup"><span data-stu-id="96ff1-176">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span> 
  
1. <span data-ttu-id="96ff1-177">Перейдите по ссылке [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="96ff1-177">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="96ff1-178">Войдите с использованием учетной записи и учетных данных, которые использовались для запуска сценария на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="96ff1-178">Sign in using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="96ff1-179">В левой области Центра безопасности & соответствия требованиям щелкните **"Поиск** \> **контента"** и нажмите значок **New** ![ "Добавить". ](../media/O365-MDM-CreatePolicy-AddIcon.gif)</span><span class="sxs-lookup"><span data-stu-id="96ff1-179">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**, and then click **New** ![Add icon](../media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="96ff1-180">На странице **Новый поиск** введите имя поиска контента.</span><span class="sxs-lookup"><span data-stu-id="96ff1-180">On the **New search** page, type a name for the Content Search.</span></span> <span data-ttu-id="96ff1-181">Это имя должно быть уникальным в пределах организации.</span><span class="sxs-lookup"><span data-stu-id="96ff1-181">This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="96ff1-182">В **разделе "Место поиска" выполните**одно из следующих действий в зависимости от того, выполняете ли вы поиск в папке почтового ящика или папке сайта:</span><span class="sxs-lookup"><span data-stu-id="96ff1-182">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="96ff1-183">Щелкните **"Выбрать определенные почтовые ящики** для поиска" и добавьте тот же почтовый ящик, который был указан при выполнении сценария на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="96ff1-183">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="96ff1-184">ИЛИ</span><span class="sxs-lookup"><span data-stu-id="96ff1-184">Or</span></span>
    
    - <span data-ttu-id="96ff1-185">Щелкните **"Выбор определенных сайтов для поиска"** и добавьте URL-адрес, указанный при выполнении скрипта на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="96ff1-185">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="96ff1-186">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="96ff1-186">Click **Next**.</span></span>
    
7. <span data-ttu-id="96ff1-187">В поле ключевых слов на **странице "Что вы хотите** искать" вставьте или  `folderid:<folderid>`  `documentlink:<path>` значение, возвращенное сценарием на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="96ff1-187">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="96ff1-188">Например, запрос на следующем снимке экрана выполняет поиск любого элемента в подпапке "Очистка" в папке пользователя "Элементы с возможностью восстановления" (значение свойства для вложенной папки "Очистка" отображается на снимке экрана `folderid` на этапе 1) и:.</span><span class="sxs-lookup"><span data-stu-id="96ff1-188">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![Вставка значения folderid или documentlink в поле ключевого слова поискового запроса](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="96ff1-190">Нажмите **кнопку** "Поиск", чтобы запустить целевой поиск в коллекции.</span><span class="sxs-lookup"><span data-stu-id="96ff1-190">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="96ff1-191">Примеры поисковых запросов для целевых коллекций</span><span class="sxs-lookup"><span data-stu-id="96ff1-191">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="96ff1-192">Ниже приведены некоторые примеры использования  `folderid` и  `documentlink` свойств в поисковом запросе для выполнения целевой коллекции.</span><span class="sxs-lookup"><span data-stu-id="96ff1-192">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="96ff1-193">Обратите внимание, что для экономии места  `folderid:<folderid>` используются  `documentlink:<path>` заполнители.</span><span class="sxs-lookup"><span data-stu-id="96ff1-193">Note that placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="96ff1-194">В этом примере выполняется поиск в трех разных папках почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="96ff1-194">This example searches three different mailbox folders.</span></span> <span data-ttu-id="96ff1-195">Для поиска в скрытых папках, подключаемых пользователя, можно использовать сходный синтаксис запросов.</span><span class="sxs-lookup"><span data-stu-id="96ff1-195">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="96ff1-196">В этом примере в папке почтового ящика выполняется поиск элементов, содержащих точную фразу.</span><span class="sxs-lookup"><span data-stu-id="96ff1-196">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="96ff1-197">В этом примере в заголовке выполняется поиск документов, содержащих буквы NDA в заголовке, в папке сайта (и во всех вложенных папках).</span><span class="sxs-lookup"><span data-stu-id="96ff1-197">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="96ff1-198">В этом примере выполняется поиск документов, измененных в пределах диапазона дат, в папке сайта (и во всех вложенных папках).</span><span class="sxs-lookup"><span data-stu-id="96ff1-198">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="96ff1-199">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="96ff1-199">More information</span></span>

<span data-ttu-id="96ff1-200">При использовании скрипта, описанного в этой статье, следует учитывать следующие моменты.</span><span class="sxs-lookup"><span data-stu-id="96ff1-200">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="96ff1-201">Сценарий не удаляет из результатов папки.</span><span class="sxs-lookup"><span data-stu-id="96ff1-201">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="96ff1-202">Поэтому некоторые папки, перечисленные в результатах, могут быть невисимы (или возвращать нулевые элементы), так как они содержат созданный системой контент.</span><span class="sxs-lookup"><span data-stu-id="96ff1-202">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="96ff1-203">Этот сценарий возвращает сведения о папке только для основного почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="96ff1-203">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="96ff1-204">Она не возвращает сведения о папках в архивном почтовом ящике пользователя.</span><span class="sxs-lookup"><span data-stu-id="96ff1-204">It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="96ff1-205">При поиске в папках почтового ящика поиск будет выполняться только в указанных папках (определяемой его  `folderid` свойством) и поиск по вложенным папкам.</span><span class="sxs-lookup"><span data-stu-id="96ff1-205">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="96ff1-206">Для поиска вложенных папок необходимо использовать идентификатор вложенной папки, в которой нужно найти в ней идентификатор вложенной папки.</span><span class="sxs-lookup"><span data-stu-id="96ff1-206">To search sub-folders, you need to use the  folder ID for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="96ff1-207">Поиск в папках сайта выполняется во всех папках (определяемых свойством) и  `documentlink` всеми вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="96ff1-207">When searching site folders, the folder (identified by its  `documentlink` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="96ff1-208">При экспорте результатов поиска, в которых было указано только свойство в поисковом запросе, вы можете выбрать первый вариант экспорта "Все элементы, кроме неизвестных формата, зашифрованных или не индексированных по `folderid` другой причине".</span><span class="sxs-lookup"><span data-stu-id="96ff1-208">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="96ff1-209">Все элементы в папке будут экспортироваться всегда независимо от их состояния индексирования, так как идентификатор папки всегда индексируется.</span><span class="sxs-lookup"><span data-stu-id="96ff1-209">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
