---
title: Создание модели обработки форм
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
description: Создание модели обработки форм в Microsoft SharePoint Синтекс.
ms.openlocfilehash: f61dbad837173c412daefb7285c4abff10a01817
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295482"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="4a4e1-103">Создание модели обработки форм в Microsoft SharePoint Синтекс</span><span class="sxs-lookup"><span data-stu-id="4a4e1-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="4a4e1-104">Содержимое этой статьи предназначено для проекта Кортекс Private Preview.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="4a4e1-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="4a4e1-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="4a4e1-106">С помощью [AI Builder](https://docs.microsoft.com/ai-builder/overview) — компонент в Microsoft PowerApps-Project Кортекс пользователи могут создавать [модели обработки форм](form-processing-overview.md) непосредственно из библиотеки документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="4a4e1-107">Создание модели обработки форм состоит из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="4a4e1-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="4a4e1-108">Шаг 1: создание модели "из обработки" для создания типа контента</span><span class="sxs-lookup"><span data-stu-id="4a4e1-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="4a4e1-109">Шаг 2: Добавление и анализ файлов примеров</span><span class="sxs-lookup"><span data-stu-id="4a4e1-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="4a4e1-110">Шаг 3: выбор полей формы</span><span class="sxs-lookup"><span data-stu-id="4a4e1-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="4a4e1-111">Шаг 4: обучение и тестирование модели</span><span class="sxs-lookup"><span data-stu-id="4a4e1-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="4a4e1-112">Шаг 5: Публикация модели</span><span class="sxs-lookup"><span data-stu-id="4a4e1-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="4a4e1-113">Шаг 6: использование модели</span><span class="sxs-lookup"><span data-stu-id="4a4e1-113">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="4a4e1-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4a4e1-114">Requirements</span></span>

<span data-ttu-id="4a4e1-115">Модель обработки форм можно создать только в библиотеках документов SharePoint, для которых она включена.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-115">You can only create a form processing model in SharePoint document libraries for which it is enabled.</span></span> <span data-ttu-id="4a4e1-116">Если обработка формы включена, в меню " **Автоматизация** " библиотеки документов можно просмотреть **AI-построитель** **"Создание модели обработки формы"** .</span><span class="sxs-lookup"><span data-stu-id="4a4e1-116">If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="4a4e1-117">Если вы хотите включить обработку в вашей библиотеке документов, необходимо обратиться к администратору SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-117">If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![Создание модели AI-построителя](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="4a4e1-119">Шаг 1: создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="4a4e1-119">Step 1: Create a form Processing model</span></span>

<span data-ttu-id="4a4e1-120">Первым шагом при создании модели обработки формы является присвойте ему имя и создайте новый тип контента и создайте для него представление библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-120">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="4a4e1-121">В библиотеке документов выберите пункт **Автоматизация** меню, выберите **AI Builder**, а затем выберите **создать модель обработки формы**.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-121">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Создание модели](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="4a4e1-123">В области **Новая модель обработки форм** в поле  **имя** введите имя модели (например, *заказы на покупку*).</span><span class="sxs-lookup"><span data-stu-id="4a4e1-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Новая модель обработки форм](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="4a4e1-125">При создании модели обработки формы создается новый тип контента SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-125">When you create a form processing model, you create a new SharePoint content type.</span></span> <span data-ttu-id="4a4e1-126">Тип контента SharePoint представляет категорию документов, имеющих общие характеристики и совместное использование коллекции столбцов или свойств метаданных для конкретного содержимого.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="4a4e1-127">Управление типами контента SharePoint осуществляется с помощью [коллекции типов контента]().</span><span class="sxs-lookup"><span data-stu-id="4a4e1-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="4a4e1-128">Выберите **Дополнительные параметры** , если вы хотите сопоставить эту модель с существующим типом контента в коллекции типов контента SharePoint, чтобы использовать ее схему.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="4a4e1-129">Модель создает новое представление в библиотеке документов для извлеченных данных.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-129">Your model creates a new view in your document library for your extracted data.</span></span> <span data-ttu-id="4a4e1-130">Если вы не хотите использовать представление по умолчанию, снимите флажок **задать представление по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="4a4e1-131">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-131">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="4a4e1-132">Шаг 2: Добавление и анализ документов</span><span class="sxs-lookup"><span data-stu-id="4a4e1-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="4a4e1-133">После создания новой модели обработки формы браузер открывает новую страницу модели обработки форм AI-построителя.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-133">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="4a4e1-134">На этой странице вы можете добавить и проанализировать документы с примерами.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="4a4e1-135">Если вы ищете примеры файлов, которые необходимо использовать, ознакомьтесь с [требованиями к входным документом модели обработки форм и советами по оптимизации](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="4a4e1-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Построитель AI для Power Apps](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="4a4e1-137">Выберите **добавить документы** , чтобы начать добавление примеров документов, проанализированных для определения пар именованных значений, которые можно извлечь.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-137">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted.</span></span> <span data-ttu-id="4a4e1-138">Затем можно выбрать **загрузку из локального хранилища**, **SharePoint**или **хранилища больших двоичных объектов Azure**.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-138">You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="4a4e1-139">Для обучения необходимо использовать по крайней мере пять файлов.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-139">You need to use at least five files for training.</span></span>

2. <span data-ttu-id="4a4e1-140">После добавления файлов выберите пункт **анализ** , чтобы проверить, все ли общие сведения являются файлами.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-140">After adding files, select **Analyze** to check for any information common is all files.</span></span> <span data-ttu-id="4a4e1-141">Выполнение может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-141">This may take several minutes to complete.</span></span></br> 
 
    ![Анализ файлов](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="4a4e1-143">После анализа файлов в списке **выберите поля формы, которые необходимо сохранить** . Выберите файл, чтобы просмотреть обнаруженные поля.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-143">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![Выбор полей формы](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="4a4e1-145">Шаг 3: выбор полей формы</span><span class="sxs-lookup"><span data-stu-id="4a4e1-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="4a4e1-146">После анализа документов для полей можно просмотреть найденные поля и определить, какие из них нужно сохранить.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-146">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save.</span></span> <span data-ttu-id="4a4e1-147">Сохраненные поля отображаются в виде столбцов в представлении библиотеки документов модели и отображают значения, извлеченные из каждого документа.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-147">Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="4a4e1-148">На следующей странице отображается один из ваших примеров файлов, а также выделяются все общие поля, автоматически обнаруженные системой.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-148">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Страница "Выбор полей"](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="4a4e1-150">Выберите поля, которые необходимо сохранить, и установите флажок, чтобы подтвердить выбор.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-150">Select the fields that you want to save and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="4a4e1-151">Например, в модели заказа на покупку выберите, чтобы выбрать поля *даты*, *ЗП*и *итоги* .</span><span class="sxs-lookup"><span data-stu-id="4a4e1-151">For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="4a4e1-152">Обратите внимание, что вы также можете изменить имя поля.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![Выбор ЗП #](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="4a4e1-154">Если поле не было обнаружено в ходе анализа, вы по-прежнему можете добавить его.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="4a4e1-155">Выделите данные, которые необходимо извлечь, и введите в поле имя нужное имя.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-155">Highlight the information you want to extract, and in the name box type in the name you want.</span></span> <span data-ttu-id="4a4e1-156">Затем установите флажок.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-156">Then select the check box.</span></span> <span data-ttu-id="4a4e1-157">Обратите внимание, что вам необходимо подтвердить необнаруженные поля в оставшихся примерах файлов.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-157">Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="4a4e1-158">После выбора полей, которые необходимо сохранить, нажмите кнопку **подтвердить поля** .</span><span class="sxs-lookup"><span data-stu-id="4a4e1-158">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![Подтверждение полей после выбора полей](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="4a4e1-160">На странице **Выбор полей формы, которые необходимо сохранить** , отображается количество выбранных полей.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-160">On the **Select the form fields you want to save** page, it shows the number of fields you have selected.</span></span> <span data-ttu-id="4a4e1-161">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="4a4e1-162">Шаг 4: обучение и тестирование модели</span><span class="sxs-lookup"><span data-stu-id="4a4e1-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="4a4e1-163">После выбора полей, которые необходимо сохранить, страница **сводки по модели** позволяет обучить и тестировать модель.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-163">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="4a4e1-164">На странице **Сводка по модели** сохраненные поля отобразятся в разделе **Выбранные поля** .</span><span class="sxs-lookup"><span data-stu-id="4a4e1-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="4a4e1-165">Выберите **обучение** , чтобы начать обучение с примерами файлов.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="4a4e1-166">Обратите внимание, что выполнение этого действия может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-166">Note that this may take a few minutes to complete.</span></span></br>

     ![Выбор полей обучения](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="4a4e1-168">Когда появится уведомление о том, что обучение завершено, нажмите **Перейти на страницу сведений**.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="4a4e1-169">На странице **сведения о модели** можно проверить, как работает модель, выбрав пункт **Быстрая проверка**.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="4a4e1-170">Это позволяет перетаскивать файлы на страницу и просматривать, обнаруживаются ли поля.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![Поля подтверждения](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="4a4e1-172">Когда появится уведомление о том, что обучение завершено, нажмите **Перейти на страницу сведений**.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-172">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="4a4e1-173">На странице **сведения о модели** выберите, чтобы проверить, как работает модель, выбрав пункт **Быстрая проверка**.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-173">On the **Model details** page, choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="4a4e1-174">Это позволяет перетаскивать файлы на страницу и просматривать, обнаруживаются ли поля.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-174">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="4a4e1-175">Шаг 5: Публикация модели</span><span class="sxs-lookup"><span data-stu-id="4a4e1-175">Step 5: Publish your model</span></span>

1. <span data-ttu-id="4a4e1-176">Если вы удовлетворены результатами вашей модели, нажмите кнопку **опубликовать** , чтобы сделать ее доступной для использования.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-176">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="4a4e1-177">После публикации модели выберите **использовать модель**.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-177">After the model is published, select **Use model**.</span></span> <span data-ttu-id="4a4e1-178">При этом создается поток Повераутомате, который может выполняться в библиотеке документов SharePoint, и извлекаются поля, идентифицированные в модели, а затем выберите команду **создать поток**.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-178">This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="4a4e1-179">После завершения вы увидите сообщение о том, что **ваш процесс был успешно создан**.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-179">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="4a4e1-180">Шаг 6: использование модели</span><span class="sxs-lookup"><span data-stu-id="4a4e1-180">Step 6: Use your model</span></span>

<span data-ttu-id="4a4e1-181">После того как вы публикуете модель и создаете ее Повераутомате, вы можете использовать модель в библиотеке документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-181">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="4a4e1-182">После публикации модели выберите **Перейти в SharePoint** , чтобы перейти в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-182">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="4a4e1-183">В представлении модель библиотеки документов Обратите внимание, что выбранные поля будут отображаться в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-183">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Примененная модель библиотеки документов](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="4a4e1-185">Обратите внимание, что в информационную ссылку рядом с **документом** заметок, к которым применяется модель обработки форм, применяется к этой библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-185">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![Кнопка "сведения"](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="4a4e1-187">Отправка файлов в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-187">Upload files to your document library.</span></span> <span data-ttu-id="4a4e1-188">Все файлы, идентифицированные моделью в качестве типа контента, имеют список файлов в представлении и отображает извлеченные данные в столбцах.</span><span class="sxs-lookup"><span data-stu-id="4a4e1-188">Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![Готово](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="4a4e1-190">См. также</span><span class="sxs-lookup"><span data-stu-id="4a4e1-190">See Also</span></span>
  
[<span data-ttu-id="4a4e1-191">Документация по автоматизации управления питанием</span><span class="sxs-lookup"><span data-stu-id="4a4e1-191">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="4a4e1-192">Обучение: повышение производительности бизнеса с помощью построителя AI</span><span class="sxs-lookup"><span data-stu-id="4a4e1-192">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
