---
title: Создание модели обработки форм (Предварительная версия)
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
description: Создание модели обработки форм в Project кортекс.
ms.openlocfilehash: 733baf24d8a484571ba9882fdda2633dc2ce0504
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612778"
---
# <a name="create-a-form-processing-model-preview"></a><span data-ttu-id="504e7-103">Создание модели обработки форм (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="504e7-103">Create a form processing model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="504e7-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="504e7-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="504e7-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="504e7-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="504e7-106">С помощью [AI Builder](https://docs.microsoft.com/ai-builder/overview) — компонент в Microsoft PowerApps-Project Кортекс пользователи могут создавать [модели обработки форм](form-processing-overview.md) непосредственно из библиотеки документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="504e7-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="504e7-107">Создание модели обработки форм состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="504e7-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="504e7-108">Шаг 1: создание модели "из обработки" для создания типа контента</span><span class="sxs-lookup"><span data-stu-id="504e7-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="504e7-109">Шаг 2: Добавление и анализ файлов примеров</span><span class="sxs-lookup"><span data-stu-id="504e7-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="504e7-110">Шаг 3: выбор полей формы</span><span class="sxs-lookup"><span data-stu-id="504e7-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="504e7-111">Шаг 4: обучение и тестирование модели</span><span class="sxs-lookup"><span data-stu-id="504e7-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="504e7-112">Шаг 5: Публикация модели</span><span class="sxs-lookup"><span data-stu-id="504e7-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="504e7-113">Шаг 6: использование модели</span><span class="sxs-lookup"><span data-stu-id="504e7-113">Step 6: Use your model</span></span>


## <a name="requirements"></a><span data-ttu-id="504e7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="504e7-114">Requirements</span></span>

<span data-ttu-id="504e7-115">Модель обработки форм можно создать только в библиотеках документов SharePoint, в которых она включена.</span><span class="sxs-lookup"><span data-stu-id="504e7-115">You can only create a form processing model in SharePoint document libraries in which it is enabled.</span></span> <span data-ttu-id="504e7-116">Если обработка формы включена, **AI-построитель** **"Создание модели обработки формы"** будет доступен в меню " **Автоматизация** " библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="504e7-116">If form processing is enabled, you will be able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="504e7-117">Если вы хотите включить обработку в вашей библиотеке документов, обратитесь к администратору.</span><span class="sxs-lookup"><span data-stu-id="504e7-117">If you need from processing enabled on your document library, contact your admin.</span></span>

 ![Создание модели AI-построителя](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="504e7-119">Шаг 1: создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="504e7-119">Step 1: Create a Form Processing model</span></span>

<span data-ttu-id="504e7-120">Первым шагом при создании модели обработки формы является назначение имени для создания нового типа контента и создания нового представления библиотеки документов для нее.</span><span class="sxs-lookup"><span data-stu-id="504e7-120">The first step in creating a form processing model is to name it to create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="504e7-121">В библиотеке документов выберите пункт **Автоматизация** меню, выберите **AI Builder**, а затем выберите **создать модель обработки формы**.</span><span class="sxs-lookup"><span data-stu-id="504e7-121">In your document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Создание модели AI-построителя](../media/content-understanding/create-ai-builder-model.png)</br>
2. <span data-ttu-id="504e7-123">В области **Новая модель обработки форм** в поле **имя** введите имя модели (например, *заказы на покупку*).</span><span class="sxs-lookup"><span data-stu-id="504e7-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Новая модель обработки форм](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="504e7-125">При создании модели обработки формы создается новый тип контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="504e7-125">When you create a form processing model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="504e7-126">Тип контента SharePoint представляет категорию документов, имеющих общие характеристики и совместное использование коллекции столбцов или свойств метаданных для конкретного содержимого.</span><span class="sxs-lookup"><span data-stu-id="504e7-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="504e7-127">Управление типами контента SharePoint осуществляется с помощью [коллекции типов контента]().</span><span class="sxs-lookup"><span data-stu-id="504e7-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="504e7-128">Выберите **Дополнительные параметры** , если вы хотите сопоставить эту модель с существующим типом контента в коллекции типов контента SharePoint, чтобы использовать ее схему.</span><span class="sxs-lookup"><span data-stu-id="504e7-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="504e7-129">Ваша модель создаст новое представление в библиотеке документов для извлеченных данных.</span><span class="sxs-lookup"><span data-stu-id="504e7-129">Your model will create a new view in your document library for your extracted data.</span></span> <span data-ttu-id="504e7-130">Если вы не хотите использовать представление по умолчанию, снимите флажок **задать представление по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="504e7-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>
5. <span data-ttu-id="504e7-131">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="504e7-131">Select **Create**.</span></span>


## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="504e7-132">Шаг 2: Добавление и анализ документов</span><span class="sxs-lookup"><span data-stu-id="504e7-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="504e7-133">После создания новой модели обработки форм браузер откроет новую страницу модели обработки форм AI-построителя.</span><span class="sxs-lookup"><span data-stu-id="504e7-133">After you create your new form processing model, your browser will open a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="504e7-134">На этой странице вы можете добавить и проанализировать документы с примерами.</span><span class="sxs-lookup"><span data-stu-id="504e7-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!Note]
> <span data-ttu-id="504e7-135">Если вы ищете примеры файлов, которые необходимо использовать, ознакомьтесь с [требованиями к входным документом модели обработки форм и советами по оптимизации](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="504e7-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Построитель AI для Power Apps](../media/content-understanding/powerapps.png)</br> 
 

1. <span data-ttu-id="504e7-137">Нажмите кнопку **добавить документы** , чтобы начать добавлять документы с примерами, которые анализируются, чтобы определить, какие именованные пары значений можно извлечь.</span><span class="sxs-lookup"><span data-stu-id="504e7-137">Click **Add documents** to begin adding example documents that are analyzed to determine what named value pairs can be extracted.</span></span> <span data-ttu-id="504e7-138">Вы можете выбрать **загрузку из локального хранилища**, **SharePoint**или **хранилища BLOB-объектов Azure**.</span><span class="sxs-lookup"><span data-stu-id="504e7-138">You can choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="504e7-139">Для обучения необходимо использовать по крайней мере пять файлов.</span><span class="sxs-lookup"><span data-stu-id="504e7-139">You will need to use at least five files for training.</span></span>
2. <span data-ttu-id="504e7-140">После добавления файлов нажмите кнопку **анализ** , чтобы проверить, все ли общие сведения являются файлами.</span><span class="sxs-lookup"><span data-stu-id="504e7-140">After adding your files, select **Analyze** to check for any information that is common is all files.</span></span> <span data-ttu-id="504e7-141">Обратите внимание, что выполнение этого действия может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="504e7-141">Note that this may take several minutes to complete.</span></span></br> 
 
    ![Анализ файлов](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="504e7-143">После анализа **выберите поля формы** , которые необходимо сохранить, и щелкните файл, чтобы увидеть обнаруженные поля.</span><span class="sxs-lookup"><span data-stu-id="504e7-143">After they have been analyzed, in the **Select the form fields you want to save** page, click the file to see the fields that were detected.</span></span></br>

    ![Выбор полей формы](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="504e7-145">Шаг 3: выбор полей формы</span><span class="sxs-lookup"><span data-stu-id="504e7-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="504e7-146">После анализа документов для полей можно увидеть, какие поля были найдены и какие из них вы хотите сохранить.</span><span class="sxs-lookup"><span data-stu-id="504e7-146">After analyzing your documents for fields, you can now see which fields were found, and which ones you want to save.</span></span> <span data-ttu-id="504e7-147">Сохраненные поля будут отображаться в виде столбцов в представлении библиотеки документов модели и будут показывать значения, извлеченные из каждого документа.</span><span class="sxs-lookup"><span data-stu-id="504e7-147">Saved fields will display as columns in your model's document library view and will show the values extracted from each document.</span></span>

1. <span data-ttu-id="504e7-148">На следующей странице отобразится один из примеров файлов и будут выделены все общие поля, автоматически обнаруженные системой.</span><span class="sxs-lookup"><span data-stu-id="504e7-148">The next page will display one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Выбор полей формы](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="504e7-150">Выберите поля, которые необходимо сохранить, и установите флажок, чтобы подтвердить выбор.</span><span class="sxs-lookup"><span data-stu-id="504e7-150">Select the fields you want to save, and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="504e7-151">Например, в модели заказа на покупку можно выбрать поля *даты*, *ЗП*и *итоги* .</span><span class="sxs-lookup"><span data-stu-id="504e7-151">For example, in the Purchase Order model, you can choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="504e7-152">Обратите внимание, что вы также можете изменить имя поля.</span><span class="sxs-lookup"><span data-stu-id="504e7-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Выбор ЗП #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="504e7-154">Если поле не было обнаружено в ходе анализа, вы по-прежнему можете добавить его.</span><span class="sxs-lookup"><span data-stu-id="504e7-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="504e7-155">Выделите данные, которые необходимо извлечь, и введите в поле Имя имя, которое вы хотите присвоить.</span><span class="sxs-lookup"><span data-stu-id="504e7-155">Highlight the information you want to extract, and in the name box type in the name you want to give it.</span></span> <span data-ttu-id="504e7-156">Затем нажмите кнопку проверить.</span><span class="sxs-lookup"><span data-stu-id="504e7-156">Then select the check.</span></span> <span data-ttu-id="504e7-157">Обратите внимание, что вам потребуется подтвердить необнаруженные поля в оставшихся примерах файлов.</span><span class="sxs-lookup"><span data-stu-id="504e7-157">Note that you will need to confirm undetected fields in your remaining example files.</span></span>
4. <span data-ttu-id="504e7-158">После выбора полей, которые необходимо сохранить, нажмите кнопку **подтвердить поля** .</span><span class="sxs-lookup"><span data-stu-id="504e7-158">Click **Confirm fields** after you have selected the fields you want to save.</span></span> </br>
 
    ![Поля подтверждения](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="504e7-160">На странице **выберите поля формы, которые необходимо сохранить** , отображается количество выбранных полей.</span><span class="sxs-lookup"><span data-stu-id="504e7-160">On the **Select the form fields you want to save** page, it will show the number of fields you have selected.</span></span> <span data-ttu-id="504e7-161">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="504e7-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="504e7-162">Шаг 4: обучение и тестирование модели</span><span class="sxs-lookup"><span data-stu-id="504e7-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="504e7-163">После выбора полей, которые необходимо сохранить, страница **сводки по модели** позволит вам обучить и тестировать модель.</span><span class="sxs-lookup"><span data-stu-id="504e7-163">After selecting the fields you want to save, the **Model Summary** page will let you train and test your model.</span></span>

1. <span data-ttu-id="504e7-164">На странице **Сводка по модели** сохраненные поля отобразятся в разделе **Выбранные поля** .</span><span class="sxs-lookup"><span data-stu-id="504e7-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="504e7-165">Выберите **обучение** , чтобы начать обучение с примерами файлов.</span><span class="sxs-lookup"><span data-stu-id="504e7-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="504e7-166">Обратите внимание, что выполнение этого действия может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="504e7-166">Note that this may take a few minutes to complete.</span></span></br>
    <span data-ttu-id="504e7-167">![Поля подтверждения](../media/content-understanding/select-fields-train.png)</span><span class="sxs-lookup"><span data-stu-id="504e7-167">![Confirm fields](../media/content-understanding/select-fields-train.png)</span></span></br> 
2. <span data-ttu-id="504e7-168">Когда появится уведомление о том, что обучение завершено, нажмите **Перейти на страницу сведений**.</span><span class="sxs-lookup"><span data-stu-id="504e7-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 
3. <span data-ttu-id="504e7-169">На странице **сведения о модели** можно проверить, как работает модель, выбрав пункт **Быстрая проверка**.</span><span class="sxs-lookup"><span data-stu-id="504e7-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="504e7-170">Это позволяет перетаскивать файлы на страницу и просматривать, обнаруживаются ли поля.</span><span class="sxs-lookup"><span data-stu-id="504e7-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="504e7-171">Шаг 5: Публикация модели</span><span class="sxs-lookup"><span data-stu-id="504e7-171">Step 5: Publish your model</span></span>



1. <span data-ttu-id="504e7-172">Если вы удовлетворены результатами вашей модели, нажмите кнопку **опубликовать** , чтобы сделать ее доступной для использования.</span><span class="sxs-lookup"><span data-stu-id="504e7-172">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>
2. <span data-ttu-id="504e7-173">После публикации модели выберите **использовать модель**.</span><span class="sxs-lookup"><span data-stu-id="504e7-173">After the model published, select **Use model**.</span></span> <span data-ttu-id="504e7-174">При этом будет создан поток Повераутомате, который будет выполняться в библиотеке документов SharePoint, и будут извлечены поля, идентифицированные в модели.</span><span class="sxs-lookup"><span data-stu-id="504e7-174">This creates a PowerAutomate flow that will run in your SharePoint document library and will extract the fields that have been identified in the model.</span></span> <span data-ttu-id="504e7-175">Выберите **создать блок**.</span><span class="sxs-lookup"><span data-stu-id="504e7-175">Select **Create Flow**.</span></span>  
3. <span data-ttu-id="504e7-176">После завершения вы увидите сообщение о том, что **ваш процесс был успешно создан**.</span><span class="sxs-lookup"><span data-stu-id="504e7-176">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="504e7-177">Шаг 6: использование модели</span><span class="sxs-lookup"><span data-stu-id="504e7-177">Step 6: Use your model</span></span>

<span data-ttu-id="504e7-178">После того как вы публикуете модель и создаете ее Повераутомате, вы можете использовать модель в библиотеке документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="504e7-178">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="504e7-179">После публикации модели выберите **Перейти в SharePoint** , чтобы перейти в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="504e7-179">After publishing your model , select **Go to SharePoint** to go to your document library.</span></span>
2. <span data-ttu-id="504e7-180">Обратите внимание, что в представлении модель библиотеки документов выбранные поля будут отображаться в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="504e7-180">On your document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Библиотека документов с примененной моделью](../media/content-understanding/doc-lib-view.png)</br> 

    <span data-ttu-id="504e7-182">Кроме того, обратите внимание на то, что информационная ссылка рядом с **документом** будет иметь значение, что модель обработки форм применена к этой библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="504e7-182">Also notice that the information link next to **Documents** will note that a forms processing model is applied to this document library.</span></span>

    ![Влекать](../media/content-understanding/info-button.png)</br>  

3. <span data-ttu-id="504e7-184">Отправка файлов в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="504e7-184">Upload files to your document library.</span></span> <span data-ttu-id="504e7-185">Все файлы, идентифицированные моделью в качестве типа контента, будут отображать файлы в представлении и будут отображать извлеченные данные в столбцах.</span><span class="sxs-lookup"><span data-stu-id="504e7-185">Any files that the model identifies as it's content type will list the files in your view, and will display the extracted data in the columns.</span></span></br>

    ![Влекать](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a><span data-ttu-id="504e7-187">См. также</span><span class="sxs-lookup"><span data-stu-id="504e7-187">See Also</span></span>
  
[<span data-ttu-id="504e7-188">Документация по автоматизации управления питанием</span><span class="sxs-lookup"><span data-stu-id="504e7-188">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="504e7-189">Обучение: повышение производительности бизнеса с помощью построителя AI</span><span class="sxs-lookup"><span data-stu-id="504e7-189">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




