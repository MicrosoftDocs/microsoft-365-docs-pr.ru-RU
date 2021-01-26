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
ms.openlocfilehash: c0396c8e702d3e32db93d26dba23ab038546bea0
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976523"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="301e4-103">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="301e4-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="301e4-104">При осмыслении документации для автоматической классификации файлов и извлечения информации используются модели искусственного интеллекта (AI).</span><span class="sxs-lookup"><span data-stu-id="301e4-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="301e4-105">Эта функция лучше всего работает с неструктурированными документами, например с письмами и контрактами.</span><span class="sxs-lookup"><span data-stu-id="301e4-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="301e4-106">Анализируемые документы должны содержать текст, который можно найти с помощью фраз или шаблонов.</span><span class="sxs-lookup"><span data-stu-id="301e4-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="301e4-107">Обнаруженный текст определяет как тип файла (его классификатор), так и подлежащие извлечению данные (его экстракторы).</span><span class="sxs-lookup"><span data-stu-id="301e4-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="301e4-108">Дополнительные сведения о примерах сценариев осмысления документации см. в статье [Внедрение SharePoint Syntex: руководство по началу работы](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example).</span><span class="sxs-lookup"><span data-stu-id="301e4-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="301e4-109">Модели осмысления документации создаются и управляются с помощью сайтов SharePoint особого типа, который называется *центр управления контентом*.</span><span class="sxs-lookup"><span data-stu-id="301e4-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="301e4-110">В модели, применяемой к библиотеке документов SharePoint и связанной с некоторым типом контента, для хранения извлеченных сведений используются столбцы.</span><span class="sxs-lookup"><span data-stu-id="301e4-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="301e4-111">Созданный вами тип контента сохраняется в галерее типов контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="301e4-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="301e4-112">Вы также можете пользоваться существующими типами контента, чтобы применять их схемы.</span><span class="sxs-lookup"><span data-stu-id="301e4-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="301e4-113">Доступные только для чтения и запечатанные типы невозможно обновлять, поэтому их нельзя использовать в модели.</span><span class="sxs-lookup"><span data-stu-id="301e4-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="301e4-114">Добавляйте *классификаторы* и *экстракторы* в свои модели осмысления документации для выполнения следующих задач.</span><span class="sxs-lookup"><span data-stu-id="301e4-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="301e4-115">Классификаторы используются для поиска и классификации документов, загружаемых в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="301e4-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="301e4-116">Например, классификатор может быть "обучен", чтобы определять все загруженные в библиотеку документы, относящиеся к *продлению контракта*.</span><span class="sxs-lookup"><span data-stu-id="301e4-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="301e4-117">Тип контента "продление контракта" определяется вами при создании классификатора.</span><span class="sxs-lookup"><span data-stu-id="301e4-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="301e4-118">Экстракторы извлекают данные из этих документов.</span><span class="sxs-lookup"><span data-stu-id="301e4-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="301e4-119">Например, для всех обнаруженных в библиотеке документов, относящихся к продлению контракта, для каждого документа отображаются столбцы с *датой начала оказания услуг* и *наименованием клиента*.</span><span class="sxs-lookup"><span data-stu-id="301e4-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="301e4-120">Чтобы обучить и протестировать классификаторы и экстракторы своей модели, можно использовать образцы файлов.</span><span class="sxs-lookup"><span data-stu-id="301e4-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="301e4-121">Образцы файлов дают вашей модели примеры информации, которую нужно искать при поиске файлов и извлечении из них данных.</span><span class="sxs-lookup"><span data-stu-id="301e4-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="301e4-122">Например, вы можете научить классификаторы и экстракторы для документов, относящихся к продлению контрактов, с помощью образцов таких документов, используемых в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="301e4-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="301e4-123">Кроме того, образцы файлов можно использовать для проверки эффективности работы вашей модели.</span><span class="sxs-lookup"><span data-stu-id="301e4-123">You can also use example files to test the effectiveness of your model.</span></span>

> [!NOTE]
> <span data-ttu-id="301e4-124">Если вы используете технологию распознавание текста для сканирования документов, в Syntex действует ограничение в 15 страниц для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="301e4-124">If you use optical character recognition (OCR) technology to scan documents, Syntex has a 15-page limit for model training.</span></span>

<span data-ttu-id="301e4-125">После публикации своей модели используйте центр управления контентом, чтобы применить ее к любой библиотеке документов SharePoint, к которой у вас есть доступ.</span><span class="sxs-lookup"><span data-stu-id="301e4-125">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="see-also"></a><span data-ttu-id="301e4-126">См. также</span><span class="sxs-lookup"><span data-stu-id="301e4-126">See Also</span></span>
[<span data-ttu-id="301e4-127">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="301e4-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="301e4-128">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="301e4-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="301e4-129">Создание центра управления контентом</span><span class="sxs-lookup"><span data-stu-id="301e4-129">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="301e4-130">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="301e4-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="301e4-131">Применение модели</span><span class="sxs-lookup"><span data-stu-id="301e4-131">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="301e4-132">Различия между моделью осмысления документации и моделью обработки форм</span><span class="sxs-lookup"><span data-stu-id="301e4-132">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="301e4-133">Общие сведения об обработке форм</span><span class="sxs-lookup"><span data-stu-id="301e4-133">Form processing overview</span></span>](form-processing-overview.md)
