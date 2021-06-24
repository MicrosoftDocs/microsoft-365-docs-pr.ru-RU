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
description: Используйте поиск контента в Центр соответствия требованиям Microsoft 365 для выполнения целевой коллекции, которая ищет элементы в определенном почтовом ящике или папке сайта.
ms.openlocfilehash: 925a6e5e0e56c63cde8bfa1b39cca6e64abcd016
ms.sourcegitcommit: 8b79d276f71f22bcaeb150e78e35101cb1ae0375
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114756"
---
# <a name="use-content-search-for-targeted-collections"></a><span data-ttu-id="9ec8e-103">Использование поиска контента для целевых коллекций</span><span class="sxs-lookup"><span data-stu-id="9ec8e-103">Use Content search for targeted collections</span></span>

<span data-ttu-id="9ec8e-104">Средство поиска контента в Центр соответствия требованиям Microsoft 365 не обеспечивает прямой путь в пользовательском интерфейсе для поиска определенных папок в Exchange почтовых ящиках или SharePoint и OneDrive для бизнеса сайтах.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-104">The Content search tool in the Microsoft 365 compliance center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites.</span></span> <span data-ttu-id="9ec8e-105">Однако можно искать определенные папки (называемые целевой коллекцией), указав свойство ID папок для свойства электронной почты или пути (DocumentLink) для сайтов в синтаксис запроса поиска.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-105">However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID property for email or path (DocumentLink) property for sites in the actual search query syntax.</span></span> <span data-ttu-id="9ec8e-106">Использование поиска контента для выполнения целевой коллекции полезно, если вы уверены, что элементы, реагирующие на конкретный случай или привилегированные элементы, находятся в определенном почтовом ящике или папке сайта.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-106">Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder.</span></span> <span data-ttu-id="9ec8e-107">Сценарий в этой статье можно использовать для получения ID папок для папок почтовых ящиков или пути (DocumentLink) для папок на SharePoint и OneDrive для бизнеса сайте.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-107">You can use the script in this article to obtain the folder ID for mailbox folders or the path (DocumentLink) for folders on a SharePoint and OneDrive for Business site.</span></span> <span data-ttu-id="9ec8e-108">Затем вы можете использовать папку ID или путь в запросе поиска для возврата элементов, расположенных в папке.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-108">Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>

> [!NOTE]
> <span data-ttu-id="9ec8e-109">Чтобы вернуть содержимое, расположенное в папке на сайте SharePoint или OneDrive для бизнеса, сценарий в этом разделе использует управляемое свойство DocumentLink вместо свойства Path.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-109">To return content located in a folder in a SharePoint or OneDrive for Business site, the script in this topic uses the DocumentLink managed property instead of the Path property.</span></span> <span data-ttu-id="9ec8e-110">Свойство DocumentLink является более надежным, чем свойство Path, так как возвращает все содержимое в папке, в то время как свойство Path не возвращает некоторые файлы мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-110">The DocumentLink property is more robust than the Path property because it will return all content in a folder, whereas the Path property won't return some media files.</span></span>

## <a name="before-you-run-a-targeted-collection"></a><span data-ttu-id="9ec8e-111">Перед запуском целевой коллекции</span><span class="sxs-lookup"><span data-stu-id="9ec8e-111">Before you run a targeted collection</span></span>

- <span data-ttu-id="9ec8e-112">Чтобы запустить сценарий в шаге 1, необходимо быть членом группы ролей диспетчера электронных данных в центре & безопасности.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-112">You have to be a member of the eDiscovery Manager role group in Security & Compliance Center to run the script in Step 1.</span></span> <span data-ttu-id="9ec8e-113">Дополнительные сведения см. в статье [Назначение разрешений на обнаружение электронных данных](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9ec8e-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="9ec8e-114">Кроме того, в вашей организации Exchange Online роли получателей почты.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-114">You also have to be assigned the Mail Recipients role in your Exchange Online organization.</span></span> <span data-ttu-id="9ec8e-115">Это необходимо для запуска **комлета Get-MailboxFolderStatistics,** который входит в сценарий.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-115">This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script.</span></span> <span data-ttu-id="9ec8e-116">По умолчанию роль получателей почты назначена группам ролей управления организацией и управления получателями в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-116">By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online.</span></span> <span data-ttu-id="9ec8e-117">Дополнительные сведения о назначении разрешений в Exchange Online см. в Exchange Online [Управление участниками группы ролей.](/exchange/manage-role-group-members-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="9ec8e-117">For more information about assigning permissions in Exchange Online, see [Manage role group members](/exchange/manage-role-group-members-exchange-2013-help).</span></span> <span data-ttu-id="9ec8e-118">Можно также создать настраиваемую группу ролей, назначить ему роль получателей почты, а затем добавить участников, которым необходимо выполнить сценарий в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-118">You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1.</span></span> <span data-ttu-id="9ec8e-119">Дополнительные сведения см. в [см. в "Управление группами ролей".](/Exchange/permissions-exo/role-groups)</span><span class="sxs-lookup"><span data-stu-id="9ec8e-119">For more information, see [Manage role groups](/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="9ec8e-120">Сценарий в этой статье поддерживает современную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-120">The script in this article supports modern authentication.</span></span> <span data-ttu-id="9ec8e-121">Сценарий можно использовать как есть, если вы Microsoft 365 или Microsoft 365 GCC организации.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-121">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="9ec8e-122">Если вы — Office 365, Microsoft 365 GCC или организация Microsoft 365 DoD, вам придется изменить сценарий, чтобы успешно запустить его.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-122">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="9ec8e-123">В частности, для подключения к Exchange Online PowerShell необходимо изменить строку и использовать параметр `Connect-ExchangeOnline` *ExchangeEnvironmentName* (и соответствующее значение для типа организации).</span><span class="sxs-lookup"><span data-stu-id="9ec8e-123">Specifically, you have to edit the line `Connect-ExchangeOnline` and use the *ExchangeEnvironmentName* parameter (and the appropriate value for your organization type) to connect to Exchange Online PowerShell.</span></span>  <span data-ttu-id="9ec8e-124">Кроме того, необходимо изменить строку и использовать параметры `Connect-IPPSSession` *ConnectionUri* и *AzureADAuthorizationEndpointUri* (и соответствующие значения для типа организации) для подключения к Центру & соответствия требованиям PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-124">Also, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="9ec8e-125">Дополнительные сведения см. в примерах Подключение в [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) и Подключение безопасности & [PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)центра соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-125">For more information, see the examples in [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-without-using-mfa) and [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="9ec8e-126">При каждом запуске сценария создается новая удаленная сессия PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-126">Each time you run the script, a new remote PowerShell session is created.</span></span> <span data-ttu-id="9ec8e-127">Это означает, что вы можете использовать все доступные удаленные сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-127">That means you can use up all the remote PowerShell sessions available to you.</span></span> <span data-ttu-id="9ec8e-128">Чтобы этого не произошло, запустите следующую команду, чтобы отключить активные удаленные сеансы PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-128">To prevent this from happening, run the following command to disconnect your active remote PowerShell sessions.</span></span>

  ```powershell
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="9ec8e-129">Дополнительные сведения см. в статье [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="9ec8e-129">For more information, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="9ec8e-130">Сценарий включает минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-130">The script includes minimal error handling.</span></span> <span data-ttu-id="9ec8e-131">Основная цель сценария — быстрое отображение списка ID-адресов папок почтовых ящиков или путей сайта, которые можно использовать в синтаксисе поисковых запросов поиска контента для выполнения целевой коллекции.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-131">The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>

- <span data-ttu-id="9ec8e-132">Пример сценария, представленного в этом разделе, не поддерживается ни в рамках стандартной программы поддержки Майкрософт, ни в службе.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-132">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="9ec8e-133">Пример сценария приводится в виде "как есть", без каких-либо гарантий.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-133">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="9ec8e-134">Кроме того, корпорация Microsoft отказывается от всех подразумеваемых гарантий, включая в том числе все подразумеваемые гарантии пригодности для продажи или определенной цели.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-134">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="9ec8e-135">Все риски, возникающие в результате использования примера сценария и документации, берет на себя пользователь.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-135">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="9ec8e-136">Корпорация Майкрософт, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценариев, ни при каких обстоятельствах не несут ответственность за какой-либо ущерб (в том числе, ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или неспособностью использовать примеры сценариев и документацию, даже если корпорации Майкрософт известно о возможности нанесения такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-136">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="9ec8e-137">Шаг 1. Запустите скрипт, чтобы получить список папок для почтового ящика или сайта</span><span class="sxs-lookup"><span data-stu-id="9ec8e-137">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="9ec8e-138">Сценарий, который вы запустите на этом первом шаге, возвращает список папок почтовых ящиков или SharePoint и OneDrive для бизнеса, а также соответствующий ID или путь папки для каждой папки.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-138">The script that you run in this first step will return a list of mailbox folders or SharePoint and OneDrive for Business folders, and the corresponding folder ID or path for each folder.</span></span> <span data-ttu-id="9ec8e-139">При запуске этого скрипта вы сможете получить следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-139">When you run this script, it will prompt you for the following information.</span></span>

- <span data-ttu-id="9ec8e-140">**Адрес электронной** почты или URL-адрес сайта: введите адрес электронной почты хранителя, чтобы вернуть список Exchange почтовых ящиков и ИД папок.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-140">**Email address or site URL**: Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs.</span></span> <span data-ttu-id="9ec8e-141">Или введите URL SharePoint или OneDrive для бизнеса, чтобы вернуть список путей для указанного сайта.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-141">Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site.</span></span> <span data-ttu-id="9ec8e-142">Ниже приводятся примеры:</span><span class="sxs-lookup"><span data-stu-id="9ec8e-142">Here are some examples:</span></span>

  - <span data-ttu-id="9ec8e-143">**Exchange**: stacig@contoso.onmicrosoft <spam> <spam> .com</span><span class="sxs-lookup"><span data-stu-id="9ec8e-143">**Exchange**: stacig@contoso.onmicrosoft<spam><spam>.com</span></span>

  - <span data-ttu-id="9ec8e-144">**SharePoint**: https <span>://</span>contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="9ec8e-144">**SharePoint**: https<span>://</span>contoso.sharepoint.com/sites/marketing</span></span>

  - <span data-ttu-id="9ec8e-145">**OneDrive для бизнеса**: https <span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="9ec8e-145">**OneDrive for Business**: https<span>://</span>contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span>

- <span data-ttu-id="9ec8e-146">**Учетные** данные пользователей. Скрипт будет использовать учетные данные для подключения к Exchange Online PowerShell или службе безопасности & PowerShell с помощью современной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-146">**Your user credentials**: The script will use your credentials to connect to Exchange Online PowerShell or Security & Compliance Center PowerShell using modern authentication.</span></span> <span data-ttu-id="9ec8e-147">Как объяснялось ранее, для успешного запуска этого сценария необходимо получить соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-147">As previously explained, you have to be assigned the appropriate permissions to successfully run this script.</span></span>

<span data-ttu-id="9ec8e-148">Отображение списка папок почтовых ящиков или имен ссылки на документы сайта (пути):</span><span class="sxs-lookup"><span data-stu-id="9ec8e-148">To display a list of mailbox folders or site documentlink (path) names:</span></span>

1. <span data-ttu-id="9ec8e-149">Сохраните следующий текст в Windows PowerShell скрипта с помощью суффикса .ps1; например, `GetFolderSearchParameters.ps1` .</span><span class="sxs-lookup"><span data-stu-id="9ec8e-149">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>

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

2. <span data-ttu-id="9ec8e-150">На локальном компьютере откройте Windows PowerShell и перейдите в папку, в которой сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-150">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="9ec8e-151">Запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="9ec8e-151">Run the script; for example:</span></span>

   ```powershell
   .\GetFolderSearchParameters.ps1
   ```

4. <span data-ttu-id="9ec8e-152">Введите сведения, которые вам подсказывует скрипт.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-152">Enter the information that the script prompts you for.</span></span>

    <span data-ttu-id="9ec8e-153">Скрипт отображает список папок почтовых ящиков или папок сайта для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-153">The script displays a list of mailbox folders or site folders for the specified user.</span></span> <span data-ttu-id="9ec8e-154">Оставьте это окно открытым, чтобы можно было скопировать ИД папки или имя documentlink и вставьте его в поисковый запрос в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-154">Leave this window open so that you can copy a folder ID or documentlink name and paste it in to a search query in Step 2.</span></span>

    > [!TIP]
    > <span data-ttu-id="9ec8e-155">Вместо отображения списка папок на экране компьютера можно перенаправить выход скрипта в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-155">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file.</span></span> <span data-ttu-id="9ec8e-156">Этот файл будет сохранен в папке, в которой находится сценарий.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-156">This file will be saved to the folder where the script is located.</span></span> <span data-ttu-id="9ec8e-157">Например, чтобы перенаправить выход скрипта в текстовый файл, запустите следующую команду в шаге 3. Затем вы можете скопировать ИД папки или документообнаправление из файла для использования в поисковом  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` запросе.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-157">For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or documentlink from the file to use in a search query.</span></span>

### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="9ec8e-158">Выход скрипта для папок почтовых ящиков</span><span class="sxs-lookup"><span data-stu-id="9ec8e-158">Script output for mailbox folders</span></span>

<span data-ttu-id="9ec8e-159">Если вы получаете ID-коды папок почтовых ящиков, сценарий подключается к Exchange Online PowerShell, запускает комлет **Get-MailboxFolderStatisics,** а затем отображает список папок из указанного почтового ящика.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-159">If you're getting mailbox folder IDs, the script connects to Exchange Online PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox.</span></span> <span data-ttu-id="9ec8e-160">Для каждой папки в почтовом ящике скрипт отображает имя папки в столбце **FolderPath** и ИД папки в столбце **FolderQuery.**</span><span class="sxs-lookup"><span data-stu-id="9ec8e-160">For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column.</span></span> <span data-ttu-id="9ec8e-161">Кроме того, скрипт добавляет префикс **папкиId** (это имя свойства почтового ящика) в папку ID.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-161">Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID.</span></span> <span data-ttu-id="9ec8e-162">Так как свойство **папки** является свойством, которое можно найти, вы будете использовать в запросе поиска в шаге 2 для поиска  `folderid:<folderid>` этой папки.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-162">Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="9ec8e-163">Скрипт отображает не более 100 папок почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-163">The script displays a maximum of 100 mailbox folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ec8e-164">Сценарий в этой статье включает логику кодиротворяния, которая преобразует значения Id папки с 64 символами, которые возвращаются **Get-MailboxFolderStatistics** в тот же формат с 48-символами, индексируемый для поиска.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-164">The script in this article includes encoding logic that converts the 64-character folder Id values that are returned by **Get-MailboxFolderStatistics** to the same 48-character format that is indexed for search.</span></span> <span data-ttu-id="9ec8e-165">Если вы только что запустите комлет **Get-MailboxFolderStatistics** в PowerShell, чтобы получить код папки (вместо запуска скрипта в этой статье), поисковый запрос, использующий это значение папки, не удастся.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-165">If you just run the **Get-MailboxFolderStatistics** cmdlet in PowerShell to obtain a folder Id (instead of running the script in this article), a search query that uses that folder Id value will fail.</span></span> <span data-ttu-id="9ec8e-166">Чтобы получить правильно отформатированные папки, которые можно использовать в поиске контента, необходимо запустить сценарий.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-166">You have to run the script to get the correctly-formatted folder Ids that can be used in a Content Search.</span></span>

<span data-ttu-id="9ec8e-167">Вот пример вывода, возвращаемого скриптом для папок почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-167">Here's an example of the output returned by the script for mailbox folders.</span></span>

![Пример списка папок почтовых ящиков и ИД папок, возвращенных скриптом](../media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)

<span data-ttu-id="9ec8e-169">В примере на шаге 2 показан запрос, используемый для поиска подмостков purges в папке "Извлекаемые элементы" пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-169">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>

### <a name="script-output-for-site-folders"></a><span data-ttu-id="9ec8e-170">Выход скрипта для папок сайта</span><span class="sxs-lookup"><span data-stu-id="9ec8e-170">Script output for site folders</span></span>

<span data-ttu-id="9ec8e-171">Если вы получаете путь свойства **documentlink** с сайтов SharePoint или OneDrive для бизнеса, скрипт подключается к PowerShell & безопасности, создает новый поиск контента, который ищет сайт для папок, а затем отображает список папок, расположенных на указанном сайте.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-171">If you're getting the path of the **documentlink** property from SharePoint or OneDrive for Business sites, the script connects to Security & Compliance PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site.</span></span> <span data-ttu-id="9ec8e-172">Скрипт отображает имя каждой папки и добавляет префикс **ссылки** на документы в URL-адрес папки.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-172">The script displays the name of each folder and adds the prefix of **documentlink** to the folder URL.</span></span> <span data-ttu-id="9ec8e-173">Так как **свойство documentlink** — это свойство, которое можно найти, для поиска в этой папке используется пара свойства:значение в запросе поиска на `documentlink:<path>` шаге 2.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-173">Because the **documentlink** property is a searchable property, you'll use `documentlink:<path>` property:value pair in a search query in Step 2 to search that folder.</span></span> <span data-ttu-id="9ec8e-174">Скрипт отображает не более 200 папок сайта.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-174">The script displays a maximum of 200 site folders.</span></span> <span data-ttu-id="9ec8e-175">Если на сайте более 200 папок, отображаются самые новые.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-175">If there are more than 200 site folders, the newest ones are displayed.</span></span>

<span data-ttu-id="9ec8e-176">Вот пример вывода, возвращаемого скриптом для папок сайта.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-176">Here's an example of the output returned by the script for site folders.</span></span>

![Пример списка имен documentlink для папок сайтов, возвращенных скриптом](../media/519e8347-7365-4067-af78-96c465dc3d15.png)

## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a><span data-ttu-id="9ec8e-178">Шаг 2. Используйте ID папки или документополулка для выполнения целевой коллекции</span><span class="sxs-lookup"><span data-stu-id="9ec8e-178">Step 2: Use a folder ID or documentlink to perform a targeted collection</span></span>

<span data-ttu-id="9ec8e-179">После запуска скрипта для сбора списка папок или ссылок на документы для определенного пользователя следующий шаг, чтобы перейти к Центр соответствия требованиям Microsoft 365 и создать новый поиск контента для поиска определенной папки.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-179">After you've run the script to collect a list of folder IDs or document links for a specific user, the next step to go to the Microsoft 365 compliance center and create a new Content Search to search a specific folder.</span></span> <span data-ttu-id="9ec8e-180">В поисковом запросе, настраиваемом в поле ключевого слова "Поиск контента" (или в качестве значения для параметра  `folderid:<folderid>`  `documentlink:<path>`  *ContentMatchQuery,*  если используется кодлет **New-ComplianceSearch,** используется пара свойств или значений).</span><span class="sxs-lookup"><span data-stu-id="9ec8e-180">You'll use the  `folderid:<folderid>` or  `documentlink:<path>` property:value pair in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet).</span></span> <span data-ttu-id="9ec8e-181">Вы можете объединить свойство  `folderid`  `documentlink` или свойство с другими параметрами поиска или условиями поиска.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-181">You can combine the  `folderid` or  `documentlink` property with other search parameters or search conditions.</span></span> <span data-ttu-id="9ec8e-182">Если в запрос включено только свойство или свойство, поиск возвращает все элементы, расположенные  `folderid`  `documentlink` в указанной папке.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-182">If you only include the  `folderid` or  `documentlink` property in the query, the search will return all items located in the specified folder.</span></span>

1. <span data-ttu-id="9ec8e-183">Перейдите к учетной записи и учетным данным, которые использовались для запуска сценария в <https://compliance.microsoft.com> шаге 1.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-183">Go to <https://compliance.microsoft.com> and sign in using the account and credentials that you used to run the script in Step 1.</span></span>

2. <span data-ttu-id="9ec8e-184">В левой области центра соответствия щелкните **Показать** весь поиск контента  >  и нажмите **кнопку Новый поиск.**</span><span class="sxs-lookup"><span data-stu-id="9ec8e-184">In the left pane of the compliance center, click **Show all** > **Content search**, and then click **New search**.</span></span>

3. <span data-ttu-id="9ec8e-185">В поле **"Ключевые** слова" вклеить значение или значение, возвращенные сценарием `folderid:<folderid>` в  `documentlink:<path>/*` шаге 1.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-185">In the **Keywords** box, paste the `folderid:<folderid>` or  `documentlink:<path>/*` value that was returned by the script in Step 1.</span></span>

    <span data-ttu-id="9ec8e-186">Например, запрос на следующем скриншоте будет искать любой элемент в подмастере Purges в папке "Извлекаемые элементы" пользователя (значение свойства подмостков Purges показано на скриншоте на `folderid` шаге 1):</span><span class="sxs-lookup"><span data-stu-id="9ec8e-186">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>

    ![Вложите папку или ссылку на документ в поле ключевого слова запроса поиска](../media/FolderIDSearchQuery.png)
    > [!IMPORTANT]
    > <span data-ttu-id="9ec8e-188">Для поиска documentlink необходимо использовать следовую  `asterisk '/*'` ссылку.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-188">documentlink searches require the use of a trailing  `asterisk '/*'`.</span></span>  

4. <span data-ttu-id="9ec8e-189">В **соответствии с положениями** выберите **конкретные расположения** и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-189">Under **Locations**, select **Specific locations** and then click **Modify**.</span></span>

5. <span data-ttu-id="9ec8e-190">Сделайте одно из следующих сообщений, основываясь на том, ищете ли вы папку почтовых ящиков или папку сайта:</span><span class="sxs-lookup"><span data-stu-id="9ec8e-190">Do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>

    - <span data-ttu-id="9ec8e-191">Рядом с **Exchange** нажмите кнопку **Выберите пользователей,** групп или групп, а затем добавьте тот же почтовый ящик, который был указан при 1-м этапе.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-191">Next to **Exchange email**, click **Choose users, groups, or teams** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span>

      <span data-ttu-id="9ec8e-192">или</span><span class="sxs-lookup"><span data-stu-id="9ec8e-192">Or</span></span>

    - <span data-ttu-id="9ec8e-193">Рядом с **SharePoint сайтами** щелкните **Выберите** сайты и добавьте тот же URL-адрес сайта, который был указан при 1-м этапе.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-193">Next to **SharePoint sites**, click **Choose sites** and then add the same site URL that you specified when you ran the script in Step 1.</span></span>

6. <span data-ttu-id="9ec8e-194">После сохранения расположения контента для поиска нажмите кнопку Сохранить **&** запустить, введите имя для поиска контента, а затем нажмите сохранить, чтобы начать целевой поиск коллекции. </span><span class="sxs-lookup"><span data-stu-id="9ec8e-194">After you save the content location to search, click **Save & run**, type a name for the Content Search, and then click **Save** to start the targeted collection search.</span></span>

### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="9ec8e-195">Примеры поисковых запросов для целевых коллекций</span><span class="sxs-lookup"><span data-stu-id="9ec8e-195">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="9ec8e-196">Вот несколько примеров использования свойств и свойств в запросе поиска для  `folderid`  `documentlink` выполнения целевой коллекции.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-196">Here are some examples of using the  `folderid` and  `documentlink` properties in a search query to perform a targeted collection.</span></span> <span data-ttu-id="9ec8e-197">Держатели используются для  `folderid:<folderid>` и  `documentlink:<path>` для сохранения пространства.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-197">Placeholders are used for  `folderid:<folderid>` and  `documentlink:<path>` to save space.</span></span>

- <span data-ttu-id="9ec8e-198">В этом примере выполняется поиск трех разных папок почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-198">This example searches three different mailbox folders.</span></span> <span data-ttu-id="9ec8e-199">Аналогичный синтаксис запроса можно использовать для поиска скрытых папок в папке "Извлекаемые элементы" пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-199">You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>

  ```powershell
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="9ec8e-200">В этом примере выполняется поиск папки почтовых ящиков для элементов, содержащих точную фразу.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-200">This example searches a mailbox folder for items that contain an exact phrase.</span></span>

  ```powershell
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="9ec8e-201">В этом примере выполняется поиск папки сайта (и любых подвещений) для документов, содержащих буквы "NDA" в заголовке.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-201">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>

  ```powershell
  documentlink:"<path>/*" AND filename:nda
  ```

- <span data-ttu-id="9ec8e-202">В этом примере выполняется поиск папки сайта (и любых подвещений) для документов, которые были изменены в диапазоне дат.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-202">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>

  ```powershell
  documentlink:"<path>/*" AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```

## <a name="more-information"></a><span data-ttu-id="9ec8e-203">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="9ec8e-203">More information</span></span>

<span data-ttu-id="9ec8e-204">Следует помнить о следующих вещах при использовании сценария в этой статье для выполнения целевых коллекций.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-204">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>

- <span data-ttu-id="9ec8e-205">Скрипт не удаляет папки из результатов.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-205">The script doesn't remove any folders from the results.</span></span> <span data-ttu-id="9ec8e-206">Так что некоторые папки, перечисленные в результатах, могут быть неотвечены (или возвращают нулевые элементы), так как содержат контент, созданный системой, или потому, что они содержат только подмостки, а не элементы почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-206">So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content or because they only contain subfolders and not mailbox items.</span></span>

- <span data-ttu-id="9ec8e-207">Этот скрипт возвращает только данные папок для основного почтового ящика пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-207">This script only returns folder information for the user's primary mailbox.</span></span> <span data-ttu-id="9ec8e-208">Он не возвращает сведения о папках в архивном почтовом ящике пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-208">It doesn't return information about folders in the user's archive mailbox.</span></span> <span data-ttu-id="9ec8e-209">Чтобы вернуть сведения о папках в архивном почтовом ящике пользователя, можно изменить сценарий.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-209">To return information about folders in the user's archive mailbox, you can edit the script.</span></span> <span data-ttu-id="9ec8e-210">Для этого измените строку, а затем сохраните и `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` запустите отредактированную скрипт.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-210">To do this, change the line `$folderStatistics = Get-MailboxFolderStatistics $emailAddress` to `$folderStatistics = Get-MailboxFolderStatistics $emailAddress -Archive` and then save and run the edited script.</span></span> <span data-ttu-id="9ec8e-211">Это изменение возвращает папки для папок и подмостков в архивном почтовом ящике пользователя.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-211">This change will return the folder IDs for folders and subfolders in the user's archive mailbox.</span></span> <span data-ttu-id="9ec8e-212">Чтобы найти весь архивный почтовый ящик, можно подключить все свойство ID папки: пары значений с оператором `OR` в запросе поиска.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-212">To search the entire archive mailbox, you can connect all folder ID property:value pairs with an `OR` operator in a search query.</span></span>

- <span data-ttu-id="9ec8e-213">При поиске папок почтовых ящиков будет искаться только указанная папка (определенная ее свойством), подмостки не будут `folderid` искаться.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-213">When searching mailbox folders, only the specified folder (identified by its `folderid` property) will be searched; subfolders won't be searched.</span></span> <span data-ttu-id="9ec8e-214">Чтобы найти подмостки, необходимо использовать папку ID для подмостка, которую необходимо искать.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-214">To search subfolders, you need to use the  folder ID for the subfolder that you want to search.</span></span>

- <span data-ttu-id="9ec8e-215">При поиске папок сайта будет искаться папка (определенная ее свойством) и все `documentlink` подмостки.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-215">When searching site folders, the folder (identified by its `documentlink` property) and all subfolders will be searched.</span></span>

- <span data-ttu-id="9ec8e-216">При экспорте результатов поиска, в котором вы только указали свойство в запросе поиска, можно выбрать первый вариант экспорта: "Все элементы, за исключением элементов, не указанных в неузнаваемом формате, шифруются или не индексируются по другим `folderid` причинам".</span><span class="sxs-lookup"><span data-stu-id="9ec8e-216">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons."</span></span> <span data-ttu-id="9ec8e-217">Все элементы в папке всегда будут экспортироваться независимо от состояния индексации, так как ID папки всегда индексируется.</span><span class="sxs-lookup"><span data-stu-id="9ec8e-217">All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
