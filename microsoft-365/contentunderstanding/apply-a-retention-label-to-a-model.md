---
title: Применение метки хранения к модели понимания документа
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: В этой статье объясняется, как применить метку хранения к модели понимания документа
ms.openlocfilehash: 2e6d300b63a173d01488406485cffa44fab4278e
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087479"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="ccff9-103">Применение метки хранения к модели понимания документа</span><span class="sxs-lookup"><span data-stu-id="ccff9-103">Apply a retention label to a document understanding model</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="ccff9-104">Вы можете легко применить [метку хранения](https://docs.microsoft.com/microsoft-365/compliance/retention) к модели понимания документа в Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="ccff9-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a document understanding model in Microsoft SharePoint Syntex.</span></span>

<span data-ttu-id="ccff9-105">Метки хранения позволяют применить параметры хранения к документам, которые определяют модели понимания документов.</span><span class="sxs-lookup"><span data-stu-id="ccff9-105">Retention labels let you apply retention settings to the documents that your document understanding models identify.</span></span>  <span data-ttu-id="ccff9-106">Например, вы хотите, чтобы ваша модель не только определяла любые документы с *уведомлением о страховании*, которые загружаются в вашу библиотеку документов, но также применяла к ним тег хранения *Бизнес*, чтобы эти документы нельзя было удалить из библиотеки документов в течение указанного периода времени (например, в течение следующих пяти месяцев).</span><span class="sxs-lookup"><span data-stu-id="ccff9-106">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="ccff9-107">Вы можете применить уже существующую метку хранения к вашей модели понимания документа с помощью параметров вашей модели на домашней странице вашей модели.</span><span class="sxs-lookup"><span data-stu-id="ccff9-107">You can apply a pre-existing retention label to your document understanding model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="ccff9-108">Для того чтобы этикетки были доступны для применения к вашей модели понимания содержимого, они должны быть [созданы и опубликованы в Центре соответствия требованиям Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="ccff9-108">For retention labels to be available to apply to your content understanding model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="ccff9-109">Чтобы добавить метку хранения к модели понимания документа, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ccff9-109">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="ccff9-110">На домашней странице модели выберите **Параметры модели**.</span><span class="sxs-lookup"><span data-stu-id="ccff9-110">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="ccff9-111">В **Параметрах модели**, в разделе **Безопасность и соответствие требованиям** выберите меню **Метка хранения**, чтобы просмотреть список меток хранения, которые можно применить к модели.</span><span class="sxs-lookup"><span data-stu-id="ccff9-111">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="ccff9-112">![Меню метки хранения](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="ccff9-112">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="ccff9-113">Выберите метку хранения, которую вы хотите применить к модели, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ccff9-113">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="ccff9-114">Добавив метку хранения к модели, вы можете применить ее к:</span><span class="sxs-lookup"><span data-stu-id="ccff9-114">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="ccff9-115">Новой библиотеке документов</span><span class="sxs-lookup"><span data-stu-id="ccff9-115">New document library</span></span>
- <span data-ttu-id="ccff9-116">Библиотеке документов, к которой уже применена модель</span><span class="sxs-lookup"><span data-stu-id="ccff9-116">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="ccff9-117">Примените метку хранения к библиотеке документов, к которой уже применена модель</span><span class="sxs-lookup"><span data-stu-id="ccff9-117">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="ccff9-118">Если модель понимания документа уже была применена к библиотеке документов, вы можете выполнить следующие действия, чтобы синхронизировать обновление метки хранения, чтобы применить его к библиотеке документов:</span><span class="sxs-lookup"><span data-stu-id="ccff9-118">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="ccff9-119">На домашней странице модели в разделе **Библиотеки с этой моделью**, выберите библиотеку документов, к которой вы хотите применить обновление метки хранения.</span><span class="sxs-lookup"><span data-stu-id="ccff9-119">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="ccff9-120">Выберите команду **Синхронизировать**.</span><span class="sxs-lookup"><span data-stu-id="ccff9-120">Select **Sync**.</span></span> </br>
 <span data-ttu-id="ccff9-121">![Модель синхронизации](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="ccff9-121">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="ccff9-122">После применения обновления и его синхронизации с моделью вы можете подтвердить, что оно было применено, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ccff9-122">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="ccff9-123">В Центре содержимого в разделе **Библиотеки с этой моделью**, щелкните библиотеку, к которой была применена обновленная модель.</span><span class="sxs-lookup"><span data-stu-id="ccff9-123">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="ccff9-124">В представлении «Библиотека документов» щелкните значок сведений, чтобы проверить свойства модели.</span><span class="sxs-lookup"><span data-stu-id="ccff9-124">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="ccff9-125">В списке **Активные модели** выберите обновленную модель.</span><span class="sxs-lookup"><span data-stu-id="ccff9-125">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="ccff9-126">В разделе **Метка хранения** будет указано имя примененной метки хранения.</span><span class="sxs-lookup"><span data-stu-id="ccff9-126">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="ccff9-127">На странице представления модели в библиотеке документов будет отображаться новая **Метка хранения**.</span><span class="sxs-lookup"><span data-stu-id="ccff9-127">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="ccff9-128">Поскольку ваша модель классифицирует файлы, которые она идентифицирует как принадлежащие к своему типу контента, и перечисляет их в представлении библиотеки, в столбце «Метка хранения» также отображается имя метки хранения, которая была применена к ней через модель.</span><span class="sxs-lookup"><span data-stu-id="ccff9-128">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="ccff9-129">Например, ко всем документам с *уведомлением о страховании*, которые определяет ваша модель, также будет применена метка хранения *Бизнес*, предотвращающая их удаление из библиотеки документов в течение пяти месяцев.</span><span class="sxs-lookup"><span data-stu-id="ccff9-129">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="ccff9-130">При попытке удалить файл из библиотеки документов будет отображаться сообщение о том, что это запрещено из-за примененной метки сохранения.</span><span class="sxs-lookup"><span data-stu-id="ccff9-130">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccff9-131">См. также</span><span class="sxs-lookup"><span data-stu-id="ccff9-131">See Also</span></span>
[<span data-ttu-id="ccff9-132">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="ccff9-132">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="ccff9-133">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="ccff9-133">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="ccff9-134">Общие сведения о понимании документа</span><span class="sxs-lookup"><span data-stu-id="ccff9-134">Document Understanding overview</span></span>](document-understanding-overview.md)


