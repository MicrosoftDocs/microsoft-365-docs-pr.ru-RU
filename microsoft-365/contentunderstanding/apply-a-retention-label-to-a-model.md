---
title: Применение метки хранения к модели
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
localization_priority: Normal
description: В этой статье объясняется, как применить метку хранения к модели в SharePoint Syntex
ms.openlocfilehash: 00a8d255b3274af3cd96527e0dcd2ae2644226ac
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861615"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a><span data-ttu-id="d807c-103">Применение метки хранения к модели в SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="d807c-103">Apply a retention label to a model in SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="d807c-104">Вы можете легко применить [метку хранения](../compliance/retention.md) к модели в Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="d807c-104">You can easily apply a [retention label](../compliance/retention.md) to a model in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="d807c-105">Вы можете это сделать как для модели осмысления документации, так и для модели обработки форм.</span><span class="sxs-lookup"><span data-stu-id="d807c-105">You can do this for both document understanding and form processing models.</span></span>

<span data-ttu-id="d807c-106">Метки хранения позволяют применить параметры хранения к документам, определяемым моделями.</span><span class="sxs-lookup"><span data-stu-id="d807c-106">Retention labels let you apply retention settings to the documents that your models identify.</span></span>  <span data-ttu-id="d807c-107">Например, вы хотите, чтобы ваша модель не только определяла любые документы с *уведомлением о страховании*, которые загружаются в вашу библиотеку документов, но также применяла к ним тег хранения *Бизнес*, чтобы эти документы нельзя было удалить из библиотеки документов в течение указанного периода времени (например, в течение следующих пяти месяцев).</span><span class="sxs-lookup"><span data-stu-id="d807c-107">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="d807c-108">Вы можете применить существующую метку хранения к вашей модели с помощью параметров модели на ее домашней странице.</span><span class="sxs-lookup"><span data-stu-id="d807c-108">You can apply a pre-existing retention label to your model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="d807c-109">Чтобы метки хранения были доступны для применения к вашей модели осмысления документации, они должны быть [созданы и опубликованы в Центре соответствия требованиям Microsoft 365](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="d807c-109">For retention labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="d807c-110">Чтобы добавить метку хранения к модели понимания документа, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d807c-110">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="d807c-111">На домашней странице модели выберите **Параметры модели**.</span><span class="sxs-lookup"><span data-stu-id="d807c-111">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="d807c-112">В **Параметрах модели**, в разделе **Безопасность и соответствие требованиям** выберите меню **Метка хранения**, чтобы просмотреть список меток хранения, которые можно применить к модели.</span><span class="sxs-lookup"><span data-stu-id="d807c-112">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="d807c-113">![Меню метки хранения](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="d807c-113">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="d807c-114">Выберите метку хранения, которую вы хотите применить к модели, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d807c-114">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="d807c-115">Добавив метку хранения к модели, вы можете применить ее к:</span><span class="sxs-lookup"><span data-stu-id="d807c-115">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="d807c-116">Новой библиотеке документов</span><span class="sxs-lookup"><span data-stu-id="d807c-116">New document library</span></span>
- <span data-ttu-id="d807c-117">Библиотеке документов, к которой уже применена модель</span><span class="sxs-lookup"><span data-stu-id="d807c-117">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="d807c-118">Примените метку хранения к библиотеке документов, к которой уже применена модель</span><span class="sxs-lookup"><span data-stu-id="d807c-118">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="d807c-119">Если модель понимания документа уже была применена к библиотеке документов, вы можете выполнить следующие действия, чтобы синхронизировать обновление метки хранения, чтобы применить его к библиотеке документов:</span><span class="sxs-lookup"><span data-stu-id="d807c-119">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="d807c-120">На домашней странице модели в разделе **Библиотеки с этой моделью**, выберите библиотеку документов, к которой вы хотите применить обновление метки хранения.</span><span class="sxs-lookup"><span data-stu-id="d807c-120">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="d807c-121">Выберите команду **Синхронизировать**.</span><span class="sxs-lookup"><span data-stu-id="d807c-121">Select **Sync**.</span></span> </br>
 <span data-ttu-id="d807c-122">![Модель синхронизации](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="d807c-122">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="d807c-123">После применения обновления и его синхронизации с моделью вы можете подтвердить, что оно было применено, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="d807c-123">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="d807c-124">В Центре содержимого в разделе **Библиотеки с этой моделью**, щелкните библиотеку, к которой была применена обновленная модель.</span><span class="sxs-lookup"><span data-stu-id="d807c-124">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="d807c-125">В представлении «Библиотека документов» щелкните значок сведений, чтобы проверить свойства модели.</span><span class="sxs-lookup"><span data-stu-id="d807c-125">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="d807c-126">В списке **Активные модели** выберите обновленную модель.</span><span class="sxs-lookup"><span data-stu-id="d807c-126">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="d807c-127">В разделе **Метка хранения** будет указано имя примененной метки хранения.</span><span class="sxs-lookup"><span data-stu-id="d807c-127">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="d807c-128">На странице представления модели в библиотеке документов будет отображаться новая **Метка хранения**.</span><span class="sxs-lookup"><span data-stu-id="d807c-128">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="d807c-129">Поскольку ваша модель классифицирует файлы, которые она идентифицирует как принадлежащие к своему типу контента, и перечисляет их в представлении библиотеки, в столбце «Метка хранения» также отображается имя метки хранения, которая была применена к ней через модель.</span><span class="sxs-lookup"><span data-stu-id="d807c-129">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="d807c-130">Например, ко всем документам с *уведомлением о страховании*, которые определяет ваша модель, также будет применена метка хранения *Бизнес*, предотвращающая их удаление из библиотеки документов в течение пяти месяцев.</span><span class="sxs-lookup"><span data-stu-id="d807c-130">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="d807c-131">При попытке удалить файл из библиотеки документов будет отображаться сообщение о том, что это запрещено из-за примененной метки сохранения.</span><span class="sxs-lookup"><span data-stu-id="d807c-131">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a><span data-ttu-id="d807c-132">Добавление метки хранения в модель обработки форм</span><span class="sxs-lookup"><span data-stu-id="d807c-132">To add a retention label to a form processing model</span></span>

> [!Important]
> <span data-ttu-id="d807c-133">Чтобы метки хранения были доступны для применения к вашей модели обработки форм, они должны быть [созданы и опубликованы в Центре соответствия требованиям Microsoft 365](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="d807c-133">For retention labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).</span></span>

<span data-ttu-id="d807c-134">Метку хранения можно применить к модели обработки форм при создании модели или применить ее к существующей модели.</span><span class="sxs-lookup"><span data-stu-id="d807c-134">You can either apply a retention label to a form processing model when you are creating a model, or apply it to an existing model.</span></span>

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a><span data-ttu-id="d807c-135">Добавление метки хранения при создании модели обработки форм</span><span class="sxs-lookup"><span data-stu-id="d807c-135">To add a retention label when you create a form processing model</span></span>

1. <span data-ttu-id="d807c-136">При [создании модели обработки форм](./create-a-form-processing-model.md) выберите <b>Дополнительные параметры</b>.</span><span class="sxs-lookup"><span data-stu-id="d807c-136">When you are [creating a new form processing model](./create-a-form-processing-model.md), select <b>Advanced settings.</b></span></span>
2. <span data-ttu-id="d807c-137">В области <b>Дополнительные параметры</b> в разделе <b>Метка хранения</b> откройте меню и выберите метку хранения, которую нужно применить к модели.</b></span><span class="sxs-lookup"><span data-stu-id="d807c-137">In <b>Advanced settings</b>, in the <b>Retention label</b> section, select the menu and then select the retention label you want to apply to the model.</b></span></span>

 
     ![Добавление в новую модель обработки форм](../media/content-understanding/retention-label-forms.png)</br>

3.  <span data-ttu-id="d807c-139">Завершив настройку оставшихся параметров модели, выберите <b>Создать</b>, чтобы создать модель.</span><span class="sxs-lookup"><span data-stu-id="d807c-139">After you've completed your remaining model settings, select <b>Create</b> to build your model.</span></span>

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a><span data-ttu-id="d807c-140">Добавление метки хранения в существующую модель обработки форм</span><span class="sxs-lookup"><span data-stu-id="d807c-140">To add a retention label to an existing form processing model</span></span>

<span data-ttu-id="d807c-141">Вы можете добавить метку хранения в существующую модель обработки форм разными способами:</span><span class="sxs-lookup"><span data-stu-id="d807c-141">You can add a retention label to an existing form processing model in different ways:</span></span>
- <span data-ttu-id="d807c-142">В меню автоматизации в библиотеке документов</span><span class="sxs-lookup"><span data-stu-id="d807c-142">Through the Automate menu in the document library</span></span>
- <span data-ttu-id="d807c-143">В параметрах активной модели в библиотеке документов</span><span class="sxs-lookup"><span data-stu-id="d807c-143">Through the Active model settings in the document library</span></span> 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a><span data-ttu-id="d807c-144">Добавление метки хранения в существующую модель обработки форм в меню автоматизации</span><span class="sxs-lookup"><span data-stu-id="d807c-144">To add a retention label to an existing form processing model through the Automate menu</span></span>

<span data-ttu-id="d807c-145">Вы можете добавить метку хранения в существующую модель обработки форм, которой вы владеете, с помощью меню автоматизации в библиотеке документов, к которой применяется модель.</span><span class="sxs-lookup"><span data-stu-id="d807c-145">You can add a retention label to an existing form processing model that you own through the Automate menu in the document library in which the model is applied.</span></span>


1. <span data-ttu-id="d807c-146">В библиотеке документов, к которой применяется модель обработки форм, откройте меню <b>Автоматизация</b>, выберите <b>AI Builder</b> и нажмите <b>Просмотр сведений о модели обработки форм</b>.</span><span class="sxs-lookup"><span data-stu-id="d807c-146">In your document library to which the form processing model is applied, select the <b>Automate</b> menu, select <b>AI Builder</b>, then select <b>View form processing model details</b>.</span></span>

   ![Меню "Автоматизация"](../media/content-understanding/automate-menu.png)</br>

2. <span data-ttu-id="d807c-148">В сведениях о модели в разделе <b>Метка хранения</b> выберите метку хранения, которую нужно применить.</span><span class="sxs-lookup"><span data-stu-id="d807c-148">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="d807c-149">Нажмите <b>Сохранить</b>.</span><span class="sxs-lookup"><span data-stu-id="d807c-149">Then select <b>Save</b>.</span></span>

     ![Добавление в существующую модель обработки форм](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a><span data-ttu-id="d807c-151">Добавление метки хранения в существующую модель обработки форм в параметрах активной модели</span><span class="sxs-lookup"><span data-stu-id="d807c-151">To add a retention label to an existing form processing model in the active model settings</span></span>

<span data-ttu-id="d807c-152">Вы можете добавить метку хранения в существующую модель обработки форм, которой вы владеете, с помощью параметров активной модели в библиотеке документов, к которой применяется модель.</span><span class="sxs-lookup"><span data-stu-id="d807c-152">You can add a retention label to an existing form processing model that you own through the Active model settings in the document library in which the model is applied.</span></span>

1. <span data-ttu-id="d807c-153">В библиотеке документов SharePoint, к которой применяется модель, щелкните значок <b>Просмотреть активные модели</b> и выберите <b>Просмотреть активные модели</b>.</b></span><span class="sxs-lookup"><span data-stu-id="d807c-153">In the SharePoint document library in which the model is applied, select the <b>View active models</b> icon, and then select <b>View active models</b>.</b></span></span>

   ![Просмотр активных моделей](../media/content-understanding/info-du.png)</br> 

2. <span data-ttu-id="d807c-155">В разделе <b>Активные модели</b> выберите модель обработки форм, к которой нужно применить метку хранения.</span><span class="sxs-lookup"><span data-stu-id="d807c-155">In <b>Active models</b>, select the form processing model to which you want to apply the retention label.</span></span>

     ![Сведения о модели](../media/content-understanding/retention-label-model-details.png)</br> 


3. <span data-ttu-id="d807c-157">В сведениях о модели в разделе <b>Метка хранения</b> выберите метку хранения, которую нужно применить.</span><span class="sxs-lookup"><span data-stu-id="d807c-157">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="d807c-158">Нажмите <b>Сохранить</b>.</span><span class="sxs-lookup"><span data-stu-id="d807c-158">Then select <b>Save</b>.</span></span>

> [!NOTE]
> <span data-ttu-id="d807c-159">Чтобы вносить изменения в области параметров модели, вы должны быть владельцем модели.</span><span class="sxs-lookup"><span data-stu-id="d807c-159">You must be the model owner for the model settings pane to be editable.</span></span> 


## <a name="see-also"></a><span data-ttu-id="d807c-160">См. также</span><span class="sxs-lookup"><span data-stu-id="d807c-160">See Also</span></span>
[<span data-ttu-id="d807c-161">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="d807c-161">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="d807c-162">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="d807c-162">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="d807c-163">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="d807c-163">Document Understanding overview</span></span>](document-understanding-overview.md)
