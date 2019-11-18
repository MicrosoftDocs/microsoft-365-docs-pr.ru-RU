---
title: Исследование частично индексированных элементов в функции обнаружения электронных данных в Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: Частично индексированные элементы (Кроме того, вызывают неиндексированные элементы) — это элементы почтовых ящиков Exchange и документы на сайтах SharePoint и OneDrive, по которым не удалось полностью индексироваться для поиска контента. В этой статье рассказывается, почему не удается индексировать элементы для поиска и возвращаются как частично индексированные элементы, Идентифицируйте ошибки поиска для частично индексированных элементов и используйте скрипт PowerShell для определения экспозиции Организации с частично индексированной электронной почтой. Недавние.
ms.openlocfilehash: 4e1430fe80c01b1cc9e67777c6955790ea1c6540
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "38687522"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a><span data-ttu-id="c3899-104">Исследование частично индексированных элементов в функции обнаружения электронных данных в Office 365</span><span class="sxs-lookup"><span data-stu-id="c3899-104">Investigating partially indexed items in Office 365 eDiscovery</span></span>

<span data-ttu-id="c3899-105">Поиск контента, который вы запускаете из центра безопасности & соответствия требованиям, автоматически включает частично индексированные элементы в оценочные результаты поиска при выполнении поиска.</span><span class="sxs-lookup"><span data-stu-id="c3899-105">A Content Search that you run from the Security & Compliance Center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="c3899-106">Частично индексированные элементы — это элементы почтовых ящиков Exchange и документы на сайтах SharePoint и OneDrive для бизнеса, по которым по какой-либо причине не удалось выполнить индексирование для поиска.</span><span class="sxs-lookup"><span data-stu-id="c3899-106">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="c3899-107">Большинство сообщений электронной почты и документов сайта успешно индексированы, так как они попадают в [пределы индексации сообщений электронной почты](limits-for-content-search.md#indexing-limits-for-email-messages).</span><span class="sxs-lookup"><span data-stu-id="c3899-107">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="c3899-108">Однако некоторые элементы могут превысить эти ограничения индексации и будут частично индексироваться.</span><span class="sxs-lookup"><span data-stu-id="c3899-108">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="c3899-109">Ниже приведены причины, по которым не удается индексировать элементы для поиска и возвращаются в виде частично индексированных элементов при выполнении поиска контента:</span><span class="sxs-lookup"><span data-stu-id="c3899-109">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run a Content Search:</span></span>
  
- <span data-ttu-id="c3899-110">Сообщения электронной почты имеют вложенный файл типа файлов, который не может индексироваться; в большинстве случаев тип файла не [распознается или не поддерживается для индексирования](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span><span class="sxs-lookup"><span data-stu-id="c3899-110">Email messages have an attached file of a file type that can't be indexed; in most cases, the file type is [unrecognized or unsupported for indexing](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)</span></span>
    
- <span data-ttu-id="c3899-111">Сообщения электронной почты имеют вложенный файл без допустимого обработчика, например файлов изображений; Это наиболее распространенная причина частично индексированных элементов электронной почты</span><span class="sxs-lookup"><span data-stu-id="c3899-111">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items</span></span>
    
- <span data-ttu-id="c3899-112">Слишком много файлов, вложенных в сообщение электронной почты</span><span class="sxs-lookup"><span data-stu-id="c3899-112">Too many files attached to an email message</span></span>
    
- <span data-ttu-id="c3899-113">Слишком большой файл, вложенный в сообщение электронной почты</span><span class="sxs-lookup"><span data-stu-id="c3899-113">A file attached to an email message is too large</span></span>
    
- <span data-ttu-id="c3899-114">Тип файла поддерживается для индексирования, но для определенного файла возникла ошибка индексирования</span><span class="sxs-lookup"><span data-stu-id="c3899-114">The file type is supported for indexing but an indexing error occurred for a specific file</span></span>
    
<span data-ttu-id="c3899-115">Несмотря на то, что это зависит от большинства пользователей Office 365, количество пользователей в Организации составляет менее 1% от объема контента и менее 12% содержимого по размеру, частично индексируемому.</span><span class="sxs-lookup"><span data-stu-id="c3899-115">Although it varies, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="c3899-116">Причина разницы между Томом и размером состоит в том, что большие файлы имеют большую вероятность того, что содержимое не может быть полностью индексировано.</span><span class="sxs-lookup"><span data-stu-id="c3899-116">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="c3899-117">Почему изменяется количество элементов с частичным индексированием для поиска?</span><span class="sxs-lookup"><span data-stu-id="c3899-117">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="c3899-118">После запуска поиска контента в центре безопасности & соответствия требованиям общее количество и размер частично индексированных элементов в найденных расположениях перечислены в статистике результатов поиска, которая отображается в подробных статистических данных для поиска.</span><span class="sxs-lookup"><span data-stu-id="c3899-118">After you run a Content Search in the Security & Compliance Center, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="c3899-119">Обратите внимание на то, что в статистике поиска называются *неиндексированные элементы* .</span><span class="sxs-lookup"><span data-stu-id="c3899-119">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="c3899-120">Ниже приведены некоторые моменты, которые влияют на количество частично индексированных элементов, возвращенных в результатах поиска.</span><span class="sxs-lookup"><span data-stu-id="c3899-120">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span> 
  
- <span data-ttu-id="c3899-121">Если элемент частично индексируется и соответствует поисковому запросу, он включается в число (и размер) элементов результатов поиска и частично индексированных элементов.</span><span class="sxs-lookup"><span data-stu-id="c3899-121">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="c3899-122">Однако при экспорте результатов поиска элемент включается только с набором результатов поиска; Он не входит в состав частично индексированного элемента.</span><span class="sxs-lookup"><span data-stu-id="c3899-122">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>
    
- <span data-ttu-id="c3899-123">Если указать диапазон дат для поискового запроса (включив его в запрос ключевых слов или с помощью условия), то все частично индексированные элементы, которые не совпадают с диапазоном дат, не включаются в число частично индексированных элементов.</span><span class="sxs-lookup"><span data-stu-id="c3899-123">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="c3899-124">Количество частично индексированных элементов включает только частично индексированные элементы, которые попадают в диапазон дат.</span><span class="sxs-lookup"><span data-stu-id="c3899-124">Only the partially indexed items that fall within date range are included in the count of partially indexed items.</span></span>
    
 <span data-ttu-id="c3899-125">**Примечание:** Частично индексированные элементы, расположенные в сайтах SharePoint и OneDrive, *не* включаются в оценку частично индексированных элементов, отображаемых в подробных статистике поиска.</span><span class="sxs-lookup"><span data-stu-id="c3899-125">**Note:** Partially indexed items located in SharePoint and OneDrive sites  *are not*  included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="c3899-126">Однако при экспорте результатов поиска контента могут быть экспортированы частично индексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="c3899-126">However, partially indexed items can be exported when you export the results of a Content Search.</span></span> <span data-ttu-id="c3899-127">Например, если поиск контента выполняется только на сайтах, то оценочное количество частично индексированных элементов будет равно нулю.</span><span class="sxs-lookup"><span data-stu-id="c3899-127">For example, if you only search sites in a Content Search, the estimated number partially indexed items will be zero.</span></span> 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="c3899-128">Вычисление соотношения частично индексированных элементов в Организации</span><span class="sxs-lookup"><span data-stu-id="c3899-128">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="c3899-129">Чтобы получить представление о выпуске частично индексированных элементов в Организации, можно выполнить поиск всего контента во всех почтовых ящиках (с помощью запроса с пустым ключевым словом).</span><span class="sxs-lookup"><span data-stu-id="c3899-129">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="c3899-130">В следующем примере ниже представлено 56 208 (4 830 МБ) полных индексированных элементов и 470 (316 МБ) частично индексированных элементов.</span><span class="sxs-lookup"><span data-stu-id="c3899-130">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![Пример статистики поиска, в которой показаны частично индексированные элементы](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="c3899-132">Вы можете определить процент частично индексированных элементов с помощью следующих вычислений.</span><span class="sxs-lookup"><span data-stu-id="c3899-132">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="c3899-133">**Чтобы вычислить отношение частично индексированных элементов в Организации:**</span><span class="sxs-lookup"><span data-stu-id="c3899-133">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
<span data-ttu-id="c3899-134">С помощью результатов поиска из предыдущего примера. 84% всех элементов почтовых ящиков частично индексируются.</span><span class="sxs-lookup"><span data-stu-id="c3899-134">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="c3899-135">**Чтобы вычислить процент от размера частично индексированных элементов в Организации, выполните указанные ниже действия.**</span><span class="sxs-lookup"><span data-stu-id="c3899-135">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="c3899-136">Таким образом, в предыдущем примере 6,54% общего размера элементов почтового ящика из частично индексированных элементов.</span><span class="sxs-lookup"><span data-stu-id="c3899-136">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="c3899-137">Как отмечалось ранее, большинство организаций Office 365 имеют менее 1% от объема контента и менее 12% содержимого по размеру, частично индексируемому.</span><span class="sxs-lookup"><span data-stu-id="c3899-137">As previously stated, most Office 365 organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="c3899-138">Работа с частично индексированными элементами</span><span class="sxs-lookup"><span data-stu-id="c3899-138">Working with partially indexed items</span></span>

<span data-ttu-id="c3899-139">В случаях, когда необходимо изучить частичные элементы, чтобы убедиться, что они не содержат релевантных сведений, можно [экспортировать отчет о поиске контента](export-a-content-search-report.md) , содержащий сведения об частично индексированных элементах.</span><span class="sxs-lookup"><span data-stu-id="c3899-139">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="c3899-140">При экспорте отчета по поиску контента обязательно Выбирайте один из вариантов экспорта, включающий частично индексированные элементы.</span><span class="sxs-lookup"><span data-stu-id="c3899-140">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span> 
  
![Выберите второй или третий вариант экспорта частично индексированных элементов](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="c3899-142">При экспорте результатов поиска контента или отчета о поиске контента с помощью одного из этих параметров экспорт включает отчет с именем "неиндексированные элементы. csv".</span><span class="sxs-lookup"><span data-stu-id="c3899-142">When you export content search results or a content search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="c3899-143">Этот отчет включает большинство тех же сведений, что и файл Ресултслог. CSV; Однако файл неиндексированных элементов. CSV также содержит два поля, связанные с частично индексированными элементами: **теги ошибок** и **свойства ошибок**.</span><span class="sxs-lookup"><span data-stu-id="c3899-143">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="c3899-144">В этих полях содержатся сведения об ошибке индексирования для каждого элемента с частичным индексированием.</span><span class="sxs-lookup"><span data-stu-id="c3899-144">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="c3899-145">Использование информации в этих двух полях поможет определить, может ли ошибка индексирования отявляться на конкретном проходе расследования.</span><span class="sxs-lookup"><span data-stu-id="c3899-145">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="c3899-146">Если это так, вы можете выполнить целевой поиск контента и извлечь и экспортировать определенные сообщения электронной почты, а также документы SharePoint или OneDrive, чтобы проверить, важны ли они для вашего расследования.</span><span class="sxs-lookup"><span data-stu-id="c3899-146">If it does, you can perform a targeted content search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="c3899-147">Пошаговые инструкции приведены [в разделе Подготовка CSV-файла для целевого поиска контента в Office 365](csv-file-for-an-id-list-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="c3899-147">For step-by-step instructions, see [Prepare a CSV file for a targeted Content Search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>
  
 <span data-ttu-id="c3899-148">**Примечание:** CSV-файл неиндексированных элементов содержит также поля " **тип ошибки** " и " **сообщение об ошибке**".</span><span class="sxs-lookup"><span data-stu-id="c3899-148">**Note:** The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="c3899-149">Это устаревшие поля, содержащие сведения, аналогичные сведениям в полях **ошибки** и **свойствах ошибок** , но с меньшими сведениями.</span><span class="sxs-lookup"><span data-stu-id="c3899-149">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="c3899-150">Вы можете спокойно проигнорировать эти устаревшие поля.</span><span class="sxs-lookup"><span data-stu-id="c3899-150">You can safely ignore these legacy fields.</span></span> 
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="c3899-151">Ошибки, связанные с частично индексированными элементами</span><span class="sxs-lookup"><span data-stu-id="c3899-151">Errors related to partially indexed items</span></span>

<span data-ttu-id="c3899-152">Теги ошибок состоят из двух частей информации, ошибки и типа файла.</span><span class="sxs-lookup"><span data-stu-id="c3899-152">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="c3899-153">Например, в этой ошибке или указанном сочетании:</span><span class="sxs-lookup"><span data-stu-id="c3899-153">For example, in this error/filetype pair:</span></span>

```text
 parseroutputsize_xls
```

   
 <span data-ttu-id="c3899-154">`parseroutputsize`— Это ошибка и `xls` тип файла, в котором произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="c3899-154">`parseroutputsize` is the error and  `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="c3899-155">В случаях, когда тип файла не распознается или тип файла не применяется к ошибке, отображается значение `noformat` на месте типа файла.</span><span class="sxs-lookup"><span data-stu-id="c3899-155">In cases were the file type wasn't recognized or the file type was doesn't apply to the error, you will see the value  `noformat` in place of the file type.</span></span> 
  
<span data-ttu-id="c3899-156">Ниже приведен список ошибок индексирования и описание возможных причин ошибки.</span><span class="sxs-lookup"><span data-stu-id="c3899-156">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
|<span data-ttu-id="c3899-157">**Тег Error**</span><span class="sxs-lookup"><span data-stu-id="c3899-157">**Error tag**</span></span>|<span data-ttu-id="c3899-158">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c3899-158">**Description**</span></span>|
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="c3899-159">В сообщении электронной почты слишком много вложений, и некоторые из этих вложений не были обработаны.</span><span class="sxs-lookup"><span data-stu-id="c3899-159">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="c3899-160">Средство извлечения контента и средство синтаксического анализа документов обнаружили слишком много уровней вложений, вложенных в другие вложения.</span><span class="sxs-lookup"><span data-stu-id="c3899-160">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="c3899-161">Некоторые из этих вложений не были обработаны.</span><span class="sxs-lookup"><span data-stu-id="c3899-161">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="c3899-162">Не удалось декодировать вложение, так как оно защищено службой управления правами.</span><span class="sxs-lookup"><span data-stu-id="c3899-162">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="c3899-163">Файл, вложенный в сообщение электронной почты, имеет слишком большой размер и не может быть обработан.</span><span class="sxs-lookup"><span data-stu-id="c3899-163">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="c3899-164">При записи обработанного сообщения электронной почты в индекс одно из индексируемых свойств было слишком большим и усечено.</span><span class="sxs-lookup"><span data-stu-id="c3899-164">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="c3899-165">Усеченные свойства перечислены в поле свойства ошибки.</span><span class="sxs-lookup"><span data-stu-id="c3899-165">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="c3899-166">Сообщение электронной почты содержит текст, который не удалось обработать как допустимый Юникод.</span><span class="sxs-lookup"><span data-stu-id="c3899-166">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="c3899-167">Индексирование этого элемента может быть неполным.</span><span class="sxs-lookup"><span data-stu-id="c3899-167">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="c3899-168">Содержимое вложения или сообщения электронной почты зашифровано, и Office 365 не удалось расшифровать содержимое.</span><span class="sxs-lookup"><span data-stu-id="c3899-168">The content of attachment or email message is encrypted, and Office 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="c3899-169">Во время синтаксического анализа произошла неизвестная ошибка.</span><span class="sxs-lookup"><span data-stu-id="c3899-169">An unknown error occurred during parsing.</span></span> <span data-ttu-id="c3899-170">Это обычно приводит к ошибке программного обеспечения или сбой службы.</span><span class="sxs-lookup"><span data-stu-id="c3899-170">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="c3899-171">Вложение слишком велико для обработки синтаксическим анализатором, и анализ этого вложения не выполнялся или не был завершен.</span><span class="sxs-lookup"><span data-stu-id="c3899-171">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="c3899-172">Вложение было неправильно сформировано и не может быть обработано средством синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="c3899-172">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="c3899-173">Это может быть вызвано устаревшими форматами файлов, файлами, созданными несовместимым программным обеспечением, или вирусами, которые не являются заявленными.</span><span class="sxs-lookup"><span data-stu-id="c3899-173">This result from can old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="c3899-174">Выходные данные синтаксического анализа вложения слишком велики и были усечены.</span><span class="sxs-lookup"><span data-stu-id="c3899-174">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="c3899-175">Для вложения имелся тип файлов, который не удалось обнаружить в Office 365.</span><span class="sxs-lookup"><span data-stu-id="c3899-175">An attachment had a file type that Office 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="c3899-176">В вложении имелся тип файла, который обнаруживается в Office 365could, но анализ этого типа файлов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c3899-176">An attachment had a file type that Office 365could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="c3899-177">Значение свойства электронной почты в хранилище Exchange слишком велико для получения, и сообщение не удалось обработать.</span><span class="sxs-lookup"><span data-stu-id="c3899-177">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="c3899-178">Обычно это происходит только для свойства Body сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c3899-178">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="c3899-179">Полученному содержимому не удалось декодировать сообщение, защищенное службой управления правами.</span><span class="sxs-lookup"><span data-stu-id="c3899-179">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="c3899-180">Во время индексирования обнаружено слишком много слов в документе.</span><span class="sxs-lookup"><span data-stu-id="c3899-180">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="c3899-181">Обработка свойства остановлена по достижении ограничения, а свойство усекается.</span><span class="sxs-lookup"><span data-stu-id="c3899-181">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |
   
<span data-ttu-id="c3899-182">Поля ошибок описывают поля, на которые влияет ошибка обработки, указанная в поле "теги ошибок".</span><span class="sxs-lookup"><span data-stu-id="c3899-182">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="c3899-183">Если вы ищете свойство, например `subject` или `participants`, ошибки в тексте сообщения, не повлияют на результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="c3899-183">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="c3899-184">Это может быть полезно, если вы точно определяет, какие частично индексированные элементы могут потребоваться для дальнейшего изучения.</span><span class="sxs-lookup"><span data-stu-id="c3899-184">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="c3899-185">Использование скрипта PowerShell для определения экспозиции Организации для частично индексированных элементов электронной почты</span><span class="sxs-lookup"><span data-stu-id="c3899-185">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="c3899-186">В следующих действиях показано, как запустить сценарий PowerShell, который выполняет поиск всех элементов во всех почтовых ящиках Exchange, а затем создает отчет о соотношении соотношения элементов электронной почты в Организации (по количеству и по размеру), а также отображает количество элементов (и их типы файлов) для каждой произошедшей ошибки индексирования.</span><span class="sxs-lookup"><span data-stu-id="c3899-186">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="c3899-187">Чтобы определить ошибку индексирования, используйте описания тегов ошибок в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="c3899-187">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="c3899-188">Сохраните приведенный ниже текст в файле скрипта Windows PowerShell, используя суффикс имени файла PS1; Пример: `PartiallyIndexedItems.ps1`.</span><span class="sxs-lookup"><span data-stu-id="c3899-188">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

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

2. <span data-ttu-id="c3899-189">[Подключитесь к PowerShell центра безопасности & соответствия требованиям](https://go.microsoft.com/fwlink/p/?linkid=627084).</span><span class="sxs-lookup"><span data-stu-id="c3899-189">[Connect to Security & Compliance Center PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084).</span></span>
    
3. <span data-ttu-id="c3899-190">В PowerShell центра безопасности & соответствия требованиям перейдите в папку, в которой сохранен сценарий на шаге 1, а затем запустите сценарий. Например:</span><span class="sxs-lookup"><span data-stu-id="c3899-190">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

    ```powershell
    .\PartiallyIndexedItems.ps1
    ```

<span data-ttu-id="c3899-191">Ниже приведен пример выходных данных, возвращаемых сценарием.</span><span class="sxs-lookup"><span data-stu-id="c3899-191">Here's an example fo the output returned by the script.</span></span>
  
![Пример выходных данных из скрипта, который создает отчет о экспозиции Организации для частично индексированных элементов электронной почты](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
<span data-ttu-id="c3899-193">Обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="c3899-193">Note the following:</span></span>
  
1. <span data-ttu-id="c3899-194">Общее количество и размер элементов электронной почты, а также степень проиндексированных элементов электронной почты в Организации (по количеству и по размеру)</span><span class="sxs-lookup"><span data-stu-id="c3899-194">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size)</span></span>
    
2. <span data-ttu-id="c3899-195">Теги ошибок списка и соответствующие типы файлов, для которых возникла ошибка.</span><span class="sxs-lookup"><span data-stu-id="c3899-195">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c3899-196">См. также</span><span class="sxs-lookup"><span data-stu-id="c3899-196">See also</span></span>

[<span data-ttu-id="c3899-197">Частично индексированные элементы в средстве "Поиск контента" в Office 365</span><span class="sxs-lookup"><span data-stu-id="c3899-197">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
