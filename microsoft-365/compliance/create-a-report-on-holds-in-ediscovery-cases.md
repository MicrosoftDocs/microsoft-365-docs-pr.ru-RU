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
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как создать отчет, содержащий сведения обо всех удержаниях, связанных с делами eDiscovery.
ms.openlocfilehash: 4da2b93ad9055363a5f8a7d61eff04270dfd00dc
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845871"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>Создание отчета об удержаниях в делах обнаружения электронных данных

Скрипт, представленный в этой статье, позволяет администраторам и менеджерам eDiscovery создать отчет, содержащий сведения обо всех удержаниях, связанных с делами обнаружения электронных данных в Центре соответствия требованиям в Office 365 или Microsoft 365. Отчет содержит такие сведения, как имя дела, с которым связано удержание, расположение контента, помещенное на удержание, и указано, является ли удержание запросом. При отсутствии сценариев, для которых нет удержаний, то скрипт создаст дополнительный отчет со списком случаев удержания.

В разделе ["Дополнительные](#more-information) сведения" представлено подробное описание сведений, присутствуемых в отчете.

## <a name="admin-requirements-and-script-information"></a>Требования к администрированию и сведения о сценарии

- Чтобы создать отчет обо всех делах обнаружения электронных данных в организации, вы должны быть администратором, ответственными за обнаружение электронных данных в организации. Если вы руководитель службы обнаружения электронных данных, то в отчет будет содержаться только информация о тех случаях, которые можно получить. Дополнительные сведения о разрешениях для обнаружения электронных данных см. в разделе ["Назначение разрешений на обнаружение электронных данных".](assign-ediscovery-permissions.md)

- Сценарий, ориентированный на ввод в этой статье, минимальный задействован. Основная задача — быстро создать отчет об удержаниях, связанный с делами обнаружения электронных данных в организации.

- Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>Шаг 1. Подключение к PowerShell в Центре безопасности & требованиям

Первый шаг подключение к PowerShell в Центре безопасности & требованиям вашей организации. Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Шаг 2. Запуск скрипта для сообщения об удержаниях, связанных с делами обнаружения электронных данных

После подключения к PowerShell Центра безопасности & соответствия требованиям следует создать и запустить сценарий, который собирает сведения о делах eDiscovery в вашей организации.

1. Сохраните приведенный ниже текст в файле сценария Windows PowerShell, используя суффикс .ps1 в имени файла. Например, CaseHoldsReport.ps1.

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

2. В сеансе Windows PowerShell, который открылся на шаге 1, перейдите к папке, где сохранен сценарий.

3. Запустите сценарий. Например:

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   Скрипт запросит в конечной папке целевую папку, в который будет сохранен отчет.

4. Введите полный путь к папке, в которой должен сохраняться отчет, и нажмите клавишу **ВВОД.**

   > [!TIP]
   > Чтобы сохранить отчет в той же папке, в которой находится сценарий, введите точку (".") при запросе целевой папки. Чтобы сохранить отчет во вложенной папке в папке, в которой находится сценарий, просто введите имя вложенной папки.

   Сценарий начинает собрать сведения обо всех делах обнаружения электронных данных в организации. Не используйте файл отчета во время выполнения сценария. После выполнения скрипта в сеансе Windows PowerShell появляется подтверждение. После отображения этого сообщения вы можете получить доступ к отчету в папке, указанной на шаге 4. Имя файла для `CaseHoldsReport<DateTimeStamp>.csv` отчета.

   Кроме того, сценарий также создает отчет со списком случаев, в которых не удержания. В этом отчете используется имя `CaseswithNoHolds<DateTimeStamp>.csv` файла.

   Вот пример выполнения скрипта CaseHoldsReport.ps1.

   ![Выходные данные после CaseHoldsReport.ps1 сценария](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>Дополнительные сведения

Отчет об удержаниях дел, созданный при запуске скрипта, приведенного в этой статье, содержит следующие сведения о каждом удержании. Как объяснялось ранее, вам необходимо быть администратором, ответственным за обнаружение электронных данных, чтобы получить сведения обо всех удержаниях в вашей организации. Дополнительные сведения об удержаниях дел см. в [делах обнаружения электронных данных.](ediscovery-cases.md)

- Имя удержания и имя дела обнаружения электронных данных, с которым связано удержание.

- Указывает, активна или закрыта ли дело eDiscovery.

- Указывает, включено ли удержание.

- Члены дела eDiscovery, с которым связано удержание. Участники дела могут просматривать дело и управлять им в зависимости от имеющиеся разрешений службы обнаружения электронных данных.

- Время и дата создания дела.

- Если закрыть регистр, лицо, закрывавший его, а также время и дата закрытия.

- Почтовые ящики Exchange и расположения сайтов SharePoint на удержании.

- Если удержание поддерживает запрос, то синтаксис запроса.

- Время и дата создания удержания и лица, создавшего удержание.

- Время и дата последнего изменения удержания, а также лица, изменившего его.
