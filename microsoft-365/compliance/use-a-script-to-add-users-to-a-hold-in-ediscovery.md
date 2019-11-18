---
title: Использование скрипта для добавления пользователей в удержание в случае обнаружения электронных данных в центре безопасности & соответствия требованиям
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/23/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
description: Запустите сценарий, чтобы быстро добавить почтовые ящики и сайты OneDrive для бизнеса в новое удержание, связанное с вариантом обнаружения электронных данных в центре безопасности & соответствия требованиям.
ms.openlocfilehash: 7a7ea582391e2fbfcef8b63d331d64f52db4460c
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38687562"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-security--compliance-center"></a>Использование скрипта для добавления пользователей в удержание в случае обнаружения электронных данных в центре безопасности & соответствия требованиям

Центр безопасности & соответствия требованиям предоставляет множество командлетов Windows PowerShell, позволяющих автоматизировать задачи, связанные с созданием и управлением делами обнаружения электронных данных. В настоящее время с помощью средства обнаружения электронных данных в центре безопасности & соответствия требованиям для размещения большого количества расположений содержимого хранитель на удержание занимается время и подготовка. Например, перед созданием удержания необходимо собрать URL-адрес для каждого сайта OneDrive для бизнеса, который необходимо разместить на удержании. Затем для каждого пользователя, который необходимо разместить на удержании, необходимо добавить свой почтовый ящик и сайт OneDrive для бизнеса в удержание. В будущих выпусках центра безопасности & соответствия требованиям это будет проще. До этого вы можете автоматизировать этот процесс с помощью сценария, описанного в этой статье.
  
В сценарии запрашивается имя домена личного сайта Организации (например, **contoso** в URL-адресе https://contoso-my.sharepoint.com), имя существующего случая обнаружения электронных данных, имя нового удержания, связанное с обращением, список адресов электронной почты пользователей, которые необходимо включить в удержание, а также поисковый запрос, который будет использоваться, если необходимо создать удержание на основе запроса. Затем сценарий получает URL-адрес сайта OneDrive для бизнеса для каждого пользователя в списке, создает новое удержание, а затем добавляет сайт "почтовый ящик и OneDrive для бизнеса" для каждого пользователя из списка в удержание. Скрипт также создает файлы журнала, содержащие сведения о новом удержании. 
  
Выполните следующие действия:
  
[Шаг 1. Установка командной консоли SharePoint Online](#step-1-install-the-sharepoint-online-management-shell)
  
[Шаг 2: Создание списка пользователей](#step-2-generate-a-list-of-users)
  
[Шаг 3: запуск скрипта для создания удержания и добавления пользователей](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-begin"></a>Перед началом работы

- Вы должны быть участником группы ролей "Диспетчер обнаружения электронных данных" в центре безопасности & соответствия требованиям и глобальном администраторе SharePoint Online для запуска скрипта на шаге 3. Дополнительные сведения см в статье [Назначение разрешений обнаружения электронных данных в центре безопасности & соответствия требованиям Office 365](assign-ediscovery-permissions.md).
    
- Максимальное количество почтовых ящиков 1 000 и 100 можно добавить в удержание, связанное с вариантом обнаружения электронных данных в центре безопасности & соответствия требованиям. Если предполагается, что у каждого пользователя, который вы хотите разместить на удержании, есть сайт OneDrive для бизнеса, вы можете добавить в удержание не более 100 пользователей с помощью сценария, описанного в этой статье. 
    
- Не забудьте сохранить список пользователей, созданных в действии 2, и сценарий, приведенный в шаге 3, в ту же папку. Это облегчит выполнение скрипта.
    
- Сценарий добавляет список пользователей в новое удержание, связанное с существующим обращением. Перед выполнением скрипта убедитесь, что вы хотите связать удержание с учетом.
    
- Сценарий включает в себя минимальную обработку ошибок. Его основная цель — быстро и легко разместить почтовый ящик и сайт OneDrive для бизнеса для каждого пользователя на удержании.
    
- Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Шаг 1. Установка командной консоли SharePoint Online

Первый шаг — установка командной консоли SharePoint Online, если она еще не установлена на локальном компьютере. В этой процедуре не нужно использовать командную консоль, но ее необходимо установить, так как она содержит необходимые условия, необходимые для сценария, выполняемого на шаге 3. Эти условия позволяют сценарию связываться с SharePoint Online для получения URL-адресов сайтов OneDrive для бизнеса.
  
Перейдите к разделу [Настройка среды Windows PowerShell в командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) и выполните действия 1 и 2, чтобы установить командную консоль SharePoint Online на локальный компьютер. 

## <a name="step-2-generate-a-list-of-users"></a>Шаг 2: Создание списка пользователей

Сценарий в действии 3 создаст удержание, связанное с вариантом обнаружения электронных данных, а также сайты "Добавление почтовых ящиков и OneDrive для бизнеса" списка пользователей в удержание. Вы можете просто ввести адреса электронной почты в текстовом файле или выполнить команду в Windows PowerShell, чтобы получить список адресов электронной почты и сохранить их в файле (расположенном в той же папке, в которой вы сохранили сценарий на шаге 3).
  
Вот команда PowerShell (которая запускается с помощью удаленной оболочки PowerShell, подключенной к организации Exchange Online), чтобы получить список адресов электронной почты для всех пользователей в Организации и сохранить их в текстовый файл с именем Холдусерс. txt.
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

После выполнения этой команды откройте текстовый файл и удалите заголовок, содержащий имя свойства `PrimarySmtpAddress`. Затем удалите все адреса электронной почты, кроме тех, для пользователей, которые нужно добавить в удержание, созданное на шаге 3. Убедитесь, что в списке адресов электронной почты нет пустых строк.
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Шаг 3: запуск скрипта для создания удержания и добавления пользователей

При выполнении скрипта на этом этапе будут предложены следующие сведения. Перед выполнением скрипта обязательно убедитесь, что эти сведения готовы к работе.
  
- **Ваши учетные данные пользователя** — сценарий будет использовать ваши учетные данные для подключения к центру безопасности & соответствия требованиям с помощью удаленной оболочки PowerShell. Он также будет использовать эти учетные данные для доступа к SharePoint Online, чтобы получить URL-адреса OneDrive для бизнеса для списка пользователей.
    
- **Имя домена личного сайта** — домен личного сайта, который содержит все сайты OneDrive для бизнеса в вашей организации. Например, если URL-адрес вашего домена личного времени указан **https://contoso-my.sharepoint.com**, то при вводе `contoso` сценария для имени домена личного сайта необходимо ввести запрос. 
    
- **Имя варианта** — имя существующего дела. Скрипт создаст новое удержание, связанное с этим случаем.
    
- **Имя удержания** — имя удержания скрипта, который будет создан и связан с заданным регистром.
    
- **Поисковый запрос для удержаний на основе запросов** — вы можете создать удержание на основе запроса, чтобы на хранение помещается только контент, соответствующий указанным условиям поиска. Чтобы поместить все содержимое на удержании, просто нажмите клавишу **Ввод** , когда появится запрос на поисковый запрос. 
    
- Независимо от того, можно **ли включать удержание** , вы можете включить удержание после его создания или создать сценарий хранения без его включения. Если у вас нет скрипта, который включает удержание, вы можете включить его позже в центре безопасности & соответствия требованиям или выполнив следующие команды PowerShell: 
    
  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Имя текстового файла со списком пользователей** — имя текстового файла из шага 2, содержащего список пользователей, которые требуется добавить в удержание. Если этот файл находится в той же папке, что и скрипт, просто введите имя файла (например, Холдусерс. txt). Если текстовый файл находится в другой папке, введите полный путь к файлу.
    
После сбора сведений, которые будут предлагаться сценарием, последним этапом является выполнение сценария для создания нового удержания и добавления в него пользователей.
  
1. Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `AddUsersToHold.ps1`.
    
  ```powershell
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Security & Compliance Center and SharePoint Online"
  $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
  $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Couldn't create PowerShell session."
          return;
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
          Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
  ""
  $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
  ""
  # Get other required information
  do{
  $casename = Read-Host "Enter the name of the case"
  $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
  if($caseexists -ne 'True')
  {""
  write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
  ""}
  }While($caseexists -ne 'True')
  ""
  do{
  $holdName = Read-Host "Enter the name of the new hold"
  $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
  if($holdexists -eq 'True')
  {""
  write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
  ""}
  }While($holdexists -eq 'True')
  ""
  $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
  ""
  $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
  do{
  ""
  $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
  ""
  $fileexists = test-path -path $inputfile
  if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
  }while($fileexists -ne 'True')
  #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
      #in the list are unique.
    [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
    [int]$dupl = $emailAddresses.count
    [array]$emailAddresses = $emailAddresses | select-object -unique
    $dupl -= $emailAddresses.count
  #Validate email addresses so the hold creation does not run in to an error.
  if($emailaddresses.count -gt 0){
  write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
  ""
  Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
  ""
  $finallist =@()
  foreach($emailAddress in $emailAddresses)
  {
  if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
  {$finallist += $emailaddress}
  else {"Unable to find the user $emailaddress"
  [array]$excludedlist += $emailaddress}
  }
  ""
  #find user's OneDrive Site URL using email address
  Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow
  ""
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
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
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
  }
  if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
  ""
  Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
  if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
  }
  else{
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
  }
  ""
  }
  else {"No valid locations were identified. Therefore, the hold wasn't created."}
  #write log files (if needed)
  $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
  $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
  if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
  {
  Write-Host "Generating output files..." -foregroundColor Yellow
  if($ODAdded.count -gt 0){
  "OneDrive Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
  if($ODExluded.count -gt 0){ 
  "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
  "================================" | add-content .\LocationsNotOnHold.txt
  $ODExluded | add-content .\LocationsNotOnHold.txt}
  if($finallist.count -gt 0){
  " " | add-content .\LocationsOnHold.txt
  "Exchange Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
  if($excludedlist.count -gt 0){
  " "| add-content .\LocationsNotOnHold.txt
  "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
  "===============================" | add-content .\LocationsNotOnHold.txt
  $excludedlist | add-content .\LocationsNotOnHold.txt}
  $FormatEnumerationLimit=-1
  if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
  if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
  }
  }
  else {"The hold wasn't created because no valid entries were found in the text file."}
  ""
  Write-host "Script complete!" -foregroundColor Yellow
  ""
  #script end
  ```

2. На локальном компьютере откройте Windows PowerShell и перейдите к папке, в которой был сохранен сценарий.
    
3. Запуск скрипта; Например:
    
      ```powershell
    .\AddUsersToHold.ps1
      ```

4. Введите сведения, которые будут запрашиваться сценарием.
    
    Сценарий подключается к PowerShell центра безопасности & соответствия требованиям, а затем создает новое удержание в случае обнаружения электронных данных и добавляет почтовые ящики и OneDrive для бизнеса для пользователей из списка. Вы можете перейти к этому случаю на странице **Обнаружение электронных** данных в центре безопасности & соответствия требованиям для просмотра нового удержания. 
    
После завершения выполнения скрипта он создает следующие файлы журнала и сохраняет их в папке, в которой расположен сценарий.
  
- **Локатионсонхолд. txt** — содержит список почтовых ящиков и сайтов OneDrive для бизнеса, которые сценарий успешно поместил в удержание.
    
- **Локатионснотонхолд. txt** — содержит список почтовых ящиков и сайтов OneDrive для бизнеса, которые не были размещены в сценарии на удержании. Если у пользователя есть почтовый ящик, но не сайт OneDrive для бизнеса, он будет включен в список сайтов OneDrive для бизнеса, не включенных в удержание.
    
- **Жеткасехолдполици. txt** — содержит выходные данные командлета **Get – caseholdpolicy позволяет** для нового удержания, который выполнялся сценарием после создания нового удержания. Сведения, возвращаемые этим командлетом, включают список пользователей, чьи почтовые ящики и сайты OneDrive для бизнеса были размещены при удержании, а также включено или отключено удержание. 
    
- **Жеткасехолдруле. txt** — содержит выходные данные командлета **Get – caseholdrule позволяет** для нового удержания, который выполнялся сценарием после создания нового удержания. Сведения, возвращаемые этим командлетом, включают поисковый запрос, если вы использовали сценарий для создания удержания на основе запроса. 
