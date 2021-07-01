---
title: Применение метки конфиденциальности к модели в Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: В этой статье объясняется, как применить метку конфиденциальности к модели в SharePoint Syntex
ms.openlocfilehash: c7d6c17dc4d41bf2dab663618e740318d88dd723
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228751"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="00f12-103">Применение метки конфиденциальности к модели в Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="00f12-103">Apply a sensitivity label to a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="00f12-104">Вы можете легко применить [метку конфиденциальности ](../compliance/sensitivity-labels.md) к модели осмысления документации в Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="00f12-104">You can easily apply a [sensitivity label](../compliance/sensitivity-labels.md) to document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="00f12-105">Эта функция пока недоступна для моделей обработки форм.</span><span class="sxs-lookup"><span data-stu-id="00f12-105">This feature isn't available yet for form processing models.</span></span>

<span data-ttu-id="00f12-106">Метки конфиденциальности позволяют применять политики шифрования, общего доступа и условного доступа к документам, выявленным вашими моделями.</span><span class="sxs-lookup"><span data-stu-id="00f12-106">Sensitivity labels let you apply encryption, sharing, and conditional access policies to the documents that your models identify.</span></span> <span data-ttu-id="00f12-107">Например, вы хотите, чтобы модель не только выявляла финансовые загруженные в библиотеку документы, содержащие номера банковских счетов или кредитных карт, но и применяла к ним метку конфиденциальности *Шифрование*, чтобы ограничить доступ к этому содержимому и его использование.</span><span class="sxs-lookup"><span data-stu-id="00f12-107">For example, you want your model to not only identify any financial documents that contain bank account numbers or credit card numbers that are uploaded to your document library, but also to apply an *Encryption* sensitivity label to them to restrict who can access that content and how it can be used.</span></span> <span data-ttu-id="00f12-108">Модели SharePoint Syntex следуют правилам, регулирующим [порядок меток](../compliance/apply-sensitivity-label-automatically.md#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label), а также не меняют существующие метки, вручную примененные пользователем к файлу.</span><span class="sxs-lookup"><span data-stu-id="00f12-108">SharePoint Syntex models honor the [label order](../compliance/apply-sensitivity-label-automatically.md#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label) rules and also do not overwrite an existing label that was manually applied by a user to the file.</span></span> 

<span data-ttu-id="00f12-109">Вы можете применить уже существующую метку хранения к своей модели, используя параметры модели на ее домашней странице.</span><span class="sxs-lookup"><span data-stu-id="00f12-109">You can apply a pre-existing sensitivity label to your model through your model settings on your model's home page.</span></span> <span data-ttu-id="00f12-110">Чтобы стать доступной для выбора в параметрах модели, метка должна быть опубликована.</span><span class="sxs-lookup"><span data-stu-id="00f12-110">The label must already be published to be available for selection from model settings.</span></span>

> [!Important]
> <span data-ttu-id="00f12-111">Чтобы метки хранения стали доступны для применения к вашей модели осмысления документации, они должны быть [созданы и опубликованы в Центре соответствия требованиям Microsoft 365](../business-video/create-sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="00f12-111">For sensitivity labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).</span></span>

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a><span data-ttu-id="00f12-112">Применение метки хранения к модели осмысления документации</span><span class="sxs-lookup"><span data-stu-id="00f12-112">Add a sensitivity label to a document understanding model</span></span>

1. <span data-ttu-id="00f12-113">На домашней странице модели выберите **Параметры модели**.</span><span class="sxs-lookup"><span data-stu-id="00f12-113">From the model home page, select **Model settings**.</span></span>

   ![Снимок экрана: страница модели с выделенной опцией "Параметры модели".](../media/content-understanding/sensitivity-model-settings.png)

2. <span data-ttu-id="00f12-115">В области **Параметры модели**, в разделе **Безопасность и соответствие требованиям**, выберите **Метка конфиденциальности**, чтобы просмотреть список меток конфиденциальности, доступных для применения к модели.</span><span class="sxs-lookup"><span data-stu-id="00f12-115">On **Model settings** pane, in the **Compliance** section, select the **Sensitivity label** menu to see a list of sensitivity labels that are available for you to apply to the model.</span></span>

   ![Снимок экрана: меню меток конфиденциальности в области параметров модели.](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. <span data-ttu-id="00f12-117">Выберите метку конфиденциальности, которую хотите применить к модели, и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="00f12-117">Select the sensitivity label you want to apply to the model, and then select **Save**.</span></span>

<span data-ttu-id="00f12-118">После применения метки конфиденциальности к модели ее можно применить к:</span><span class="sxs-lookup"><span data-stu-id="00f12-118">After you apply the sensitivity label to your model, you can apply it to a:</span></span>

- <span data-ttu-id="00f12-119">Новой библиотеке документов</span><span class="sxs-lookup"><span data-stu-id="00f12-119">New document library</span></span>
- <span data-ttu-id="00f12-120">Библиотеке документов, к которой уже применена модель</span><span class="sxs-lookup"><span data-stu-id="00f12-120">Document library to which the model is already applied</span></span>
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="00f12-121">Примените метку конфиденциальности к библиотеке документов, к которой уже применена модель</span><span class="sxs-lookup"><span data-stu-id="00f12-121">Apply the sensitivity label to a document library to which the model is already applied</span></span>

<span data-ttu-id="00f12-122">Если модель осмысления документации уже была применена к библиотеке документов, вы можете выполнить следующие действия, чтобы синхронизировать обновление метки конфиденциальности и применить ее к библиотеке документов:</span><span class="sxs-lookup"><span data-stu-id="00f12-122">If your document understanding model has already been applied to a document library, you can do the following to sync your sensitivity label update to apply it to the document library:</span></span>

1. <span data-ttu-id="00f12-123">На домашней странице модели в разделе **Библиотеки с этой моделью**, выберите библиотеку документов, к которой хотите применить обновление метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="00f12-123">On the model home page, in the **Libraries with this model** section, select the document library to which you want to apply the sensitivity label update.</span></span>

2. <span data-ttu-id="00f12-124">Выберите **Синхронизировать**.</span><span class="sxs-lookup"><span data-stu-id="00f12-124">Select **Sync**.</span></span>

   ![Снимок экрана: раздел "Библиотеки с этой моделью" с выделенным элементом управления синхронизацией.](../media/content-understanding/sensitivity-libraries-sync.png)

<span data-ttu-id="00f12-126">После применения обновления и его синхронизации с моделью вы можете удостовериться, что оно было применено, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="00f12-126">After you apply the update and sync it to your model, you can confirm that it has been applied by doing the following steps:</span></span>

1. <span data-ttu-id="00f12-127">В Центре содержимого в разделе **Библиотеки с этой моделью** щелкните библиотеку, к которой была применена обновленная модель.</span><span class="sxs-lookup"><span data-stu-id="00f12-127">In the content center, in the **Libraries with this model** section, select the library to which your updated model was applied.</span></span> 

2. <span data-ttu-id="00f12-128">В представлении «Библиотека документов» щелкните значок сведений, чтобы проверить свойства модели.</span><span class="sxs-lookup"><span data-stu-id="00f12-128">In your document library view, select the information icon to check the model properties.</span></span>

3. <span data-ttu-id="00f12-129">В списке **Активные модели** выберите обновленную модель.</span><span class="sxs-lookup"><span data-stu-id="00f12-129">In the **Active models** list, select your updated model.</span></span>

4. <span data-ttu-id="00f12-130">В разделе **Метки конфиденциальности** вы увидите имя примененной метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="00f12-130">In the **Sensitivity label** section, you'll see the name of the applied sensitivity label.</span></span>

<span data-ttu-id="00f12-131">На странице представления модели в библиотеке документов будет показана новая **Метка конфиденциальности**.</span><span class="sxs-lookup"><span data-stu-id="00f12-131">On your model's view page in your document library, a new **Sensitivity label** column will display.</span></span> <span data-ttu-id="00f12-132">Поскольку ваша модель классифицирует файлы, выявленные ею как принадлежащие к нужному типу контента, и перечисляет их в представлении библиотеки, в столбце **Метка конфиденциальности** также появится имя метки хранения, которая была применена к ней через модель.</span><span class="sxs-lookup"><span data-stu-id="00f12-132">As your model classifies files it identifies as belonging to its content type and lists them in the library view, the **Sensitivity label** column will also display the name of the sensitivity label that has been applied to it through the model.</span></span>

<span data-ttu-id="00f12-133">Например, ко всем финансовым документам, выявленным вашей моделью, также будет применена метка конфиденциальности *Шифрование*, предотвращающая неавторизованный доступ.</span><span class="sxs-lookup"><span data-stu-id="00f12-133">For example, all financial documents that your model identifies also will have the *Encryption* sensitivity label applied to them, preventing them from being accessed by unauthorized people.</span></span> <span data-ttu-id="00f12-134">Если пользователь, не имеющий нужных полномочий, попытается удалить файл из библиотеки документов, будет выведено сообщение о том, что это запрещено из-за примененной метки конфиденциальности.</span><span class="sxs-lookup"><span data-stu-id="00f12-134">If an attempt is made to access the file from the document library by an unauthorized person, an error will display saying it isn't allowed because of the applied sensitivity label.</span></span>

<!---
## Add a sensitivity label to a form processing model

> [!Important]
> For sensitivity labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).

You can either apply a sensitivity label to a form processing model when you are creating a model, or apply it to an existing model.

### Add a sensitivity label when you create a form processing model

1. When you [create a new form processing model](create-a-form-processing-model.md), select **Advanced settings**.

2. In **Advanced settings**, in the **Sensitivity label** section, select the menu and then select the sensitivity label you want to apply to the model.

3.  After you've completed your remaining model settings, select **Create** to build your model.

### Add a sensitivity label to an existing form processing model

You can add a sensitivity label to an existing form processing model in different ways:

- Through the **Automate** menu in the document library
- Through the **Active model** settings in the document library 

#### Add a sensitivity label to an existing form processing model through the Automate menu

You can add a sensitivity label to an existing form processing model that you own through the **Automate** menu in the document library in which the model is applied.

1. In your document library to which the form processing model is applied, select the **Automate** menu, select **AI Builder**, and then select **View form processing model details**.

2. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

#### Add a sensitivity label to an existing form processing model in the active model settings

You can add a sensitivity label to an existing form processing model that you own through the **Active model** settings in the document library in which the model is applied.

1. In the SharePoint document library in which the model is applied, select the **View active models** icon, and then select **View active models**.

2. In **Active models**, select the form processing model to which you want to apply the sensitivity label.

3. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

   > [!NOTE]
   > You must be the model owner for the **Model settings** pane to be editable. 
--->

## <a name="see-also"></a><span data-ttu-id="00f12-135">См. также</span><span class="sxs-lookup"><span data-stu-id="00f12-135">See also</span></span>

[<span data-ttu-id="00f12-136">Применение метки хранения</span><span class="sxs-lookup"><span data-stu-id="00f12-136">Apply a retention label</span></span>](apply-a-retention-label-to-a-model.md)

[<span data-ttu-id="00f12-137">Создание классификатора</span><span class="sxs-lookup"><span data-stu-id="00f12-137">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="00f12-138">Создание средства извлечения</span><span class="sxs-lookup"><span data-stu-id="00f12-138">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="00f12-139">Общие сведения об осмыслении документации</span><span class="sxs-lookup"><span data-stu-id="00f12-139">Document Understanding overview</span></span>](document-understanding-overview.md)
