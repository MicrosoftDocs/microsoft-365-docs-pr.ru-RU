---
title: Создание средства извлечения (Предварительная версия)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как создать средство извлечения
ms.openlocfilehash: 76cb17df069c6905080baabb0b57d765fe5cc94c
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540110"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="f1a59-103">Создание средства извлечения (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f1a59-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="f1a59-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="f1a59-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="f1a59-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="f1a59-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="f1a59-106">До или после создания модели классификатора для автоматизации идентификации и классификации определенных типов документов можно дополнительно добавить в модель средства извлечения для извлечения определенных сведений из этих документов.</span><span class="sxs-lookup"><span data-stu-id="f1a59-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="f1a59-107">Например, вам может потребоваться, чтобы модель не только определяла все документы по *обновлению контрактов* , добавленные в библиотеку документов, но и отображала *дату начала службы* для каждого документа в виде столбца в библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="f1a59-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="f1a59-108">Необходимо создать средство извлечения для каждой сущности в документе, который необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="f1a59-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="f1a59-109">В нашем примере мы хотим извлечь *дату начала службы* для каждого документа *продления контракта* , идентифицируемого моделью.</span><span class="sxs-lookup"><span data-stu-id="f1a59-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="f1a59-110">Нам нужна возможность просматривать представление в библиотеке документов для всех документов по *обновлению контрактов* со столбцом, в котором отображается значение даты начала каждого документа.</span><span class="sxs-lookup"><span data-stu-id="f1a59-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="f1a59-111">Перед созданием средства извлечения необходимо [Добавить файлы примеров](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) , чтобы обучить модель, чтобы определить сведения, которые необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="f1a59-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="f1a59-112">Используйте те же примеры файлов, которые использовались для создания классификатора.</span><span class="sxs-lookup"><span data-stu-id="f1a59-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="f1a59-113">Имя средства извлечения</span><span class="sxs-lookup"><span data-stu-id="f1a59-113">Name your extractor</span></span>

1. <span data-ttu-id="f1a59-114">На плитке " **Создание и обучение** " в разделе "Домашняя страница модели" щелкните " **Извлечение**и обучение".</span><span class="sxs-lookup"><span data-stu-id="f1a59-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="f1a59-115">На экране **Создание средства извлечения сущностей** введите имя средства извлечения в поле **новое имя средства извлечения** .</span><span class="sxs-lookup"><span data-stu-id="f1a59-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="f1a59-116">Например, если нам нужно извлечь дату начала службы из каждого документа продления контракта, мы можем назвать ее как **дату начала** .</span><span class="sxs-lookup"><span data-stu-id="f1a59-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="f1a59-117">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="f1a59-118">Добавление метки</span><span class="sxs-lookup"><span data-stu-id="f1a59-118">Add a label</span></span>

<span data-ttu-id="f1a59-119">Следующий шаг — маркировка сведений, которые необходимо извлечь в примерах обучающих файлов.</span><span class="sxs-lookup"><span data-stu-id="f1a59-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="f1a59-120">При создании средства извлечения будет открыта страница извлечения, в которой вы увидите список файлов с примерами, с первым файлом в списке, отображаемом в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="f1a59-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="f1a59-121">В средстве просмотра выберите данные, которые необходимо извлечь из файлов.</span><span class="sxs-lookup"><span data-stu-id="f1a59-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="f1a59-122">Например, если вы хотите извлечь *дату начала обслуживания*, в первом файле будет выделено значение даты, которое будет выделено в первом файле (*понедельник, 14 октября 2019*).</span><span class="sxs-lookup"><span data-stu-id="f1a59-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="f1a59-123">Затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-123">Then click **Save**.</span></span>  <span data-ttu-id="f1a59-124">Отобразится значение для файла в списке помеченные примеры под столбцом **метки** .</span><span class="sxs-lookup"><span data-stu-id="f1a59-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="f1a59-125">Выберите пункт **следующий файл** для автосохранения и откройте следующий файл в списке в средстве просмотра или выберите **сохранить** и выберите другой файл из списка **помеченных примеров** .</span><span class="sxs-lookup"><span data-stu-id="f1a59-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="f1a59-126">В средстве просмотра повторите шаги 1 и 2 и сделайте это, пока метка не будет сохранена в пяти файлах.</span><span class="sxs-lookup"><span data-stu-id="f1a59-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![Дополнительные параметры](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="f1a59-128">Добавление отрицательного примера</span><span class="sxs-lookup"><span data-stu-id="f1a59-128">Add a negative example</span></span>

<span data-ttu-id="f1a59-129">Аналогично добавлению файла с отрицательным примером при создании классификатора, необходимо добавить к средству извлечения отрицательный пример.</span><span class="sxs-lookup"><span data-stu-id="f1a59-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="f1a59-130">В нашем примере это должен быть файл, который не содержит значение даты начала службы.</span><span class="sxs-lookup"><span data-stu-id="f1a59-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="f1a59-131">В списке **помеченные примеры** выберите отрицательный пример.</span><span class="sxs-lookup"><span data-stu-id="f1a59-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="f1a59-132">В средстве просмотра, расположенном в верхней части статьи, выберите **Метка отсутствует**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="f1a59-133">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-133">Click **Save**.</span></span>
 
<span data-ttu-id="f1a59-134">Получив пять файлов, отображается баннер уведомления о том, что вы перейдете к учебному обучению.</span><span class="sxs-lookup"><span data-stu-id="f1a59-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="f1a59-135">Вы можете выбрать дополнительные документы или перейти к учебному обучению.</span><span class="sxs-lookup"><span data-stu-id="f1a59-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="f1a59-136">Добавление объяснения</span><span class="sxs-lookup"><span data-stu-id="f1a59-136">Add an explanation</span></span>

<span data-ttu-id="f1a59-137">В нашем примере мы создадим объяснение, в котором приводится подсказка о самом формате сущностей и варианты, которые она может содержать в документах примера.</span><span class="sxs-lookup"><span data-stu-id="f1a59-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="f1a59-138">Например, значение даты может быть в разных форматах, например:</span><span class="sxs-lookup"><span data-stu-id="f1a59-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="f1a59-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="f1a59-139">10/14/2019</span></span>
- <span data-ttu-id="f1a59-140">14 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="f1a59-140">October 14, 2019</span></span>
- <span data-ttu-id="f1a59-141">Понедельник, 14 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="f1a59-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="f1a59-142">Чтобы помочь определить *дату начала службы* , можно создать описание шаблона.</span><span class="sxs-lookup"><span data-stu-id="f1a59-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="f1a59-143">В разделе объяснение выберите **создать**, а затем введите имя (например, *Date*).</span><span class="sxs-lookup"><span data-stu-id="f1a59-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="f1a59-144">В поле Тип выберите **шаблон список**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="f1a59-145">Чтобы указать значение, необходимо указать вариант даты, отображаемый в примерах файлов.</span><span class="sxs-lookup"><span data-stu-id="f1a59-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="f1a59-146">Например, если у вас есть форматы дат 0/00/0000, введите любые варианты, которые могут отображаться в документах, например:</span><span class="sxs-lookup"><span data-stu-id="f1a59-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="f1a59-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="f1a59-147">0/0/0000</span></span>
    - <span data-ttu-id="f1a59-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="f1a59-148">0/00/0000</span></span>
    - <span data-ttu-id="f1a59-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="f1a59-149">00/0/0000</span></span>
    - <span data-ttu-id="f1a59-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="f1a59-150">00/00/0000</span></span>
4. <span data-ttu-id="f1a59-151">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="f1a59-152">Использование библиотеки объяснений</span><span class="sxs-lookup"><span data-stu-id="f1a59-152">Use the Explanation library</span></span>

<span data-ttu-id="f1a59-153">Для создания объяснений для таких вещей, как даты, значительно проще использовать библиотеку объяснений, чем вводить все варианты вручную.</span><span class="sxs-lookup"><span data-stu-id="f1a59-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="f1a59-154">Библиотека объяснений — это набор готовых пояснений и шаблонов фраз.</span><span class="sxs-lookup"><span data-stu-id="f1a59-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="f1a59-155">Библиотека пытается предоставить все форматы для стандартных фраз или списков шаблонов, таких как даты, Номера телефонов, почтовый индекс и многие другие.</span><span class="sxs-lookup"><span data-stu-id="f1a59-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="f1a59-156">Для нашего примера *даты начала службы* более эффективно использовать предварительно построенное объяснение *даты* в библиотеке объяснений:</span><span class="sxs-lookup"><span data-stu-id="f1a59-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="f1a59-157">В **разделе объяснение**\* \* выберите **создать**, а затем выберите **из объяснения библиотеки**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="f1a59-158">В библиотеке объяснение выберите элемент **Дата**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="f1a59-159">Вы можете просмотреть все варианты даты, которые будут распознаны.</span><span class="sxs-lookup"><span data-stu-id="f1a59-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="f1a59-160">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-160">Select **Add**.</span></span></br>

    ![Библиотека объяснений](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="f1a59-162">На странице **Создание объяснения** информация о *дате* в библиотеке объяснений будет заполнена полями.</span><span class="sxs-lookup"><span data-stu-id="f1a59-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="f1a59-163">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-163">Select **Save**.</span></span></br>

    ![Библиотека объяснений](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="f1a59-165">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="f1a59-165">Train the model</span></span> 

<span data-ttu-id="f1a59-166">Чтобы начать обучение, сохраните объяснение.</span><span class="sxs-lookup"><span data-stu-id="f1a59-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="f1a59-167">Если в вашей модели достаточно информации для извлечения данных из примеров файлов с метками, вы увидите каждый файл с меткой " **соответствует**".</span><span class="sxs-lookup"><span data-stu-id="f1a59-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Библиотека объяснений](../media/content-understanding/match2.png) 

<span data-ttu-id="f1a59-169">Если в объяснении недостаточно сведений для поиска данных, которые необходимо извлечь, каждый файл будет снабжен **несовпадением**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="f1a59-170">Вы можете щелкнуть несовпадающие файлы, чтобы просмотреть дополнительные сведения о причине несовпадения.</span><span class="sxs-lookup"><span data-stu-id="f1a59-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="f1a59-171">Добавление дополнительного объяснения</span><span class="sxs-lookup"><span data-stu-id="f1a59-171">Add another explanation</span></span>

<span data-ttu-id="f1a59-172">Часто несовпадение указывает на то, что предоставленное объяснение не предоставило достаточно сведений для извлечения значения даты начала службы для соответствия нашим файлам с метками.</span><span class="sxs-lookup"><span data-stu-id="f1a59-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="f1a59-173">Возможно, его потребуется изменить или добавить еще одно объяснение.</span><span class="sxs-lookup"><span data-stu-id="f1a59-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="f1a59-174">В нашем примере обратите внимание на то, что текстовая строка " *Начало обслуживания* " всегда предшествует фактическому значению.</span><span class="sxs-lookup"><span data-stu-id="f1a59-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="f1a59-175">Чтобы помочь определить дату начала службы, мы можем создать фразу объяснение.</span><span class="sxs-lookup"><span data-stu-id="f1a59-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="f1a59-176">В разделе объяснение выберите **создать**, а затем введите имя (например, *Строка префикса*).</span><span class="sxs-lookup"><span data-stu-id="f1a59-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="f1a59-177">В поле Тип выберите пункт **список фраз**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="f1a59-178">Используйте *дату начала службы* в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="f1a59-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="f1a59-179">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f1a59-179">Select **Save**.</span></span>

    ![Библиотека объяснений](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="f1a59-181">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="f1a59-181">Train the model</span></span>

<span data-ttu-id="f1a59-182">При сохранении объяснения вы снова начнете обучение, на этот раз используя оба объяснения в нашем примере.</span><span class="sxs-lookup"><span data-stu-id="f1a59-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="f1a59-183">Если в вашей модели достаточно информации для извлечения данных из примеров файлов с метками, вы увидите каждый файл с меткой " **соответствует**".</span><span class="sxs-lookup"><span data-stu-id="f1a59-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="f1a59-184">Если вы опять получите **несовпадение** с подписанными файлами, вам может потребоваться создать другое пояснение, чтобы предоставить модели дополнительные сведения для определения типа документа, или просмотреть изменения, внесенные в существующие.</span><span class="sxs-lookup"><span data-stu-id="f1a59-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="f1a59-185">Тестирование модели</span><span class="sxs-lookup"><span data-stu-id="f1a59-185">Test your model</span></span>

<span data-ttu-id="f1a59-186">Если вы получили соответствующее приложение с помеченными примерами файлов, теперь вы можете проверить модель на оставшихся файлов примеров без метки.</span><span class="sxs-lookup"><span data-stu-id="f1a59-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="f1a59-187">На домашней странице модели перейдите на вкладку **тест** .  Это приведет к запуску модели для файлов примеров без метки.</span><span class="sxs-lookup"><span data-stu-id="f1a59-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="f1a59-188">В списке **тестовые файлы** будут отображаться файлы, которые будут отображаться, и отобразится, если модель сможет извлекать нужные сведения.</span><span class="sxs-lookup"><span data-stu-id="f1a59-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="f1a59-189">Вы можете использовать эти сведения, чтобы определить эффективность классификатора в определении ваших документов.</span><span class="sxs-lookup"><span data-stu-id="f1a59-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Тестирование файлов](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="f1a59-191">См. также</span><span class="sxs-lookup"><span data-stu-id="f1a59-191">See Also</span></span>
  




