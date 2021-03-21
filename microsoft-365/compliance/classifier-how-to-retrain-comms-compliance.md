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
description: Узнайте, как предоставить отзывы обучаемого классификатора в соответствии с нормами связи.
ms.openlocfilehash: 75fff8220b052618c70a6490b8c3569c11ecc861
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918150"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a><span data-ttu-id="1e82e-103">Повторное обучение классификаторов в соответствии с требованиями к обмену данными</span><span class="sxs-lookup"><span data-stu-id="1e82e-103">How to retrain a classifier in communications compliance</span></span>

<span data-ttu-id="1e82e-104">Классификатор Microsoft 365 — это средство, которое можно обучить распознавать различные типы контента, предоставляя ему примеры для анализа.</span><span class="sxs-lookup"><span data-stu-id="1e82e-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="1e82e-105">После обучения его можно использовать для определения элемента для применения меток конфиденциальности Office, политик соответствия требованиям к коммуникациям и политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="1e82e-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="1e82e-106">В этой статье показано, как повысить производительность настраиваемых классификаторов и некоторых предварительно подготовленных классификаторов, предоставив им дополнительные отзывы.</span><span class="sxs-lookup"><span data-stu-id="1e82e-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="1e82e-107">Дополнительные новости о различных типах классификаторов см. в дополнительных подробной информации о [классификаторах,](classifier-learn-about.md)которые можно обучить.</span><span class="sxs-lookup"><span data-stu-id="1e82e-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="1e82e-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="1e82e-108">Permissions</span></span>

<span data-ttu-id="1e82e-109">Чтобы получить доступ к классификаторам в центре соответствия требованиям Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="1e82e-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="1e82e-110">роль администратора соответствия требованиям или администратора данных соответствия требованиям требуется для подготовки классификатора</span><span class="sxs-lookup"><span data-stu-id="1e82e-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="1e82e-111">Для использования классификаторов в этих сценариях потребуется учетная запись с этими разрешениями:</span><span class="sxs-lookup"><span data-stu-id="1e82e-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="1e82e-112">Сценарий политики соответствия требованиям к коммуникации: администратор управления рисками изнутри, администратор надзорных обзоров</span><span class="sxs-lookup"><span data-stu-id="1e82e-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="1e82e-113">Общий рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="1e82e-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e82e-114">Вы предоставляете обратную связь в решении соответствия требованиям, которое использует классификатор в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="1e82e-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="1e82e-115">**Если у вас нет политики соответствия требованиям к коммуникациям, которая использует классификатор в качестве условия, остановитесь здесь.**</span><span class="sxs-lookup"><span data-stu-id="1e82e-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="1e82e-116">При использовании классификаторов может потребоваться повысить точность классификаций, которые они делают.</span><span class="sxs-lookup"><span data-stu-id="1e82e-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="1e82e-117">Вы делаете это, оценивая качество классификаций, сделанных для элементов, которые она определила как совпадающие или не совпадающие.</span><span class="sxs-lookup"><span data-stu-id="1e82e-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="1e82e-118">После 30 оценок классификатору требуется обратная связь и автоматически переобучение.</span><span class="sxs-lookup"><span data-stu-id="1e82e-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="1e82e-119">Чтобы узнать больше об общем процессе переподготовки классификатора, см. в ленте [Process flow for retraining a classifier.](classifier-learn-about.md#retraining-classifiers)</span><span class="sxs-lookup"><span data-stu-id="1e82e-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="1e82e-120">Классификатор уже должен быть опубликован и используется, прежде чем он может быть переобучен.</span><span class="sxs-lookup"><span data-stu-id="1e82e-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a><span data-ttu-id="1e82e-121">Переподготовка классификатора в политиках соответствия требованиям к коммуникациям</span><span class="sxs-lookup"><span data-stu-id="1e82e-121">How to retrain a classifier in communication compliance policies</span></span>

1. <span data-ttu-id="1e82e-122">Откройте политику соответствия требованиям связи, которая использует классификатор в качестве условия, и выберите один из идентифицированных элементов из списка **Ожидающих.**</span><span class="sxs-lookup"><span data-stu-id="1e82e-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="1e82e-123">Выберите ellipsis и **улучшение классификации**.</span><span class="sxs-lookup"><span data-stu-id="1e82e-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="1e82e-124">В области **Подробные отзывы,** если элемент является истинным положительным, выберите, **Match**.</span><span class="sxs-lookup"><span data-stu-id="1e82e-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="1e82e-125">Если элемент является ложным срабатываем, то есть он был неправильно включен в категорию, выберите **Not a match**.</span><span class="sxs-lookup"><span data-stu-id="1e82e-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="1e82e-126">Если есть другой классификатор, который был бы более подходящим для элемента, вы можете выбрать его из списка Предложить другие классификаторы, которые можно **обучить.**</span><span class="sxs-lookup"><span data-stu-id="1e82e-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="1e82e-127">Это вызовет другой классификатор для оценки элемента.</span><span class="sxs-lookup"><span data-stu-id="1e82e-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="1e82e-128">Вы можете предоставить обратную связь по нескольким элементов одновременно, выбрав их все, а затем выбрав **предоставить** подробные отзывы в панели команд.</span><span class="sxs-lookup"><span data-stu-id="1e82e-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="1e82e-129">Выберите **отправку** отзывов, чтобы отправить оценку `match` классификаций и `not a match` предложить другие классификаторы, которые можно обучить.</span><span class="sxs-lookup"><span data-stu-id="1e82e-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="1e82e-130">Если классификатору предоставлено 30 экземпляров отзывов, он автоматически будет переобучиваться.</span><span class="sxs-lookup"><span data-stu-id="1e82e-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="1e82e-131">Переобучение может занять от 1 до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="1e82e-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="1e82e-132">Классификаторы можно переобучить только дважды в день.</span><span class="sxs-lookup"><span data-stu-id="1e82e-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e82e-133">Эта информация отправляется в классификатор в клиенте, он **не возвращается в Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="1e82e-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="1e82e-134">Откройте **страницу классификации** данных в центре соответствия **требованиям Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="1e82e-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="1e82e-135">Откройте **классификаторы, которые можно обучить.**</span><span class="sxs-lookup"><span data-stu-id="1e82e-135">Open **Trainable classifiers**.</span></span>
8. <span data-ttu-id="1e82e-136">Классификатор, используемый в политике соответствия требованиям к коммуникациям, будет отображаться под заголовком **Re-training.**</span><span class="sxs-lookup"><span data-stu-id="1e82e-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![классификатор в состоянии переподготовки](../media/classifier-retraining.png)

9. <span data-ttu-id="1e82e-138">После завершения переподготовки выберите классификатор, чтобы открыть обзор переподготовки.</span><span class="sxs-lookup"><span data-stu-id="1e82e-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Обзор результатов переподготовки классификаторов](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="1e82e-140">Просмотрите рекомендуемое действие и сравнение прогнозов переподготовки и опубликованных в настоящее время версий классификатора.</span><span class="sxs-lookup"><span data-stu-id="1e82e-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="1e82e-141">Если вы удовлетворены результатами переподготовки, выберите **переопубликовку.**</span><span class="sxs-lookup"><span data-stu-id="1e82e-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="1e82e-142">Если вы не удовлетворены результатами переподготовки, вы можете предоставить дополнительные отзывы классификатору в интерфейсе соответствия коммуникациям и запустить еще один цикл переподготовки или ничего не делать, в этом случае опубликованная версия классификатора будет по-прежнему использоваться.</span><span class="sxs-lookup"><span data-stu-id="1e82e-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="1e82e-143">Сведения о переопубликовывающих рекомендациях</span><span class="sxs-lookup"><span data-stu-id="1e82e-143">Details on republishing recommendations</span></span>

<span data-ttu-id="1e82e-144">Вот немного сведений о том, как сформулировать рекомендацию о повторной публикации классификатора переподготовки или предложить дальнейшую переподготовку.</span><span class="sxs-lookup"><span data-stu-id="1e82e-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="1e82e-145">Для этого необходимо немного глубже понять, как работают классификаторы, которые можно обучить.</span><span class="sxs-lookup"><span data-stu-id="1e82e-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="1e82e-146">После переподготовки мы оцениваем производительность классификатора как для элементов с обратной связью, так и для всех элементов, первоначально используемых для обучения классификатора.</span><span class="sxs-lookup"><span data-stu-id="1e82e-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="1e82e-147">Для встроенных моделей элементы, используемые для обучения классификатора, являются элементами, используемыми Корпорацией Майкрософт для создания модели.</span><span class="sxs-lookup"><span data-stu-id="1e82e-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="1e82e-148">Для пользовательских моделей элементы, используемые в исходной подготовке классификатора, находятся на сайтах, добавленных для тестирования и проверки.</span><span class="sxs-lookup"><span data-stu-id="1e82e-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="1e82e-149">Мы сравниваем показатели производительности для обоих наборов элементов для классификатора переподготовки и опубликованного, чтобы дать рекомендации по улучшению переопубликовки.</span><span class="sxs-lookup"><span data-stu-id="1e82e-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="1e82e-150">См. также</span><span class="sxs-lookup"><span data-stu-id="1e82e-150">See also</span></span>

- [<span data-ttu-id="1e82e-151">Информация об обучаемых классификаторах</span><span class="sxs-lookup"><span data-stu-id="1e82e-151">Learn about trainable classifiers</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="1e82e-152">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="1e82e-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)