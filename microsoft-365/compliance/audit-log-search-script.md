---
title: Поиск в журнале аудита с помощью сценария PowerShell
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Чтобы выполнить поиск в журнале аудита, воспользуйтесь сценарием PowerShell, выполняющим командлет Search-UnifiedAuditLog. Этот сценарий предназначен для возврата больших наборов записей аудита (до 50 000). Сценарий экспортирует эти записи в CSV-файл, который можно просмотреть или преобразовать с помощью Power Query в Excel.
ms.openlocfilehash: d4fcf59297747d0499f6616438299ad8cbe96d7f
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094790"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a><span data-ttu-id="ad4a9-105">Поиск в журнале аудита с помощью сценария PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad4a9-105">Use a PowerShell script to search the audit log</span></span>

<span data-ttu-id="ad4a9-106">Сегодня для ИТ-администраторов нет задачи важнее, чем обеспечить в работе безопасность, соответствие требованиям и готовность к аудиту.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-106">Security, compliance, and auditing have become a top priority for IT administrators in today’s world.</span></span> <span data-ttu-id="ad4a9-107">Microsoft 365 предлагает ряд встроенных возможностей, которые помогут предприятиям контролировать безопасность, соответствие требованиям и аудиты.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-107">Microsoft 365 has several built-in capabilities to help organizations manage security, compliance, and auditing.</span></span> <span data-ttu-id="ad4a9-108">В частности, чтобы справиться с несоответствиями и нарушениями безопасности, вам поможет единое ведение журналов аудита.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-108">In particular, unified audit logging can help you investigate security incidents and compliance issues.</span></span> <span data-ttu-id="ad4a9-109">Получить журналы аудита можно следующими способами:</span><span class="sxs-lookup"><span data-stu-id="ad4a9-109">You can retrieve audit logs by using the following methods:</span></span>

- [<span data-ttu-id="ad4a9-110">API действий управления Office 365</span><span class="sxs-lookup"><span data-stu-id="ad4a9-110">The Office 365 Management Activity API</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

- <span data-ttu-id="ad4a9-111">[Средство поиска в журналах аудита](search-the-audit-log-in-security-and-compliance.md) в центре соответствия требованиям Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad4a9-111">The [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center</span></span>

- <span data-ttu-id="ad4a9-112">Командлет [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) в Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad4a9-112">The [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell</span></span>

<span data-ttu-id="ad4a9-113">Если вам часто приходится вызывать журналы аудита, рассмотрите решение, использующее API действий управления Office 365. Оно дает крупным предприятиям возможность масштабирования и производительность, необходимую для получения миллионов записей аудита на постоянной основе.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-113">If you need to retrieve audit logs on a regular basis, you should consider a solution that uses the Office 365 Management Activity API because it that can provide large organizations with the scalability and performance to retrieve millions of audit records on an ongoing basis.</span></span> <span data-ttu-id="ad4a9-114">Средство поиска в журналах аудита в центре соответствия требованиям Microsoft 365 — это отличный способ быстро отыскать записи аудита по конкретным операциям за небольшие периоды.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-114">Using the audit log search tool in Microsoft 365 compliance center is a good way to quickly find audit records for specific operations that occur in shorter time range.</span></span> <span data-ttu-id="ad4a9-115">При поиске в более широких временных рамках, особенно когда дело касается крупных организаций, средство поиска в журналах аудита может вернуть слишком много записей, что приведет к трудностям в их обработке и экспорте.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-115">Using longer time ranges in the audit log search tool, especially for large organizations, might return too many records to easily manage or export.</span></span>

<span data-ttu-id="ad4a9-116">Если для расследования конкретного случая или инцидента вам нужно вручную извлечь данные аудита, особенно в обширном временном диапазоне для крупного предприятия, лучшим выбором будет командлет **Search-UnifiedAuditLog**.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-116">When there are situations where you need to manually retrieve auditing data for a specific investigation or incident, particularly for longer date ranges in larger organizations, using the **Search-UnifiedAuditLog** cmdlet may be the best option.</span></span> <span data-ttu-id="ad4a9-117">В этой статье описан сценарий PowerShell, использующий командлет, чтобы извлечь до 50 000 записей аудита и экспортировать их в CSV-файл, который затем можно привести в удобный формат с помощью Power Query в Excel.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-117">This article includes a PowerShell script that uses the cmdlet to retrieve up to 50,000 audit records and then export them to a CSV file that you can format using Power Query in Excel to help with your review.</span></span> <span data-ttu-id="ad4a9-118">Сценарий, приведенный в статье, также сводит к минимуму вероятность того, что поисковый запрос большого объема записей аудита превысит время ожидания службы.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-118">Using the script in this article also minimizes the chance that large audit log searches will time out in the service.</span></span>

## <a name="before-you-run-the-script"></a><span data-ttu-id="ad4a9-119">Перед запуском сценария</span><span class="sxs-lookup"><span data-stu-id="ad4a9-119">Before you run the script</span></span>

- <span data-ttu-id="ad4a9-120">Для того чтобы пользоваться сценарием и искать записи аудита, в вашей организации должно быть включено ведение журналов аудита.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-120">Audit logging has to be enabled for your organization to successfully use the script to return audit records.</span></span> <span data-ttu-id="ad4a9-121">По умолчанию ведение журналов аудита включено для организаций, использующих Microsoft 365 и Office 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-121">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="ad4a9-122">Чтобы убедиться, что для вашей организации доступен поиск в журнале аудита, можно выполнить следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ad4a9-122">To verify that audit log search is turned on for your organization, you can run the following command in Exchange Online PowerShell:</span></span>

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```
  
  <span data-ttu-id="ad4a9-123">Значение `True` для свойства **UnifiedAuditLogIngestionEnabled** указывает на то, что поиск в журнале аудита включен.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-123">The value of `True` for the **UnifiedAuditLogIngestionEnabled** property indicates that audit log search is turned on.</span></span>

- <span data-ttu-id="ad4a9-124">Для запуска сценария вам должна быть назначена роль “Журналы аудита только для просмотра” или “Журналы аудита” в Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-124">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to run successfully the script.</span></span> <span data-ttu-id="ad4a9-125">Эти роли по умолчанию назначены группам ролей "Управление соответствием" и "Управление организацией" на странице Разрешения в Центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-125">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="ad4a9-126">Чтобы узнать больше, см. пункт "Требования для поиска в журнале аудита" в разделе [Поиск в журнале аудита в Центре соответствия требованиям](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span><span class="sxs-lookup"><span data-stu-id="ad4a9-126">For more information, see the "Requirements to search the audit log" section in [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span>

- <span data-ttu-id="ad4a9-127">Выполнение сценария может занять много времени.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-127">It may take a long time for the script to complete.</span></span> <span data-ttu-id="ad4a9-128">Время выполнения зависит от диапазона дат и длины интервала, в котором сценарий ищет записи аудита.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-128">How long it takes to run depends on the date range and the size of the interval that you configure the script to retrieve audit records for.</span></span> <span data-ttu-id="ad4a9-129">Большие диапазоны и малые интервалы увеличивают срок работы.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-129">Larger date ranges and smaller intervals will result in a long running time.</span></span> <span data-ttu-id="ad4a9-130">Чтобы узнать больше о диапазонах дат и интервалах, см. таблицу на этапе 2.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-130">See the table in Step 2 for more information about the date range and intervals.</span></span>

- <span data-ttu-id="ad4a9-131">Пример сценария, приведенный в данной статье, не поддерживается ни одной из стандартных программ и служб технической поддержки Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-131">The sample script provided in this article isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="ad4a9-132">Пример сценария приводится в виде "как есть", без каких-либо гарантий.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-132">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="ad4a9-133">Кроме того, корпорация Microsoft отказывается от всех подразумеваемых гарантий, включая в том числе все подразумеваемые гарантии пригодности для продажи или определенной цели.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-133">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="ad4a9-134">Все риски, возникающие в результате использования примера сценария и документации, берет на себя пользователь.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-134">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="ad4a9-135">Корпорация Microsoft, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценария, ни при каких обстоятельствах не несут ответственности за какой-либо ущерб (в том числе ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или невозможностью использования примера сценария и документации, даже если корпорации Microsoft известно о возможности нанесения такого ущерба.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-135">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="ad4a9-136">Этап 1. Подключение к Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad4a9-136">Step 1: Connect to Exchange Online PowerShell</span></span>

<span data-ttu-id="ad4a9-137">Первый шаг — подключение к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-137">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="ad4a9-138">Подключиться можно, пройдя современную проверку подлинности или многофакторную проверку подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="ad4a9-138">You can connect using modern authentication or with multi-factor authentication (MFA).</span></span> <span data-ttu-id="ad4a9-139">Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ad4a9-139">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a><span data-ttu-id="ad4a9-140">Этап 2. Изменение и запуск сценария для получения записей аудита</span><span class="sxs-lookup"><span data-stu-id="ad4a9-140">Step 2: Modify and run the script to retrieve audit records</span></span>

<span data-ttu-id="ad4a9-141">После подключения к Exchange Online PowerShell необходимо создать, изменить и запустить сценарий для получения данных аудита.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-141">After you've connected to Exchange Online PowerShell, the next step is to create, modify, and run the script to retrieve the auditing data.</span></span> <span data-ttu-id="ad4a9-142">Первые семь строк сценария поиска в журнале аудита содержат указанные ниже переменные, которые можно изменить для настройки поиска.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-142">The first seven lines in the audit log search script contain the following variables that you can modify to configure your search.</span></span> <span data-ttu-id="ad4a9-143">Описание этих переменных см. в таблице на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-143">See the table in step 2 for a description of these variables.</span></span>

1. <span data-ttu-id="ad4a9-144">Сохраните приведенный ниже текст в сценарии Windows PowerShell, используя суффикс .ps1 в имени файла.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-144">Save the following text to a Windows PowerShell script by using a filename suffix of .ps1.</span></span> <span data-ttu-id="ad4a9-145">Например, SearchAuditLog.ps1.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-145">For example, SearchAuditLog.ps1.</span></span>

```powershell
#Modify the values for the following variables to configure the audit log search.
$logFile = "d:\AuditLogSearch\AuditLogSearchLog.txt"
$outputFile = "d:\AuditLogSearch\AuditLogRecords.csv"
[DateTime]$start = [DateTime]::UtcNow.AddDays(-1)
[DateTime]$end = [DateTime]::UtcNow
$record = "AzureActiveDirectory"
$resultSize = 5000
$intervalMinutes = 60

#Start script
[DateTime]$currentStart = $start
[DateTime]$currentEnd = $start

Function Write-LogFile ([String]$Message)
{
    $final = [DateTime]::Now.ToString("s") + ":" + $Message
    $final | Out-File $logFile -Append
}

Write-LogFile "BEGIN: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize."
Write-Host "Retrieving audit records for the date range between $($start) and $($end), RecordType=$record, ResultsSize=$resultSize"

$totalCount = 0
while ($true)
{
    $currentEnd = $currentStart.AddMinutes($intervalMinutes)
    if ($currentEnd -gt $end)
    {
        $currentEnd = $end
    }

    if ($currentStart -eq $currentEnd)
    {
        break
    }

    $sessionID = [DateTime]::Now.ToString("s")
    Write-LogFile "INFO: Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
    Write-Host "Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
    $currentCount = 0

    $sw = [Diagnostics.StopWatch]::StartNew()
    do
    {
        $results = Search-UnifiedAuditLog -StartDate $currentStart -EndDate $currentEnd -RecordType $record -SessionId $sessionID -SessionCommand ReturnLargeSet -ResultSize $resultSize

        if (($results | Measure-Object).Count -ne 0)
        {
            $results | export-csv -Path $outputFile -Append -NoTypeInformation

            $currentTotal = $results[0].ResultCount
            $totalCount += $results.Count
            $currentCount += $results.Count
            Write-LogFile "INFO: Retrieved $($currentCount) audit records out of the total $($currentTotal)"

            if ($currentTotal -eq $results[$results.Count - 1].ResultIndex)
            {
                $message = "INFO: Successfully retrieved $($currentTotal) audit records for the current time range. Moving on!"
                Write-LogFile $message
                Write-Host "Successfully retrieved $($currentTotal) audit records for the current time range. Moving on to the next interval." -foregroundColor Yellow
                ""
                break
            } 
        }
    }
    while (($results | Measure-Object).Count -ne 0)

    $currentStart = $currentEnd
}

Write-LogFile "END: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize, total count: $totalCount."
Write-Host "Script complete! Finished retrieving audit records for the date range between $($start) and $($end). Total count: $totalCount" -foregroundColor Green

```

2. <span data-ttu-id="ad4a9-146">Для настройки параметров поиска изменяйте переменные, приведенные в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-146">Modify the variables listed in the following table to configure the search criteria.</span></span> <span data-ttu-id="ad4a9-147">Для этих переменных в сценарии используются примеры значений, но их можно изменять (если не указано иначе) в соответствии с конкретными требованиями.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-147">The script includes sample values for these variables, but you should change them (unless stated otherwise) to meet your specific requirements.</span></span>

   |<span data-ttu-id="ad4a9-148">Переменная</span><span class="sxs-lookup"><span data-stu-id="ad4a9-148">Variable</span></span>|<span data-ttu-id="ad4a9-149">Пример значения</span><span class="sxs-lookup"><span data-stu-id="ad4a9-149">Sample value</span></span>|<span data-ttu-id="ad4a9-150">Описание</span><span class="sxs-lookup"><span data-stu-id="ad4a9-150">Description</span></span>|
   |---|---|---|
   |`$logFile`|<span data-ttu-id="ad4a9-151">"d:\temp\AuditSearchLog.txt"</span><span class="sxs-lookup"><span data-stu-id="ad4a9-151">"d:\temp\AuditSearchLog.txt"</span></span>|<span data-ttu-id="ad4a9-152">Определяет имя и расположение файла журнала с информацией о ходе поиска в журнале аудита, выполняемого сценарием.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-152">Specifies the name and location for the log file that contains information about the progress of the audit log search performed by the script.</span></span>|
   |`$outputFile`|<span data-ttu-id="ad4a9-153">"d:\temp\AuditRecords.csv"</span><span class="sxs-lookup"><span data-stu-id="ad4a9-153">"d:\temp\AuditRecords.csv"</span></span>|<span data-ttu-id="ad4a9-154">Определяет имя и расположение CSV-файла, содержащего записи аудита, возвращаемые сценарием.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-154">Specifies the name and location of the CSV file that contains the audit records returned by the script.</span></span>|
   |<span data-ttu-id="ad4a9-155">`[DateTime]$start` и `[DateTime]$end`</span><span class="sxs-lookup"><span data-stu-id="ad4a9-155">`[DateTime]$start` and `[DateTime]$end`</span></span>|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|<span data-ttu-id="ad4a9-158">Определяет диапазон дат для поиска в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-158">Specifies the date range for the audit log search.</span></span> <span data-ttu-id="ad4a9-159">Сценарий возвращает записи действий аудита, входящие в указанный диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-159">The script will return records for audit activities that occurred within the specified date range.</span></span> <span data-ttu-id="ad4a9-160">Например, чтобы вернуть действия, выполненные в январе 2021 г., можно указать дату начала `"2021-01-01"` и дату окончания `"2021-01-31"` (обязательно заключите значения в кавычки). Пример значения в сценарии возвращает записи действий, совершенных за последние 24 часа.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-160">For example, to return activities performed in January 2021, you can use a start date of `"2021-01-01"` and an end date of `"2021-01-31"` (be sure to surround the values in double-quotation marks) The sample value in the script returns records for activities performed in the previous 24 hours.</span></span> <span data-ttu-id="ad4a9-161">Если в значении не указана метка времени, по умолчанию к выбранной дате применяется метка времени 24:00 (полночь).</span><span class="sxs-lookup"><span data-stu-id="ad4a9-161">If you don't include a timestamp in the value, the default timestamp is 12:00 AM (midnight) on the specified date.</span></span>|
   |`$record`|<span data-ttu-id="ad4a9-162">"AzureActiveDirectory"</span><span class="sxs-lookup"><span data-stu-id="ad4a9-162">"AzureActiveDirectory"</span></span>|<span data-ttu-id="ad4a9-163">Определяет тип записи действий аудита (также называемых *операциями*) для поиска.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-163">Specifies the record type of the audit activities (also called *operations*) to search for.</span></span> <span data-ttu-id="ad4a9-164">Это свойство означает службу или функцию, в которой было инициировано действие.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-164">This property indicates the service or feature that an activity was triggered in.</span></span> <span data-ttu-id="ad4a9-165">Чтобы просмотреть список типов записей, которые можно использовать для этой переменной, см. [Тип записи журнала аудита](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span><span class="sxs-lookup"><span data-stu-id="ad4a9-165">For a list of record types that you can use for this variable, see [Audit log record type](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span> <span data-ttu-id="ad4a9-166">Можно использовать имя типа записи или значение перечисления.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-166">You can use the record type name or ENUM value.</span></span> <br/><br/><span data-ttu-id="ad4a9-167">**Совет.** Для возврата записей аудита всех типов используйте значение `$null` (без кавычек).</span><span class="sxs-lookup"><span data-stu-id="ad4a9-167">**Tip:** To return audit records for all record types, use the value `$null` (without double-quotations marks).</span></span>|
   |`$resultSize`|<span data-ttu-id="ad4a9-168">5000</span><span class="sxs-lookup"><span data-stu-id="ad4a9-168">5000</span></span>|<span data-ttu-id="ad4a9-169">Определяет число результатов, возвращаемых каждый раз, когда сценарий вызывает командлет **Search-UnifiedAuditLog** (также называется *результирующим набором*).</span><span class="sxs-lookup"><span data-stu-id="ad4a9-169">Specifies the number of results returned each time the **Search-UnifiedAuditLog** cmdlet is called by the script (called a *result set*).</span></span> <span data-ttu-id="ad4a9-170">Максимальное значение, поддерживаемое командлетом, — 5000.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-170">The value of 5,000 is the maximum value supported by the cmdlet.</span></span> <span data-ttu-id="ad4a9-171">Оставьте это значение без изменений.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-171">Leave this value as-is.</span></span>|
   |`$intervalMinutes`|<span data-ttu-id="ad4a9-172">60</span><span class="sxs-lookup"><span data-stu-id="ad4a9-172">60</span></span>|<span data-ttu-id="ad4a9-173">Чтобы превысить ограничение в 5000 возвращаемых записей, эта переменная принимает указанный диапазон дат и разбивает его на меньшие интервалы.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-173">To help overcome the limit of 5000 records returned, this variable takes the data range you specified and slices it up into smaller time intervals.</span></span> <span data-ttu-id="ad4a9-174">После этого ограничение в 5000 записей применяется не ко всему диапазону, а к каждому из меньших интервалов.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-174">Now each interval, not the entire date range, is subject to the 5000 record output limit of the command.</span></span> <span data-ttu-id="ad4a9-175">Для большинства организаций должно быть достаточно значения по умолчанию, равного 5000 записей за интервал длительностью 60 минут в диапазоне дат.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-175">The default value of 5000 records per 60-minute interval within the date range should be sufficient for most organizations.</span></span> <span data-ttu-id="ad4a9-176">Но если сценарий вернул ошибку `maximum results limitation reached`, то уменьшите интервал времени (например, до 30 или даже до 15 минут) и повторно запустите сценарий.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-176">But, if the script returns an error that says, `maximum results limitation reached`, decrease the time interval (for example, to 30 minutes or even 15 minutes) and rerun the script.</span></span>|
   ||||

   <span data-ttu-id="ad4a9-177">Большинство переменных, перечисленных в предыдущей таблице, соответствует параметрам командлета **Search-UnifiedAuditLog**.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-177">Most of the variables listed in the previous table correspond to parameters for the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="ad4a9-178">Дополнительные сведения об этих параметрах см. в разделе [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog).</span><span class="sxs-lookup"><span data-stu-id="ad4a9-178">For more information about these parameters, see [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog).</span></span>

3. <span data-ttu-id="ad4a9-179">На локальном компьютере откройте Windows PowerShell и перейдите в папку, где сохранен измененный сценарий.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-179">On your local computer, open Windows PowerShell and go to the folder where you saved the modified script.</span></span>

4. <span data-ttu-id="ad4a9-180">Запустите сценарий в Exchange Online PowerShell. Например:</span><span class="sxs-lookup"><span data-stu-id="ad4a9-180">Run the script in Exchange Online PowerShell; for example:</span></span>

   ```powershell
   .\SearchAuditLog.ps1
   ```

<span data-ttu-id="ad4a9-181">После запуска сценарий отображает сообщения о ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-181">The script displays progress messages while it's running.</span></span> <span data-ttu-id="ad4a9-182">После завершения сценарий создает файл журнала и CSV-файл, содержащий записи аудита, и сохраняет их в папках, определяемых переменными `$logFile` и `$outputFile`.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-182">After the script is finished running, it creates the log file and the CSV file that contains the audit records and saves them to the folders defined by the `$logFile` and `$outputFile` variables.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad4a9-183">При запуске сценария предусмотрено максимальное ограничение в 50 000 записей аудита.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-183">There is a 50,000 limit for the maximum number of audit records returned each time you run this script.</span></span> <span data-ttu-id="ad4a9-184">Если сценарий вернул 50 000 результатов, вероятно, что в них не включены все записи аудита для действий, входящих в этот диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-184">If you run this script and it returns 50,000 results, then it's likely that audit records for activities that occurred within the date range weren't included.</span></span> <span data-ttu-id="ad4a9-185">В этом случае рекомендуется разбить диапазон на дат на меньшие интервалы и повторно запустить сценарий для каждого из таких интервалов.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-185">If this happens, we recommend that you divide the date range into smaller durations and then rerun the script for each date range.</span></span> <span data-ttu-id="ad4a9-186">Например, если диапазон дат длительностью 90 дней содержит 50 000 результатов, то можно повторно запустить сценарий сначала для первых 45 дней, затем для последующих 45 дней.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-186">For example, if a date range of 90 days returns 50,000 results then you can rerun the script twice, once for the first 45 days in the date range and then again for the next 45 days.</span></span>

## <a name="step-3-format-and-view-the-audit-records"></a><span data-ttu-id="ad4a9-187">Этап 3. Форматирование и просмотр записей аудита</span><span class="sxs-lookup"><span data-stu-id="ad4a9-187">Step 3: Format and view the audit records</span></span>

<span data-ttu-id="ad4a9-188">После окончания работы сценария и экспорта записей аудита в CSV-файл этот файл можно форматировать, чтобы облегчить просмотр и анализ данных аудита.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-188">After you've run the script and exported the audit records to a CSV file, you may want to format the CSV to make easier to review and analyze the audit records.</span></span> <span data-ttu-id="ad4a9-189">Один из способов сделать это — воспользоваться функцией преобразования Power Query JSON в Excel и разнести каждое свойство объекта JSON в столбце **AuditData** по отдельным столбцам.</span><span class="sxs-lookup"><span data-stu-id="ad4a9-189">One way to do this is to the Power Query JSON transform feature in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="ad4a9-190">Пошаговые инструкции см. в пункте "Этап 2. Форматирование экспортированного журнала аудита с помощью редактора Power Query" в разделе [Экспорт, настройка и просмотр записей журнала аудита](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span><span class="sxs-lookup"><span data-stu-id="ad4a9-190">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>
