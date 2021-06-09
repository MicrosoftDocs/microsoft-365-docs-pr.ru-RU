---
title: Повторное обучение классификаторов в обозревателе содержимого
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
description: Узнайте, как предоставить отзывы обучаемому классификатору в обозревателе контента.
ms.openlocfilehash: ef0539a3d474ffecaeac8633b4a58aa068a5c182
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793068"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="17271-103">Повторное обучение классификаторов в обозревателе содержимого</span><span class="sxs-lookup"><span data-stu-id="17271-103">How to retrain a classifier in content explorer</span></span>

<span data-ttu-id="17271-104">Классификатор Microsoft 365, который можно обучить распознавать различные типы контента, предоставляя ему примеры для анализа.</span><span class="sxs-lookup"><span data-stu-id="17271-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="17271-105">После обучения вы можете использовать его для определения элемента для применения меток Office, политик соответствия требованиям к коммуникациям и политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="17271-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="17271-106">В этой статье показано, как повысить производительность настраиваемых классификаторов и некоторых предварительно подготовленных классификаторов, предоставив им дополнительные отзывы.</span><span class="sxs-lookup"><span data-stu-id="17271-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="17271-107">Дополнительные новости о различных типах классификаторов см. в дополнительных подробной информации о [классификаторах,](classifier-learn-about.md)которые можно обучить.</span><span class="sxs-lookup"><span data-stu-id="17271-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="17271-108">Просмотрите это видео для краткой сводки процесса настройки и переподготовки.</span><span class="sxs-lookup"><span data-stu-id="17271-108">Watch this video for a quick summary of the tuning and retraining process.</span></span> <span data-ttu-id="17271-109">Вам по-прежнему необходимо прочитать эту полную статью, чтобы получить подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="17271-109">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a><span data-ttu-id="17271-110">Разрешения</span><span class="sxs-lookup"><span data-stu-id="17271-110">Permissions</span></span>

<span data-ttu-id="17271-111">Чтобы получить доступ к классификаторам в центре Microsoft 365 соответствия требованиям:</span><span class="sxs-lookup"><span data-stu-id="17271-111">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="17271-112">роль администратора соответствия требованиям или администратора данных соответствия требованиям требуется для подготовки классификатора</span><span class="sxs-lookup"><span data-stu-id="17271-112">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="17271-113">Для использования классификаторов в этих сценариях потребуется учетная запись с этими разрешениями:</span><span class="sxs-lookup"><span data-stu-id="17271-113">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="17271-114">Сценарий политики меток хранения: роли управления записями и управления хранением</span><span class="sxs-lookup"><span data-stu-id="17271-114">Retention label policy scenario: Record Management and Retention Management roles</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="17271-115">Общий рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="17271-115">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17271-116">Вы предоставляете обратную связь в обозревателе контента для автоматического применения политик меток хранения для Exchange элементов и использует классификатор в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="17271-116">You provide feedback in content explorer for auto-apply retention label policies to Exchange items and uses the classifier as a condition.</span></span> <span data-ttu-id="17271-117">**Если у вас нет политики хранения, которая автоматически применяет метку хранения для Exchange элементов и использует классификатор в качестве условия, остановитесь здесь.**</span><span class="sxs-lookup"><span data-stu-id="17271-117">**If you don't have a retention policy that auto-applies a retention label to Exchange items and      uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="17271-118">При использовании классификаторов может потребоваться повысить точность классификаций, которые они делают.</span><span class="sxs-lookup"><span data-stu-id="17271-118">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="17271-119">Вы делаете это, оценивая качество классификаций, сделанных для элементов, которые она определила как совпадающие или не совпадающие.</span><span class="sxs-lookup"><span data-stu-id="17271-119">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="17271-120">После 30 оценок классификатору требуется обратная связь и автоматически переобучение.</span><span class="sxs-lookup"><span data-stu-id="17271-120">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="17271-121">Чтобы узнать больше об общем процессе переподготовки классификатора, см. в ленте [Process flow for retraining a classifier.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="17271-121">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="17271-122">Классификатор уже должен быть опубликован и используется, прежде чем он может быть переобучен.</span><span class="sxs-lookup"><span data-stu-id="17271-122">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a><span data-ttu-id="17271-123">Повторное обучение классификаторов в обозревателе содержимого</span><span class="sxs-lookup"><span data-stu-id="17271-123">How to retrain a classifier in content explorer</span></span>

1. <span data-ttu-id="17271-124">Во входе в Microsoft 365 центра соответствия требованиям с доступом к роли **администратора** или администратора безопасности и откройте Microsoft 365 центр классификации данных  >    >  **контента.**</span><span class="sxs-lookup"><span data-stu-id="17271-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** > **Data classification** > **Content explorer**.</span></span> 
2. <span data-ttu-id="17271-125">В соответствии со списком Фильтр на **метки, типы** информации или категории расширяют **классификаторы,** которые можно обучить.</span><span class="sxs-lookup"><span data-stu-id="17271-125">Under the **Filter on labels, info types, or categories** list, expand **Trainable classifiers**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17271-126">Для появления агрегированных элементов под заголовком обучаемые классификаторы может занять до восьми дней.</span><span class="sxs-lookup"><span data-stu-id="17271-126">It can take up to eight days for aggregated items to appear under the trainable classifiers heading.</span></span>

3. <span data-ttu-id="17271-127">Выберите классификатор, используемый в политике автоматического применения метки хранения.</span><span class="sxs-lookup"><span data-stu-id="17271-127">Choose the trainable classifier you used in you auto-apply retention label policy.</span></span> <span data-ttu-id="17271-128">Это классификатор, который можно обучить.</span><span class="sxs-lookup"><span data-stu-id="17271-128">This is the trainable classifier you will give feedback on.</span></span>

> [!NOTE]
> <span data-ttu-id="17271-129">Если элемент имеет запись в столбце **Метка Хранения,** это означает, что элемент классифицируется как `match` .</span><span class="sxs-lookup"><span data-stu-id="17271-129">If an item has an entry in the **Retention label** column, it means that the item was classified as a `match`.</span></span>  <span data-ttu-id="17271-130">Если элемент не имеет записи в столбце **Метка хранения,** это означает, что он был классифицирован как `close match` .</span><span class="sxs-lookup"><span data-stu-id="17271-130">If an item doesn't have an entry in the **Retention label** column, it means it was classified as a `close match`.</span></span> <span data-ttu-id="17271-131">Вы можете повысить точность классификатора больше всего, предоставив обратную связь по `close match` пунктам.</span><span class="sxs-lookup"><span data-stu-id="17271-131">You can improve the classifier precision the most by providing feedback on `close match` items.</span></span> 

4. <span data-ttu-id="17271-132">Выберите элемент и откройте его.</span><span class="sxs-lookup"><span data-stu-id="17271-132">Choose an item and open it.</span></span>
 
 > [!TIP]
> <span data-ttu-id="17271-133">Вы можете предоставить обратную связь по нескольким пунктам одновременно, выбрав их все, а затем выбрав **классификацию Улучшения** в панели команд.</span><span class="sxs-lookup"><span data-stu-id="17271-133">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Improve classification** in the command bar.</span></span>

5. <span data-ttu-id="17271-134">Выберите **Предоставление обратной связи**.</span><span class="sxs-lookup"><span data-stu-id="17271-134">Choose **Provide feedback**.</span></span>
6. <span data-ttu-id="17271-135">В области **Подробные отзывы,** если элемент является истинным положительным, выберите, **Match**.</span><span class="sxs-lookup"><span data-stu-id="17271-135">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="17271-136">Если элемент является ложным срабатываем, то есть он был неправильно включен в категорию, выберите **Not a match**.</span><span class="sxs-lookup"><span data-stu-id="17271-136">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
7. <span data-ttu-id="17271-137">Если есть другой классификатор, который был бы более подходящим для элемента, вы можете выбрать его из списка Предложить другие классификаторы, которые можно **обучить.**</span><span class="sxs-lookup"><span data-stu-id="17271-137">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="17271-138">Это вызовет другой классификатор для оценки элемента.</span><span class="sxs-lookup"><span data-stu-id="17271-138">This will trigger the other classifier to evaluate the item.</span></span>
8. <span data-ttu-id="17271-139">Выберите **отправку** отзывов, чтобы отправить оценку `match` классификаций и `not a match` предложить другие классификаторы, которые можно обучить.</span><span class="sxs-lookup"><span data-stu-id="17271-139">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="17271-140">Если классификатору предоставлено 30 экземпляров отзывов, он автоматически будет переобучиваться.</span><span class="sxs-lookup"><span data-stu-id="17271-140">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="17271-141">Переобучение может занять от одного до четырех часов.</span><span class="sxs-lookup"><span data-stu-id="17271-141">Retraining can take from one to four hours.</span></span> <span data-ttu-id="17271-142">Классификаторы можно переобучить только дважды в день.</span><span class="sxs-lookup"><span data-stu-id="17271-142">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17271-143">Эта информация отправляется в классификатор в клиенте, он **не возвращается в Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="17271-143">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

9. <span data-ttu-id="17271-144">Откройте **классификаторы, которые можно обучить.**</span><span class="sxs-lookup"><span data-stu-id="17271-144">Open **Trainable classifiers**.</span></span>
10. <span data-ttu-id="17271-145">Классификатор, используемый в политике соответствия требованиям к коммуникациям, будет отображаться под заголовком **Re-training.**</span><span class="sxs-lookup"><span data-stu-id="17271-145">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![классификатор в состоянии переподготовки](../media/classifier-retraining.png)

11. <span data-ttu-id="17271-147">После завершения переподготовки выберите классификатор, чтобы открыть обзор переподготовки.</span><span class="sxs-lookup"><span data-stu-id="17271-147">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Обзор результатов переподготовки классификаторов](../media/classifier-retraining-overview.png)

12. <span data-ttu-id="17271-149">Просмотрите рекомендуемое действие и сравнение прогнозов переподготовки и опубликованных в настоящее время версий классификатора.</span><span class="sxs-lookup"><span data-stu-id="17271-149">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
13. <span data-ttu-id="17271-150">Если вы удовлетворены результатами переподготовки, выберите **переопубликовку.**</span><span class="sxs-lookup"><span data-stu-id="17271-150">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
14. <span data-ttu-id="17271-151">Если вы не удовлетворены результатами переподготовки, вы можете предоставить дополнительные отзывы классификатору в интерфейсе Content Explorer и запустить еще один цикл переподготовки или ничего не делать, в этом случае в настоящее время опубликованная версия классификатора будет по-прежнему использоваться.</span><span class="sxs-lookup"><span data-stu-id="17271-151">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Content Explorer interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="17271-152">Сведения о переопубликовывающих рекомендациях</span><span class="sxs-lookup"><span data-stu-id="17271-152">Details on republishing recommendations</span></span>

<span data-ttu-id="17271-153">Вот немного сведений о том, как сформулировать рекомендацию о повторной публикации классификатора переподготовки или предложить дальнейшую переподготовку.</span><span class="sxs-lookup"><span data-stu-id="17271-153">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="17271-154">Для этого необходимо немного глубже понять, как работают классификаторы, которые можно обучить.</span><span class="sxs-lookup"><span data-stu-id="17271-154">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="17271-155">После переподготовки мы оцениваем производительность классификатора как для элементов с обратной связью, так и для всех элементов, первоначально используемых для обучения классификатора.</span><span class="sxs-lookup"><span data-stu-id="17271-155">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="17271-156">Для встроенных моделей элементы, используемые для обучения классификатора, являются элементами, используемыми Корпорацией Майкрософт для создания модели.</span><span class="sxs-lookup"><span data-stu-id="17271-156">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="17271-157">Для пользовательских моделей элементы, используемые в исходной подготовке классификатора, находятся на сайтах, добавленных для тестирования и проверки.</span><span class="sxs-lookup"><span data-stu-id="17271-157">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="17271-158">Мы сравниваем показатели производительности для обоих наборов элементов для классификатора переподготовки и опубликованного, чтобы дать рекомендации по улучшению переопубликовки.</span><span class="sxs-lookup"><span data-stu-id="17271-158">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="17271-159">См. также</span><span class="sxs-lookup"><span data-stu-id="17271-159">See also</span></span>

- [<span data-ttu-id="17271-160">Информация об обучаемых классификаторах</span><span class="sxs-lookup"><span data-stu-id="17271-160">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="17271-161">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="17271-161">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)