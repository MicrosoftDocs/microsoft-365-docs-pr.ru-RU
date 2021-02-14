---
title: Поиск списка пользователей с & oneDrive для бизнеса в почтовом ящике
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
description: Используйте поиск контента и сценарий в этой статье для поиска группы пользователей в почтовых ящиках и на сайтах OneDrive для бизнеса.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e3a10913cc4d8618e3d25bdf34e30c9d55a43324
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357801"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Использование поиска содержимого для поиска списка пользователей в почтовом ящике и на сайте OneDrive для бизнеса

Центр безопасности & соответствия требованиям предоставляет ряд Windows PowerShell, которые обеспечивают автоматизацию трудоемких задач, связанных с eDiscovery. В настоящее время создание поиска контента в Центре & соответствия требованиям для поиска большого количества местоположений контента хранителя требует времени и подготовки. Перед созданием поиска необходимо собрать URL-адрес для каждого сайта OneDrive для бизнеса, а затем добавить в поиск каждый почтовый ящик и сайт OneDrive для бизнеса. В последующих выпусках это будет проще сделать в Центре безопасности & соответствия требованиям. До этого момента вы можете использовать сценарий, данная статья, для автоматизации этого процесса. Этот сценарий запрашивает имя домена MySite вашей организации (например, **contoso** в URL-адресе), список адресов электронной почты пользователей, имя нового поиска контента и поисковый запрос для `https://contoso-my.sharepoint.com` использования. Сценарий получает URL-адрес OneDrive для бизнеса для каждого пользователя в списке, а затем создает и запускает поиск контента, который выполняет поиск в почтовом ящике и на сайте OneDrive для бизнеса для каждого пользователя в списке, используя поисковый запрос, который вы предоставляете.
  
## <a name="permissions-and-script-information"></a>Разрешения и сведения о скриптах

- Для запуска сценария на шаге 3 необходимо быть членом группы ролей "Руководитель службы eDiscovery" в Центре безопасности и соответствия требованиям & и глобальным администратором SharePoint Online.

- Обязательно сохраните список пользователей, который вы создали на шаге 2, и скрипт на шаге 3 в ту же папку. Это упростит запуск сценария.

- Сценарий включает минимальную обработку ошибок. Его основная цель — быстро и легко искать в почтовом ящике и на сайте OneDrive для бизнеса каждого пользователя.

- Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Шаг 1. Установка командной консоли SharePoint Online

Первым шагом является установка оболочки управления SharePoint Online. Вам не нужно использовать оболочку в этой процедуре, но ее необходимо установить, так как она содержит необходимые порядок, необходимые для скрипта, который вы запустите в шаге 3. Эти необходимые условия позволяют сценарию взаимодействовать с SharePoint Online для получения URL-адресов сайтов OneDrive для бизнеса.
  
Перейдите к разделу "Настройка среды управления [Windows PowerShell SharePoint Online"](https://go.microsoft.com/fwlink/p/?LinkID=286318) и выполните шаг 1 и шаг 2, чтобы установить оболочку управления SharePoint Online.
  
## <a name="step-2-generate-a-list-of-users"></a>Шаг 2. Создание списка пользователей

Сценарий на шаге 3 создаст поиск контента для поиска списка пользователей в почтовых ящиках и учетных записях OneDrive. Вы можете просто ввести адреса электронной почты в текстовый файл или выполнить команду в Windows PowerShell, чтобы получить список адресов электронной почты и сохранить их в файл (расположенный в той же папке, в которую вы сохраните сценарий на шаге 3).
  
Вот команда [Exchange Online PowerShell,](https://go.microsoft.com/fwlink/p/?LinkId=517283) которую можно запустить, чтобы получить список адресов электронной почты для всех пользователей в организации и сохранить его в текстовый файл с именем `Users.txt` . 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

После запуска этой команды обязательно откройте файл и удалите заглавную папку с именем  `PrimarySmtpAddress` свойства. Текстовый файл должен содержать только список адресов электронной почты, и больше ничего. Убедитесь, что до или после списка адресов электронной почты нет пустых строк.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Шаг 3. Запуск скрипта для создания и запуска поиска

При запуске скрипта на этом этапе вам будут предложены следующие сведения. Перед запуском сценария обязательно подготовьтесь к этим данным.
  
-  Учетные данные пользователя. Сценарий будет использовать ваши учетные данные для доступа к SharePoint Online, чтобы получить URL-адреса OneDrive для бизнеса и подключиться к Центру безопасности & и соответствия требованиям с помощью удаленной powerShell. 
    
- **Имя вашего домена MySite** — это домен, содержащий все сайты OneDrive для бизнеса в вашей организации. Например, если URL-адресом для вашего домена MySite является , то вы вводите, когда сценарий запросит имя вашего домена **https://contoso-my.sharepoint.com**  `contoso` MySite. 
    
- **Путь к текстовом файлу** из шага 2 . Путь к текстовом файлу, созданному на шаге 2. Если текстовый файл и сценарий находятся в одной папке, введите имя текстового файла. В противном случае введите полное имя пути для текстового файла. 
    
- **Имя поиска контента** — имя поиска контента, который будет создан сценарием. 
    
- **Поисковый запрос** — создается и запустится поисковый запрос, который будет использоваться с поиском контента. Дополнительные сведения о поисковых запросах см. в статье "Запросы по ключевым словам и условия поиска [контента".](keyword-queries-and-search-conditions.md)


**Чтобы запустить сценарий, сделайте следующее:**
    
1. Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, `SearchEXOOD4B.ps1` . Сохраните файл в той же папке, в которой вы сохранили список пользователей на шаге 2.
    
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

2. Откройте Windows PowerShell и перейдите в папку, в которой сохранен сценарий, и список пользователей из шага 2.
    
3. Запустите сценарий; Например:
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. При запросе учетных данных введите свой адрес электронной почты и пароль, а затем нажмите кнопку **"ОК".** 
    
5. Введите следующую информацию при запросе сценария. Введите каждый фрагмент информации и нажмите **ввод.**
    
    - Имя вашего домена MySite. 
    
    - Путь к текстовом файлу, который содержит список пользователей.
    
    - Имя для поиска контента.
    
    - Поисковый запрос (оставьте этот запрос пустым, чтобы вернуть все элементы в расположениях контента).
    
    Сценарий получает URL-адреса для каждого сайта OneDrive для бизнеса, а затем создает и запускает поиск. Чтобы отобразить статистику и результаты поиска, можно запустить в PowerShell Центра безопасности и соответствия требованиям (PowerShell) **get-ComplianceSe & arch** или перейти на страницу поиска контента в Центре безопасности и соответствия требованиям &, чтобы просмотреть сведения о поиске.  
