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
description: Используйте сценарий, приведенный в этой статье, для создания отчета, который содержит сведения обо всех удержаниях, связанных с вариантами обнаружения электронных данных в центре соответствия требованиям в Office 365 или Microsoft 365.
ms.openlocfilehash: 4a4d9c4195a201482228226ddd781260bb19499c
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208381"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a><span data-ttu-id="496e0-103">Создание отчета об удержаниях в делах обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="496e0-103">Create a report on holds in eDiscovery cases</span></span>
  
<span data-ttu-id="496e0-104">Сценарий, описанный в этой статье, позволяет администраторам обнаружения электронных данных и диспетчерам eDiscovery создавать отчеты, содержащие сведения обо всех удержаниях, связанных с вариантами обнаружения электронных данных в центре соответствия требованиям в Office 365 или Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="496e0-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="496e0-105">Отчет содержит такие сведения, как имя случая, с которым связана удержание, расположения содержимого, помещаемые в удержание, а также хранение на основе запросов.</span><span class="sxs-lookup"><span data-stu-id="496e0-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="496e0-106">Если существуют случаи, в которых нет удержаний, скрипт создаст дополнительный отчет со списком вариантов без удержания.</span><span class="sxs-lookup"><span data-stu-id="496e0-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="496e0-107">Подробное описание сведений, включенных в отчет, представлено в разделе [Дополнительные сведения](#more-information) .</span><span class="sxs-lookup"><span data-stu-id="496e0-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="496e0-108">Подготовка</span><span class="sxs-lookup"><span data-stu-id="496e0-108">Before you begin</span></span>

- <span data-ttu-id="496e0-109">Чтобы создать отчет по всем случаям обнаружения электронных данных в Организации, необходимо быть администратором обнаружения электронных данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="496e0-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="496e0-110">Если вы являетесь диспетчером обнаружения электронных данных, отчет будет содержать только сведения о случаях, к которым вы можете получить доступ.</span><span class="sxs-lookup"><span data-stu-id="496e0-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="496e0-111">Дополнительные сведения о разрешениях обнаружения электронных данных приведены в разделе [Назначение разрешений обнаружения электронных](assign-ediscovery-permissions.md)данных.</span><span class="sxs-lookup"><span data-stu-id="496e0-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="496e0-112">Сценарий в этой статье имеет минимальную обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="496e0-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="496e0-113">Основной целью является быстрое создание отчета о удержаниях, связанных с вариантами обнаружения электронных данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="496e0-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="496e0-p104">Примеры скриптов, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры скриптов предоставляются КАК ЕСТЬ и без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, в том числе гарантий товарного качества и пригодности для использования по назначению. Ответственность за риск, возникающий в результате выполнения примеров скриптов и использования документации, полностью возлагается на вас. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации скриптов, не несут ответственности за какой-либо ущерб (в том числе потерю прибыли предприятия, приостановку его деятельности, потерю бизнес-данных и другой денежный ущерб), вызванный использованием или неспособностью использования примеров скриптов или документации, даже если корпорации Майкрософт было известно о возможности такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="496e0-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="496e0-119">Шаг 1: подключение к PowerShell центра безопасности & соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="496e0-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="496e0-120">Первый шаг — подключение к PowerShell центра безопасности & соответствия требованиям для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="496e0-120">The first step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="496e0-121">Пошаговые инструкции см. в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="496e0-121">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="496e0-122">Если ваша учетная запись Microsoft 365 использует многофакторную проверку подлинности (MFA) или федеративную проверку подлинности, вы не сможете использовать приведенные в предыдущем разделе инструкции по подключению к PowerShell в Центре безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="496e0-122">If your Microsoft 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="496e0-123">В таком случае см. инструкции в статье [Подключение к PowerShell в Центре безопасности и соответствия требованиям с использованием многофакторной проверки подлинности](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="496e0-123">Instead, see the instructions in the topic [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="496e0-124">Шаг 2: запуск скрипта для создания отчета о удержаниях, связанных с делами обнаружения электронных данных</span><span class="sxs-lookup"><span data-stu-id="496e0-124">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="496e0-125">После подключения к PowerShell центра безопасности & соответствия требованиям необходимо создать и запустить сценарий, собирающий сведения о вариантах обнаружения электронных данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="496e0-125">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="496e0-126">Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Например, Касехолдсрепорт. ps1.</span><span class="sxs-lookup"><span data-stu-id="496e0-126">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
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

2. <span data-ttu-id="496e0-127">В сеансе Windows PowerShell, открытом в действии 1, перейдите в папку, в которой сохранен сценарий.</span><span class="sxs-lookup"><span data-stu-id="496e0-127">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="496e0-128">Запуск скрипта; Например:</span><span class="sxs-lookup"><span data-stu-id="496e0-128">Run the script; for example:</span></span>

    ```powershell
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="496e0-129">Сценарий запросит целевую папку для сохранения отчета.</span><span class="sxs-lookup"><span data-stu-id="496e0-129">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="496e0-130">Введите полный путь к папке, в которую необходимо сохранить отчет, а затем нажмите клавишу **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="496e0-130">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="496e0-131">Чтобы сохранить отчет в той же папке, в которой находится скрипт, введите точку ("."), когда будет предложено указать целевую папку.</span><span class="sxs-lookup"><span data-stu-id="496e0-131">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="496e0-132">Чтобы сохранить отчет в папке, в которой расположен сценарий, просто введите имя вложенной папки.</span><span class="sxs-lookup"><span data-stu-id="496e0-132">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="496e0-133">Сценарий запускает сбор сведений обо всех случаях обнаружения электронных данных в Организации.</span><span class="sxs-lookup"><span data-stu-id="496e0-133">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="496e0-134">Не изменяйте доступ к файлу отчета во время выполнения скрипта.</span><span class="sxs-lookup"><span data-stu-id="496e0-134">Don't access the report file while the script is running.</span></span> <span data-ttu-id="496e0-135">После завершения выполнения скрипта в сеансе Windows PowerShell отображается сообщение подтверждения.</span><span class="sxs-lookup"><span data-stu-id="496e0-135">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="496e0-136">После отображения этого сообщения вы можете получить доступ к отчету в папке, указанной на шаге 4.</span><span class="sxs-lookup"><span data-stu-id="496e0-136">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="496e0-137">Для отчета используется имя файла `CaseHoldsReport<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="496e0-137">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="496e0-138">Аддтионалли сценарий также создает отчет со списком случаев, в которых нет удержаний.</span><span class="sxs-lookup"><span data-stu-id="496e0-138">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="496e0-139">Для этого отчета используется имя файла `CaseswithNoHolds<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="496e0-139">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="496e0-140">Ниже приведен пример выполнения сценария Касехолдсрепорт. ps1.</span><span class="sxs-lookup"><span data-stu-id="496e0-140">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![Выходные данные после выполнения сценария Касехолдсрепорт. ps1](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="496e0-142">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="496e0-142">More information</span></span>

<span data-ttu-id="496e0-143">Отчет о наличии содержит отчет, который создается при выполнении сценария, описанного в этой статье, содержит следующие сведения о каждом удержании.</span><span class="sxs-lookup"><span data-stu-id="496e0-143">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="496e0-144">Как было сказано ранее, администратор обнаружения электронных данных должен получить сведения для всех удержаний в Организации.</span><span class="sxs-lookup"><span data-stu-id="496e0-144">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="496e0-145">Дополнительные сведения о удержании [дел](ediscovery-cases.md)см.</span><span class="sxs-lookup"><span data-stu-id="496e0-145">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="496e0-146">Имя удержания и имя случая обнаружения электронных данных, с которым связано удержание.</span><span class="sxs-lookup"><span data-stu-id="496e0-146">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="496e0-147">Указывает, является ли ситуация обнаружения электронных данных активной или закрытой.</span><span class="sxs-lookup"><span data-stu-id="496e0-147">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="496e0-148">Указывает, включено или отключено удержание.</span><span class="sxs-lookup"><span data-stu-id="496e0-148">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="496e0-149">Элементы дела обнаружения электронных данных, с которыми связана удержание.</span><span class="sxs-lookup"><span data-stu-id="496e0-149">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="496e0-150">Элементы CASE могут просматривать обращение или управлять им, в зависимости от назначенных им разрешений на обнаружение электронных данных.</span><span class="sxs-lookup"><span data-stu-id="496e0-150">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="496e0-151">Время и Дата создания варианта.</span><span class="sxs-lookup"><span data-stu-id="496e0-151">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="496e0-152">Если обращение закрыто, человек, который его закрыл, а также дату и время закрытия.</span><span class="sxs-lookup"><span data-stu-id="496e0-152">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="496e0-153">Расположений почтовых ящиков Exchange и сайтов SharePoint, которые находятся на удержании.</span><span class="sxs-lookup"><span data-stu-id="496e0-153">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="496e0-154">Если удержание выполняется на основе запроса, синтаксис запроса.</span><span class="sxs-lookup"><span data-stu-id="496e0-154">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="496e0-155">Время и Дата создания и пользователя, создавшего удержание.</span><span class="sxs-lookup"><span data-stu-id="496e0-155">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="496e0-156">Время и Дата последнего изменения удержания и пользователя, который его изменил.</span><span class="sxs-lookup"><span data-stu-id="496e0-156">The time and date the hold was last changed and the person who changed it.</span></span>
