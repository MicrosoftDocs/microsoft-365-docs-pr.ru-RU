---
title: Этап 1. Используйте SharePoint Syntex для идентификации файлов контрактов и извлечения данных
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Узнайте, как использовать SharePoint Syntex для идентификации файлов контрактов и извлечения данных с помощью Microsoft 365 решения.
ms.openlocfilehash: b73f7b96a1f1a9159770fb1bfb20bf2718f08c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287357"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="e8aee-104">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="e8aee-104">Step 1.</span></span> <span data-ttu-id="e8aee-105">Используйте SharePoint Syntex для идентификации файлов контрактов и извлечения данных</span><span class="sxs-lookup"><span data-stu-id="e8aee-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="e8aee-106">Вашей организации необходим способ определения и классификации всех документов по контрактам из множества файлов, которые вы получаете.</span><span class="sxs-lookup"><span data-stu-id="e8aee-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="e8aee-107">Кроме *того,* необходимо быстро просмотреть несколько ключевых элементов в каждом из идентифицированных файлов контрактов (например, клиент, *подрядчик* и сумма *платы).*</span><span class="sxs-lookup"><span data-stu-id="e8aee-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="e8aee-108">Это можно сделать с помощью [SharePoint Syntex](index.md) для создания модели понимания документов и ее применения в библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="e8aee-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="e8aee-109">Обзор процесса</span><span class="sxs-lookup"><span data-stu-id="e8aee-109">Overview of the process</span></span>

<span data-ttu-id="e8aee-110">[Для автоматизации](document-understanding-overview.md) классификации файлов и извлечения информации для понимания документов используются модели искусственного интеллекта (AI).</span><span class="sxs-lookup"><span data-stu-id="e8aee-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="e8aee-111">Модели понимания документов также являются оптимальными для извлечения информации из неструктурированных и полуструктурированных документов, в которых необходимая информация не содержится в таблицах или формах, например в контрактах.</span><span class="sxs-lookup"><span data-stu-id="e8aee-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span> 

<span data-ttu-id="e8aee-112">Модели осмысления документации используют технологию распознавания текста для сканирования PDF-файлов, изображений и TIFF-файлов как при обучении модели с помощью файлов примеров, так и при запуске модели с файлами в библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="e8aee-112">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

1. <span data-ttu-id="e8aee-113">Сначала необходимо найти по крайней мере пять примеров файлов, которые можно использовать для "обучения" модели для поиска характеристик, определенных типу контента, который вы пытаетесь определить (контракт).</span><span class="sxs-lookup"><span data-stu-id="e8aee-113">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="e8aee-114">С SharePoint Syntex создайте новую модель понимания документов.</span><span class="sxs-lookup"><span data-stu-id="e8aee-114">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="e8aee-115">С помощью примеров файлов необходимо [создать классификатор](create-a-classifier.md).</span><span class="sxs-lookup"><span data-stu-id="e8aee-115">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="e8aee-116">Обучив классификатор с примерными файлами, вы научите его искать характеристики, характерные для того, что вы увидите в контрактах вашей компании.</span><span class="sxs-lookup"><span data-stu-id="e8aee-116">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="e8aee-117">Например, [создайте "объяснение",](create-a-classifier.md#create-an-explanation) которое ищет определенные строки, которые находятся в ваших контрактах, таких как соглашение об обслуживании, условия соглашения *и* *компенсации*.</span><span class="sxs-lookup"><span data-stu-id="e8aee-117">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="e8aee-118">Вы даже можете обучить объяснению искать эти строки в определенных разделах документа или расположенных рядом с другими строками.</span><span class="sxs-lookup"><span data-stu-id="e8aee-118">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="e8aee-119">Если вы считаете, что обучили классификатор сведениям, которые ему необходимы, вы можете проверить модель на примере набора примеров файлов, чтобы узнать, насколько она эффективна.</span><span class="sxs-lookup"><span data-stu-id="e8aee-119">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="e8aee-120">После тестирования можно при необходимости внести изменения в свои объяснения, чтобы сделать их более эффективными.</span><span class="sxs-lookup"><span data-stu-id="e8aee-120">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="e8aee-121">В модели можно [создать](create-an-extractor.md) экстрактор для получения определенных фрагментов данных из каждого контракта.</span><span class="sxs-lookup"><span data-stu-id="e8aee-121">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="e8aee-122">Например, для каждого контракта больше всего вас беспокоит информация о том, кто клиент, имя подрядчика и общая стоимость.</span><span class="sxs-lookup"><span data-stu-id="e8aee-122">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="e8aee-123">После успешного создания модели применяйте ее в библиотеке SharePoint [документов.](apply-a-model.md)</span><span class="sxs-lookup"><span data-stu-id="e8aee-123">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="e8aee-124">При отправке документов в библиотеку документов будет работать модель понимания документов, которая будет определять и классифицировать все файлы, соответствующие типу контента контрактов, определенному в модели.</span><span class="sxs-lookup"><span data-stu-id="e8aee-124">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="e8aee-125">Все файлы, классифицируются как контракты, будут отображаться в пользовательском представлении библиотеки.</span><span class="sxs-lookup"><span data-stu-id="e8aee-125">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="e8aee-126">В файлах также будут отображаться значения из каждого контракта, определенного в экстракторе.</span><span class="sxs-lookup"><span data-stu-id="e8aee-126">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![Контракты в библиотеке документов](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="e8aee-128">Если у вас есть требования к хранению или безопасности для контрактов, вы [](apply-a-sensitivity-label-to-a-model.md) также можете использовать модель для применения метки хранения или метки конфиденциальности, которые не будут удалять ваши контракты в течение определенного периода времени или ограничить доступ к контрактам. [](apply-a-retention-label-to-a-model.md)</span><span class="sxs-lookup"><span data-stu-id="e8aee-128">If you have retention or security requirements for your contracts, you can also use your model to apply a [retention label](apply-a-retention-label-to-a-model.md) or a [sensitivity label](apply-a-sensitivity-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time or to restrict who can access the contracts.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="e8aee-129">Действия по созданию и подготовке модели</span><span class="sxs-lookup"><span data-stu-id="e8aee-129">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="e8aee-130">Для этих действий можно использовать примеры файлов в репозитории ресурсов решений по управлению [контрактами.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)</span><span class="sxs-lookup"><span data-stu-id="e8aee-130">For these steps, you can use the example files in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span> <span data-ttu-id="e8aee-131">Примеры в этом репозитории содержат как файлы модели для понимания документов, так и файлы, используемые для подготовки модели.</span><span class="sxs-lookup"><span data-stu-id="e8aee-131">The examples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="e8aee-132">Создание модели Contract</span><span class="sxs-lookup"><span data-stu-id="e8aee-132">Create a Contract model</span></span>

<span data-ttu-id="e8aee-133">Первым шагом является создание модели Контракта.</span><span class="sxs-lookup"><span data-stu-id="e8aee-133">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="e8aee-134">В центре контента выберите **Создать**, а затем —**Создать модель**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-134">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="e8aee-135">В поле **"Новое понимание документа"** в поле **Имя** введите имя модели.</span><span class="sxs-lookup"><span data-stu-id="e8aee-135">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="e8aee-136">Для этого решения по управлению контрактом можно назвать типовой *контракт.*</span><span class="sxs-lookup"><span data-stu-id="e8aee-136">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="e8aee-137">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-137">Choose **Create**.</span></span> <span data-ttu-id="e8aee-138">В результате будет создана домашняя страница для модели.</span><span class="sxs-lookup"><span data-stu-id="e8aee-138">This creates a home page for the model.</span></span></br>

    ![Снимок экрана домашней страницы Contract.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="e8aee-140">Обучение модели классификации типа файла</span><span class="sxs-lookup"><span data-stu-id="e8aee-140">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="e8aee-141">Добавление примеров файлов для модели</span><span class="sxs-lookup"><span data-stu-id="e8aee-141">Add example files for your model</span></span>

<span data-ttu-id="e8aee-142">Необходимо добавить по крайней мере пять примеров файлов, которые являются документами контрактов, и один пример файла, который не является документом контракта (например, заявление о работе).</span><span class="sxs-lookup"><span data-stu-id="e8aee-142">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="e8aee-143">На странице **Models >,** в статье **Основные** действия  >  **Добавить примеры файлов**, выберите Добавить **файлы**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-143">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![Снимок экрана, показывающий страницу Контракты с выделенной опцией Добавить примеры файлов.](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="e8aee-145">В **примере Выберите файлы для страницы** модели откройте папку Контракт, выберите файлы, которые вы хотите использовать, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-145">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="e8aee-146">Если у вас нет примеров файлов, выберите Upload **добавить** их.</span><span class="sxs-lookup"><span data-stu-id="e8aee-146">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="e8aee-147">Пометить файлы как положительные или отрицательные примеры</span><span class="sxs-lookup"><span data-stu-id="e8aee-147">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="e8aee-148">На странице **Models >,** в статье **Ключевые** действия классифицировать файлы и выполнить обучение, выберите  >   **классификатор Train**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-148">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![Снимок экрана, показывающий страницу Контракты с классифицировать файлы и выделенную возможность обучения.](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="e8aee-150">На странице классификатора > contract **> Contract** в верхней части файла первого примера будет см. текст с вопросом, является ли файл примером созданной модели Contract.</span><span class="sxs-lookup"><span data-stu-id="e8aee-150">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="e8aee-151">Если это положительный пример выберите **Да**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-151">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="e8aee-152">Если это отрицательный пример выберите **Нет**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-152">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="e8aee-153">В **списке примеры с** меткой слева выберите другие файлы, которые необходимо использовать в качестве примеров, и пометить их.</span><span class="sxs-lookup"><span data-stu-id="e8aee-153">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![Домашняя страница классификатора](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier&quot;></a><span data-ttu-id=&quot;e8aee-155&quot;>Добавьте хотя бы одно объяснение для обучения классификатора</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e8aee-155&quot;>Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id=&quot;e8aee-156&quot;>На странице **классификатора > contract > contract** выберите вкладку **Train.**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e8aee-156&quot;>On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id=&quot;e8aee-157&quot;>В разделе **&quot;Обученные файлы&quot;** вы увидите список файлов примеров, которые были помечены ранее.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e8aee-157&quot;>In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id=&quot;e8aee-158&quot;>Выберите один из положительных файлов из списка, чтобы отобразить его в зритель.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e8aee-158&quot;>Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id=&quot;e8aee-159&quot;>В разделе **Пояснения** выберите **New,** а затем **Blank**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e8aee-159&quot;>In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id=&quot;e8aee-160&quot;>На странице **Создание объяснения**:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e8aee-160&quot;>On the **Create an explanation** page:</span></span>

    <span data-ttu-id=&quot;e8aee-161&quot;>а.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;e8aee-161&quot;>a.</span></span> <span data-ttu-id=&quot;e8aee-162&quot;>В поле **Name** введите имя объяснения (например, &quot;Согласование").</span><span class="sxs-lookup"><span data-stu-id="e8aee-162">In the **Name** field, type the name of the explanation (such as "Agreement").</span></span>

    <span data-ttu-id="e8aee-163">б.</span><span class="sxs-lookup"><span data-stu-id="e8aee-163">b.</span></span> <span data-ttu-id="e8aee-164">В поле **"Разъяснение"** выберите **список Фразы,** так как вы добавляете текстовую строку.</span><span class="sxs-lookup"><span data-stu-id="e8aee-164">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="e8aee-165">в.</span><span class="sxs-lookup"><span data-stu-id="e8aee-165">c.</span></span> <span data-ttu-id="e8aee-166">В поле **Список фраз** введите строку (например, "AGREEMENT").</span><span class="sxs-lookup"><span data-stu-id="e8aee-166">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="e8aee-167">Вы можете выбрать **чувствительный к делу,** если строка должна быть чувствительной к делу.</span><span class="sxs-lookup"><span data-stu-id="e8aee-167">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="e8aee-168">г.</span><span class="sxs-lookup"><span data-stu-id="e8aee-168">d.</span></span> <span data-ttu-id="e8aee-169">Выберите **Сохранить и обучить**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-169">Select **Save and train**.</span></span>

    ![Снимок экрана панели "Создание панели объяснений".](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="e8aee-171">Тестирование модели</span><span class="sxs-lookup"><span data-stu-id="e8aee-171">Test your model</span></span>

<span data-ttu-id="e8aee-172">Вы можете протестировать модель контракта на примере файлов, которые она еще не видела.</span><span class="sxs-lookup"><span data-stu-id="e8aee-172">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="e8aee-173">Это необязательно, но это может быть полезной наилучшей практикой.</span><span class="sxs-lookup"><span data-stu-id="e8aee-173">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="e8aee-174">На странице **классификатора > contract > contract** выберите вкладку **Test.** Эта модель выполняется в неослабных файлах примеров.</span><span class="sxs-lookup"><span data-stu-id="e8aee-174">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="e8aee-175">В **списке Тестовые файлы** отображаются файлы примера и показано, предсказывает ли модель положительный или отрицательный результат.</span><span class="sxs-lookup"><span data-stu-id="e8aee-175">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="e8aee-176">Используйте эти сведения, чтобы определить эффективность классификатора в определении ваших документов.</span><span class="sxs-lookup"><span data-stu-id="e8aee-176">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Снимок экрана неослабных файлов в списке текстовых файлов](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="e8aee-178">После этого выберите **обучение выходу.**</span><span class="sxs-lookup"><span data-stu-id="e8aee-178">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="e8aee-179">Создание и обучение экстрактора</span><span class="sxs-lookup"><span data-stu-id="e8aee-179">Create and train an extractor</span></span>

1. <span data-ttu-id="e8aee-180">На странице **Models > Contract** в статье Key **Actions** Create and  >  **train extractors** выберите Create **extractor**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-180">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![Снимок экрана, показывающий страницу Контракты с выделенным параметром Create and Train extractors.](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="e8aee-182">На панели **извлечений нового** объекта в поле **Новое** имя введите имя извлечения.</span><span class="sxs-lookup"><span data-stu-id="e8aee-182">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="e8aee-183">Например, назови его *Клиент,* если вы хотите извлечь имя клиента из каждого контракта.</span><span class="sxs-lookup"><span data-stu-id="e8aee-183">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="e8aee-184">Когда вы закончили, выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-184">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="e8aee-185">Метка объекта, который необходимо извлечь</span><span class="sxs-lookup"><span data-stu-id="e8aee-185">Label the entity you want to extract</span></span>

<span data-ttu-id="e8aee-186">При создании экстрактора откроется страница экстрактора.</span><span class="sxs-lookup"><span data-stu-id="e8aee-186">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="e8aee-187">Здесь вы видите список ваших примеров файлов, причем первый файл в списке отображается в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="e8aee-187">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

![Снимок экрана страницы примеры примеры с меткой client extractor.](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="e8aee-189">Чтобы пометить объект:</span><span class="sxs-lookup"><span data-stu-id="e8aee-189">To label the entity:</span></span>

1. <span data-ttu-id="e8aee-190">В средстве просмотра выберите данные, которые нужно извлечь из файлов.</span><span class="sxs-lookup"><span data-stu-id="e8aee-190">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="e8aee-191">Например, если вы хотите извлечь *клиента,* вы выделяете значение клиента в первом файле (в этом примере Best *For You Organics),* а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-191">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="e8aee-192">В столбце **Метка** отображается отображение  значения из файла в списке примеров с меткой.</span><span class="sxs-lookup"><span data-stu-id="e8aee-192">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="e8aee-193">Выберите **следующий файл** для автозаданий и откройте следующий файл в списке в зрителье.</span><span class="sxs-lookup"><span data-stu-id="e8aee-193">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="e8aee-194">Или выберите **Сохранить,** а затем выберите другой файл из списка **примеров с меткой.**</span><span class="sxs-lookup"><span data-stu-id="e8aee-194">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="e8aee-195">В представлении повторите шаги 1 и 2, а затем повторите, пока не сэкономит метку во всех файлах.</span><span class="sxs-lookup"><span data-stu-id="e8aee-195">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="e8aee-196">После маркировки файлов отображается баннер уведомлений, информирующий о переходе на обучение.</span><span class="sxs-lookup"><span data-stu-id="e8aee-196">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="e8aee-197">Вы можете выбрать метку дополнительных документов или продвижения к обучению.</span><span class="sxs-lookup"><span data-stu-id="e8aee-197">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="e8aee-198">Добавление объяснений</span><span class="sxs-lookup"><span data-stu-id="e8aee-198">Add an explanation</span></span>

<span data-ttu-id="e8aee-199">Вы можете создать объяснение, которое содержит подсказку о самом формате сущности и вариантах, которые он может иметь в примерах файлов.</span><span class="sxs-lookup"><span data-stu-id="e8aee-199">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="e8aee-200">Например, значение даты может быть в разных форматах, таких как:</span><span class="sxs-lookup"><span data-stu-id="e8aee-200">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="e8aee-201">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="e8aee-201">10/14/2019</span></span>
- <span data-ttu-id="e8aee-202">14 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="e8aee-202">October 14, 2019</span></span>
- <span data-ttu-id="e8aee-203">Понедельник, 14 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="e8aee-203">Monday, October 14, 2019</span></span>

<span data-ttu-id="e8aee-204">Чтобы определить дату *начала контракта,* можно создать объяснение шаблона.</span><span class="sxs-lookup"><span data-stu-id="e8aee-204">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="e8aee-205">В разделе **Пояснения** выберите **New,** а затем **Blank**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-205">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="e8aee-206">На странице **Создание объяснения**:</span><span class="sxs-lookup"><span data-stu-id="e8aee-206">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="e8aee-207">а.</span><span class="sxs-lookup"><span data-stu-id="e8aee-207">a.</span></span> <span data-ttu-id="e8aee-208">В поле **Имя** введите имя объяснения (например, *Дата).*</span><span class="sxs-lookup"><span data-stu-id="e8aee-208">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="e8aee-209">б.</span><span class="sxs-lookup"><span data-stu-id="e8aee-209">b.</span></span> <span data-ttu-id="e8aee-210">В поле **"Разъяснение"** выберите **список шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-210">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="e8aee-211">в.</span><span class="sxs-lookup"><span data-stu-id="e8aee-211">c.</span></span> <span data-ttu-id="e8aee-212">В поле **Значение** укай вариант даты, как они отображаются в примере файлов.</span><span class="sxs-lookup"><span data-stu-id="e8aee-212">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="e8aee-213">Например, если у вас есть форматы даты, которые отображаются как 0/00/0000, вы вводите любые варианты, которые появляются в ваших документах, например:</span><span class="sxs-lookup"><span data-stu-id="e8aee-213">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="e8aee-214">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="e8aee-214">0/0/0000</span></span>
    - <span data-ttu-id="e8aee-215">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="e8aee-215">0/00/0000</span></span>
    - <span data-ttu-id="e8aee-216">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="e8aee-216">00/0/0000</span></span>
    - <span data-ttu-id="e8aee-217">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="e8aee-217">00/00/0000</span></span>

4. <span data-ttu-id="e8aee-218">Выберите **Сохранить и обучить**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-218">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="e8aee-219">Снова протестировать модель</span><span class="sxs-lookup"><span data-stu-id="e8aee-219">Test your model again</span></span>

<span data-ttu-id="e8aee-220">Вы можете протестировать модель контракта на примере файлов, которые она еще не видела.</span><span class="sxs-lookup"><span data-stu-id="e8aee-220">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="e8aee-221">Это необязательно, но это может быть полезной наилучшей практикой.</span><span class="sxs-lookup"><span data-stu-id="e8aee-221">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="e8aee-222">На странице **классификатора > contract > contract** выберите вкладку **Test.** Эта модель выполняется в неослабных файлах примеров.</span><span class="sxs-lookup"><span data-stu-id="e8aee-222">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="e8aee-223">В **списке тестовых файлов** отображаются файлы примера и показано, может ли модель извлекать необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="e8aee-223">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="e8aee-224">Используйте эти сведения, чтобы определить эффективность классификатора в определении ваших документов.</span><span class="sxs-lookup"><span data-stu-id="e8aee-224">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="e8aee-225">После этого выберите **обучение выходу.**</span><span class="sxs-lookup"><span data-stu-id="e8aee-225">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="e8aee-226">Применение модели в библиотеке документов</span><span class="sxs-lookup"><span data-stu-id="e8aee-226">Apply your model to a document library</span></span>

<span data-ttu-id="e8aee-227">Чтобы применить модель к библиотеке SharePoint документов:</span><span class="sxs-lookup"><span data-stu-id="e8aee-227">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="e8aee-228">На странице **Models >, в** статье **Ключевые** действия Применить модель к  >  **библиотекам,** выберите **Применить модель**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-228">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![Снимок экрана, на котором показана страница Контракты с моделью Apply to libraries option highlighted.](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="e8aee-230">На панели **Добавить контракт** выберите SharePoint, на который содержится библиотека документов, на которую необходимо применить модель.</span><span class="sxs-lookup"><span data-stu-id="e8aee-230">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="e8aee-231">Если сайт не отображается в списке, используйте поле поиска, чтобы найти его.</span><span class="sxs-lookup"><span data-stu-id="e8aee-231">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="e8aee-232">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="e8aee-232">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e8aee-233">Вам потребуются разрешения *Управление списком* или права на *редактирование* для библиотеки документов, к которой применяется модель.</span><span class="sxs-lookup"><span data-stu-id="e8aee-233">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="e8aee-234">После выбора сайта выберите библиотеку документов, к которой необходимо применить модель.</span><span class="sxs-lookup"><span data-stu-id="e8aee-234">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="e8aee-235">Так как модель связана с типом контента, при ее применении к библиотеке будет добавлен тип контента и его представление с метки, извлеченные в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="e8aee-235">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="e8aee-236">Это представление является представлением библиотеки по умолчанию, но по умолчанию можно выбрать, чтобы оно не было представлением  по умолчанию, выбрав **расширенные** параметры и очистив это новое представление в качестве контрольного окна по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e8aee-236">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="e8aee-237">Нажмите кнопку **Добавить**, чтобы применить модель к библиотеке.</span><span class="sxs-lookup"><span data-stu-id="e8aee-237">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="e8aee-238">На странице **Models > Contract** в  разделе Библиотеки с этой моделью вы увидите URL-адрес SharePoint сайта.</span><span class="sxs-lookup"><span data-stu-id="e8aee-238">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![Снимок экрана домашней страницы Contract, показывающая библиотеки с этим разделом модели.](../media/content-understanding/contract-libraries-with-this-model.png)

7. <span data-ttu-id="e8aee-240">В **Параметры**  >  **параметров библиотеки:**</span><span class="sxs-lookup"><span data-stu-id="e8aee-240">Under **Settings** > **Library settings**:</span></span>

   - <span data-ttu-id="e8aee-241">Добавьте столбец с **именем Status** и **выберите Выбор** в качестве типа столбца.</span><span class="sxs-lookup"><span data-stu-id="e8aee-241">Add a column named **Status** and select **Choice** as the column type.</span></span>
   - <span data-ttu-id="e8aee-242">Применить значения **In Review,** **Approved** и **Rejected.**</span><span class="sxs-lookup"><span data-stu-id="e8aee-242">Apply the **In review**, **Approved**, and **Rejected** values.</span></span>

<span data-ttu-id="e8aee-243">После применения модели к библиотеке документов можно приступить к отправке документов на сайт и увидеть результаты.</span><span class="sxs-lookup"><span data-stu-id="e8aee-243">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="e8aee-244">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="e8aee-244">Next step</span></span>

[<span data-ttu-id="e8aee-245">Шаг 2. Используйте Microsoft Teams для создания канала управления контрактами</span><span class="sxs-lookup"><span data-stu-id="e8aee-245">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)