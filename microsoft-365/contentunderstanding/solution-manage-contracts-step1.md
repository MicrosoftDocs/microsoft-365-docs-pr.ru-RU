---
title: Этап 1. Использование SharePoint Syntex для определения файлов контрактов и извлечения данных
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/17/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как использовать SharePoint Syntex для определения файлов контрактов и извлечения данных с помощью Microsoft 365 решения.
ms.openlocfilehash: 67c0a072b070cd414f5079fe4fb61e7391839951
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583572"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="3b91c-104">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="3b91c-104">Step 1.</span></span> <span data-ttu-id="3b91c-105">Использование SharePoint Syntex для определения файлов контрактов и извлечения данных</span><span class="sxs-lookup"><span data-stu-id="3b91c-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="3b91c-106">Вашей организации необходим способ определения и классификации всех документов по контрактам из множества файлов, которые вы получаете.</span><span class="sxs-lookup"><span data-stu-id="3b91c-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="3b91c-107">Кроме *того,* необходимо быстро просмотреть несколько ключевых элементов в каждом из идентифицированных файлов контрактов (например, клиент, *подрядчик* и сумма *платы).*</span><span class="sxs-lookup"><span data-stu-id="3b91c-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="3b91c-108">Это можно сделать с помощью [SharePoint Syntex](index.md) для создания модели понимания документов и ее применения в библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="3b91c-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="3b91c-109">Обзор процесса</span><span class="sxs-lookup"><span data-stu-id="3b91c-109">Overview of the process</span></span>

<span data-ttu-id="3b91c-110">[Для автоматизации](document-understanding-overview.md) классификации файлов и извлечения информации для понимания документов используются модели искусственного интеллекта (AI).</span><span class="sxs-lookup"><span data-stu-id="3b91c-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="3b91c-111">Модели понимания документов также являются оптимальными для извлечения информации из неструктурированных и полуструктурированных документов, в которых необходимая информация не содержится в таблицах или формах, например в контрактах.</span><span class="sxs-lookup"><span data-stu-id="3b91c-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span>

1. <span data-ttu-id="3b91c-112">Сначала необходимо найти по крайней мере пять примеров файлов, которые можно использовать для "обучения" модели для поиска характеристик, определенных типу контента, который вы пытаетесь определить (контракт).</span><span class="sxs-lookup"><span data-stu-id="3b91c-112">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="3b91c-113">С SharePoint Syntex создайте новую модель понимания документов.</span><span class="sxs-lookup"><span data-stu-id="3b91c-113">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="3b91c-114">С помощью примеров файлов необходимо [создать классификатор](create-a-classifier.md).</span><span class="sxs-lookup"><span data-stu-id="3b91c-114">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="3b91c-115">Обучив классификатор с примерными файлами, вы научите его искать характеристики, характерные для того, что вы увидите в контрактах вашей компании.</span><span class="sxs-lookup"><span data-stu-id="3b91c-115">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="3b91c-116">Например, [создайте "объяснение",](create-a-classifier.md#create-an-explanation) которое ищет определенные строки, которые находятся в ваших контрактах, таких как соглашение об обслуживании, условия соглашения *и* *компенсации*.</span><span class="sxs-lookup"><span data-stu-id="3b91c-116">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="3b91c-117">Вы даже можете обучить объяснению искать эти строки в определенных разделах документа или расположенных рядом с другими строками.</span><span class="sxs-lookup"><span data-stu-id="3b91c-117">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="3b91c-118">Если вы считаете, что обучили классификатор сведениям, которые ему необходимы, вы можете проверить модель на примере набора примеров файлов, чтобы узнать, насколько она эффективна.</span><span class="sxs-lookup"><span data-stu-id="3b91c-118">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="3b91c-119">После тестирования можно при необходимости внести изменения в свои объяснения, чтобы сделать их более эффективными.</span><span class="sxs-lookup"><span data-stu-id="3b91c-119">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="3b91c-120">В модели можно [создать](create-an-extractor.md) экстрактор для получения определенных фрагментов данных из каждого контракта.</span><span class="sxs-lookup"><span data-stu-id="3b91c-120">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="3b91c-121">Например, для каждого контракта больше всего вас беспокоит информация о том, кто клиент, имя подрядчика и общая стоимость.</span><span class="sxs-lookup"><span data-stu-id="3b91c-121">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="3b91c-122">После успешного создания модели применяйте ее в библиотеке SharePoint [документов.](apply-a-model.md)</span><span class="sxs-lookup"><span data-stu-id="3b91c-122">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="3b91c-123">При отправке документов в библиотеку документов будет работать модель понимания документов, которая будет определять и классифицировать все файлы, соответствующие типу контента контрактов, определенному в модели.</span><span class="sxs-lookup"><span data-stu-id="3b91c-123">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="3b91c-124">Все файлы, классифицируются как контракты, будут отображаться в пользовательском представлении библиотеки.</span><span class="sxs-lookup"><span data-stu-id="3b91c-124">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="3b91c-125">В файлах также будут отображаться значения из каждого контракта, определенного в экстракторе.</span><span class="sxs-lookup"><span data-stu-id="3b91c-125">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![Контракты в библиотеке документов](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="3b91c-127">Если у вас есть требования к удержанию для [](apply-a-retention-label-to-a-model.md) контрактов, вы также можете использовать модель для применения метки хранения, которая не позволит удалить контракты в течение определенного периода времени.</span><span class="sxs-lookup"><span data-stu-id="3b91c-127">If you have retention requirements for your contracts, you can also use your model to [apply a retention label](apply-a-retention-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="3b91c-128">Действия по созданию и подготовке модели</span><span class="sxs-lookup"><span data-stu-id="3b91c-128">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="3b91c-129">Для этих действий можно использовать примеры файлов в репозитории ресурсов решений по управлению [контрактами.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)</span><span class="sxs-lookup"><span data-stu-id="3b91c-129">For these steps, you can use the example files in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span> <span data-ttu-id="3b91c-130">Примеры в этом репозитории содержат как файлы модели для понимания документов, так и файлы, используемые для подготовки модели.</span><span class="sxs-lookup"><span data-stu-id="3b91c-130">The examples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="3b91c-131">Создание модели Contract</span><span class="sxs-lookup"><span data-stu-id="3b91c-131">Create a Contract model</span></span>

<span data-ttu-id="3b91c-132">Первым шагом является создание модели Контракта.</span><span class="sxs-lookup"><span data-stu-id="3b91c-132">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="3b91c-133">В центре контента выберите **Создать**, а затем —**Создать модель**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-133">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="3b91c-134">В поле **"Новое понимание документа"** в поле **Имя** введите имя модели.</span><span class="sxs-lookup"><span data-stu-id="3b91c-134">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="3b91c-135">Для этого решения по управлению контрактом можно назвать типовой *контракт.*</span><span class="sxs-lookup"><span data-stu-id="3b91c-135">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="3b91c-136">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-136">Choose **Create**.</span></span> <span data-ttu-id="3b91c-137">В результате будет создана домашняя страница для модели.</span><span class="sxs-lookup"><span data-stu-id="3b91c-137">This creates a home page for the model.</span></span></br>

    ![Снимок экрана домашней страницы Contract.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="3b91c-139">Обучение модели классификации типа файла</span><span class="sxs-lookup"><span data-stu-id="3b91c-139">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="3b91c-140">Добавление примеров файлов для модели</span><span class="sxs-lookup"><span data-stu-id="3b91c-140">Add example files for your model</span></span>

<span data-ttu-id="3b91c-141">Необходимо добавить по крайней мере пять примеров файлов, которые являются документами контрактов, и один пример файла, который не является документом контракта (например, заявление о работе).</span><span class="sxs-lookup"><span data-stu-id="3b91c-141">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="3b91c-142">На странице **Models >,** в статье **Основные** действия  >  **Добавить примеры файлов**, выберите Добавить **файлы**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-142">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![Снимок экрана, показывающий страницу Контракты с выделенной опцией Добавить примеры файлов.](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="3b91c-144">В **примере Выберите файлы для страницы** модели откройте папку Контракт, выберите файлы, которые вы хотите использовать, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-144">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="3b91c-145">Если у вас нет примеров файлов, выберите Upload **добавить** их.</span><span class="sxs-lookup"><span data-stu-id="3b91c-145">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="3b91c-146">Пометить файлы как положительные или отрицательные примеры</span><span class="sxs-lookup"><span data-stu-id="3b91c-146">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="3b91c-147">На странице **Models >,** в статье **Ключевые** действия классифицировать файлы и выполнить обучение, выберите  >   **классификатор Train**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-147">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![Снимок экрана, показывающий страницу Контракты с классифицировать файлы и выделенную возможность обучения.](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="3b91c-149">На странице классификатора > contract **> Contract** в верхней части файла первого примера будет см. текст с вопросом, является ли файл примером созданной модели Contract.</span><span class="sxs-lookup"><span data-stu-id="3b91c-149">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="3b91c-150">Если это положительный пример выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-150">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="3b91c-151">Если это отрицательный пример выберите **Нет**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-151">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="3b91c-152">В **списке примеры с** меткой слева выберите другие файлы, которые необходимо использовать в качестве примеров, и пометить их.</span><span class="sxs-lookup"><span data-stu-id="3b91c-152">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![Домашняя страница классификатора](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a><span data-ttu-id=&quot;3b91c-154&quot;>Добавьте хотя бы одно объяснение для обучения классификатора</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3b91c-154&quot;>Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id=&quot;3b91c-155&quot;>На странице **классификатора > contract > contract** выберите вкладку **Train.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3b91c-155&quot;>On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id=&quot;3b91c-156&quot;>В разделе **&quot;Обученные файлы&quot;** вы увидите список файлов примеров, которые были помечены ранее.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3b91c-156&quot;>In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id=&quot;3b91c-157&quot;>Выберите один из положительных файлов из списка, чтобы отобразить его в зритель.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3b91c-157&quot;>Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id=&quot;3b91c-158&quot;>В разделе **Пояснения** выберите **New,** а затем **Blank**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3b91c-158&quot;>In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id=&quot;3b91c-159&quot;>На странице **Создание объяснения**:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3b91c-159&quot;>On the **Create an explanation** page:</span></span>

    <span data-ttu-id=&quot;3b91c-160&quot;>а.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;3b91c-160&quot;>a.</span></span> <span data-ttu-id=&quot;3b91c-161&quot;>В поле **Name** введите имя объяснения (например, &quot;Согласование").</span><span class="sxs-lookup"><span data-stu-id="3b91c-161">In the **Name** field, type the name of the explanation (such as "Agreement").</span></span>

    <span data-ttu-id="3b91c-162">Б.</span><span class="sxs-lookup"><span data-stu-id="3b91c-162">b.</span></span> <span data-ttu-id="3b91c-163">В поле **"Разъяснение"** выберите **список Фразы,** так как вы добавляете текстовую строку.</span><span class="sxs-lookup"><span data-stu-id="3b91c-163">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="3b91c-164">В.</span><span class="sxs-lookup"><span data-stu-id="3b91c-164">c.</span></span> <span data-ttu-id="3b91c-165">В поле **Список фраз** введите строку (например, "AGREEMENT").</span><span class="sxs-lookup"><span data-stu-id="3b91c-165">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="3b91c-166">Вы можете выбрать **чувствительный к делу,** если строка должна быть чувствительной к делу.</span><span class="sxs-lookup"><span data-stu-id="3b91c-166">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="3b91c-167">г.</span><span class="sxs-lookup"><span data-stu-id="3b91c-167">d.</span></span> <span data-ttu-id="3b91c-168">Выберите **Сохранить и обучить**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-168">Select **Save and train**.</span></span>

    ![Снимок экрана панели "Создание панели объяснений".](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="3b91c-170">Тестирование модели</span><span class="sxs-lookup"><span data-stu-id="3b91c-170">Test your model</span></span>

<span data-ttu-id="3b91c-171">Вы можете протестировать модель контракта на примере файлов, которые она еще не видела.</span><span class="sxs-lookup"><span data-stu-id="3b91c-171">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="3b91c-172">Это необязательно, но это может быть полезной наилучшей практикой.</span><span class="sxs-lookup"><span data-stu-id="3b91c-172">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="3b91c-173">На странице **классификатора > contract > contract** выберите вкладку **Test.** Эта модель выполняется в неослабных файлах примеров.</span><span class="sxs-lookup"><span data-stu-id="3b91c-173">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="3b91c-174">В **списке Тестовые файлы** отображаются файлы примера и показано, предсказывает ли модель положительный или отрицательный результат.</span><span class="sxs-lookup"><span data-stu-id="3b91c-174">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="3b91c-175">Используйте эти сведения, чтобы определить эффективность классификатора в определении ваших документов.</span><span class="sxs-lookup"><span data-stu-id="3b91c-175">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Снимок экрана неослабных файлов в списке текстовых файлов](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="3b91c-177">После этого выберите **обучение выходу.**</span><span class="sxs-lookup"><span data-stu-id="3b91c-177">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="3b91c-178">Создание и обучение экстрактора</span><span class="sxs-lookup"><span data-stu-id="3b91c-178">Create and train an extractor</span></span>

1. <span data-ttu-id="3b91c-179">На странице **Models > Contract** в статье Key **Actions** Create and  >  **train extractors** выберите Create **extractor**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-179">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![Снимок экрана, показывающий страницу Контракты с выделенным параметром Create and Train extractors.](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="3b91c-181">На панели **извлечений нового** объекта в поле **Новое** имя введите имя извлечения.</span><span class="sxs-lookup"><span data-stu-id="3b91c-181">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="3b91c-182">Например, назови его *Клиент,* если вы хотите извлечь имя клиента из каждого контракта.</span><span class="sxs-lookup"><span data-stu-id="3b91c-182">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="3b91c-183">Когда вы закончили, выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-183">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="3b91c-184">Метка объекта, который необходимо извлечь</span><span class="sxs-lookup"><span data-stu-id="3b91c-184">Label the entity you want to extract</span></span>

<span data-ttu-id="3b91c-185">При создании экстрактора откроется страница экстрактора.</span><span class="sxs-lookup"><span data-stu-id="3b91c-185">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="3b91c-186">Здесь вы видите список ваших примеров файлов, причем первый файл в списке отображается в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="3b91c-186">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

![Снимок экрана страницы примеры примеры с меткой client extractor.](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="3b91c-188">Чтобы пометить объект:</span><span class="sxs-lookup"><span data-stu-id="3b91c-188">To label the entity:</span></span>

1. <span data-ttu-id="3b91c-189">В средстве просмотра выберите данные, которые нужно извлечь из файлов.</span><span class="sxs-lookup"><span data-stu-id="3b91c-189">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="3b91c-190">Например, если вы хотите извлечь *клиента,* вы выделяете значение клиента в первом файле (в этом примере Best *For You Organics),* а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-190">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="3b91c-191">В столбце **Метка** отображается отображение  значения из файла в списке примеров с меткой.</span><span class="sxs-lookup"><span data-stu-id="3b91c-191">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="3b91c-192">Выберите **следующий файл** для автозаданий и откройте следующий файл в списке в зрителье.</span><span class="sxs-lookup"><span data-stu-id="3b91c-192">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="3b91c-193">Или выберите **Сохранить,** а затем выберите другой файл из списка **примеров с меткой.**</span><span class="sxs-lookup"><span data-stu-id="3b91c-193">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="3b91c-194">В представлении повторите шаги 1 и 2, а затем повторите, пока не сэкономит метку во всех файлах.</span><span class="sxs-lookup"><span data-stu-id="3b91c-194">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="3b91c-195">После маркировки файлов отображается баннер уведомлений, информирующий о переходе на обучение.</span><span class="sxs-lookup"><span data-stu-id="3b91c-195">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="3b91c-196">Вы можете выбрать метку дополнительных документов или продвижения к обучению.</span><span class="sxs-lookup"><span data-stu-id="3b91c-196">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="3b91c-197">Добавление объяснений</span><span class="sxs-lookup"><span data-stu-id="3b91c-197">Add an explanation</span></span>

<span data-ttu-id="3b91c-198">Вы можете создать объяснение, которое содержит подсказку о самом формате сущности и вариантах, которые он может иметь в примерах файлов.</span><span class="sxs-lookup"><span data-stu-id="3b91c-198">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="3b91c-199">Например, значение даты может быть в разных форматах, таких как:</span><span class="sxs-lookup"><span data-stu-id="3b91c-199">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="3b91c-200">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="3b91c-200">10/14/2019</span></span>
- <span data-ttu-id="3b91c-201">14 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="3b91c-201">October 14, 2019</span></span>
- <span data-ttu-id="3b91c-202">Понедельник, 14 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="3b91c-202">Monday, October 14, 2019</span></span>

<span data-ttu-id="3b91c-203">Чтобы определить дату *начала контракта,* можно создать объяснение шаблона.</span><span class="sxs-lookup"><span data-stu-id="3b91c-203">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="3b91c-204">В разделе **Пояснения** выберите **New,** а затем **Blank**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-204">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="3b91c-205">На странице **Создание объяснения**:</span><span class="sxs-lookup"><span data-stu-id="3b91c-205">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="3b91c-206">а.</span><span class="sxs-lookup"><span data-stu-id="3b91c-206">a.</span></span> <span data-ttu-id="3b91c-207">В поле **Имя** введите имя объяснения (например, *Дата).*</span><span class="sxs-lookup"><span data-stu-id="3b91c-207">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="3b91c-208">Б.</span><span class="sxs-lookup"><span data-stu-id="3b91c-208">b.</span></span> <span data-ttu-id="3b91c-209">В поле **"Разъяснение"** выберите **список шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-209">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="3b91c-210">В.</span><span class="sxs-lookup"><span data-stu-id="3b91c-210">c.</span></span> <span data-ttu-id="3b91c-211">В поле **Значение** укай вариант даты, как они отображаются в примере файлов.</span><span class="sxs-lookup"><span data-stu-id="3b91c-211">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="3b91c-212">Например, если у вас есть форматы даты, которые отображаются как 0/00/0000, вы вводите любые варианты, которые появляются в ваших документах, например:</span><span class="sxs-lookup"><span data-stu-id="3b91c-212">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="3b91c-213">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="3b91c-213">0/0/0000</span></span>
    - <span data-ttu-id="3b91c-214">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="3b91c-214">0/00/0000</span></span>
    - <span data-ttu-id="3b91c-215">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="3b91c-215">00/0/0000</span></span>
    - <span data-ttu-id="3b91c-216">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="3b91c-216">00/00/0000</span></span>

4. <span data-ttu-id="3b91c-217">Выберите **Сохранить и обучить**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-217">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="3b91c-218">Снова протестировать модель</span><span class="sxs-lookup"><span data-stu-id="3b91c-218">Test your model again</span></span>

<span data-ttu-id="3b91c-219">Вы можете протестировать модель контракта на примере файлов, которые она еще не видела.</span><span class="sxs-lookup"><span data-stu-id="3b91c-219">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="3b91c-220">Это необязательно, но это может быть полезной наилучшей практикой.</span><span class="sxs-lookup"><span data-stu-id="3b91c-220">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="3b91c-221">На странице **классификатора > contract > contract** выберите вкладку **Test.** Эта модель выполняется в неослабных файлах примеров.</span><span class="sxs-lookup"><span data-stu-id="3b91c-221">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="3b91c-222">В **списке тестовых файлов** отображаются файлы примера и показано, может ли модель извлекать необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="3b91c-222">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="3b91c-223">Используйте эти сведения, чтобы определить эффективность классификатора в определении ваших документов.</span><span class="sxs-lookup"><span data-stu-id="3b91c-223">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="3b91c-224">После этого выберите **обучение выходу.**</span><span class="sxs-lookup"><span data-stu-id="3b91c-224">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="3b91c-225">Применение модели в библиотеке документов</span><span class="sxs-lookup"><span data-stu-id="3b91c-225">Apply your model to a document library</span></span>

<span data-ttu-id="3b91c-226">Чтобы применить модель к библиотеке SharePoint документов:</span><span class="sxs-lookup"><span data-stu-id="3b91c-226">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="3b91c-227">На странице **Models >, в** статье **Ключевые** действия Применить модель к  >  **библиотекам,** выберите **Применить модель**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-227">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![Снимок экрана, на котором показана страница Контракты с моделью Apply to libraries option highlighted.](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="3b91c-229">На панели **Добавить контракт** выберите SharePoint, на который содержится библиотека документов, на которую необходимо применить модель.</span><span class="sxs-lookup"><span data-stu-id="3b91c-229">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="3b91c-230">Если сайт не отображается в списке, используйте поле поиска, чтобы найти его.</span><span class="sxs-lookup"><span data-stu-id="3b91c-230">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="3b91c-231">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="3b91c-231">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b91c-232">Вам потребуются разрешения *Управление списком* или права на *редактирование* для библиотеки документов, к которой применяется модель.</span><span class="sxs-lookup"><span data-stu-id="3b91c-232">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="3b91c-233">После выбора сайта выберите библиотеку документов, к которой необходимо применить модель.</span><span class="sxs-lookup"><span data-stu-id="3b91c-233">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="3b91c-234">Так как модель связана с типом контента, при ее применении к библиотеке будет добавлен тип контента и его представление с метки, извлеченные в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="3b91c-234">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="3b91c-235">Это представление является представлением библиотеки по умолчанию, но по умолчанию можно выбрать, чтобы оно не было представлением  по умолчанию, выбрав **расширенные** параметры и очистив это новое представление в качестве контрольного окна по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3b91c-235">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="3b91c-236">Нажмите кнопку **Добавить**, чтобы применить модель к библиотеке.</span><span class="sxs-lookup"><span data-stu-id="3b91c-236">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="3b91c-237">На странице **Models > Contract** в  разделе Библиотеки с этой моделью вы увидите URL-адрес SharePoint сайта.</span><span class="sxs-lookup"><span data-stu-id="3b91c-237">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![Снимок экрана домашней страницы Contract, показывающая библиотеки с этим разделом модели.](../media/content-understanding/contract-libraries-with-this-model.png)

<span data-ttu-id="3b91c-239">После применения модели к библиотеке документов можно приступить к отправке документов на сайт и увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="3b91c-239">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="3b91c-240">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="3b91c-240">Next step</span></span>

[<span data-ttu-id="3b91c-241">Шаг 2. Используйте Microsoft Teams для создания канала управления контрактами</span><span class="sxs-lookup"><span data-stu-id="3b91c-241">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)