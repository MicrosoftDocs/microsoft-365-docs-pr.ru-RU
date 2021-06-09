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
description: Узнайте, как создать отчет, содержащий сведения обо всех хламах, связанных с случаями, связанными с электронным открытием.
ms.openlocfilehash: 04282f6f2481d892fa16d685936efeec55feae77
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908413"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>Создание отчета об удержаниях в делах обнаружения электронных данных

Скрипт в этой статье позволяет администраторам и менеджерам по обнаружению электронных данных создавать отчет, содержащий сведения обо всех хламах, связанных с случаями проверки электронных данных в центре соответствия требованиям в Office 365 или Microsoft 365. В отчете содержатся сведения, такие как имя случая, с помощью которого связан удержание, расположения контента, размещенные на удержании, а также сведения о том, является ли удержание на основе запроса. Если имеются случаи, когда нет никаких удерживаний, сценарий создаст дополнительный отчет со списком случаев без удерживаний.

Подробные [сведения,](#more-information) включенные в отчет, см. в разделе Дополнительные сведения.

## <a name="admin-requirements-and-script-information"></a>Требования администратора и сведения о скриптах

- Чтобы создать отчет по всем случаям получения электронных сообщений в организации, необходимо быть администратором по обнаружению электронных сообщений в организации. Если вы менеджер по обнаружению электронных данных, в отчет будут включены только сведения о случаях, к которые можно получить доступ. Дополнительные сведения о разрешениях на открытие электронных данных см. в дополнительных сведениях [о назначении разрешений на открытие электронных данных.](assign-ediscovery-permissions.md)

- Сценарий в этой статье имеет минимальную обработку ошибок. Основная цель состоит в том, чтобы быстро создать отчет о личных удерживает, связанных с делами об обнаружении электронных сообщений в организации.

- Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>Шаг 1. Подключение в Центр & безопасности PowerShell

Первый шаг — подключение к PowerShell в Центре безопасности и соответствия требованиям вашей организации. Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell).

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Шаг 2. Запуск скрипта для отчета о хламах, связанных с случаями, связанными с электронным открытием

После подключения к центру & безопасности PowerShell необходимо создать и запустить сценарий, который собирает сведения о случаях, связанных с электронным открытием в организации.

1. Сохраните следующий текст в файле Windows PowerShell с помощью суффикса файлового имени .ps1; например, CaseHoldsReport.ps1.

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

2. В сеансе Windows PowerShell, открываемом в шаге 1, перейдите к папке, в которой сохранен сценарий.

3. Запустите сценарий; Например:

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   Сценарий будет подсказок для целевой папки, чтобы сохранить отчет.

4. Введите полное имя пути папки, чтобы сохранить отчет, и нажмите **кнопку Ввод**.

   > [!TIP]
   > Чтобы сохранить отчет в той же папке, в которую находится скрипт, введите период (".") при запросе целевой папки. Чтобы сохранить отчет в подмостках в папке, где расположен сценарий, просто введите имя подмостка.

   Сценарий начинает сбор сведений обо всех случаях получения электронных данных в организации. Не доступ к файлу отчета во время запуска скрипта. После завершения сценария в сеансе Windows PowerShell подтверждение. После отображения этого сообщения можно получить доступ к отчету в папке, указанной в шаге 4. Имя файла для отчета `CaseHoldsReport<DateTimeStamp>.csv` .

   Addtionally, скрипт также создает отчет со списком случаев, которые не имеют каких-либо удерживает. Имя файла для этого отчета `CaseswithNoHolds<DateTimeStamp>.csv` .

   Вот пример запуска сценария CaseHoldsReport.ps1.

   ![Вывод после запуска сценария CaseHoldsReport.ps1](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>Дополнительные сведения

В случае содержится отчет, созданный при запуске сценария в этой статье, содержит следующие сведения о каждом удержании. Как было объяснено ранее, необходимо быть администратором электронных данных, чтобы возвращать сведения для всех удерживаемой информации в вашей организации. Дополнительные сведения о случаях, которые имеется в деле, см. в примере [eDiscovery cases](./get-started-core-ediscovery.md).

- Имя удержания и имя дела об обнаружении электронной почты, связанного с удержанием.

- Активен или закрыт случай с электронным открытием.

- Включено или отключено удержание.

- Участники дела об обнаружении электронных обнаружений, с чем связан удержание. Участники дела могут просматривать или управлять случаем в зависимости от разрешений на открытие электронных данными, которые им были назначены.

- Время и дата создания дела.

- Если дело закрыто, человек, закрывавший его, и время и дату его закрытия.

- Почтовые Exchange и SharePoint сайты, которые находятся на удержании.

- Если удержание основано на запросе, синтаксис запроса.

- Время и дата создания удержания и лицо, создавшего его.

- Время и дата последнего изменения удержания и человека, который изменил его.