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
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a><span data-ttu-id="41137-103">Создание отчета об удержаниях в делах обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="41137-103">Create a report on holds in eDiscovery cases</span></span>

<span data-ttu-id="41137-104">Скрипт в этой статье позволяет администраторам и менеджерам по обнаружению электронных данных создавать отчет, содержащий сведения обо всех хламах, связанных с случаями проверки электронных данных в центре соответствия требованиям в Office 365 или Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41137-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="41137-105">В отчете содержатся сведения, такие как имя случая, с помощью которого связан удержание, расположения контента, размещенные на удержании, а также сведения о том, является ли удержание на основе запроса.</span><span class="sxs-lookup"><span data-stu-id="41137-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="41137-106">Если имеются случаи, когда нет никаких удерживаний, сценарий создаст дополнительный отчет со списком случаев без удерживаний.</span><span class="sxs-lookup"><span data-stu-id="41137-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="41137-107">Подробные [сведения,](#more-information) включенные в отчет, см. в разделе Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="41137-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>

## <a name="admin-requirements-and-script-information"></a><span data-ttu-id="41137-108">Требования администратора и сведения о скриптах</span><span class="sxs-lookup"><span data-stu-id="41137-108">Admin requirements and script information</span></span>

- <span data-ttu-id="41137-109">Чтобы создать отчет по всем случаям получения электронных сообщений в организации, необходимо быть администратором по обнаружению электронных сообщений в организации.</span><span class="sxs-lookup"><span data-stu-id="41137-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="41137-110">Если вы менеджер по обнаружению электронных данных, в отчет будут включены только сведения о случаях, к которые можно получить доступ.</span><span class="sxs-lookup"><span data-stu-id="41137-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="41137-111">Дополнительные сведения о разрешениях на открытие электронных данных см. в дополнительных сведениях [о назначении разрешений на открытие электронных данных.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="41137-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="41137-112">Сценарий в этой статье имеет минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="41137-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="41137-113">Основная цель состоит в том, чтобы быстро создать отчет о личных удерживает, связанных с делами об обнаружении электронных сообщений в организации.</span><span class="sxs-lookup"><span data-stu-id="41137-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>

- <span data-ttu-id="41137-p104">Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="41137-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="41137-119">Шаг 1. Подключение в Центр & безопасности PowerShell</span><span class="sxs-lookup"><span data-stu-id="41137-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="41137-120">Первый шаг — подключение к PowerShell в Центре безопасности и соответствия требованиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="41137-120">The first step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="41137-121">Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="41137-121">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="41137-122">Шаг 2. Запуск скрипта для отчета о хламах, связанных с случаями, связанными с электронным открытием</span><span class="sxs-lookup"><span data-stu-id="41137-122">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="41137-123">После подключения к центру & безопасности PowerShell необходимо создать и запустить сценарий, который собирает сведения о случаях, связанных с электронным открытием в организации.</span><span class="sxs-lookup"><span data-stu-id="41137-123">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span>

1. <span data-ttu-id="41137-124">Сохраните следующий текст в файле Windows PowerShell с помощью суффикса файлового имени .ps1; например, CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="41137-124">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span>

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

2. <span data-ttu-id="41137-125">В сеансе Windows PowerShell, открываемом в шаге 1, перейдите к папке, в которой сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="41137-125">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="41137-126">Запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="41137-126">Run the script; for example:</span></span>

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   <span data-ttu-id="41137-127">Сценарий будет подсказок для целевой папки, чтобы сохранить отчет.</span><span class="sxs-lookup"><span data-stu-id="41137-127">The script will prompt for a target folder to save the report to.</span></span>

4. <span data-ttu-id="41137-128">Введите полное имя пути папки, чтобы сохранить отчет, и нажмите **кнопку Ввод**.</span><span class="sxs-lookup"><span data-stu-id="41137-128">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>

   > [!TIP]
   > <span data-ttu-id="41137-129">Чтобы сохранить отчет в той же папке, в которую находится скрипт, введите период (".") при запросе целевой папки.</span><span class="sxs-lookup"><span data-stu-id="41137-129">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="41137-130">Чтобы сохранить отчет в подмостках в папке, где расположен сценарий, просто введите имя подмостка.</span><span class="sxs-lookup"><span data-stu-id="41137-130">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span>

   <span data-ttu-id="41137-131">Сценарий начинает сбор сведений обо всех случаях получения электронных данных в организации.</span><span class="sxs-lookup"><span data-stu-id="41137-131">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="41137-132">Не доступ к файлу отчета во время запуска скрипта.</span><span class="sxs-lookup"><span data-stu-id="41137-132">Don't access the report file while the script is running.</span></span> <span data-ttu-id="41137-133">После завершения сценария в сеансе Windows PowerShell подтверждение.</span><span class="sxs-lookup"><span data-stu-id="41137-133">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="41137-134">После отображения этого сообщения можно получить доступ к отчету в папке, указанной в шаге 4.</span><span class="sxs-lookup"><span data-stu-id="41137-134">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="41137-135">Имя файла для отчета `CaseHoldsReport<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="41137-135">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="41137-136">Addtionally, скрипт также создает отчет со списком случаев, которые не имеют каких-либо удерживает.</span><span class="sxs-lookup"><span data-stu-id="41137-136">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="41137-137">Имя файла для этого отчета `CaseswithNoHolds<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="41137-137">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="41137-138">Вот пример запуска сценария CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="41137-138">Here's an example of running the CaseHoldsReport.ps1 script.</span></span>

   ![Вывод после запуска сценария CaseHoldsReport.ps1](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a><span data-ttu-id="41137-140">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="41137-140">More information</span></span>

<span data-ttu-id="41137-141">В случае содержится отчет, созданный при запуске сценария в этой статье, содержит следующие сведения о каждом удержании.</span><span class="sxs-lookup"><span data-stu-id="41137-141">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="41137-142">Как было объяснено ранее, необходимо быть администратором электронных данных, чтобы возвращать сведения для всех удерживаемой информации в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="41137-142">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="41137-143">Дополнительные сведения о случаях, которые имеется в деле, см. в примере [eDiscovery cases](./get-started-core-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="41137-143">For more information about case holds, see [eDiscovery cases](./get-started-core-ediscovery.md).</span></span>

- <span data-ttu-id="41137-144">Имя удержания и имя дела об обнаружении электронной почты, связанного с удержанием.</span><span class="sxs-lookup"><span data-stu-id="41137-144">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>

- <span data-ttu-id="41137-145">Активен или закрыт случай с электронным открытием.</span><span class="sxs-lookup"><span data-stu-id="41137-145">Whether or not the eDiscovery case is active or closed.</span></span>

- <span data-ttu-id="41137-146">Включено или отключено удержание.</span><span class="sxs-lookup"><span data-stu-id="41137-146">Whether or not the hold is enabled or disabled.</span></span>

- <span data-ttu-id="41137-147">Участники дела об обнаружении электронных обнаружений, с чем связан удержание.</span><span class="sxs-lookup"><span data-stu-id="41137-147">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="41137-148">Участники дела могут просматривать или управлять случаем в зависимости от разрешений на открытие электронных данными, которые им были назначены.</span><span class="sxs-lookup"><span data-stu-id="41137-148">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>

- <span data-ttu-id="41137-149">Время и дата создания дела.</span><span class="sxs-lookup"><span data-stu-id="41137-149">The time and date the case was created.</span></span>

- <span data-ttu-id="41137-150">Если дело закрыто, человек, закрывавший его, и время и дату его закрытия.</span><span class="sxs-lookup"><span data-stu-id="41137-150">If a case is closed, the person who closed it and the time and date it was closed.</span></span>

- <span data-ttu-id="41137-151">Почтовые Exchange и SharePoint сайты, которые находятся на удержании.</span><span class="sxs-lookup"><span data-stu-id="41137-151">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>

- <span data-ttu-id="41137-152">Если удержание основано на запросе, синтаксис запроса.</span><span class="sxs-lookup"><span data-stu-id="41137-152">If the hold is query-based, the query syntax.</span></span>

- <span data-ttu-id="41137-153">Время и дата создания удержания и лицо, создавшего его.</span><span class="sxs-lookup"><span data-stu-id="41137-153">The time and date the hold was created and the person who created it.</span></span>

- <span data-ttu-id="41137-154">Время и дата последнего изменения удержания и человека, который изменил его.</span><span class="sxs-lookup"><span data-stu-id="41137-154">The time and date the hold was last changed and the person who changed it.</span></span>