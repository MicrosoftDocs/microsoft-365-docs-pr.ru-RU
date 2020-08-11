---
title: Создание классификатора (Предварительная версия)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как создать классификатор
ms.openlocfilehash: 088770ace8914b583b184c78c3ce110d9d68b4c7
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612612"
---
# <a name="create-a-classifier-preview"></a><span data-ttu-id="906fd-103">Создание классификатора (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="906fd-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="906fd-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="906fd-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="906fd-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="906fd-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="906fd-106">Классификатор — это тип модели, автоматизирующий идентификацию и классификацию типа документа.</span><span class="sxs-lookup"><span data-stu-id="906fd-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="906fd-107">Например, вам может потребоваться определить все документы по *обновлению контрактов* , добавленные в библиотеку документов, например:</span><span class="sxs-lookup"><span data-stu-id="906fd-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![Документ по обновлению контракта](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="906fd-109">При создании классификатора будет создан новый [тип контента SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) , который будет связан с моделью.</span><span class="sxs-lookup"><span data-stu-id="906fd-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="906fd-110">При создании классификатора необходимо создать *объяснения* , которые помогут определить модель, указав общие данные, которые будут ожидать согласования для этого типа документа.</span><span class="sxs-lookup"><span data-stu-id="906fd-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="906fd-111">Вы используете примеры типа документа ("example Files"), чтобы помочь "обучить" модель для определения файлов с одинаковым типом контента.</span><span class="sxs-lookup"><span data-stu-id="906fd-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="906fd-112">Чтобы создать классификатор, необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="906fd-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="906fd-113">Назовите модель</span><span class="sxs-lookup"><span data-stu-id="906fd-113">Name your model</span></span>
2. <span data-ttu-id="906fd-114">Добавление файлов примеров</span><span class="sxs-lookup"><span data-stu-id="906fd-114">Add your example files</span></span>
3. <span data-ttu-id="906fd-115">Добавление меток к примерам файлов</span><span class="sxs-lookup"><span data-stu-id="906fd-115">Label your example files</span></span>
4. <span data-ttu-id="906fd-116">Создание объяснения</span><span class="sxs-lookup"><span data-stu-id="906fd-116">Create an explanation</span></span>
5. <span data-ttu-id="906fd-117">Тестирование модели</span><span class="sxs-lookup"><span data-stu-id="906fd-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="906fd-118">В то время как классификатор использует модель для определения и классификации типов документов, можно также запросить определенные части информации из каждого файла, идентифицируемого моделью.</span><span class="sxs-lookup"><span data-stu-id="906fd-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="906fd-119">Для этого необходимо создать средство **извлечения** для модели, которое описывается в статье [Создание средства извлечения](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="906fd-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="906fd-120">Назовите модель</span><span class="sxs-lookup"><span data-stu-id="906fd-120">Name your model</span></span>

<span data-ttu-id="906fd-121">Первым шагом является создание модели в центре контента, указав ее имя:</span><span class="sxs-lookup"><span data-stu-id="906fd-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="906fd-122">В центре управления контентом нажмите кнопку **создать**, а затем выберите команду **создать модель**.</span><span class="sxs-lookup"><span data-stu-id="906fd-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="906fd-123">В области **модель нового документа "Общие сведения** " в поле **имя** введите имя модели.</span><span class="sxs-lookup"><span data-stu-id="906fd-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="906fd-124">Для нашего примера, если мы хотим определить документы для продления контрактов, мы можем назвать эту модель *продление контракта*.</span><span class="sxs-lookup"><span data-stu-id="906fd-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="906fd-125">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="906fd-125">Click **Create**.</span></span> <span data-ttu-id="906fd-126">При этом будет создана домашняя страница модели.</span><span class="sxs-lookup"><span data-stu-id="906fd-126">This will create a home page for the model.</span></span></br>

    ![Домашняя страница модели классификатора](../media/content-understanding/model-home.png)

<span data-ttu-id="906fd-128">При создании модели создается новый тип контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="906fd-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="906fd-129">Тип контента SharePoint представляет категорию документов, имеющих общие характеристики и совместное использование коллекции столбцов или свойств метаданных для конкретного содержимого.</span><span class="sxs-lookup"><span data-stu-id="906fd-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="906fd-130">Управление типами контента SharePoint осуществляется с помощью [коллекции типов контента]().</span><span class="sxs-lookup"><span data-stu-id="906fd-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="906fd-131">Для нашего примера при создании модели мы создадим новый тип контента " *Обновление контракта* ".</span><span class="sxs-lookup"><span data-stu-id="906fd-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="906fd-132">Выберите **Дополнительные параметры** , если вы хотите сопоставить эту модель с существующим типом контента в коллекции типов контента SharePoint, чтобы использовать ее схему.</span><span class="sxs-lookup"><span data-stu-id="906fd-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="906fd-133">Обратите внимание, что хотя вы можете использовать существующий тип контента для использования его схемы, чтобы упростить идентификацию и классификацию, вам все равно потребуется научить модель для извлечения информации из файлов, которые она идентифицирует.</span><span class="sxs-lookup"><span data-stu-id="906fd-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![Дополнительные параметры](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="906fd-135">Добавление файлов примеров</span><span class="sxs-lookup"><span data-stu-id="906fd-135">Add your example files</span></span>

<span data-ttu-id="906fd-136">На домашней странице модели можно добавить файлы примеров, которые помогут вам обучить модель для определения типа документа.</span><span class="sxs-lookup"><span data-stu-id="906fd-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="906fd-137">Эти же файлы должны использоваться для обучения классификатора и [извлечения](create-an-extractor.md).</span><span class="sxs-lookup"><span data-stu-id="906fd-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="906fd-138">Вы всегда можете добавить более позднее, но обычно необходимо добавить полный набор файлов примеров.</span><span class="sxs-lookup"><span data-stu-id="906fd-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="906fd-139">Вы увидите метку для обучения модели и протестируйте оставшиеся непомеченные, чтобы оценить фитнес модели.</span><span class="sxs-lookup"><span data-stu-id="906fd-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="906fd-140">Для вашего учебного набора вам потребуется использовать как положительные, так и отрицательные примеры:</span><span class="sxs-lookup"><span data-stu-id="906fd-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="906fd-141">Положительный пример: документы, представляющие тип документа.</span><span class="sxs-lookup"><span data-stu-id="906fd-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="906fd-142">Они содержат строки и сведения, которые всегда будут находиться в документе этого типа.</span><span class="sxs-lookup"><span data-stu-id="906fd-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="906fd-143">Негативный пример: документы, не представляющие тип документа.</span><span class="sxs-lookup"><span data-stu-id="906fd-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="906fd-144">В них отсутствуют строки и сведения, которые должны присутствовать в документе этого типа.</span><span class="sxs-lookup"><span data-stu-id="906fd-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="906fd-145">Для обучения модели необходимо использовать по крайней мере пять положительных примеров и один отрицательный пример.</span><span class="sxs-lookup"><span data-stu-id="906fd-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="906fd-146">Вам потребуются дополнительные шаблоны для тестирования модели после обучения.</span><span class="sxs-lookup"><span data-stu-id="906fd-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="906fd-147">Добавление файлов примеров:</span><span class="sxs-lookup"><span data-stu-id="906fd-147">To add sample files:</span></span>

1. <span data-ttu-id="906fd-148">На домашней странице модели в плитке **Библиотека образца построения** щелкните **Добавить файлы**.</span><span class="sxs-lookup"><span data-stu-id="906fd-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="906fd-149">На странице **Выбор примеров файлов для модели** выберите файлы примера из библиотеки образцов файлов в центре управления контентом.</span><span class="sxs-lookup"><span data-stu-id="906fd-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="906fd-150">Если вы еще не отправляли их там, вы можете отправить их сейчас, нажав кнопку **Отправить** , чтобы переместить их в библиотеку образцов файлов.</span><span class="sxs-lookup"><span data-stu-id="906fd-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="906fd-151">Выбрав файлы примеров, которые необходимо использовать для обучения модели, нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="906fd-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![Выбор файлов примеров](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="906fd-153">Добавление меток к примерам файлов</span><span class="sxs-lookup"><span data-stu-id="906fd-153">Label your example files</span></span>

<span data-ttu-id="906fd-154">После добавления файлов примеров необходимо добавить их в качестве положительных или отрицательных примеров.</span><span class="sxs-lookup"><span data-stu-id="906fd-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="906fd-155">На домашней странице модели в разделе **Классификация файлов и запуск учебной** плитки щелкните элемент **классификатор**.</span><span class="sxs-lookup"><span data-stu-id="906fd-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="906fd-156">При этом отобразится страница метки со списком файлов с примерами, где первый файл будет виден в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="906fd-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="906fd-157">В средстве просмотра, расположенном в верхней части первого файла примера, вы увидите сообщение с вопросом, является ли этот файл примером модели, которую вы только что создали.</span><span class="sxs-lookup"><span data-stu-id="906fd-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="906fd-158">Если это положительный пример, нажмите **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="906fd-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="906fd-159">Если это отрицательный пример, выберите **нет**.</span><span class="sxs-lookup"><span data-stu-id="906fd-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="906fd-160">В списке **примеры с заголовками** слева выберите дополнительные файлы, которые необходимо использовать в качестве примеров, а также пометьте их.</span><span class="sxs-lookup"><span data-stu-id="906fd-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![Домашняя страница модели классификатора](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="906fd-162">Подпись по крайней мере из пяти положительных примеров и один отрицательный пример.</span><span class="sxs-lookup"><span data-stu-id="906fd-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="906fd-163">Создание объяснения</span><span class="sxs-lookup"><span data-stu-id="906fd-163">Create an explanation</span></span>

<span data-ttu-id="906fd-164">Следующий шаг — создание объяснения на странице "обучение".</span><span class="sxs-lookup"><span data-stu-id="906fd-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="906fd-165">Объяснение — это подсказка или подсказка, которая поможет модели понять, как распознать этот документ.</span><span class="sxs-lookup"><span data-stu-id="906fd-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="906fd-166">Например, документы для продления контракта всегда содержат *запрос на дополнительную строку с раскрытием* текста.</span><span class="sxs-lookup"><span data-stu-id="906fd-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="906fd-167">При использовании с извлечением объяснение используется для идентификации строки, которую необходимо извлечь из документа.</span><span class="sxs-lookup"><span data-stu-id="906fd-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="906fd-168">Чтобы создать объяснение:</span><span class="sxs-lookup"><span data-stu-id="906fd-168">To create an explanation:</span></span>

1. <span data-ttu-id="906fd-169">На домашней странице модели перейдите на вкладку **обучение** , чтобы перейти на страницу обучение.</span><span class="sxs-lookup"><span data-stu-id="906fd-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="906fd-170">На странице обучение в разделе " **обученные файлы** " вы увидите список примеров файлов, помеченных ранее.</span><span class="sxs-lookup"><span data-stu-id="906fd-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="906fd-171">Выберите из списка один из ваших положительных файлов, который будет отображаться в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="906fd-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="906fd-172">В разделе объяснение нажмите кнопку **создать**, а затем — **пустое**.</span><span class="sxs-lookup"><span data-stu-id="906fd-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="906fd-173">На странице **Создание объяснения** :</span><span class="sxs-lookup"><span data-stu-id="906fd-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="906fd-174">а.</span><span class="sxs-lookup"><span data-stu-id="906fd-174">a.</span></span> <span data-ttu-id="906fd-175">Введите **имя** (например, "блок раскрытия").</span><span class="sxs-lookup"><span data-stu-id="906fd-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="906fd-176">б.</span><span class="sxs-lookup"><span data-stu-id="906fd-176">b.</span></span> <span data-ttu-id="906fd-177">Выберите **тип**.</span><span class="sxs-lookup"><span data-stu-id="906fd-177">Select the **Type**.</span></span> <span data-ttu-id="906fd-178">В нашем примере мы будем выбирать **список фраз**, так как добавляется текстовая строка.</span><span class="sxs-lookup"><span data-stu-id="906fd-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="906fd-179">в.</span><span class="sxs-lookup"><span data-stu-id="906fd-179">c.</span></span> <span data-ttu-id="906fd-180">В поле **Введите здесь** введите строку.</span><span class="sxs-lookup"><span data-stu-id="906fd-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="906fd-181">В нашем примере мы добавим "запрос на дополнительную раскрытие".</span><span class="sxs-lookup"><span data-stu-id="906fd-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="906fd-182">Вы можете выбрать параметр **с учетом регистра** , если строка должна учитывать регистр.</span><span class="sxs-lookup"><span data-stu-id="906fd-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="906fd-183">г.</span><span class="sxs-lookup"><span data-stu-id="906fd-183">d.</span></span> <span data-ttu-id="906fd-184">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="906fd-184">Click **Save**.</span></span>

    ![Создание объяснения](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="906fd-186">Теперь модель проверит, было ли созданное вами объяснение достаточно хорошо, чтобы правильно определить промаркированные примеры файлов, как положительные и отрицательные.</span><span class="sxs-lookup"><span data-stu-id="906fd-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="906fd-187">В разделе "подготовленные файлы" Проверьте столбец **оценки** после завершения обучения, чтобы увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="906fd-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="906fd-188">Если созданное объяснение было достаточно для того, чтобы оно было было отмечено как (положительное или отрицательное), файлы будут отображаться **соответствующим** образом.</span><span class="sxs-lookup"><span data-stu-id="906fd-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![Создание объяснения](../media/content-understanding/match.png) 

<span data-ttu-id="906fd-190">Если вы получили **несовпадение** с подписанными файлами, вам может потребоваться создать дополнительное пояснение, чтобы предоставить модели дополнительные сведения для определения типа документа.</span><span class="sxs-lookup"><span data-stu-id="906fd-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="906fd-191">Вы можете щелкнуть файл, чтобы получить дополнительные сведения о причине несоответствия.</span><span class="sxs-lookup"><span data-stu-id="906fd-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="906fd-192">Тестирование модели</span><span class="sxs-lookup"><span data-stu-id="906fd-192">Test your model</span></span>

<span data-ttu-id="906fd-193">Если вы получили соответствующее приложение с помеченными примерами файлов, теперь вы можете проверить модель на оставшихся файлов примеров без метки.</span><span class="sxs-lookup"><span data-stu-id="906fd-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="906fd-194">На домашней странице модели перейдите на вкладку **тест** .  Это приведет к запуску модели для файлов примеров без метки.</span><span class="sxs-lookup"><span data-stu-id="906fd-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="906fd-195">В списке **тестовые файлы** будут отображаться файлы, которые будут отображаться, и отобразится, если модель прогнозируется как положительные или отрицательные примеры.</span><span class="sxs-lookup"><span data-stu-id="906fd-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="906fd-196">Вы можете использовать эти сведения, чтобы определить эффективность классификатора в определении ваших документов.</span><span class="sxs-lookup"><span data-stu-id="906fd-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Проверка непомеченных файлов](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="906fd-198">См. также</span><span class="sxs-lookup"><span data-stu-id="906fd-198">See Also</span></span>
[<span data-ttu-id="906fd-199">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="906fd-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="906fd-200">Общие сведения о документе</span><span class="sxs-lookup"><span data-stu-id="906fd-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="906fd-201">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="906fd-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="906fd-202">Применение модели</span><span class="sxs-lookup"><span data-stu-id="906fd-202">Apply a model</span></span>](apply-a-model.md) 




