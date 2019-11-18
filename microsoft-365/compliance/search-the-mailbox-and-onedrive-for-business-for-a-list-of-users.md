---
title: Использование поиска содержимого для поиска списка пользователей в почтовом ящике и на сайте OneDrive для бизнеса
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
search.appverid: MOE150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: Используйте поиск контента и сценарий, описанный в этой статье, для поиска группы пользователей в почтовых ящиках и на сайтах OneDrive для бизнеса.
ms.openlocfilehash: 02b89646fdb4175d30dce8840ac069f62995cbbc
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38687510"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Использование поиска содержимого для поиска списка пользователей в почтовом ящике и на сайте OneDrive для бизнеса

Центр безопасности & соответствия требованиям предоставляет ряд командлетов Windows PowerShell, позволяющих автоматизировать задачи, связанные с обнаружением электронных данных. В настоящее время создание поиска контента в центре безопасности & соответствия требованиям для поиска большого количества расположений содержимого хранитель занимает время и подготовку. Перед созданием поиска необходимо собрать URL-адрес для каждого сайта OneDrive для бизнеса, а затем добавить в поиск каждый почтовый ящик и сайт OneDrive для бизнеса. В будущих выпусках этот процесс будет проще в центре безопасности & соответствия требованиям. До этого вы можете автоматизировать этот процесс с помощью сценария, описанного в этой статье. Этот сценарий запрашивает имя домена личного сайта Организации (например, **contoso** в URL-адресе https://contoso-my.sharepoint.com), список адресов электронной почты пользователей, имя нового поиска контента и используемый запрос поиска. Сценарий получает URL-адрес OneDrive для бизнеса для каждого пользователя в списке, а затем создает и запускает поиск контента, который выполняет поиск каждого пользователя в списке в почтовом ящике и OneDrive для бизнеса, используя предоставленный вами запрос поиска. 
  
## <a name="before-you-begin"></a>Перед началом работы

- Вы должны быть участником группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & соответствия требованиям и глобальном администраторе SharePoint Online для запуска скрипта на шаге 3.
    
- Не забудьте сохранить список пользователей, созданных в действии 2, и сценарий, приведенный в шаге 3, в ту же папку. Это облегчит выполнение скрипта.
    
- Сценарий включает в себя минимальную обработку ошибок. Основная цель — быстро и легко искать в почтовом ящике и на сайте OneDrive для бизнеса каждого пользователя.
    
- Примеры сценариев, приведенные в этом разделе, не поддерживаются ни в одной из стандартных программ или услуг поддержки Майкрософт. Примеры сценариев предоставляются как есть и без каких-либо гарантий. Кроме того, корпорация Майкрософт отказывается от всех[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)мплиедных гарантий, включая, без ограничений, любые подразумеваемые гарантии пригодности для продавца или пригодности для конкретной цели. Ответственность за риск, возникающий в результате выполнения примеров сценариев и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации сценариев, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров сценариев или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Шаг 1. Установка командной консоли SharePoint Online

Первый шаг — установка командной консоли SharePoint Online. В этой процедуре не нужно использовать командную консоль, но ее необходимо установить, так как она содержит необходимые условия, необходимые для сценария, выполняемого на шаге 3. Эти условия позволяют сценарию связываться с SharePoint Online для получения URL-адресов сайтов OneDrive для бизнеса.
  
Перейдите в раздел [Настройка среды Windows PowerShell для командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) и выполните действия 1 и 2, чтобы установить командную консоль SharePoint Online.
  
## <a name="step-2-generate-a-list-of-users"></a>Шаг 2: Создание списка пользователей

Сценарий, приведенный в шаге 3, создаст поиск контента для поиска в почтовых ящиках и записях OneDrive для списка пользователей. Вы можете просто ввести адреса электронной почты в текстовом файле или выполнить команду в Windows PowerShell, чтобы получить список адресов электронной почты и сохранить их в файле (расположенном в той же папке, в которой вы сохранили сценарий на шаге 3).
  
Ниже приведена команда [PowerShell для Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=517283) , которую можно рунт, чтобы получить список адресов электронной почты для всех пользователей в Организации и сохранить его в текстовом файле с именем `Users.txt`. 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

После выполнения этой команды не забудьте открыть файл и удалить заголовок, содержащий имя свойства `PrimarySmtpAddress`. Текстовый файл должен содержать только список адресов электронной почты и ничего другое. Убедитесь, что в списке адресов электронной почты нет пустых строк.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Шаг 3: запуск скрипта для создания и запуска поиска

При выполнении скрипта на этом этапе будут предложены следующие сведения. Перед выполнением скрипта обязательно убедитесь, что эти сведения готовы к работе.
  
- **Ваши учетные данные пользователя** : сценарий будет использовать ваши учетные данные для доступа к SharePoint Online, чтобы получить URL-адреса OneDrive для бизнеса и подключиться к центру безопасности & соответствия требованиям с помощью удаленной оболочки PowerShell. 
    
- **Имя домена личного сайта** — домен личного сайта, который содержит все сайты OneDrive для бизнеса в вашей организации. Например, если URL-адрес вашего домена личного времени указан **https://contoso-my.sharepoint.com**, то при вводе `contoso` сценария для имени домена личного сайта необходимо ввести запрос. 
    
- **Путь к текстовому файлу из шага 2** : путь к текстовому файлу, созданному в шаге 2. Если текстовый файл и сценарий находятся в одной папке, введите имя текстового файла. В противном случае введите полный путь к текстовому файлу. 
    
- **Имя поиска контента** — имя поиска контента, которое будет создано сценарием. 
    
- **Поисковый запрос** — запрос поиска, который будет использоваться с поиском контента, создан и запущен. Дополнительные сведения о поисковых запросах можно узнать в статье [запросы и условия поиска контента](keyword-queries-and-search-conditions.md).


**Чтобы запустить сценарий, сделайте следующее:**
    
1. Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `SearchEXOOD4B.ps1`. Сохраните файл в ту же папку, в которой вы сохранили список пользователей, указанных в шаге 2.
    
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

2. Откройте Windows PowerShell и перейдите к папке, в которой сохранен сценарий, и список пользователей, указанных в шаге 2.
    
3. Запустите сценарий; Например:
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. При запросе учетных данных введите свой адрес электронной почты и пароль, а затем нажмите кнопку **ОК**. 
    
5. Введите следующие сведения, когда запрашивается сценарий. Введите все данные и нажмите клавишу **Ввод**.
    
    - Имя домена личного сайта. 
    
    - Путь к текстовому файлу, содержащему список пользователей.
    
    - Имя для поиска контента.
    
    - Поисковый запрос (оставьте это поле пустым, чтобы возвратить все элементы в расположениях контента).
    
    Сценарий получает URL-адреса для каждого сайта OneDrive для бизнеса, а затем создает и запускает поиск. Вы можете запустить командлет **Get-ComplianceSearch** в консоли безопасности & центра соответствия требованиям, чтобы отобразить статистику и результаты поиска, или можно перейти на страницу **поиска содержимого** в центре безопасности & соответствия для просмотра сведений о поиске. 
