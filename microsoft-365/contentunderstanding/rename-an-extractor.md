---
title: Переименование средства извлечения в Microsoft SharePoint Syntex
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
description: Узнайте, как и зачем переименовывать средство извлечения в Microsoft SharePoint Syntex.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2021
ms.locfileid: "51446056"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="6a5a9-103">Переименование средства извлечения в Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="6a5a9-103">Rename an extractor in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="6a5a9-104">В определенный момент может потребоваться переименовать извлечения, если вы хотите ссылаться на извлеченное поле данных с другим именем.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-104">At some point, you might need to rename an extractor if you want to refer to an extracted data field by a different name.</span></span> <span data-ttu-id="6a5a9-105">Например, ваша организация решает вносить изменения в свои контрактные документы и называет "клиентов" (customers) в своих документах "клиентами" (clients).</span><span class="sxs-lookup"><span data-stu-id="6a5a9-105">For example, your organization decides to make changes to their contract documents, and refers to “customers” as “clients” in their documents.</span></span> <span data-ttu-id="6a5a9-106">При извлечении поля "Клиент" (Customer) в модели, вы можете переименовать его в "Клиент" (Client).</span><span class="sxs-lookup"><span data-stu-id="6a5a9-106">If you were extracting a “Customer” field in your model, you can choose to rename it to “Client.”</span></span>

<span data-ttu-id="6a5a9-107">При синхронизации обновленной модели с библиотекой документов SharePoint вы увидите новый столбец "Клиент" в представлении библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-107">When you sync your updated model to your SharePoint document library, you will see a new “Client” column in your document library view.</span></span> <span data-ttu-id="6a5a9-108">В вашем представлении сохранится столбец "Клиент" (Customer) для прошлых действий, но будет обновлен новый столбец "Клиент" (Client) для всех новых документов, обрабатываемых вашей моделью.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-108">Your view will retain the “Customer” column for past activity, but will update the new “Client” column for all new documents that are processed by your model.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="6a5a9-109">Обязательно синхронизируйте обновленную модель с библиотеками документов, в которых она была ранее применена для отображения нового имени столбца.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-109">Make sure to sync your updated model to the document libraries where you had previously applied it for the new column name to display.</span></span> 

## <a name="rename-an-extractor"></a><span data-ttu-id="6a5a9-110">Переименование средства извлечения</span><span class="sxs-lookup"><span data-stu-id="6a5a9-110">Rename an extractor</span></span>

<span data-ttu-id="6a5a9-111">Выполните следующие действия, чтобы переименовать средство извлечения объектов.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-111">Follow these steps to rename an entity extractor.</span></span>

1. <span data-ttu-id="6a5a9-112">В центре контента выберите **Модели**, чтобы просмотреть список моделей.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="6a5a9-113">На странице **Модели** в столбце **Имя** выберите модель, для которой нужно переименовать средство извлечения.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-113">On the **Models** page, in the **Name** column, select the model for which you want to rename an extractor.</span></span>

3. <span data-ttu-id="6a5a9-114">В разделе **Средства извлечения объектов** выберите имя средства извлечения, которое вы хотите переименовать, а затем выберите **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-114">Under **Entity extractors**, select the name of the extractor you want to rename, and then select **Rename**.</span></span></br>

    ![Снимок экрана: раздел "Средство извлечения объектов" с выбранным средством извлечения с выделенной опцией "Переименовать".](../media/content-understanding/entity-extractor-rename.png) </br>

4. <span data-ttu-id="6a5a9-116">На панели **Переименование средства извлечения объектов**:</span><span class="sxs-lookup"><span data-stu-id="6a5a9-116">On the **Rename entity extractor** panel:</span></span>

   <span data-ttu-id="6a5a9-117">а.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-117">a.</span></span> <span data-ttu-id="6a5a9-118">В разделе **Новое имя** введите новое имя средства извлечения.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-118">Under **New name**, enter the new name of the extractor.</span></span></br>

    ![Снимок экрана: панель средства извлечения объектов.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   <span data-ttu-id="6a5a9-120">б.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-120">b.</span></span> <span data-ttu-id="6a5a9-121">(Необязательно) В разделе **Дополнительные параметры** выберите, следует ли связать существующий столбец сайта.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-121">(Optional) Under **Advanced settings**, select whether you want to associate an existing site column.</span></span>

5. <span data-ttu-id="6a5a9-122">Выберите **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="6a5a9-122">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a5a9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6a5a9-123">See Also</span></span>
[<span data-ttu-id="6a5a9-124">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="6a5a9-124">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="6a5a9-125">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="6a5a9-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="6a5a9-126">Переименование модели</span><span class="sxs-lookup"><span data-stu-id="6a5a9-126">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="6a5a9-127">Типы объяснения</span><span class="sxs-lookup"><span data-stu-id="6a5a9-127">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="6a5a9-128">Использование таксономии банка терминов при создании средства извлечения</span><span class="sxs-lookup"><span data-stu-id="6a5a9-128">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="6a5a9-129">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="6a5a9-129">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="6a5a9-130">Применение модели</span><span class="sxs-lookup"><span data-stu-id="6a5a9-130">Apply a model</span></span>](apply-a-model.md) 
