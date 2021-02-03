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
ms.openlocfilehash: a91a54a6c35f96b90df156eaf4bc9735c911fc11
ms.sourcegitcommit: 4f40f5be140a23bacff6fd7b85536de14fc7d499
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084709"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a>Поиск в журнале аудита с помощью сценария PowerShell

Сегодня для ИТ-администраторов нет задачи важнее, чем обеспечить в работе безопасность, соответствие требованиям и готовность к аудиту. Microsoft 365 предлагает ряд встроенных возможностей, которые помогут предприятиям контролировать безопасность, соответствие требованиям и аудиты. В частности, чтобы справиться с несоответствиями и нарушениями безопасности, вам поможет единое ведение журналов аудита. Получить журналы аудита можно следующими способами:

- [API действий управления Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

- [Средство поиска в журналах аудита](search-the-audit-log-in-security-and-compliance.md) в центре соответствия требованиям Microsoft 365

- Командлет [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) в Exchange Online PowerShell

Если вам часто приходится вызывать журналы аудита, рассмотрите решение, использующее API действий управления Office 365. Оно дает крупным предприятиям возможность масштабирования и производительность, необходимую для получения миллионов записей аудита на постоянной основе. Средство поиска в журналах аудита в центре соответствия требованиям Microsoft 365 — это отличный способ быстро отыскать записи аудита по конкретным операциям за небольшие периоды. При поиске в более широких временных рамках, особенно когда дело касается крупных организаций, средство поиска в журналах аудита может вернуть слишком много записей, что приведет к трудностям в их обработке и экспорте.

Если для расследования конкретного случая или инцидента вам нужно вручную извлечь данные аудита, особенно в обширном временном диапазоне для крупного предприятия, лучшим выбором будет командлет **Search-UnifiedAuditLog**. В этой статье описан сценарий PowerShell, использующий командлет, чтобы извлечь до 50 000 записей аудита и экспортировать их в CSV-файл, который затем можно привести в удобный формат с помощью Power Query в Excel. Сценарий, приведенный в статье, также сводит к минимуму вероятность того, что поисковый запрос большого объема записей аудита превысит время ожидания службы.

## <a name="before-you-run-the-script"></a>Перед запуском сценария

- Для того чтобы пользоваться сценарием и искать записи аудита, в вашей организации должно быть включено ведение журналов аудита. По умолчанию ведение журналов аудита включено для организаций, использующих Microsoft 365 и Office 365 корпоративный. Чтобы убедиться, что для вашей организации доступен поиск в журнале аудита, можно выполнить следующую команду в Exchange Online PowerShell:

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```
  
  Значение `True` для свойства **UnifiedAuditLogIngestionEnabled** указывает на то, что поиск в журнале аудита включен.

- Для запуска сценария вам должна быть назначена роль “Журналы аудита только для просмотра” или “Журналы аудита” в Exchange Online. Эти роли по умолчанию назначены группам ролей "Управление соответствием" и "Управление организацией" на странице Разрешения в Центре администрирования Exchange. Чтобы узнать больше, см. пункт "Требования для поиска в журнале аудита" в разделе [Поиск в журнале аудита в Центре соответствия требованиям](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).

- Выполнение сценария может занять много времени. Время выполнения зависит от диапазона дат и длины интервала, в котором сценарий ищет записи аудита. Большие диапазоны и малые интервалы увеличивают срок работы. Чтобы узнать больше о диапазонах дат и интервалах, см. таблицу на этапе 2.

- Пример сценария, приведенный в данной статье, не поддерживается ни одной из стандартных программ и служб технической поддержки Microsoft. Пример сценария приводится в виде "как есть", без каких-либо гарантий. Кроме того, корпорация Microsoft отказывается от всех подразумеваемых гарантий, включая в том числе все подразумеваемые гарантии пригодности для продажи или определенной цели. Все риски, возникающие в результате использования примера сценария и документации, берет на себя пользователь. Корпорация Microsoft, ее штатные авторы и другие лица, принимающие участие в создании, подготовке и выпуске сценария, ни при каких обстоятельствах не несут ответственности за какой-либо ущерб (в том числе ущерб, вызванный потерей доходов предприятия, остановкой его работы, потерей бизнес-данных и другими материальными потерями), вызванный использованием или невозможностью использования примера сценария и документации, даже если корпорации Microsoft известно о возможности нанесения такого ущерба.

## <a name="step-1-connect-to-exchange-online-powershell"></a>Этап 1. Подключение к Exchange Online PowerShell

Первый шаг — подключение к Exchange Online PowerShell. Подключиться можно, пройдя современную проверку подлинности или многофакторную проверку подлинности (MFA). Пошаговые инструкции см. в статье [Подключение к Exchange Online с помощью удаленной оболочки PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a>Этап 2. Изменение и запуск сценария для получения записей аудита

После подключения к Exchange Online PowerShell необходимо создать, изменить и запустить сценарий для получения данных аудита. Первые семь строк сценария поиска в журнале аудита содержат указанные ниже переменные, которые можно изменить для настройки поиска. Описание этих переменных см. в таблице на шаге 2.

1. Сохраните приведенный ниже текст в сценарии Windows PowerShell, используя суффикс .ps1 в имени файла. Например, SearchAuditLog.ps1.

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

2. Для настройки параметров поиска изменяйте переменные, приведенные в таблице ниже. Для этих переменных в сценарии используются примеры значений, но их можно изменять (если не указано иначе) в соответствии с конкретными требованиями.

   |Переменная|Пример значения|Описание|
   |---|---|---|
   |`$logFile`|"d:\temp\AuditSearchLog.txt"|Определяет имя и расположение файла журнала с информацией о ходе поиска в журнале аудита, выполняемого сценарием.|
   |`$outputFile`|"d:\temp\AuditRecords.csv"|Определяет имя и расположение CSV-файла, содержащего записи аудита, возвращаемые сценарием.|
   |`[DateTime]$start` и `[DateTime]$end`|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|Определяет диапазон дат для поиска в журнале аудита. Сценарий возвращает записи действий аудита, входящие в указанный диапазон дат. Например, чтобы вернуть действия, выполненные в январе 2021 г., можно указать дату начала `"2021-01-01"` и дату окончания `"2021-01-31"` (обязательно заключите значения в кавычки). Пример значения в сценарии возвращает записи действий, совершенных за последние 24 часа. Если в значении не указана метка времени, по умолчанию к выбранной дате применяется метка времени 24:00 (полночь).|
   |`$record`|"AzureActiveDirectory"|Определяет тип записи действий аудита (также называемых *операциями*) для поиска. Это свойство означает службу или функцию, в которой было инициировано действие. Чтобы просмотреть список типов записей, которые можно использовать для этой переменной, см. [Тип записи журнала аудита](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype). Можно использовать имя типа записи или значение перечисления. <br/><br/>**Совет.** Для возврата записей аудита всех типов используйте значение `$null` (без кавычек).|
   |`$resultSize`|5000|Определяет число результатов, возвращаемых каждый раз, когда сценарий вызывает командлет **Search-UnifiedAuditLog** (также называется *результирующим набором*). Максимальное значение, поддерживаемое командлетом, — 5000. Оставьте это значение без изменений.|
   |`$intervalMinutes`|60|Чтобы превысить ограничение в 5000 возвращаемых записей, эта переменная принимает указанный диапазон дат и разбивает его на меньшие интервалы. После этого ограничение в 5000 записей применяется не ко всему диапазону, а к каждому из меньших интервалов. Для большинства организаций должно быть достаточно значения по умолчанию, равного 5000 записей за интервал длительностью 60 минут в диапазоне дат. Но если сценарий вернул ошибку `maximum results limitation reached`, то уменьшите интервал времени (например, до 30 или даже до 15 минут) и повторно запустите сценарий.|
   ||||

   Большинство переменных, перечисленных в предыдущей таблице, соответствует параметрам командлета **Search-UnifiedAuditLog**. Дополнительные сведения об этих параметрах см. в разделе [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog).

3. На локальном компьютере откройте Windows PowerShell и перейдите в папку, где сохранен измененный сценарий.

4. Запустите сценарий в Exchange Online PowerShell. Например:

   ```powershell
   .\SearchAuditLog.ps1
   ```

После запуска сценарий отображает сообщения о ходе выполнения. После завершения сценарий создает файл журнала и CSV-файл, содержащий записи аудита, и сохраняет их в папках, определяемых переменными `$logFile` и `$outputFile`.

> [!IMPORTANT]
> При запуске сценария предусмотрено максимальное ограничение в 50 000 записей аудита. Если сценарий вернул 50 000 результатов, вероятно, что в них не включены все записи аудита для действий, входящих в этот диапазон дат. В этом случае рекомендуется разбить диапазон на дат на меньшие интервалы и повторно запустить сценарий для каждого из таких интервалов. Например, если диапазон дат длительностью 90 дней содержит 50 000 результатов, то можно повторно запустить сценарий сначала для первых 45 дней, затем для последующих 45 дней.

## <a name="step-3-format-and-view-the-audit-records"></a>Этап 3. Форматирование и просмотр записей аудита

После окончания работы сценария и экспорта записей аудита в CSV-файл этот файл можно форматировать, чтобы облегчить просмотр и анализ данных аудита. Один из способов сделать это — воспользоваться функцией преобразования Power Query JSON в Excel и разнести каждое свойство объекта JSON в столбце **AuditData** по отдельным столбцам. Пошаговые инструкции см. в пункте "Этап 2. Форматирование экспортированного журнала аудита с помощью редактора Power Query" в разделе [Экспорт, настройка и просмотр записей журнала аудита](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).
