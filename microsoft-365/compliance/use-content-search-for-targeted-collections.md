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
description: Используйте поиск контента в центре безопасности & соответствия требованиям, чтобы выполнять целевые коллекции, которые обеспечивают расположение элементов в определенном почтовом ящике или папке сайта.
ms.openlocfilehash: fb7f900e8deaef6946d1ed8ea109d42207a882b3
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819109"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="e77c4-103">Использование поиска контента для целевых коллекций</span><span class="sxs-lookup"><span data-stu-id="e77c4-103">Use Content Search for targeted collections</span></span>

<span data-ttu-id="e77c4-104">Функция поиска контента в &amp; центре соответствия требованиям безопасности не предоставляет прямой способ для поиска определенных папок в почтовых ящиках Exchange, а также на сайтах SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e77c4-104">The Content Search feature in the Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="e77c4-105">Тем не менее, можно выполнять поиск по определенным папкам (называемым *целевой коллекцией*), УКАЗАВ свойство ID папки для свойства email или Path (документлинк) для сайтов в фактическом синтаксисе поискового запроса.</span><span class="sxs-lookup"><span data-stu-id="e77c4-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="e77c4-106">Использование функции поиска контента для выполнения целевой коллекции полезно, если вы уверены, что элементы, реагирующие на обращение или привилегированные элементы, расположены в определенном почтовом ящике или папке сайта.</span><span class="sxs-lookup"><span data-stu-id="e77c4-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="e77c4-107">С помощью сценария, описанного в этой статье, можно получить идентификатор папки для папок почтовых ящиков или путь (Документлинк) для папок на сайте SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e77c4-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="e77c4-108">Затем вы можете использовать идентификатор или путь к папке в запросе поиска, чтобы вернуть элементы, расположенные в папке.</span><span class="sxs-lookup"><span data-stu-id="e77c4-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="e77c4-109">Чтобы получить контент, расположенный в папке на сайте SharePoint или OneDrive для бизнеса, сценарий в этом разделе использует управляемое свойство Документлинк вместо свойства Path.</span><span class="sxs-lookup"><span data-stu-id="e77c4-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="e77c4-110">Свойство Документлинк является более надежным, чем свойство Path, так как оно возвращает весь контент в папке, а свойство Path не возвращает некоторые файлы мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="e77c4-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-use-content-search"></a><span data-ttu-id="e77c4-111">Перед использованием поиска контента</span><span class="sxs-lookup"><span data-stu-id="e77c4-111">Before you use Content Search</span></span>

- <span data-ttu-id="e77c4-112">Вы должны быть участником группы ролей "Диспетчер обнаружения электронных данных" в &amp; центре соответствия требованиям безопасности, чтобы запустить сценарий на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="e77c4-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="e77c4-113">Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e77c4-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="e77c4-114">Кроме того, необходимо назначить роль получателей почты в организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e77c4-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="e77c4-115">Это необходимо для запуска командлета **Get-MailboxFolderStatistics** , который включен в сценарий, описанный в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="e77c4-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1.</span></span> <span data-ttu-id="e77c4-116">По умолчанию роль получателей почты назначается группам ролей "Управление организацией" и "Управление получателями" в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e77c4-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="e77c4-117">Дополнительные сведения о назначении разрешений в Exchange Online содержатся в разделе [Управление участниками группы ролей](https://go.microsoft.com/fwlink/p/?linkid=692102).</span><span class="sxs-lookup"><span data-stu-id="e77c4-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="e77c4-118">Вы также можете создать настраиваемую группу ролей, назначить ей роль получателей почты, а затем добавить участников, которым требуется запустить сценарий, на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="e77c4-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="e77c4-119">Дополнительные сведения можно найти в разделе [Manage Role Groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span><span class="sxs-lookup"><span data-stu-id="e77c4-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="e77c4-120">Каждый раз при запуске скрипта на этапе 1 создается новый удаленный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e77c4-120">Each time you run the script in Step 1, a new remote PowerShell session is created.</span></span> <span data-ttu-id="e77c4-121">Поэтому можно использовать все удаленные сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e77c4-121">So you could use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="e77c4-122">Чтобы избежать этого, можно выполнить следующую команду, чтобы отключить активные сеансы удаленной оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e77c4-122">To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="e77c4-123">Дополнительные сведения см. в статье [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="e77c4-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="e77c4-124">Сценарий включает в себя минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="e77c4-124">The script includes minimal error handling.</span></span> <span data-ttu-id="e77c4-125">Основной целью сценария является быстрое отображение списка идентификаторов папок почтовых ящиков или путей сайтов, которые можно использовать в синтаксисе запроса поиска контента для выполнения целевой коллекции.</span><span class="sxs-lookup"><span data-stu-id="e77c4-125">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="e77c4-126">Пример сценария, представленный в этом разделе, не поддерживается ни в одной из стандартных программ или услуг поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="e77c4-126">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="e77c4-127">Пример сценария предоставляется без каких-либо гарантий.</span><span class="sxs-lookup"><span data-stu-id="e77c4-127">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="e77c4-128">Кроме того, корпорация Майкрософт отказывается от всех косвенных гарантий товарного качества.</span><span class="sxs-lookup"><span data-stu-id="e77c4-128">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="e77c4-129">Весь риск, возникающий из примера использования или производительности примера сценария и документации, остается без вас.</span><span class="sxs-lookup"><span data-stu-id="e77c4-129">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="e77c4-130">Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации сценариев, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров сценариев или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="e77c4-130">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="e77c4-131">Шаг 1: запуск скрипта для получения списка папок для почтового ящика или сайта</span><span class="sxs-lookup"><span data-stu-id="e77c4-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="e77c4-132">Скрипт, выполняемый на первом шаге, вернет список папок почтовых ящиков или папок SharePoint и OneDrive для бизнеса, а также соответствующий идентификатор или путь к папке.</span><span class="sxs-lookup"><span data-stu-id="e77c4-132">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="e77c4-133">При выполнении этого сценария будет предложено ввести следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="e77c4-133">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="e77c4-134">**Адрес электронной почты или URL-адрес сайта** Введите адрес электронной почты хранитель, чтобы получить список папок почтовых ящиков Exchange и идентификаторов папок.</span><span class="sxs-lookup"><span data-stu-id="e77c4-134">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="e77c4-135">Или введите URL-адрес сайта SharePoint или сайта OneDrive для бизнеса, чтобы получить список путей для указанного сайта.</span><span class="sxs-lookup"><span data-stu-id="e77c4-135">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="e77c4-136">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="e77c4-136">Here are some examples:</span></span> 
    
  - <span data-ttu-id="e77c4-137">**Exchange** — stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e77c4-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="e77c4-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="e77c4-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="e77c4-139">**OneDrive для бизнеса** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="e77c4-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="e77c4-140">**Ваши учетные данные пользователя** : сценарий будет использовать ваши учетные данные для подключения к Exchange Online и центра безопасности & соответствия требованиям с помощью удаленной оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e77c4-140">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="e77c4-141">Как было сказано выше, для успешного выполнения этого сценария необходимо назначить соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="e77c4-141">As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="e77c4-142">Чтобы отобразить список папок почтовых ящиков или документлинк (путей) сайта, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="e77c4-142">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="e77c4-143">Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `GetFolderSearchParameters.ps1` .</span><span class="sxs-lookup"><span data-stu-id="e77c4-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
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

2. <span data-ttu-id="e77c4-144">На локальном компьютере откройте Windows PowerShell и перейдите к папке, в которой был сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="e77c4-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="e77c4-145">Запуск скрипта; Например:</span><span class="sxs-lookup"><span data-stu-id="e77c4-145">Run the script; for example:</span></span>
    
      ```powershell
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="e77c4-146">Введите сведения, которые будут запрашиваться сценарием.</span><span class="sxs-lookup"><span data-stu-id="e77c4-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="e77c4-147">В этом сценарии отображается список папок или папок почтового ящика для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="e77c4-147">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="e77c4-148">Разрешите это окно, чтобы можно было скопировать идентификатор папки или имя документлинк и вставить его в поисковый запрос на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="e77c4-148">Let this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e77c4-149">Вместо того чтобы отображать список папок на экране компьютера, можно повторно перенаправить выходные данные сценария в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="e77c4-149">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="e77c4-150">Этот файл будет сохранен в папке, в которой расположен сценарий.</span><span class="sxs-lookup"><span data-stu-id="e77c4-150">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="e77c4-151">Например, чтобы перенаправить выходные данные сценария в текстовый файл, выполните следующую команду на шаге 3: `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` затем вы можете скопировать идентификатор папки или документлинк из файла для использования в поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="e77c4-151">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="e77c4-152">Вывод сценариев для папок почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="e77c4-152">Script output for mailbox folders</span></span>

<span data-ttu-id="e77c4-153">Если вы получаете идентификаторы папок почтовых ящиков, сценарий подключается к Exchange Online с помощью удаленной оболочки PowerShell, запускает командлет **Get-маилбоксфолдерстатисикс** , а затем отображает список папок из указанного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="e77c4-153">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="e77c4-154">Для каждой папки в почтовом ящике сценарий отображает имя папки в столбце **FolderPath** и идентификатор папки в столбце **фолдеркуери** .</span><span class="sxs-lookup"><span data-stu-id="e77c4-154">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="e77c4-155">Кроме того, скрипт добавляет префикс **FolderId** (имя свойства почтового ящика) к идентификатору папки.</span><span class="sxs-lookup"><span data-stu-id="e77c4-155">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="e77c4-156">Так как свойство **FolderId** является свойством для поиска, вы будете использовать поисковую `folderid:<folderid>` папку в запросе поиска на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="e77c4-156">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="e77c4-157">В этом сценарии отображается не более 100 папок почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="e77c4-157">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e77c4-158">Сценарий, описанный в этой статье, включает логику кодирования, преобразующую значения идентификаторов папок 64-character, которые возвращаются командой **Get-MailboxFolderStatistics** , в тот же формат 48 символов, который индексируется для поиска.</span><span class="sxs-lookup"><span data-stu-id="e77c4-158">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="e77c4-159">Если вы просто выполняете командлет **Get-MailboxFolderStatistics** в PowerShell, чтобы получить идентификатор папки (вместо того, чтобы выполнять сценарий в этой статье), поисковый запрос, в котором используется значение идентификатора этой папки, завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="e77c4-159">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="e77c4-160">Для получения правильно отформатированных идентификаторов папок, которые можно использовать при поиске контента, необходимо выполнить сценарий.</span><span class="sxs-lookup"><span data-stu-id="e77c4-160">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="e77c4-161">Ниже приведен пример выходных данных, возвращаемых сценарием для папок почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="e77c4-161">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![Пример списка папок и идентификаторов папок почтовых ящиков, возвращенных сценарием](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="e77c4-163">В примере на шаге 2 показан запрос, используемый для поиска вложенной папки "очистки" в папке "элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="e77c4-163">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="e77c4-164">Выходные данные сценариев для папок сайта</span><span class="sxs-lookup"><span data-stu-id="e77c4-164">Script output for site folders</span></span>

<span data-ttu-id="e77c4-165">Если вы получаете путь к свойству **документлинк** из сайтов SharePoint или OneDrive для бизнеса, сценарий подключается к центру безопасности & соответствия требованиям с помощью удаленной оболочки PowerShell, создает новый поиск контента, который выполняет поиск в сайтах для папок, а затем отображает список папок, расположенных на указанном сайте.</span><span class="sxs-lookup"><span data-stu-id="e77c4-165">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to the Security & Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="e77c4-166">В этом сценарии отображается имя каждой папки и добавляется префикс **документлинк** к URL-адресу папки.</span><span class="sxs-lookup"><span data-stu-id="e77c4-166">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="e77c4-167">Так как свойство **документлинк** является свойством, `documentlink:<path>` поддерживающим Поиск, для поиска в этой папке используется значение "свойство: значение" в поисковом запросе на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="e77c4-167">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="e77c4-168">В этом сценарии отображается не более 200 папок сайта.</span><span class="sxs-lookup"><span data-stu-id="e77c4-168">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="e77c4-169">Если количество папок сайта превышает 200, отображаются последние из них.</span><span class="sxs-lookup"><span data-stu-id="e77c4-169">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="e77c4-170">Ниже приведен пример выходных данных, возвращаемых сценарием для папок сайта.</span><span class="sxs-lookup"><span data-stu-id="e77c4-170">Here's an example of the output returned by the script for site folders.</span></span>
  
![Пример списка имен документлинк для папок сайта, возвращаемых сценарием](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="e77c4-172">Шаг 2: использование идентификатора папки или документлинк для выполнения целевой коллекции</span><span class="sxs-lookup"><span data-stu-id="e77c4-172">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="e77c4-173">После выполнения сценария для сбора списка идентификаторов папок или документлинкс для определенного пользователя необходимо перейти в центр безопасности & соответствия требованиям и создать новый поиск контента для поиска в определенной папке.</span><span class="sxs-lookup"><span data-stu-id="e77c4-173">After you've run the script to collect a list of folder IDs or documentlinks for a specific user, the next step to go to the Security & Compliance Center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="e77c4-174">В `folderid:<folderid>` `documentlink:<path>` поле ключевое слово поиска контента (или в качестве значения параметра *контентматчкуери* при использовании командлета **New-ComplianceSearch** ) будет использоваться значение "свойство: значение" в запросе поиска, которое вы настроили.</span><span class="sxs-lookup"><span data-stu-id="e77c4-174">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="e77c4-175">Можно сочетать `folderid` `documentlink` свойство или с другими параметрами поиска или условиями поиска.</span><span class="sxs-lookup"><span data-stu-id="e77c4-175">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="e77c4-176">Если вы включаете `folderid` `documentlink` в запрос только свойство или, то поиск вернет все элементы, расположенные в указанной папке.</span><span class="sxs-lookup"><span data-stu-id="e77c4-176">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span> 
  
1. <span data-ttu-id="e77c4-177">Перейдите по адресу [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="e77c4-177">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="e77c4-178">Войдите в систему, используя учетную запись и учетные данные, которые использовались для запуска скрипта на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="e77c4-178">Sign in using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="e77c4-179">В левой области центра безопасности & соответствия **требованиям выберите Поиск** \> **контента**поиска и нажмите **создать** ![ значок добавления ](../media/O365-MDM-CreatePolicy-AddIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="e77c4-179">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**, and then click **New** ![Add icon](../media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="e77c4-180">На странице **Новый поиск** введите имя поиска контента.</span><span class="sxs-lookup"><span data-stu-id="e77c4-180">On the **New search** page, type a name for the Content Search.</span></span> <span data-ttu-id="e77c4-181">Это имя должно быть уникальным в пределах организации.</span><span class="sxs-lookup"><span data-stu-id="e77c4-181">This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="e77c4-182">В разделе **где вы хотите посмотреть**, выполните одно из следующих действий в зависимости от того, выполняется ли поиск в папке почтовых ящиков или в папке сайта:</span><span class="sxs-lookup"><span data-stu-id="e77c4-182">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="e77c4-183">Щелкните **выбрать конкретные почтовые ящики для поиска** , а затем добавьте тот же почтовый ящик, который вы указали при выполнении сценария, описанного в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="e77c4-183">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="e77c4-184">или</span><span class="sxs-lookup"><span data-stu-id="e77c4-184">Or</span></span>
    
    - <span data-ttu-id="e77c4-185">Щелкните **выбрать конкретные сайты для поиска** , а затем добавьте тот же URL-адрес сайта, который вы указали при выполнении сценария, описанного в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="e77c4-185">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="e77c4-186">Нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="e77c4-186">Click **Next**.</span></span>
    
7. <span data-ttu-id="e77c4-187">В поле ключевое слово на странице **что вы хотите искать** на странице, вставьте `folderid:<folderid>` `documentlink:<path>` значение или значение, возвращенное сценарием на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="e77c4-187">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="e77c4-188">Например, запрос на следующем снимке экрана будет искать любой элемент в подпапке "очистки" в папке "элементы с возможностью восстановления" (значение `folderid` свойства для вложенной папки "очистки" отображается на снимке экрана на шаге 1):</span><span class="sxs-lookup"><span data-stu-id="e77c4-188">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![Вставьте FolderId или документлинк в поле ключевое слово поискового запроса.](../media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="e77c4-190">Нажмите кнопку **Поиск** , чтобы начать поиск целевой коллекции.</span><span class="sxs-lookup"><span data-stu-id="e77c4-190">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="e77c4-191">Примеры запросов поиска для целевых коллекций</span><span class="sxs-lookup"><span data-stu-id="e77c4-191">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="e77c4-192">Ниже приведено несколько примеров использования `folderid` свойств и `documentlink` в запросе поиска для выполнения целевой коллекции.</span><span class="sxs-lookup"><span data-stu-id="e77c4-192">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="e77c4-193">Обратите внимание, что заполнители используются для `folderid:<folderid>` `documentlink:<path>` хранения и экономии места.</span><span class="sxs-lookup"><span data-stu-id="e77c4-193">Note that placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="e77c4-194">В этом примере выполняется поиск трех разных папок почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="e77c4-194">This example searches three different mailbox folders.</span></span> <span data-ttu-id="e77c4-195">Аналогичный синтаксис запроса можно использовать для поиска в скрытых папках в папке "элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="e77c4-195">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="e77c4-196">В этом примере выполняется поиск элементов, содержащих точную фразу, в папке почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="e77c4-196">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="e77c4-197">В этом примере выполняется поиск в папке сайта (и всех вложенных папках) для документов, содержащих буквы "нда" в заголовке.</span><span class="sxs-lookup"><span data-stu-id="e77c4-197">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="e77c4-198">В этом примере выполняется поиск в папке сайта (и любой вложенной папке) для документов, которые были изменены в пределах диапазона дат.</span><span class="sxs-lookup"><span data-stu-id="e77c4-198">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="e77c4-199">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="e77c4-199">More information</span></span>

<span data-ttu-id="e77c4-200">При использовании сценария, описанного в этой статье, следует учитывать следующие моменты для выполнения целевых коллекций.</span><span class="sxs-lookup"><span data-stu-id="e77c4-200">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="e77c4-201">Сценарий не удаляет папки из результатов.</span><span class="sxs-lookup"><span data-stu-id="e77c4-201">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="e77c4-202">Поэтому некоторые папки, перечисленные в результатах, могут быть недоступными (или возвращать нулевые элементы), так как они содержат содержимое, созданное системой.</span><span class="sxs-lookup"><span data-stu-id="e77c4-202">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="e77c4-203">Этот сценарий возвращает только сведения о папке для основного почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="e77c4-203">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="e77c4-204">Он не возвращает сведения о папках в архивном почтовом ящике пользователя.</span><span class="sxs-lookup"><span data-stu-id="e77c4-204">It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="e77c4-205">При поиске в папках почтового ящика Поиск будет выполняться только в указанной папке (определяется `folderid` свойством); вложенные папки не будут выполнять поиск.</span><span class="sxs-lookup"><span data-stu-id="e77c4-205">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="e77c4-206">Чтобы выполнить поиск в вложенных папках, необходимо использовать идентификатор папки для вложенной папки, в которой требуется выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="e77c4-206">To search sub-folders, you need to use the  folder ID for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="e77c4-207">При поиске в папках сайта папка (определенная ее `documentlink` свойствами) и все вложенные папки будут искаться.</span><span class="sxs-lookup"><span data-stu-id="e77c4-207">When searching site folders, the folder (identified by its  `documentlink` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="e77c4-208">При экспорте результатов поиска, в которых вы указали только `folderid` свойство в поисковом запросе, вы можете выбрать первый вариант экспорта, "все элементы, кроме тех, которые имеют неизвестный формат, шифруются или не индексируются по другим причинам".</span><span class="sxs-lookup"><span data-stu-id="e77c4-208">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="e77c4-209">Все элементы в папке всегда будут экспортироваться независимо от состояния их индексирования, так как идентификатор папки всегда индексируется.</span><span class="sxs-lookup"><span data-stu-id="e77c4-209">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
