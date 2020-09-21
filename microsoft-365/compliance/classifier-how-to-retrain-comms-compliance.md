---
title: Как переучить классификатор в соответствии с требованиями к связи (Предварительная версия)
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
description: Узнайте, как предоставить отзыв классификатору для обучения в соответствии с требованиями к общению.
ms.openlocfilehash: 1466c211e3a4958f58a7c1f1a6a5a77bed881d60
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132357"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance-preview"></a><span data-ttu-id="15a4a-103">Как переучить классификатор в соответствии с требованиями к связи (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="15a4a-103">How to retrain a classifier in communications compliance (preview)</span></span>

<span data-ttu-id="15a4a-104">Классификатор Microsoft 365, предназначенный для обучения, — это средство, которое можно обучить для распознавания различных типов контента, предоставляя ИТ-примерам возможность взглянуть на.</span><span class="sxs-lookup"><span data-stu-id="15a4a-104">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="15a4a-105">После обучения вы можете использовать его для определения элемента для применения меток конфиденциальности Office, политик соответствия требованиям и политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="15a4a-105">Once trained, you can use it to identify item for application of Office sensitivity labels, communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="15a4a-106">В этой статье показано, как увеличить производительность настраиваемых классификаторов и предварительно обученных классификаторов, предоставив им дополнительные отзывы.</span><span class="sxs-lookup"><span data-stu-id="15a4a-106">This article shows you how to improve the performance of custom trainable classifiers and some pre-trained classifiers by providing them additional feedback.</span></span>

<span data-ttu-id="15a4a-107">Чтобы узнать больше о различных типах классификаторов, ознакомьтесь со статьей [сведения о классификаторах (Предварительная версия)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="15a4a-107">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="15a4a-108">Разрешения</span><span class="sxs-lookup"><span data-stu-id="15a4a-108">Permissions</span></span>

<span data-ttu-id="15a4a-109">Чтобы получить доступ к классификаторам в центре соответствия требованиям Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="15a4a-109">To access classifiers in the Microsoft 365 Compliance center:</span></span>

- <span data-ttu-id="15a4a-110">для обучения классификатора требуется роль администратора соответствия или администратор данных соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="15a4a-110">the Compliance admin role or Compliance Data Administrator is required to train a classifier</span></span>

<span data-ttu-id="15a4a-111">Учетные записи с этими разрешениями потребуются для использования классификаторов в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="15a4a-111">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="15a4a-112">Политика соответствия требованиям к общению: администратору управления рисками для участников программы, администратору Супервизорной проверки</span><span class="sxs-lookup"><span data-stu-id="15a4a-112">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

## <a name="overall-workflow"></a><span data-ttu-id="15a4a-113">Общий рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="15a4a-113">Overall workflow</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15a4a-114">Вы предоставляете отзыв в решении для обеспечения соответствия требованиям, которое использует классификатор в качестве условия.</span><span class="sxs-lookup"><span data-stu-id="15a4a-114">You provide feedback in the compliance solution that is using the classifier as a condition.</span></span> <span data-ttu-id="15a4a-115">**Если у вас нет политики соответствия требованиям на связь, в которой используется классификатор в качестве условия, остановите отсюда.**</span><span class="sxs-lookup"><span data-stu-id="15a4a-115">**If you don't have a communications compliance policy that uses a classifier as a condition, stop here.**</span></span>

<span data-ttu-id="15a4a-116">Когда вы используете классификаторы, вам может потребоваться увеличить точность этих классификаций.</span><span class="sxs-lookup"><span data-stu-id="15a4a-116">As you use your classifiers, you may want to increase the precision of the classifications that they're making.</span></span> <span data-ttu-id="15a4a-117">Для этого необходимо оценить качество классификаций, созданных для элементов, обнаруженных в качестве соответствия или не совпадающий.</span><span class="sxs-lookup"><span data-stu-id="15a4a-117">You do this by evaluating the quality of the classifications made  for items it has identified as being a match or not a match.</span></span> <span data-ttu-id="15a4a-118">После выполнения 30 оценочных оценок для классификатора он выполняет обратную связь и автоматически выполняет его реобучение.</span><span class="sxs-lookup"><span data-stu-id="15a4a-118">After you make 30 evaluations for a classifier it takes that feedback and automatically retrains itself.</span></span>

<span data-ttu-id="15a4a-119">Чтобы узнать больше об общем рабочем процессе рекурсии классификатора, ознакомьтесь со статьей [поток обработки для рекурсии классификатора](classifier-learn-about.md#retraining-classifiers).</span><span class="sxs-lookup"><span data-stu-id="15a4a-119">To understand more about the overall workflow of retraining a classifier, see [Process flow for retraining a classifier](classifier-learn-about.md#retraining-classifiers).</span></span>

> [!NOTE]
> <span data-ttu-id="15a4a-120">Классификатор должен быть уже опубликован и использован до его переподготовки.</span><span class="sxs-lookup"><span data-stu-id="15a4a-120">A classifier must already be published and in use before it can be retrained.</span></span>

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies-preview"></a><span data-ttu-id="15a4a-121">Реобучение классификатору в политиках обеспечения соответствия в общении (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="15a4a-121">How to retrain a classifier in communication compliance policies (preview)</span></span>

1. <span data-ttu-id="15a4a-122">Откройте политику соответствия для взаимодействия, в которой используется классификатор в качестве условия, и выберите один из идентифицированных элементов из списка **ожидания** .</span><span class="sxs-lookup"><span data-stu-id="15a4a-122">Open the Communication compliance policy that uses a classifier as a condition and choose one of the identified items from the **Pending** list.</span></span>
2. <span data-ttu-id="15a4a-123">Нажмите кнопку с многоточием и **улучшите классификацию**.</span><span class="sxs-lookup"><span data-stu-id="15a4a-123">Choose the ellipsis and **Improve classification**.</span></span>
3. <span data-ttu-id="15a4a-124">Если элемент имеет истинный положительный результат, в области **подробной обратной связи** выберите, **ПОИСКПОЗ**.</span><span class="sxs-lookup"><span data-stu-id="15a4a-124">In the **Detailed feedback** pane, if the item is a true positive, choose, **Match**.</span></span>  <span data-ttu-id="15a4a-125">Если элемент является ложным положительным, он был ошибочно включен в категорию, выберите пункт **не найдено**.</span><span class="sxs-lookup"><span data-stu-id="15a4a-125">If the item is a false positive, that is it was incorrectly included in the category, choose **Not a match**.</span></span>
4. <span data-ttu-id="15a4a-126">Если имеется другой классификатор, который будет более подходящим для элемента, можно выбрать его в списке **предлагаемые классификаторы для обучения** .</span><span class="sxs-lookup"><span data-stu-id="15a4a-126">If there is another classifier that would be more appropriate for the item, you can choose it from the **Suggest other trainable classifiers** list.</span></span> <span data-ttu-id="15a4a-127">При этом другой классификатор будет активирован для оценки элемента.</span><span class="sxs-lookup"><span data-stu-id="15a4a-127">This will trigger the other classifier to evaluate the item.</span></span>

> [!TIP]
> <span data-ttu-id="15a4a-128">Вы можете предоставить отзывы сразу для нескольких элементов, выбрав их все, а затем указав **подробную обратную связь** на панели команд.</span><span class="sxs-lookup"><span data-stu-id="15a4a-128">You can provide feedback on multiple items simultaneously by choosing them all and then choosing **Provide detailed feedback** in the command bar.</span></span>

5. <span data-ttu-id="15a4a-129">Нажмите кнопку **Отправить отзыв** , чтобы отправить результаты оценки `match` , `not a match` классификации и предложения других классификаторов, которые могут быть обучены.</span><span class="sxs-lookup"><span data-stu-id="15a4a-129">Choose **Send feedback** to send your evaluation of the `match`, `not a match` classifications and suggest other trainable classifiers.</span></span> <span data-ttu-id="15a4a-130">Когда вы предоставили классификатору 30 экземпляров обратной связи, он будет автоматически переучить.</span><span class="sxs-lookup"><span data-stu-id="15a4a-130">When you've provided 30 instances of feedback to a classifier, it will automatically  retrain.</span></span> <span data-ttu-id="15a4a-131">Для рекурсии может потребоваться от 1-4 часов.</span><span class="sxs-lookup"><span data-stu-id="15a4a-131">Retraining can take from 1-4 hours.</span></span> <span data-ttu-id="15a4a-132">Классификаторы можно переучить только дважды в день.</span><span class="sxs-lookup"><span data-stu-id="15a4a-132">Classifiers can only be retrained twice per day.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15a4a-133">Эти сведения отправляются классификатору в клиенте, **поэтому он не возвращается в корпорацию Майкрософт**.</span><span class="sxs-lookup"><span data-stu-id="15a4a-133">This information goes to the classifier in your tenant, **it does not go back to Microsoft**.</span></span>

6.  <span data-ttu-id="15a4a-134">Откройте страницу **классификация данных** в **центре соответствия требованиям Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="15a4a-134">Open the **Data classification** page in the **Microsoft 365 compliance center**.</span></span>
7. <span data-ttu-id="15a4a-135">Откройте **классификаторы, которые вы научитесь (Предварительная версия)**.</span><span class="sxs-lookup"><span data-stu-id="15a4a-135">Open **Trainable classifiers (preview)**.</span></span>
8. <span data-ttu-id="15a4a-136">Классификатор, который использовался в политике соответствия требованиям, будет отображаться под заголовком " **повторное обучение** ".</span><span class="sxs-lookup"><span data-stu-id="15a4a-136">The classifier that was used in your Communications compliance policy will appear under the **Re-training** heading.</span></span>

![Классификатор в состоянии переподготовки](../media/classifier-retraining.png)

9. <span data-ttu-id="15a4a-138">После завершения переподготовки выберите классификатор, чтобы открыть обзор переподготовки.</span><span class="sxs-lookup"><span data-stu-id="15a4a-138">Once retraining completes, choose the classifier to open the retraining overview.</span></span>

![Обзор результатов по расучению классификатора](../media/classifier-retraining-overview.png)

10. <span data-ttu-id="15a4a-140">Ознакомьтесь с рекомендуемым действием и сравнением прогноза для версий классификатора, переученных и опубликованных в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="15a4a-140">Review the recommended action, and the prediction comparisons of the retrained and currently published versions of the classifier.</span></span>
11. <span data-ttu-id="15a4a-141">Если вы удовлетворены результатами повторного изучения, нажмите кнопку **повторно опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="15a4a-141">If you satisfied with the results of the retraining, choose **Re-publish**.</span></span>
12. <span data-ttu-id="15a4a-142">Если вы не удовлетворены результатами повторного изучения, вы можете предоставить дополнительную реакцию классификатора в интерфейсе обеспечения соответствия требованиям и запустить другой цикл повторного обучения или ничего не делать, если в данный момент опубликованная версия классификатора будет продолжать использоваться.</span><span class="sxs-lookup"><span data-stu-id="15a4a-142">If you are not satisfied with the results of the retraining, you can choose to provide additional feedback to the classifier in the Communications compliance interface and start another retraining cycle or do nothing in which case the currently published version of the classifier will continue to be used.</span></span> 

## <a name="details-on-republishing-recommendations"></a><span data-ttu-id="15a4a-143">Сведения о повторной публикации рекомендаций</span><span class="sxs-lookup"><span data-stu-id="15a4a-143">Details on republishing recommendations</span></span>

<span data-ttu-id="15a4a-144">Ниже приведены некоторые сведения о том, как мы определяем рекомендацию для повторной публикации переназначенного классификатора или предложения дальнейших переработок.</span><span class="sxs-lookup"><span data-stu-id="15a4a-144">Here is a little information on how we formulate the recommendation to re-publish a retrained classifier or suggest further retraining.</span></span> <span data-ttu-id="15a4a-145">Это требует более глубокого понимания принципов работы классификаторов, предназначенных для обучения.</span><span class="sxs-lookup"><span data-stu-id="15a4a-145">This requires a little deeper understanding of how trainable classifiers work.</span></span>

<span data-ttu-id="15a4a-146">После переподготовки мы оцениваем производительность классификатора для элементов с обратной связью, а также для всех элементов, изначально использованных для обучения классификатора.</span><span class="sxs-lookup"><span data-stu-id="15a4a-146">After a retrain, we evaluate the classifier's performance on both the items with feedback as well as any items originally used to train the classifier.</span></span> 

- <span data-ttu-id="15a4a-147">Для встроенных моделей элементы, используемые для обучения классификатора, это элементы, используемые корпорацией Майкрософт для создания модели.</span><span class="sxs-lookup"><span data-stu-id="15a4a-147">For built-in models, items used to train the classifier are the items used by Microsoft to build the model.</span></span>
- <span data-ttu-id="15a4a-148">Для настраиваемых моделей элементы, используемые при исходном обучении классификатора, находятся на сайтах, добавленных для тестирования и рецензирования.</span><span class="sxs-lookup"><span data-stu-id="15a4a-148">For custom models, items used in the original training the classifier are from the sites you had added for test and review.</span></span>

<span data-ttu-id="15a4a-149">Мы сравниваем номера производительности в обоих наборах элементов для реученного и опубликованного классификатора, чтобы предоставить рекомендации о том, было ли возобновлено улучшение публикации.</span><span class="sxs-lookup"><span data-stu-id="15a4a-149">We compare the performance numbers on both sets of items for the retrained and published classifier to provide a recommendation on whether there was improvement to republish.</span></span> 

## <a name="see-also"></a><span data-ttu-id="15a4a-150">См. также</span><span class="sxs-lookup"><span data-stu-id="15a4a-150">See also</span></span>

- [<span data-ttu-id="15a4a-151">Сведения о классификаторах для обучения (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="15a4a-151">Learn about trainable classifiers (preview)</span></span>](classifier-learn-about.md)
- [<span data-ttu-id="15a4a-152">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="15a4a-152">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
