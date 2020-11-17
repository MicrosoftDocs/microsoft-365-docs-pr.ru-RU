---
title: Создание модели обработки форм
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Создание модели обработки форм в Microsoft SharePoint Syntex.
ms.openlocfilehash: aed918d899fe7c5e3c49b733d2411c178e9b98d0
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087695"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="e9dbd-103">Создание модели обработки форм в Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="e9dbd-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

<span data-ttu-id="e9dbd-104">Использование [AI Builder](https://docs.microsoft.com/ai-builder/overview) — функция в Microsoft PowerApps — пользователи SharePoint Syntex могут создавать [модель обработки форм](form-processing-overview.md) непосредственно из библиотеки документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-104">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - SharePoint Syntex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="e9dbd-105">Создание модели обработки форм состоит из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="e9dbd-105">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="e9dbd-106">Шаг 1. Создание модели обработки для создания типа контента</span><span class="sxs-lookup"><span data-stu-id="e9dbd-106">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="e9dbd-107">Шаг 2. Добавление и анализ примеров файлов</span><span class="sxs-lookup"><span data-stu-id="e9dbd-107">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="e9dbd-108">Шаг 3. Выбор полей формы</span><span class="sxs-lookup"><span data-stu-id="e9dbd-108">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="e9dbd-109">Шаг 4. Обучение и тестирование модели</span><span class="sxs-lookup"><span data-stu-id="e9dbd-109">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="e9dbd-110">Шаг 5. Публикация модели</span><span class="sxs-lookup"><span data-stu-id="e9dbd-110">Step 5: Publish your model</span></span>
 - <span data-ttu-id="e9dbd-111">Шаг 6. Использование модели</span><span class="sxs-lookup"><span data-stu-id="e9dbd-111">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="e9dbd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e9dbd-112">Requirements</span></span>

<span data-ttu-id="e9dbd-p101">Модель обработки форм можно создать только в библиотеках документов SharePoint, для которых она включена. Если обработка формы включена, вы можете просмотреть **AI Builder** **"Создать модель обработки форм"** в меню **Автоматизация** в библиотеке документов. Если вам требуется обработка в библиотеке документов, необходимо обратиться к администратору SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p101">You can only create a form processing model in SharePoint document libraries for which it is enabled. If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.  If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![Создание модели AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="e9dbd-117">Шаг 1. Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="e9dbd-117">Step 1: Create a form processing model</span></span>

<span data-ttu-id="e9dbd-118">Первым шагом в создании модели обработки формы является присвоение ей имени и создание нового типа содержимого и нового представления библиотеки документов.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-118">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="e9dbd-119">В библиотеке документов выберите меню **Автоматизация**, выберите **AI Builder** и щелкните **Создать модель обработки форм**.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-119">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![Создание модели](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="e9dbd-121">В области **Новая модель обработки форм**, в поле **Имя** введите имя модели (например, *Заказы на покупку*).</span><span class="sxs-lookup"><span data-stu-id="e9dbd-121">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![Новая модель обработки форм](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="e9dbd-p102">При создании модели обработки форм создается новый тип содержимого SharePoint. Тип содержимого SharePoint представляет собой категорию документов, имеющих общие характеристики и использующих коллекцию столбцов или свойств метаданных для определенного содержимого. Управление типами содержимого SharePoint осуществляется с помощью [коллекции типов содержимого]().</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p102">When you create a form processing model, you create a new SharePoint content type. A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content. SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="e9dbd-126">Выберите **Дополнительные параметры**, если вы хотите сопоставить эту модель с существующим типом содержимого в коллекции типов содержимого SharePoint, чтобы использовать ее схему.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-126">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="e9dbd-p103">Ваша модель создает новое представление в вашей библиотеке документов для извлеченных данных. Если вы не хотите использовать это представление по умолчанию, снимите флажок **Сделать представлением по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p103">Your model creates a new view in your document library for your extracted data. If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="e9dbd-129">Нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-129">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="e9dbd-130">Шаг 2. Добавление и анализ документов</span><span class="sxs-lookup"><span data-stu-id="e9dbd-130">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="e9dbd-p104">После создания новой модели обработки форм браузер открывает новую страницу модели обработки форм PowerApps AI Builder. На этой странице вы можете добавить и проанализировать примеры документов.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p104">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page. On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="e9dbd-133">При поиске примеров файлов для использования см. раздел [Требования к входному документу модели обработки формы и советы по оптимизации](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="e9dbd-133">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="e9dbd-p105">Выберите **Добавить документы**, чтобы начать добавление примеров документов, проанализированных для определения именованных пар значений, которые могут быть извлечены. После этого можно выбрать **Отправить из локального хранилища**, **SharePoint** или **Хранилище BLOB-объектов Azure**. Для обучения необходимо использовать не менее пяти файлов.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p105">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted. You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**. You need to use at least five files for training.</span></span>

2. <span data-ttu-id="e9dbd-p106">После добавления файлов нажмите **Анализировать**, чтобы проверить наличие общих сведений для всех файлов. Это может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p106">After adding files, select **Analyze** to check for any information common is all files. This may take several minutes to complete.</span></span></br> 
 
    ![Анализ файлов](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="e9dbd-141">После анализа файлов на странице **Выберите поля формы, которые хотите сохранить** выберите файл, чтобы просмотреть найденные поля.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-141">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![Выбор полей формы](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="e9dbd-143">Шаг 3. Выбор полей формы</span><span class="sxs-lookup"><span data-stu-id="e9dbd-143">Step 3: Select your form fields</span></span>

<span data-ttu-id="e9dbd-p107">Проанализировав документы на наличие полей, вы можете просмотреть найденные поля и определить те, которые нужно сохранить. Сохраненные поля отображаются в виде столбцов в представлении библиотеки документов вашей модели и показывают значения, извлеченные из каждого документа.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p107">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save. Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="e9dbd-146">На следующей странице показан один из примеров файлов и выделены все общие поля, которые были автоматически обнаружены системой.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-146">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![Страница выбора полей](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="e9dbd-p108">Выберите поля, которые нужно сохранить, и установите флажок, чтобы подтвердить выбор. Например, в модели "Заказ на покупку" можно выбрать поля *Дата*, *Заказ на покупку* и *Итого*. Обратите внимание, что вы также можете переименовать поле, если захотите.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p108">Select the fields that you want to save and select the checkbox to confirm your selection. For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.  Note that you can also choose to rename a field if you choose. </span></span></br>

    ![Выбор заказа на покупку №](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="e9dbd-p109">Если поле не было обнаружено при анализе, его все равно можно добавить. Выделите сведения, которые нужно извлечь, и в поле имени введите нужное имя. Затем установите флажок. Обратите внимание, что вам необходимо подтвердить необнаруженные поля в оставшихся примерах файлов.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p109">If a field was not detected by analysis, you can still choose to add it. Highlight the information you want to extract, and in the name box type in the name you want. Then select the check box. Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="e9dbd-156">Щелкните **Подтвердить поля** после выбора полей, которые нужно сохранить.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-156">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![Подтверждение полей после их выбора](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="e9dbd-p110">На странице **Выбор полей формы, которые нужно сохранить** будет указано количество выбранных полей. Нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p110">On the **Select the form fields you want to save** page, it shows the number of fields you have selected. Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="e9dbd-160">Шаг 4. Обучение и тестирование модели</span><span class="sxs-lookup"><span data-stu-id="e9dbd-160">Step 4: Train and test your model</span></span>

<span data-ttu-id="e9dbd-161">После выбора полей, которые нужно сохранить, на странице **Сведения о модели** можно начать обучение и протестировать модель.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-161">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="e9dbd-p111">На странице **Сведения о модели** сохраненные поля будут показаны в разделе **Выбранные поля**. Чтобы начать обучение по примерам файлов, выберите **Обучение**. Обратите внимание, что это займет несколько минут.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p111">On the **Model Summary** page, the saved fields will show in the **Selected fields** section. Select **Train** to begin training on your example files. Note that this may take a few minutes to complete.</span></span></br>

     ![Обучение по выбранным полям](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="e9dbd-166">Когда появится уведомление о том, что обучение завершено, выберите **Перейти на страницу сведений**.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-166">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="e9dbd-p112">На странице **Сведения о модели** вы можете проверить, как работает ваша модель, выбрав **Быстрый тест**. Это позволяет перетаскивать файлы на страницу и проверять, обнаруживаются ли поля.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p112">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**. This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![Подтверждение полей](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="e9dbd-170">Когда появится уведомление о том, что обучение завершено, выберите **Перейти на страницу сведений**.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-170">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="e9dbd-p113">На странице **Сведения о модели** проверьте, как работает ваша модель, выбрав **Быстрый тест**. Это позволяет перетаскивать файлы на страницу и проверять, обнаруживаются ли поля.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p113">On the **Model details** page, choose to test how your model works by selecting **Quick test**. This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="e9dbd-173">Шаг 5. Публикация модели</span><span class="sxs-lookup"><span data-stu-id="e9dbd-173">Step 5: Publish your model</span></span>

1. <span data-ttu-id="e9dbd-174">Если вы удовлетворены результатами вашей модели, выберите **Опубликовать**, чтобы сделать ее доступной для использования.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-174">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="e9dbd-p114">После публикации модели выберите **Использовать модель**. В результате создается поток PowerAutomate, который может выполняться в вашей библиотеке документов SharePoint и извлекает поля, идентифицированные в модели. Затем выберите **Создать поток**.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p114">After the model is published, select **Use model**. This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="e9dbd-177">После завершения вы увидите сообщение: **Поток успешно создан**.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-177">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="e9dbd-178">Шаг 6. Использование модели</span><span class="sxs-lookup"><span data-stu-id="e9dbd-178">Step 6: Use your model</span></span>

<span data-ttu-id="e9dbd-179">После публикации модели и создания потока PowerAutomate вы можете использовать модель в библиотеке документов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-179">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="e9dbd-180">После публикации модели выберите **Перейти в SharePoint**, чтобы перейти в библиотеку документов.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-180">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="e9dbd-181">В представлении модели библиотеки документов обратите внимание, что выбранные вами поля теперь отображаются в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-181">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![Модель библиотеки документов применена](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="e9dbd-183">Обратите внимание, что информационная ссылка рядом с **документами** указывает на то, что к этой библиотеке документов применяется модель обработки форм.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-183">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![Кнопка сведений](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="e9dbd-p115">Отправка файлов в вашу библиотеку документов. Все файлы, которые модель определяет как собственный тип содержимого, содержат список файлов в вашем представлении и отображают извлеченные данные в столбцах.</span><span class="sxs-lookup"><span data-stu-id="e9dbd-p115">Upload files to your document library. Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![Готово](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="e9dbd-188">См. также</span><span class="sxs-lookup"><span data-stu-id="e9dbd-188">See Also</span></span>
  
[<span data-ttu-id="e9dbd-189">Документация Power Automate</span><span class="sxs-lookup"><span data-stu-id="e9dbd-189">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="e9dbd-190">Учебный курс. Повышение продуктивности бизнеса с помощью AI Builder</span><span class="sxs-lookup"><span data-stu-id="e9dbd-190">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
