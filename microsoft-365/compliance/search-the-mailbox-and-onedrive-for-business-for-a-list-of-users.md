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
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>Использование поиска содержимого для поиска списка пользователей в почтовом ящике и на сайте OneDrive для бизнеса

Центр & безопасности предоставляет ряд Windows PowerShell, которые позволяет автоматизировать задачи, связанные с электронным открытием, отнимающие много времени. В настоящее время создание поиска контента в Центре & безопасности для поиска большого количества местоположений контента хранителя требует времени и подготовки. Перед созданием поиска необходимо собрать URL-адрес для каждого OneDrive для бизнеса, а затем добавить в поиск каждый почтовый ящик и OneDrive для бизнеса сайт. В будущих выпусках это будет проще сделать в Центре & безопасности. До этого момента можно использовать сценарий в этой статье для автоматизации этого процесса. В этом скрипте вы можете найти имя домена MySite организации (например, **contoso** в URL-адресе), список адресов электронной почты пользователей, имя нового поиска контента и запрос на `https://contoso-my.sharepoint.com` поиск. Сценарий получает URL OneDrive для бизнеса для каждого пользователя в списке, а затем создает и запускает поиск контента, который ищет почтовый ящик и OneDrive для бизнеса для каждого пользователя в списке, используя поисковый запрос, который вы предоставляете.
  
## <a name="permissions-and-script-information"></a>Сведения о разрешениях и сценариях

- Чтобы запустить сценарий в шаге 3, необходимо быть членом группы ролей диспетчера электронных данных в Центре & безопасности и глобальным администратором SharePoint Online.

- Не забудьте сохранить список пользователей, которые вы создаете в шаге 2, и скрипт в шаге 3 в той же папке. Это облегчит запуск сценария.

- Сценарий включает минимальную обработку ошибок. Его основная цель — быстро и легко искать почтовый ящик и OneDrive для бизнеса сайта каждого пользователя.

- Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Шаг 1. Установка командной консоли SharePoint Online

Первым шагом является установка SharePoint Online Management Shell. Вы не должны использовать оболочку в этой процедуре, но ее необходимо установить, так как она содержит предварительные требования, необходимые сценарию, который вы запустите в шаге 3. Эти условия позволяют скрипту взаимодействовать с SharePoint Online для получения URL-адресов для OneDrive для бизнеса сайтов.
  
Перейдите к установке SharePoint [сетевой](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) Windows PowerShell и выполните шаг 1 и шаг 2 для установки SharePoint online Management Shell.
  
## <a name="step-2-generate-a-list-of-users"></a>Шаг 2. Создание списка пользователей

Сценарий в шаге 3 создаст поиск контента для поиска почтовых ящиков и OneDrive учетных записей для списка пользователей. Вы можете просто ввести адреса электронной почты в текстовом файле или запустить команду в Windows PowerShell, чтобы получить список адресов электронной почты и сохранить их в файле (расположен в той же папке, в которую вы сохраните сценарий в шаге 3).
  
Вот команда [Exchange Online PowerShell,](/powershell/exchange/connect-to-exchange-online-powershell) в которую можно запустить, чтобы получить список адресов электронной почты для всех пользователей в организации и сохранить его в текстовом файле с именем `Users.txt` . 
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

После запуска этой команды обязательно откройте файл и удалите заготку с именем  `PrimarySmtpAddress` свойства. В текстовом файле должен быть только список адресов электронной почты и ничего другого. Убедитесь, что до или после списка адресов электронной почты не существует пустых строк.
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>Шаг 3. Запустите сценарий для создания и запуска поиска

При запуске скрипта на этом этапе будет предложена следующая информация. Убедитесь, что эти сведения будут готовы перед запуском сценария.
  
- Учетные данные пользователей **—** скрипт будет использовать учетные данные для доступа SharePoint Online для получения URL OneDrive для бизнеса и подключения к Центру соответствия требованиям безопасности & с помощью удаленной powerShell. 
    
- **Имя домена MySite** . Домен MySite — это домен, содержащий все OneDrive для бизнеса в вашей организации. Например, если URL-адрес для домена MySite есть, вы введите, когда сценарий подсказит вам имя **https://contoso-my.sharepoint.com**  `contoso` домена MySite. 
    
- **Имя текста из шага 2** — имя пути текстового файла, созданного в шаге 2. Если текстовый файл и скрипт находятся в одной папке, введите имя текстового файла. В противном случае введите полное имя пути для текстового файла. 
    
- **Имя поиска контента** — имя поиска контента, который будет создан по сценарию. 
    
- **Поисковый запрос** . Создается и запустится поисковый запрос, который будет использоваться с помощью поиска контента. Дополнительные сведения о поисковых запросах см. в статье [Keyword queries and search conditions for Content Search.](keyword-queries-and-search-conditions.md)


**Чтобы запустить сценарий, сделайте следующее:**
    
1. Сохраните следующий текст в Windows PowerShell скрипта с помощью суффикса .ps1; например, `SearchEXOOD4B.ps1` . Сохраните файл в той же папке, в которой сохранен список пользователей в шаге 2.
    
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

2. Откройте Windows PowerShell и перейдите в папку, в которой сохранен сценарий и список пользователей из шага 2.
    
3. Запустите сценарий; Например:
    
    ```powershell
    .\SearchEXOOD4B.ps1
    ```

4. При запросе учетных данных введите адрес электронной почты и пароль, а затем нажмите **кнопку ОК**. 
    
5. Ввод следующих сведений по запросу скрипта. Введите каждый элемент информации и нажмите кнопку **Ввод**.
    
    - Имя домена MySite. 
    
    - Имя пути текстового файла, который содержит список пользователей.
    
    - Имя поиска контента.
    
    - Запрос поиска (оставьте этот пробел, чтобы вернуть все элементы в расположениях контента).
    
    Скрипт получает URL-адреса для OneDrive для бизнеса сайта, а затем создает и запускает поиск. Для отображения статистики и результатов поиска можно запустить в Центре безопасности & PowerShell cmdlet **Get-ComplianceSearch,** а можно перейти на страницу поиска контента в Центре соответствия требованиям & безопасности, чтобы просмотреть сведения о поиске. 