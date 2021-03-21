---
title: Изучение частично индексных элементов в eDiscovery
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
description: Узнайте, как управлять частично индексными элементами (также называемыми неиндексуалными элементами) из Exchange, SharePoint и OneDrive для бизнеса в вашей организации.
ms.openlocfilehash: 5d30c0f7c6ae77236ba7fd9f2dbfcc7a0397ae21
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922583"
---
# <a name="investigating-partially-indexed-items-in-ediscovery"></a><span data-ttu-id="a0639-103">Изучение частично индексных элементов в eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a0639-103">Investigating partially indexed items in eDiscovery</span></span>

<span data-ttu-id="a0639-104">Поиск по обнаружению электронных данных, который вы запустите из центра соответствия требованиям Microsoft 365, автоматически включает частично индексные элементы в предполагаемые результаты поиска при выполнении поиска.</span><span class="sxs-lookup"><span data-stu-id="a0639-104">An eDiscovery search that you run from the Microsoft 365 compliance center automatically includes partially indexed items in the estimated search results when you run a search.</span></span> <span data-ttu-id="a0639-105">Частично индексация элементов — это элементы почтовых ящиков Exchange и документы на сайтах SharePoint и OneDrive для бизнеса, которые по каким-то причинам не были полностью индексироваться для поиска.</span><span class="sxs-lookup"><span data-stu-id="a0639-105">Partially indexed items are Exchange mailbox items and documents on SharePoint and OneDrive for Business sites that for some reason weren't completely indexed for search.</span></span> <span data-ttu-id="a0639-106">Большинство сообщений электронной почты и документов сайта успешно индексироваться, поскольку они подпадают под ограничения индексации [для сообщений электронной почты](limits-for-content-search.md#indexing-limits-for-email-messages).</span><span class="sxs-lookup"><span data-stu-id="a0639-106">Most email messages and site documents are successfully indexed because they fall within the [Indexing limits for email messages](limits-for-content-search.md#indexing-limits-for-email-messages).</span></span> <span data-ttu-id="a0639-107">Однако некоторые элементы могут превышать эти ограничения индексации и будут частично индексироваться.</span><span class="sxs-lookup"><span data-stu-id="a0639-107">However, some items may exceed these indexing limits, and will be partially indexed.</span></span> <span data-ttu-id="a0639-108">Вот другие причины, по которым элементы не могут индексироваться для поиска и возвращаются в качестве частично индексных элементов при запуске поиска по обнаружению электронных обнаружений:</span><span class="sxs-lookup"><span data-stu-id="a0639-108">Here are other reasons why items can't be indexed for search and are returned as partially indexed items when you run an eDiscovery search:</span></span>
  
- <span data-ttu-id="a0639-109">Сообщения электронной почты имеют присоединенный файл без допустимой обработки, например файлов изображений; это самая распространенная причина частично индексации элементов электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a0639-109">Email messages have an attached file without a valid handler, such as image files; this is the most common cause of partially indexed email items.</span></span>

- <span data-ttu-id="a0639-110">В сообщение электронной почты вложено слишком много файлов.</span><span class="sxs-lookup"><span data-stu-id="a0639-110">Too many files attached to an email message.</span></span>

- <span data-ttu-id="a0639-111">Размер файла, вложенного в сообщение электронной почты, превышает допустимый.</span><span class="sxs-lookup"><span data-stu-id="a0639-111">A file attached to an email message is too large.</span></span>

- <span data-ttu-id="a0639-112">Тип файла поддерживает индексирование, но произошла ошибка индексирования определенного файла.</span><span class="sxs-lookup"><span data-stu-id="a0639-112">The file type is supported for indexing but an indexing error occurred for a specific file.</span></span>

<span data-ttu-id="a0639-113">Несмотря на то, что он изменяется, большинство клиентов организаций имеют менее 1% контента по объему и менее 12% контента по размеру, который частично индексировали.</span><span class="sxs-lookup"><span data-stu-id="a0639-113">Although it varies, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span> <span data-ttu-id="a0639-114">Разница между объемом и размером заключается в том, что более крупные файлы имеют более высокую вероятность содержать содержимое, которое не может быть полностью проиндексироваться.</span><span class="sxs-lookup"><span data-stu-id="a0639-114">The reason for the difference between the volume versus size is that larger files have a higher probability of containing content that can't be completely indexed.</span></span>
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a><span data-ttu-id="a0639-115">Почему для поиска меняется частично индексация элементов?</span><span class="sxs-lookup"><span data-stu-id="a0639-115">Why does the partially indexed item count change for a search?</span></span>

<span data-ttu-id="a0639-116">После запуска поиска по обнаружению электронных данных общее число и размер частично индексированных элементов в поисковых расположениях перечислены в статистике результатов поиска, отображаемой в подробной статистике поиска.</span><span class="sxs-lookup"><span data-stu-id="a0639-116">After you run an eDiscovery search, the total number and size of partially indexed items in the locations that were searched are listed in the search result statistics that are displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="a0639-117">Обратите внимание,  *что*  в статистике поиска эти элементы называются неиндексуалами.</span><span class="sxs-lookup"><span data-stu-id="a0639-117">Note these are called  *unindexed items*  in the search statistics.</span></span> <span data-ttu-id="a0639-118">Вот несколько вещей, которые влияют на количество частично индексных элементов, возвращаемого в результатах поиска:</span><span class="sxs-lookup"><span data-stu-id="a0639-118">Here are a few things that will affect the number of partially indexed items that are returned in the search results:</span></span>
  
- <span data-ttu-id="a0639-119">Если элемент частично проиндексировали и соответствует запросу поиска, он включается как в число (и размер) элементов результатов поиска, так и частично индексные элементы.</span><span class="sxs-lookup"><span data-stu-id="a0639-119">If an item is partially indexed and matches the search query, it's included in both the count (and size) of search result items and partially indexed items.</span></span> <span data-ttu-id="a0639-120">Однако при экспорте результатов этого же поиска элемент включается только с набором результатов поиска; он не включен в качестве частично индексного элемента.</span><span class="sxs-lookup"><span data-stu-id="a0639-120">However, when the results of that same search are exported, the item is included only with set of search results; it's not included as a partially indexed item.</span></span>

- <span data-ttu-id="a0639-121">Если указать диапазон дат для запроса поиска (включив его в запрос ключевого слова или с помощью условия), любой частично индексированный элемент, не совпадающий с диапазоном дат, не входит в число частично индексных элементов.</span><span class="sxs-lookup"><span data-stu-id="a0639-121">If you specify a date range for a search query (by including it in the keyword query or by using a condition), any partially indexed item that doesn't match the date range isn't included in the count of partially indexed items.</span></span> <span data-ttu-id="a0639-122">Частично индексные элементы, которые входят в диапазон дат, включаются в число индексных элементов.</span><span class="sxs-lookup"><span data-stu-id="a0639-122">Partially indexed items that fall within date range are included in the count of indexed items.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a0639-123">Частично индексированные элементы, расположенные на сайтах  SharePoint и OneDrive, не включаются в оценку частично индексированных элементов, отображаемую в подробной статистике поиска.</span><span class="sxs-lookup"><span data-stu-id="a0639-123">Partially indexed items located in SharePoint and OneDrive sites *are not* included in the estimate of partially indexed items that's displayed in the detailed statistics for the search.</span></span> <span data-ttu-id="a0639-124">Однако частично индексируемые элементы можно экспортировать при экспорте результатов поиска об обнаружении электронных обнаружений.</span><span class="sxs-lookup"><span data-stu-id="a0639-124">However, partially indexed items can be exported when you export the results of an eDiscovery search.</span></span> <span data-ttu-id="a0639-125">Например, если искать только сайты, предполагаемое число частично индексных элементов будет нулевым.</span><span class="sxs-lookup"><span data-stu-id="a0639-125">For example, if you only search sites, the estimated number partially indexed items will be zero.</span></span>
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a><span data-ttu-id="a0639-126">Вычисление соотношения частично индексных элементов в организации</span><span class="sxs-lookup"><span data-stu-id="a0639-126">Calculating the ratio of partially indexed items in your organization</span></span>

<span data-ttu-id="a0639-127">Чтобы понять, как организация подвержена частично индексации элементов, можно выполнить поиск всего контента во всех почтовых ящиках (с помощью пустого запроса на ключевое слово).</span><span class="sxs-lookup"><span data-stu-id="a0639-127">To understand your organization's exposure to partially indexed items, you can run a search for all content in all mailboxes (by using a blank keyword query).</span></span> <span data-ttu-id="a0639-128">В следующем примере ниже 56 208 (4830 МБ) полностью индексировали элементы и 470 (316 МБ) частично индексировали элементы.</span><span class="sxs-lookup"><span data-stu-id="a0639-128">In the following example below, there are 56,208 (4,830 MB) fully indexed items and 470 (316 MB) partially indexed items.</span></span>
  
![Пример статистики поиска, показывающая частично индексные элементы](../media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
<span data-ttu-id="a0639-130">Процент частично индексных элементов можно определить с помощью следующих вычислений.</span><span class="sxs-lookup"><span data-stu-id="a0639-130">You can determine the percentage of partially indexed items by using the following calculations.</span></span>
  
 <span data-ttu-id="a0639-131">**Для вычисления соотношения частично индексных элементов в организации:**</span><span class="sxs-lookup"><span data-stu-id="a0639-131">**To calculate the ratio of partially indexed items in your organization:**</span></span>

`(Total number of partially indexed items/Total number of items) x 100`

`(470/56,208) x 100 = 0.84%`

<span data-ttu-id="a0639-132">С помощью результатов поиска из предыдущего примера частично индексируется 0,84% всех элементов почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="a0639-132">By using the search results from the previous example, .84% of all mailboxes items are partially indexed.</span></span>
  
 <span data-ttu-id="a0639-133">**Чтобы рассчитать процент от размера частично индексных элементов в организации:**</span><span class="sxs-lookup"><span data-stu-id="a0639-133">**To calculate the percentage of the size of partially indexed items in your organization:**</span></span>

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

<span data-ttu-id="a0639-134">Таким образом, в предыдущем примере 6,54% от общего размера элементов почтовых ящиков из частично индексных элементов.</span><span class="sxs-lookup"><span data-stu-id="a0639-134">So in the previous example, 6.54% of the total size of mailbox items are from partially indexed items.</span></span> <span data-ttu-id="a0639-135">Как уже говорилось ранее, большинство клиентов организаций имеют менее 1% контента по объему и менее 12% контента по размеру, который частично индексировали.</span><span class="sxs-lookup"><span data-stu-id="a0639-135">As previously stated, most organizations customers have less than 1% of content by volume and less than 12% of content by size that is partially indexed.</span></span>

## <a name="working-with-partially-indexed-items"></a><span data-ttu-id="a0639-136">Работа с частично индексными элементами</span><span class="sxs-lookup"><span data-stu-id="a0639-136">Working with partially indexed items</span></span>

<span data-ttu-id="a0639-137">В случаях, когда необходимо частично изучить элементы, чтобы проверить, что [](export-a-content-search-report.md) они не содержат релевантные сведения, можно экспортировать отчет о поиске контента, содержащий сведения о частично индексируемом элементе.</span><span class="sxs-lookup"><span data-stu-id="a0639-137">In cases when you need to examine partially items to validate that they don't contain relevant information, you can [export a content search report](export-a-content-search-report.md) that contains information about partially indexed items.</span></span> <span data-ttu-id="a0639-138">При экспорте отчета о поиске контента обязательно выберите один из вариантов экспорта, который включает частично индексируемые элементы.</span><span class="sxs-lookup"><span data-stu-id="a0639-138">When you export a content search report, be sure to choose one of the export options that includes partially indexed items.</span></span>
  
![Выберите второй или третий вариант экспорта частично индексных элементов](../media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
<span data-ttu-id="a0639-140">При экспорте результатов поиска электронных данных или отчета поиска с помощью одного из этих вариантов экспорт включает отчет с именем Unindexed Items.csv.</span><span class="sxs-lookup"><span data-stu-id="a0639-140">When you export eDiscovery search results or a search report using one of these options, the export includes a report named Unindexed Items.csv.</span></span> <span data-ttu-id="a0639-141">В этом отчете содержится большая часть той же информации, что и ResultsLog.csv файл; однако, файл Items.csv Unindexed также включает два поля, связанные с частично индексными элементами: **Теги** ошибок и **Свойства ошибок.**</span><span class="sxs-lookup"><span data-stu-id="a0639-141">This report includes most of the same information as the ResultsLog.csv file; however, the Unindexed Items.csv file also includes two fields related to partially indexed items: **Error Tags** and **Error Properties**.</span></span> <span data-ttu-id="a0639-142">В этих полях содержатся сведения об ошибке индексации для каждого частично индексного элемента.</span><span class="sxs-lookup"><span data-stu-id="a0639-142">These fields contain information about the indexing error for each partially indexed item.</span></span> <span data-ttu-id="a0639-143">Использование сведений в этих двух полях поможет определить, влияет ли ошибка индексации на конкретное исследование.</span><span class="sxs-lookup"><span data-stu-id="a0639-143">Using the information in these two fields can help you determine whether or not the indexing error for a particular impacts your investigation.</span></span> <span data-ttu-id="a0639-144">В этом случае можно выполнить целенаправленный поиск, получить и экспортировать определенные сообщения электронной почты и документы SharePoint или OneDrive, чтобы проверить их, чтобы определить, имеют ли они отношение к вашему расследованию.</span><span class="sxs-lookup"><span data-stu-id="a0639-144">If it does, you can perform a targeted search and retrieve and export specific email messages and SharePoint or OneDrive documents so that you can examine them to determine if they're relevant to your investigation.</span></span> <span data-ttu-id="a0639-145">Инструкции пошаговым образом см. в [материалах Prepare a CSV file for a targeted search in Office 365.](csv-file-for-an-id-list-content-search.md)</span><span class="sxs-lookup"><span data-stu-id="a0639-145">For step-by-step instructions, see [Prepare a CSV file for a targeted search in Office 365](csv-file-for-an-id-list-content-search.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a0639-146">Файл Единой Items.csv также содержит поля с именем **Тип ошибки** и **сообщение об ошибке.**</span><span class="sxs-lookup"><span data-stu-id="a0639-146">The Unindexed Items.csv file also contains fields named **Error Type** and **Error Message**.</span></span> <span data-ttu-id="a0639-147">Это устаревшие поля, содержащие сведения, аналогичные сведениям  в полях **Теги** ошибок и Свойства ошибок, но с менее подробными сведениями.</span><span class="sxs-lookup"><span data-stu-id="a0639-147">These are legacy fields that contain information that is similar to the information in the **Error Tags** and **Error Properties** fields, but with less detailed information.</span></span> <span data-ttu-id="a0639-148">Можно смело игнорировать эти устаревшие поля.</span><span class="sxs-lookup"><span data-stu-id="a0639-148">You can safely ignore these legacy fields.</span></span>
  
## <a name="errors-related-to-partially-indexed-items"></a><span data-ttu-id="a0639-149">Ошибки, связанные с частично индексациями элементов</span><span class="sxs-lookup"><span data-stu-id="a0639-149">Errors related to partially indexed items</span></span>

<span data-ttu-id="a0639-150">Теги ошибок состоит из двух частей информации: ошибки и типа файла.</span><span class="sxs-lookup"><span data-stu-id="a0639-150">Error tags are made up of two pieces of information, the error and the file type.</span></span> <span data-ttu-id="a0639-151">Например, в этой паре типа ошибки/файла:</span><span class="sxs-lookup"><span data-stu-id="a0639-151">For example, in this error/file-type pair:</span></span>

```text
 parseroutputsize_xls
```

 <span data-ttu-id="a0639-152">`parseroutputsize` является ошибкой `xls` и является типом файла, в который произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="a0639-152">`parseroutputsize` is the error and `xls` is the file type of the file the error occurred on.</span></span> <span data-ttu-id="a0639-153">В тех случаях, когда тип файла не был распознана или тип файла не применяется к ошибке, вы увидите значение на месте `noformat` типа файла.</span><span class="sxs-lookup"><span data-stu-id="a0639-153">In cases where the file type wasn't recognized or the file type didn't apply to the error, you will see the value `noformat` in place of the file type.</span></span>
  
<span data-ttu-id="a0639-154">Ниже приводится список ошибок индексации и описание возможной причины ошибки.</span><span class="sxs-lookup"><span data-stu-id="a0639-154">The following is a list of indexing errors and a description of the possible cause of the error.</span></span>
  
| <span data-ttu-id="a0639-155">Тег ошибки</span><span class="sxs-lookup"><span data-stu-id="a0639-155">Error tag</span></span> | <span data-ttu-id="a0639-156">Описание</span><span class="sxs-lookup"><span data-stu-id="a0639-156">Description</span></span> |
|:-----|:-----|
| `attachmentcount` <br/> |<span data-ttu-id="a0639-157">В сообщении электронной почты было слишком много вложений, и некоторые из этих вложений не обрабатывались.</span><span class="sxs-lookup"><span data-stu-id="a0639-157">An email message had too many attachments, and some of these attachments weren't processed.</span></span>  <br/> |
| `attachmentdepth` <br/> |<span data-ttu-id="a0639-158">Ретривер контента и парсер документов обнаружили слишком много уровней вложений, вложенных в другие вложения.</span><span class="sxs-lookup"><span data-stu-id="a0639-158">The content retriever and document parser found too many levels of attachments nested inside other attachments.</span></span> <span data-ttu-id="a0639-159">Некоторые из этих вложений не были обработаны.</span><span class="sxs-lookup"><span data-stu-id="a0639-159">Some of these attachments were not processed.</span></span>  <br/> |
| `attachmentrms` <br/> |<span data-ttu-id="a0639-160">Вложение не удалось декодировать, так как оно было защищено RMS.</span><span class="sxs-lookup"><span data-stu-id="a0639-160">An attachment failed decoding because it was RMS-protected.</span></span>  <br/> |
| `attachmentsize` <br/> |<span data-ttu-id="a0639-161">Файл, прикрепленный к сообщению электронной почты, был слишком большим и не мог быть обработан.</span><span class="sxs-lookup"><span data-stu-id="a0639-161">A file attached to an email message was too large and couldn't be processed.</span></span>  <br/> |
| `indexingtruncated` <br/> |<span data-ttu-id="a0639-162">При записи обработанного сообщения электронной почты в индекс одно из индексируемых свойств было слишком большим и было усечено.</span><span class="sxs-lookup"><span data-stu-id="a0639-162">When writing the processed email message to the index, one of the indexable properties was too large and was truncated.</span></span> <span data-ttu-id="a0639-163">Усеченные свойства перечислены в поле Свойства ошибок.</span><span class="sxs-lookup"><span data-stu-id="a0639-163">The truncated properties are listed in Error Properties field.</span></span>  <br/> |
| `invalidunicode` <br/> |<span data-ttu-id="a0639-164">Сообщение электронной почты содержит текст, который не может быть обработан как допустимый Юникод.</span><span class="sxs-lookup"><span data-stu-id="a0639-164">An email message contained text that couldn't be processed as valid Unicode.</span></span> <span data-ttu-id="a0639-165">Индексация этого элемента может быть неполной.</span><span class="sxs-lookup"><span data-stu-id="a0639-165">Indexing for this item may be incomplete.</span></span>  <br/> |
| `parserencrypted` <br/> |<span data-ttu-id="a0639-166">Содержимое вложения или сообщения электронной почты шифруется, и Microsoft 365 не может расшифровать содержимое.</span><span class="sxs-lookup"><span data-stu-id="a0639-166">The content of attachment or email message is encrypted, and Microsoft 365 couldn't decode the content.</span></span>  <br/> |
| `parsererror` <br/> |<span data-ttu-id="a0639-167">Неизвестная ошибка произошла при размыве.</span><span class="sxs-lookup"><span data-stu-id="a0639-167">An unknown error occurred during parsing.</span></span> <span data-ttu-id="a0639-168">Как правило, это является результатом ошибки программного обеспечения или сбоя службы.</span><span class="sxs-lookup"><span data-stu-id="a0639-168">This typically results from a software bug or a service crash.</span></span>  <br/> |
| `parserinputsize` <br/> |<span data-ttu-id="a0639-169">Вложение было слишком большим для обработки размерщика, и его обработка не была выполнена или не выполнена.</span><span class="sxs-lookup"><span data-stu-id="a0639-169">An attachment was too large for the parser to handle, and the parsing of that attachment didn't happen or wasn't completed.</span></span>  <br/> |
| `parsermalformed` <br/> |<span data-ttu-id="a0639-170">Вложение было неправильно обработано и не могло быть обработано с помощью parser.</span><span class="sxs-lookup"><span data-stu-id="a0639-170">An attachment was malformed and couldn't be handled by the parser.</span></span> <span data-ttu-id="a0639-171">Этот результат может быть обусловлен старыми форматами файлов, файлами, созданными несовместимым программным обеспечением, или вирусами, которые делают вид, что они не являются заявленными.</span><span class="sxs-lookup"><span data-stu-id="a0639-171">This result can be due to old file formats, files created by incompatible software, or viruses pretending to be something other than claimed.</span></span>  <br/> |
| `parseroutputsize` <br/> |<span data-ttu-id="a0639-172">Вывод при размыве вложения был слишком большим и его пришлось усечено.</span><span class="sxs-lookup"><span data-stu-id="a0639-172">The output from the parsing of an attachment was too large and had to be truncated.</span></span>  <br/> |
| `parserunknowntype` <br/> |<span data-ttu-id="a0639-173">Вложение было типом файла, который Не удалось обнаружить Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0639-173">An attachment had a file type that Microsoft 365 couldn't detect.</span></span>  <br/> |
| `parserunsupportedtype` <br/> |<span data-ttu-id="a0639-174">Вложение имеет тип файла, который Office 365 может обнаруживать, но его размыв не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a0639-174">An attachment had a file type that Office 365 could detect, but parsing that file type isn't supported.</span></span>  <br/> |
| `propertytoobig` <br/> |<span data-ttu-id="a0639-175">Значение свойства электронной почты в Exchange Store было слишком большим, чтобы получить и сообщение не может быть обработано.</span><span class="sxs-lookup"><span data-stu-id="a0639-175">The value of an email property in Exchange Store was too large to be retrieved and the message couldn't be processed.</span></span> <span data-ttu-id="a0639-176">Обычно это происходит только с свойством тела сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a0639-176">This typically only happens to the body property of an email message.</span></span>  <br/> |
| `retrieverrms` <br/> |<span data-ttu-id="a0639-177">Ретривер контента не смог расшифровать сообщение, защищенное от RMS.</span><span class="sxs-lookup"><span data-stu-id="a0639-177">The content retriever failed to decode an RMS-protected message.</span></span>  <br/> |
| `wordbreakertruncated` <br/> |<span data-ttu-id="a0639-178">Слишком много слов было обнаружено в документе во время индексации.</span><span class="sxs-lookup"><span data-stu-id="a0639-178">Too many words were identified in the document during indexing.</span></span> <span data-ttu-id="a0639-179">Обработка свойства остановлена при достижении предела, и свойство усечено.</span><span class="sxs-lookup"><span data-stu-id="a0639-179">Processing of the property stopped when reaching the limit, and the property is truncated.</span></span>  <br/> |

<span data-ttu-id="a0639-180">Поля ошибок описывают, на какие поля влияет ошибка обработки, указанная в поле Теги ошибок.</span><span class="sxs-lookup"><span data-stu-id="a0639-180">Error fields describe which fields are affected by the processing error listed in the Error Tags field.</span></span> <span data-ttu-id="a0639-181">Если вы ищете свойство, например или , ошибки в теле сообщения не влияют  `subject`  `participants` на результаты поиска.</span><span class="sxs-lookup"><span data-stu-id="a0639-181">If you're searching a property such as  `subject` or  `participants`, errors in the body of the message won't impact the results of your search.</span></span> <span data-ttu-id="a0639-182">Это может быть полезно при точном определении того, какие элементы частично индексировать, возможно, потребуется дополнительно изучить.</span><span class="sxs-lookup"><span data-stu-id="a0639-182">This can be useful when determining exactly which partially indexed items you might need to further investigate.</span></span>
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a><span data-ttu-id="a0639-183">Использование скрипта PowerShell для определения воздействия организации на частично индексные элементы электронной почты</span><span class="sxs-lookup"><span data-stu-id="a0639-183">Using a PowerShell script to determine your organization's exposure to partially indexed email items</span></span>

<span data-ttu-id="a0639-184">В следующих действиях покажите, как запустить скрипт PowerShell, который выполняет поиск всех элементов во всех почтовых ящиках Exchange, а затем создает отчет о соотношении частично индексных элементов электронной почты организации (по количеству и размеру) и отображает количество элементов (и их тип файла) для каждой ошибки индексации.</span><span class="sxs-lookup"><span data-stu-id="a0639-184">The following steps show you how to run a PowerShell script that searches for all items in all Exchange mailboxes, and then generates a report about your organization's ratio of partially indexed email items (by count and by size) and displays the number of items (and their file type) for each indexing error that occurs.</span></span> <span data-ttu-id="a0639-185">Чтобы определить ошибку индексирования, используйте описания тегов ошибок в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="a0639-185">Use the error tag descriptions in the previous section to identify the indexing error.</span></span>
  
1. <span data-ttu-id="a0639-186">Сохраните следующий текст в Windows PowerShell скрипта с помощью суффикса .ps1; например, `PartiallyIndexedItems.ps1` .</span><span class="sxs-lookup"><span data-stu-id="a0639-186">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `PartiallyIndexedItems.ps1`.</span></span>

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

2. <span data-ttu-id="a0639-187">[Подключитесь к Центру безопасности и соответствия требованиям PowerShell](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a0639-187">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

3. <span data-ttu-id="a0639-188">В центре & безопасности PowerShell перейдите в папку, в которой вы сохранили сценарий на шаге 1, а затем запустите сценарий; Например:</span><span class="sxs-lookup"><span data-stu-id="a0639-188">In Security & Compliance Center PowerShell, go to the folder where you saved the script in step 1, and then run the script; for example:</span></span>

   ```powershell
   .\PartiallyIndexedItems.ps1
   ```

<span data-ttu-id="a0639-189">Вот пример вывода, возвращаемой сценарием.</span><span class="sxs-lookup"><span data-stu-id="a0639-189">Here's an example fo the output returned by the script.</span></span>
  
![Пример вывода из скрипта, который создает отчет о воздействии организации на частично индексные элементы электронной почты](../media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)

> [!NOTE]
> <span data-ttu-id="a0639-191">Обратите внимание на следующее:</span><span class="sxs-lookup"><span data-stu-id="a0639-191">Note the following:</span></span>
>  
> - <span data-ttu-id="a0639-192">Общее число и размер элементов электронной почты, а также отношение организации к частично индексным пунктам электронной почты (по количеству и по размеру).</span><span class="sxs-lookup"><span data-stu-id="a0639-192">The total number and size of email items, and your organization's ratio of partially indexed email items (by count and by size).</span></span>
> 
> - <span data-ttu-id="a0639-193">Теги ошибок списка и соответствующие типы файлов, для которых произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="a0639-193">A list error tags and the corresponding file types for which the error occurred.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a0639-194">См. также</span><span class="sxs-lookup"><span data-stu-id="a0639-194">See also</span></span>

[<span data-ttu-id="a0639-195">Частично индексация элементов в eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a0639-195">Partially indexed items in eDiscovery</span></span>](partially-indexed-items-in-content-search.md)