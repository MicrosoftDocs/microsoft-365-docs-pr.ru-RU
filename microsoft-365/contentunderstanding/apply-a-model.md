---
title: Применение модели документа к библиотеке документов (Предварительная версия)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Узнайте, как применить опубликованную модель к библиотеке документов SharePoint.
ms.openlocfilehash: 8a4931f4b7a936caeb99d7f8c07deefdac62919b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950252"
---
# <a name="apply-a-document-understanding-model-preview"></a><span data-ttu-id="c637c-103">Применение модели "Общие сведения о документе" (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="c637c-103">Apply a document understanding model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="c637c-104">Содержимое этой статьи предназначено для Кортексного предварительного просмотра Project.</span><span class="sxs-lookup"><span data-stu-id="c637c-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="c637c-105">[Узнайте больше о Кортекс Project](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="c637c-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="c637c-106">После публикации этой модели можно применить ее к библиотеке документов SharePoint в клиенте Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c637c-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!Note]
> <span data-ttu-id="c637c-107">Вы сможете применить модель только к библиотекам документов, к которым у вас есть доступ.</span><span class="sxs-lookup"><span data-stu-id="c637c-107">You will only be able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="c637c-108">Примените модель к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="c637c-108">Apply your model to a document library.</span></span>

<span data-ttu-id="c637c-109">Чтобы применить модель к библиотеке документов SharePoint, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c637c-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="c637c-110">На плитке " **применить модель к библиотекам** " на плитке Главная страница модели выберите пункт **опубликовать модель**.</span><span class="sxs-lookup"><span data-stu-id="c637c-110">On the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="c637c-111">Кроме того, вы можете выбрать  **+ Добавить библиотеку** в разделе **библиотеки с этой моделью** .</span><span class="sxs-lookup"><span data-stu-id="c637c-111">Or you can  select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![Добавление модели в библиотеку](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="c637c-113">Затем можно выбрать сайт SharePoint, содержащий библиотеку документов, к которой требуется применить модель.</span><span class="sxs-lookup"><span data-stu-id="c637c-113">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="c637c-114">Если сайт не отображается в списке, используйте поле поиска, чтобы найти его.</span><span class="sxs-lookup"><span data-stu-id="c637c-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![Выбор сайта](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > <span data-ttu-id="c637c-116">Необходимо иметь разрешения на *Управление списками* или *изменить* права для библиотеки документов, к которой применяется модель.</span><span class="sxs-lookup"><span data-stu-id="c637c-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="c637c-117">После выбора сайта необходимо выбрать библиотеку документов, к которой требуется применить модель.</span><span class="sxs-lookup"><span data-stu-id="c637c-117">After selecting the site, you then need to select the document library to which you want to apply the model.</span></span> <span data-ttu-id="c637c-118">В этом примере мы выбираете *библиотеку документов Documents на сайте* *отслеживания дел Contoso* .</span><span class="sxs-lookup"><span data-stu-id="c637c-118">In the example, we are selecting the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![Выбор библиотеки документов](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="c637c-120">Так как модель связана с типом контента, при его применении к библиотеке он создаст представление для типа контента с метками, которые вы извлекли в виде столбцов.</span><span class="sxs-lookup"><span data-stu-id="c637c-120">Since the model is associated to a content type, when you apply it to the library it will create a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="c637c-121">Это представление по умолчанию будет представлением библиотеки по умолчанию, но при желании можно не использовать представление по умолчанию, выбрав **Дополнительные параметры** и отменить **установку нового представления по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="c637c-121">This view will be the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![Представление библиотеки](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="c637c-123">Нажмите кнопку **Добавить** , чтобы применить модель к библиотеке.</span><span class="sxs-lookup"><span data-stu-id="c637c-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="c637c-124">На домашней странице модели в разделе **библиотеки с данной моделью** отображается URL-адрес сайта SharePoint, указанного в списке.</span><span class="sxs-lookup"><span data-stu-id="c637c-124">On the model home page, in the **Libraries with this model** section, you will see the URL to the SharePoint site listed.</span></span></br>

    ![Представление библиотеки](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="c637c-126">Перейдите в библиотеку документов и убедитесь, что вы используете представление "Библиотека документов" модели.</span><span class="sxs-lookup"><span data-stu-id="c637c-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="c637c-127">Обратите внимание, что если нажать кнопку сведения рядом с именем библиотеки документов, появится сообщение о том, что модель применена к библиотеке документов.</span><span class="sxs-lookup"><span data-stu-id="c637c-127">You'll notice that if you select the information button next to the document library name, a message will note that your model has been applied to the document library.</span></span>

    ![Представление библиотеки](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="c637c-129">После применения модели к библиотеке документов можно начать отправку документов на сайт и просмотр результатов.</span><span class="sxs-lookup"><span data-stu-id="c637c-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="c637c-130">Модель будет определять все файлы с типом контента, связанные с моделью, и будет отображать их в представлении.</span><span class="sxs-lookup"><span data-stu-id="c637c-130">The model will identify any files with model’s associated content type and will list them in your view.</span></span> <span data-ttu-id="c637c-131">Если в вашей модели есть средства извлечения, представление будет отображать столбцы для извлекаемых данных из каждого файла.</span><span class="sxs-lookup"><span data-stu-id="c637c-131">If your model has any extractors, the view will display columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="c637c-132">Применение модели к файлам, уже включенным в библиотеку документов</span><span class="sxs-lookup"><span data-stu-id="c637c-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="c637c-133">Несмотря на то, что примененная модель будет обрабатывать все файлы, отправленные в библиотеку документов после применения, можно также выполнить следующие действия, чтобы запустить модель для файлов, которые уже существовали в библиотеке документов перед применением модели:</span><span class="sxs-lookup"><span data-stu-id="c637c-133">While an applied model will process all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already existed in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="c637c-134">В библиотеке документов выберите файлы, которые будут обрабатываться моделью.</span><span class="sxs-lookup"><span data-stu-id="c637c-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="c637c-135">После выбора файлов **классификация и извлечение** отобразятся на ленте библиотека документов.</span><span class="sxs-lookup"><span data-stu-id="c637c-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="c637c-136">Выберите **классифицировать и извлечь**.</span><span class="sxs-lookup"><span data-stu-id="c637c-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="c637c-137">Выбранные файлы будут добавлены в очередь для обработки.</span><span class="sxs-lookup"><span data-stu-id="c637c-137">The files you selected will be added to the queue to be processed.</span></span>

      ![Классификация и извлечение](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a><span data-ttu-id="c637c-139">См. также</span><span class="sxs-lookup"><span data-stu-id="c637c-139">See Also</span></span>
[<span data-ttu-id="c637c-140">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="c637c-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="c637c-141">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="c637c-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="c637c-142">Общие сведения о документе</span><span class="sxs-lookup"><span data-stu-id="c637c-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="c637c-143">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="c637c-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  




