---
title: Переименование модели в Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Узнайте, как и зачем переименовывать модель в Microsoft SharePoint Syntex.
ms.openlocfilehash: d0d17f040199b2e6b60bfc98d325f18b6de0b7f2
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446062"
---
# <a name="rename-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="5ee3b-103">Переименование модели в Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="5ee3b-103">Rename a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="5ee3b-104">В какой-то момент может потребоваться переименовать модель осмысления документации.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-104">At some point, you might want to rename a document understanding model.</span></span> <span data-ttu-id="5ee3b-105">Распространенным примером является создание исходного черновика модели, вы, возможно, не задумывались об окончательном имени (например, вы могли бы назвать его «AlexWilburModel1»).</span><span class="sxs-lookup"><span data-stu-id="5ee3b-105">A common example is when you create an initial draft of a model, you might not have given a lot of thought as to the final name (for example, you might have named it “AlexWilburModel1”).</span></span> <span data-ttu-id="5ee3b-106">По мере приближения к завершению модели и ее использованию, вы понимаете, что более правильным названием было бы «Продление контракта», и вы хотите переименовать его.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-106">As you come closer to finalizing the model and putting it to use, you realize that a more proper name would be “Contract Renewals,” and you want to rename it.</span></span>  

<span data-ttu-id="5ee3b-107">Еще один пример — когда ваша организация принимает решение ссылаться на процесс или тип документа под другим именем.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-107">Another example is when your organization makes a decision to refer to a process or document type by a different name.</span></span> <span data-ttu-id="5ee3b-108">Например, после создания модели и ее готовности к применению ваша организация может потребовать, чтобы все «Контракты» теперь формально назывались «Соглашениями».</span><span class="sxs-lookup"><span data-stu-id="5ee3b-108">For example, after you create your model and are ready to apply it, your organization might mandate that all “Contracts” will now formally be referred to as “Agreements.”</span></span> <span data-ttu-id="5ee3b-109">При необходимости вы можете переименовать модель с «Продление контракта» на «Продление соглашения».</span><span class="sxs-lookup"><span data-stu-id="5ee3b-109">If needed, you can choose to rename your model from “Contract Renewals” to “Agreement Renewals.”</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ee3b-110">Модель осмысления документации можно переименовать, только если она не была применена к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-110">You can only rename a document understanding model if it has not been applied to a document library.</span></span> 

<span data-ttu-id="5ee3b-111">Переименование модели также переименовывает [тип контента](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview), связанный с моделью.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-111">Renaming a model also renames the [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that is associated with the model.</span></span>

## <a name="rename-a-model"></a><span data-ttu-id="5ee3b-112">Переименование модели</span><span class="sxs-lookup"><span data-stu-id="5ee3b-112">Rename a model</span></span>

<span data-ttu-id="5ee3b-113">Выполните следующие действия, чтобы переименовать модель осмысления документации.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-113">Follow these steps to rename a document understanding model.</span></span>

1. <span data-ttu-id="5ee3b-114">В центре контента выберите **Модели**, чтобы просмотреть список моделей.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-114">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="5ee3b-115">На странице **Модели** выберите модель, которую нужно переименовать.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-115">On the **Models** page, select the model you want to rename.</span></span>

3. <span data-ttu-id="5ee3b-116">С помощью ленты или кнопки **Показать действия** (рядом с именем модели) выберите **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-116">By using either the ribbon or the **Show actions** button (next to the model name), select **Rename**.</span></span> </br>

    ![Снимок экрана: страница "Модели", на которой показана выбранная модель с выделенными параметрами "Переименовать".](../media/content-understanding/select-model-rename-both.png) </br>

4. <span data-ttu-id="5ee3b-118">На панели **Переименование модели**:</span><span class="sxs-lookup"><span data-stu-id="5ee3b-118">On the **Rename model** panel:</span></span>

   <span data-ttu-id="5ee3b-119">а.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-119">a.</span></span> <span data-ttu-id="5ee3b-120">В разделе **Новое имя** введите новое имя модели, которую вы хотите переименовать.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-120">Under **New name**, enter the new name of the model that you want to rename.</span></span></br>

    ![Снимок экрана: панель переименования модели.](../media/content-understanding/rename-model-panel.png) </br>

   <span data-ttu-id="5ee3b-122">б.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-122">b.</span></span> <span data-ttu-id="5ee3b-123">(Необязательно) В разделе **Дополнительные параметры** выберите, следует ли связать существующий [тип контента](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span><span class="sxs-lookup"><span data-stu-id="5ee3b-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span> <span data-ttu-id="5ee3b-124">Если выбрать **Использовать существующий тип контента**, модель будет переименована в соответствие с выбранным типом контента.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-124">If you choose **Use an existing content type**, the model will be renamed to match the selected content type.</span></span>

5. <span data-ttu-id="5ee3b-125">Выберите **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="5ee3b-125">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ee3b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="5ee3b-126">See Also</span></span>
[<span data-ttu-id="5ee3b-127">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="5ee3b-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="5ee3b-128">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="5ee3b-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="5ee3b-129">Переименование средства извлечения</span><span class="sxs-lookup"><span data-stu-id="5ee3b-129">Rename an extractor</span></span>](rename-an-extractor.md)

[<span data-ttu-id="5ee3b-130">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="5ee3b-130">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="5ee3b-131">Типы объяснения</span><span class="sxs-lookup"><span data-stu-id="5ee3b-131">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="5ee3b-132">Применение модели</span><span class="sxs-lookup"><span data-stu-id="5ee3b-132">Apply a model</span></span>](apply-a-model.md) 
