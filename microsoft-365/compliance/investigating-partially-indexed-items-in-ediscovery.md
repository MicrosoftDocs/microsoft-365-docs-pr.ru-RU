---
title: Исследование частично индексных элементов в eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как управлять частично индексными элементами (также называемыми неиндексациями) из Exchange, SharePoint и OneDrive для бизнеса в организации.
ms.openlocfilehash: 6a2a1d042c52a445538903fd7db9fc54305e6c13
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655453"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="57758-103">Исследование частично индексных элементов в eDiscovery</span><span class="sxs-lookup"><span data-stu-id="57758-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="57758-104">Поиск eDiscovery, который вы запустите из Центра соответствия требованиям Microsoft 365, автоматически включает частично индексные элементы в предполагаемые результаты поиска при выполнении поиска.</span><span class="sxs-lookup"><span data-stu-id="57758-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="57758-105">Частично индексные элементы — это элементы почтового ящика Exchange и документы на сайтах SharePoint и OneDrive для бизнеса, которые по какой-то причине не были полностью индексироваться для поиска.</span><span class="sxs-lookup"><span data-stu-id="57758-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="57758-106">Большинство сообщений электронной почты и документов сайта успешно индексироваться, так как они находятся в пределах индексации [для сообщений электронной почты.](limits-for-content-search.md#indexing-limits-for-email-messages)</span><span class="sxs-lookup"><span data-stu-id="57758-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="57758-107">Однако некоторые элементы могут превысить эти ограничения индексации и будут частично индексироваться.</span><span class="sxs-lookup"><span data-stu-id="57758-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="57758-108">Вот другие причины, по которым элементы не могут индексироваться для поиска и возвращаются в качестве частично индексных элементов при поиске при обнаружении электронных данными:</span><span class="sxs-lookup"><span data-stu-id="57758-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="57758-109">Сообщения электронной почты имеют вложенный файл без допустимой обработки, например файлы изображений; Это наиболее распространенная причина частично индексации элементов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="57758-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="57758-110">В сообщение электронной почты вложено слишком много файлов.</span><span class="sxs-lookup"><span data-stu-id="57758-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="57758-111">Размер файла, вложенного в сообщение электронной почты, превышает допустимый.</span><span class="sxs-lookup"><span data-stu-id="57758-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="57758-112">Тип файла поддерживает индексирование, но произошла ошибка индексирования определенного файла.</span><span class="sxs-lookup"><span data-stu-id="57758-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="57758-113">Хотя они различаются, в большинстве организаций клиенты имеют менее 1 % контента по объему и менее 12 % контента по размеру, который частично индексировать.</span><span class="sxs-lookup"><span data-stu-id="57758-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="57758-114">Разница между томом и размером заключается в том, что большие файлы с большей вероятностью содержат содержимое, которое не может быть полностью проиндексировать.</span><span class="sxs-lookup"><span data-stu-id="57758-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="57758-115">Почему количество частично индексных элементов меняется для поиска?</span><span class="sxs-lookup"><span data-stu-id="57758-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="57758-116">После запуска поиска при обнаружении электронных данных общее число и размер частично индексированных элементов в расположениях, в которые был внесен поиск, перечислены в статистике результатов поиска, которая отображается в подробной статистике поиска.</span><span class="sxs-lookup"><span data-stu-id="57758-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="57758-117">Обратите внимание, что они  *называются неndexed элементами*  в статистике поиска.</span><span class="sxs-lookup"><span data-stu-id="57758-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="57758-118">Вот несколько вещей, которые влияют на количество частично индексных элементов, которые возвращаются в результатах поиска:</span><span class="sxs-lookup"><span data-stu-id="57758-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="57758-119">Если элемент частично индексен и соответствует поисковому запросу, он включается как в число (и размер) элементов результатов поиска, так и в частично индексные элементы.</span><span class="sxs-lookup"><span data-stu-id="57758-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="57758-120">Однако при экспорте результатов того же поиска элемент включается только в набор результатов поиска; он не включается в качестве частично индексного элемента.</span><span class="sxs-lookup"><span data-stu-id="57758-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="57758-121">Если вы указываете диапазон дат для поискового запроса (включив его в запрос по ключевому слову или с помощью условия), то любой частично индексированный элемент, не совпадающий с диапазоном дат, не включается в число частично индексных элементов.</span><span class="sxs-lookup"><span data-stu-id="57758-121">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="57758-122">Частично индексные элементы, которые находятся в пределах диапазона дат, включаются в число индексных элементов.</span><span class="sxs-lookup"><span data-stu-id="57758-122">Partially indexed items that fall within date range are included in the count of indexed items.</span></span>

  > [!NOTE]
  > <span data-ttu-id="57758-123">Частично индексированные элементы, расположенные на сайтах  SharePoint и OneDrive, не включаются в оценку частично индексированных элементов, отображаемую в подробной статистике поиска.</span><span class="sxs-lookup"><span data-stu-id="57758-123">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="57758-124">Однако при экспорте результатов поиска eDiscovery можно экспортировать частично индексные элементы.</span><span class="sxs-lookup"><span data-stu-id="57758-124">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="57758-125">Например, если поиск ведется только на сайтах, приблизительный номер частично индексных элементов будет нулем.</span><span class="sxs-lookup"><span data-stu-id="57758-125">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="57758-126">Вычисление соотношения частично индексных элементов в организации</span><span class="sxs-lookup"><span data-stu-id="57758-126">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="57758-127">Чтобы понять, как организация подвержена частично индексации элементов, можно выполнить поиск всего содержимого во всех почтовых ящиках (с помощью пустого запроса по ключевому слову).</span><span class="sxs-lookup"><span data-stu-id="57758-127">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="57758-128">В следующем примере ниже 56 208 (4830 МБ) полностью индексных элементов и 470 (316 МБ) частично индексных элементов.</span><span class="sxs-lookup"><span data-stu-id="57758-128">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![Пример статистики поиска с частично индексными элементами](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="57758-130">Процент частично индексных элементов можно определить с помощью следующих вычислений.</span><span class="sxs-lookup"><span data-stu-id="57758-130">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="57758-131">**Чтобы вычислить отношение частично индексных элементов в организации:**</span><span class="sxs-lookup"><span data-stu-id="57758-131">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(470/56,208) x 100 = 0.84%`

<span data-ttu-id="57758-132">С помощью результатов поиска из предыдущего примера 0,84 % всех элементов почтовых ящиков индексируется частично.</span><span class="sxs-lookup"><span data-stu-id="57758-132">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="57758-133">**Чтобы вычислить процент от размера частично индексных элементов в организации:**</span><span class="sxs-lookup"><span data-stu-id="57758-133">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="57758-134">Таким образом, в предыдущем примере 6,54 % от общего размера элементов почтового ящика из частично индексных элементов.</span><span class="sxs-lookup"><span data-stu-id="57758-134">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="57758-135">Как было сказано ранее, в большинстве организаций клиенты имеют менее 1 % контента по объему и менее 12 % контента по размеру, который частично индексен.</span><span class="sxs-lookup"><span data-stu-id="57758-135">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="57758-136">Работа с частично индексными элементами</span><span class="sxs-lookup"><span data-stu-id="57758-136">Working with partially indexed items</span></span>

<span data-ttu-id="57758-137">В случаях, когда необходимо изучить частично элементы, чтобы проверить, что [](export-a-content-search-report.md) они не содержат релевантную информацию, можно экспортировать отчет о поиске контента, содержащий сведения о частично индексных элементов.</span><span class="sxs-lookup"><span data-stu-id="57758-137">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="57758-138">При экспорте отчета о поиске контента выберите один из вариантов экспорта, который включает частично индексные элементы.</span><span class="sxs-lookup"><span data-stu-id="57758-138">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![Выбор второго или третьего варианта экспорта частично индексных элементов](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="57758-140">При экспорте результатов поиска при обнаружении электронных данных или отчета о поиске с помощью одного из этих параметров экспорт включает отчет с именем Unindexed Items.csv.</span><span class="sxs-lookup"><span data-stu-id="57758-140">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="57758-141">Этот отчет включает большую часть той же информации, что и ResultsLog.csv файла; Однако файл неиндексирования Items.csv также содержит два поля, связанных с частично индексными элементами: **теги** ошибок и свойства **ошибки.**</span><span class="sxs-lookup"><span data-stu-id="57758-141">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="57758-142">Эти поля содержат сведения об ошибке индексирования для каждого частично индексирования элемента.</span><span class="sxs-lookup"><span data-stu-id="57758-142">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="57758-143">Использование данных в этих двух полях поможет определить, влияет ли ошибка индексирования на конкретное исследование.</span><span class="sxs-lookup"><span data-stu-id="57758-143">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="57758-144">В этом случае вы можете выполнить целевой поиск, а также получить и экспортировать определенные сообщения электронной почты, а также документы SharePoint или OneDrive, чтобы проверить их, чтобы определить, релевантны ли они для расследования.</span><span class="sxs-lookup"><span data-stu-id="57758-144">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="57758-145">Пошаговая инструкция см. в подготовьте CSV-файл для целевого поиска [в Office 365.](csv-file-for-an-id-list-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="57758-145">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="57758-146">Файл Неndexed Items.csv также содержит поля с именами **Error Type** и **Error Message.**</span><span class="sxs-lookup"><span data-stu-id="57758-146">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="57758-147">Это устаревшие поля, содержащие информацию, аналогичную сведениям в полях **"Теги** ошибок" и "Свойства **ошибки",** но с менее подробными сведениями.</span><span class="sxs-lookup"><span data-stu-id="57758-147">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="57758-148">Вы можете игнорировать эти устаревшие поля.</span><span class="sxs-lookup"><span data-stu-id="57758-148">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="57758-149">Ошибки, связанные с частично индексными элементами</span><span class="sxs-lookup"><span data-stu-id="57758-149">Errors related to partially indexed items</span></span>

<span data-ttu-id="57758-150">Теги ошибок состоит из двух сведений: ошибки и типа файла.</span><span class="sxs-lookup"><span data-stu-id="57758-150">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="57758-151">Например, в этой паре "ошибка/тип файла":</span><span class="sxs-lookup"><span data-stu-id="57758-151">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="57758-152">`parseroutputsize` — это ошибка и тип файла, в который `xls` произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="57758-152">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="57758-153">В случаях, когда тип файла не был распознат или тип файла не применяется к ошибке, вы увидите значение, а не `noformat` тип файла.</span><span class="sxs-lookup"><span data-stu-id="57758-153">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="57758-154">Ниже приводится список ошибок индексирования и описание возможной причины ошибки.</span><span class="sxs-lookup"><span data-stu-id="57758-154">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="57758-155">Тег ошибки</span><span class="sxs-lookup"><span data-stu-id="57758-155">Error tag</span></span> | <span data-ttu-id="57758-156">Описание</span><span class="sxs-lookup"><span data-stu-id="57758-156">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="57758-157">Сообщение электронной почты было слишком много вложений, и некоторые из этих вложений не были обработаны.</span><span class="sxs-lookup"><span data-stu-id="57758-157">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="57758-158">При извлечении контента и разберителе документов обнаружено слишком много уровней вложений, вложенных в другие вложения.</span><span class="sxs-lookup"><span data-stu-id="57758-158">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="57758-159">Некоторые из этих вложений не были обработаны.</span><span class="sxs-lookup"><span data-stu-id="57758-159">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="57758-160">Сбой декодирования вложения, так как он был защищен с защитой RMS.</span><span class="sxs-lookup"><span data-stu-id="57758-160">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="57758-161">Файл, вложенный в сообщение электронной почты, слишком велик и не может быть обработан.</span><span class="sxs-lookup"><span data-stu-id="57758-161">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="57758-162">При записи обработанного сообщения электронной почты в индекс одно из индексируемых свойств было слишком большим и было усечено.</span><span class="sxs-lookup"><span data-stu-id="57758-162">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="57758-163">Усеченные свойства перечислены в поле "Свойства ошибки".</span><span class="sxs-lookup"><span data-stu-id="57758-163">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="57758-164">Сообщение электронной почты содержало текст, который не удалось обработать как допустимый код Юникод.</span><span class="sxs-lookup"><span data-stu-id="57758-164">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="57758-165">Индексация для этого элемента может быть неполной.</span><span class="sxs-lookup"><span data-stu-id="57758-165">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="57758-166">Содержимое вложения или сообщения электронной почты зашифровано, и Microsoft 365 не удалось декодировать содержимое.</span><span class="sxs-lookup"><span data-stu-id="57758-166">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="57758-167">При разчете произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="57758-167">An unknown error occurred during parsing.</span></span> <span data-ttu-id="57758-168">Как правило, это является результатом ошибки программного обеспечения или сбоя службы.</span><span class="sxs-lookup"><span data-stu-id="57758-168">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="57758-169">Вложение было слишком большим, чтобы обработать его, а разбиение этого вложения не было выполнено или не было завершено.</span><span class="sxs-lookup"><span data-stu-id="57758-169">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="57758-170">Вложение было неправильно отформатированно и не может быть обработано с помощью разберегатель.</span><span class="sxs-lookup"><span data-stu-id="57758-170">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="57758-171">Это может быть вызвано старыми форматами файлов, файлами, созданными несовместимым программным обеспечением, или вирусами, которые утверждают, что они не являются утверждениями.</span><span class="sxs-lookup"><span data-stu-id="57758-171">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="57758-172">Выходные данные при разбиение вложения были слишком большими и были усечены.</span><span class="sxs-lookup"><span data-stu-id="57758-172">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="57758-173">Вложение имеет тип файла, который не удалось обнаружить в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57758-173">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="57758-174">Вложение имеет тип файла, который может обнаружить Office 365, но его разбиение не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="57758-174">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="57758-175">Значение свойства электронной почты в Магазине Exchange было слишком большим, чтобы его можно было извлечь, и сообщение не удалось обработать.</span><span class="sxs-lookup"><span data-stu-id="57758-175">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="57758-176">Обычно это происходит только со свойством body сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="57758-176">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="57758-177">Реизвлечения контента не удалось декодировать сообщение, защищенное RMS.</span><span class="sxs-lookup"><span data-stu-id="57758-177">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="57758-178">Во время индексации в документе было обнаружено слишком много слов.</span><span class="sxs-lookup"><span data-stu-id="57758-178">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="57758-179">Обработка свойства останавливается при достижении предела, а свойство усечено.</span><span class="sxs-lookup"><span data-stu-id="57758-179">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="57758-180">Поля ошибок описывают, на какие поля влияет ошибка обработки, указанная в поле "Теги ошибок".</span><span class="sxs-lookup"><span data-stu-id="57758-180">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="57758-181">Если вы ищете такие свойства, как или , ошибки в тексте сообщения не повлияет на  `subject`  `participants` результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="57758-181">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="57758-182">Это может быть полезно при точном определении частично индексных элементов, которые могут потребоваться для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="57758-182">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="57758-183">Использование сценария PowerShell для определения подверженности вашей организации частично индексным электронным письмам</span><span class="sxs-lookup"><span data-stu-id="57758-183">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="57758-184">Ниже покажите, как запустить сценарий PowerShell, который выполняет поиск всех элементов во всех почтовых ящиках Exchange, а затем создает отчет о соотношении частично индексных элементов электронной почты в организации (по количеству и размеру) и отображает количество элементов (и их тип файла) для каждой ошибки индексирования.</span><span class="sxs-lookup"><span data-stu-id="57758-184">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="57758-185">Используйте описания тегов ошибок в предыдущем разделе, чтобы определить ошибку индексирования.</span><span class="sxs-lookup"><span data-stu-id="57758-185">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="57758-186">Сохраните следующий текст в Windows PowerShell сценария с помощью суффикса имени файла PS1; например, `PartiallyIndexedItems.ps1` .</span><span class="sxs-lookup"><span data-stu-id="57758-186">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

   ```powershell
     write-host "**************************************************"
     write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
     write-host "**************************************************"
     " " 
     # Create a search with Error Tags Refinders enabled
     Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
     New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
     Start-ComplianceSearch "RefinerTest"
     # Loop while search is in progress
     do{
         Write-host "Waiting for search to complete..."
         Start-Sleep -s 5
         $complianceSearch = Get-ComplianceSearch "RefinerTest"
     }while ($complianceSearch.Status -ne 'Completed')
     $refiners = $complianceSearch.Refiners | ConvertFrom-Json
     $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
     $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
     $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
     " "
     "===== Partially indexed items ====="
     "         Total          Ratio"
     "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
     "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
     " "
     Write-Host ===== Reasons for partially indexed items =====
     foreach($errorTagProperty in $errorTagProperties)
     {
         $name = $refiners.Entries.($errorTagProperty.Name).Name
         $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
         $frag = $name.Split("{_}")
         $errorTag = $frag[0]
         $fileType = $frag[1]
         if ($errorTag -ne $lastErrorTag)
         {
             $errorTag
         }
         "    " + $fileType + " => " + $count
         $lastErrorTag = $errorTag
     }
   ```

2. <span data-ttu-id="57758-187">[Подключитесь к Центру безопасности и соответствия требованиям PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span><span class="sxs-lookup"><span data-stu-id="57758-187">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>

3. <span data-ttu-id="57758-188">В PowerShell & Центра безопасности и соответствия требованиям перейдите в папку, в которой вы сохранили сценарий на шаге 1, а затем запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="57758-188">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

<span data-ttu-id="57758-189">Вот пример выходных данных, возвращаемой сценарием.</span><span class="sxs-lookup"><span data-stu-id="57758-189">Here's an example fo the output returned by the script.</span></span>
  
![Пример выходных данных сценария, который создает отчет о риске частичной индексации элементов электронной почты в организации](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> <span data-ttu-id="57758-191">Обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="57758-191">Note the following:</span></span>
>  
> - <span data-ttu-id="57758-192">Общее количество и размер элементов электронной почты, а также соотношение частично индексных элементов электронной почты в организации (в зависимости от количества и размера).</span><span class="sxs-lookup"><span data-stu-id="57758-192">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size).</span></span>
> 
> - <span data-ttu-id="57758-193">Теги ошибок списка и соответствующие типы файлов, для которых произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="57758-193">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="57758-194">См. также</span><span class="sxs-lookup"><span data-stu-id="57758-194">See also</span></span>

[<span data-ttu-id="57758-195">Частично индексные элементы в eDiscovery</span><span class="sxs-lookup"><span data-stu-id="57758-195">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)
