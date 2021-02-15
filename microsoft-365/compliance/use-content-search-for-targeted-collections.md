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
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="5dd9e-103">Использование поиска контента для целевых коллекций</span><span class="sxs-lookup"><span data-stu-id="5dd9e-103">Use Content Search for targeted collections</span></span>

<span data-ttu-id="5dd9e-104">Функция "Поиск контента" в Центре соответствия требованиям Microsoft 365 не предоставляет прямой путь в пользовательском интерфейсе для поиска определенных папок в почтовых ящиках Exchange, а также на сайтах SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-104">The Content Search feature in the Microsoft 365 compliance center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="5dd9e-105">Однако можно искать определенные папки (называемые целевой коллекцией), указав свойство ID папки для электронной почты или пути (DocumentLink) для сайтов в фактическом синтаксис запроса поиска.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="5dd9e-106">Использование поиска контента для выполнения целевой коллекции полезно, если вы уверены, что элементы, реагирующие на дела или привилегированные элементы, находятся в определенном почтовом ящике или папке сайта.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="5dd9e-107">С помощью сценария в этой статье можно получить ИД папки почтовых ящиков или путь (DocumentLink) для папок на сайте SharePoint и OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="5dd9e-108">Затем можно использовать ИД папки или путь в поисковом запросе, чтобы вернуть элементы, расположенные в папке.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="5dd9e-109">Для возврата контента, расположенного в папке на сайте SharePoint или OneDrive для бизнеса, сценарий в этом разделе использует управляемое свойство DocumentLink вместо свойства Path.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="5dd9e-110">Свойство DocumentLink является более надежным, чем свойство Path, так как оно возвращает все содержимое папки, тогда как свойство Path не возвращает некоторые файлы мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-run-a-targeted-collection"></a><span data-ttu-id="5dd9e-111">Перед запуском целевой коллекции</span><span class="sxs-lookup"><span data-stu-id="5dd9e-111">Before you run a targeted collection</span></span>

- <span data-ttu-id="5dd9e-112">Чтобы запустить сценарий на шаге 1, необходимо быть членом группы ролей "Менеджер по обнаружению электронных данных" в Центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="5dd9e-113">Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5dd9e-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

    <span data-ttu-id="5dd9e-114">Кроме того, вам должна быть назначена роль получателей почты в организации Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-114">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="5dd9e-115">Это необходимо для запуска включаемого в сценарий cmdlet **Get-MailboxFolderStatistics.**</span><span class="sxs-lookup"><span data-stu-id="5dd9e-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script.</span></span> <span data-ttu-id="5dd9e-116">По умолчанию роль получателей почты назначена группам ролей "Управление организацией" и "Управление получателями" в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="5dd9e-117">Дополнительные сведения о назначении разрешений в Exchange Online см. в под [управлением участников группы ролей.](https://go.microsoft.com/fwlink/p/?linkid=692102)</span><span class="sxs-lookup"><span data-stu-id="5dd9e-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102).</span></span> <span data-ttu-id="5dd9e-118">Вы также можете создать настраиваемую группу ролей, назначить для нее роль получателей почты, а затем добавить участников, которым необходимо выполнить сценарий на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="5dd9e-119">Дополнительные сведения см. в [под управлением групп ролей.](https://go.microsoft.com/fwlink/p/?linkid=730688)</span><span class="sxs-lookup"><span data-stu-id="5dd9e-119">For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>

- <span data-ttu-id="5dd9e-120">Сценарий в этой статье поддерживает современную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-120">The script in this article supports modern authentication.</span></span> <span data-ttu-id="5dd9e-121">Вы можете использовать сценарий как есть, если вы — microsoft 365 или организация Microsoft 365 GCC.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-121">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="5dd9e-122">Если вы — организация Office 365 Germany, Microsoft 365 GCC High или Microsoft 365 DoD, вам придется изменить сценарий, чтобы успешно запустить его.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-122">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="5dd9e-123">В частности, необходимо изменить строку и использовать параметр `Connect-ExchangeOnline` *ExchangeEnvironmentName* (и соответствующее значение для типа организации) для подключения к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-123">Specifically, you have to edit the line `Connect-ExchangeOnline` and use the *ExchangeEnvironmentName* parameter (and the appropriate value for your organization type) to connect to Exchange Online PowerShell.</span></span>  <span data-ttu-id="5dd9e-124">Кроме того, необходимо изменить строку и использовать параметры ConnectionUri и `Connect-IPPSSession` *AzureADAuthorizationEndpointUri* (и соответствующие значения для типа организации) для подключения к *PowerShell* Центра безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-124">Also, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="5dd9e-125">Дополнительные сведения см. в примерах в [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) Connect to Exchange Online [и Connect to Security & Compliance Center PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)</span><span class="sxs-lookup"><span data-stu-id="5dd9e-125">For more information, see the examples in [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?#connect-to-exchange-online-powershell-without-using-mfa) and [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="5dd9e-126">При каждом запуске сценария создается новый удаленный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-126">Each time you run the script, a new remote PowerShell session is created.</span></span> <span data-ttu-id="5dd9e-127">Это означает, что вы можете использовать все доступные удаленные сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-127">That means you can use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="5dd9e-128">Чтобы предотвратить это, запустите следующую команду, чтобы отключить активные удаленные сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-128">To prevent this from happening, run the following command to disconnect your active remote PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="5dd9e-129">Дополнительные сведения см. в статье [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="5dd9e-129">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="5dd9e-130">Сценарий включает минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-130">The script includes minimal error handling.</span></span> <span data-ttu-id="5dd9e-131">Основная цель сценария — быстрое отображение списка ИД папок почтовых ящиков или путей к сайту, которые можно использовать в синтаксисах поисковых запросов поиска контента для выполнения целевой коллекции.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-131">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>

- <span data-ttu-id="5dd9e-132">Пример сценария, предоставленный в этом разделе, не поддерживается ни в одной стандартной программе или службе поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-132">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="5dd9e-133">Пример сценария приводится в виде "как есть", без каких-либо гарантий.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-133">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="5dd9e-134">Кроме того, корпорация Microsoft отказывается от всех подразумеваемых гарантий, включая в том числе все подразумеваемые гарантии пригодности для продажи или определенной цели.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-134">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="5dd9e-135">Все риски, возникающие в результате использования примера сценария и документации, берет на себя пользователь.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-135">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="5dd9e-136">Корпорация Майкрософт, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценариев, ни при каких обстоятельствах не несут ответственность за какой-либо ущерб (в том числе, ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или неспособностью использовать примеры сценариев и документацию, даже если корпорации Майкрософт известно о возможности нанесения такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-136">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="5dd9e-137">Шаг 1. Запуск сценария для получения списка папок для почтового ящика или сайта</span><span class="sxs-lookup"><span data-stu-id="5dd9e-137">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="5dd9e-138">Сценарий, который вы запустите на этом первом этапе, возвращает список папок почтовых ящиков или папок SharePoint и OneDrive для бизнеса, а также соответствующий ид папки или путь для каждой папки.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-138">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="5dd9e-139">При запуске этого сценария вам будут предложены следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-139">When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="5dd9e-140">**Адрес электронной почты или URL-адрес** сайта: введите адрес электронной почты хранителя, чтобы получить список папок и папок почтовых ящиков Exchange.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-140">**Email address or site URL**: Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="5dd9e-141">Или введите URL-адрес сайта SharePoint или сайта OneDrive для бизнеса, чтобы получить список путей для указанного сайта.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-141">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="5dd9e-142">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="5dd9e-142">Here are some examples:</span></span>

  - <span data-ttu-id="5dd9e-143">**Exchange**: stacig@contoso.onmicrosoft <spam> <spam> .com</span><span class="sxs-lookup"><span data-stu-id="5dd9e-143">**Exchange**: stacig@contoso.onmicrosoft<spam><spam>.com</span></span>

  - <span data-ttu-id="5dd9e-144">**SharePoint**: https <span>://</span>contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="5dd9e-144">**SharePoint**: https<span>://</span>contoso.sharepoint.com/sites/marketing</span></span> 

  - <span data-ttu-id="5dd9e-145">**OneDrive для бизнеса**: https <span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="5dd9e-145">**OneDrive for Business**: https<span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 

- <span data-ttu-id="5dd9e-146">**Учетные** данные пользователя: сценарий будет использовать ваши учетные данные для подключения к Exchange Online PowerShell или PowerShell Центра безопасности и & соответствия требованиям с использованием современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-146">**Your user credentials**: The script will use your credentials to connect to Exchange Online PowerShell or Security & Compliance Center PowerShell using modern authentication.</span></span> <span data-ttu-id="5dd9e-147">Как объяснялось ранее, для успешного запуска этого сценария вам должны быть назначены соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-147">As previously explained, you have to be assigned the appropriate permissions to successfully run this script.</span></span>

<span data-ttu-id="5dd9e-148">Чтобы отобразить список папок почтовых ящиков или имен документов сайта (пути):</span><span class="sxs-lookup"><span data-stu-id="5dd9e-148">To display a list of mailbox folders or site documentlink (path) names:</span></span>
  
1. <span data-ttu-id="5dd9e-149">Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, `GetFolderSearchParameters.ps1` .</span><span class="sxs-lookup"><span data-stu-id="5dd9e-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>

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

2. <span data-ttu-id="5dd9e-150">На локальном компьютере откройте Windows PowerShell и перейдите в папку, в которой сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-150">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="5dd9e-151">Запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="5dd9e-151">Run the script; for example:</span></span>

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="5dd9e-152">Введите сведения, которые вам будет предложено ввести в сценарии.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-152">Enter the information that the script prompts you for.</span></span>

    <span data-ttu-id="5dd9e-153">Сценарий отображает список папок почтовых ящиков или папок сайта для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-153">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="5dd9e-154">Оставьте это окно открытым, чтобы вы могли скопировать ИД папки или имя ссылки на документ и вставьте его в поисковый запрос на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-154">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>

    > [!TIP]
    > <span data-ttu-id="5dd9e-155">Вместо отображения списка папок на экране компьютера можно перенаправить выходные данные сценария в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-155">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="5dd9e-156">Этот файл будет сохранен в папке, в которой находится сценарий.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-156">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="5dd9e-157">Например, чтобы перенаправить выходные данные сценария в текстовый файл, запустите следующую команду на шаге 3. Затем можно скопировать из файла ИД папки или ссылку на документ для использования в поисковом  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` запросе.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-157">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="5dd9e-158">Выходные данные скрипта для папок почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="5dd9e-158">Script output for mailbox folders</span></span>

<span data-ttu-id="5dd9e-159">Если вы получаете коды папок почтовых ящиков, сценарий подключается к Exchange Online PowerShell, запускается cmdlet **Get-MailboxFolderStatisics,** а затем отображается список папок из указанного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-159">If you're getting mailbox folder IDs, the script connects to Exchange Online PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="5dd9e-160">Для каждой папки в почтовом ящике сценарий отображает имя папки в столбце **FolderPath** и ее ИД в столбце **FolderQuery.**</span><span class="sxs-lookup"><span data-stu-id="5dd9e-160">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="5dd9e-161">Кроме того, сценарий добавляет префикс **folderId** (который является именем свойства почтового ящика) в ИД папки.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-161">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="5dd9e-162">Так как **свойство folderid** является свойством, которое можно найти, вы будете использовать в поисковом запросе на  `folderid:<folderid>` шаге 2 для поиска в этой папке.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-162">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="5dd9e-163">Сценарий отображает не более 100 папок почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-163">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5dd9e-164">Сценарий в этой статье содержит логику кодиации, которая преобразует 64-символьные значения кодов папок, которые возвращаются **Get-MailboxFolderStatistics,** в 48-символьный формат, индексируемый для поиска.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-164">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="5dd9e-165">Если вы только что запустите в PowerShell с помощью **get-MailboxFolderStatistics,** чтобы получить ИД папки (а не запускать сценарий в этой статье), поисковый запрос, использующий это значение, не будет работать.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-165">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="5dd9e-166">Чтобы получить правильно отформатированные ИД папок, которые можно использовать в поиске контента, необходимо запустить сценарий.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-166">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>
  
<span data-ttu-id="5dd9e-167">Вот пример выходных данных, возвращаемого сценарием для папок почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-167">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![Пример списка папок и папок почтовых ящиков, возвращаемого сценарием](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="5dd9e-169">В примере на шаге 2 показан запрос, используемый для поиска вложенной папки "Очистка" в папке пользователя "Элементы с возможностью восстановления".</span><span class="sxs-lookup"><span data-stu-id="5dd9e-169">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="5dd9e-170">Выходные данные скрипта для папок сайта</span><span class="sxs-lookup"><span data-stu-id="5dd9e-170">Script output for site folders</span></span>

<span data-ttu-id="5dd9e-171">Если вы получаете путь к свойству **documentlink** с сайтов SharePoint или OneDrive для бизнеса, сценарий подключается к PowerShell для обеспечения соответствия требованиям безопасности &, создает новый поиск контента, который выполняет поиск папок на сайте, а затем отображает список папок, расположенных на указанном сайте.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-171">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to Security & Compliance PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="5dd9e-172">Сценарий отображает имя каждой папки и добавляет префикс **documentlink** в URL-адрес папки.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-172">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="5dd9e-173">Так как **свойство documentlink** является свойством, которое можно найти, вы будете использовать пару property:value в поисковом запросе на шаге 2 для поиска `documentlink:<path>` в этой папке.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-173">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="5dd9e-174">Сценарий отображает не более 200 папок сайта.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-174">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="5dd9e-175">Если имеется более 200 папок сайта, отображаются самые новые папки.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-175">If there are more than 200 site folders, the newest ones are displayed.</span></span>
  
<span data-ttu-id="5dd9e-176">Вот пример выходных данных, возвращаемого сценарием для папок сайта.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-176">Here's an example of the output returned by the script for site folders.</span></span>
  
![Пример списка имен ссылок на документы для папок сайта, возвращаемого сценарием](../media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="5dd9e-178">Шаг 2. Использование ИД папки или ссылки на документ для выполнения целевой коллекции</span><span class="sxs-lookup"><span data-stu-id="5dd9e-178">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="5dd9e-179">После выполнения сценария для сбора списка папок или ссылок на документы для определенного пользователя необходимо перейти в Центр соответствия требованиям Microsoft 365 и создать новый поиск контента для поиска в определенной папке.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-179">After you've run the script to collect a list of folder IDs or document links for a specific user, the next step to go to the Microsoft 365 compliance center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="5dd9e-180">В поисковом запросе, настроенном в поле ключевых слов "Поиск контента" (или в качестве значения параметра  `folderid:<folderid>`  `documentlink:<path>`  *ContentMatchQuery,*  если используется cmdlet **New-ComplianceSearch),** используется пара "свойство-значение".</span><span class="sxs-lookup"><span data-stu-id="5dd9e-180">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="5dd9e-181">Свойство или свойство можно  `folderid` объединить  `documentlink` с другими параметрами поиска или условиями поиска.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-181">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="5dd9e-182">Если в запрос включено только свойство или свойство, поиск возвращает все элементы, расположенные  `folderid`  `documentlink` в указанной папке.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-182">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span>
  
1. <span data-ttu-id="5dd9e-183">Войдите в учетную запись и учетные данные, которые использовались для запуска сценария на [https://compliance.microsoft.com](https://compliance.microsoft.com) шаге 1.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-183">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the account and credentials that you used to run the script in Step 1.</span></span>

2. <span data-ttu-id="5dd9e-184">В левой области Центра соответствия требованиям щелкните **"Показать все** поиск контента" и выберите  >   **"Новый поиск".**</span><span class="sxs-lookup"><span data-stu-id="5dd9e-184">In the left pane of the compliance center, click **Show all** > **Content search**, and then click **New search**.</span></span>

3. <span data-ttu-id="5dd9e-185">В поле **"Ключевые** слова" в paste the `folderid:<folderid>` or value that was  `documentlink:<path>` returned by the script in Step 1.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-185">In the **Keywords** box, paste the `folderid:<folderid>` or  `documentlink:<path>` value that was returned by the script in Step 1.</span></span>

    <span data-ttu-id="5dd9e-186">Например, запрос на следующем снимке экрана будет искать любой элемент во вложенной папке "Очистка" в папке "Элементы с восстановления" пользователя (значение свойства вложенной папки "Очистка" показано на снимке экрана на шаге `folderid` 1):</span><span class="sxs-lookup"><span data-stu-id="5dd9e-186">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>

    ![Вложите папку или ссылку на документ в поле ключевого слова поискового запроса](../media/FolderIDSearchQuery.png)

4. <span data-ttu-id="5dd9e-188">В **области "Расположения"** выберите **"Определенные расположения"** и нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="5dd9e-188">Under **Locations**, select **Specific locations** and then click **Modify**.</span></span>

5. <span data-ttu-id="5dd9e-189">В зависимости от того, где вы ищете папку почтового ящика или сайта, сделайте одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="5dd9e-189">Do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>

    - <span data-ttu-id="5dd9e-190">Рядом с **электронной почтой Exchange** щелкните "Выбрать пользователей, группы или команды", а затем добавьте тот же почтовый **ящик,** который вы указали при сценарии на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-190">Next to **Exchange email**, click **Choose users, groups, or teams** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span>

      <span data-ttu-id="5dd9e-191">или</span><span class="sxs-lookup"><span data-stu-id="5dd9e-191">Or</span></span>

    - <span data-ttu-id="5dd9e-192">Рядом с **сайтами SharePoint** щелкните "Выбрать сайты", а затем добавьте тот же URL-адрес сайта, который был указан при сценарии на шаге 1. </span><span class="sxs-lookup"><span data-stu-id="5dd9e-192">Next to **SharePoint sites**, click **Choose sites** and then add the same site URL that you specified when you ran the script in Step 1.</span></span>

6. <span data-ttu-id="5dd9e-193">После сохранения расположения контента для поиска нажмите кнопку "Сохранить & **выполнить",** введите имя для поиска контента, а затем нажмите кнопку "Сохранить", чтобы запустить поиск в целевой коллекции. </span><span class="sxs-lookup"><span data-stu-id="5dd9e-193">After you save the content location to search, click **Save & run**, type a name for the Content Search, and then click **Save** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="5dd9e-194">Примеры поисковых запросов для целевых коллекций</span><span class="sxs-lookup"><span data-stu-id="5dd9e-194">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="5dd9e-195">Вот несколько примеров использования свойств и свойств в поисковом запросе  `folderid`  `documentlink` для выполнения целевой коллекции.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-195">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="5dd9e-196">Для и экономии места используются заметики. `folderid:<folderid>` `documentlink:<path>`</span><span class="sxs-lookup"><span data-stu-id="5dd9e-196">Placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span> 
  
- <span data-ttu-id="5dd9e-197">В этом примере выполняется поиск в трех различных папках почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-197">This example searches three different mailbox folders.</span></span> <span data-ttu-id="5dd9e-198">Для поиска скрытых папок в папке "Элементы с возможностью восстановления" пользователя можно использовать аналогичный синтаксис запроса.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-198">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="5dd9e-199">В этом примере выполняется поиск элементов, содержащих точную фразу, в папке почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-199">This example searches a mailbox folder for items that contain an exact phrase.</span></span>

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="5dd9e-200">В этом примере выполняется поиск в папке сайта (и всех вложенных папок) документов, содержащих буквы "NDA" в заголовке.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-200">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>

  ```powershell
  documentlink:<path> AND filename:nda
  ```

- <span data-ttu-id="5dd9e-201">В этом примере выполняется поиск документов, которые были изменены в пределах диапазона дат, в папке сайта (и в любой вложенной папке).</span><span class="sxs-lookup"><span data-stu-id="5dd9e-201">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>

  ```powershell
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="5dd9e-202">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="5dd9e-202">More information</span></span>

<span data-ttu-id="5dd9e-203">При использовании скрипта, написанного в этой статье, для выполнения целевых коллекций следует иметь в виду следующее.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-203">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="5dd9e-204">Сценарий не удаляет папки из результатов.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-204">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="5dd9e-205">Поэтому некоторые папки, перечисленные в результатах, могут быть недоступны для поиска (или возвращать элементы без возврата), так как они содержат контент, созданный системой, или содержат только вложенные папки, а не элементы почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-205">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content or because they only contain subfolders and not mailbox items.</span></span>

- <span data-ttu-id="5dd9e-206">Этот сценарий возвращает только сведения о папке для основного почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-206">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="5dd9e-207">Он не возвращает сведения о папках в архивном почтовом ящике пользователя.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-207">It doesn't return information about folders in the user's archive mailbox.</span></span> <span data-ttu-id="5dd9e-208">Чтобы получить сведения о папках в архивном почтовом ящике пользователя, можно изменить сценарий.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-208">To return information about folders in the user's archive mailbox, you can edit the script.</span></span> <span data-ttu-id="5dd9e-209">Для этого измените строку на строку, а затем сохраните и `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` запустите измененный сценарий.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-209">To do this, change the line `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` to `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` and then save and run the edited script.</span></span> <span data-ttu-id="5dd9e-210">Это изменение возвратит ИД папок и вложенных папок в архивном почтовом ящике пользователя.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-210">This change will return the folder IDs for folders and subfolders in the user's archive mailbox.</span></span> <span data-ttu-id="5dd9e-211">Чтобы найти весь архивный почтовый ящик, можно подключить все пары "свойство-значение" и "свойство-значение" к оператору `OR` в поисковом запросе.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-211">To search the entire archive mailbox, you can connect all folder ID property:value pairs with an `OR` operator in a search query.</span></span>

- <span data-ttu-id="5dd9e-212">При поиске в папках почтовых ящиков будет искаться только указанная папка (указанная по ее свойству), а вложенные папки не будут `folderid` искаться.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-212">When searching mailbox folders, only the specified folder (identified by its `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="5dd9e-213">Для поиска вложенных папок необходимо использовать ИД папки для вложенной папки, которую требуется найти.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-213">To search subfolders, you need to use the  folder ID for the subfolder that you want to search.</span></span>

- <span data-ttu-id="5dd9e-214">При поиске в папках сайта будет искаться папка (по ее свойству) и все `documentlink` вложенные папки.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-214">When searching site folders, the folder (identified by its `documentlink` property) and all subfolders will be searched.</span></span> 

- <span data-ttu-id="5dd9e-215">При экспорте результатов поиска, в которых указано только свойство в поисковом запросе, можно выбрать первый вариант экспорта: "Все элементы, кроме элементов, которые имеют неизвестный формат, шифруются или не индексируются по другим `folderid` причинам".</span><span class="sxs-lookup"><span data-stu-id="5dd9e-215">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="5dd9e-216">Все элементы в папке всегда будут экспортироваться независимо от их состояния индексации, так как ИД папки всегда индексируется.</span><span class="sxs-lookup"><span data-stu-id="5dd9e-216">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
