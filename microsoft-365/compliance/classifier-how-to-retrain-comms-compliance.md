---
title: Повторное обучение классификаторов в соответствии с требованиями к обмену данными
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Узнайте, как предоставлять отзывы обучаемого классификатора в соответствии с коммуникациями.
ms.openlocfilehash: cdb8787715c3e022dfa0aa17cd83cc405aeef955
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752653"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a><span data-ttu-id="34939-103">Повторное обучение классификаторов в соответствии с требованиями к обмену данными</span><span class="sxs-lookup"><span data-stu-id="34939-103">How to retrain a classifier in communications compliance</span></span>

<span data-ttu-id="34939-104">Обучаемый классификатор Microsoft 365 — это средство, которое можно обучить распознавать различные типы контента, предоставляя ему примеры для анализа.</span><span class="sxs-lookup"><span data-stu-id="34939-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="34939-105">После обучения вы можете использовать его для определения элемента для применения меток конфиденциальности Office, политик соответствия коммуникациям и политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="34939-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="34939-106">В этой статье показано, как повысить производительность настраиваемых обучаемых классификаторов и некоторых предварительно обученных классификаторов, предоставив им дополнительную обратную связь.</span><span class="sxs-lookup"><span data-stu-id="34939-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="34939-107">Дополнительные информацию о различных типах классификаторов см. в дополнительных данных об обучаемых [классификаторах.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="34939-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="34939-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="34939-108">Permissions</span></span>

<span data-ttu-id="34939-109">Чтобы получить доступ к классификаторам в Центре соответствия требованиям Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="34939-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="34939-110">Для обучения классификатора требуется роль администратора соответствия требованиям или администратора данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="34939-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="34939-111">Для использования классификаторов в таких сценариях необходимы учетные записи с этими разрешениями:</span><span class="sxs-lookup"><span data-stu-id="34939-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="34939-112">Сценарий политики соответствия коммуникациям: администратор управления рисками, администратор надзорной проверки</span><span class="sxs-lookup"><span data-stu-id="34939-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="34939-113">Общий рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="34939-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34939-114">Вы предоставляете отзыв в решении для обеспечения соответствия требованиям, которое использует классификатор в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="34939-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="34939-115">**Если у вас нет политики соответствия коммуникациям, использующей классификатор в качестве условия, остановите это.**</span><span class="sxs-lookup"><span data-stu-id="34939-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="34939-116">При использовании классификаторов может потребоваться повысить точность классификаций, которые они делают.</span><span class="sxs-lookup"><span data-stu-id="34939-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="34939-117">Это можно сделать, оценив качество классификаций, сделанных для элементов, которые они определили как совпадающие или не совпадающие.</span><span class="sxs-lookup"><span data-stu-id="34939-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="34939-118">После того как вы сделаете 30 оценок для классификатора, он будет принимать этот отзыв и автоматически переучивать себя.</span><span class="sxs-lookup"><span data-stu-id="34939-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="34939-119">Подробнее об общем процессе переподготовки классификатора см. в процедуре переподготовки [классификатора.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="34939-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="34939-120">Классификатор уже должен быть опубликован и используется, прежде чем его можно будет переучить.</span><span class="sxs-lookup"><span data-stu-id="34939-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a><span data-ttu-id="34939-121">Переподготовка классификатора в политиках соответствия коммуникациям</span><span class="sxs-lookup"><span data-stu-id="34939-121">How to retrain a classifier in communication compliance policies</span></span>

1. <span data-ttu-id="34939-122">Откройте политику соответствия требованиям связи, которая использует классификатор в качестве  условия, и выберите один из идентифицированных элементов в списке "Ожидание".</span><span class="sxs-lookup"><span data-stu-id="34939-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="34939-123">Выберите многоязык и **усовершенствовать классификацию.**</span><span class="sxs-lookup"><span data-stu-id="34939-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="34939-124">В области **"Подробные отзывы",** если элемент имеет настоящий положительный результат, выберите "Соответствие". </span><span class="sxs-lookup"><span data-stu-id="34939-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="34939-125">Если элемент имеет ложный срабатыв, то есть он был неправильно включен в категорию, выберите **"Не совпадать".**</span><span class="sxs-lookup"><span data-stu-id="34939-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="34939-126">Если есть другой классификатор, который больше подходит для элемента, его можно выбрать в списке "Предложить другие обучаемые **классификаторы".**</span><span class="sxs-lookup"><span data-stu-id="34939-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="34939-127">Это активирует другой классификатор для оценки элемента.</span><span class="sxs-lookup"><span data-stu-id="34939-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="34939-128">Вы можете одновременно предоставить отзывы о нескольких пунктах, выбрав их все, а затем выбрав пункт "Предоставить **подробный отзыв"** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="34939-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="34939-129">Choose **Send feedback** to send your evaluation of the , `match` `not a match` classifications and suggest other trainable classifiers.</span><span class="sxs-lookup"><span data-stu-id="34939-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="34939-130">Когда вы предоставляете классификатору 30 экземпляров обратной связи, он автоматически переучен.</span><span class="sxs-lookup"><span data-stu-id="34939-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="34939-131">Переподготовка может занять от 1 до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="34939-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="34939-132">Классификаторы можно переподготовить только дважды в день.</span><span class="sxs-lookup"><span data-stu-id="34939-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34939-133">Эти сведения пойдут в классификатор в вашем клиенте и не будут **возвращаться в Корпорацию Майкрософт.**</span><span class="sxs-lookup"><span data-stu-id="34939-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="34939-134">Откройте **страницу классификации** данных в **Центре соответствия требованиям Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="34939-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="34939-135">Откройте **обучаемые классификаторы.**</span><span class="sxs-lookup"><span data-stu-id="34939-135">Open **Trainable classifiers**.</span></span>
8. <span data-ttu-id="34939-136">Классификатор, используемый в политике соответствия коммуникациям, будет отображаться под заголовком **"Повторное обучение".**</span><span class="sxs-lookup"><span data-stu-id="34939-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![классификатор в состоянии переподготовки](../media/classifier-retraining.png)

9. <span data-ttu-id="34939-138">После завершения переподготовки выберите классификатор, чтобы открыть обзор переподготовки.</span><span class="sxs-lookup"><span data-stu-id="34939-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Обзор результатов повторной подготовки классификаторов](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="34939-140">Просмотрите рекомендуемое действие и сравнение прогнозирования для повторной и опубликованной версии классификатора.</span><span class="sxs-lookup"><span data-stu-id="34939-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="34939-141">Если вы удовлетворены результатами переподготовки, выберите **"Переопубликовка".**</span><span class="sxs-lookup"><span data-stu-id="34939-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="34939-142">Если вы не удовлетворены результатами переподготовки, вы можете предоставить дополнительные отзывы классификатору в интерфейсе соответствия коммуникациям и запустить еще один цикл переподготовки или ничего не делать, в этом случае опубликованная версия классификатора будет по-прежнему использоваться.</span><span class="sxs-lookup"><span data-stu-id="34939-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="34939-143">Подробные сведения о переопубликовывающих рекомендациях</span><span class="sxs-lookup"><span data-stu-id="34939-143">Details on republishing recommendations</span></span>

<span data-ttu-id="34939-144">Ниже немного информации о том, как мы сформулировали рекомендацию повторно опубликовать классификатор с переподготовленным классификатором или предложить дополнительную переподготовку.</span><span class="sxs-lookup"><span data-stu-id="34939-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="34939-145">Для этого требуется более глубокое понимание работы обучаемых классификаторов.</span><span class="sxs-lookup"><span data-stu-id="34939-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="34939-146">После переподготовки мы оцениваем производительность классификатора как для элементов с обратной связью, так и для всех элементов, изначально используемых для обучения классификатора.</span><span class="sxs-lookup"><span data-stu-id="34939-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="34939-147">Для встроенных моделей элементы, используемые для обучения классификатора, — это элементы, используемые корпорацией Майкрософт для создания модели.</span><span class="sxs-lookup"><span data-stu-id="34939-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="34939-148">Для пользовательских моделей элементы, используемые в исходном обучении классификатора, находятся на сайтах, добавленных для тестирования и проверки.</span><span class="sxs-lookup"><span data-stu-id="34939-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="34939-149">Мы сравниваем показатели производительности для обоих наборов элементов для классификатора с переподготовленным и опубликованным классификатором, чтобы дать рекомендации о том, были ли усовершенствования для повторной публикации.</span><span class="sxs-lookup"><span data-stu-id="34939-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="34939-150">См. также</span><span class="sxs-lookup"><span data-stu-id="34939-150">See also</span></span>

- [<span data-ttu-id="34939-151">Информация об обучаемых классификаторах</span><span class="sxs-lookup"><span data-stu-id="34939-151">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="34939-152">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="34939-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
