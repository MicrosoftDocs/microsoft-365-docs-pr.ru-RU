---
title: Экспорт, настройка и просмотр записей журнала аудита
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
ms.custom: seo-marvel-apr2020
description: В этой статье вы узнаете, как экспортировать, настраивать и просматривать записи журналов аудита Microsoft 365.
ms.openlocfilehash: a7f731bb30ffdddfe7898ee4051060b8e22c093e
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454670"
---
# <a name="export-configure-and-view-audit-log-records"></a><span data-ttu-id="6631f-103">Экспорт, настройка и просмотр записей журнала аудита</span><span class="sxs-lookup"><span data-stu-id="6631f-103">Export, configure, and view audit log records</span></span>

<span data-ttu-id="6631f-104">После поиска журнала аудита и загрузки результатов поиска в CSV-файл файл содержит столбец **AuditData,** содержащий дополнительные сведения о каждом событии.</span><span class="sxs-lookup"><span data-stu-id="6631f-104">After you search the audit log and download the search results to a CSV file, the file contains a column named **AuditData**, which contains additional information about each event.</span></span> <span data-ttu-id="6631f-105">Данные в этом столбце отформатированы как объект JSON, который содержит несколько свойств, настроенных как *свойства:пары* значений, разделенные запятой.</span><span class="sxs-lookup"><span data-stu-id="6631f-105">The data in this column is formatted as a JSON object, which contains multiple properties that are configured as *property:value* pairs separated by commas.</span></span> <span data-ttu-id="6631f-106">Вы можете использовать функцию преобразования JSON в редакторе запроса питания в Excel, чтобы разделить каждое свойство объекта JSON в столбце **AuditData** на несколько столбцов, чтобы каждое свойство было иметь свой столбец.</span><span class="sxs-lookup"><span data-stu-id="6631f-106">You can use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into multiple columns so that each property has its own column.</span></span> <span data-ttu-id="6631f-107">Это позволяет сортировать и фильтровать одно или несколько этих свойств, что поможет быстро найти определенные данные аудита, которые вы ищете.</span><span class="sxs-lookup"><span data-stu-id="6631f-107">This lets you sort and filter on one or more of these properties, which can help you quickly locate the specific auditing data you're looking for.</span></span>

## <a name="step-1-export-audit-log-search-results"></a><span data-ttu-id="6631f-108">Шаг 1. Экспорт результатов поиска журнала аудита</span><span class="sxs-lookup"><span data-stu-id="6631f-108">Step 1: Export audit log search results</span></span>

<span data-ttu-id="6631f-109">Первым шагом является поиск журнала аудита, а затем экспорт результатов в разделенном запятой файле значения (CSV) на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6631f-109">The first step is to search the audit log and then export the results in a comma-separated value (CSV) file to your local computer.</span></span>
  
1. <span data-ttu-id="6631f-110">Запустите [поиск журнала аудита](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) и при необходимости пересмотрите критерии поиска до тех пор, пока не будет желаемых результатов.</span><span class="sxs-lookup"><span data-stu-id="6631f-110">Run an [audit log search](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) and revise the search criteria if necessary until you have the desired results.</span></span>

2. <span data-ttu-id="6631f-111">Нажмите **кнопку Экспорт результатов** и **выберите Скачать все результаты**.</span><span class="sxs-lookup"><span data-stu-id="6631f-111">Click **Export results** and select **Download all results**.</span></span> 

   ![Щелкните Скачать все результаты](../media/ExportAuditSearchResults.png)

   <span data-ttu-id="6631f-113">Этот параметр экспортирует все записи аудита из поиска журнала аудита, который вы запустили на шаге 1, и загружает необработанные данные из журнала аудита в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="6631f-113">This option to exports all the audit records from the audit log search you ran in step 1, and downloads the raw data from the audit log to a CSV file.</span></span> 

   <span data-ttu-id="6631f-114">В нижней части окна отображается сообщение, которое позволяет открыть или сохранить CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="6631f-114">A message is displayed at the bottom of the window that prompts you to open or save the CSV file.</span></span> 

3. <span data-ttu-id="6631f-115">Нажмите **кнопку Сохранить > сохранить** как и сохранить CSV-файл на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="6631f-115">Click **Save > Save as** and save the CSV file to your local computer.</span></span> <span data-ttu-id="6631f-116">Загрузка многих результатов поиска занимает некоторое время.</span><span class="sxs-lookup"><span data-stu-id="6631f-116">It takes a while to download many search results.</span></span> <span data-ttu-id="6631f-117">Обычно это происходит при поиске всех действий или широкого диапазона дат.</span><span class="sxs-lookup"><span data-stu-id="6631f-117">This is typically the case when searching for all activities or a broad date range.</span></span> <span data-ttu-id="6631f-118">Сообщение в нижней части окна отображается при загрузке CSV-файла.</span><span class="sxs-lookup"><span data-stu-id="6631f-118">A message at the bottom of the windows is displayed when the CSV file is finished downloading.</span></span>

   ![Сообщение, отображаемая при загрузке CSV-файла](../media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > <span data-ttu-id="6631f-120">В CSV-файл можно загрузить до 50 000 записей результатов одной операции поиска по журналу аудита.</span><span class="sxs-lookup"><span data-stu-id="6631f-120">You can download a maximum of 50,000 entries to a CSV file from a single audit log search.</span></span> <span data-ttu-id="6631f-121">Если в CSV-файл загружено 50 000 записей, можно предположить, что условиям поиска соответствует более 50 000 событий.</span><span class="sxs-lookup"><span data-stu-id="6631f-121">If 50,000 entries are downloaded to the CSV file, you can probably assume there are more than 50,000 events that met the search criteria.</span></span> <span data-ttu-id="6631f-122">Чтобы экспортировать больше, чем это ограничение, попробуйте использовать диапазон дат, чтобы уменьшить количество записей журналов аудита.</span><span class="sxs-lookup"><span data-stu-id="6631f-122">To export more than this limit, try using a date range to reduce the number of audit log records.</span></span> <span data-ttu-id="6631f-123">Чтобы экспортировать больше 50 000 записей, вы можете выполнить поиск несколько раз со смежными диапазонами дат.</span><span class="sxs-lookup"><span data-stu-id="6631f-123">You might have to run multiple searches with smaller date ranges to export more than 50,000 entries.</span></span>

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a><span data-ttu-id="6631f-124">Шаг 2. Формат экспортируемой журнал аудита с помощью редактора power query</span><span class="sxs-lookup"><span data-stu-id="6631f-124">Step 2: Format the exported audit log using the Power Query Editor</span></span>

<span data-ttu-id="6631f-125">Следующим шагом является использование функции преобразования JSON в редакторе запроса питания в Excel, чтобы разделить каждое свойство объекта JSON в столбце **AuditData** на свой столбец.</span><span class="sxs-lookup"><span data-stu-id="6631f-125">The next step is to use the JSON transform feature in the Power Query Editor in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="6631f-126">Затем вы фильтруете столбцы для просмотра записей на основе значений определенных свойств.</span><span class="sxs-lookup"><span data-stu-id="6631f-126">Then you filter columns to view records based on the values of specific properties.</span></span> <span data-ttu-id="6631f-127">Это поможет вам быстро найти определенные данные аудита, которые вы ищете.</span><span class="sxs-lookup"><span data-stu-id="6631f-127">This can help you quickly locate the specific auditing data you're looking for.</span></span>

1. <span data-ttu-id="6631f-128">Откройте пустую книгу в Excel для Office 365, Excel 2019 или Excel 2016.</span><span class="sxs-lookup"><span data-stu-id="6631f-128">Open a blank workbook in Excel for Office 365, Excel 2019, or Excel 2016.</span></span>

2. <span data-ttu-id="6631f-129">На **вкладке Data** в **группе ленты Get & преобразование** данных нажмите **кнопку Текст/CSV**.</span><span class="sxs-lookup"><span data-stu-id="6631f-129">On the **Data** tab, in the **Get & Transform Data** ribbon group, click **From Text/CSV**.</span></span>

    ![На вкладке Data нажмите кнопку Text/CSV](../media/JSONTransformOpenCSVFile.png)

3. <span data-ttu-id="6631f-131">Откройте файл CSV, загруженный в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="6631f-131">Open the CSV file that you downloaded in Step 1.</span></span>

4. <span data-ttu-id="6631f-132">В отображаемом окне щелкните **Преобразование данных.**</span><span class="sxs-lookup"><span data-stu-id="6631f-132">In the window that's displayed, click **Transform Data**.</span></span>

   ![Щелкните Преобразование данных](../media/JSONOpenPowerQuery.png)

   <span data-ttu-id="6631f-134">Файл CSV открыт в **редакторе запроса.**</span><span class="sxs-lookup"><span data-stu-id="6631f-134">The CSV file is opened in the **Query Editor**.</span></span> <span data-ttu-id="6631f-135">Существует четыре столбца: **CreationDate,** **UserIds,** **Operations** и **AuditData.**</span><span class="sxs-lookup"><span data-stu-id="6631f-135">There are four columns: **CreationDate**, **UserIds**, **Operations**, and **AuditData**.</span></span> <span data-ttu-id="6631f-136">Столбец **AuditData** — это объект JSON, содержащий несколько свойств.</span><span class="sxs-lookup"><span data-stu-id="6631f-136">The **AuditData** column is a JSON object that contains multiple properties.</span></span> <span data-ttu-id="6631f-137">Следующий шаг — создание столбца для каждого свойства объекта JSON.</span><span class="sxs-lookup"><span data-stu-id="6631f-137">The next step is to create a column for each property in the JSON object.</span></span>

5. <span data-ttu-id="6631f-138">Щелкните правой кнопкой мыши название в столбце **AuditData,** щелкните **Преобразование** и нажмите **кнопку JSON**.</span><span class="sxs-lookup"><span data-stu-id="6631f-138">Right-click the title in the **AuditData** column, click **Transform**, and then click **JSON**.</span></span> 

   ![Щелкните правой кнопкой мыши столбец AuditData, щелкните Преобразование и выберите JSON](../media/JSONTransform.png)

6. <span data-ttu-id="6631f-140">В верхнем правом углу столбца **AuditData** щелкните значок расширения.</span><span class="sxs-lookup"><span data-stu-id="6631f-140">In the upper-right corner of the **AuditData** column, click the expand icon.</span></span>

   ![В столбце AuditData щелкните значок расширения](../media/JSONTransformExpandIcon.png)

   <span data-ttu-id="6631f-142">Отображается неполный список свойств объектов JSON в столбце **AuditData.**</span><span class="sxs-lookup"><span data-stu-id="6631f-142">A partial list of the properties in the JSON objects in the **AuditData** column is displayed.</span></span>

7. <span data-ttu-id="6631f-143">Щелкните **Загрузить больше,** чтобы отобразить все свойства в объектах JSON в столбце **AuditData.**</span><span class="sxs-lookup"><span data-stu-id="6631f-143">Click **Load more** to display all properties in the JSON objects in the **AuditData** column.</span></span>

   ![Щелкните Загрузить больше, чтобы отобразить все свойства в объекте JSON](../media/JSONTransformLoadJSONProperties.png)

   <span data-ttu-id="6631f-145">Вы можете отключить почтовый ящик рядом с любым свойством, которое вы не хотите включать.</span><span class="sxs-lookup"><span data-stu-id="6631f-145">You can unselect the checkbox next to any property that you don't want to include.</span></span> <span data-ttu-id="6631f-146">Устранение столбцов, которые не являются полезными для вашего расследования, — это хороший способ уменьшить количество данных, отображающихся в журнале аудита.</span><span class="sxs-lookup"><span data-stu-id="6631f-146">Eliminating columns that aren't useful for your investigation is a good way to reduce the amount of data displayed in the audit log.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="6631f-147">Свойства JSON, отображаемые на предыдущем скриншоте (после нажатия нагрузки **больше),** основаны на свойствах, найденных в столбце **AuditData** из первых 1000 строк в CSV-файле.</span><span class="sxs-lookup"><span data-stu-id="6631f-147">The JSON properties displayed in the previous screenshot (after you click **Load more**) are based on the properties found in the **AuditData** column from the first 1,000 rows in the CSV file.</span></span> <span data-ttu-id="6631f-148">Если после первых 1000 строк в записях имеются различные свойства JSON, эти свойства (и соответствующий столбец) не будут включены при разделении столбца **AuditData** на несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="6631f-148">If there are different JSON properties in records after the first 1,000 rows, these properties (and a corresponding column) won't be included when the **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="6631f-149">Чтобы предотвратить это, рассмотрите возможность повторного запуска поиска журнала аудита и сузить критерии поиска, чтобы было возвращено меньше записей.</span><span class="sxs-lookup"><span data-stu-id="6631f-149">To help prevent this, consider re-running the audit log search and narrow the search criteria so that fewer records are returned.</span></span> <span data-ttu-id="6631f-150">Другим обходным решением является фильтрация элементов в столбце **Operations,** чтобы уменьшить число строк (перед выполнением шага 5 выше) перед преобразованием объекта JSON в столбце **AuditData.**</span><span class="sxs-lookup"><span data-stu-id="6631f-150">Another workaround is to filter items in the **Operations** column to reduce the number of rows (before you perform step 5 above) before transforming the JSON object in the **AuditData** column.</span></span>

   > [!TIP]
   > <span data-ttu-id="6631f-151">Чтобы просмотреть атрибут в списке, например AuditData.AffectedItems, щелкните значок Расширение в правом верхнем углу столбца, из чего нужно вытащить атрибут, а затем выберите Расширение до **New Row**. </span><span class="sxs-lookup"><span data-stu-id="6631f-151">To view an attribute within a list such as AuditData.AffectedItems, click the **Expand** icon in the upper right corner of the column you want to pull an attribute from, and then select **Expand to New Row**.</span></span>  <span data-ttu-id="6631f-152">Оттуда будет запись, и вы можете щелкнуть значок **Расширение** в верхнем правом углу столбца, просмотреть атрибуты и выбрать тот, который необходимо просмотреть или извлечь.</span><span class="sxs-lookup"><span data-stu-id="6631f-152">From there it will be a record and you can click the **Expand** icon in the upper right corner of the column, view the attributes, and select the one you want to view or extract.</span></span>

8. <span data-ttu-id="6631f-153">Сделайте одно из следующих вещей для формата заголовка столбцов, добавляемого для каждого выбранного свойства JSON.</span><span class="sxs-lookup"><span data-stu-id="6631f-153">Do one of the following things to format the title of the columns that are added for each JSON property that's selected.</span></span>

    - <span data-ttu-id="6631f-154">Отклонйте исходное имя **столбца** в качестве почтового ящика префикса, чтобы использовать имя свойства JSON в качестве имен столбцов; например, **RecordType** или **SourceFileName.**</span><span class="sxs-lookup"><span data-stu-id="6631f-154">Unselect the **Use original column name as prefix** checkbox to use the name of the JSON property as the column names; for example, **RecordType** or **SourceFileName**.</span></span>

    - <span data-ttu-id="6631f-155">Оставьте **исходное имя столбца в** качестве почтового ящика префикса, выбранного для добавления префикса AuditData в имена столбцов; например, **AuditData.RecordType** или **AuditData.SourceFileName.**</span><span class="sxs-lookup"><span data-stu-id="6631f-155">Leave the **Use original column name as prefix** checkbox selected to add the AuditData prefix to the column names; for example, **AuditData.RecordType** or **AuditData.SourceFileName**.</span></span>

9. <span data-ttu-id="6631f-156">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6631f-156">Click **OK**.</span></span>

    <span data-ttu-id="6631f-157">Столбец **AuditData** разделен на несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="6631f-157">The **AuditData** column is split into multiple columns.</span></span> <span data-ttu-id="6631f-158">Каждый новый столбец соответствует свойству объекта AuditData JSON.</span><span class="sxs-lookup"><span data-stu-id="6631f-158">Each new column corresponds to a property in the AuditData JSON object.</span></span> <span data-ttu-id="6631f-159">Каждая строка в столбце содержит значение свойства.</span><span class="sxs-lookup"><span data-stu-id="6631f-159">Each row in the column contains the value for the property.</span></span> <span data-ttu-id="6631f-160">Если свойство не содержит значения, отображается *значение null.*</span><span class="sxs-lookup"><span data-stu-id="6631f-160">If the property doesn't contain a value, the *null* value is displayed.</span></span> <span data-ttu-id="6631f-161">В Excel ячейки со значениями null пусты.</span><span class="sxs-lookup"><span data-stu-id="6631f-161">In Excel, cells with null values are empty.</span></span>
  
10. <span data-ttu-id="6631f-162">На **вкладке Главная** **нажмите кнопку Закрыть &,** чтобы закрыть редактор запроса питания и открыть преобразованный CSV-файл в книге Excel.</span><span class="sxs-lookup"><span data-stu-id="6631f-162">On the **Home** tab, click **Close & Load** to close the Power Query Editor and open the transformed CSV file in an Excel workbook.</span></span>

## <a name="use-powershell-to-search-and-export-audit-log-records"></a><span data-ttu-id="6631f-163">Использование PowerShell для поиска и экспорта записей журналов аудита</span><span class="sxs-lookup"><span data-stu-id="6631f-163">Use PowerShell to search and export audit log records</span></span>

<span data-ttu-id="6631f-164">Вместо использования средства поиска журналов аудита в Центре & обеспечения [](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) соответствия требованиям можно использовать в Exchange Online PowerShell для экспорта результатов поиска журнала аудита в CSV-файл.</span><span class="sxs-lookup"><span data-stu-id="6631f-164">Instead of using the audit log search tool in the Security & Compliance Center, you can use the [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell to export the results of an audit log search to a CSV file.</span></span> <span data-ttu-id="6631f-165">Затем вы можете следовать той же процедуре, описанной в шаге 2, чтобы форматирование журнала аудита с помощью редактора Power Query.</span><span class="sxs-lookup"><span data-stu-id="6631f-165">Then you can follow the same procedure described in Step 2 to format the audit log using the Power Query editor.</span></span> <span data-ttu-id="6631f-166">Одно из преимуществ использования комлета PowerShell заключается в том, что вы можете искать события из определенной службы с помощью *параметра RecordType.*</span><span class="sxs-lookup"><span data-stu-id="6631f-166">One advantage of using the PowerShell cmdlet is that you can search for events from a specific service by using the *RecordType* parameter.</span></span> <span data-ttu-id="6631f-167">Вот несколько примеров использования PowerShell для экспорта записей аудита в CSV-файл, чтобы можно было использовать редактор Power Query для преобразования объекта JSON в столбце **AuditData,** как описано в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="6631f-167">Here are few examples of using PowerShell to export audit records to a CSV file so you can use the Power Query editor to transform the JSON object in the **AuditData** column as described in Step 2.</span></span>

<span data-ttu-id="6631f-168">В этом примере запустите следующие команды, чтобы вернуть все записи, связанные с операциями общего доступа SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6631f-168">In this example, run the following commands to return all records related to SharePoint sharing operations.</span></span>

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

<span data-ttu-id="6631f-169">Результаты поиска экспортируются в CSV-файл с именем *PowerShellAuditlog,* содержащий четыре столбца: CreationDate, UserIds, RecordType, AuditData.</span><span class="sxs-lookup"><span data-stu-id="6631f-169">The search results are exported to a CSV file named *PowerShellAuditlog* that contains four columns: CreationDate, UserIds, RecordType, AuditData).</span></span>

<span data-ttu-id="6631f-170">В качестве значения параметра *RecordType* можно также использовать имя или значение переписи для типа записи.</span><span class="sxs-lookup"><span data-stu-id="6631f-170">You can also use the name or enum value for the record type as the value for the *RecordType* parameter.</span></span> <span data-ttu-id="6631f-171">Список имен типов записей и соответствующих значений списка см. в таблице *AuditLogRecordType* в схеме API управления [Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)</span><span class="sxs-lookup"><span data-stu-id="6631f-171">For a list of record type names and their corresponding enum values, see the *AuditLogRecordType* table in [Office 365 Management Activity API schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32).</span></span>

<span data-ttu-id="6631f-172">Можно включить только одно значение для *параметра RecordType.*</span><span class="sxs-lookup"><span data-stu-id="6631f-172">You can only include a single value for the *RecordType* parameter.</span></span> <span data-ttu-id="6631f-173">Чтобы найти записи аудита для других типов записей, необходимо выполнить две предыдущие команды, чтобы указать другой тип записи и примедить эти результаты к исходному CSV-файлу.</span><span class="sxs-lookup"><span data-stu-id="6631f-173">To search for audit records for other record types, you have to run the two previous commands again to specify a different record type and append those results to the original CSV file.</span></span> <span data-ttu-id="6631f-174">Например, вы запустите следующие две команды, чтобы добавить действия файла SharePoint из того же диапазона дат в PowerShellAuditlog.csv файл.</span><span class="sxs-lookup"><span data-stu-id="6631f-174">For example, you would run the following two commands to add SharePoint file activities from the same date range to the PowerShellAuditlog.csv file.</span></span>

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a><span data-ttu-id="6631f-175">Советы по экспорту и просмотру журнала аудита</span><span class="sxs-lookup"><span data-stu-id="6631f-175">Tips for exporting and viewing the audit log</span></span>

<span data-ttu-id="6631f-176">Ниже представлены некоторые советы и примеры экспорта и просмотра журнала аудита до и после использования функции преобразования JSON для разделения столбца **AuditData** на несколько столбцов.</span><span class="sxs-lookup"><span data-stu-id="6631f-176">Here are some tips and examples of exporting and viewing the audit log before and after you use the JSON transform feature to split the **AuditData** column into multiple columns.</span></span>

- <span data-ttu-id="6631f-177">Фильтр **столбца RecordType** для отображения только записей из определенной службы или функциональной области.</span><span class="sxs-lookup"><span data-stu-id="6631f-177">Filter the **RecordType** column to display only the records from a specific service or functional area.</span></span> <span data-ttu-id="6631f-178">Например, чтобы показать события, связанные с совместной деятельностью SharePoint, необходимо выбрать **14** (значение enum для записей, запускаемой действиями совместного доступа SharePoint).</span><span class="sxs-lookup"><span data-stu-id="6631f-178">For example, to show events related to SharePoint sharing, you would select **14** (the enum value for records triggered by SharePoint sharing activities).</span></span> <span data-ttu-id="6631f-179">Список служб, соответствующих значениям списка, отображаемого в столбце **RecordType,** см. в статье Подробные свойства в [журнале аудита.](detailed-properties-in-the-office-365-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="6631f-179">For a list of the services that correspond to the enum values displayed in the **RecordType** column, see [Detailed properties in the audit log](detailed-properties-in-the-office-365-audit-log.md).</span></span>

- <span data-ttu-id="6631f-180">Фильтр **столбца Operations** для отображения записей для определенных действий.</span><span class="sxs-lookup"><span data-stu-id="6631f-180">Filter the **Operations** column to display the records for specific activities.</span></span> <span data-ttu-id="6631f-181">Список большинства операций, соответствующих поисковой активности в средстве поиска журналов аудита в Центре соответствия требованиям & безопасности, см. в разделе "Аудит действий" в разделе Поиск журнала аудита в Центре соответствия требованиям & [безопасности.](search-the-audit-log-in-security-and-compliance.md#audited-activities)</span><span class="sxs-lookup"><span data-stu-id="6631f-181">For a list of most operations that correspond to a searchable activity in the audit log search tool in the Security & Compliance Center, see the "Audited activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#audited-activities).</span></span>
