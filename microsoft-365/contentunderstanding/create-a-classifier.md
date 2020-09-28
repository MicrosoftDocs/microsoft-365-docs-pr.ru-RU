---
title: Создание классификатора
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как создать классификатор
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294906"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="8aa99-103">Создание классификатора в Microsoft SharePoint Синтекс</span><span class="sxs-lookup"><span data-stu-id="8aa99-103">Create a classifier in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="8aa99-104">Содержимое этой статьи предназначено для проекта Кортекс Private Preview.</span><span class="sxs-lookup"><span data-stu-id="8aa99-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="8aa99-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="8aa99-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="8aa99-106">Классификатор — это тип модели, который можно использовать для автоматизации идентификации и классификации типов документов.</span><span class="sxs-lookup"><span data-stu-id="8aa99-106">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="8aa99-107">Например, вы можете определить все документы для *продления контрактов* , добавленные в библиотеку документов, например, показанные на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="8aa99-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![Документ по обновлению контракта](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="8aa99-109">Создание классификатора позволяет создать новый [тип контента SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) , который будет связан с моделью.</span><span class="sxs-lookup"><span data-stu-id="8aa99-109">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="8aa99-110">При создании классификатора необходимо создать *объяснения* для определения модели.</span><span class="sxs-lookup"><span data-stu-id="8aa99-110">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="8aa99-111">Это позволяет заметок о распространенных данных, которые будут ожидать согласованного поиска этого типа документа.</span><span class="sxs-lookup"><span data-stu-id="8aa99-111">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="8aa99-112">Используйте примеры типа документа ("example Files"), чтобы "обучить" модель для идентификации файлов с одинаковым типом контента.</span><span class="sxs-lookup"><span data-stu-id="8aa99-112">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="8aa99-113">Чтобы создать классификатор, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="8aa99-113">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="8aa99-114">Назовите модель.</span><span class="sxs-lookup"><span data-stu-id="8aa99-114">Name your model.</span></span>
2. <span data-ttu-id="8aa99-115">Добавьте файлы примеров.</span><span class="sxs-lookup"><span data-stu-id="8aa99-115">Add your example files.</span></span>
3. <span data-ttu-id="8aa99-116">Пометьте примеры файлов.</span><span class="sxs-lookup"><span data-stu-id="8aa99-116">Label your example files.</span></span>
4. <span data-ttu-id="8aa99-117">Создание объяснения.</span><span class="sxs-lookup"><span data-stu-id="8aa99-117">Create an explanation.</span></span>
5. <span data-ttu-id="8aa99-118">Протестируйте модель.</span><span class="sxs-lookup"><span data-stu-id="8aa99-118">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="8aa99-119">Пока модель использует классификатор для определения и классификации типов документов, вы также можете получить определенные фрагменты данных из каждого файла, идентифицируемого моделью.</span><span class="sxs-lookup"><span data-stu-id="8aa99-119">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="8aa99-120">Для этого создайте средство **извлечения** , которое будет добавлено в модель.</span><span class="sxs-lookup"><span data-stu-id="8aa99-120">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="8aa99-121">Ознакомьтесь [со](create-an-extractor.md)статьей Создание средства извлечения.</span><span class="sxs-lookup"><span data-stu-id="8aa99-121">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="8aa99-122">Назовите модель</span><span class="sxs-lookup"><span data-stu-id="8aa99-122">Name your model</span></span>

<span data-ttu-id="8aa99-123">Первым этапом создания модели является присвоение ему имени:</span><span class="sxs-lookup"><span data-stu-id="8aa99-123">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="8aa99-124">В центре управления контентом выберите **создать**, а затем **Создайте модель**.</span><span class="sxs-lookup"><span data-stu-id="8aa99-124">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="8aa99-125">В области **модель нового документа "Общие сведения** " в поле **имя** введите имя модели.</span><span class="sxs-lookup"><span data-stu-id="8aa99-125">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="8aa99-126">Например, если вы хотите определить документы для продления контрактов, можно назвать *Обновление контракта*модели.</span><span class="sxs-lookup"><span data-stu-id="8aa99-126">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="8aa99-127">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8aa99-127">Choose **Create**.</span></span> <span data-ttu-id="8aa99-128">При этом будет создана домашняя страница модели.</span><span class="sxs-lookup"><span data-stu-id="8aa99-128">This creates a home page for the model.</span></span></br>

    ![Домашняя страница модели классификатора](../media/content-understanding/model-home.png)

<span data-ttu-id="8aa99-130">При создании модели также создается новый тип контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8aa99-130">When you create a model, you are also creating a new SharePoint content type.</span></span> <span data-ttu-id="8aa99-131">Тип контента SharePoint представляет категорию документов, имеющих общие характеристики и совместное использование коллекции столбцов или свойств метаданных для конкретного содержимого.</span><span class="sxs-lookup"><span data-stu-id="8aa99-131">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="8aa99-132">Управление типами контента SharePoint осуществляется с помощью [коллекции типов контента](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span><span class="sxs-lookup"><span data-stu-id="8aa99-132">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="8aa99-133">В этом примере при создании модели создается новый тип контента *обновления контракта* .</span><span class="sxs-lookup"><span data-stu-id="8aa99-133">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="8aa99-134">Выберите **Дополнительные параметры** , если вы хотите сопоставить эту модель с существующим типом контента в коллекции типов контента SharePoint, чтобы использовать ее схему.</span><span class="sxs-lookup"><span data-stu-id="8aa99-134">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="8aa99-135">Обратите внимание, что хотя вы можете использовать существующий тип контента для использования его схемы, чтобы упростить идентификацию и классификацию, вам по-прежнему нужно провести обучение модели, чтобы извлечь информацию из файлов, которые она идентифицирует.</span><span class="sxs-lookup"><span data-stu-id="8aa99-135">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![Дополнительные параметры](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="8aa99-137">Добавление файлов примеров</span><span class="sxs-lookup"><span data-stu-id="8aa99-137">Add your example files</span></span>

<span data-ttu-id="8aa99-138">На домашней странице модели добавьте файлы примеров, которые понадобятся вам при обучении модели, чтобы определить тип документа.</span><span class="sxs-lookup"><span data-stu-id="8aa99-138">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="8aa99-139">Вы должны использовать одни и те же файлы для обучения классификатора и [извлечения](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="8aa99-139">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="8aa99-140">Вы всегда можете добавить более позднее, но обычно вы добавляете полный набор образцов файлов.</span><span class="sxs-lookup"><span data-stu-id="8aa99-140">You always have the option to add more later, but typically you add a full set of sample files.</span></span> <span data-ttu-id="8aa99-141">Пометьте, что нужно обучить модель, и протестируйте оставшиеся непомеченные, чтобы оценить фитнес модели.</span><span class="sxs-lookup"><span data-stu-id="8aa99-141">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="8aa99-142">Для вашего учебного набора вы хотите использовать как положительные, так и отрицательные примеры:</span><span class="sxs-lookup"><span data-stu-id="8aa99-142">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="8aa99-143">Положительный пример: документы, представляющие тип документа.</span><span class="sxs-lookup"><span data-stu-id="8aa99-143">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="8aa99-144">Они содержат строки и сведения, которые всегда будут находиться в документе этого типа.</span><span class="sxs-lookup"><span data-stu-id="8aa99-144">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="8aa99-145">Негативный пример: документы, не представляющие тип документа.</span><span class="sxs-lookup"><span data-stu-id="8aa99-145">Negative example: Documents that do not represent the document type.</span></span> <span data-ttu-id="8aa99-146">В них отсутствуют строки и сведения, которые должны присутствовать в документе этого типа.</span><span class="sxs-lookup"><span data-stu-id="8aa99-146">These are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="8aa99-147">Обязательно используйте по крайней мере пять положительных примеров и по крайней мере один отрицательный пример для обучения модели.</span><span class="sxs-lookup"><span data-stu-id="8aa99-147">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="8aa99-148">Вы хотите создать дополнительные единицы, чтобы протестировать модель после учебного процесса.</span><span class="sxs-lookup"><span data-stu-id="8aa99-148">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="8aa99-149">Добавление файлов примеров:</span><span class="sxs-lookup"><span data-stu-id="8aa99-149">To add sample files:</span></span>

1. <span data-ttu-id="8aa99-150">На домашней странице модели в плитке **Библиотека образцов** нажмите кнопку **Добавить файлы**.</span><span class="sxs-lookup"><span data-stu-id="8aa99-150">From the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="8aa99-151">На странице **Выбор примеров файлов для модели** выберите файлы примера из библиотеки образцов файлов в центре управления контентом.</span><span class="sxs-lookup"><span data-stu-id="8aa99-151">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="8aa99-152">Если вы еще не отправляли их там, нажмите кнопку **Отправить** , чтобы переместить их в библиотеку образцов файлов.</span><span class="sxs-lookup"><span data-stu-id="8aa99-152">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="8aa99-153">Выбрав файлы примеров, которые необходимо использовать для обучения модели, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="8aa99-153">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Выбор файлов примеров](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="8aa99-155">Добавление меток к примерам файлов</span><span class="sxs-lookup"><span data-stu-id="8aa99-155">Label your example files</span></span>

<span data-ttu-id="8aa99-156">После добавления файлов примеров их необходимо добавить в качестве положительного или отрицательного примера.</span><span class="sxs-lookup"><span data-stu-id="8aa99-156">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="8aa99-157">На домашней странице модели в разделе **Классификация файлов и запуск обучающих материалов** нажмите кнопку **обучение классификатора**.</span><span class="sxs-lookup"><span data-stu-id="8aa99-157">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="8aa99-158">Откроется страница метки со списком файлов с примерами, где первый файл виден в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="8aa99-158">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="8aa99-159">В средстве просмотра, расположенном в верхней части первого файла примера, вы увидите вопрос, является ли он примером модели, которую вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="8aa99-159">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="8aa99-160">Если это положительный пример, нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="8aa99-160">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="8aa99-161">Если это отрицательный пример, выберите **нет**.</span><span class="sxs-lookup"><span data-stu-id="8aa99-161">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="8aa99-162">В списке **помеченных примеров** слева выберите дополнительные файлы, которые нужно использовать в качестве примеров, и пометьте их.</span><span class="sxs-lookup"><span data-stu-id="8aa99-162">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![Главная страница классификатора](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="8aa99-164">Подпись по крайней мере из пяти положительных примеров и один отрицательный пример.</span><span class="sxs-lookup"><span data-stu-id="8aa99-164">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="8aa99-165">Создание объяснения</span><span class="sxs-lookup"><span data-stu-id="8aa99-165">Create an explanation</span></span>

<span data-ttu-id="8aa99-166">Следующий шаг предназначен для создания объяснения на странице "обучение".</span><span class="sxs-lookup"><span data-stu-id="8aa99-166">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="8aa99-167">Объяснение помогает модели понять, как распознать документ.</span><span class="sxs-lookup"><span data-stu-id="8aa99-167">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="8aa99-168">Например, документы для продления контракта всегда содержат *запрос на дополнительную строку с раскрытием* текста.</span><span class="sxs-lookup"><span data-stu-id="8aa99-168">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="8aa99-169">При использовании с извлечением объяснение определяет строку, которую необходимо извлечь из документа.</span><span class="sxs-lookup"><span data-stu-id="8aa99-169">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="8aa99-170">Чтобы создать объяснение:</span><span class="sxs-lookup"><span data-stu-id="8aa99-170">To create an explanation:</span></span>

1. <span data-ttu-id="8aa99-171">На домашней странице модели выберите вкладку **обучение** , чтобы перейти на страницу обучение.</span><span class="sxs-lookup"><span data-stu-id="8aa99-171">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="8aa99-172">На странице "обучение" в разделе " **подготовленные файлы** " вы увидите список образцов файлов, помеченных ранее.</span><span class="sxs-lookup"><span data-stu-id="8aa99-172">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="8aa99-173">Выберите один из положительных файлов в списке и отобразится в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="8aa99-173">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="8aa99-174">В разделе объяснение выберите **создать** , а затем — **пустое**.</span><span class="sxs-lookup"><span data-stu-id="8aa99-174">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="8aa99-175">На странице **Создание объяснения** :</span><span class="sxs-lookup"><span data-stu-id="8aa99-175">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="8aa99-176">а.</span><span class="sxs-lookup"><span data-stu-id="8aa99-176">a.</span></span> <span data-ttu-id="8aa99-177">Введите **имя** (например, "блок раскрытия").</span><span class="sxs-lookup"><span data-stu-id="8aa99-177">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="8aa99-178">б.</span><span class="sxs-lookup"><span data-stu-id="8aa99-178">b.</span></span> <span data-ttu-id="8aa99-179">Выберите **тип**.</span><span class="sxs-lookup"><span data-stu-id="8aa99-179">Select the **Type**.</span></span> <span data-ttu-id="8aa99-180">Для примера выберите пункт **список фраз**, так как вы добавите текстовую строку.</span><span class="sxs-lookup"><span data-stu-id="8aa99-180">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="8aa99-181">в.</span><span class="sxs-lookup"><span data-stu-id="8aa99-181">c.</span></span> <span data-ttu-id="8aa99-182">В поле **Введите здесь** введите строку.</span><span class="sxs-lookup"><span data-stu-id="8aa99-182">In the **Type here** box, type the string.</span></span> <span data-ttu-id="8aa99-183">Для примера добавьте "запрос на дополнительную раскрытие".</span><span class="sxs-lookup"><span data-stu-id="8aa99-183">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="8aa99-184">Вы можете выбрать параметр **с учетом регистра** , если строка должна учитывать регистр.</span><span class="sxs-lookup"><span data-stu-id="8aa99-184">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="8aa99-185">г.</span><span class="sxs-lookup"><span data-stu-id="8aa99-185">d.</span></span> <span data-ttu-id="8aa99-186">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="8aa99-186">Click **Save**.</span></span>

    ![Создание объяснения](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="8aa99-188">Теперь модель проверяет, было ли созданное вами объяснение достаточно хорошо, чтобы правильно определить оставшиеся помеченные файлы примеров, как положительные и отрицательные примеры.</span><span class="sxs-lookup"><span data-stu-id="8aa99-188">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="8aa99-189">В разделе ученые файлы проверьте столбец **Оценка** после завершения обучения, чтобы увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="8aa99-189">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="8aa99-190">В файлах отображается значение " **совпадает**", если созданные вами объяснения были достаточно, чтобы соблюдались как положительные, так и отрицательные.</span><span class="sxs-lookup"><span data-stu-id="8aa99-190">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Значение параметра ПОИСКПОЗ](../media/content-understanding/match.png) 

<span data-ttu-id="8aa99-192">Если вы получаете **несовпадение** с помеченными файлами, вам может потребоваться создать дополнительное пояснение, чтобы предоставить модели дополнительные сведения для определения типа документа.</span><span class="sxs-lookup"><span data-stu-id="8aa99-192">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="8aa99-193">Если это произойдет, щелкните файл, чтобы получить дополнительные сведения о причине несоответствия.</span><span class="sxs-lookup"><span data-stu-id="8aa99-193">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="8aa99-194">Тестирование модели</span><span class="sxs-lookup"><span data-stu-id="8aa99-194">Test your model</span></span>

<span data-ttu-id="8aa99-195">Если вы получили соответствующее помеченные файлы примеров, теперь вы можете проверить модель на оставшихся файлов примеров без метки.</span><span class="sxs-lookup"><span data-stu-id="8aa99-195">If you received a match on your labeled sample files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="8aa99-196">На домашней странице модели перейдите на вкладку **тест** .  В этом примере выполняется модель для файлов примеров без метки.</span><span class="sxs-lookup"><span data-stu-id="8aa99-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="8aa99-197">В списке **тестовые файлы** показаны примеры файлов и показывается, если модель прогнозируется как положительное или отрицательное.</span><span class="sxs-lookup"><span data-stu-id="8aa99-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="8aa99-198">Используйте эти сведения, чтобы определить эффективность классификатора в определении ваших документов.</span><span class="sxs-lookup"><span data-stu-id="8aa99-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Проверка непомеченных файлов](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="8aa99-200">См. также</span><span class="sxs-lookup"><span data-stu-id="8aa99-200">See Also</span></span>
[<span data-ttu-id="8aa99-201">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="8aa99-201">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="8aa99-202">Общие сведения о документе</span><span class="sxs-lookup"><span data-stu-id="8aa99-202">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="8aa99-203">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="8aa99-203">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="8aa99-204">Применение модели</span><span class="sxs-lookup"><span data-stu-id="8aa99-204">Apply a model</span></span>](apply-a-model.md) 
