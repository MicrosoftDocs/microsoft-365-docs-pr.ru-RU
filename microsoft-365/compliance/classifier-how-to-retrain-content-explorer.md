---
title: Переподготовка классификатора в обозревателе содержимого
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
description: Узнайте, как предоставлять отзывы обучаемому классификатору в обозревателе содержимого.
ms.openlocfilehash: 786ebb682e9cdd96c0c6503294bd4f316f777f68
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752627"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="10b94-103">Переподготовка классификатора в обозревателе содержимого</span><span class="sxs-lookup"><span data-stu-id="10b94-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="10b94-104">Обучаемый классификатор Microsoft 365 — это средство, которое можно обучить распознавать различные типы контента, предоставляя ему примеры для анализа.</span><span class="sxs-lookup"><span data-stu-id="10b94-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="10b94-105">После обучения вы можете использовать его для определения элемента для применения меток конфиденциальности Office, политик соответствия коммуникациям и политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="10b94-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="10b94-106">В этой статье показано, как повысить производительность настраиваемых обучаемых классификаторов и некоторых предварительно обученных классификаторов, предоставив им дополнительную обратную связь.</span><span class="sxs-lookup"><span data-stu-id="10b94-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="10b94-107">Дополнительные информацию о различных типах классификаторов см. в дополнительных данных об обучаемых [классификаторах.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="10b94-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="10b94-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="10b94-108">Permissions</span></span>

<span data-ttu-id="10b94-109">Чтобы получить доступ к классификаторам в Центре соответствия требованиям Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="10b94-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="10b94-110">Для обучения классификатора требуется роль администратора соответствия требованиям или администратора данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="10b94-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="10b94-111">Для использования классификаторов в таких сценариях необходимы учетные записи с этими разрешениями:</span><span class="sxs-lookup"><span data-stu-id="10b94-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="10b94-112">Сценарий политики меток хранения: роли управления записями и управления хранением</span><span class="sxs-lookup"><span data-stu-id="10b94-112">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="10b94-113">Общий рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="10b94-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10b94-114">Вы предоставляете отзыв в обозревателе содержимого для автоматического применения политик меток хранения к элементами Exchange и использует классификатор в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="10b94-114">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="10b94-115">**Если у вас нет политики хранения, которая автоматически применяет метку хранения к элементу Exchange и использует классификатор в качестве условия, остановите это.**</span><span class="sxs-lookup"><span data-stu-id="10b94-115">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="10b94-116">При использовании классификаторов может потребоваться повысить точность классификаций, которые они делают.</span><span class="sxs-lookup"><span data-stu-id="10b94-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="10b94-117">Это можно сделать, оценив качество классификаций, сделанных для элементов, которые они определили как совпадающие или не совпадающие.</span><span class="sxs-lookup"><span data-stu-id="10b94-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="10b94-118">После того как вы сделаете 30 оценок для классификатора, он будет принимать этот отзыв и автоматически переучивать себя.</span><span class="sxs-lookup"><span data-stu-id="10b94-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="10b94-119">Подробнее об общем процессе переподготовки классификатора см. в процедуре переподготовки [классификатора.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="10b94-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="10b94-120">Классификатор уже должен быть опубликован и используется, прежде чем его можно будет переучить.</span><span class="sxs-lookup"><span data-stu-id="10b94-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="10b94-121">Переподготовка классификатора в обозревателе содержимого</span><span class="sxs-lookup"><span data-stu-id="10b94-121">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="10b94-122">Во sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** Data  >  **classification**  >  **Content explorer.**</span><span class="sxs-lookup"><span data-stu-id="10b94-122">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="10b94-123">В **списке фильтра по меткам,** типам информации или категориям разо расширении обучаемых **классификаторов.**</span><span class="sxs-lookup"><span data-stu-id="10b94-123">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10b94-124">Сводные элементы могут отображаться под заголовком обучаемых классификаторов в течение восьми дней.</span><span class="sxs-lookup"><span data-stu-id="10b94-124">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="10b94-125">Выберите обучаемый классификатор, используемый в политике автоматического применения меток хранения.</span><span class="sxs-lookup"><span data-stu-id="10b94-125">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="10b94-126">Это обучаемый классификатор, на который вы будете давать отзывы.</span><span class="sxs-lookup"><span data-stu-id="10b94-126">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="10b94-127">Если элемент имеет запись  в столбце метки хранения, это означает, что элемент был классифицирован как `match` .</span><span class="sxs-lookup"><span data-stu-id="10b94-127">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="10b94-128">Если элемент не имеет записи  в столбце метки хранения, это означает, что он был классифицирован как `close match` .</span><span class="sxs-lookup"><span data-stu-id="10b94-128">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="10b94-129">Вы можете повысить точность классификатора максимально, предоставив отзывы об `close match` элементе.</span><span class="sxs-lookup"><span data-stu-id="10b94-129">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="10b94-130">Выберите элемент и откройте его.</span><span class="sxs-lookup"><span data-stu-id="10b94-130">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="10b94-131">Вы можете одновременно предоставить отзывы о нескольких пунктах, выбрав их все, а затем выбрав "Улучшить **классификацию"** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="10b94-131">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="10b94-132">Choose **Provide feedback**.</span><span class="sxs-lookup"><span data-stu-id="10b94-132">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="10b94-133">В области **"Подробные отзывы",** если элемент является истинным положительным, выберите "Match" (Совпадение). </span><span class="sxs-lookup"><span data-stu-id="10b94-133">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="10b94-134">Если элемент имеет ложный срабатыв, то есть он был неправильно включен в категорию, выберите **"Не совпадать".**</span><span class="sxs-lookup"><span data-stu-id="10b94-134">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="10b94-135">Если есть другой классификатор, который больше подходит для элемента, его можно выбрать в списке "Предложить другие обучаемые **классификаторы".**</span><span class="sxs-lookup"><span data-stu-id="10b94-135">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="10b94-136">Это активирует другой классификатор для оценки элемента.</span><span class="sxs-lookup"><span data-stu-id="10b94-136">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="10b94-137">Choose **Send feedback** to send your evaluation of the , `match` `not a match` classifications and suggest other trainable classifiers.</span><span class="sxs-lookup"><span data-stu-id="10b94-137">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="10b94-138">Когда вы предоставляете классификатору 30 экземпляров обратной связи, он автоматически переучен.</span><span class="sxs-lookup"><span data-stu-id="10b94-138">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="10b94-139">Переподготовка может занять от одного до четырех часов.</span><span class="sxs-lookup"><span data-stu-id="10b94-139">Retraining can take from one to four hours.</span></span> <span data-ttu-id="10b94-140">Классификаторы можно переподготовить только дважды в день.</span><span class="sxs-lookup"><span data-stu-id="10b94-140">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10b94-141">Эти сведения перейти к классификатору в клиенте, **они не будут возвращаться в Корпорацию Майкрософт.**</span><span class="sxs-lookup"><span data-stu-id="10b94-141">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="10b94-142">Откройте **обучаемые классификаторы.**</span><span class="sxs-lookup"><span data-stu-id="10b94-142">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="10b94-143">Классификатор, который использовался в политике соответствия коммуникациям, будет отображаться под заголовком **"Переучение".**</span><span class="sxs-lookup"><span data-stu-id="10b94-143">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![классификатор в состоянии переподготовки](../media/classifier-retraining.png)

11. <span data-ttu-id="10b94-145">После завершения переподготовки выберите классификатор, чтобы открыть обзор переподготовки.</span><span class="sxs-lookup"><span data-stu-id="10b94-145">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Обзор результатов повторной подготовки классификаторов](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="10b94-147">Просмотрите рекомендуемое действие и сравнение прогнозирования для повторной и опубликованной версии классификатора.</span><span class="sxs-lookup"><span data-stu-id="10b94-147">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="10b94-148">Если вы удовлетворены результатами переподготовки, выберите **"Переопубликовка".**</span><span class="sxs-lookup"><span data-stu-id="10b94-148">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="10b94-149">Если вы не удовлетворены результатами переподготовки, вы можете предоставить дополнительные отзывы классификатору в интерфейсе соответствия коммуникациям и запустить еще один цикл переподготовки или ничего не делать, в этом случае опубликованная версия классификатора будет по-прежнему использоваться.</span><span class="sxs-lookup"><span data-stu-id="10b94-149">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="10b94-150">Подробные сведения о переопубликовывающих рекомендациях</span><span class="sxs-lookup"><span data-stu-id="10b94-150">Details on republishing recommendations</span></span>

<span data-ttu-id="10b94-151">Ниже немного информации о том, как мы сформулировали рекомендацию повторно опубликовать классификатор с переподготовленным классификатором или предложить дополнительную переподготовку.</span><span class="sxs-lookup"><span data-stu-id="10b94-151">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="10b94-152">Для этого требуется более глубокое понимание работы обучаемых классификаторов.</span><span class="sxs-lookup"><span data-stu-id="10b94-152">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="10b94-153">После переподготовки мы оцениваем производительность классификатора как для элементов с обратной связью, так и для всех элементов, изначально используемых для обучения классификатора.</span><span class="sxs-lookup"><span data-stu-id="10b94-153">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="10b94-154">Для встроенных моделей элементы, используемые для обучения классификатора, — это элементы, используемые корпорацией Майкрософт для создания модели.</span><span class="sxs-lookup"><span data-stu-id="10b94-154">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="10b94-155">Для пользовательских моделей элементы, используемые в исходном обучении классификатора, находятся на сайтах, добавленных для тестирования и проверки.</span><span class="sxs-lookup"><span data-stu-id="10b94-155">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="10b94-156">Мы сравниваем показатели производительности для обоих наборов элементов для классификатора с переподготовленным и опубликованным классификатором, чтобы дать рекомендации о том, были ли усовершенствования для повторной публикации.</span><span class="sxs-lookup"><span data-stu-id="10b94-156">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="10b94-157">См. также</span><span class="sxs-lookup"><span data-stu-id="10b94-157">See also</span></span>

- [<span data-ttu-id="10b94-158">Узнайте об обучаемых классификаторах</span><span class="sxs-lookup"><span data-stu-id="10b94-158">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="10b94-159">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="10b94-159">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
