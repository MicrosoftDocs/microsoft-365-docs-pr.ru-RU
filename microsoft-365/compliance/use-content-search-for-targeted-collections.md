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
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="991a9-103">Использование поиска контента для целевых коллекций</span><span class="sxs-lookup"><span data-stu-id="991a9-103">Use Content Search for targeted collections</span></span>

<span data-ttu-id="991a9-104">Функция поиска контента в центре соответствия требованиям Microsoft 365 не предоставляет прямой способ для поиска определенных папок в почтовых ящиках Exchange, а также на сайтах SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="991a9-104">The Content Search feature in the Microsoft 365 compliance center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="991a9-105">Тем не менее, можно выполнять поиск по определенным папкам (называемым *целевой коллекцией*), УКАЗАВ свойство ID папки для свойства email или Path (документлинк) для сайтов в фактическом синтаксисе поискового запроса.</span><span class="sxs-lookup"><span data-stu-id="991a9-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="991a9-106">Использование функции поиска контента для выполнения целевой коллекции полезно, если вы уверены, что элементы, реагирующие на обращение или привилегированные элементы, расположены в определенном почтовом ящике или папке сайта.</span><span class="sxs-lookup"><span data-stu-id="991a9-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="991a9-107">С помощью сценария, описанного в этой статье, можно получить идентификатор папки для папок почтовых ящиков или путь (Документлинк) для папок на сайте SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="991a9-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="991a9-108">Затем вы можете использовать идентификатор или путь к папке в запросе поиска, чтобы вернуть элементы, расположенные в папке.</span><span class="sxs-lookup"><span data-stu-id="991a9-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="991a9-109">Чтобы получить контент, расположенный в папке на сайте SharePoint или OneDrive для бизнеса, сценарий в этом разделе использует управляемое свойство Документлинк вместо свойства Path.</span><span class="sxs-lookup"><span data-stu-id="991a9-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="991a9-110">Свойство Документлинк является более надежным, чем свойство Path, так как оно возвращает весь контент в папке, а свойство Path не возвращает некоторые файлы мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="991a9-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-run-a-targeted-collection"></a><span data-ttu-id="991a9-111">Перед запуском целевой коллекции</span><span class="sxs-lookup"><span data-stu-id="991a9-111">Before you run a targeted collection</span></span>

- <span data-ttu-id="991a9-112">Вы должны быть участником группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & соответствия требованиям для запуска скрипта на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="991a9-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="991a9-113">Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="991a9-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

    <span data-ttu-id="991a9-114">Кроме того, необходимо назначить роль получателей почты в организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="991a9-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="991a9-115">Это необходимо для запуска командлета **Get-MailboxFolderStatistics** , включенного в сценарий.</span><span class="sxs-lookup"><span data-stu-id="991a9-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script.</span></span> <span data-ttu-id="991a9-116">По умолчанию роль получателей почты назначается группам ролей "Управление организацией" и "Управление получателями" в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="991a9-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="991a9-117">Дополнительные сведения о назначении разрешений в Exchange Online содержатся в разделе [Управление участниками группы ролей](https://go.microsoft.com/fwlink/p/?linkid=692102).</span><span class="sxs-lookup"><span data-stu-id="991a9-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="991a9-118">Вы также можете создать настраиваемую группу ролей, назначить ей роль получателей почты, а затем добавить участников, которым требуется запустить сценарий, на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="991a9-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="991a9-119">Дополнительные сведения можно найти в разделе [Manage Role Groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span><span class="sxs-lookup"><span data-stu-id="991a9-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>

- <span data-ttu-id="991a9-120">Сценарий, описанный в этой статье, поддерживает современная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="991a9-120">The script in this article supports modern authentication.</span></span> <span data-ttu-id="991a9-121">Вы можете использовать сценарий как есть, если вы используете Microsoft 365 или Microsoft 365 GCC.</span><span class="sxs-lookup"><span data-stu-id="991a9-121">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="991a9-122">Если вы являетесь организацией Office 365 Германия, высокоорганизационной организацией Microsoft 365 или Microsoft 365 DoD, вам потребуется изменить сценарий, чтобы успешно запустить его.</span><span class="sxs-lookup"><span data-stu-id="991a9-122">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="991a9-123">В частности, необходимо изменить строку `Connect-ExchangeOnline` и использовать параметр *ексчанжеенвиронментнаме* (и соответствующее значение для типа организации) для подключения к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="991a9-123">Specifically, you have to edit the line `Connect-ExchangeOnline` and use the *ExchangeEnvironmentName* parameter (and the appropriate value for your organization type) to connect to Exchange Online PowerShell.</span></span>  <span data-ttu-id="991a9-124">Кроме того, необходимо изменить строку `Connect-IPPSSession` и использовать параметры *ConnectionURI* и *азуреадаусоризатионендпоинтури* (и соответствующие значения для типа организации), чтобы подключиться к PowerShell центра безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="991a9-124">Also, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="991a9-125">Для получения дополнительных сведений ознакомьтесь с примерами, приведенными в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) , и [подключитесь к серверу безопасности & панели управления соответствия требованиям PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span><span class="sxs-lookup"><span data-stu-id="991a9-125">For more information, see the examples in [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) and [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="991a9-126">Каждый раз при запуске скрипта создается новый удаленный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="991a9-126">Each time you run the script, a new remote PowerShell session is created.</span></span> <span data-ttu-id="991a9-127">Это означает, что вы можете использовать все удаленные сеансы PowerShell, доступные вам.</span><span class="sxs-lookup"><span data-stu-id="991a9-127">That means you can use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="991a9-128">Чтобы избежать этого, выполните следующую команду, чтобы отключить активные сеансы удаленной среды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="991a9-128">To prevent this from happening, run the following command to disconnect your active remote PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="991a9-129">Дополнительные сведения см. в статье [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="991a9-129">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="991a9-130">Сценарий включает в себя минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="991a9-130">The script includes minimal error handling.</span></span> <span data-ttu-id="991a9-131">Основной целью сценария является быстрое отображение списка идентификаторов папок почтовых ящиков или путей сайтов, которые можно использовать в синтаксисе запроса поиска контента для выполнения целевой коллекции.</span><span class="sxs-lookup"><span data-stu-id="991a9-131">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>

- <span data-ttu-id="991a9-132">Пример сценария, представленный в этом разделе, не поддерживается ни в одной из стандартных программ или услуг поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="991a9-132">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="991a9-133">Пример сценария предоставляется без каких-либо гарантий.</span><span class="sxs-lookup"><span data-stu-id="991a9-133">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="991a9-134">Кроме того, корпорация Майкрософт отказывается от всех подразумеваемых гарантий, включая, но не ограничиваясь указанным, все подразумеваемые гарантии пригодности для продажи или определенной цели.</span><span class="sxs-lookup"><span data-stu-id="991a9-134">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="991a9-135">Весь риск, возникающий из примера использования или производительности примера сценария и документации, остается без вас.</span><span class="sxs-lookup"><span data-stu-id="991a9-135">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="991a9-136">Корпорация Майкрософт, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценариев, ни при каких обстоятельствах не несут ответственность за какой-либо ущерб (в том числе, ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или неспособностью использовать примеры сценариев и документацию, даже если корпорации Майкрософт известно о возможности нанесения такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="991a9-136">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="991a9-137">Шаг 1: запуск скрипта для получения списка папок для почтового ящика или сайта</span><span class="sxs-lookup"><span data-stu-id="991a9-137">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="991a9-138">Скрипт, выполняемый на первом шаге, вернет список папок почтовых ящиков или папок SharePoint и OneDrive для бизнеса, а также соответствующий идентификатор или путь к папке.</span><span class="sxs-lookup"><span data-stu-id="991a9-138">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="991a9-139">При выполнении этого сценария будет предложено ввести следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="991a9-139">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="991a9-140">**Адрес электронной почты или URL-адрес сайта**: введите адрес электронной почты хранитель, чтобы получить список папок почтовых ящиков Exchange и идентификаторов папок.</span><span class="sxs-lookup"><span data-stu-id="991a9-140">**Email address or site URL**: Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="991a9-141">Или введите URL-адрес сайта SharePoint или сайта OneDrive для бизнеса, чтобы получить список путей для указанного сайта.</span><span class="sxs-lookup"><span data-stu-id="991a9-141">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="991a9-142">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="991a9-142">Here are some examples:</span></span>

  - <span data-ttu-id="991a9-143">**Exchange**: stacig@contoso. onmicrosoft <spam> <spam> . com</span><span class="sxs-lookup"><span data-stu-id="991a9-143">**Exchange**: stacig@contoso.onmicrosoft<spam><spam>.com</span></span>

  - <span data-ttu-id="991a9-144">**SharePoint**: HTTPS <span>://</span>contoso.SharePoint.com/sites/Marketing</span><span class="sxs-lookup"><span data-stu-id="991a9-144">**SharePoint**: https<span>://</span>contoso.sharepoint.com/sites/marketing</span></span> 

  - <span data-ttu-id="991a9-145">**OneDrive для бизнеса**: HTTPS <span>://</span>Contoso-My.SharePoint.com/Personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="991a9-145">**OneDrive for Business**: https<span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 

- <span data-ttu-id="991a9-146">**Ваши учетные данные пользователя**: сценарий будет использовать ваши учетные данные для подключения к Exchange Online PowerShell или центр безопасности & безопасности PowerShell с помощью современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="991a9-146">**Your user credentials**: The script will use your credentials to connect to Exchange Online PowerShell or Security & Compliance Center PowerShell using modern authentication.</span></span> <span data-ttu-id="991a9-147">Как было сказано ранее, вам необходимо назначить соответствующие разрешения для успешного выполнения этого сценария.</span><span class="sxs-lookup"><span data-stu-id="991a9-147">As previously explained, you have to be assigned the appropriate permissions to successfully run this script.</span></span>

<span data-ttu-id="991a9-148">Чтобы отобразить список папок почтовых ящиков или документлинк (путей) сайта, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="991a9-148">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="991a9-149">Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `GetFolderSearchParameters.ps1` .</span><span class="sxs-lookup"><span data-stu-id="991a9-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>

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

2. <span data-ttu-id="991a9-150">На локальном компьютере откройте Windows PowerShell и перейдите к папке, в которой был сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="991a9-150">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="991a9-151">Запуск скрипта; Например:</span><span class="sxs-lookup"><span data-stu-id="991a9-151">Run the script; for example:</span></span>

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="991a9-152">Введите сведения, которые будут запрашиваться сценарием.</span><span class="sxs-lookup"><span data-stu-id="991a9-152">Enter the information that the script prompts you for.</span></span>

    <span data-ttu-id="991a9-153">В этом сценарии отображается список папок или папок почтового ящика для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="991a9-153">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="991a9-154">Оставьте это окно открытым, чтобы можно было скопировать идентификатор папки или имя документлинк и вставить его в поисковый запрос на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="991a9-154">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>

    > [!TIP]
    > <span data-ttu-id="991a9-155">Вместо того чтобы отображать список папок на экране компьютера, можно повторно перенаправить выходные данные сценария в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="991a9-155">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="991a9-156">Этот файл будет сохранен в папке, в которой расположен сценарий.</span><span class="sxs-lookup"><span data-stu-id="991a9-156">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="991a9-157">Например, чтобы перенаправить выходные данные сценария в текстовый файл, выполните следующую команду на шаге 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` затем вы можете скопировать идентификатор папки или документлинк из файла для использования в поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="991a9-157">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="991a9-158">Вывод сценариев для папок почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="991a9-158">Script output for mailbox folders</span></span>

<span data-ttu-id="991a9-159">Если вы получаете идентификаторы папок почтовых ящиков, сценарий подключается к Exchange Online PowerShell, запускает командлет **Get-маилбоксфолдерстатисикс** , а затем отображает список папок из указанного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="991a9-159">If you're getting mailbox folder IDs, the script connects to Exchange Online PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="991a9-160">Для каждой папки в почтовом ящике сценарий отображает имя папки в столбце **FolderPath** и идентификатор папки в столбце **фолдеркуери** .</span><span class="sxs-lookup"><span data-stu-id="991a9-160">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="991a9-161">Кроме того, скрипт добавляет префикс **FolderId** (имя свойства почтового ящика) к идентификатору папки.</span><span class="sxs-lookup"><span data-stu-id="991a9-161">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="991a9-162">Так как свойство **FolderId** является свойством для поиска, вы будете использовать поисковую  `folderid:<folderid>` папку в запросе поиска на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="991a9-162">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="991a9-163">В этом сценарии отображается не более 100 папок почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="991a9-163">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="991a9-164">Сценарий, описанный в этой статье, включает логику кодирования, преобразующую значения идентификаторов папок 64-character, которые возвращаются командой **Get-MailboxFolderStatistics** , в тот же формат 48 символов, который индексируется для поиска.</span><span class="sxs-lookup"><span data-stu-id="991a9-164">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="991a9-165">Если вы просто выполняете командлет **Get-MailboxFolderStatistics** в PowerShell, чтобы получить идентификатор папки (вместо того, чтобы выполнять сценарий в этой статье), поисковый запрос, в котором используется значение идентификатора этой папки, завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="991a9-165">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="991a9-166">Для получения правильно отформатированных идентификаторов папок, которые можно использовать при поиске контента, необходимо выполнить сценарий.</span><span class="sxs-lookup"><span data-stu-id="991a9-166">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="991a9-167">Ниже приведен пример выходных данных, возвращаемых сценарием для папок почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="991a9-167">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![Пример списка папок и идентификаторов папок почтовых ящиков, возвращенных сценарием](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="991a9-169">В примере на шаге 2 показан запрос, используемый для поиска вложенной папки "очистки" в папке "элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="991a9-169">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="991a9-170">Выходные данные сценариев для папок сайта</span><span class="sxs-lookup"><span data-stu-id="991a9-170">Script output for site folders</span></span>

<span data-ttu-id="991a9-171">Если вы получаете путь к свойству **документлинк** из сайтов SharePoint или OneDrive для бизнеса, сценарий подключается к системе безопасности & соответствии с оболочкой PowerShell, создает новый поиск контента, который ищет папки на сайте, а затем отображает список папок, расположенных на указанном сайте.</span><span class="sxs-lookup"><span data-stu-id="991a9-171">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to Security & Compliance PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="991a9-172">В этом сценарии отображается имя каждой папки и добавляется префикс **документлинк** к URL-адресу папки.</span><span class="sxs-lookup"><span data-stu-id="991a9-172">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="991a9-173">Так как свойство **документлинк** является свойством, `documentlink:<path>` поддерживающим Поиск, для поиска в этой папке используется значение "свойство: значение" в поисковом запросе на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="991a9-173">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="991a9-174">В этом сценарии отображается не более 200 папок сайта.</span><span class="sxs-lookup"><span data-stu-id="991a9-174">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="991a9-175">Если количество папок сайта превышает 200, отображаются последние из них.</span><span class="sxs-lookup"><span data-stu-id="991a9-175">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="991a9-176">Ниже приведен пример выходных данных, возвращаемых сценарием для папок сайта.</span><span class="sxs-lookup"><span data-stu-id="991a9-176">Here's an example of the output returned by the script for site folders.</span></span>
  
![Пример списка имен документлинк для папок сайта, возвращаемых сценарием](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="991a9-178">Шаг 2: использование идентификатора папки или документлинк для выполнения целевой коллекции</span><span class="sxs-lookup"><span data-stu-id="991a9-178">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="991a9-179">После выполнения сценария для сбора списка идентификаторов папок или ссылок на документы для определенного пользователя необходимо перейти в центр соответствия требованиям Microsoft 365 и создать новый поиск контента для поиска в определенной папке.</span><span class="sxs-lookup"><span data-stu-id="991a9-179">After you've run the script to collect a list of folder IDs or document links for a specific user, the next step to go to the Microsoft 365 compliance center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="991a9-180">В  `folderid:<folderid>`  `documentlink:<path>` поле ключевое слово поиска контента (или в качестве значения параметра  *контентматчкуери*  при использовании командлета **New-ComplianceSearch** ) будет использоваться значение "свойство: значение" в запросе поиска, которое вы настроили.</span><span class="sxs-lookup"><span data-stu-id="991a9-180">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="991a9-181">Можно сочетать  `folderid`  `documentlink` свойство или с другими параметрами поиска или условиями поиска.</span><span class="sxs-lookup"><span data-stu-id="991a9-181">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="991a9-182">Если вы включаете  `folderid`  `documentlink` в запрос только свойство или, то поиск вернет все элементы, расположенные в указанной папке.</span><span class="sxs-lookup"><span data-stu-id="991a9-182">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span>
  
1. <span data-ttu-id="991a9-183">Перейдите на страницу [https://compliance.microsoft.com](https://compliance.microsoft.com) и войдите, используя учетную запись и учетные данные, которые использовались для запуска скрипта на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="991a9-183">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the account and credentials that you used to run the script in Step 1.</span></span>

2. <span data-ttu-id="991a9-184">В левой области центра соответствия требованиям щелкните **Показать**  >  **Поиск всего контента**, а затем нажмите кнопку **создать поиск**.</span><span class="sxs-lookup"><span data-stu-id="991a9-184">In the left pane of the compliance center, click **Show all** > **Content search**, and then click **New search**.</span></span>

3. <span data-ttu-id="991a9-185">В поле **Ключевые слова** вставьте `folderid:<folderid>`  `documentlink:<path>` значение или значение, возвращенное сценарием на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="991a9-185">In the **Keywords** box, paste the `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span>

    <span data-ttu-id="991a9-186">Например, запрос на следующем снимке экрана будет искать любой элемент в подпапке "очистки" в папке "элементы с возможностью восстановления" (значение `folderid` свойства для вложенной папки "очистки" отображается на снимке экрана на шаге 1):</span><span class="sxs-lookup"><span data-stu-id="991a9-186">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>

    ![Вставьте FolderId или документлинк в поле ключевое слово поискового запроса.](../media/FolderIDSearchQuery.png)

4. <span data-ttu-id="991a9-188">В разделе **расположения** выберите **определенные расположения** и нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="991a9-188">Under **Locations**, select **Specific locations** and then click **Modify**.</span></span>

5. <span data-ttu-id="991a9-189">Выполните одно из следующих действий в зависимости от того, выполняется ли поиск в папке почтового ящика или в папке сайта:</span><span class="sxs-lookup"><span data-stu-id="991a9-189">Do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>

    - <span data-ttu-id="991a9-190">Рядом с пунктом **Электронная почта Exchange** нажмите кнопку **выбрать пользователей, группы или Teams** , а затем добавьте тот же почтовый ящик, который вы указали при выполнении сценария на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="991a9-190">Next to **Exchange email**, click **Choose users, groups, or teams** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span>

      <span data-ttu-id="991a9-191">или</span><span class="sxs-lookup"><span data-stu-id="991a9-191">Or</span></span>

    - <span data-ttu-id="991a9-192">Рядом с пунктом **сайты SharePoint** нажмите кнопку **выбрать сайты** , а затем добавьте тот же URL-адрес сайта, который вы указали при выполнении сценария, описанного в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="991a9-192">Next to **SharePoint sites**, click **Choose sites** and then add the same site URL that you specified when you ran the script in Step 1.</span></span>

6. <span data-ttu-id="991a9-193">После сохранения расположения контента для поиска нажмите кнопку **сохранить & выполнить**, введите имя для поиска контента, а затем нажмите кнопку **сохранить** , чтобы запустить поиск целевой коллекции.</span><span class="sxs-lookup"><span data-stu-id="991a9-193">After you save the content location to search, click **Save & run**, type a name for the Content Search, and then click **Save** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="991a9-194">Примеры запросов поиска для целевых коллекций</span><span class="sxs-lookup"><span data-stu-id="991a9-194">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="991a9-195">Ниже приведено несколько примеров использования  `folderid` свойств и  `documentlink` в запросе поиска для выполнения целевой коллекции.</span><span class="sxs-lookup"><span data-stu-id="991a9-195">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="991a9-196">Заполнители используются для  `folderid:<folderid>` хранения и  `documentlink:<path>` экономии места.</span><span class="sxs-lookup"><span data-stu-id="991a9-196">Placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="991a9-197">В этом примере выполняется поиск трех разных папок почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="991a9-197">This example searches three different mailbox folders.</span></span> <span data-ttu-id="991a9-198">Аналогичный синтаксис запроса можно использовать для поиска в скрытых папках в папке "элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="991a9-198">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="991a9-199">В этом примере выполняется поиск элементов, содержащих точную фразу, в папке почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="991a9-199">This example searches a mailbox folder for items that contain an exact phrase.</span></span>

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="991a9-200">В этом примере выполняется поиск в папке сайта (и всех вложенных папках) для документов, содержащих буквы "нда" в заголовке.</span><span class="sxs-lookup"><span data-stu-id="991a9-200">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="991a9-201">В этом примере выполняется поиск в папке сайта (и любой вложенной папке) для документов, которые были изменены в пределах диапазона дат.</span><span class="sxs-lookup"><span data-stu-id="991a9-201">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="991a9-202">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="991a9-202">More information</span></span>

<span data-ttu-id="991a9-203">При использовании сценария, описанного в этой статье, следует учитывать следующие моменты для выполнения целевых коллекций.</span><span class="sxs-lookup"><span data-stu-id="991a9-203">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="991a9-204">Сценарий не удаляет папки из результатов.</span><span class="sxs-lookup"><span data-stu-id="991a9-204">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="991a9-205">Поэтому некоторые папки, перечисленные в результатах, могут быть недоступными (или возвращать нулевые элементы), так как они содержат содержимое, созданное системой, или они содержат только вложенные папки, а не элементы почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="991a9-205">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content or because they only contain subfolders and not mailbox items.</span></span>

- <span data-ttu-id="991a9-206">Этот сценарий возвращает только сведения о папке для основного почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="991a9-206">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="991a9-207">Он не возвращает сведения о папках в архивном почтовом ящике пользователя.</span><span class="sxs-lookup"><span data-stu-id="991a9-207">It doesn't return information about folders in the user's archive mailbox.</span></span> <span data-ttu-id="991a9-208">Чтобы получить сведения о папках в архивном почтовом ящике пользователя, можно изменить сценарий.</span><span class="sxs-lookup"><span data-stu-id="991a9-208">To return information about folders in the user's archive mailbox, you can edit the script.</span></span> <span data-ttu-id="991a9-209">Для этого измените строку, `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` а затем сохраните и запустите измененный скрипт.</span><span class="sxs-lookup"><span data-stu-id="991a9-209">To do this, change the line `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` to `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` and then save and run the edited script.</span></span> <span data-ttu-id="991a9-210">Это изменение вернет идентификаторы папок и вложенных папок в архивном почтовом ящике пользователя.</span><span class="sxs-lookup"><span data-stu-id="991a9-210">This change will return the folder IDs for folders and subfolders in the user's archive mailbox.</span></span> <span data-ttu-id="991a9-211">Чтобы выполнить поиск по всему архивному почтовому ящику, можно подключить все пары свойств идентификатора папки: значение с `OR` оператором в запросе поиска.</span><span class="sxs-lookup"><span data-stu-id="991a9-211">To search the entire archive mailbox, you can connect all folder ID property:value pairs with an `OR` operator in a search query.</span></span>

- <span data-ttu-id="991a9-212">При поиске в папках почтового ящика Поиск будет выполняться только в указанной папке (определяется `folderid` свойством); вложенные папки не будут выполнять поиск.</span><span class="sxs-lookup"><span data-stu-id="991a9-212">When searching mailbox folders, only the specified folder (identified by its `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="991a9-213">Чтобы найти вложенные папки, необходимо использовать идентификатор папки для вложенной папки, в которой требуется выполнить поиск.</span><span class="sxs-lookup"><span data-stu-id="991a9-213">To search subfolders, you need to use the  folder ID for the subfolder that you want to search.</span></span>

- <span data-ttu-id="991a9-214">При поиске в папках сайта папка (определенная ее `documentlink` свойствами) и все вложенные папки будут искаться.</span><span class="sxs-lookup"><span data-stu-id="991a9-214">When searching site folders, the folder (identified by its `documentlink` property) and all subfolders will be searched.</span></span> 

- <span data-ttu-id="991a9-215">При экспорте результатов поиска, в которых вы указали только `folderid` свойство в поисковом запросе, вы можете выбрать первый вариант экспорта, "все элементы, кроме тех, которые имеют неизвестный формат, шифруются или не индексируются по другим причинам".</span><span class="sxs-lookup"><span data-stu-id="991a9-215">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="991a9-216">Все элементы в папке всегда будут экспортироваться независимо от состояния их индексирования, так как идентификатор папки всегда индексируется.</span><span class="sxs-lookup"><span data-stu-id="991a9-216">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
