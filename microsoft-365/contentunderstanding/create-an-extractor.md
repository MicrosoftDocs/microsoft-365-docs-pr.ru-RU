---
title: Создание средства извлечения
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Узнайте, как создать средство извлечения в Microsoft SharePoint Syntex.
ms.openlocfilehash: d68cc8b8c337c1ae6740eb5775576a54279b8389
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321813"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="c2a21-103">Создание средства извлечения (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c2a21-103">Create an extractor (Preview)</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="c2a21-104">До или после того, как вы создадите модель классификатора для автоматизации идентификации и классификации определенных типов документов, вы можете при необходимости выбрать добавить средство извлечения в вашу модель для извлечения определенной информации из этих документов.</span><span class="sxs-lookup"><span data-stu-id="c2a21-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="c2a21-105">Например, вам может потребоваться, чтобы ваша модель не только идентифицировала все документы о *возобновлении контракта* документы, добавленные в вашу библиотеку документов, но также отображала *дату начала службы* для каждого документа в виде значения столбца в библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="c2a21-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="c2a21-106">Необходимо создать средство извлечения для каждого объекта в документе, который необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="c2a21-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="c2a21-107">В нашем примере нужно извлечь  **дату начала службы**  для каждого документа о  **возобновлении контракта** , который определяется моделью.</span><span class="sxs-lookup"><span data-stu-id="c2a21-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="c2a21-108">Необходимо, чтобы в библиотеке документов были видны все документы о  **возобновлении контракта**  со столбцом, в котором отображается значение даты **начала службы** для каждого документа.</span><span class="sxs-lookup"><span data-stu-id="c2a21-108">We want to be able to see a view in the document library of all **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="c2a21-109">Чтобы создать средство извлечения, используйте те же файлы, которые вы ранее загрузили для обучения классификатора.</span><span class="sxs-lookup"><span data-stu-id="c2a21-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="c2a21-110">Назовите ваше средство извлечения</span><span class="sxs-lookup"><span data-stu-id="c2a21-110">Name your extractor</span></span>

1. <span data-ttu-id="c2a21-111">На домашней странице модели в разделе **Создание и обучение средств извлечения** нажмите **Обучение средства извлечения**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="c2a21-112">На экране **Средство извлечения нового объекта** введите имя для вашего средства извлечения в поле **Имя нового средства извлечения**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="c2a21-113">Например, вы можете назвать его **Дата начала службы**, если вы хотите извлечь дату начала службы из каждого документа о возобновлении контракта.</span><span class="sxs-lookup"><span data-stu-id="c2a21-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="c2a21-114">Кроме того, вы можете повторно использовать уже созданный столбец (например, столбец управляемых метаданных).</span><span class="sxs-lookup"><span data-stu-id="c2a21-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
3. <span data-ttu-id="c2a21-115">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-115">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="c2a21-116">Добавление метки</span><span class="sxs-lookup"><span data-stu-id="c2a21-116">Add a label</span></span>

<span data-ttu-id="c2a21-117">Следующий этап — пометка объекта, который вы хотите извлечь, в ваших примерах обучающих файлов.</span><span class="sxs-lookup"><span data-stu-id="c2a21-117">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="c2a21-118">Создание средства извлечения открывает страницу средства извлечения.</span><span class="sxs-lookup"><span data-stu-id="c2a21-118">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="c2a21-119">Здесь вы видите список ваших примеров файлов, причем первый файл в списке отображается в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="c2a21-119">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="c2a21-120">В средстве просмотра выберите данные, которые нужно извлечь из файлов.</span><span class="sxs-lookup"><span data-stu-id="c2a21-120">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="c2a21-121">Например, если вы хотите извлечь *Дату начала службы*, вы можете выделить значение даты в первом файле (*Понедельник, 14 октября 2019*).</span><span class="sxs-lookup"><span data-stu-id="c2a21-121">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="c2a21-122">и затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-122">and then click **Save**.</span></span>  <span data-ttu-id="c2a21-123">Вы должны увидеть отображение значения из файла в списке «Примеры с метками» в столбце **Метка**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-123">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="c2a21-124">Нажмите кнопку **Следующий файл** для автоматического сохранения и откройте следующий файл в списке в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="c2a21-124">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="c2a21-125">Или выберите **Сохранить**, а затем выберите другой файл в списке **Примеры с метками**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-125">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="c2a21-126">В средстве просмотра повторите шаги 1 и 2, затем повторяйте, пока не сохраните метку во всех пяти файлах.</span><span class="sxs-lookup"><span data-stu-id="c2a21-126">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Дополнительные параметры](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="c2a21-128">После того, как вы отметите пять файлов, отобразится баннер с уведомлением о переходе к обучению.</span><span class="sxs-lookup"><span data-stu-id="c2a21-128">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="c2a21-129">Вы можете добавить метки для большего количества документов или перейти к обучению.</span><span class="sxs-lookup"><span data-stu-id="c2a21-129">You can choose to more label more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="c2a21-130">Добавление объяснений</span><span class="sxs-lookup"><span data-stu-id="c2a21-130">Add an explanation</span></span>

<span data-ttu-id="c2a21-131">В нашем примере мы собираемся создать объяснение, которое дает подсказку о самом формате объекта и его вариациях в примерах документов.</span><span class="sxs-lookup"><span data-stu-id="c2a21-131">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="c2a21-132">Например, значение даты может быть в нескольких различных форматах, например:</span><span class="sxs-lookup"><span data-stu-id="c2a21-132">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="c2a21-133">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="c2a21-133">10/14/2019</span></span>
- <span data-ttu-id="c2a21-134">14 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="c2a21-134">October 14, 2019</span></span>
- <span data-ttu-id="c2a21-135">Понедельник, 14 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="c2a21-135">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="c2a21-136">Чтобы помочь определить *дату начала службы*, можно создать объяснение к шаблону.</span><span class="sxs-lookup"><span data-stu-id="c2a21-136">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="c2a21-137">В разделе «Объяснения» выберите **Создать** и введите имя (например, *Дата*).</span><span class="sxs-lookup"><span data-stu-id="c2a21-137">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="c2a21-138">Для «Типа» выберите **Список шаблонов**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-138">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="c2a21-139">Для «Значения» укажите варианты даты в том виде, в каком он указан в файлах примеров.</span><span class="sxs-lookup"><span data-stu-id="c2a21-139">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="c2a21-140">Например, если у вас есть форматы даты, которые отображаются как 0/00/0000, вы вводите любые варианты, которые появляются в ваших документах, например:</span><span class="sxs-lookup"><span data-stu-id="c2a21-140">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="c2a21-141">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="c2a21-141">0/0/0000</span></span>
    - <span data-ttu-id="c2a21-142">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="c2a21-142">0/00/0000</span></span>
    - <span data-ttu-id="c2a21-143">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="c2a21-143">00/0/0000</span></span>
    - <span data-ttu-id="c2a21-144">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="c2a21-144">00/00/0000</span></span>
4. <span data-ttu-id="c2a21-145">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-145">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="c2a21-146">Дополнительные сведения о типах объяснения см. в разделе [Типы объяснений](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span><span class="sxs-lookup"><span data-stu-id="c2a21-146">For more learn more about explanation types, see [Explanation types](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="c2a21-147">Использование библиотеки объяснений</span><span class="sxs-lookup"><span data-stu-id="c2a21-147">Use the Explanation library</span></span>

<span data-ttu-id="c2a21-148">Для создания объяснений для таких элементов, как даты, проще [использовать библиотеку объяснений](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library), чем вручную вводить все варианты.</span><span class="sxs-lookup"><span data-stu-id="c2a21-148">For creating explanations for items such as dates, it is easier to [use the explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) than to manually enter all variations.</span></span> <span data-ttu-id="c2a21-149">Библиотека объяснений представляет собой набор предварительно созданных объяснений фраз и шаблонов.</span><span class="sxs-lookup"><span data-stu-id="c2a21-149">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="c2a21-150">Библиотека пытается предоставить все форматы для общих списков фраз или шаблонов, таких как даты, номера телефонов, почтовые индексы и многие другие.</span><span class="sxs-lookup"><span data-stu-id="c2a21-150">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="c2a21-151">Для примера *Дата начала службы* более эффективно использовать предварительно созданное объяснение для *даты* в библиотеке объяснений:</span><span class="sxs-lookup"><span data-stu-id="c2a21-151">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="c2a21-152">В **разделе объяснений**, выберите **Создать**, и затем выберите **Из библиотеки объяснений**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-152">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="c2a21-153">В библиотеке объяснений выберите **Дата**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-153">From the explanation library, select **Date**.</span></span> <span data-ttu-id="c2a21-154">Вы можете просмотреть все варианты распознаваемой даты.</span><span class="sxs-lookup"><span data-stu-id="c2a21-154">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="c2a21-155">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-155">Select **Add**.</span></span></br>

    ![Библиотека объяснений](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="c2a21-157">На странице **Создание объяснения** информация о *дате* из библиотеки объяснений автоматически заполняет поля.</span><span class="sxs-lookup"><span data-stu-id="c2a21-157">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="c2a21-158">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-158">Select **Save**.</span></span></br>

    ![Дата](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="c2a21-160">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="c2a21-160">Train the model</span></span> 

<span data-ttu-id="c2a21-161">Сохранение объяснения начинает обучение.</span><span class="sxs-lookup"><span data-stu-id="c2a21-161">Saving your explanation start the training.</span></span> <span data-ttu-id="c2a21-162">Если в вашей модели достаточно сведений для извлечения данных из помеченных примеров файлов, вы увидите каждый файл с пометкой **Соответствует**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-162">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Соответствует](../media/content-understanding/match2.png) 

<span data-ttu-id="c2a21-164">Если в объяснении недостаточно сведений для поиска данных, которые нужно извлечь, каждый файл будет помечен как **Не соответствует**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-164">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="c2a21-165">Вы можете щелкнуть **Несоответствующие** файлы, чтобы узнать больше о причинах несоответствия.</span><span class="sxs-lookup"><span data-stu-id="c2a21-165">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="c2a21-166">Добавление другого объяснения</span><span class="sxs-lookup"><span data-stu-id="c2a21-166">Add another explanation</span></span>

<span data-ttu-id="c2a21-167">Часто несовпадение указывает на то, что мы не предоставили достаточно сведений для извлечения значения даты начала службы, соответствующего нашим помеченным файлам.</span><span class="sxs-lookup"><span data-stu-id="c2a21-167">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="c2a21-168">Возможно, вам потребуется изменить его или добавить другое объяснение.</span><span class="sxs-lookup"><span data-stu-id="c2a21-168">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="c2a21-169">В нашем примере обратите внимание, что текстовая строка *Начало даты службы* всегда предшествует действительному значению.</span><span class="sxs-lookup"><span data-stu-id="c2a21-169">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="c2a21-170">Чтобы помочь определить дату начала службы, необходимо создать объяснение фразы.</span><span class="sxs-lookup"><span data-stu-id="c2a21-170">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="c2a21-171">В разделе «Объяснения» выберите **Создать** и введите имя (например *Строка префикса*).</span><span class="sxs-lookup"><span data-stu-id="c2a21-171">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="c2a21-172">Для «Типа» выберите **Список фраз**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-172">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="c2a21-173">Используйте в качестве значения *Дату начала службы*.</span><span class="sxs-lookup"><span data-stu-id="c2a21-173">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="c2a21-174">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-174">Select **Save**.</span></span>

    ![Строка префикса](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="c2a21-176">Повторное обучение модели</span><span class="sxs-lookup"><span data-stu-id="c2a21-176">Train the model again</span></span>

<span data-ttu-id="c2a21-177">Сохранение объяснения запускает обучение снова, на этот раз с использованием обоих объяснений в примере.</span><span class="sxs-lookup"><span data-stu-id="c2a21-177">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="c2a21-178">Если в вашей модели достаточно сведений для извлечения данных из помеченных примеров файлов, вы увидите каждый файл с пометкой **Соответствует**.</span><span class="sxs-lookup"><span data-stu-id="c2a21-178">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="c2a21-179">Если вы снова получаете сообщение **Не соответствует** в помеченных файлах, вероятно, вам потребуется создать другое объяснение, чтобы предоставить модели больше сведений для определения типа документа или рассмотреть возможность внесения изменений в существующие.</span><span class="sxs-lookup"><span data-stu-id="c2a21-179">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="c2a21-180">Тестирование модели</span><span class="sxs-lookup"><span data-stu-id="c2a21-180">Test your model</span></span>

<span data-ttu-id="c2a21-181">Если вы получили сообщение о соответствии помеченных файлов примеров, вы можете протестировать свою модель на оставшихся примерах файлов без меток.</span><span class="sxs-lookup"><span data-stu-id="c2a21-181">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="c2a21-182">Это полезный шаг для оценки «пригодности» или готовности модели перед ее использованием путем тестирования ее на файлах, которые модель ранее не видела.</span><span class="sxs-lookup"><span data-stu-id="c2a21-182">This is a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="c2a21-183">На домашней странице модели откройте вкладку **Тестирование**. Это запустит модель на примерах файлов без меток.</span><span class="sxs-lookup"><span data-stu-id="c2a21-183">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="c2a21-184">В списке **Тестовые файлы** отображаются ваши примеры файлов, чтобы показать, может ли модель извлечь необходимые вам сведения.</span><span class="sxs-lookup"><span data-stu-id="c2a21-184">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="c2a21-185">Используйте эти сведения, чтобы определить эффективность классификатора в определении ваших документов.</span><span class="sxs-lookup"><span data-stu-id="c2a21-185">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Протестируйте ваши файлы](../media/content-understanding/test-filies-extractor.png) 
