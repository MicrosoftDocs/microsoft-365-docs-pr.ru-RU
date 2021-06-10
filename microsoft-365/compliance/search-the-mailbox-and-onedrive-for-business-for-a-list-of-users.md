---
title: Поиск на сайте & OneDrive для бизнеса почтового ящика для списка пользователей с помощью поиска контента
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
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
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Используйте поиск контента и сценарий в этой статье для поиска почтовых ящиков и OneDrive для бизнеса сайтов для группы пользователей.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51e668438c6016a0c5f2c914dc2b2e86cc56f49e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922471"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="e9fa4-103">Использование поиска содержимого для поиска списка пользователей в почтовом ящике и на сайте OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e9fa4-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="e9fa4-104">Центр & безопасности предоставляет ряд Windows PowerShell, которые позволяет автоматизировать задачи, связанные с электронным открытием, отнимающие много времени.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="e9fa4-105">В настоящее время создание поиска контента в Центре & безопасности для поиска большого количества местоположений контента хранителя требует времени и подготовки.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="e9fa4-106">Перед созданием поиска необходимо собрать URL-адрес для каждого OneDrive для бизнеса, а затем добавить в поиск каждый почтовый ящик и OneDrive для бизнеса сайт.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="e9fa4-107">В будущих выпусках это будет проще сделать в Центре & безопасности.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="e9fa4-108">До этого момента можно использовать сценарий в этой статье для автоматизации этого процесса.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="e9fa4-109">В этом скрипте вы можете найти имя домена MySite организации (например, **contoso** в URL-адресе), список адресов электронной почты пользователей, имя нового поиска контента и запрос на `https://contoso-my.sharepoint.com` поиск.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL `https://contoso-my.sharepoint.com`), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="e9fa4-110">Сценарий получает URL OneDrive для бизнеса для каждого пользователя в списке, а затем создает и запускает поиск контента, который ищет почтовый ящик и OneDrive для бизнеса для каждого пользователя в списке, используя поисковый запрос, который вы предоставляете.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span>
  
## <a name="permissions-and-script-information"></a><span data-ttu-id="e9fa4-111">Сведения о разрешениях и сценариях</span><span class="sxs-lookup"><span data-stu-id="e9fa4-111">Permissions and script information</span></span>

- <span data-ttu-id="e9fa4-112">Чтобы запустить сценарий в шаге 3, необходимо быть членом группы ролей диспетчера электронных данных в Центре & безопасности и глобальным администратором SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>

- <span data-ttu-id="e9fa4-113">Не забудьте сохранить список пользователей, которые вы создаете в шаге 2, и скрипт в шаге 3 в той же папке.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="e9fa4-114">Это облегчит запуск сценария.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-114">That will make it easier to run the script.</span></span>

- <span data-ttu-id="e9fa4-115">Сценарий включает минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-115">The script includes minimal error handling.</span></span> <span data-ttu-id="e9fa4-116">Его основная цель — быстро и легко искать почтовый ящик и OneDrive для бизнеса сайта каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-116">Its primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>

- <span data-ttu-id="e9fa4-p104">Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="e9fa4-122">Шаг 1. Установка командной консоли SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e9fa4-122">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="e9fa4-123">Первым шагом является установка SharePoint Online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-123">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="e9fa4-124">Вы не должны использовать оболочку в этой процедуре, но ее необходимо установить, так как она содержит предварительные требования, необходимые сценарию, который вы запустите в шаге 3.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-124">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="e9fa4-125">Эти условия позволяют скрипту взаимодействовать с SharePoint Online для получения URL-адресов для OneDrive для бизнеса сайтов.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-125">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="e9fa4-126">Перейдите к установке SharePoint [сетевой](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) Windows PowerShell и выполните шаг 1 и шаг 2 для установки SharePoint online Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-126">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="e9fa4-127">Шаг 2. Создание списка пользователей</span><span class="sxs-lookup"><span data-stu-id="e9fa4-127">Step 2: Generate a list of users</span></span>

<span data-ttu-id="e9fa4-128">Сценарий в шаге 3 создаст поиск контента для поиска почтовых ящиков и OneDrive учетных записей для списка пользователей.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-128">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="e9fa4-129">Вы можете просто ввести адреса электронной почты в текстовом файле или запустить команду в Windows PowerShell, чтобы получить список адресов электронной почты и сохранить их в файле (расположен в той же папке, в которую вы сохраните сценарий в шаге 3).</span><span class="sxs-lookup"><span data-stu-id="e9fa4-129">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="e9fa4-130">Вот команда [Exchange Online PowerShell,](/powershell/exchange/connect-to-exchange-online-powershell) в которую можно запустить, чтобы получить список адресов электронной почты для всех пользователей в организации и сохранить его в текстовом файле с именем `Users.txt` .</span><span class="sxs-lookup"><span data-stu-id="e9fa4-130">Here's an [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="e9fa4-131">После запуска этой команды обязательно откройте файл и удалите заготку с именем  `PrimarySmtpAddress` свойства.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-131">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="e9fa4-132">В текстовом файле должен быть только список адресов электронной почты и ничего другого.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-132">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="e9fa4-133">Убедитесь, что до или после списка адресов электронной почты не существует пустых строк.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-133">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="e9fa4-134">Шаг 3. Запустите сценарий для создания и запуска поиска</span><span class="sxs-lookup"><span data-stu-id="e9fa4-134">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="e9fa4-135">При запуске скрипта на этом этапе будет предложена следующая информация.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-135">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="e9fa4-136">Убедитесь, что эти сведения будут готовы перед запуском сценария.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-136">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="e9fa4-137">Учетные данные пользователей **—** скрипт будет использовать учетные данные для доступа SharePoint Online для получения URL OneDrive для бизнеса и подключения к Центру соответствия требованиям безопасности & с помощью удаленной powerShell.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-137">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="e9fa4-138">**Имя домена MySite** . Домен MySite — это домен, содержащий все OneDrive для бизнеса в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-138">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="e9fa4-139">Например, если URL-адрес для домена MySite есть, вы введите, когда сценарий подсказит вам имя **https://contoso-my.sharepoint.com**  `contoso` домена MySite.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-139">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="e9fa4-140">**Имя текста из шага 2** — имя пути текстового файла, созданного в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-140">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="e9fa4-141">Если текстовый файл и скрипт находятся в одной папке, введите имя текстового файла.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-141">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="e9fa4-142">В противном случае введите полное имя пути для текстового файла.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-142">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="e9fa4-143">**Имя поиска контента** — имя поиска контента, который будет создан по сценарию.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-143">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="e9fa4-144">**Поисковый запрос** . Создается и запустится поисковый запрос, который будет использоваться с помощью поиска контента.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-144">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="e9fa4-145">Дополнительные сведения о поисковых запросах см. в статье [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md)</span><span class="sxs-lookup"><span data-stu-id="e9fa4-145">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="e9fa4-146">**Чтобы запустить сценарий, сделайте следующее:**</span><span class="sxs-lookup"><span data-stu-id="e9fa4-146">**To run the script:**</span></span>
    
1. <span data-ttu-id="e9fa4-147">Сохраните следующий текст в Windows PowerShell скрипта с помощью суффикса .ps1; например, `SearchEXOOD4B.ps1` .</span><span class="sxs-lookup"><span data-stu-id="e9fa4-147">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="e9fa4-148">Сохраните файл в той же папке, в которой сохранен список пользователей в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-148">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
  ```powershell
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. <span data-ttu-id="e9fa4-149">Откройте Windows PowerShell и перейдите в папку, в которой сохранен сценарий и список пользователей из шага 2.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-149">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="e9fa4-150">Запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="e9fa4-150">Start the script; for example:</span></span>
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="e9fa4-151">При запросе учетных данных введите адрес электронной почты и пароль, а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-151">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="e9fa4-152">Ввод следующих сведений по запросу скрипта.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-152">Enter following information when prompted by the script.</span></span> <span data-ttu-id="e9fa4-153">Введите каждый элемент информации и нажмите кнопку **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-153">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="e9fa4-154">Имя домена MySite.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-154">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="e9fa4-155">Имя пути текстового файла, который содержит список пользователей.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-155">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="e9fa4-156">Имя поиска контента.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-156">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="e9fa4-157">Запрос поиска (оставьте этот пробел, чтобы вернуть все элементы в расположениях контента).</span><span class="sxs-lookup"><span data-stu-id="e9fa4-157">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="e9fa4-158">Скрипт получает URL-адреса для OneDrive для бизнеса сайта, а затем создает и запускает поиск.</span><span class="sxs-lookup"><span data-stu-id="e9fa4-158">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="e9fa4-159">Для отображения статистики и результатов поиска можно запустить в Центре безопасности & PowerShell cmdlet **Get-ComplianceSearch,** а можно перейти на страницу поиска контента в Центре соответствия требованиям & безопасности, чтобы просмотреть сведения о поиске. </span><span class="sxs-lookup"><span data-stu-id="e9fa4-159">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span>