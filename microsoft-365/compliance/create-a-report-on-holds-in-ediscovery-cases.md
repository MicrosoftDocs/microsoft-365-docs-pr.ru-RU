---
title: Создание отчета об удержаниях в делах обнаружения электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: Используйте сценарий, приведенный в этой статье, для создания отчета, который содержит сведения обо всех удержаниях, связанных с вариантами обнаружения электронных данных в центре соответствия требованиям в Office 365 или Microsoft 365.
ms.openlocfilehash: 263ac052f320a989b8843f2954a5df0933cdb2f4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632254"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>Создание отчета об удержаниях в делах обнаружения электронных данных
  
Сценарий, описанный в этой статье, позволяет администраторам обнаружения электронных данных и диспетчерам eDiscovery создавать отчеты, содержащие сведения обо всех удержаниях, связанных с вариантами обнаружения электронных данных в центре соответствия требованиям в Office 365 или Microsoft 365. Отчет содержит такие сведения, как имя случая, с которым связана удержание, расположения содержимого, помещаемые в удержание, а также хранение на основе запросов. Если существуют случаи, в которых нет удержаний, скрипт создаст дополнительный отчет со списком вариантов без удержания.

Подробное описание сведений, включенных в отчет, представлено в разделе [Дополнительные сведения](#more-information) .
  
## <a name="before-you-begin"></a>Перед началом работы

- Чтобы создать отчет по всем случаям обнаружения электронных данных в Организации, необходимо быть администратором обнаружения электронных данных в Организации. Если вы являетесь диспетчером обнаружения электронных данных, отчет будет содержать только сведения о случаях, к которым вы можете получить доступ. Дополнительные сведения о разрешениях обнаружения электронных данных приведены в разделе [Назначение разрешений обнаружения электронных](assign-ediscovery-permissions.md)данных.
    
- Сценарий в этой статье имеет минимальную обработку ошибок. Основной целью является быстрое создание отчета о удержаниях, связанных с вариантами обнаружения электронных данных в Организации.
    
- Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>Шаг 1: подключение к PowerShell центра безопасности & соответствия требованиям

Первый шаг — подключение к центру безопасности & соответствия требованиям для вашей организации.
  
1. Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `ConnectSCC.ps1`. 
    
      ```powershell
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. На локальном компьютере откройте Windows PowerShell и перейдите к папке, в которой был сохранен сценарий. 
    
3. Запуск скрипта; Например:

    ```powershell
    .\ConnectSCC.ps1
    ```

4. При запросе учетных данных введите свой адрес электронной почты и пароль, а затем нажмите кнопку **ОК**. 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Шаг 2: запуск скрипта для создания отчета о удержаниях, связанных с делами обнаружения электронных данных

После подключения к PowerShell центра безопасности & соответствия требованиям необходимо создать и запустить сценарий, собирающий сведения о вариантах обнаружения электронных данных в Организации. 
  
1. Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Например, Касехолдсрепорт. ps1. 
    
  ```powershell
#script begin
" " 
write-host "***********************************************"
write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" " 
#prompt users to specify a path to store the output files
$time=get-date
$Path = Read-Host 'Enter a file path to save the report to a .csv file'
$outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
$noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
#add case details to the csv file
function add-tocasereport{
Param([string]$casename,
[String]$casestatus,
[datetime]$casecreatedtime,
[string]$casemembers,
[datetime]$caseClosedDateTime,
[string]$caseclosedby,
[string]$holdname,
[String]$Holdenabled,
[string]$holdcreatedby,
[string]$holdlastmodifiedby,
[string]$ExchangeLocation,
[string]$sharePointlocation,
[string]$ContentMatchQuery,
[datetime]$holdcreatedtime,
[datetime]$holdchangedtime
)
$addRow = New-Object PSObject 
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
$allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
$allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii 
}
#get information on the cases and pass values to the case report function
" "
write-host "Gathering a list of cases and holds..."
" "
$edc =Get-ComplianceCase -ErrorAction SilentlyContinue
foreach($cc in $edc)
{
write-host "Working on case :" $cc.name
if($cc.status -eq 'Closed')
{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers 
}
else{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
$policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
if ($policies -ne $NULL)
{
foreach ($policy in $policies)
{
$rule=Get-CaseHoldRule -Policy $policy.name
add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
}
}
else{
write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
" "
[string]$cc.name | out-file -filepath $noholdsfilepath -append 
}
}
}

" "
Write-host "Script complete! Report files saved to this folder: '$Path'"
" "
#script end
  ```

2. В сеансе Windows PowerShell, открытом в действии 1, перейдите в папку, в которой сохранен сценарий. 
    
3. Запуск скрипта; Например:

    ```powershell
    .\CaseHoldsReport.ps1
    ```

    Сценарий запросит целевую папку для сохранения отчета. 
    
4. Введите полный путь к папке, в которую необходимо сохранить отчет, а затем нажмите клавишу **Ввод**.
    
    > [!TIP]
    > Чтобы сохранить отчет в той же папке, в которой находится скрипт, введите точку ("."), когда будет предложено указать целевую папку. Чтобы сохранить отчет в папке, в которой расположен сценарий, просто введите имя вложенной папки. 
  
    Сценарий запускает сбор сведений обо всех случаях обнаружения электронных данных в Организации. Не изменяйте доступ к файлу отчета во время выполнения скрипта. После завершения выполнения скрипта в сеансе Windows PowerShell отображается сообщение подтверждения. После отображения этого сообщения вы можете получить доступ к отчету в папке, указанной на шаге 4. Для отчета используется `CaseHoldsReport<DateTimeStamp>.csv`имя файла.

    Аддтионалли сценарий также создает отчет со списком случаев, в которых нет удержаний. Для этого отчета используется `CaseswithNoHolds<DateTimeStamp>.csv`имя файла.
    
    Ниже приведен пример выполнения сценария Касехолдсрепорт. ps1. 
    
    ![Выходные данные после выполнения сценария Касехолдсрепорт. ps1](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>Дополнительные сведения

Отчет о наличии содержит отчет, который создается при выполнении сценария, описанного в этой статье, содержит следующие сведения о каждом удержании. Как было сказано ранее, администратор обнаружения электронных данных должен получить сведения для всех удержаний в Организации. Дополнительные сведения о удержании [дел](ediscovery-cases.md)см.
  
  - Имя удержания и имя случая обнаружения электронных данных, с которым связано удержание.
    
  - Указывает, является ли ситуация обнаружения электронных данных активной или закрытой.
    
  - Указывает, включено или отключено удержание.
    
  - Элементы дела обнаружения электронных данных, с которыми связана удержание. Элементы CASE могут просматривать обращение или управлять им, в зависимости от назначенных им разрешений на обнаружение электронных данных.
    
  - Время и Дата создания варианта.
    
  - Если обращение закрыто, человек, который его закрыл, а также дату и время закрытия.
    
  - Расположений почтовых ящиков Exchange и сайтов SharePoint, которые находятся на удержании.
    
  - Если удержание выполняется на основе запроса, синтаксис запроса.
    
  - Время и Дата создания и пользователя, создавшего удержание.
    
  - Время и Дата последнего изменения удержания и пользователя, который его изменил.
