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
description: Сведения о том, как создать отчет, содержащий сведения обо всех случаях, связанных с делами eDiscovery.
ms.openlocfilehash: 35e432104e7c1358887eb89ae96b9bb0d1d12a0f
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546981"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>Создание отчета об удержаниях в делах обнаружения электронных данных

Сценарий в этой статье позволяет администраторам и менеджерам по обнаружению электронных данных создавать отчет, содержащий сведения обо всех случаях, связанных с делами eDiscovery, в Центре соответствия требованиям в Office 365 или Microsoft 365. Отчет содержит такие сведения, как имя дела, с которого связано удержание, расположения содержимого, помещенные на удержание, и сведения о том, основано ли удержание на запросе. Если существуют случаи, в которые не затмеются, сценарий создаст дополнительный отчет со списком дел без списания.

Подробное [описание сведений,](#more-information) включенных в отчет, см. в разделе "Дополнительные сведения".

## <a name="admin-requirements-and-script-information"></a>Требования администратора и сведения о скриптах

- Чтобы создать отчет по всем делам eDiscovery в организации, необходимо быть администратором eDiscovery в организации. Если вы менеджер по обнаружению электронных данных, отчет будет включать только сведения о доступных случаях. Дополнительные сведения о разрешениях на eDiscovery см. в поддомене "Назначение разрешений на [eDiscovery".](assign-ediscovery-permissions.md)

- Сценарий в этой статье имеет минимальную обработку ошибок. Основная цель — быстро создать отчет о личных случаях, связанных с делами eDiscovery в организации.

- Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>Шаг 1. Подключение к PowerShell Центра & безопасности

Первый шаг — подключение к PowerShell Центра & безопасности для вашей организации. Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Шаг 2. Запуск скрипта для создания отчетов об хламах, связанных с делами eDiscovery

После подключения к PowerShell Центра безопасности & соответствия требованиям необходимо создать и запустить сценарий, который собирает сведения о случаях eDiscovery в организации.

1. Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, CaseHoldsReport.ps1.

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

2. В сеансе Windows PowerShell, открываемом на шаге 1, перейдите в папку, в которой сохранен сценарий.

3. Запустите сценарий; Например:

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   Сценарий запросит у целевой папки сохранение отчета.

4. Введите полный путь к папке, чтобы сохранить отчет, и нажмите **ввод.**

   > [!TIP]
   > Чтобы сохранить отчет в той же папке, в которую находится сценарий, введите период (".") при запросе целевой папки. Чтобы сохранить отчет во вложенной папке в папке, в которой находится сценарий, просто введите имя вложенной папки.

   Сценарий начинает собирать сведения обо всех случаях eDiscovery в организации. Не получать доступ к файлу отчета во время работы сценария. После выполнения сценария в сеансе Windows PowerShell подтверждения. После отображения этого сообщения вы можете получить доступ к отчету в папке, указанной в шаге 4. Имя файла отчета : `CaseHoldsReport<DateTimeStamp>.csv` .

   Кроме того, сценарий создает отчет со списком случаев, в которые не занося каких-либо удерживаний. Имя файла для этого отчета : `CaseswithNoHolds<DateTimeStamp>.csv` .

   Вот пример запуска сценария CaseHoldsReport.ps1.

   ![Выходные данные после запуска CaseHoldsReport.ps1 сценария](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>Дополнительные сведения

Отчет об удержаниях, созданный при запуске сценария в этой статье, содержит следующие сведения о каждом удержании. Как было поясняется ранее, для возврата сведений о всех схимах в организации необходимо быть администратором eDiscovery. Дополнительные сведения о делах см. в делах [eDiscovery.](ediscovery-cases.md)

- Имя удержания и имя дела eDiscovery, с помощью которого связано удержание.

- Является ли дело eDiscovery активным или закрытым.

- Включено ли удержание или отключено.

- Члены дела eDiscovery, с чем связано удержание. Участники дела могут просматривать дела и управлять ими в зависимости от разрешений на eDiscovery, которые им были назначены.

- Время и дата создания дела.

- Если дело закрыто, лицо, закровшего его, а также время и дату закрытия.

- Почтовые ящики Exchange и расположения сайтов SharePoint, которые находятся на удержании.

- Если удержание основано на запросе, синтаксис запроса.

- Время и дата создания удержания и лицо, создавшего его.

- Время и дата последнего изменения удержания и лица, который изменил его.
