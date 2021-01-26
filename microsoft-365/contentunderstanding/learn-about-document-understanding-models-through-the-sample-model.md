---
title: Подробнее о моделях осмысления документации на примере образца модели
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
description: Подробнее о моделях осмысления документации на примере образца модели
ms.openlocfilehash: f455e1ec854b4f9a6eea3fa6560ae5390892a640
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976415"
---
# <a name="learn-about-document-understanding-models-through-a-sample-model"></a><span data-ttu-id="ceb4f-103">Подробнее о моделях осмысления документации на примере образца модели</span><span class="sxs-lookup"><span data-stu-id="ceb4f-103">Learn about document understanding models through a sample model</span></span>

<span data-ttu-id="ceb4f-104">В Microsoft SharePoint Syntex имеется образец модели, которую можно исследовать, чтобы лучше понять, как создавать собственные модели.</span><span class="sxs-lookup"><span data-stu-id="ceb4f-104">Microsoft SharePoint Syntex provides you a with a sample model you can use to examine, giving you a better understanding of how to create your own models.</span></span> <span data-ttu-id="ceb4f-105">Образец модели также позволяет исследовать компоненты модели, такие как классификатор, средства извлечения и пояснения.</span><span class="sxs-lookup"><span data-stu-id="ceb4f-105">The sample model also allows you to examine model components, such as its classifier, extractors, and explanations.</span></span> <span data-ttu-id="ceb4f-106">Также можно использовать образцы файлов, чтобы обучить модель.</span><span class="sxs-lookup"><span data-stu-id="ceb4f-106">You can also use the sample files to train the model.</span></span>

## <a name="import-the-sample-model"></a><span data-ttu-id="ceb4f-107">Импорт образца модели</span><span class="sxs-lookup"><span data-stu-id="ceb4f-107">Import the sample model</span></span>

<span data-ttu-id="ceb4f-108">Чтобы получить доступ к образцу модели, нужно сначала импортировать модель в центр контента.</span><span class="sxs-lookup"><span data-stu-id="ceb4f-108">To access the sample model, you need to first import the model to your content center.</span></span>

1. <span data-ttu-id="ceb4f-109">В центре контента выберите **Модели**, чтобы просмотреть список моделей.</span><span class="sxs-lookup"><span data-stu-id="ceb4f-109">From the content center, select **Models** to see your models list.</span></span></br>
2. <span data-ttu-id="ceb4f-110">На странице **Модели** выберите **Импортировать образец модели**.</span><span class="sxs-lookup"><span data-stu-id="ceb4f-110">On the **Models** page, select **Import sample model**.</span></span></br>

    ![Импорт образца модели](../media/content-understanding/import-sample-model.png) </br>

3. <span data-ttu-id="ceb4f-112">Когда импорт завершится, откроется домашняя страница модели **BenefitsChangeNotice**.</span><span class="sxs-lookup"><span data-stu-id="ceb4f-112">When the import completes, the **BenefitsChangeNotice** model home page will open.</span></span> <span data-ttu-id="ceb4f-113">Если потребуется открыть образец модели в дальнейшем, это можно сделать в списке моделей в центре контента.</span><span class="sxs-lookup"><span data-stu-id="ceb4f-113">If you need to open the sample model in the future, you can do this from the models list in the content center.</span></span> </br>

     ![Домашняя страница образца](../media/content-understanding/sample-home-page.png)</br>

<span data-ttu-id="ceb4f-115">Можно анализировать образец модели не только для того, чтобы лучше понять устройство модели, но и чтобы улучшить рабочую модель и сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="ceb4f-115">You can not only look through analyze the sample model to get a better understanding of how the model is constructed, but as a working model can go further and do things such as:</span></span>

- <span data-ttu-id="ceb4f-116">Добавить еще одно средство извлечения.</span><span class="sxs-lookup"><span data-stu-id="ceb4f-116">Add a another extractor.</span></span> <span data-ttu-id="ceb4f-117">Например, добавить средство извлечения, которое извлекает *дисконтную комиссию*.</span><span class="sxs-lookup"><span data-stu-id="ceb4f-117">For example, add one that extracts the *discount fee*.</span></span>
- <span data-ttu-id="ceb4f-118">Применить модель к библиотеке документов и загрузить в нее некоторые учебные файлы, чтобы узнать, как модель классифицирует файлы и извлекает из них данные.</span><span class="sxs-lookup"><span data-stu-id="ceb4f-118">Apply the model to a document library, and upload some of the training files to it to see how the model classifies files and extracts data from them.</span></span>


## <a name="see-also"></a><span data-ttu-id="ceb4f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ceb4f-119">See Also</span></span>
[<span data-ttu-id="ceb4f-120">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="ceb4f-120">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="ceb4f-121">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="ceb4f-121">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="ceb4f-122">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="ceb4f-122">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="ceb4f-123">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="ceb4f-123">Create a form processing model</span></span>](create-a-form-processing-model.md)  
