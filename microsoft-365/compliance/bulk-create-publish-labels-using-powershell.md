---
title: Создание и публикация меток хранения с помощью PowerShell
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
ms.date: ''
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как с помощью PowerShell создавать и публиковать метки хранения из командной строки независимо от центра соответствия требованиям Microsoft 365.
ms.openlocfilehash: 6dc008784d46567bfa76b5bbcf9b3fa6ee8155a1
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924967"
---
# <a name="create-and-publish-retention-labels-by-using-powershell"></a><span data-ttu-id="78520-103">Создание и публикация меток хранения с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="78520-103">Create and publish retention labels by using PowerShell</span></span>

><span data-ttu-id="78520-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="78520-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="78520-105">Если вы решили использовать [метки хранения](retention.md), которые помогут хранить и удалять документы и электронные письма в Microsoft 365, то, вероятно, вы понимаете, что это решение влечет за собой создание и публикацию множества (возможно, сотен) меток хранения.</span><span class="sxs-lookup"><span data-stu-id="78520-105">After you've decided to use [retention labels](retention.md) to help you keep or delete documents and emails in Microsoft 365, you might have realized that you have many and possibly hundreds of retention labels to create and publish.</span></span> <span data-ttu-id="78520-106">Для массового создания меток хранения рекомендуется использовать [план хранения](file-plan-manager.md) в центре соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78520-106">The recommended method to create retention labels at scale is by using [file plan](file-plan-manager.md) from the Microsoft 365 compliance center.</span></span> <span data-ttu-id="78520-107">Однако можно использовать и [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="78520-107">However, you can also use [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels).</span></span>
  
<span data-ttu-id="78520-108">Используйте сведения, файлы и примеры шаблонов, а также сценарий из этой статьи при массовом создании меток хранения и их публикации в политиках меток хранения.</span><span class="sxs-lookup"><span data-stu-id="78520-108">Use the information, template files and examples, and script in this article to help you bulk-create retention labels and publish them in retention label policies.</span></span> <span data-ttu-id="78520-109">После этого метки хранения могут [применяться администраторами и пользователями](create-apply-retention-labels.md#how-to-apply-published-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="78520-109">Then, the retention labels can be [applied by administrators and users](create-apply-retention-labels.md#how-to-apply-published-retention-labels).</span></span>

<span data-ttu-id="78520-110">Представленные инструкции не поддерживают метки хранения с автоматическим применением</span><span class="sxs-lookup"><span data-stu-id="78520-110">The supplied instructions don't support retention labels that are auto-applied.</span></span>

<span data-ttu-id="78520-111">Обзор</span><span class="sxs-lookup"><span data-stu-id="78520-111">Overview:</span></span> 

1. <span data-ttu-id="78520-112">Создайте в Excel список меток хранения и список соответствующих политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="78520-112">In Excel, create a list of your retention labels and a list of their retention label policies.</span></span>

2. <span data-ttu-id="78520-113">Создайте метки хранения и политики меток хранения, указанные в этих списках, с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78520-113">Use PowerShell to create the retention labels and retention label policies in those lists.</span></span>
  
## <a name="disclaimer"></a><span data-ttu-id="78520-114">Заявление об отказе от ответственности</span><span class="sxs-lookup"><span data-stu-id="78520-114">Disclaimer</span></span>

<span data-ttu-id="78520-p103">Примеры сценариев, представленные в этой статье, не поддерживаются ни одной из стандартных программ поддержки или служб Майкрософт. Примеры сценариев предоставляются КАК ЕСТЬ, без каких-либо гарантий. Кроме того, корпорация Майкрософт не дает никаких обязательств в отношении подразумеваемых гарантий, включая, но не ограничиваясь перечисленным, гарантий товарного качества и пригодности для использования по назначению. Вы несете полную ответственность за риск, возникающий в связи с выполнением примеров сценариев и использованием документации. Корпорация Майкрософт, ее авторы и все, кто принимает участие в создании, подготовке и публикации сценарии, не несут ответственности за любой ущерб (включая, но не ограничиваясь перечисленным, ущерб в связи с потерей коммерческой прибыли, нарушением работы бизнеса, утратой коммерческих сведений или других денежных убытков), вызванный использованием или невозможностью использовать примеров сценариев или документацию, даже если корпорации Майкрософт было известно о возможности такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="78520-p103">The sample scripts provided in this article aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-create-a-csv-file-for-the-retention-labels"></a><span data-ttu-id="78520-120">Шаг 1. Создание CSV-файла для меток хранения</span><span class="sxs-lookup"><span data-stu-id="78520-120">Step 1: Create a .csv file for the retention labels</span></span>

1. <span data-ttu-id="78520-121">Скопируйте приведенный ниже пример CSV-файла с шаблоном и примерами четырех различных меток хранения и вставьте их в Excel.</span><span class="sxs-lookup"><span data-stu-id="78520-121">Copy the following sample .csv file for a template and example entries for four different retention labels, and paste them into Excel.</span></span> 

2. <span data-ttu-id="78520-122">Преобразуйте текст в столбцы: вкладка **Данные** \> **Текст по столбцам** \> **Разделители** \> **Запятая** \> **Общие**.</span><span class="sxs-lookup"><span data-stu-id="78520-122">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="78520-123">Замените примеры вашими собственными метками и параметрами хранения.</span><span class="sxs-lookup"><span data-stu-id="78520-123">Replace the examples with entries for your own retention labels and settings.</span></span> <span data-ttu-id="78520-124">Дополнительные сведения о значениях параметров см. в разделе [New-ComplianceTag](/powershell/module/exchange/new-compliancetag).</span><span class="sxs-lookup"><span data-stu-id="78520-124">For more information about the parameter values, see [New-ComplianceTag](/powershell/module/exchange/new-compliancetag).</span></span>

3. <span data-ttu-id="78520-125">Сохраните лист как CSV-файл в таком месте, где его будет легко найти.</span><span class="sxs-lookup"><span data-stu-id="78520-125">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="78520-126">Например: C:\>Scripts\Labels.csv</span><span class="sxs-lookup"><span data-stu-id="78520-126">For example: C:\>Scripts\Labels.csv</span></span>

  
<span data-ttu-id="78520-127">Примечания.</span><span class="sxs-lookup"><span data-stu-id="78520-127">Notes:</span></span>

- <span data-ttu-id="78520-p106">Если CSV-файл содержит метку хранения с уже существующим именем, скрипт пропускает создание этой метки хранения. Повторяющиеся метки хранения не создаются.</span><span class="sxs-lookup"><span data-stu-id="78520-p106">If the .csv file contains a retention label with the same name as one that already exists, the script skips creating that retention label. No duplicate retention labels are created.</span></span>
    
- <span data-ttu-id="78520-130">Не изменяйте и не переименовывайте заголовки столбцов в CSV-файле примера, иначе сценарий не будет работать.</span><span class="sxs-lookup"><span data-stu-id="78520-130">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-labels"></a><span data-ttu-id="78520-131">Пример CSV-файла для меток хранения</span><span class="sxs-lookup"><span data-stu-id="78520-131">Sample .csv file for retention labels</span></span>

```
Name (Required),Comment (Optional),IsRecordLabel (Required),RetentionAction (Optional),RetentionDuration (Optional),RetentionType (Optional),ReviewerEmail (Optional)
LabelName_t_1,Record - keep and delete - 2 years,$true,KeepAndDelete,730,CreationAgeInDays,
LabelName_t_2,Keep and delete tag - 7 years,$false,KeepAndDelete,2555,ModificationAgeInDays,
LabelName_t_3,5 year delete,$false,Delete,1825,TaggedAgeInDays,
LabelName_t_4,Record label tag - financial,$true,Keep,730,CreationAgeInDays,
```

## <a name="step-2-create-a-csv-file-for-the-retention-label-policies"></a><span data-ttu-id="78520-132">Шаг 2. Создание CSV-файла для политик меток хранения</span><span class="sxs-lookup"><span data-stu-id="78520-132">Step 2: Create a .csv file for the retention label policies</span></span>

1. <span data-ttu-id="78520-133">Скопируйте приведенный ниже пример CSV-файла с шаблоном и примерами трех различных политик меток хранения и вставьте их в Excel.</span><span class="sxs-lookup"><span data-stu-id="78520-133">Copy the following sample .csv file for a template and example entries for three different retention label policies, and paste them into Excel.</span></span> 

2. <span data-ttu-id="78520-134">Преобразуйте текст в столбцы: вкладка **Данные** \> **Текст по столбцам** \> **Разделители** \> **Запятая** \> **Общие**.</span><span class="sxs-lookup"><span data-stu-id="78520-134">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="78520-135">Замените примеры вашими собственными политиками меток хранения и их параметров.</span><span class="sxs-lookup"><span data-stu-id="78520-135">Replace the examples with entries for your own retention label policies and their settings.</span></span> <span data-ttu-id="78520-136">Дополнительные сведения о значениях параметров этого командлета см. в разделе [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy).</span><span class="sxs-lookup"><span data-stu-id="78520-136">For more information about the parameter values for this cmdlet, see [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy).</span></span>

3. <span data-ttu-id="78520-137">Сохраните лист как CSV-файл в таком месте, где его будет легко найти.</span><span class="sxs-lookup"><span data-stu-id="78520-137">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="78520-138">Пример: `<path>Policies.csv`</span><span class="sxs-lookup"><span data-stu-id="78520-138">For example: `<path>Policies.csv`</span></span>


<span data-ttu-id="78520-139">Примечания.</span><span class="sxs-lookup"><span data-stu-id="78520-139">Notes:</span></span>
  
- <span data-ttu-id="78520-p109">Если CSV-файл содержит политику меток хранения с уже существующим именем, скрипт пропускает создание этой политики меток хранения. Повторяющиеся политики меток хранения не создаются.</span><span class="sxs-lookup"><span data-stu-id="78520-p109">If the .csv file contains a retention label policy with the same name as one that already exists, the script skips creating that retention label policy. No duplicate retention label policies are created.</span></span>
    
- <span data-ttu-id="78520-142">Не изменяйте и не переименовывайте заголовки столбцов в CSV-файле примера, иначе сценарий не будет работать.</span><span class="sxs-lookup"><span data-stu-id="78520-142">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-policies"></a><span data-ttu-id="78520-143">Пример CSV-файла для политик хранения</span><span class="sxs-lookup"><span data-stu-id="78520-143">Sample .csv file for retention policies</span></span>

```
Policy Name (Required),PublishComplianceTag (Required),Comment (Optional),Enabled (Required),ExchangeLocation (Optional),ExchangeLocationException (Optional),ModernGroupLocation (Optional),ModernGroupLocationException (Optional),OneDriveLocation (Optional),OneDriveLocationException (Optional),PublicFolderLocation (Optional),SharePointLocation (Optional),SharePointLocationException (Optional),SkypeLocation (Optional),SkypeLocationException (Optional)
Publishing Policy Red1,"LabelName_t_1, LabelName_t_2, LabelName_t_3, LabelName_t_4",N/A,$true,All,,All,,All,,,All,,,
Publishing Policy Orange1,"LabelName_t_1, LabelName_t_2",N/A,$true,All,,,,,,,,,,
Publishing Policy Yellow1,"LabelName_t_3, LabelName_t_4",N/A,$false,All,,,,,,,,,,
```

## <a name="step-3-create-the-powershell-script"></a><span data-ttu-id="78520-144">Шаг 3. Создание скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="78520-144">Step 3: Create the PowerShell script</span></span>

1. <span data-ttu-id="78520-145">Скопируйте и вставьте следующий сценарий PowerShell в Блокнот.</span><span class="sxs-lookup"><span data-stu-id="78520-145">Copy and paste the following PowerShell script into Notepad.</span></span>

2. <span data-ttu-id="78520-146">Сохраните файл с расширением **.ps1** в таком месте, где его будет легко найти.</span><span class="sxs-lookup"><span data-stu-id="78520-146">Save the file by using a file name extension of **.ps1** in a location that's easy to find.</span></span> <span data-ttu-id="78520-147">Пример: `<path>CreateRetentionSchedule.ps1`</span><span class="sxs-lookup"><span data-stu-id="78520-147">For example: `<path>CreateRetentionSchedule.ps1`</span></span>

<span data-ttu-id="78520-148">Примечания.</span><span class="sxs-lookup"><span data-stu-id="78520-148">Notes:</span></span>

- <span data-ttu-id="78520-149">Сценарий предложит указать два исходных файла, которые вы создали на предыдущих двух шагах.</span><span class="sxs-lookup"><span data-stu-id="78520-149">The script prompts you to provide the two source files that you created in the previous two steps:</span></span>
    - <span data-ttu-id="78520-150">Если вы не укажете исходный файл для создания меток хранения, сценарий перейдет к созданию политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="78520-150">If you don't specify the source file to create the retention labels, the script moves on to create the retention label policies.</span></span> 
    - <span data-ttu-id="78520-151">Если вы не укажете исходный файл для создания политик меток хранения, сценарий создаст только метки хранения.</span><span class="sxs-lookup"><span data-stu-id="78520-151">If you don't specify the source file to create the retention label policies, the script creates the retention labels only.</span></span>

- <span data-ttu-id="78520-152">Сценарий создает файл журнала, в который записываются все выполненные сценарием действия и их результат.</span><span class="sxs-lookup"><span data-stu-id="78520-152">The script generates a log file that records each action it took and whether the action succeeded or failed.</span></span> <span data-ttu-id="78520-153">Инструкции по поиску файла журнала см. в описании последнего шага.</span><span class="sxs-lookup"><span data-stu-id="78520-153">See the final step for instructions how to locate this log file.</span></span>

### <a name="powershell-script"></a><span data-ttu-id="78520-154">Скрипт PowerShell</span><span class="sxs-lookup"><span data-stu-id="78520-154">PowerShell script</span></span>

```Powershell
<#
. Steps: Import and publish retention labels
    ○ Load retention labels csv file 
    ○ Validate csv file input
    ○ Create retention labels
    ○ Create retention policies
    ○ Publish retention labels for the policies
    ○ Generate the log for retention labels and policies creation
    ○ Generate the csv result for the labels and policies created
. Syntax
    .\Publish-ComplianceTag.ps1 [-LabelListCSV <string>] [-PolicyListCSV <string>] 
. Detailed Description
    1) [-LabelListCSV <string>]
    -LabelListCSV ".\SampleInputFile_LabelList.csv"
    Load compliance tag for creation.
    2) [-PolicyListCSV <string>]
    -PolicyListCSV ".\SampleInputFile_PolicyList.csv"
    Load compliance tag for creation.
#>
param (
    [Parameter(Mandatory = $true)]
    [string]$LabelListCSV = "",
    [Parameter(Mandatory = $true)]
    [string]$PolicyListCSV = "",
    [Switch]$ResultCSV
)
# -------------------
# File operation
# -------------------
Function FileExist
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath,
        [Switch]$Warning
    )
    $inputFileExist = Test-Path $FilePath
    if (!$inputFileExist)
    {
        if ($Warning -eq $false) 
        { 
            WriteToLog -Type "Failed" -Message "[File: $FilePath] The file doesn't exist"
            throw 
        }
        else 
        { 
            WriteToLog -Type "Warning" -Message "[File: $FilePath] The file doesn't exist"
        }
    }
    else
    {
        WriteToLog -Type "Succeed" -Message "[File: $FilePath] The file is found"
    }
}
# -------------------
# Log operation
# -------------------
Function WriteToLog
{
    Param(
        # Message want to write to log file
        [Parameter(Mandatory = $true)]
        [String]$Message,
        # "Succeed" or "Faild"
        [String]$Type = "Message"
    )
    $date = Get-Date -Format 'HH:mm:ss'
    $logInfo = $date + " - [$Type] " + $Message
    $logInfo | Out-File -FilePath $logfilePath -Append
    if ($Type -eq "Succeed") { Write-Host $logInfo -ForegroundColor Green }
    elseif ($Type -eq "Failed") { Write-Host $logInfo -ForegroundColor Red }
    elseif ($Type -eq "Warning") { Write-Host $logInfo -ForegroundColor Yellow }
    elseif ($Type -eq "Start") { Write-Host $logInfo -ForegroundColor Cyan }
    else { Write-Verbose $logInfo }
}
Function Create-Log
{
    Param(
        # Log folder Root
        [Parameter(Mandatory = $true)]
        [String]$LogFolderRoot,
        # The function Log file for
        [Parameter(Mandatory = $true)]
        [String]$LogFunction
    )
    $logFolderPath = "$LogFolderRoot\logfiles"
    $folderExist = Test-Path "$logFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$logFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $logfilePath = "$logFolderPath\Log_{0}_{1}.txt" -f $LogFunction, $date
    Write-Verbose "Log file is written to: $logfilePath"
    $logfile = New-Item $logfilePath  -type file
    return $logfilePath
}
Function Create-ResultCSV
{
    Param(
        # Result folder Root
        [Parameter(Mandatory = $true)]
        [String]$ResultFolderRoot,
        # The function Result file for
        [Parameter(Mandatory = $true)]
        [String]$ResultFunction
    )
    $retFolderPath = "$ResultFolderRoot\logfiles"
    $folderExist = Test-Path "$retFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$retFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $retfilePath = "$retFolderPath\Result_{0}_{1}.csv" -f $ResultFunction, $date
    Write-Verbose "Result file is written to: $retfilePath"
    $retfile = New-Item $retfilePath  -type file
    return $retfilePath
}
# -------------------
# Prepare Log File
# -------------------
$scriptPath = '.\'
$logfilePath = Create-Log -LogFolderRoot $scriptPath -LogFunction "Publish_Compliance_Tag"
if ($ResultCSV)
{
    $tagRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Creation"
    $tagPubRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Publish"
}
# -------------------
# Invoke Powershell cmdlet
# -------------------
Function InvokePowerShellCmdlet
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$CmdLet
    )
    try
    {
        WriteToLog -Type "Start" -Message "Execute Cmdlet : '$CmdLet'" 
        return Invoke-Expression $CmdLet -ErrorAction SilentlyContinue
    }
    catch
    {
        WriteToLog -Type "Failed" "Failed to execute cmdlet!"
        WriteToLog -Type "Failed" $error[0]
        return $null
    }
}
# -------------------
# Create Compliance Tag
# -------------------
Function CreateComplianceTag
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to create Compliance Tag"
    FileExist $FilePath
    
    # TODO Validate CSV file for the Header
    try
    {
        # Import csv
        $labels = Import-Csv $FilePath
        # Retrieve existing compliance tags
        $tags = InvokePowerShellCmdlet "Get-ComplianceTag"
        foreach($lab in $labels)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $cmdlet = 'New-ComplianceTag'
            if ([String]::IsNullOrEmpty($lab.'Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $name = $lab.'Name (Required)'
                $cmdlet += " -Name '" + $name + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'Comment (Optional)'))
            {
                $para = $lab.'Comment (Optional)'
                $cmdlet += " -Comment '" + $para + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'IsRecordLabel (Required)'))
            {
                $para = $lab.'IsRecordLabel (Required)'
                $cmdlet += " -IsRecordLabel " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionAction (Optional)'))
            {
                $para = $lab.'RetentionAction (Optional)'
                $cmdlet += " -RetentionAction " + $para 
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionDuration (Optional)'))
            {
                $para = $lab.'RetentionDuration (Optional)'
                $cmdlet += " -RetentionDuration " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionType (Optional)'))
            {
                $para = $lab.'RetentionType (Optional)'
                $cmdlet += " -RetentionType " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'ReviewerEmail (Optional)'))
            {
                $emails = $lab.'ReviewerEmail (Optional)'.Split(",") | ForEach-Object { $_.Trim() }
                if (($emails -ne $null) -and ($emails.Count -ne 0))
                {
                    $eml = '@('
                    foreach($email in $emails)
                    {
                        $eml += "'{0}'," -f $email
                    }
                    $eml = $eml.Substring(0, $eml.Length - 1) + ')'
                    
                    $cmdlet += " -ReviewerEmail " + $eml
                }
            }
            # If the tag already exists, skip for creation
            if (($tags -eq $null) -or ($tags | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create compliance tag
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
                
                $ret = InvokePowerShellCmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The tag '$name' already exists! Skip for creation!"
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Create Retention Compliance Policy
# -------------------
Function CreateRetentionCompliancePolicy
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to Create Retention Policy"
    FileExist $FilePath
    try
    {
        # Import csv
        $list = Import-Csv -Path $FilePath
        # Retrieve existing retention compliance policy
        $policies = InvokePowerShellCmdlet "Get-RetentionCompliancePolicy"
        foreach($rp in $list)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $rpid = [String]::Empty;
            $cmdlet = 'New-RetentionCompliancePolicy'
            if ([String]::IsNullOrEmpty($rp.'Policy Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
               $name = $rp.'Policy Name (Required)'
               $cmdlet += " -Name '" + $name + "'"
            }
            if ([String]::IsNullOrEmpty($rp.'Enabled (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $enabled = $rp.'Enabled (Required)'
                $cmdlet += " -Enabled " + $enabled
            }
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocation (Optional)'))
            {
                $para = $rp.'ExchangeLocation (Optional)'
                $cmdlet += " -ExchangeLocation " + $para
            }
         
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocationException (Optional)'))
            {
                $para = $rp.'ExchangeLocationException (Optional)'
                $cmdlet += " -ExchangeLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocation (Optional)'))
            {
                $para = $rp.'ModernGroupLocation (Optional)'
                $cmdlet += " -ModernGroupLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocationException (Optional)'))
            {
                $para = $rp.'ModernGroupLocationException (Optional)'
                $cmdlet += " -ModernGroupLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocation (Optional)'))
            {
                $para = $rp.'OneDriveLocation (Optional)'
                $cmdlet += " -OneDriveLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocationException (Optional)'))
            {
                $para = $rp.'OneDriveLocationException (Optional)'
                $cmdlet += " -OneDriveLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocation (Optional)'))
            {
                $para = $rp.'SharePointLocation (Optional)'
                $cmdlet += " -SharePointLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocationException (Optional)'))
            {
                $para = $rp.'SharePointLocationException (Optional)'
                $cmdlet += " -SharePointLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'PublicFolderLocation (Optional)'))
            {
                $para = $rp.'PublicFolderLocation (Optional)'
                $cmdlet += " -PublicFolderLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocation (Optional)'))
            {
                $para = $rp.'SkypeLocation (Optional)'
                $cmdlet += " -SkypeLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocationException (Optional)'))
            {
                $para = $rp.'SkypeLocationException (Optional)'
                $cmdlet += " -SkypeLocationException " + $para
            }
            # If the policy already exists, skip for creation
            if (($policies -eq $null) -or ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create retention compliance policy
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
            
                $ret = invokepowershellcmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
                $rpid = $ret.Guid
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The policy '$name' already exists! Skip for creation!"
                $rpid = ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }).Guid
            }
                        
            # Retrieve tag name for publishing
            $ts = $rp.'PublishComplianceTag (Required)'
            $tagList = $ts.Split(",") | ForEach-Object { $_.Trim() }
            
            WriteToLog -Type "Message" -Message "Publish Tags : '$ts'" 
            
            PublishComplianceTag -PolicyGuid $rpid -TagName $tagList
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Publish Compliance Tag
# -------------------
Function PublishComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$PolicyGuid,
        [Parameter(Mandatory = $true)]
        [String[]]$TagNames
    )
    
    WriteToLog -Type "Start" "Start to Publish Compliance Tag"
    try
    {
        # Retrieve existing rule related to the given compliance policy
        $rule = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $PolicyGuid)
        $tagGuids = New-Object System.Collections.ArrayList
        
        foreach ($tn in $TagNames)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag {0}" -f $tn)
            $tagGuids.Add($t.Guid) | Out-Null
        }
        if ($rule -ne $null)
        {
            foreach ($r in $rule)
            {
                if ([String]::IsNullOrEmpty($r.PublishComplianceTag))
                {
                    continue;
                }
                else
                {
                    $tl = $r.PublishComplianceTag.Split(",")
                    if ($tagGuids.Contains([GUID]$tl[0]))
                    {
                        $tagGuids.Remove([GUID]$tl[0]);
                    }
                }
            }
        }
        
        foreach($t in $tagGuids)
        {
            # Publish compliance tag
            $cmdlet = "New-RetentionComplianceRule -Policy {0} -PublishComplianceTag {1}" -f $PolicyGuid, $t
            $ret = InvokePowerShellCmdlet $cmdlet
            
            if ($ret -eq $null)
            {
                WriteToLog -Type "Failed" $error[0]
                break;
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Export All Labels Created in The Process
# -------------------
Function ExportCreatedComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$LabelFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Compliance Tag Created"
    try
    {
        # Import input csv
        $labels = Import-Csv $LabelFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn Name,([string])
        $col2 = New-Object system.Data.DataColumn Comment,([string])
        $col3 = New-Object system.Data.DataColumn IsRecordLabel,([string])
        $col4 = New-Object system.Data.DataColumn RetentionAction,([string])
        $col5 = New-Object system.Data.DataColumn RetentionDuration,([string])
        $col6 = New-Object system.Data.DataColumn RetentionType,([string])
        $col7 = New-Object system.Data.DataColumn ReviewerEmail,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        foreach($lab in $labels)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag '{0}' " -f $lab.'Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Name'] = $t.Name
            $row['Comment'] = $t.Comment
            $row['IsRecordLabel'] = $t.IsRecordLabel
            $row['RetentionAction'] = $t.RetentionAction
            $row['RetentionDuration'] = $t.RetentionDuration
            $row['RetentionType'] = $t.RetentionType
            $row['ReviewerEmail'] = $t.ReviewerEmail
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# -------------------
# Export All Published Labels and Policies in The Process
# -------------------
Function ExportPublishedComplianceTagAndPolicy
{
    Param(
        [Parameter(Mandatory = $true)]
        [String[]]$PolicyFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Published Compliance Tag and Policy"
    try
    {
        # Import input csv
        $policies = Import-Csv $PolicyFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn 'Policy Name',([string])
        $col2 = New-Object system.Data.DataColumn PublishComplianceTag,([string])
        $col3 = New-Object system.Data.DataColumn Comment,([string])
        $col4 = New-Object system.Data.DataColumn Enabled,([string])
        $col5 = New-Object system.Data.DataColumn ExchangeLocation,([string])
        $col6 = New-Object system.Data.DataColumn ExchangeLocationException,([string])
        $col7 = New-Object system.Data.DataColumn ModernGroupLocation,([string])
        $col8 = New-Object system.Data.DataColumn ModernGroupLocationException,([string])
        $col9 = New-Object system.Data.DataColumn OneDriveLocation,([string])
        $col10 = New-Object system.Data.DataColumn OneDriveLocationException,([string])
        $col11 = New-Object system.Data.DataColumn PublicFolderLocation,([string])
        $col12 = New-Object system.Data.DataColumn SharePointLocation,([string])
        $col13 = New-Object system.Data.DataColumn SharePointLocationException,([string])
        $col14 = New-Object system.Data.DataColumn SkypeLocation,([string])
        $col15 = New-Object system.Data.DataColumn SkypeLocationException,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        $table.columns.add($col8)
        $table.columns.add($col9)
        $table.columns.add($col10)
        $table.columns.add($col11)
        $table.columns.add($col12)
        $table.columns.add($col13)
        $table.columns.add($col14)
        $table.columns.add($col15)
        foreach($policy in $policies)
        {
            $t = InvokePowerShellCmdlet ("Get-RetentionCompliancePolicy '{0}' -DistributionDetail" -f $policy.'Policy Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Policy Name'] = $t.Name
            
            $rules = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $t.Guid)
            $tagList = [String]::Empty
            foreach($rule in $rules)
            {
                if ([String]::IsNullOrEmpty($rule.PublishComplianceTag) -eq $False)
                {
                    $tName = $rule.PublishComplianceTag.Split(',')[1]
                    $tagList = [String]::Concat($tagList, $tName, ",")
                }
            }
            if (![String]::IsNullOrEmpty($tagList))
            {
                $tagList = $tagList.Substring(0, $tagList.LastIndexOf(','))
            }
            $row['PublishComplianceTag'] = $tagList
            $row['Comment'] = $t.Comment
            $row['Enabled'] = $t.Enabled
            $row['ExchangeLocation'] = $t.ExchangeLocation
            $row['ExchangeLocationException'] = $t.ExchangeLocationException
            $row['ModernGroupLocation'] = $t.ModernGroupLocation
            $row['ModernGroupLocationException'] = $t.ModernGroupLocationException
            $row['OneDriveLocation'] = $t.OneDriveLocation
            $row['OneDriveLocationException'] = $t.OneDriveLocationException
            $row['PublicFolderLocation'] = $t.PublicFolderLocation
            $row['SharePointLocation'] = $t.SharePointLocation
            $row['SharePointLocationException'] = $t.SharePointLocationException
            $row['SkypeLocation'] = $t.SkypeLocation
            $row['SkypeLocationException'] = $t.SkypeLocationException
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagPubRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# Create compliance tag
CreateComplianceTag -FilePath $LabelListCSV
# Create retention policy and publish compliance tag with the policy
CreateRetentionCompliancePolicy -FilePath $PolicyListCSV
# Export to result csv
if ($ResultCSV)
{
    ExportCreatedComplianceTag -LabelFilePath $LabelListCSV
    ExportPublishedComplianceTagAndPolicy -PolicyFilePath $PolicyListCSV 
}

```

## <a name="step-4-run-the-powershell-script"></a><span data-ttu-id="78520-155">Шаг 4. Запуск скрипта PowerShell</span><span class="sxs-lookup"><span data-stu-id="78520-155">Step 4: Run the PowerShell script</span></span>

<span data-ttu-id="78520-156">Сначала [выполните подключение к PowerShell Центра безопасности и соответствия требованиям](/powershell/exchange/connect-to-scc-powershell)</span><span class="sxs-lookup"><span data-stu-id="78520-156">First, [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="78520-157">Затем запустите сценарий, создающий и публикующий метки хранения.</span><span class="sxs-lookup"><span data-stu-id="78520-157">Then, run the script that creates and publishes the retention labels:</span></span>
  
1. <span data-ttu-id="78520-158">В сеансе PowerShell Центра безопасности и соответствия требованиям введите путь, затем символы `.\` и имя файла сценария, после чего нажмите клавишу ВВОД, чтобы запустить сценарий.</span><span class="sxs-lookup"><span data-stu-id="78520-158">In your Security & Compliance Center PowerShell session, enter the path, followed by the characters `.\` and the file name of the script, and then press ENTER to run the script.</span></span> <span data-ttu-id="78520-159">Например:</span><span class="sxs-lookup"><span data-stu-id="78520-159">For example:</span></span>
    
    ```powershell
    <path>.\CreateRetentionSchedule.ps1
    ```

2. <span data-ttu-id="78520-160">Скрипт предлагает указать расположения ранее созданных CSV-файлов.</span><span class="sxs-lookup"><span data-stu-id="78520-160">The script prompts you for the locations of the .csv files that you created in the previous steps.</span></span> <span data-ttu-id="78520-161">Введите путь, затем символы `.\` и имя CSV-файла, после чего нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="78520-161">Enter the path, followed by the characters `.\` and file name of the .csv file, and then press ENTER.</span></span> <span data-ttu-id="78520-162">Например, для первого запроса:</span><span class="sxs-lookup"><span data-stu-id="78520-162">For example, for the first prompt:</span></span>
    
    ```powershell
    <path>.\Labels.csv
    ```

## <a name="step-5-view-the-log-file-with-the-results"></a><span data-ttu-id="78520-163">Шаг 5. Просмотр файла журнала с результатами</span><span class="sxs-lookup"><span data-stu-id="78520-163">Step 5: View the log file with the results</span></span>

<span data-ttu-id="78520-164">Используйте созданный сценарием файл журнала для проверки результатов и выявления сбоев, которые необходимо устранить.</span><span class="sxs-lookup"><span data-stu-id="78520-164">Use the log file that the script created to check the results and identify any failures that need resolving.</span></span>

<span data-ttu-id="78520-165">Файл журнала можно найти в указанной ниже папке (обратите внимание, что цифры в имени файла могут быть другими).</span><span class="sxs-lookup"><span data-stu-id="78520-165">You can find the log file at the following location, although the digits in the example file name vary.</span></span>
  
```
<path>.\Log_Publish_Compliance_Tag_01112018_151239.txt
```