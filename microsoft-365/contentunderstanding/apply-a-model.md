---
title: Применение модели осмысления документации к библиотеке документов
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Сведения о применении опубликованной модели к библиотеке документов SharePoint
ms.openlocfilehash: 17da1e37f72504ac5e0e26c0dd190efced08d285
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080784"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="4e501-103">Применение модели осмысления документации в Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="4e501-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="4e501-104">После публикации модель осмысления документации можно применить к одной или нескольким библиотекам документов SharePoint в клиенте Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e501-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="4e501-105">Вы можете применить модель только к тем библиотекам документов, к которым у вас есть доступ.</span><span class="sxs-lookup"><span data-stu-id="4e501-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="4e501-106">Примените модель к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="4e501-106">Apply your model to a document library.</span></span>

<span data-ttu-id="4e501-107">Чтобы применить модель к библиотеке документов SharePoint, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4e501-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="4e501-108">На домашней странице модели на плитке **Применение модели к библиотекам** выберите **Опубликовать модель**.</span><span class="sxs-lookup"><span data-stu-id="4e501-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="4e501-109">Вы также можете выбрать пункт **+ Добавить библиотеку** в разделе **Библиотеки с этой моделью**.</span><span class="sxs-lookup"><span data-stu-id="4e501-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Добавление модели в библиотеку](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="4e501-111">Затем вы можете выбрать сайт SharePoint, содержащий библиотеку документов, к которой нужно применить модель.</span><span class="sxs-lookup"><span data-stu-id="4e501-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="4e501-112">Если сайт не отображается в списке, используйте поле поиска, чтобы найти его.</span><span class="sxs-lookup"><span data-stu-id="4e501-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Выбор сайта](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="4e501-114">Вам потребуются разрешения *Управление списком* или права на *редактирование* для библиотеки документов, к которой применяется модель.</span><span class="sxs-lookup"><span data-stu-id="4e501-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="4e501-115">Выбрав сайт, выберите библиотеку документов, к которой нужно применить модель.</span><span class="sxs-lookup"><span data-stu-id="4e501-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="4e501-116">В приведенном примере выберите библиотеку документов *Документы* на сайте *Отслеживание обращения в Contoso*.</span><span class="sxs-lookup"><span data-stu-id="4e501-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Выбор библиотеки документов](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="4e501-118">Поскольку модель связана с типом контента, при ее применении к библиотеке будет добавлен тип контента и его представление с извлеченными метками в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="4e501-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="4e501-119">Это представление по умолчанию является представлением библиотеки по умолчанию, но при желании можно не использовать его как таковое. Для этого выберите **Дополнительные параметры** и отмените выбор пункта **Использовать это новое представление по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="4e501-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Представление библиотеки](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="4e501-121">Нажмите кнопку **Добавить**, чтобы применить модель к библиотеке.</span><span class="sxs-lookup"><span data-stu-id="4e501-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="4e501-122">На домашней странице модели в разделе **Библиотеки с этой моделью** вы увидите URL-адрес указанного сайта SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4e501-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Выбранная библиотека](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="4e501-124">Перейдите в библиотеку документов и убедитесь, что вы находитесь в представлении библиотеки документов, к которой применяется модель.</span><span class="sxs-lookup"><span data-stu-id="4e501-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="4e501-125">Обратите внимание, что при нажатии кнопки сведений рядом с именем библиотеки документов появляется сообщение о том, что к библиотеке документов применена модель.</span><span class="sxs-lookup"><span data-stu-id="4e501-125">Notice that if you select the information button next to the document library name, a message notes that the document library has a model applied to it.</span></span>

    ![Представление сведений](../media/content-understanding/info-du.png)</br> 

    <span data-ttu-id="4e501-127">Чтобы просмотреть подробные сведения о любой модели, примененной к библиотеке документов, выберите **Просмотр активных моделей**.</span><span class="sxs-lookup"><span data-stu-id="4e501-127">You can the select **View active models** to see details about any models that are applied to the document library.</span></span>

8. <span data-ttu-id="4e501-128">В области **Активные модели** можно просмотреть модели, примененные к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="4e501-128">In the **Active models** pane, you can see the models that are applied to the document library.</span></span> <span data-ttu-id="4e501-129">Выберите модель, чтобы просмотреть дополнительные сведения о ней, например описание модели, кто ее опубликовал, а также сведения о том, применяет ли модель метку хранения к файлам, которые она классифицирует.</span><span class="sxs-lookup"><span data-stu-id="4e501-129">Select a model to see more details about it, such as a description of the model, who published the model, and if the model applies a retention label to the files it classifies.</span></span>

    ![Область "Активные модели"](../media/content-understanding/active-models.png)</br> 

<span data-ttu-id="4e501-131">После применения модели к библиотеке документов можно начать отправку документов на сайт и просмотр результатов.</span><span class="sxs-lookup"><span data-stu-id="4e501-131">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="4e501-132">Модель определяет все файлы со связанным типом контента и выводит их в представлении.</span><span class="sxs-lookup"><span data-stu-id="4e501-132">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="4e501-133">Если модель содержит средства извлечения, в представлении отображаются столбцы для данных, извлекаемых из каждого файла.</span><span class="sxs-lookup"><span data-stu-id="4e501-133">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="4e501-134">Применение модели к файлам, уже находящимся в библиотеке документов</span><span class="sxs-lookup"><span data-stu-id="4e501-134">Apply the model to files already in the document library</span></span>

<span data-ttu-id="4e501-135">В результате применения модели выполняется обработка всех файлов, отправленных в библиотеку документов. Чтобы запустить модель для файлов, которые уже находились в библиотеке документов до применения модели, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4e501-135">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="4e501-136">В библиотеке документов выберите файлы, которые нужно обработать с помощью модели.</span><span class="sxs-lookup"><span data-stu-id="4e501-136">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="4e501-137">После того как вы выберете файлы, на ленте библиотеки документов появится элемент **Классификация и извлечение**.</span><span class="sxs-lookup"><span data-stu-id="4e501-137">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="4e501-138">Выберите элемент **Классификация и извлечение**.</span><span class="sxs-lookup"><span data-stu-id="4e501-138">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="4e501-139">Выбранные файлы будут добавлены в очередь на обработку.</span><span class="sxs-lookup"><span data-stu-id="4e501-139">The files you selected will be added to the queue to be processed.</span></span>

      ![Классификация и извлечение](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> <span data-ttu-id="4e501-141">Вы можете скопировать отдельные файлы в библиотеку и применить их к модели, но не к папкам.</span><span class="sxs-lookup"><span data-stu-id="4e501-141">You can copy individual files to a library and apply them to a model, but not folders.</span></span>

### <a name="the-classification-date-field"></a><span data-ttu-id="4e501-142">Поле "Дата классификации"</span><span class="sxs-lookup"><span data-stu-id="4e501-142">The Classification Date field</span></span>

<span data-ttu-id="4e501-143">Если к библиотеке документов применяется модель обработки форм или осмысления документации SharePoint Syntex, поле <b>Дата классификации</b> добавляется в схему библиотеки.</span><span class="sxs-lookup"><span data-stu-id="4e501-143">When a SharePoint Syntex document understanding or form processing model is applied to a document library, a <b> Classification date </b> field is included in the library schema.</span></span> <span data-ttu-id="4e501-144">По умолчанию это поле не заполнено, но если документы обрабатываются и классифицируются моделью, в это поле будет добавлена метка даты и времени завершения.</span><span class="sxs-lookup"><span data-stu-id="4e501-144">By default this field is empty, but when documents are processed and classified by a model, this field is updated with a date-time stamp of completion.</span></span> 

   ![Столбец "Дата классификации"](../media/content-understanding/class-date-column.png)</br> 

<span data-ttu-id="4e501-146">Поле "Дата классификации" используется [триггером <b>Когда файл классифицируется моделью осмысления контента</b>](https://docs.microsoft.com/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) для запуска потока Power Automate, после того как модель осмысления контента Syntex завершит обработку файла и обновление поля "Дата классификации".</span><span class="sxs-lookup"><span data-stu-id="4e501-146">The Classification date field is used by the [<b>When a file is classified by a content understanding model</b> trigger](https://docs.microsoft.com/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) to run a Power Automate flow after a Syntex content understanding model has finished processing a file and updated the "Classification date" field.</span></span>

   ![Триггер потока](../media/content-understanding/trigger.png)</br>

<span data-ttu-id="4e501-148">Затем триггер <b>Когда файл классифицируется моделью осмысления контента</b> можно использовать для запуска другого рабочего процесса с использованием любой извлеченной из файла информации.</span><span class="sxs-lookup"><span data-stu-id="4e501-148">The <b>When a file is classified by a content understanding model</b> trigger can then be used to start another workflow using any  extracted information from the file.</span></span>



## <a name="see-also"></a><span data-ttu-id="4e501-149">См. также</span><span class="sxs-lookup"><span data-stu-id="4e501-149">See Also</span></span>
[<span data-ttu-id="4e501-150">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="4e501-150">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="4e501-151">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="4e501-151">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="4e501-152">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="4e501-152">Document Understanding overview</span></span>](document-understanding-overview.md)


