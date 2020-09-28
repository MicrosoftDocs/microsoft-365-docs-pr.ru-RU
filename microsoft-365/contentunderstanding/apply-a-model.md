---
title: Применение модели документа к документу "Общие сведения"
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
description: Узнайте, как применять опубликованную модель к библиотеке документов SharePoint.
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295494"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="98bb8-103">Применение модели документа "Общие сведения" в Microsoft SharePoint Синтекс</span><span class="sxs-lookup"><span data-stu-id="98bb8-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="98bb8-104">Содержимое этой статьи предназначено для проекта Кортекс Private Preview.</span><span class="sxs-lookup"><span data-stu-id="98bb8-104">The content in this article is for the the Project Cortex Private Preview.</span></span> <span data-ttu-id="98bb8-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="98bb8-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="98bb8-106">После публикации этой модели можно применить ее к библиотеке документов SharePoint в клиенте Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="98bb8-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="98bb8-107">Вы можете применить модель только к библиотекам документов, к которым у вас есть доступ.</span><span class="sxs-lookup"><span data-stu-id="98bb8-107">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="98bb8-108">Примените модель к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="98bb8-108">Apply your model to a document library.</span></span>

<span data-ttu-id="98bb8-109">Чтобы применить модель к библиотеке документов SharePoint, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="98bb8-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="98bb8-110">На плитке **применение модели к библиотекам** на плитке Главная страница модели выберите пункт **опубликовать модель**.</span><span class="sxs-lookup"><span data-stu-id="98bb8-110">From the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="98bb8-111">Кроме того, вы можете выбрать  **+ Добавить библиотеку** в разделе **библиотеки с этой моделью** .</span><span class="sxs-lookup"><span data-stu-id="98bb8-111">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Добавление модели в библиотеку](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="98bb8-113">Выберите сайт SharePoint, содержащий библиотеку документов, к которой требуется применить модель.</span><span class="sxs-lookup"><span data-stu-id="98bb8-113">Select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="98bb8-114">Если сайт не отображается в списке, используйте поле поиска, чтобы найти его.</span><span class="sxs-lookup"><span data-stu-id="98bb8-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Выбор сайта](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="98bb8-116">Необходимо иметь разрешения на *Управление списками* или *изменить* права для библиотеки документов, к которой применяется модель.</span><span class="sxs-lookup"><span data-stu-id="98bb8-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="98bb8-117">Выбрав сайт, выберите библиотеку документов, к которой требуется применить модель.</span><span class="sxs-lookup"><span data-stu-id="98bb8-117">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="98bb8-118">В примере выберите библиотеку документов *документы* на сайте *отслеживания дел Contoso* .</span><span class="sxs-lookup"><span data-stu-id="98bb8-118">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Выбор библиотеки документов](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="98bb8-120">Так как модель связана с типом контента, при его применении к библиотеке она создает представление для типа контента с метками, извлеченными в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="98bb8-120">Since the model is associated to a content type, when you apply it to the library it creates a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="98bb8-121">Это представление по умолчанию является представлением библиотеки по умолчанию, но при необходимости можно выбрать не использовать представление по умолчанию, выбрав **Дополнительные параметры** и нажав кнопку **установить новое представление как по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="98bb8-121">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Представление библиотеки](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="98bb8-123">Нажмите кнопку **Добавить** , чтобы применить модель к библиотеке.</span><span class="sxs-lookup"><span data-stu-id="98bb8-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="98bb8-124">На домашней странице модели в разделе **библиотеки с данной моделью** должен отобразиться URL-адрес сайта SharePoint, указанного в списке.</span><span class="sxs-lookup"><span data-stu-id="98bb8-124">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![Выбранная библиотека](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="98bb8-126">Перейдите в библиотеку документов и убедитесь, что вы используете представление "Библиотека документов" модели.</span><span class="sxs-lookup"><span data-stu-id="98bb8-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="98bb8-127">Обратите внимание, что если нажать кнопку сведения рядом с именем библиотеки документов, появится сообщение о том, что модель применена к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="98bb8-127">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![Представление сведений](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="98bb8-129">После применения модели к библиотеке документов можно начать отправку документов на сайт и просмотр результатов.</span><span class="sxs-lookup"><span data-stu-id="98bb8-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="98bb8-130">Модель определяет все файлы с типом контента, связанные с моделью, и отображает их в представлении.</span><span class="sxs-lookup"><span data-stu-id="98bb8-130">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="98bb8-131">Если в вашей модели есть средства извлечения, в представлении отображаются столбцы для данных, извлекаемых из каждого файла.</span><span class="sxs-lookup"><span data-stu-id="98bb8-131">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="98bb8-132">Применение модели к файлам, уже включенным в библиотеку документов</span><span class="sxs-lookup"><span data-stu-id="98bb8-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="98bb8-133">Несмотря на то, что примененная модель обрабатывает все файлы, отправленные в библиотеку документов после применения, можно также выполнить следующие действия, чтобы запустить модель для файлов, которые уже существуют в библиотеке документов перед применением модели:</span><span class="sxs-lookup"><span data-stu-id="98bb8-133">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="98bb8-134">В библиотеке документов выберите файлы, которые будут обрабатываться моделью.</span><span class="sxs-lookup"><span data-stu-id="98bb8-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="98bb8-135">После выбора файлов **классификация и извлечение** отобразятся на ленте библиотека документов.</span><span class="sxs-lookup"><span data-stu-id="98bb8-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="98bb8-136">Выберите **классифицировать и извлечь**.</span><span class="sxs-lookup"><span data-stu-id="98bb8-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="98bb8-137">Выбранные файлы будут добавлены в очередь для обработки.</span><span class="sxs-lookup"><span data-stu-id="98bb8-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Классификация и извлечение](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="98bb8-139">См. также</span><span class="sxs-lookup"><span data-stu-id="98bb8-139">See Also</span></span>
[<span data-ttu-id="98bb8-140">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="98bb8-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="98bb8-141">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="98bb8-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="98bb8-142">Общие сведения о документе</span><span class="sxs-lookup"><span data-stu-id="98bb8-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="98bb8-143">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="98bb8-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  
