---
title: Общие сведения об осмыслении документации
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Узнайте об осмыслении документации в инструменте Microsoft SharePoint Syntex.
ms.openlocfilehash: d2bf581468eeee008d09a242876bed5ad07ae01f
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242414"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="87b39-103">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="87b39-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="87b39-104">При осмыслении документации для автоматической классификации файлов и извлечения информации используются модели искусственного интеллекта (AI).</span><span class="sxs-lookup"><span data-stu-id="87b39-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="87b39-105">Эта функция лучше всего работает с неструктурированными документами, например с письмами и контрактами.</span><span class="sxs-lookup"><span data-stu-id="87b39-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="87b39-106">Анализируемые документы должны содержать текст, который можно найти с помощью фраз или шаблонов.</span><span class="sxs-lookup"><span data-stu-id="87b39-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="87b39-107">Обнаруженный текст определяет как тип файла (его классификатор), так и подлежащие извлечению данные (его экстракторы).</span><span class="sxs-lookup"><span data-stu-id="87b39-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="87b39-108">Дополнительные сведения о примерах сценариев осмысления документации см. в статье [Внедрение SharePoint Syntex: руководство по началу работы](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="87b39-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="87b39-109">Модели осмысления документации создаются и управляются с помощью сайтов SharePoint особого типа, который называется *центр управления контентом*.</span><span class="sxs-lookup"><span data-stu-id="87b39-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="87b39-110">В модели, применяемой к библиотеке документов SharePoint и связанной с некоторым типом контента, для хранения извлеченных сведений используются столбцы.</span><span class="sxs-lookup"><span data-stu-id="87b39-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="87b39-111">Созданный вами тип контента сохраняется в галерее типов контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="87b39-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="87b39-112">Вы также можете пользоваться существующими типами контента, чтобы применять их схемы.</span><span class="sxs-lookup"><span data-stu-id="87b39-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="87b39-113">Доступные только для чтения и запечатанные типы невозможно обновлять, поэтому их нельзя использовать в модели.</span><span class="sxs-lookup"><span data-stu-id="87b39-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="87b39-114">Добавляйте *классификаторы* и *экстракторы* в свои модели осмысления документации для выполнения следующих задач.</span><span class="sxs-lookup"><span data-stu-id="87b39-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="87b39-115">Классификаторы используются для поиска и классификации документов, загружаемых в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="87b39-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="87b39-116">Например, классификатор может быть "обучен", чтобы определять все загруженные в библиотеку документы, относящиеся к *продлению контракта*.</span><span class="sxs-lookup"><span data-stu-id="87b39-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="87b39-117">Тип контента "продление контракта" определяется вами при создании классификатора.</span><span class="sxs-lookup"><span data-stu-id="87b39-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="87b39-118">Экстракторы извлекают данные из этих документов.</span><span class="sxs-lookup"><span data-stu-id="87b39-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="87b39-119">Например, для всех обнаруженных в библиотеке документов, относящихся к продлению контракта, для каждого документа отображаются столбцы с *датой начала оказания услуг* и *наименованием клиента*.</span><span class="sxs-lookup"><span data-stu-id="87b39-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="87b39-120">Чтобы обучить и протестировать классификаторы и экстракторы своей модели, можно использовать образцы файлов.</span><span class="sxs-lookup"><span data-stu-id="87b39-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="87b39-121">Образцы файлов дают вашей модели примеры информации, которую нужно искать при поиске файлов и извлечении из них данных.</span><span class="sxs-lookup"><span data-stu-id="87b39-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="87b39-122">Например, вы можете научить классификаторы и экстракторы для документов, относящихся к продлению контрактов, с помощью образцов таких документов, используемых в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="87b39-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="87b39-123">Кроме того, образцы файлов можно использовать для проверки эффективности работы вашей модели.</span><span class="sxs-lookup"><span data-stu-id="87b39-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="87b39-124">После публикации своей модели используйте центр управления контентом, чтобы применить ее к любой библиотеке документов SharePoint, к которой у вас есть доступ.</span><span class="sxs-lookup"><span data-stu-id="87b39-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

### <a name="file-limitations"></a><span data-ttu-id="87b39-125">Ограничения файлов</span><span class="sxs-lookup"><span data-stu-id="87b39-125">File limitations</span></span>

<span data-ttu-id="87b39-126">Модели осмысления документации используют технологию распознавания текста для сканирования PDF-файлов, изображений и TIFF-файлов как при обучении модели с помощью файлов примеров, так и при запуске модели с файлами в библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="87b39-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="87b39-127">Обратите внимание на следующие различия в текстовых файлах Microsoft Office и файлах, отсканированных с помощью технологии распознавания текста (PDF, изображение или TIFF):</span><span class="sxs-lookup"><span data-stu-id="87b39-127">Note the following differences in regards to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="87b39-128">Файлы Office: сокращаются на 64K символов (при обучении и при работе с файлами в библиотеке документов).</span><span class="sxs-lookup"><span data-stu-id="87b39-128">Office files: We truncate at 64K characters (in training and when run against files in a document library).</span></span>
- <span data-ttu-id="87b39-129">Файлы, отсканированные с помощью технологии распознавания текста: имеется ограничение в 20 страниц.</span><span class="sxs-lookup"><span data-stu-id="87b39-129">OCR-scanned files: There is a 20 page limit.</span></span>  

#### <a name="supported-file-types"></a><span data-ttu-id="87b39-130">Поддерживаемые типы файлов</span><span class="sxs-lookup"><span data-stu-id="87b39-130">Supported file types</span></span>

<span data-ttu-id="87b39-131">Модели осмысления документации поддерживают следующие типы файлов:</span><span class="sxs-lookup"><span data-stu-id="87b39-131">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="87b39-132">DOC</span><span class="sxs-lookup"><span data-stu-id="87b39-132">doc</span></span>
- <span data-ttu-id="87b39-133">DOCX</span><span class="sxs-lookup"><span data-stu-id="87b39-133">docx</span></span>
- <span data-ttu-id="87b39-134">EML</span><span class="sxs-lookup"><span data-stu-id="87b39-134">eml</span></span>
- <span data-ttu-id="87b39-135">HEIC</span><span class="sxs-lookup"><span data-stu-id="87b39-135">heic</span></span>
- <span data-ttu-id="87b39-136">HEIF</span><span class="sxs-lookup"><span data-stu-id="87b39-136">heif</span></span>
- <span data-ttu-id="87b39-137">HTM</span><span class="sxs-lookup"><span data-stu-id="87b39-137">htm</span></span>
- <span data-ttu-id="87b39-138">HTML</span><span class="sxs-lookup"><span data-stu-id="87b39-138">html</span></span>
- <span data-ttu-id="87b39-139">JPEG</span><span class="sxs-lookup"><span data-stu-id="87b39-139">jpeg</span></span>
- <span data-ttu-id="87b39-140">JPG</span><span class="sxs-lookup"><span data-stu-id="87b39-140">jpg</span></span>
- <span data-ttu-id="87b39-141">Markdown</span><span class="sxs-lookup"><span data-stu-id="87b39-141">markdown</span></span>
- <span data-ttu-id="87b39-142">MD</span><span class="sxs-lookup"><span data-stu-id="87b39-142">md</span></span>
- <span data-ttu-id="87b39-143">MSG</span><span class="sxs-lookup"><span data-stu-id="87b39-143">msg</span></span>
- <span data-ttu-id="87b39-144">PDF</span><span class="sxs-lookup"><span data-stu-id="87b39-144">pdf</span></span>
- <span data-ttu-id="87b39-145">PNG</span><span class="sxs-lookup"><span data-stu-id="87b39-145">png</span></span>
- <span data-ttu-id="87b39-146">PPT</span><span class="sxs-lookup"><span data-stu-id="87b39-146">ppt</span></span>
- <span data-ttu-id="87b39-147">PPTX</span><span class="sxs-lookup"><span data-stu-id="87b39-147">pptx</span></span>
- <span data-ttu-id="87b39-148">RTF</span><span class="sxs-lookup"><span data-stu-id="87b39-148">rtf</span></span>
- <span data-ttu-id="87b39-149">TIF</span><span class="sxs-lookup"><span data-stu-id="87b39-149">tif</span></span>
- <span data-ttu-id="87b39-150">TIFF</span><span class="sxs-lookup"><span data-stu-id="87b39-150">tiff</span></span>
- <span data-ttu-id="87b39-151">TXT</span><span class="sxs-lookup"><span data-stu-id="87b39-151">txt</span></span>
- <span data-ttu-id="87b39-152">XLS</span><span class="sxs-lookup"><span data-stu-id="87b39-152">xls</span></span>
- <span data-ttu-id="87b39-153">XLSX</span><span class="sxs-lookup"><span data-stu-id="87b39-153">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="87b39-154">См. также</span><span class="sxs-lookup"><span data-stu-id="87b39-154">See Also</span></span>
[<span data-ttu-id="87b39-155">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="87b39-155">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="87b39-156">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="87b39-156">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="87b39-157">Создание центра управления контентом</span><span class="sxs-lookup"><span data-stu-id="87b39-157">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="87b39-158">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="87b39-158">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="87b39-159">Применение модели</span><span class="sxs-lookup"><span data-stu-id="87b39-159">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="87b39-160">Различия между моделью осмысления документации и моделью обработки форм</span><span class="sxs-lookup"><span data-stu-id="87b39-160">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="87b39-161">Общие сведения об обработке форм</span><span class="sxs-lookup"><span data-stu-id="87b39-161">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="87b39-162">Режим специальных возможностей SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="87b39-162">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)
