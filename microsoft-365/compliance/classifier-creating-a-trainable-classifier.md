---
title: Создание классификатора для обучения (Предварительная версия)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Используйте предназначенные для обучения классификаторы, если один из встроенных классификаторов не отвечает вашим потребностям. Классификатор Microsoft 365 — это инструмент, который можно обучить для распознавания различных типов контента, предоставляя им примеры для поиска. В этом разделе показано, как создать настраиваемый классификатор.
ms.openlocfilehash: 05ec9992fb4ec072403e193df3d7dbbbb8b1a96b
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126360"
---
# <a name="creating-a-trainable-classifier-preview"></a><span data-ttu-id="32916-105">Создание классификатора для обучения (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="32916-105">Creating a trainable classifier (preview)</span></span>

<span data-ttu-id="32916-106">Используйте предназначенные для обучения классификаторы, если один из классификаторов не отвечает вашим потребностям.</span><span class="sxs-lookup"><span data-stu-id="32916-106">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="32916-107">Классификатор Microsoft 365 — это инструмент, который можно обучить для распознавания различных типов контента, предоставляя им примеры для поиска.</span><span class="sxs-lookup"><span data-stu-id="32916-107">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="32916-108">Обучение классификатору включает в себя предварительные примеры, которые применяют человеческий персонал и однозначно совпадают со категорией.</span><span class="sxs-lookup"><span data-stu-id="32916-108">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="32916-109">После этого вы тестируете прогнозы, предоставляя им смесь положительных и отрицательных примеров.</span><span class="sxs-lookup"><span data-stu-id="32916-109">Then, after it has processed those, you test the predictions by giving it a mix of positive and negative samples.</span></span>

<span data-ttu-id="32916-110">Чтобы узнать больше о различных типах классификаторов, ознакомьтесь со статьей [Начало работы с обучением классификаторов (Предварительная версия)](classifier-getting-started-with.md)</span><span class="sxs-lookup"><span data-stu-id="32916-110">To learn more about the different types of classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md)</span></span>

<span data-ttu-id="32916-111">Эта временная шкала отражает пример развертывания.</span><span class="sxs-lookup"><span data-stu-id="32916-111">This timeline reflects a sample deployment.</span></span>

![обучение — классификатор — временная шкала](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="32916-113">В первый раз для обучения классификаторам необходим явный запрос.</span><span class="sxs-lookup"><span data-stu-id="32916-113">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="32916-114">Для выполнения базовой оценки контента организации в Microsoft 365 требуется 12 дней.</span><span class="sxs-lookup"><span data-stu-id="32916-114">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="32916-115">Обратитесь к глобальному администратору, чтобы отказаться от участия в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="32916-115">Contact your global administrator to kick off the opt-in process.</span></span>

## <a name="seed-content"></a><span data-ttu-id="32916-116">Начальное содержимое</span><span class="sxs-lookup"><span data-stu-id="32916-116">Seed content</span></span>

<span data-ttu-id="32916-117">Если вы хотите, чтобы предназначенный для обучения классификатор был независимым и точно определить элемент в определенной категории контента, сначала необходимо предоставить ему множество образцов типа контента, находящиеся в категории.</span><span class="sxs-lookup"><span data-stu-id="32916-117">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="32916-118">Такое подача образцов классификатору, предназначенному для обучения, называется *Заполнение*.</span><span class="sxs-lookup"><span data-stu-id="32916-118">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="32916-119">Начальное содержимое выбирается человеком и определяется для представления категории контента.</span><span class="sxs-lookup"><span data-stu-id="32916-119">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="32916-120">Необходимо иметь по крайней мере 50 положительные примеры и до 500.</span><span class="sxs-lookup"><span data-stu-id="32916-120">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="32916-121">Классификатор, который будет обучаться, будет обрабатываться в 500 самых последних созданных примеров (по дате создания файла или метки времени).</span><span class="sxs-lookup"><span data-stu-id="32916-121">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="32916-122">Чем больше предоставленных примеров, тем точнее прогнозы, которые будет выполнять классификатор.</span><span class="sxs-lookup"><span data-stu-id="32916-122">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

## <a name="testing-content"></a><span data-ttu-id="32916-123">Тестирование содержимого</span><span class="sxs-lookup"><span data-stu-id="32916-123">Testing content</span></span>

<span data-ttu-id="32916-124">После того как классификатор обработал достаточное количество положительных образцов для создания прогнозной модели, необходимо протестировать прогноз, чтобы определить, может ли классификатор правильно различать элементы, которые совпадают со категорией и элементами.</span><span class="sxs-lookup"><span data-stu-id="32916-124">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="32916-125">Для этого вы передаете другое, надеемся, что набор собраний, который содержит примеры, которые должны относиться к категории и примерам.</span><span class="sxs-lookup"><span data-stu-id="32916-125">You do this by feeding it another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="32916-126">После обработки этих результатов вручную пройдите по результатам и убедитесь, что каждый прогноз является правильным, неверным или нет.</span><span class="sxs-lookup"><span data-stu-id="32916-126">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="32916-127">Классификатор для обучения использует этот отзыв для усовершенствования модели прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="32916-127">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="32916-128">Для достижения лучших результатов Попросите 10 000 элементов в образце теста с одинаковым распределением положительных и отрицательных совпадений.</span><span class="sxs-lookup"><span data-stu-id="32916-128">For best results, have 10,000 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="32916-129">Создание классификатора для обучения</span><span class="sxs-lookup"><span data-stu-id="32916-129">How to create a trainable classifier</span></span>

1. <span data-ttu-id="32916-130">Сбор данных между начальными элементами содержимого 50-500.</span><span class="sxs-lookup"><span data-stu-id="32916-130">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="32916-131">Они должны быть только примерами, которые строго представляют тип контента, который классификатор должен указать в категории классификации.</span><span class="sxs-lookup"><span data-stu-id="32916-131">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="32916-132">В SharePoint Server для поддерживаемых типов файлов вы найдете файлы с [расширениями для обхода по умолчанию и проанализированные типы файлов](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) .</span><span class="sxs-lookup"><span data-stu-id="32916-132">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32916-133">Начальные и проверочные элементы примеров не должны быть зашифрованы и должны быть на английском языке.</span><span class="sxs-lookup"><span data-stu-id="32916-133">The seed and test sample items must not be encrypted and they must be in English.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32916-134">Убедитесь, что элементы в наборе начального значения являются **надежными** примерами категории.</span><span class="sxs-lookup"><span data-stu-id="32916-134">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="32916-135">Классификатор, для которого выполняется обучение, изначально создает свою модель в зависимости от того, что вы инициализируем.</span><span class="sxs-lookup"><span data-stu-id="32916-135">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="32916-136">Классификатор предполагает, что все примеры начального значения являются надежными и не позволяют узнать, является ли пример слабым или отрицательным для категории.</span><span class="sxs-lookup"><span data-stu-id="32916-136">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="32916-137">Поместите начальное содержимое в папку SharePoint Online, предназначенную для хранения *только начального контента*.</span><span class="sxs-lookup"><span data-stu-id="32916-137">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="32916-138">Запишите URL-адрес сайта, библиотеки и папки.</span><span class="sxs-lookup"><span data-stu-id="32916-138">Make note of the site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="32916-139">Если вы создаете новый сайт и папку для своих начальных данных, разрешите индексирование этого расположения по крайней мере в течение часа, прежде чем создавать предназначенный для обучения классификатор, который будет использовать эти начальные данные.</span><span class="sxs-lookup"><span data-stu-id="32916-139">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="32916-140">Войдите в центр соответствия требованиям Microsoft 365, используя доступ к роли администратора безопасности или администратора безопасности и откройте **центр соответствия требованиям Microsoft 365** или **Майкрософт 365 Data Center Security Center**  >  **Data classification**</span><span class="sxs-lookup"><span data-stu-id="32916-140">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**</span></span>

4. <span data-ttu-id="32916-141">Выберите вкладку **классификаторы для обучения** .</span><span class="sxs-lookup"><span data-stu-id="32916-141">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="32916-142">Выберите **создать классификатор для обучения**.</span><span class="sxs-lookup"><span data-stu-id="32916-142">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="32916-143">Введите подходящие значения для `Name` `Description` полей и категорий элементов, которые должны быть идентифицированы этим классификатором для обучения.</span><span class="sxs-lookup"><span data-stu-id="32916-143">Fill in appropriate values for the `Name`, and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="32916-144">Введите точный сайт SharePoint Online, библиотеку и URL-адрес папки начального контента, начиная с шага 2.</span><span class="sxs-lookup"><span data-stu-id="32916-144">Enter the exact SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="32916-145">Выберите `Add` .</span><span class="sxs-lookup"><span data-stu-id="32916-145">Choose `Add`.</span></span>

8. <span data-ttu-id="32916-146">Проверьте параметры и нажмите кнопку `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="32916-146">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="32916-147">В течение 24 часов классификатор с обучением будет обрабатывать начальные данные и создавать прогнозную модель.</span><span class="sxs-lookup"><span data-stu-id="32916-147">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="32916-148">Состояние классификатора это `In progress` время обработки начального значения.</span><span class="sxs-lookup"><span data-stu-id="32916-148">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="32916-149">Когда классификатор закончит обработку начальных данных, состояние изменится на `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="32916-149">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="32916-150">Теперь вы можете просмотреть страницу сведений, выбрав классификатор.</span><span class="sxs-lookup"><span data-stu-id="32916-150">You can now view the details page by choosing the classifier.</span></span>


![подготовленный классификатор для тестирования](../media/classifier-trainable-ready-to-test-detail.png)

11. <span data-ttu-id="32916-152">Соберите по крайней мере 200 тестовых элементов контента.</span><span class="sxs-lookup"><span data-stu-id="32916-152">Collect at least 200 test content items.</span></span> <span data-ttu-id="32916-153">Для достижения лучших результатов Корпорация Майкрософт рекомендует 10 000.</span><span class="sxs-lookup"><span data-stu-id="32916-153">Microsoft recommends 10,000 for best results.</span></span> <span data-ttu-id="32916-154">Они должны быть смесью элементов, которые являются надежными положительными значениями, а некоторые — небольшими очевидными причинами.</span><span class="sxs-lookup"><span data-stu-id="32916-154">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="32916-155">В SharePoint Server для поддерживаемых типов файлов вы найдете файлы с [расширениями для обхода по умолчанию и проанализированные типы файлов](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) .</span><span class="sxs-lookup"><span data-stu-id="32916-155">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32916-156">Элементы примера не должны быть зашифрованы и должны быть на английском языке.</span><span class="sxs-lookup"><span data-stu-id="32916-156">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="32916-157">Поместите тестовый контент в папку SharePoint Online, предназначенную для хранения *только тестового контента*.</span><span class="sxs-lookup"><span data-stu-id="32916-157">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="32916-158">Запишите URL-адрес сайта, библиотеки и папки SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="32916-158">Make note of the SharePoint Online site, library, and folder URL.</span></span>

> [!TIP]
> <span data-ttu-id="32916-159">Если вы создаете новый сайт и папку для тестовых данных, разрешите индексирование этого расположения по крайней мере в течение часа перед созданием классификатора, который будет использовать эти начальные данные.</span><span class="sxs-lookup"><span data-stu-id="32916-159">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="32916-160">Выберите `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="32916-160">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="32916-161">Введите точный сайт SharePoint Online, библиотеку и URL-адрес для тестового сайта контента с шага 12.</span><span class="sxs-lookup"><span data-stu-id="32916-161">Enter the exact SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="32916-162">Выберите `Add` .</span><span class="sxs-lookup"><span data-stu-id="32916-162">Choose `Add`.</span></span>

15. <span data-ttu-id="32916-163">Завершите работу мастера, нажав кнопку `Done` .</span><span class="sxs-lookup"><span data-stu-id="32916-163">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="32916-164">Для обработки тестовых файлов классификатор должен пройти до часа.</span><span class="sxs-lookup"><span data-stu-id="32916-164">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="32916-165">Когда предназначенный для обучения классификатор обрабатывает тестовые файлы, состояние на странице сведений изменится на `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="32916-165">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="32916-166">Если требуется увеличить размер образца теста, выберите `Add items to test` и разрешите классификатору обрабатывать дополнительные элементы.</span><span class="sxs-lookup"><span data-stu-id="32916-166">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

![готовность к просмотру снимка экрана](../media/classifier-trainable-ready-to-review-detail.png)

17. <span data-ttu-id="32916-168">Нажмите `Tested items to review` клавишу TAB для просмотра элементов.</span><span class="sxs-lookup"><span data-stu-id="32916-168">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="32916-169">В Microsoft 365 в каждый момент времени будет находиться 30 элементов.</span><span class="sxs-lookup"><span data-stu-id="32916-169">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="32916-170">Просмотрите их и в `We predict this item is "Relevant". Do you agree?` поле выберите либо `Yes` или `No` `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="32916-170">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="32916-171">Точность модели автоматически обновляется после каждых 30 элементов.</span><span class="sxs-lookup"><span data-stu-id="32916-171">Model accuracy is automatically updated after every 30 items.</span></span>

![поле "Просмотр элементов"](../media/classifier-trainable-review-detail.png)

19. <span data-ttu-id="32916-173">Просмотрите *по крайней мере* 200 элементов.</span><span class="sxs-lookup"><span data-stu-id="32916-173">Review *at least* 200 items.</span></span>

<!-- insert Analyze steps here-->

20. <span data-ttu-id="32916-174">Продолжайте просмотр до тех пор, пока точность не достигнет минимум 70%, а `Publish the classifier` состояние — `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="32916-174">Continue to review until the accuracy reaches at least 70% and the `Publish the classifier` status is `Ready to use`.</span></span>

![точность и готовность к публикации](../media/classifier-trainable-review-ready-to-publish.png)

21. <span data-ttu-id="32916-176">Опубликуйте классификатор.</span><span class="sxs-lookup"><span data-stu-id="32916-176">Publish the classifier.</span></span>

22. <span data-ttu-id="32916-177">После публикации классификатор будет доступен в качестве условия в [подметке Office с метками конфиденциальности](apply-sensitivity-label-automatically.md), [автоматически применять политику меток хранения на основе условия](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) и в [соответствии с соответствием связью](communication-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="32916-177">Once published your classifier will be available as a condition in [Office autolabeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="32916-178">После публикации классификатор не может пройти какие-либо дополнительные обучающие материалы, поэтому убедитесь, что вы тестировали и проверили как можно больше элементов, чтобы убедиться, что точность максимально высока.</span><span class="sxs-lookup"><span data-stu-id="32916-178">Once a classifier is published, it can't go through any additional training, so be very sure that you have tested and reviewed as many items as possible to ensure that the accuracy is as high as possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="32916-179">См. также</span><span class="sxs-lookup"><span data-stu-id="32916-179">See also</span></span>

- [<span data-ttu-id="32916-180">Начало работы с обучаемыми классификаторами (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="32916-180">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="32916-181">Анализируемые типы файлов и расширения имен файлов для обхода по умолчанию в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="32916-181">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
