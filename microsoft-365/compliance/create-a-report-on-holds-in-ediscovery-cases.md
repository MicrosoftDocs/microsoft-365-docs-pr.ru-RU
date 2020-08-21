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
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a><span data-ttu-id="4b0ea-103">Создание отчета об удержаниях в делах обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="4b0ea-103">Create a report on holds in eDiscovery cases</span></span>

<span data-ttu-id="4b0ea-104">Скрипт, представленный в этой статье, позволяет администраторам и менеджерам eDiscovery создать отчет, содержащий сведения обо всех удержаниях, связанных с делами обнаружения электронных данных в Центре соответствия требованиям в Office 365 или Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="4b0ea-105">Отчет содержит такие сведения, как имя дела, с которым связано удержание, расположение контента, помещенное на удержание, и указано, является ли удержание запросом.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="4b0ea-106">При отсутствии сценариев, для которых нет удержаний, то скрипт создаст дополнительный отчет со списком случаев удержания.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="4b0ea-107">В разделе ["Дополнительные](#more-information) сведения" представлено подробное описание сведений, присутствуемых в отчете.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>

## <a name="admin-requirements-and-script-information"></a><span data-ttu-id="4b0ea-108">Требования к администрированию и сведения о сценарии</span><span class="sxs-lookup"><span data-stu-id="4b0ea-108">Admin requirements and script information</span></span>

- <span data-ttu-id="4b0ea-109">Чтобы создать отчет обо всех делах обнаружения электронных данных в организации, вы должны быть администратором, ответственными за обнаружение электронных данных в организации.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="4b0ea-110">Если вы руководитель службы обнаружения электронных данных, то в отчет будет содержаться только информация о тех случаях, которые можно получить.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="4b0ea-111">Дополнительные сведения о разрешениях для обнаружения электронных данных см. в разделе ["Назначение разрешений на обнаружение электронных данных".](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="4b0ea-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="4b0ea-112">Сценарий, ориентированный на ввод в этой статье, минимальный задействован.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="4b0ea-113">Основная задача — быстро создать отчет об удержаниях, связанный с делами обнаружения электронных данных в организации.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>

- <span data-ttu-id="4b0ea-p104">Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="4b0ea-119">Шаг 1. Подключение к PowerShell в Центре безопасности & требованиям</span><span class="sxs-lookup"><span data-stu-id="4b0ea-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="4b0ea-120">Первый шаг подключение к PowerShell в Центре безопасности & требованиям вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-120">The first step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="4b0ea-121">Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="4b0ea-121">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="4b0ea-122">Шаг 2. Запуск скрипта для сообщения об удержаниях, связанных с делами обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="4b0ea-122">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="4b0ea-123">После подключения к PowerShell Центра безопасности & соответствия требованиям следует создать и запустить сценарий, который собирает сведения о делах eDiscovery в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-123">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span>

1. <span data-ttu-id="4b0ea-124">Сохраните приведенный ниже текст в файле сценария Windows PowerShell, используя суффикс .ps1 в имени файла. Например, CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-124">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span>

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

2. <span data-ttu-id="4b0ea-125">В сеансе Windows PowerShell, который открылся на шаге 1, перейдите к папке, где сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-125">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="4b0ea-126">Запустите сценарий. Например:</span><span class="sxs-lookup"><span data-stu-id="4b0ea-126">Run the script; for example:</span></span>

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   <span data-ttu-id="4b0ea-127">Скрипт запросит в конечной папке целевую папку, в который будет сохранен отчет.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-127">The script will prompt for a target folder to save the report to.</span></span>

4. <span data-ttu-id="4b0ea-128">Введите полный путь к папке, в которой должен сохраняться отчет, и нажмите клавишу **ВВОД.**</span><span class="sxs-lookup"><span data-stu-id="4b0ea-128">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>

   > [!TIP]
   > <span data-ttu-id="4b0ea-129">Чтобы сохранить отчет в той же папке, в которой находится сценарий, введите точку (".") при запросе целевой папки.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-129">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="4b0ea-130">Чтобы сохранить отчет во вложенной папке в папке, в которой находится сценарий, просто введите имя вложенной папки.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-130">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span>

   <span data-ttu-id="4b0ea-131">Сценарий начинает собрать сведения обо всех делах обнаружения электронных данных в организации.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-131">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="4b0ea-132">Не используйте файл отчета во время выполнения сценария.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-132">Don't access the report file while the script is running.</span></span> <span data-ttu-id="4b0ea-133">После выполнения скрипта в сеансе Windows PowerShell появляется подтверждение.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-133">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="4b0ea-134">После отображения этого сообщения вы можете получить доступ к отчету в папке, указанной на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-134">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="4b0ea-135">Имя файла для `CaseHoldsReport<DateTimeStamp>.csv` отчета.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-135">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="4b0ea-136">Кроме того, сценарий также создает отчет со списком случаев, в которых не удержания.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-136">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="4b0ea-137">В этом отчете используется имя `CaseswithNoHolds<DateTimeStamp>.csv` файла.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-137">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="4b0ea-138">Вот пример выполнения скрипта CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-138">Here's an example of running the CaseHoldsReport.ps1 script.</span></span>

   ![Выходные данные после CaseHoldsReport.ps1 сценария](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a><span data-ttu-id="4b0ea-140">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4b0ea-140">More information</span></span>

<span data-ttu-id="4b0ea-141">Отчет об удержаниях дел, созданный при запуске скрипта, приведенного в этой статье, содержит следующие сведения о каждом удержании.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-141">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="4b0ea-142">Как объяснялось ранее, вам необходимо быть администратором, ответственным за обнаружение электронных данных, чтобы получить сведения обо всех удержаниях в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-142">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="4b0ea-143">Дополнительные сведения об удержаниях дел см. в [делах обнаружения электронных данных.](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="4b0ea-143">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>

- <span data-ttu-id="4b0ea-144">Имя удержания и имя дела обнаружения электронных данных, с которым связано удержание.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-144">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>

- <span data-ttu-id="4b0ea-145">Указывает, активна или закрыта ли дело eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-145">Whether or not the eDiscovery case is active or closed.</span></span>

- <span data-ttu-id="4b0ea-146">Указывает, включено ли удержание.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-146">Whether or not the hold is enabled or disabled.</span></span>

- <span data-ttu-id="4b0ea-147">Члены дела eDiscovery, с которым связано удержание.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-147">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="4b0ea-148">Участники дела могут просматривать дело и управлять им в зависимости от имеющиеся разрешений службы обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-148">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>

- <span data-ttu-id="4b0ea-149">Время и дата создания дела.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-149">The time and date the case was created.</span></span>

- <span data-ttu-id="4b0ea-150">Если закрыть регистр, лицо, закрывавший его, а также время и дата закрытия.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-150">If a case is closed, the person who closed it and the time and date it was closed.</span></span>

- <span data-ttu-id="4b0ea-151">Почтовые ящики Exchange и расположения сайтов SharePoint на удержании.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-151">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>

- <span data-ttu-id="4b0ea-152">Если удержание поддерживает запрос, то синтаксис запроса.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-152">If the hold is query-based, the query syntax.</span></span>

- <span data-ttu-id="4b0ea-153">Время и дата создания удержания и лица, создавшего удержание.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-153">The time and date the hold was created and the person who created it.</span></span>

- <span data-ttu-id="4b0ea-154">Время и дата последнего изменения удержания, а также лица, изменившего его.</span><span class="sxs-lookup"><span data-stu-id="4b0ea-154">The time and date the hold was last changed and the person who changed it.</span></span>
