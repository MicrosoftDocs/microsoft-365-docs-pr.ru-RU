---
title: Дублирование модели в Microsoft SharePoint Syntex
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
description: Узнайте, как и зачем дублировать модель в Microsoft SharePoint Syntex
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446081"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="fe548-103">Дублирование модели в Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="fe548-103">Duplicate a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="fe548-104">Дублирование модели осмысления документации может сэкономить время и усилия, если вам нужно создать новую модель и вы знаете, что существующая модель очень похожа на нужную вам.</span><span class="sxs-lookup"><span data-stu-id="fe548-104">Duplicating a document understanding model can save you time and effort if you need to create a new model, and know that an existing model is very similar to what you need.</span></span>

<span data-ttu-id="fe548-105">Например, существующая модель с именем "Контракты" классифицирует те же файлы, с которыми вам потребуется работать.</span><span class="sxs-lookup"><span data-stu-id="fe548-105">For example, an existing model named “Contracts” classifies the same files you need to work with.</span></span> <span data-ttu-id="fe548-106">Новая модель будет извлекать некоторые существующие данные, но ее потребуется обновить для извлечения дополнительных данных.</span><span class="sxs-lookup"><span data-stu-id="fe548-106">Your new model will extract some of the existing data, but will need to be updated to extract some additional data.</span></span> <span data-ttu-id="fe548-107">Вместо создания и обучения новой модели с нуля можно использовать функцию дублирования модели, чтобы создать копию модели "Контракты", которая также будет копировать все связанные элементы обучения, такие как примеры файлов и средства извлечения объектов.</span><span class="sxs-lookup"><span data-stu-id="fe548-107">Instead of creating and training a new model from scratch, you can use the duplicate model feature to make a copy of the Contracts model, which will also copy all associated training items, such as example files and entity extractors.</span></span>

<span data-ttu-id="fe548-108">Если вы дублируете модель, после ее переименования (например, на "Продление контрактов") вы можете внести в нее изменения.</span><span class="sxs-lookup"><span data-stu-id="fe548-108">When you duplicate the model, after you rename it (for example, to “Contract Renewals”), you can then make updates to it.</span></span> <span data-ttu-id="fe548-109">Например, можно удалить некоторые существующие извлеченные поля, которые вам не нужны, а затем обучить модель извлечению нового поля (например, "Дата продления").</span><span class="sxs-lookup"><span data-stu-id="fe548-109">For example, you can choose to remove some of the existing extracted fields that you don’t need, and then train the model to extract a new one (for example, “Renewal date”).</span></span>

## <a name="duplicate-a-model"></a><span data-ttu-id="fe548-110">Дублирование модели</span><span class="sxs-lookup"><span data-stu-id="fe548-110">Duplicate a model</span></span>

<span data-ttu-id="fe548-111">Выполните следующие действия, чтобы дублировать модель осмысления документации.</span><span class="sxs-lookup"><span data-stu-id="fe548-111">Follow these steps to duplicate a document understanding model.</span></span>

1. <span data-ttu-id="fe548-112">В центре контента выберите **Модели**, чтобы просмотреть список моделей.</span><span class="sxs-lookup"><span data-stu-id="fe548-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="fe548-113">На странице **Модели** выберите модель, которую нужно дублировать.</span><span class="sxs-lookup"><span data-stu-id="fe548-113">On the **Models** page, select the model you want to duplicate.</span></span>

3. <span data-ttu-id="fe548-114">С помощью ленты или кнопки **Показать действия** (рядом с именем модели) выберите **Дублировать**.</span><span class="sxs-lookup"><span data-stu-id="fe548-114">By using either the ribbon or the **Show actions** button (next to the model name), select **Duplicate**.</span></span></br>

    ![Снимок экрана: страница "Модели", на которой показана выбранная модель с выделенными параметрами "Дублировать".](../media/content-understanding/select-model-duplicate-both.png) </br>

4. <span data-ttu-id="fe548-116">На панели **Дублировать модель**:</span><span class="sxs-lookup"><span data-stu-id="fe548-116">On the **Duplicate model** panel:</span></span>

   <span data-ttu-id="fe548-117">а.</span><span class="sxs-lookup"><span data-stu-id="fe548-117">a.</span></span> <span data-ttu-id="fe548-118">В поле **Имя** введите новое имя модели, которую вы хотите дублировать.</span><span class="sxs-lookup"><span data-stu-id="fe548-118">Under **Name**, enter the new name of the model that you want to duplicate.</span></span></br>

    ![Снимок экрана: панель дублирования модели.](../media/content-understanding/duplicate-model-panel.png) </br>

   <span data-ttu-id="fe548-120">б.</span><span class="sxs-lookup"><span data-stu-id="fe548-120">b.</span></span> <span data-ttu-id="fe548-121">В разделе **Описание** добавьте описание новой модели.</span><span class="sxs-lookup"><span data-stu-id="fe548-121">Under **Description**, add a description of your new model.</span></span>

   <span data-ttu-id="fe548-122">в.</span><span class="sxs-lookup"><span data-stu-id="fe548-122">c.</span></span> <span data-ttu-id="fe548-123">(Необязательно) В разделе **Дополнительные параметры** выберите, следует ли связать существующий [тип контента](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span><span class="sxs-lookup"><span data-stu-id="fe548-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span>

5. <span data-ttu-id="fe548-124">Выберите **Дублировать**.</span><span class="sxs-lookup"><span data-stu-id="fe548-124">Select **Duplicate**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe548-125">См. также</span><span class="sxs-lookup"><span data-stu-id="fe548-125">See Also</span></span>
[<span data-ttu-id="fe548-126">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="fe548-126">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="fe548-127">Переименование модели</span><span class="sxs-lookup"><span data-stu-id="fe548-127">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="fe548-128">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="fe548-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="fe548-129">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="fe548-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="fe548-130">Типы объяснения</span><span class="sxs-lookup"><span data-stu-id="fe548-130">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="fe548-131">Применение модели</span><span class="sxs-lookup"><span data-stu-id="fe548-131">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="fe548-132">Режим специальных возможностей SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="fe548-132">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)