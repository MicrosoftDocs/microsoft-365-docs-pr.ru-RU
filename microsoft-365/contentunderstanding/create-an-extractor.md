---
title: Создание средства извлечения
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
description: Узнайте, как создать средство извлечения в Microsoft SharePoint Синтекс.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295460"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="decbf-103">Создание средства извлечения (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="decbf-103">Create an extractor (Preview)</span></span>

<span data-ttu-id="decbf-104">Содержимое этой статьи предназначено для проекта Кортекс Private Preview.</span><span class="sxs-lookup"><span data-stu-id="decbf-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="decbf-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="decbf-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="decbf-106">До или после создания модели классификатора для автоматизации идентификации и классификации определенных типов документов можно дополнительно добавить в модель средства извлечения для извлечения определенных сведений из этих документов.</span><span class="sxs-lookup"><span data-stu-id="decbf-106">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="decbf-107">Например, вам может потребоваться, чтобы модель не только определяла все документы по *обновлению контрактов* , добавленные в библиотеку документов, но и отображала *дату начала службы* для каждого документа в виде столбца в библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="decbf-107">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="decbf-108">Необходимо создать средство извлечения для каждой сущности в документе, который необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="decbf-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="decbf-109">В этом примере необходимо извлечь *дату запуска службы* для каждого документа *продления контракта* , идентифицируемого моделью.</span><span class="sxs-lookup"><span data-stu-id="decbf-109">In the sample, you want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="decbf-110">Это должно произойти, если вы хотите просмотреть представление в библиотеке документов для всех документов по *обновлению контрактов* со столбцом, в котором отображается значение даты начала службы для каждого документа.</span><span class="sxs-lookup"><span data-stu-id="decbf-110">This must happen when you want to see a view in the document library of all the *Contract Renewal* documents with a column showing the Service Start date value for each document.</span></span>

> [!NOTE]
> <span data-ttu-id="decbf-111">Перед созданием средства извлечения необходимо [Добавить файлы примеров](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) , чтобы помочь обучить модель для определения сведений, которые необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="decbf-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="decbf-112">Используйте те же примеры файлов, которые использовались для создания классификатора.</span><span class="sxs-lookup"><span data-stu-id="decbf-112">Use the same sample files you used to create your classifier.</span></span>

## <a name="name-your-extractor"></a><span data-ttu-id="decbf-113">Имя средства извлечения</span><span class="sxs-lookup"><span data-stu-id="decbf-113">Name your extractor</span></span>

1. <span data-ttu-id="decbf-114">На плитке **Создание и обучение извлечений** на странице Домашняя модель выберите команду **обучение изучению**.</span><span class="sxs-lookup"><span data-stu-id="decbf-114">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="decbf-115">На экране **Создание средства извлечения сущностей** введите имя средства извлечения в поле **новое имя средства извлечения** .</span><span class="sxs-lookup"><span data-stu-id="decbf-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="decbf-116">Например, введите **дату начала** для ИТ – службы, если вы хотите извлечь дату начала службы из каждого документа продления контрактов.</span><span class="sxs-lookup"><span data-stu-id="decbf-116">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="decbf-117">Нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="decbf-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="decbf-118">Добавление метки</span><span class="sxs-lookup"><span data-stu-id="decbf-118">Add a label</span></span>

<span data-ttu-id="decbf-119">Следующий шаг — маркировка информации, которую необходимо извлечь в примерах обучающих файлов.</span><span class="sxs-lookup"><span data-stu-id="decbf-119">The next step is to label the information you want to extract in your sample training files.</span></span>

<span data-ttu-id="decbf-120">Создание средства извлечения открывает страницу извлечения.</span><span class="sxs-lookup"><span data-stu-id="decbf-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="decbf-121">Здесь отображается список файлов примеров с первым файлом в списке, отображаемом в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="decbf-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="decbf-122">В средстве просмотра выберите данные, которые необходимо извлечь из файлов.</span><span class="sxs-lookup"><span data-stu-id="decbf-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="decbf-123">Например, если вы хотите извлечь *дату начала обслуживания*, выделите значение даты в первом файле (*понедельник, 14 октября 2019*).</span><span class="sxs-lookup"><span data-stu-id="decbf-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="decbf-124">а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="decbf-124">and then click **Save**.</span></span>  <span data-ttu-id="decbf-125">Значение отображается в списке примеры примеров под столбцом " **метки** ".</span><span class="sxs-lookup"><span data-stu-id="decbf-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="decbf-126">Выберите **следующий файл** для автоматического сохранения и откройте следующий файл в списке в средстве просмотра.</span><span class="sxs-lookup"><span data-stu-id="decbf-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="decbf-127">Или нажмите кнопку **сохранить** , а затем выберите другой файл из списка **помеченные примеры** .</span><span class="sxs-lookup"><span data-stu-id="decbf-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="decbf-128">В средстве просмотра Повторяйте шаги 1 и 2, а затем повторяйте, пока не сохраните метку во всех пяти файлах.</span><span class="sxs-lookup"><span data-stu-id="decbf-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![Дополнительные параметры](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a><span data-ttu-id="decbf-130">Добавление отрицательного примера</span><span class="sxs-lookup"><span data-stu-id="decbf-130">Add a negative example</span></span>

<span data-ttu-id="decbf-131">Подобно тому, как вы добавляете Неотрицательный образец файла при создании классификатора, необходимо добавить к средству извлечения отрицательный образец.</span><span class="sxs-lookup"><span data-stu-id="decbf-131">Similar to how you add a negative sample file when creating a classifier, you need to add a negative sample for the extractor.</span></span> <span data-ttu-id="decbf-132">Это должен быть файл, который не содержит значение даты запуска службы.</span><span class="sxs-lookup"><span data-stu-id="decbf-132">It should be a file that does not contain a "Service Start" date value.</span></span>

1. <span data-ttu-id="decbf-133">В списке **помеченные примеры** выберите отрицательный пример.</span><span class="sxs-lookup"><span data-stu-id="decbf-133">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="decbf-134">В средстве просмотра, расположенном в верхней части статьи, выберите **Метка отсутствует**.</span><span class="sxs-lookup"><span data-stu-id="decbf-134">In the viewer on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="decbf-135">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="decbf-135">Click **Save**.</span></span>
 
<span data-ttu-id="decbf-136">Когда вы помечайте пять файлов, отображается баннер уведомления о том, что вы хотите перейти к учебному обучению.</span><span class="sxs-lookup"><span data-stu-id="decbf-136">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="decbf-137">Вы можете выбрать дополнительные документы или перейти к учебному обучению.</span><span class="sxs-lookup"><span data-stu-id="decbf-137">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="decbf-138">Добавление объяснения</span><span class="sxs-lookup"><span data-stu-id="decbf-138">Add an explanation</span></span>

<span data-ttu-id="decbf-139">В этом примере создается объяснение, в котором приводится подсказка о самом формате объекта и варианты, которые она может иметь в образце документов.</span><span class="sxs-lookup"><span data-stu-id="decbf-139">For the example, you create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="decbf-140">Например, значение даты может быть в разных форматах, например:</span><span class="sxs-lookup"><span data-stu-id="decbf-140">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="decbf-141">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="decbf-141">10/14/2019</span></span>
- <span data-ttu-id="decbf-142">14 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="decbf-142">October 14, 2019</span></span>
- <span data-ttu-id="decbf-143">Понедельник, 14 октября 2019 г.</span><span class="sxs-lookup"><span data-stu-id="decbf-143">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="decbf-144">Чтобы помочь определить *дату начала службы* , вы создадите описание шаблона.</span><span class="sxs-lookup"><span data-stu-id="decbf-144">To help identify the *Service Start Date* you create a pattern explanation.</span></span>

1. <span data-ttu-id="decbf-145">В разделе объяснение выберите **создать** и введите имя (например, *Date*).</span><span class="sxs-lookup"><span data-stu-id="decbf-145">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="decbf-146">В списке Тип выберите **шаблон**.</span><span class="sxs-lookup"><span data-stu-id="decbf-146">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="decbf-147">В поле Value (значение) укажите вариант даты, отображаемый в примерах файлов.</span><span class="sxs-lookup"><span data-stu-id="decbf-147">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="decbf-148">Например, если у вас есть форматы дат 0/00/0000, вы вводите любые варианты, которые появятся в документах, например:</span><span class="sxs-lookup"><span data-stu-id="decbf-148">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="decbf-149">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="decbf-149">0/0/0000</span></span>
    - <span data-ttu-id="decbf-150">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="decbf-150">0/00/0000</span></span>
    - <span data-ttu-id="decbf-151">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="decbf-151">00/0/0000</span></span>
    - <span data-ttu-id="decbf-152">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="decbf-152">00/00/0000</span></span>
4. <span data-ttu-id="decbf-153">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="decbf-153">Select **Save**.</span></span>

### <a name="use-the-explanation-library"></a><span data-ttu-id="decbf-154">Использование библиотеки объяснений</span><span class="sxs-lookup"><span data-stu-id="decbf-154">Use the Explanation library</span></span>

<span data-ttu-id="decbf-155">Для создания объяснений элементов, таких как даты, проще использовать библиотеку объяснений, а не вводить все варианты вручную.</span><span class="sxs-lookup"><span data-stu-id="decbf-155">For creating explanations for items such as dates, it is easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="decbf-156">Библиотека объяснений — это набор готовых пояснений и шаблонов фраз.</span><span class="sxs-lookup"><span data-stu-id="decbf-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="decbf-157">Библиотека предоставляет все форматы для стандартных фраз или списков шаблонов, таких как даты, Номера телефонов, почтовый индекс и т. д.</span><span class="sxs-lookup"><span data-stu-id="decbf-157">The library provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, etc.</span></span> 

<span data-ttu-id="decbf-158">Для примера *даты запуска службы* более эффективно использовать предварительно построенное объяснение *даты* в библиотеке объяснений:</span><span class="sxs-lookup"><span data-stu-id="decbf-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="decbf-159">В **разделе объяснение**выберите **создать**, а затем выберите **из объяснения библиотека**.</span><span class="sxs-lookup"><span data-stu-id="decbf-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="decbf-160">В библиотеке объяснение выберите элемент **Дата**.</span><span class="sxs-lookup"><span data-stu-id="decbf-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="decbf-161">Вы можете просмотреть все варианты распознанной даты.</span><span class="sxs-lookup"><span data-stu-id="decbf-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="decbf-162">Нажмите кнопку **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="decbf-162">Select **Add**.</span></span></br>

    ![Библиотека объяснений](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="decbf-164">На странице **Создание объяснения** сведения о *дате* автоматически заполняют поля в библиотеке пояснения.</span><span class="sxs-lookup"><span data-stu-id="decbf-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="decbf-165">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="decbf-165">Select **Save**.</span></span></br>

    ![Date](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="decbf-167">Обучение модели</span><span class="sxs-lookup"><span data-stu-id="decbf-167">Train the model</span></span> 

<span data-ttu-id="decbf-168">Чтобы сохранить объяснение, Начните обучение.</span><span class="sxs-lookup"><span data-stu-id="decbf-168">Saving your explanation start the training.</span></span> <span data-ttu-id="decbf-169">Если в вашей модели достаточно информации для извлечения данных из примеров файлов с метками, вы увидите каждый файл с меткой " **соответствует**".</span><span class="sxs-lookup"><span data-stu-id="decbf-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![ПОИСКПОЗ](../media/content-understanding/match2.png) 

<span data-ttu-id="decbf-171">Если в объяснении недостаточно сведений для поиска данных, которые необходимо извлечь, каждый файл будет снабжен **несовпадением**.</span><span class="sxs-lookup"><span data-stu-id="decbf-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="decbf-172">Вы можете щелкнуть **несовпадающие** файлы, чтобы просмотреть дополнительные сведения о причине несовпадения.</span><span class="sxs-lookup"><span data-stu-id="decbf-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="decbf-173">Добавление дополнительного объяснения</span><span class="sxs-lookup"><span data-stu-id="decbf-173">Add another explanation</span></span>

<span data-ttu-id="decbf-174">Часто несовпадение указывает на то, что предоставленное объяснение не предоставило достаточно сведений для извлечения значения даты начала службы для соответствия нашим файлам с метками.</span><span class="sxs-lookup"><span data-stu-id="decbf-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="decbf-175">Возможно, его потребуется изменить или добавить еще одно объяснение.</span><span class="sxs-lookup"><span data-stu-id="decbf-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="decbf-176">Обратите внимание, что в качестве значения параметра *Дата начала* для текстовой строки всегда предшествует фактическое значение.</span><span class="sxs-lookup"><span data-stu-id="decbf-176">For the sample, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="decbf-177">Чтобы помочь определить дату начала службы, необходимо создать описание фразы.</span><span class="sxs-lookup"><span data-stu-id="decbf-177">To help identify the Service Start Date, you need ot create a phrase explanation.</span></span>

1. <span data-ttu-id="decbf-178">В разделе объяснение выберите **создать**, а затем введите имя (например, *Строка префикса*).</span><span class="sxs-lookup"><span data-stu-id="decbf-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="decbf-179">В поле Тип выберите пункт **список фраз**.</span><span class="sxs-lookup"><span data-stu-id="decbf-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="decbf-180">Используйте *дату начала службы* в качестве значения.</span><span class="sxs-lookup"><span data-stu-id="decbf-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="decbf-181">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="decbf-181">Select **Save**.</span></span>

    ![Строка префикса](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="decbf-183">Еще раз обучить модель</span><span class="sxs-lookup"><span data-stu-id="decbf-183">Train the model again</span></span>

<span data-ttu-id="decbf-184">При сохранении объяснения вы снова начнете обучение, на этот раз используя оба объяснения в примере.</span><span class="sxs-lookup"><span data-stu-id="decbf-184">Saving the explanation starts the training again, this time using both explanations in the sample.</span></span> <span data-ttu-id="decbf-185">Если в вашей модели достаточно информации для извлечения данных из помеченных примеров файлов, вы увидите каждый файл с меткой " **соответствует**".</span><span class="sxs-lookup"><span data-stu-id="decbf-185">If your model has enough information to extract the data from the labeled sample files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="decbf-186">Если вы опять получите **несовпадение** с подписанными файлами, вам, скорее всего, потребуется создать другое пояснение, чтобы предоставить модели дополнительные сведения для определения типа документа, или рассмотреть возможность внесения изменений в образец модели.</span><span class="sxs-lookup"><span data-stu-id="decbf-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your sample model.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="decbf-187">Тестирование модели</span><span class="sxs-lookup"><span data-stu-id="decbf-187">Test your model</span></span>

<span data-ttu-id="decbf-188">Если вы получили такое же значение в примере файлов с метками, теперь вы можете проверить модель на оставшихся файлов примеров без метки.</span><span class="sxs-lookup"><span data-stu-id="decbf-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled sample files.</span></span>

1. <span data-ttu-id="decbf-189">На домашней странице модели перейдите на вкладку **тест** .  В этом примере выполняется модель для файлов примеров без метки.</span><span class="sxs-lookup"><span data-stu-id="decbf-189">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="decbf-190">В списке **тестовые файлы** показаны примеры файлов, которые отображаются, если модель может извлекать нужные сведения.</span><span class="sxs-lookup"><span data-stu-id="decbf-190">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="decbf-191">Используйте эти сведения, чтобы определить эффективность классификатора в определении ваших документов.</span><span class="sxs-lookup"><span data-stu-id="decbf-191">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![Тестирование файлов](../media/content-understanding/test-filies-extractor.png) 
