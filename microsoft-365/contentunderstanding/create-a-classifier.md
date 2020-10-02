---
title: Создание классификатора
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Сведения о создании классификатора
ms.openlocfilehash: 948ece1a19b7e6049167c373b3200efd316a60cd
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338641"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="5696e-103">Создание классификатора в Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="5696e-103">Create a classifier in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="5696e-104">Классификатор — это разновидность модели, с помощью которой можно автоматизировать определение и классификацию типов документов.</span><span class="sxs-lookup"><span data-stu-id="5696e-104">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="5696e-105">Например, вы можете определить все документы для *продления контракта*, добавленные в библиотеку документов, например, как на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="5696e-105">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Документ для продления контракта](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="5696e-107">Создание классификатора позволяет создать новый [тип контента SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview), который будет связан с моделью.</span><span class="sxs-lookup"><span data-stu-id="5696e-107">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="5696e-108">При создании классификатора вам требуется создать *объяснения*, чтобы определить модель.</span><span class="sxs-lookup"><span data-stu-id="5696e-108">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="5696e-109">Это позволяет вам отметить общие данные, которые вы ожидаете видеть в этом типе документа.</span><span class="sxs-lookup"><span data-stu-id="5696e-109">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="5696e-110">Используйте примеры типа документа ("примеры файлов"), чтобы "обучить" модель определению файлов с таким же типом контента.</span><span class="sxs-lookup"><span data-stu-id="5696e-110">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="5696e-111">Чтобы создать классификатор, вам потребуется выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5696e-111">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="5696e-112">Присвоение имени модели.</span><span class="sxs-lookup"><span data-stu-id="5696e-112">Name your model.</span></span>
2. <span data-ttu-id="5696e-113">Добавление примеров файлов.</span><span class="sxs-lookup"><span data-stu-id="5696e-113">Add your example files.</span></span>
3. <span data-ttu-id="5696e-114">Пометка примеров файлов.</span><span class="sxs-lookup"><span data-stu-id="5696e-114">Label your example files.</span></span>
4. <span data-ttu-id="5696e-115">Создание объяснения.</span><span class="sxs-lookup"><span data-stu-id="5696e-115">Create an explanation.</span></span>
5. <span data-ttu-id="5696e-116">Тестирование модели.</span><span class="sxs-lookup"><span data-stu-id="5696e-116">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="5696e-117">Ваша модель использует классификатор для определения и классификации типов документов, но вы также можете извлекать конкретные элементы информации из каждого файла, определенного моделью.</span><span class="sxs-lookup"><span data-stu-id="5696e-117">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="5696e-118">Для этого создайте **средство извлечения**, чтобы добавить его в свою модель.</span><span class="sxs-lookup"><span data-stu-id="5696e-118">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="5696e-119">См. статью [Создание средства извлечения](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="5696e-119">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="5696e-120">Присвоение имени модели</span><span class="sxs-lookup"><span data-stu-id="5696e-120">Name your model</span></span>

<span data-ttu-id="5696e-121">Первым шагом при создании модели является присвоение ей имени.</span><span class="sxs-lookup"><span data-stu-id="5696e-121">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="5696e-122">В центре контента выберите **Создать**, а затем —**Создать модель**.</span><span class="sxs-lookup"><span data-stu-id="5696e-122">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="5696e-123">В области **Новая модель осмысления документации** в поле **Имя** введите имя модели.</span><span class="sxs-lookup"><span data-stu-id="5696e-123">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="5696e-124">Например, если вы хотите определить документы для продления контракта, можно назвать модель *Продление контракта*.</span><span class="sxs-lookup"><span data-stu-id="5696e-124">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="5696e-125">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="5696e-125">Choose **Create**.</span></span> <span data-ttu-id="5696e-126">В результате будет создана домашняя страница для модели.</span><span class="sxs-lookup"><span data-stu-id="5696e-126">This creates a home page for the model.</span></span></br>

    ![Домашняя страница модели классификатора](../media/content-understanding/model-home.png)

<span data-ttu-id="5696e-128">При создании модели вы также создаете новый тип контента сайта.</span><span class="sxs-lookup"><span data-stu-id="5696e-128">When you create a model, you are also creating a new site content type.</span></span> <span data-ttu-id="5696e-129">Тип контента представляет категорию документов с общими характеристиками и коллекцией столбцов или свойств метаданных для определенного контента.</span><span class="sxs-lookup"><span data-stu-id="5696e-129">A content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="5696e-130">Управление типами контента SharePoint осуществляется с помощью [коллекции типов контента](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span><span class="sxs-lookup"><span data-stu-id="5696e-130">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="5696e-131">В этом примере при создании модели вы создаете новый тип контента *Продление контракта*.</span><span class="sxs-lookup"><span data-stu-id="5696e-131">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="5696e-132">Выберите **Дополнительные параметры**, если хотите сопоставить эту модель с существующим корпоративным типом контента в коллекции типов контента SharePoint, чтобы использовать его схему.</span><span class="sxs-lookup"><span data-stu-id="5696e-132">Select **Advanced settings** if you want to map this model to an existing enterprise content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="5696e-133">Корпоративные типы контента хранятся в центре типов контента в Центре администрирования SharePoint и являются общими для всех сайтов в клиенте.</span><span class="sxs-lookup"><span data-stu-id="5696e-133">Enterprise content types are stored in the Content Type Hub in the SharePoint admin center and are syndicated to all sites in the tenant.</span></span> <span data-ttu-id="5696e-134">Обратите внимание, что хотя вы можете применять существующий тип контента для использования его схемы с целью упрощения определения и классификации, вам по-прежнему требуется обучить свою модель для извлечения информации из файлов, которые она определяет.</span><span class="sxs-lookup"><span data-stu-id="5696e-134">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Дополнительные параметры](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="5696e-136">Добавление примеров файлов</span><span class="sxs-lookup"><span data-stu-id="5696e-136">Add your example files</span></span>

<span data-ttu-id="5696e-137">На домашней странице модели добавьте примеры файлов, которые потребуются, чтобы обучить модель определять ваш тип документа.</span><span class="sxs-lookup"><span data-stu-id="5696e-137">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="5696e-138">Вам следует использовать одинаковые файлы как для классификатора, так и для [обучения средства извлечения](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="5696e-138">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="5696e-139">Вы всегда можете добавить другие файлы позже, но обычно добавляется полный набор примеров файлов.</span><span class="sxs-lookup"><span data-stu-id="5696e-139">You always have the option to add more later, but typically you add a full set of example files.</span></span> <span data-ttu-id="5696e-140">Пометьте некоторые из них, чтобы обучить свою модель, и протестируйте остальные файлы без меток, чтобы оценить пригодность модели.</span><span class="sxs-lookup"><span data-stu-id="5696e-140">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="5696e-141">В качестве обучающего набора следует использовать положительные и отрицательные примеры:</span><span class="sxs-lookup"><span data-stu-id="5696e-141">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="5696e-142">Положительный пример: документы, представляющие тип документа.</span><span class="sxs-lookup"><span data-stu-id="5696e-142">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="5696e-143">Они содержат строки и сведения, которые всегда будут присутствовать в этом типе документа.</span><span class="sxs-lookup"><span data-stu-id="5696e-143">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="5696e-144">Отрицательные примеры: любой другой документ, не представляющий тип документа, который вы хотите классифицировать.</span><span class="sxs-lookup"><span data-stu-id="5696e-144">Negative example: Any other document that does not represent the document you want to classify.</span></span> 

<span data-ttu-id="5696e-145">Используйте не менее пяти положительных примеров и хотя бы один отрицательный пример, чтобы обучить свою модель.</span><span class="sxs-lookup"><span data-stu-id="5696e-145">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="5696e-146">Желательно создать дополнительные примеры, чтобы протестировать свою модель после обучения.</span><span class="sxs-lookup"><span data-stu-id="5696e-146">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="5696e-147">Добавление примеров файлов:</span><span class="sxs-lookup"><span data-stu-id="5696e-147">To add example files:</span></span>

1. <span data-ttu-id="5696e-148">На домашней странице модели на плитке **Добавить примеры файлов** щелкните **Добавить файлы**.</span><span class="sxs-lookup"><span data-stu-id="5696e-148">On the model home page, in the **Add example files** tile, click **Add files**.</span></span>
2. <span data-ttu-id="5696e-149">На странице **Выберите примеры файлов для модели** выберите примеры файлов из библиотеки учебных файлов в центре контента.</span><span class="sxs-lookup"><span data-stu-id="5696e-149">On the **Select example files for your model** page, select your example files from the Training files library in the content center.</span></span> <span data-ttu-id="5696e-150">Если вы еще не отправили их туда, щелкните **Отправить**, чтобы скопировать их в библиотеку учебных файлов.</span><span class="sxs-lookup"><span data-stu-id="5696e-150">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to copy them to the Training files library.</span></span>
3. <span data-ttu-id="5696e-151">Выбрав примеры файлов для обучения модели, щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="5696e-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Выбор примеров файлов](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="5696e-153">Пометка примеров файлов</span><span class="sxs-lookup"><span data-stu-id="5696e-153">Label your example files</span></span>

<span data-ttu-id="5696e-154">После добавления примеров файлов вам требуется пометить их в качестве положительных или отрицательных примеров.</span><span class="sxs-lookup"><span data-stu-id="5696e-154">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="5696e-155">На домашней странице модели на плитке **Классификация файлов и запуск обучения** щелкните **Обучить классификатор**.</span><span class="sxs-lookup"><span data-stu-id="5696e-155">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="5696e-156">Отобразится страница присвоения метки со списком ваших примеров файлов и первым файлом, отображаемым в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="5696e-156">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="5696e-157">В средстве просмотра поверх первого примера файла вы увидите текст с вопросом, является ли файл примером для созданной вами модели.</span><span class="sxs-lookup"><span data-stu-id="5696e-157">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="5696e-158">Если это положительный пример выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="5696e-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="5696e-159">Если это отрицательный пример выберите **Нет**.</span><span class="sxs-lookup"><span data-stu-id="5696e-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="5696e-160">В списке **Примеры с метками** слева выберите дополнительные файлы, которые нужно использовать в качестве примеров, и пометьте их.</span><span class="sxs-lookup"><span data-stu-id="5696e-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Домашняя страница классификатора](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="5696e-162">Пометьте как минимум пять положительных примеров.</span><span class="sxs-lookup"><span data-stu-id="5696e-162">Label at least five positive examples.</span></span> <span data-ttu-id="5696e-163">Вы также должны пометить хотя бы один отрицательный пример.</span><span class="sxs-lookup"><span data-stu-id="5696e-163">You must also label at least one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="5696e-164">Создание объяснения</span><span class="sxs-lookup"><span data-stu-id="5696e-164">Create an explanation</span></span>

<span data-ttu-id="5696e-165">Следующее действие — создание объяснения на странице обучения.</span><span class="sxs-lookup"><span data-stu-id="5696e-165">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="5696e-166">Объяснение помогает модели понять, как распознать документ.</span><span class="sxs-lookup"><span data-stu-id="5696e-166">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="5696e-167">Например, документы для продления контракта всегда содержат текстовую строку *Запрос дополнительного раскрытия информации*.</span><span class="sxs-lookup"><span data-stu-id="5696e-167">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="5696e-168">При использовании со средствами извлечения объяснение определяет строку, которую нужно извлечь из документа.</span><span class="sxs-lookup"><span data-stu-id="5696e-168">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="5696e-169">Создание объяснения:</span><span class="sxs-lookup"><span data-stu-id="5696e-169">To create an explanation:</span></span>

1. <span data-ttu-id="5696e-170">На домашней странице модели откройте вкладку **Обучение**, чтобы перейти на страницу обучения.</span><span class="sxs-lookup"><span data-stu-id="5696e-170">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="5696e-171">На странице обучения в разделе **Подготовленные файлы** вы увидите список примеров файлов, которые вы пометили ранее.</span><span class="sxs-lookup"><span data-stu-id="5696e-171">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="5696e-172">Выберите один из положительных файлов из списка, и он отобразится в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="5696e-172">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="5696e-173">В разделе объяснения выберите **Создать**, а затем — **Пустое**.</span><span class="sxs-lookup"><span data-stu-id="5696e-173">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="5696e-174">На странице **Создание объяснения**:</span><span class="sxs-lookup"><span data-stu-id="5696e-174">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="5696e-175">а.</span><span class="sxs-lookup"><span data-stu-id="5696e-175">a.</span></span> <span data-ttu-id="5696e-176">Введите **имя** (например, "блок раскрытия информации").</span><span class="sxs-lookup"><span data-stu-id="5696e-176">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="5696e-177">б.</span><span class="sxs-lookup"><span data-stu-id="5696e-177">b.</span></span> <span data-ttu-id="5696e-178">Выберите **Тип**.</span><span class="sxs-lookup"><span data-stu-id="5696e-178">Select the **Type**.</span></span> <span data-ttu-id="5696e-179">В качестве примера выберите **Список фраз**, так как вы добавляете текстовую строку.</span><span class="sxs-lookup"><span data-stu-id="5696e-179">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="5696e-180">в.</span><span class="sxs-lookup"><span data-stu-id="5696e-180">c.</span></span> <span data-ttu-id="5696e-181">В поле **Введите здесь** введите строку.</span><span class="sxs-lookup"><span data-stu-id="5696e-181">In the **Type here** box, type the string.</span></span> <span data-ttu-id="5696e-182">В качестве примера добавьте "Запрос дополнительного раскрытия информации".</span><span class="sxs-lookup"><span data-stu-id="5696e-182">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="5696e-183">Вы можете выбрать **С учетом регистра**, если требуется учитывать регистр строки.</span><span class="sxs-lookup"><span data-stu-id="5696e-183">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="5696e-184">г.</span><span class="sxs-lookup"><span data-stu-id="5696e-184">d.</span></span> <span data-ttu-id="5696e-185">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5696e-185">Click **Save**.</span></span>

    ![Создание объяснения](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="5696e-187">Теперь модель проверяет, является ли созданное объяснение достаточно хорошим, чтобы правильно определить остальные помеченные примеры файлов в качестве положительных и отрицательных примеров.</span><span class="sxs-lookup"><span data-stu-id="5696e-187">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="5696e-188">В разделе подготовленных файлов просмотрите столбец **Оценка** после завершения обучения, чтобы увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="5696e-188">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="5696e-189">Файлы имеют значение **Соответствие**, если созданные вами объяснения были достаточными, чтобы сопоставить помеченные файлы с положительными или отрицательными примерами.</span><span class="sxs-lookup"><span data-stu-id="5696e-189">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Значение соответствия](../media/content-understanding/match.png) 

<span data-ttu-id="5696e-191">Если вы видите значение **Несоответствие** для помеченных файлов, вам может потребоваться создать дополнительное объяснение, чтобы предоставить модели больше сведений для определения типа документа.</span><span class="sxs-lookup"><span data-stu-id="5696e-191">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="5696e-192">В этом случае щелкните файл, чтобы получить дополнительные сведения о причине несоответствия.</span><span class="sxs-lookup"><span data-stu-id="5696e-192">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="5696e-193">Тестирование модели</span><span class="sxs-lookup"><span data-stu-id="5696e-193">Test your model</span></span>

<span data-ttu-id="5696e-194">Если вы получили сообщение о соответствии помеченных примеров файлов, вы можете протестировать свою модель на оставшихся примерах файлов без меток, которые еще не использовались в модели.</span><span class="sxs-lookup"><span data-stu-id="5696e-194">If you received a match on your labeled sample files, you can now  test your model on your remaining unlabeled example files that the model has not seen before.</span></span>  <span data-ttu-id="5696e-195">Это необязательный, но полезный шаг для оценки "пригодности" или готовности модели перед ее использованием путем тестирования ее на файлах, которые модель ранее не видела.</span><span class="sxs-lookup"><span data-stu-id="5696e-195">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="5696e-196">На домашней странице модели откройте вкладку **Тестирование**. Это запустит модель на примерах файлов без меток.</span><span class="sxs-lookup"><span data-stu-id="5696e-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="5696e-197">В списке **Тестовые файлы** отображаются ваши примеры файлов и указывается прогноз модели в их отношении: положительные или отрицательные.</span><span class="sxs-lookup"><span data-stu-id="5696e-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="5696e-198">Используйте эти сведения, чтобы определить эффективность классификатора в определении ваших документов.</span><span class="sxs-lookup"><span data-stu-id="5696e-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Тестирование файлов без метки](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="5696e-200">См. также</span><span class="sxs-lookup"><span data-stu-id="5696e-200">See Also</span></span>
[<span data-ttu-id="5696e-201">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="5696e-201">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="5696e-202">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="5696e-202">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="5696e-203">Типы объяснения</span><span class="sxs-lookup"><span data-stu-id="5696e-203">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="5696e-204">Применение модели</span><span class="sxs-lookup"><span data-stu-id="5696e-204">Apply a model</span></span>](apply-a-model.md) 
