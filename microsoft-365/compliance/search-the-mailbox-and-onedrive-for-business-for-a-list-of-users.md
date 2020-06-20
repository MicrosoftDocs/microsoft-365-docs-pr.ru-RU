---
title: Поиск в почтовом ящике & OneDrive для бизнеса для просмотра списка пользователей с поиском контента
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
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
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Используйте поиск контента и сценарий, описанный в этой статье, для поиска группы пользователей в почтовых ящиках и на сайтах OneDrive для бизнеса.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 714574739256f98353f01478fb9216432f3dcb47
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818979"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="c2dc8-103">Использование поиска содержимого для поиска списка пользователей в почтовом ящике и на сайте OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c2dc8-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="c2dc8-104">Центр безопасности & соответствия требованиям предоставляет ряд командлетов Windows PowerShell, позволяющих автоматизировать задачи, связанные с обнаружением электронных данных.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-104">The Security & Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks.</span></span> <span data-ttu-id="c2dc8-105">В настоящее время создание поиска контента в центре безопасности & соответствия требованиям для поиска большого количества расположений содержимого хранитель занимает время и подготовку.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-105">Currently, creating a Content Search in the Security & Compliance Center to search a large number of custodian content locations takes time and preparation.</span></span> <span data-ttu-id="c2dc8-106">Перед созданием поиска необходимо собрать URL-адрес для каждого сайта OneDrive для бизнеса, а затем добавить в поиск каждый почтовый ящик и сайт OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-106">Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and OneDrive for Business site to the search.</span></span> <span data-ttu-id="c2dc8-107">В будущих выпусках этот процесс будет проще в центре безопасности & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-107">In future releases, this will be easier to do in the Security & Compliance Center.</span></span> <span data-ttu-id="c2dc8-108">До этого вы можете автоматизировать этот процесс с помощью сценария, описанного в этой статье.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-108">Until then, you can use the script in this article to automate this process.</span></span> <span data-ttu-id="c2dc8-109">Этот сценарий запрашивает имя домена личного сайта Организации (например, **contoso** в URL-адресе https://contoso-my.sharepoint.com) , список адресов электронной почты пользователей, имя нового поиска контента и используемый запрос поиска.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-109">This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), a list of user email addresses, the name of the new Content Search, and the search query to use.</span></span> <span data-ttu-id="c2dc8-110">Сценарий получает URL-адрес OneDrive для бизнеса для каждого пользователя в списке, а затем создает и запускает поиск контента, который выполняет поиск каждого пользователя в списке в почтовом ящике и OneDrive для бизнеса, используя предоставленный вами запрос поиска.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-110">The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span> 
  
## <a name="permissions-and-script-information"></a><span data-ttu-id="c2dc8-111">Сведения о разрешениях и сценариях</span><span class="sxs-lookup"><span data-stu-id="c2dc8-111">Permissions and script information</span></span>

- <span data-ttu-id="c2dc8-112">Вы должны быть участником группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & соответствия требованиям и глобальном администраторе SharePoint Online для запуска скрипта на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-112">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>
    
- <span data-ttu-id="c2dc8-113">Не забудьте сохранить список пользователей, созданных в действии 2, и сценарий, приведенный в шаге 3, в ту же папку.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-113">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="c2dc8-114">Это облегчит выполнение скрипта.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-114">That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="c2dc8-115">Сценарий включает в себя минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-115">The script includes minimal error handling.</span></span> <span data-ttu-id="c2dc8-116">Основная цель — быстро и легко искать в почтовом ящике и на сайте OneDrive для бизнеса каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-116">It's primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>
    
- <span data-ttu-id="c2dc8-117">Примеры сценариев, приведенные в этом разделе, не поддерживаются ни в одной из стандартных программ или услуг поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-117">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="c2dc8-118">Примеры сценариев предоставляются как есть и без каких-либо гарантий.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-118">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="c2dc8-119">Кроме того, корпорация Майкрософт отказывается [https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283) от всех мплиедных гарантий, включая, без ограничений, любые подразумеваемые гарантии пригодности для продавца или пригодности для конкретной цели.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-119">Microsoft further disclaims all i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="c2dc8-120">Ответственность за риск, возникающий в результате выполнения примеров сценариев и использования документации, полностью возлагается на вас.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-120">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="c2dc8-121">Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации сценариев, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров сценариев или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-121">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="c2dc8-122">Шаг 1. Установка командной консоли SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c2dc8-122">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="c2dc8-123">Первый шаг — установка командной консоли SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-123">The first step is to install the SharePoint Online Management Shell.</span></span> <span data-ttu-id="c2dc8-124">В этой процедуре не нужно использовать командную консоль, но ее необходимо установить, так как она содержит необходимые условия, необходимые для сценария, выполняемого на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-124">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="c2dc8-125">Эти условия позволяют сценарию связываться с SharePoint Online для получения URL-адресов сайтов OneDrive для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-125">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="c2dc8-126">Перейдите в раздел [Настройка среды Windows PowerShell для командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) и выполните действия 1 и 2, чтобы установить командную консоль SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-126">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="c2dc8-127">Шаг 2: Создание списка пользователей</span><span class="sxs-lookup"><span data-stu-id="c2dc8-127">Step 2: Generate a list of users</span></span>

<span data-ttu-id="c2dc8-128">Сценарий, приведенный в шаге 3, создаст поиск контента для поиска в почтовых ящиках и записях OneDrive для списка пользователей.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-128">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users.</span></span> <span data-ttu-id="c2dc8-129">Вы можете просто ввести адреса электронной почты в текстовом файле или выполнить команду в Windows PowerShell, чтобы получить список адресов электронной почты и сохранить их в файле (расположенном в той же папке, в которой вы сохранили сценарий на шаге 3).</span><span class="sxs-lookup"><span data-stu-id="c2dc8-129">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="c2dc8-130">Ниже приведена команда [PowerShell для Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283) , которую можно рунт, чтобы получить список адресов электронной почты для всех пользователей в Организации и сохранить его в текстовом файле с именем `Users.txt` .</span><span class="sxs-lookup"><span data-stu-id="c2dc8-130">Here's an [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="c2dc8-131">После выполнения этой команды не забудьте открыть файл и удалить заголовок, содержащий имя свойства `PrimarySmtpAddress` .</span><span class="sxs-lookup"><span data-stu-id="c2dc8-131">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="c2dc8-132">Текстовый файл должен содержать только список адресов электронной почты и ничего другое.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-132">The text file should just contain a list of email addresses, and nothing else.</span></span> <span data-ttu-id="c2dc8-133">Убедитесь, что в списке адресов электронной почты нет пустых строк.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-133">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="c2dc8-134">Шаг 3: запуск скрипта для создания и запуска поиска</span><span class="sxs-lookup"><span data-stu-id="c2dc8-134">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="c2dc8-135">При выполнении скрипта на этом этапе будут предложены следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-135">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="c2dc8-136">Перед выполнением скрипта обязательно убедитесь, что эти сведения готовы к работе.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-136">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="c2dc8-137">**Ваши учетные данные пользователя** : сценарий будет использовать ваши учетные данные для доступа к SharePoint Online, чтобы получить URL-адреса OneDrive для бизнеса и подключиться к центру безопасности & соответствия требованиям с помощью удаленной оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-137">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security & Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="c2dc8-138">**Имя домена личного сайта** — домен личного сайта, который содержит все сайты OneDrive для бизнеса в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-138">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="c2dc8-139">Например, если URL-адрес вашего домена личного времени указан **https://contoso-my.sharepoint.com** , то при вводе `contoso` сценария для имени домена личного сайта необходимо ввести запрос.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-139">For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="c2dc8-140">**Путь к текстовому файлу из шага 2** : путь к текстовому файлу, созданному в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-140">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2.</span></span> <span data-ttu-id="c2dc8-141">Если текстовый файл и сценарий находятся в одной папке, введите имя текстового файла.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-141">If the text file and the script are located in the same folder, then enter the name of the text file.</span></span> <span data-ttu-id="c2dc8-142">В противном случае введите полный путь к текстовому файлу.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-142">Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="c2dc8-143">**Имя поиска контента** — имя поиска контента, которое будет создано сценарием.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-143">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="c2dc8-144">**Поисковый запрос** — запрос поиска, который будет использоваться с поиском контента, создан и запущен.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-144">**Search query** - The search query that will be used with the Content Search is created and run.</span></span> <span data-ttu-id="c2dc8-145">Дополнительные сведения о поисковых запросах можно узнать в статье [запросы и условия поиска контента](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="c2dc8-145">For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="c2dc8-146">**Чтобы запустить сценарий, сделайте следующее:**</span><span class="sxs-lookup"><span data-stu-id="c2dc8-146">**To run the script:**</span></span>
    
1. <span data-ttu-id="c2dc8-147">Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `SearchEXOOD4B.ps1` .</span><span class="sxs-lookup"><span data-stu-id="c2dc8-147">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`.</span></span> <span data-ttu-id="c2dc8-148">Сохраните файл в ту же папку, в которой вы сохранили список пользователей, указанных в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-148">Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
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

2. <span data-ttu-id="c2dc8-149">Откройте Windows PowerShell и перейдите к папке, в которой сохранен сценарий, и список пользователей, указанных в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-149">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="c2dc8-150">Запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="c2dc8-150">Start the script; for example:</span></span>
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="c2dc8-151">При запросе учетных данных введите свой адрес электронной почты и пароль, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-151">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="c2dc8-152">Введите следующие сведения, когда запрашивается сценарий.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-152">Enter following information when prompted by the script.</span></span> <span data-ttu-id="c2dc8-153">Введите все данные и нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-153">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="c2dc8-154">Имя домена личного сайта.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-154">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="c2dc8-155">Путь к текстовому файлу, содержащему список пользователей.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-155">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="c2dc8-156">Имя для поиска контента.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-156">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="c2dc8-157">Поисковый запрос (оставьте это поле пустым, чтобы возвратить все элементы в расположениях контента).</span><span class="sxs-lookup"><span data-stu-id="c2dc8-157">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="c2dc8-158">Сценарий получает URL-адреса для каждого сайта OneDrive для бизнеса, а затем создает и запускает поиск.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-158">The script gets the URLs for each OneDrive for Business site and then creates and starts the search.</span></span> <span data-ttu-id="c2dc8-159">Вы можете запустить командлет **Get-ComplianceSearch** в консоли безопасности & центра соответствия требованиям, чтобы отобразить статистику и результаты поиска, или можно перейти на страницу **поиска содержимого** в центре безопасности & соответствия для просмотра сведений о поиске.</span><span class="sxs-lookup"><span data-stu-id="c2dc8-159">You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security & Compliance Center to view information about the search.</span></span> 
