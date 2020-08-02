---
title: Разница между общими сведениями о документе и моделями обработки форм (Предварительная версия)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Описывает ключевые различия между обзором документа и моделями обработки форм.
ms.openlocfilehash: bceeb4b2f52ecf95aa0a23bf8970d1427088d877
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537433"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a><span data-ttu-id="16f71-103">Разница между общими сведениями о документе и моделями обработки форм (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="16f71-103">Difference between document understanding and form processing models (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="16f71-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="16f71-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="16f71-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="16f71-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="16f71-106">Сведения о контенте в Project Кортекс позволяют определять и классифицировать документы, которые передаются в библиотеки документов SharePoint, а также извлекают релевантную информацию из каждого файла.</span><span class="sxs-lookup"><span data-stu-id="16f71-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="16f71-107">Например, когда файлы передаются в библиотеку документов SharePoint, все файлы, которые определены как *заказы на покупку* , классифицируются как такие и отображаются в представлении настраиваемой библиотеки документов, в которой они отображаются.</span><span class="sxs-lookup"><span data-stu-id="16f71-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such and displayed in a custom document library view in which they are displayed.</span></span> <span data-ttu-id="16f71-108">Кроме того, можно получить определенные сведения из каждого файла (например, *номер заказа на покупку* и *итог*) и отображать их в столбце представления библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="16f71-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it in a column in your document library view.</span></span> 


<span data-ttu-id="16f71-109">Общее представление о содержимом позволяет создавать *модели* для идентификации и извлечения нужных сведений.</span><span class="sxs-lookup"><span data-stu-id="16f71-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span>  <span data-ttu-id="16f71-110">Существует два типа моделей, которые можно использовать:</span><span class="sxs-lookup"><span data-stu-id="16f71-110">There are two types of models that can be used:</span></span>

- [<span data-ttu-id="16f71-111">Общие сведения о моделях</span><span class="sxs-lookup"><span data-stu-id="16f71-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="16f71-112">Модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="16f71-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="16f71-113">Несмотря на то что обе модели используются для одной цели, существуют ключевые различия, которые повлияют на то, какие из них можно использовать.</span><span class="sxs-lookup"><span data-stu-id="16f71-113">While both models are used for generally the same purpose, there are key differences that will affect which ones you may choose to use.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="16f71-114">Структурированное и неструктурированное и частично структурированное содержимое</span><span class="sxs-lookup"><span data-stu-id="16f71-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="16f71-115">Используйте общие сведения о моделях для идентификации и извлечения данных из неструктурированных документов, таких как буквы или контракты, которые необходимо извлечь, в предложениях или определенных областях документа.</span><span class="sxs-lookup"><span data-stu-id="16f71-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="16f71-116">Например, неструктурированный документ может быть письмом продления контракта, который может быть записан различными способами.</span><span class="sxs-lookup"><span data-stu-id="16f71-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="16f71-117">Тем не менее, в тексте каждого документа, воздействующего на обновление контракта, есть информация, которая постоянно отображается, например текстовая строка "Дата начала службы", за которой следует фактическая дата.</span><span class="sxs-lookup"><span data-stu-id="16f71-117">However, there is information that is consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="16f71-118">Используйте модели обработки форм для определения файлов и извлечения данных из структурированных или частично структурированных документов, таких как формы или накладные, в которых имеются неясные пары "ключ-значение" (например, *Date: 10/1/2020*) \* или Table Data.</span><span class="sxs-lookup"><span data-stu-id="16f71-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices, where you have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="16f71-119">Например, хорошим кандидатом на обработку формы может быть форма запроса заказа компании, в которой клиенты должны предоставить сведения об определенных полях, расположенных в той же области макета документа, например, *имя*, *номер телефона*, *Общие затраты*и т. д.  Налоговая форма — это хороший пример структурированного документа.</span><span class="sxs-lookup"><span data-stu-id="16f71-119">As an example, a good candidate for form processing would be a company's order request form in which clients need to provide their information for specific fields which are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="16f71-120">Где они создаются</span><span class="sxs-lookup"><span data-stu-id="16f71-120">Where they are created</span></span>

<span data-ttu-id="16f71-121">Общие сведения о моделях создаются и управляются на сайте центра контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="16f71-121">Document understanding models are created and managed in a SharePoint content center site.</span></span> <span data-ttu-id="16f71-122">Необходимо иметь доступ к сайту центра контента, чтобы создать общие сведения о модели или применить ее к библиотеке документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="16f71-122">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="16f71-123">При создании общие сведения о модели вы создаете новый [тип контента SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) , который сохраняется в коллекции типов контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="16f71-123">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="16f71-124">При необходимости можно использовать существующие типы контента, чтобы определить модель, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="16f71-124">You can optionally use existing content types to define your model if needed.</span></span>

<span data-ttu-id="16f71-125">Модели обработки форм создаются в [построителе PowerApps AI](https://docs.microsoft.com/ai-builder/overview), но создание инициируется непосредственно из библиотеки документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="16f71-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint Document library.</span></span> <span data-ttu-id="16f71-126">Создание модели обработки форм должно быть включено в библиотеке документов, чтобы пользователь мог создать для него модель обработки формы, а администратор может сделать это в содержимом параметров администрирования.</span><span class="sxs-lookup"><span data-stu-id="16f71-126">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="16f71-127">Модели обработки форм используют потоки Повераутомате для обработки файлов при их отправке в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="16f71-127">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="16f71-128">С помощью моделей обработки форм также создаются новые [типы контента SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), которые также хранятся в коллекции типов контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="16f71-128">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), which are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="16f71-129">Где они могут быть применены</span><span class="sxs-lookup"><span data-stu-id="16f71-129">Where they can be applied</span></span>

<span data-ttu-id="16f71-130">Общие сведения о моделях документов можно применять к разным библиотекам документов SharePoint, к которым у вас есть доступ.</span><span class="sxs-lookup"><span data-stu-id="16f71-130">Document understanding models can be applied to different SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="16f71-131">С помощью центра контента можно не только создавать общие сведения о модели документа, но и применять ее к различным библиотекам документов.</span><span class="sxs-lookup"><span data-stu-id="16f71-131">You can use the content center to not only create a document understanding model, but also to apply it to different document libraries.</span></span> <span data-ttu-id="16f71-132">Центр управления контентом предоставляет более централизованный контроль над использованием моделей и их применении, так как эти сведения должны быть сведены в центр контента.</span><span class="sxs-lookup"><span data-stu-id="16f71-132">The content center gives a more central control of how document understanding models are used and where they are applied, since this information must roll up to a content center.</span></span>

<span data-ttu-id="16f71-133">Модели обработки форм в настоящее время можно применить только к библиотеке документов SharePoint, из которой они были созданы.</span><span class="sxs-lookup"><span data-stu-id="16f71-133">Form processing models can currently only be applied to the SharePoint document library from which they were created.</span></span> <span data-ttu-id="16f71-134">Это позволяет любому лицензированному пользователю, имеющему доступ к сайту, создавать модель обработки форм.</span><span class="sxs-lookup"><span data-stu-id="16f71-134">This allows any licensed user who has access to the site to create a form processing model.</span></span>




 ## <a name="see-also"></a><span data-ttu-id="16f71-135">См. также</span><span class="sxs-lookup"><span data-stu-id="16f71-135">See Also</span></span>
[<span data-ttu-id="16f71-136">Обучение: повышение производительности бизнеса с помощью построителя AI</span><span class="sxs-lookup"><span data-stu-id="16f71-136">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="16f71-137">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="16f71-137">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="16f71-138">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="16f71-138">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="16f71-139">Применение модели "Общие сведения о документе"</span><span class="sxs-lookup"><span data-stu-id="16f71-139">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="16f71-140">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="16f71-140">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>



  
  



