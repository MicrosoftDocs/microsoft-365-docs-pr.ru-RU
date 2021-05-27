---
title: Общие сведения об осмыслении документации
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Узнайте об осмыслении документации в инструменте Microsoft SharePoint Syntex.
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683827"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="c2baf-103">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="c2baf-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="c2baf-104">При осмыслении документации для автоматической классификации файлов и извлечения информации используются модели искусственного интеллекта (AI).</span><span class="sxs-lookup"><span data-stu-id="c2baf-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="c2baf-105">Эта функция лучше всего работает с неструктурированными документами, например с письмами и контрактами.</span><span class="sxs-lookup"><span data-stu-id="c2baf-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="c2baf-106">Анализируемые документы должны содержать текст, который можно найти с помощью фраз или шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c2baf-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="c2baf-107">Обнаруженный текст определяет как тип файла (его классификатор), так и подлежащие извлечению данные (его экстракторы).</span><span class="sxs-lookup"><span data-stu-id="c2baf-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="c2baf-108">Дополнительные сведения о примерах сценариев осмысления документации см. в статье [Внедрение SharePoint Syntex: руководство по началу работы](./adoption-getstarted.md).</span><span class="sxs-lookup"><span data-stu-id="c2baf-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="c2baf-109">Модели осмысления документации создаются и управляются с помощью сайтов SharePoint особого типа, который называется *центр управления контентом*.</span><span class="sxs-lookup"><span data-stu-id="c2baf-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="c2baf-110">В модели, применяемой к библиотеке документов SharePoint и связанной с некоторым типом контента, для хранения извлеченных сведений используются столбцы.</span><span class="sxs-lookup"><span data-stu-id="c2baf-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="c2baf-111">Созданный вами тип контента сохраняется в галерее типов контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c2baf-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="c2baf-112">Вы также можете пользоваться существующими типами контента, чтобы применять их схемы.</span><span class="sxs-lookup"><span data-stu-id="c2baf-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="c2baf-113">Доступные только для чтения и запечатанные типы невозможно обновлять, поэтому их нельзя использовать в модели.</span><span class="sxs-lookup"><span data-stu-id="c2baf-113">Read-only or sealed content types cannot be updated, so they can't be used in a model.</span></span>

<span data-ttu-id="c2baf-114">Добавляйте *классификаторы* и *экстракторы* в свои модели осмысления документации для выполнения следующих задач.</span><span class="sxs-lookup"><span data-stu-id="c2baf-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="c2baf-115">Классификаторы используются для поиска и классификации документов, загружаемых в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="c2baf-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="c2baf-116">Например, классификатор может быть "обучен", чтобы определять все загруженные в библиотеку документы, относящиеся к *продлению контракта*.</span><span class="sxs-lookup"><span data-stu-id="c2baf-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="c2baf-117">Тип контента "продление контракта" определяется вами при создании классификатора.</span><span class="sxs-lookup"><span data-stu-id="c2baf-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="c2baf-118">Экстракторы извлекают данные из этих документов.</span><span class="sxs-lookup"><span data-stu-id="c2baf-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="c2baf-119">Например, для всех обнаруженных в библиотеке документов, относящихся к продлению контракта, для каждого документа отображаются столбцы с *датой начала оказания услуг* и *наименованием клиента*.</span><span class="sxs-lookup"><span data-stu-id="c2baf-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="c2baf-120">Чтобы обучить и протестировать классификаторы и экстракторы своей модели, можно использовать образцы файлов.</span><span class="sxs-lookup"><span data-stu-id="c2baf-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="c2baf-121">Образцы файлов дают вашей модели примеры информации, которую нужно искать при поиске файлов и извлечении из них данных.</span><span class="sxs-lookup"><span data-stu-id="c2baf-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="c2baf-122">Например, вы можете научить классификаторы и экстракторы для документов, относящихся к продлению контрактов, с помощью образцов таких документов, используемых в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c2baf-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="c2baf-123">Кроме того, образцы файлов можно использовать для проверки эффективности работы вашей модели.</span><span class="sxs-lookup"><span data-stu-id="c2baf-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="c2baf-124">После публикации своей модели используйте центр управления контентом, чтобы применить ее к любой библиотеке документов SharePoint, к которой у вас есть доступ.</span><span class="sxs-lookup"><span data-stu-id="c2baf-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="file-limitations"></a><span data-ttu-id="c2baf-125">Ограничения файлов</span><span class="sxs-lookup"><span data-stu-id="c2baf-125">File limitations</span></span>

<span data-ttu-id="c2baf-126">Модели осмысления документации используют технологию распознавания текста для сканирования PDF-файлов, изображений и TIFF-файлов как при обучении модели с помощью файлов примеров, так и при запуске модели с файлами в библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="c2baf-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="c2baf-127">Обратите внимание на следующие различия в текстовых файлах Microsoft Office и файлах, отсканированных с помощью технологии распознавания текста (PDF, изображение или TIFF):</span><span class="sxs-lookup"><span data-stu-id="c2baf-127">Note the following differences with regard to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="c2baf-128">Файлы Office: сокращаются на 64 000 символов (при обучении и при работе с файлами в библиотеке документов).</span><span class="sxs-lookup"><span data-stu-id="c2baf-128">Office files: Truncated at 64,000 characters (in training and when run against files in a document library).</span></span>

- <span data-ttu-id="c2baf-129">Файлы, отсканированные с помощью технологии распознавания текста: имеется ограничение в 20 страниц.</span><span class="sxs-lookup"><span data-stu-id="c2baf-129">OCR-scanned files: There's a 20-page limit.</span></span>  

### <a name="requirements"></a><span data-ttu-id="c2baf-130">Требования</span><span class="sxs-lookup"><span data-stu-id="c2baf-130">Requirements</span></span>

<span data-ttu-id="c2baf-131">Обработка с помощью технологии распознавания текста лучше всего работает с документами, которые соответствуют следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="c2baf-131">OCR processing works best on documents that meet the following requirements:</span></span>

- <span data-ttu-id="c2baf-132">Формат JPG, PNG или PDF (текст или сканирование).</span><span class="sxs-lookup"><span data-stu-id="c2baf-132">JPG, PNG, or PDF format (text or scanned).</span></span> <span data-ttu-id="c2baf-133">PDF-файлы со встроенным текстом лучше, так как при извлечении и расположении символов не будет ошибок.</span><span class="sxs-lookup"><span data-stu-id="c2baf-133">Text-embedded PDFs are better, because there won't be any errors in character extraction and location.</span></span>

- <span data-ttu-id="c2baf-134">Если ваши PDF-файлы заблокированы паролем, необходимо снять блокировку перед их отправкой.</span><span class="sxs-lookup"><span data-stu-id="c2baf-134">If your PDFs are password-locked, you must remove the lock before submitting them.</span></span>

- <span data-ttu-id="c2baf-135">Общий размер файла документов, используемых для обучения в каждой коллекции, не должен превышать 50 МБ, а PDF-документы не должны содержать более 500 страниц.</span><span class="sxs-lookup"><span data-stu-id="c2baf-135">The combined file size of the documents used for training per collection must not exceed 50 MB, and PDF documents shouldn't have more than 500 pages.</span></span>

- <span data-ttu-id="c2baf-136">Для изображений размеры должны быть от 50 × 50 до 10 000 × 10 000 пикселей.</span><span class="sxs-lookup"><span data-stu-id="c2baf-136">For images, dimensions must be between 50 × 50 and 10,000 × 10,000 pixels.</span></span>
   > [!NOTE]
   > <span data-ttu-id="c2baf-137">Очень широкие изображения или изображения нестандартных размеров (например, планы этажей) могут быть обрезаны в процессе распознавания текста и потерять точность.</span><span class="sxs-lookup"><span data-stu-id="c2baf-137">Images that are very wide or have odd dimensions (for example, floor plans) might get truncated in the OCR process and lose accuracy.</span></span>
 
- <span data-ttu-id="c2baf-138">Для PDF-файлов размеры должны быть не более 17 x 17 дюймов, что соответствует размерам бумаги Legal или A3 и меньше.</span><span class="sxs-lookup"><span data-stu-id="c2baf-138">For PDF files, dimensions must be at most 17 x 17 inches, corresponding to Legal or A3 paper sizes and smaller.</span></span>

- <span data-ttu-id="c2baf-139">При сканировании с бумажных документов отсканированные изображения должны быть высококачественными изображениями.</span><span class="sxs-lookup"><span data-stu-id="c2baf-139">If scanned from paper documents, scans should be high-quality images.</span></span>

- <span data-ttu-id="c2baf-140">Необходимо использовать латинский алфавит (английские символы).</span><span class="sxs-lookup"><span data-stu-id="c2baf-140">Must use the Latin alphabet (English characters).</span></span>

> [!NOTE]
> <span data-ttu-id="c2baf-141">AI Builder в настоящее время не поддерживает следующие типы входных данных обработки форм:</span><span class="sxs-lookup"><span data-stu-id="c2baf-141">AI Builder doesn't currently support the following types of form processing input data:</span></span><br><span data-ttu-id="c2baf-142">– Флажки или переключатели</span><span class="sxs-lookup"><span data-stu-id="c2baf-142">- Check boxes or radio buttons</span></span><br><span data-ttu-id="c2baf-143">– Подписи</span><span class="sxs-lookup"><span data-stu-id="c2baf-143">- Signatures</span></span><br><span data-ttu-id="c2baf-144">– Заполняемые PDF-файлы</span><span class="sxs-lookup"><span data-stu-id="c2baf-144">- Fillable PDFs</span></span>

### <a name="supported-file-types"></a><span data-ttu-id="c2baf-145">Поддерживаемые типы файлов</span><span class="sxs-lookup"><span data-stu-id="c2baf-145">Supported file types</span></span>

<span data-ttu-id="c2baf-146">Модели осмысления документации поддерживают следующие типы файлов:</span><span class="sxs-lookup"><span data-stu-id="c2baf-146">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="c2baf-147">DOC</span><span class="sxs-lookup"><span data-stu-id="c2baf-147">doc</span></span>
- <span data-ttu-id="c2baf-148">DOCX</span><span class="sxs-lookup"><span data-stu-id="c2baf-148">docx</span></span>
- <span data-ttu-id="c2baf-149">EML</span><span class="sxs-lookup"><span data-stu-id="c2baf-149">eml</span></span>
- <span data-ttu-id="c2baf-150">HEIC</span><span class="sxs-lookup"><span data-stu-id="c2baf-150">heic</span></span>
- <span data-ttu-id="c2baf-151">HEIF</span><span class="sxs-lookup"><span data-stu-id="c2baf-151">heif</span></span>
- <span data-ttu-id="c2baf-152">HTM</span><span class="sxs-lookup"><span data-stu-id="c2baf-152">htm</span></span>
- <span data-ttu-id="c2baf-153">HTML</span><span class="sxs-lookup"><span data-stu-id="c2baf-153">html</span></span>
- <span data-ttu-id="c2baf-154">JPEG</span><span class="sxs-lookup"><span data-stu-id="c2baf-154">jpeg</span></span>
- <span data-ttu-id="c2baf-155">JPG</span><span class="sxs-lookup"><span data-stu-id="c2baf-155">jpg</span></span>
- <span data-ttu-id="c2baf-156">Markdown</span><span class="sxs-lookup"><span data-stu-id="c2baf-156">markdown</span></span>
- <span data-ttu-id="c2baf-157">MD</span><span class="sxs-lookup"><span data-stu-id="c2baf-157">md</span></span>
- <span data-ttu-id="c2baf-158">MSG</span><span class="sxs-lookup"><span data-stu-id="c2baf-158">msg</span></span>
- <span data-ttu-id="c2baf-159">PDF</span><span class="sxs-lookup"><span data-stu-id="c2baf-159">pdf</span></span>
- <span data-ttu-id="c2baf-160">PNG</span><span class="sxs-lookup"><span data-stu-id="c2baf-160">png</span></span>
- <span data-ttu-id="c2baf-161">PPT</span><span class="sxs-lookup"><span data-stu-id="c2baf-161">ppt</span></span>
- <span data-ttu-id="c2baf-162">PPTX</span><span class="sxs-lookup"><span data-stu-id="c2baf-162">pptx</span></span>
- <span data-ttu-id="c2baf-163">RTF</span><span class="sxs-lookup"><span data-stu-id="c2baf-163">rtf</span></span>
- <span data-ttu-id="c2baf-164">TIF</span><span class="sxs-lookup"><span data-stu-id="c2baf-164">tif</span></span>
- <span data-ttu-id="c2baf-165">TIFF</span><span class="sxs-lookup"><span data-stu-id="c2baf-165">tiff</span></span>
- <span data-ttu-id="c2baf-166">TXT</span><span class="sxs-lookup"><span data-stu-id="c2baf-166">txt</span></span>
- <span data-ttu-id="c2baf-167">XLS</span><span class="sxs-lookup"><span data-stu-id="c2baf-167">xls</span></span>
- <span data-ttu-id="c2baf-168">XLSX</span><span class="sxs-lookup"><span data-stu-id="c2baf-168">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="c2baf-169">См. также</span><span class="sxs-lookup"><span data-stu-id="c2baf-169">See Also</span></span>
[<span data-ttu-id="c2baf-170">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="c2baf-170">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="c2baf-171">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="c2baf-171">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="c2baf-172">Создание центра управления контентом</span><span class="sxs-lookup"><span data-stu-id="c2baf-172">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="c2baf-173">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="c2baf-173">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="c2baf-174">Применение модели</span><span class="sxs-lookup"><span data-stu-id="c2baf-174">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="c2baf-175">Различия между моделью осмысления документации и моделью обработки форм</span><span class="sxs-lookup"><span data-stu-id="c2baf-175">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="c2baf-176">Общие сведения об обработке форм</span><span class="sxs-lookup"><span data-stu-id="c2baf-176">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="c2baf-177">Режим специальных возможностей SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="c2baf-177">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)