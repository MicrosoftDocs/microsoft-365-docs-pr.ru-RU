---
title: Общие сведения о документе (Предварительная версия)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Общие сведения о документе, Познакомьтесь в проекте кортекс.
ms.openlocfilehash: c1e4092164ee96d4f244f10be9ebab62a2c8da5b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950052"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="49eec-103">Общие сведения о документе (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="49eec-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="49eec-104">Проект Кортекс в настоящее время находится в режиме предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="49eec-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="49eec-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="49eec-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="49eec-106">В документе Общие сведения об использовании моделей AI для автоматизации классификации файлов и извлечения данных.</span><span class="sxs-lookup"><span data-stu-id="49eec-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="49eec-107">Лучше всего использовать неструктурированные документы, например, буквы и контракты.</span><span class="sxs-lookup"><span data-stu-id="49eec-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="49eec-108">В документах должен быть текст, который можно определить на основе фраз или шаблонов.</span><span class="sxs-lookup"><span data-stu-id="49eec-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="49eec-109">Указанный текст может обозначать как тип файла (его классификацию), так и то, что нужно извлечь (его средства извлечения).</span><span class="sxs-lookup"><span data-stu-id="49eec-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="49eec-110">Общие сведения о моделях создаются и управляются на сайте SharePoint, который называется центром контента.</span><span class="sxs-lookup"><span data-stu-id="49eec-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="49eec-111">При применении к библиотеке документов SharePoint модель связана с типом контента, который содержит столбцы для хранения извлекаемых данных.</span><span class="sxs-lookup"><span data-stu-id="49eec-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="49eec-112">Созданный тип контента хранится в коллекции типов контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="49eec-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="49eec-113">Вы также можете использовать существующие типы контента, чтобы использовать их схему.</span><span class="sxs-lookup"><span data-stu-id="49eec-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="49eec-114">Вы можете добавлять *классификаторы* и средства *извлечения* в документ, чтобы понять, как выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="49eec-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="49eec-115">Классификаторы используются для определения и классификации документов, которые передаются в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="49eec-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="49eec-116">Например, классификатор может иметь значение "обучено", чтобы определить все документы *продления контракта* , отправленные в библиотеку.</span><span class="sxs-lookup"><span data-stu-id="49eec-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="49eec-117">Тип контента для обновления по контракту определяется при создании классификатора.</span><span class="sxs-lookup"><span data-stu-id="49eec-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="49eec-118">Извлеченные данные извлекаются из этих документов.</span><span class="sxs-lookup"><span data-stu-id="49eec-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="49eec-119">Например, для всех документов по обновлению контрактов, идентифицированных в библиотеке документов, в представлении отображаются столбцы, в которых также отображается *Дата начала* и  *клиент* для каждого документа по обновлению контрактов.</span><span class="sxs-lookup"><span data-stu-id="49eec-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="49eec-120">Примеры файлов используются для обучения и тестирования классификаторов и средств извлечения в модели.</span><span class="sxs-lookup"><span data-stu-id="49eec-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="49eec-121">Примеры файлов предоставляют модель, которая будет выглядеть при попытке идентификации и извлечения данных из файлов.</span><span class="sxs-lookup"><span data-stu-id="49eec-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="49eec-122">Например, вы научитесь Научите классификаторы продления и средства извлечения с помощью примеров документов по продлению контрактов, с которыми работает ваша компания.</span><span class="sxs-lookup"><span data-stu-id="49eec-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="49eec-123">Кроме того, можно использовать примеры файлов для проверки эффективности модели.</span><span class="sxs-lookup"><span data-stu-id="49eec-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="49eec-124">После публикации модели используйте центр управления контентом, чтобы применить его к любой библиотеке документов SharePoint, к которой у вас есть доступ.</span><span class="sxs-lookup"><span data-stu-id="49eec-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="49eec-125">См. также</span><span class="sxs-lookup"><span data-stu-id="49eec-125">See Also</span></span>
[<span data-ttu-id="49eec-126">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="49eec-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="49eec-127">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="49eec-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="49eec-128">[Создание центра контента](create-a-content-center.md) 
 [Создание модели обработки форм](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="49eec-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="49eec-129">[Применение модели](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="49eec-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="49eec-130">Различие между документом Общие сведения и моделью обработки формы</span><span class="sxs-lookup"><span data-stu-id="49eec-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="49eec-131">Обзор обработки форм</span><span class="sxs-lookup"><span data-stu-id="49eec-131">Form processing overview</span></span>](form-processing-overview.md)




