---
title: Использование скрипта для добавления пользователей в удержание в случае core eDiscovery
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
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Узнайте, как запустить скрипт для добавления почтовых ящиков & сайтов OneDrive для бизнеса в новый удержание, связанное с делом об обнаружении электронных данных в центре соответствия требованиям Microsoft 365.
ms.openlocfilehash: d6e6ff1ca053fd8c729054490e78ef42dc64e829
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909919"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a>Использование скрипта для добавления пользователей в удержание в случае core eDiscovery

Центр & обеспечения соответствия требованиям PowerShell предоставляет cmdlets, которые позволяет автоматизировать трудоемкие задачи, связанные с созданием и управлением делами по обнаружению электронных данных. В настоящее время использование дела об обнаружении основных электронных данных в Центре & безопасности для размещения большого количества местоположений контента хранителя для удержания занимает время и подготовка. Например, перед созданием удержания необходимо собрать URL-адрес для каждого сайта OneDrive для бизнеса, который необходимо разместить на удержании. Затем для каждого пользователя, который необходимо разместить на удержании, необходимо добавить в удержание почтовый ящик и сайт OneDrive для бизнеса. Чтобы автоматизировать этот процесс, можно использовать сценарий в этой статье.
  
Скрипт запрашивает имя домена "Мой сайт" организации (например, в URL-адресе, имя существующего дела об обнаружении электронных данных, имя нового удержания, связанного с делом, список адресов электронной почты пользователей, которые необходимо поместить на удержание, а также запрос на поиск, который необходимо использовать, если вы хотите создать удержание на основе `contoso` https://contoso-my.sharepoint.com) запросов. Затем скрипт получает URL-адрес сайта OneDrive для бизнеса для каждого пользователя в списке, создает новое удержание, а затем добавляет почтовый ящик и сайт OneDrive для бизнеса для каждого пользователя в списке в удержание. Скрипт также создает файлы журнала, содержащие сведения о новом удержании.
  
Для этого необходимо сделать следующие действия.
  
[Шаг 1. Установка командной консоли SharePoint Online](#step-1-install-the-sharepoint-online-management-shell)
  
[Шаг 2. Создание списка пользователей](#step-2-generate-a-list-of-users)
  
[Шаг 3. Запустите скрипт, чтобы создать удержание и добавить пользователей](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a>Перед добавлением пользователей в удержание

- Чтобы запустить сценарий в шаге 3, необходимо быть членом группы ролей диспетчера электронных данных в Центре & безопасности и администратором SharePoint Online. Дополнительные сведения см. в дополнительных сведениях о назначении разрешений на открытие электронных данных в Центре безопасности [Office 365 & соответствия](assign-ediscovery-permissions.md)требованиям.

- В удержание, связанном с делом об обнаружении электронных данных в Центре соответствия требованиям безопасности, можно добавить не более 10 & 00 почтовых ящиков и 100 сайтов. Если предположить, что каждый пользователь, который необходимо разместить на удержании, имеет сайт OneDrive для бизнеса, можно добавить не более 100 пользователей в удержание с помощью сценария в этой статье.

- Не забудьте сохранить список пользователей, которые вы создаете в шаге 2, и скрипт в шаге 3 в той же папке. Это облегчит запуск сценария.

- Скрипт добавляет список пользователей в новое удержание, связанное с существующим случаем. Убедитесь, что случай, с помощью который необходимо связать удержание, создается перед запуском сценария.

- Сценарий в этой статье поддерживает современную проверку подлинности при подключении к центру & безопасности PowerShell и SharePoint Online Management Shell. Вы можете использовать сценарий как есть, если вы microsoft 365 или организация GCC Microsoft 365. Если вы — организация Office 365 в Германии, организация Microsoft 365 GCC High или организация Дод Microsoft 365, для успешного ее запуска вам придется изменить сценарий. В частности, необходимо изменить строку и использовать параметры `Connect-IPPSSession` *ConnectionUri* и *AzureADAuthorizationEndpointUri* (а также соответствующие значения для типа организации) для подключения к Центру & соответствия требованиям PowerShell. Дополнительные сведения см. в примере [Connect to Security & PowerShell](/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa)Центра соответствия требованиям.

- Скрипт автоматически отключается от центра & powerShell и SharePoint Online Management Shell.

- Сценарий включает минимальную обработку ошибок. Его основная цель состоит в том, чтобы быстро и легко разместить почтовый ящик и сайт OneDrive для бизнеса каждого пользователя на удержание.

- Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>Шаг 1. Установка командной консоли SharePoint Online

Первый шаг — установка оболочки управления SharePoint Online, если она еще не установлена на локальном компьютере. Вы не должны использовать оболочку в этой процедуре, но ее необходимо установить, так как она содержит предварительные требования, необходимые сценарию, который вы запустите в шаге 3. Эти условия позволяют скрипту взаимодействовать с SharePoint Online для получения URL-адресов сайтов OneDrive для бизнеса.
  
Перейдите к установке оболочки управления [SharePoint Online Windows PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) и выполните шаг 1 и шаг 2 для установки оболочки управления SharePoint Online на локальном компьютере.

## <a name="step-2-generate-a-list-of-users"></a>Шаг 2. Создание списка пользователей

Скрипт в шаге 3 создаст удержание, связанное с делом об обнаружении электронных данных, и добавит почтовые ящики и сайты OneDrive для бизнеса списка пользователей в удержание. Вы можете просто ввести адреса электронной почты в текстовом файле или запустить команду в Windows PowerShell, чтобы получить список адресов электронной почты и сохранить их в файл (расположенный в той же папке, в которую вы сохраните сценарий в шаге 3).
  
Вот команда PowerShell (которую вы используете с помощью удаленной powerShell, подключенной к организации Exchange Online), чтобы получить список адресов электронной почты для всех пользователей в организации и сохранить его в текстовом файле с именем HoldUsers.txt.
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

После запуска этой команды откройте текстовый файл и удалите заготку с именем  `PrimarySmtpAddress` свойства. Затем удалите все адреса электронной почты, за исключением тех, которые необходимо добавить в удержание, которое будет создаваться в шаге 3. Убедитесь, что до или после списка адресов электронной почты не существует пустых строк.
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>Шаг 3. Запустите скрипт, чтобы создать удержание и добавить пользователей

При запуске скрипта на этом этапе будет предложена следующая информация. Убедитесь, что эти сведения будут готовы перед запуском сценария.
  
- **Учетные данные пользователей:** Скрипт будет использовать учетные данные для подключения к Центру & безопасности с PowerShell. Он также будет использовать эти учетные данные для доступа к SharePoint Online для получения URL-адресов OneDrive для бизнеса для списка пользователей.

- **Имя домена SharePoint:** Скрипт подсказит ввести это имя, чтобы подключиться к центру администрирования SharePoint. Кроме того, в организации используется доменное имя URL-адресов OneDrive. Например, если URL-адрес для центра администрирования и URL-адрес OneDrive — это, то вы введите его, когда скрипт подсылает вам `https://contoso-admin.sharepoint.com` `https://contoso-my.sharepoint.com` `contoso` доменное имя.

- **Имя дела:** Имя существующего дела. Сценарий создаст новый удержание, связанное с этим случаем.

- **Имя удержания:** Имя удержания скрипт будет создавать и связывать с указанным случаем.

- **Поиск запроса для удержания на основе запроса:** Можно создать удержание на основе запроса, чтобы приодержится только контент, отвечающий указанным критериям поиска. Чтобы разместить все содержимое на удержании, нажмите **кнопку Ввод,** когда вам будет предложен запрос на поиск.

- **Включение удержания или нет:** После создания скрипта можно включить удержание или создать удержание без его включения. Если сценарий не включит удержание, его можно включить позже в Центре & безопасности или при выполнении следующих команд PowerShell:

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **Имя текстового файла** со списком пользователей — имя текстового файла из шага 2, содержаного список пользователей, добавляемого в удержание. Если этот файл расположен в той же папке, что и сценарий, просто введите имя файла (например, HoldUsers.txt). Если текстовый файл находится в другой папке, введите полное имя пути файла.

После сбора сведений, которые будет предложено сценарием, последний шаг состоит в запуске скрипта для создания нового удержания и добавления пользователей в него.
  
1. Сохраните следующий текст в Windows PowerShell скрипта с помощью суффикса имени файла `.ps1` . Например, `AddUsersToHold.ps1`.

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

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
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
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
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. На локальном компьютере откройте Windows PowerShell и перейдите в папку, в которой сохранен сценарий.

3. Запустите сценарий; Например:

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. Введите сведения, которые вам подсказывует скрипт.

   Сценарий подключается к центру & безопасности PowerShell, а затем создает новое удержание в деле об обнаружении электронных данных и добавляет почтовые ящики и OneDrive для бизнеса для пользователей в списке. Вы можете перейти к делу на странице **eDiscovery** в Центре & безопасности, чтобы просмотреть новое удержание.

После завершения работы скрипта он создает следующие файлы журналов и сохраняет их в папке, где находится сценарий.
  
- **LocationsOnHold.txt:** Содержит список почтовых ящиков и сайтов OneDrive для бизнеса, которые сценарий успешно поместил на удержание.

- **LocationsNotOnHold.txt:** Содержит список почтовых ящиков и сайтов OneDrive для бизнеса, которые сценарий не удерживал. Если у пользователя есть почтовый ящик, но не сайт OneDrive для бизнеса, он будет включен в список сайтов OneDrive для бизнеса, которые не были помещены в удержание.

- **GetCaseHoldPolicy.txt:** Содержит вывод **комлета Get-CaseHoldPolicy** для нового удержания, который сценарий запустил после создания нового удержания. Возвращаемая этим комлетом информация включает список пользователей, чьи почтовые ящики и сайты OneDrive для бизнеса были помещены на удержание и включено ли удержание или отключено. 

- **GetCaseHoldRule.txt:** Содержит вывод **комлета Get-CaseHoldRule** для нового удержания, который сценарий запустил после создания нового удержания. Сведения, возвращаемые этим комлетом, включают поисковый запрос, если сценарий использовался для создания удержания на основе запроса.