---
title: Общие сведения о документе
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Общие сведения о документе, Познакомьтесь со статьей Microsoft SharePoint Синтекс.
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294764"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="f94ec-103">Общие сведения о документе</span><span class="sxs-lookup"><span data-stu-id="f94ec-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="f94ec-104">Общие сведения об использовании моделей искусственной аналитики (AI) для автоматизации классификации файлов и извлечения информации.</span><span class="sxs-lookup"><span data-stu-id="f94ec-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="f94ec-105">Лучше всего использовать неструктурированные документы, например буквы или контракты.</span><span class="sxs-lookup"><span data-stu-id="f94ec-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="f94ec-106">В этих документах должен быть текст, который можно определить на основе фраз или шаблонов.</span><span class="sxs-lookup"><span data-stu-id="f94ec-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="f94ec-107">Указанный текст определяет тип файла (его классификацию) и то, что вы хотите извлечь (его средства извлечения).</span><span class="sxs-lookup"><span data-stu-id="f94ec-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="f94ec-108">Общие сведения о моделях создаются и управляются на сайте SharePoint, который называется *центром контента*.</span><span class="sxs-lookup"><span data-stu-id="f94ec-108">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="f94ec-109">При применении к библиотеке документов SharePoint модель, связанная с типом контента, содержит столбцы для хранения извлекаемых данных.</span><span class="sxs-lookup"><span data-stu-id="f94ec-109">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="f94ec-110">Созданный тип контента хранится в коллекции типов контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f94ec-110">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="f94ec-111">Вы также можете использовать существующие типы контента для использования их схемы.</span><span class="sxs-lookup"><span data-stu-id="f94ec-111">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="f94ec-112">Добавьте *классификаторы* и средства *извлечения* в документ, чтобы понять, какие модели выполняют следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="f94ec-112">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="f94ec-113">Классификаторы используются для определения и классификации документов, которые передаются в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="f94ec-113">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="f94ec-114">Например, классификатор может иметь значение "обучено", чтобы определить все документы *продления контракта* , отправленные в библиотеку.</span><span class="sxs-lookup"><span data-stu-id="f94ec-114">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="f94ec-115">Тип контента для обновления по контракту определяется при создании классификатора.</span><span class="sxs-lookup"><span data-stu-id="f94ec-115">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="f94ec-116">Извлеченные данные извлекаются из этих документов.</span><span class="sxs-lookup"><span data-stu-id="f94ec-116">Extractors pull information from these documents.</span></span> <span data-ttu-id="f94ec-117">Например, для всех документов по обновлению контрактов, определенных в библиотеке документов, в представлении отображаются столбцы, в которых также отображается *Дата начала* и  *клиент* для каждого документа продления контракта.</span><span class="sxs-lookup"><span data-stu-id="f94ec-117">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="f94ec-118">Вы можете использовать образцы файлов для обучения и тестирования классификаторов и средств извлечения в модели.</span><span class="sxs-lookup"><span data-stu-id="f94ec-118">You can use sample files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="f94ec-119">Примеры файлов предоставляют модель, которая будет выглядеть при попытке идентификации и извлечения данных из файлов.</span><span class="sxs-lookup"><span data-stu-id="f94ec-119">Sample files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="f94ec-120">Например, вы научитесь Научите классификаторы продления срока действия и средства извлечения, используя примеры документов по продлению контрактов, с которыми работает ваша компания.</span><span class="sxs-lookup"><span data-stu-id="f94ec-120">For example, you would train your contract renewal classifiers and extractors with samples of contract renewal documents your company works with.</span></span> <span data-ttu-id="f94ec-121">Кроме того, можно использовать примеры файлов для проверки эффективности модели.</span><span class="sxs-lookup"><span data-stu-id="f94ec-121">You can also use sample files to test the effectiveness of your model.</span></span>

<span data-ttu-id="f94ec-122">После публикации модели используйте центр управления контентом, чтобы применить его к любой библиотеке документов SharePoint, к которой у вас есть доступ.</span><span class="sxs-lookup"><span data-stu-id="f94ec-122">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="f94ec-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f94ec-123">See Also</span></span>
[<span data-ttu-id="f94ec-124">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="f94ec-124">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="f94ec-125">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="f94ec-125">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="f94ec-126">[Создание центра контента](create-a-content-center.md) 
 [Создание модели обработки форм](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="f94ec-126">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="f94ec-127">[Применение модели](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="f94ec-127">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="f94ec-128">Различие между документом Общие сведения и моделью обработки формы</span><span class="sxs-lookup"><span data-stu-id="f94ec-128">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="f94ec-129">Обзор обработки форм</span><span class="sxs-lookup"><span data-stu-id="f94ec-129">Form processing overview</span></span>](form-processing-overview.md)
