---
title: Применение метки хранения к модели документа "Общие сведения"
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: В этой статье описывается применение метки хранения к модели "Общие сведения о модели"
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294927"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="fd729-103">Применение метки хранения к модели документа "Общие сведения"</span><span class="sxs-lookup"><span data-stu-id="fd729-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="fd729-104">Вы можете легко присвоить [метку хранения](https://docs.microsoft.com/microsoft-365/compliance/retention) документу "Общие сведения о модели" в Microsoft SharePoint Синтекс.</span><span class="sxs-lookup"><span data-stu-id="fd729-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="fd729-105">Метки хранения позволяют применять параметры хранения к документам, которые определяются моделями.</span><span class="sxs-lookup"><span data-stu-id="fd729-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="fd729-106">Например, вы хотите, чтобы ваша модель не только определяла документы *оповещений о страховании* , которые были отправлены в библиотеку документов, но также могут *Применить к ним тег хранения,* чтобы эти документы невозможно было удалить из библиотеки документов за указанный период (например, в следующие пять месяцев).</span><span class="sxs-lookup"><span data-stu-id="fd729-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="fd729-107">Вы можете применить уже существующую метку хранения к модели с помощью параметров модели на домашней странице модели.</span><span class="sxs-lookup"><span data-stu-id="fd729-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="fd729-108">Чтобы метки хранения были доступны для применения к содержимому модели, их необходимо [создать и опубликовать в центре соответствия требованиям Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="fd729-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="fd729-109">Добавление метки хранения в модель документа "Общие сведения"</span><span class="sxs-lookup"><span data-stu-id="fd729-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="fd729-110">На домашней странице модели выберите **Параметры модели**.</span><span class="sxs-lookup"><span data-stu-id="fd729-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="fd729-111">В разделе **безопасность и соответствие** в **параметрах модели**выберите меню **метки хранения** , чтобы просмотреть список меток хранения, доступных для применения к модели.</span><span class="sxs-lookup"><span data-stu-id="fd729-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="fd729-112">![Меню меток хранения](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="fd729-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="fd729-113">Выберите метку хранения, которую нужно применить к модели, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fd729-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="fd729-114">После применения метки хранения к модели вы можете применить ее к:</span><span class="sxs-lookup"><span data-stu-id="fd729-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="fd729-115">Новая библиотека документов</span><span class="sxs-lookup"><span data-stu-id="fd729-115">New document library</span></span>
- <span data-ttu-id="fd729-116">Библиотека документов, к которой уже применена модель</span><span class="sxs-lookup"><span data-stu-id="fd729-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="fd729-117">Применение метки хранения к библиотеке документов, к которой уже применена модель</span><span class="sxs-lookup"><span data-stu-id="fd729-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="fd729-118">Если к библиотеке документов уже применена модель "Общие сведения о документе", можно выполнить следующие действия, чтобы синхронизировать обновление меток хранения, чтобы применить его к библиотеке документов:</span><span class="sxs-lookup"><span data-stu-id="fd729-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="fd729-119">На домашней странице модели в разделе **библиотеки с данной моделью** выберите библиотеку документов, к которой необходимо применить обновление метки хранения.</span><span class="sxs-lookup"><span data-stu-id="fd729-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="fd729-120">Нажмите кнопку **синхронизировать**.</span><span class="sxs-lookup"><span data-stu-id="fd729-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="fd729-121">![Модель синхронизации](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="fd729-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="fd729-122">После применения обновления и его синхронизации с моделью можно убедиться, что она была применена, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="fd729-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="fd729-123">В центре управления контентом в разделе **библиотеки с данной моделью** щелкните библиотеку, к которой применен обновленная модель.</span><span class="sxs-lookup"><span data-stu-id="fd729-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="fd729-124">В представлении библиотека документов выберите значок сведений, чтобы проверить свойства модели.</span><span class="sxs-lookup"><span data-stu-id="fd729-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="fd729-125">В списке **активные модели** выберите обновленную модель.</span><span class="sxs-lookup"><span data-stu-id="fd729-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="fd729-126">В разделе **Метка хранения** будет отображаться имя примененной метки хранения.</span><span class="sxs-lookup"><span data-stu-id="fd729-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="fd729-127">На странице представления модели в библиотеке документов отображается новый столбец **метки хранения** .</span><span class="sxs-lookup"><span data-stu-id="fd729-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="fd729-128">Когда модель классифицирует файлы, которые она идентифицирует как принадлежащая типу контента, и отображает их в представлении библиотеки, в столбце Метка хранения будет отображаться имя метки хранения, которая была применена к ней через модель.</span><span class="sxs-lookup"><span data-stu-id="fd729-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="fd729-129">Например, все документы с *уведомлениями о страховки* , которые идентифицирует ваша модель, также будут иметь к ним метку хранения *бизнес-* файлов, что предотвращает их удаление из библиотеки документов в течение пяти месяцев.</span><span class="sxs-lookup"><span data-stu-id="fd729-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="fd729-130">При попытке удалить файл из библиотеки документов отображается сообщение об ошибке "не разрешено" из-за примененной метки хранения.</span><span class="sxs-lookup"><span data-stu-id="fd729-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd729-131">См. также</span><span class="sxs-lookup"><span data-stu-id="fd729-131">See Also</span></span>
[<span data-ttu-id="fd729-132">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="fd729-132">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="fd729-133">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="fd729-133">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="fd729-134">Общие сведения о документе</span><span class="sxs-lookup"><span data-stu-id="fd729-134">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="fd729-135">Создание модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="fd729-135">Create a form processing model</span></span>](create-a-form-processing-model.md)  
