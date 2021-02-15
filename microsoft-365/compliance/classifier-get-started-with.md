---
title: Начало работы с обучаемыми классификаторами
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
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Классификатор Microsoft 365 — это средство, которое можно обучить распознавать различные типы контента, предоставляя ему примеры для анализа. В этой статье показано, как создать и обучить настраиваемый классификатор, а также как переучить их для повышения точности.
ms.openlocfilehash: bca1de5edc3efd38f943b02091c3f47d832e6a19
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752663"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="34579-104">Начало работы с обучаемыми классификаторами</span><span class="sxs-lookup"><span data-stu-id="34579-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="34579-105">Обучаемый классификатор Microsoft 365 — это средство, которое можно обучить распознавать различные типы контента, предоставляя ему примеры для анализа.</span><span class="sxs-lookup"><span data-stu-id="34579-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="34579-106">После обучения его можно использовать для идентификации элемента для применения меток конфиденциальности Office, политик соответствия коммуникациям и политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="34579-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="34579-107">Для создания настраиваемого обучаемого классификатора сначала нужно дать ему образцы, которые человек выбирает и положительно соответствует категории.</span><span class="sxs-lookup"><span data-stu-id="34579-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="34579-108">Затем после их обработки вы тестируете способность классификаторов прогнозировать, предоставляя ей сочетание положительных и отрицательных примеров.</span><span class="sxs-lookup"><span data-stu-id="34579-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="34579-109">В этой статье показано, как создать и обучить настраиваемый классификатор, а также повысить производительность настраиваемых обучаемых классификаторов и предварительно обученных классификаторов за время их существования путем переподготовки.</span><span class="sxs-lookup"><span data-stu-id="34579-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="34579-110">Дополнительные информацию о различных типах классификаторов см. в дополнительных данных об обучаемых [классификаторах.](classifier-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="34579-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="34579-111">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="34579-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="34579-112">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="34579-112">Licensing requirements</span></span>

<span data-ttu-id="34579-113">Классификаторы — это функция соответствия требованиям Microsoft 365 E5 или E5.</span><span class="sxs-lookup"><span data-stu-id="34579-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="34579-114">Чтобы использовать их, необходимо иметь одну из этих подписок.</span><span class="sxs-lookup"><span data-stu-id="34579-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="34579-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="34579-115">Permissions</span></span>

<span data-ttu-id="34579-116">Для доступа к классификаторам в пользовательском интерфейсе:</span><span class="sxs-lookup"><span data-stu-id="34579-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="34579-117">Глобальный администратор должен выбрать для клиента создание настраиваемые классификаторы.</span><span class="sxs-lookup"><span data-stu-id="34579-117">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="34579-118">Для обучения классификатора необходима роль администратора соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="34579-118">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="34579-119">Для использования классификаторов в таких сценариях необходимы учетные записи с этими разрешениями:</span><span class="sxs-lookup"><span data-stu-id="34579-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="34579-120">Сценарий политики меток хранения: роли управления записями и управления хранением</span><span class="sxs-lookup"><span data-stu-id="34579-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="34579-121">Сценарий политики меток конфиденциальности: администратор безопасности, администратор соответствия требованиям, администратор данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="34579-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="34579-122">Сценарий политики соответствия коммуникациям: администратор управления рисками, администратор надзорной проверки</span><span class="sxs-lookup"><span data-stu-id="34579-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="34579-123">По умолчанию только пользователь, создавший настраиваемый классификатор, может обучить и просмотреть прогнозы, сделанные этим классификатором.</span><span class="sxs-lookup"><span data-stu-id="34579-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="34579-124">Подготовка настраиваемого обучаемого классификатора</span><span class="sxs-lookup"><span data-stu-id="34579-124">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="34579-125">Перед началом обучения полезно понять, что необходимо для создания настраиваемого обучаемого классификатора.</span><span class="sxs-lookup"><span data-stu-id="34579-125">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="34579-126">Временная шкала</span><span class="sxs-lookup"><span data-stu-id="34579-126">Timeline</span></span>

<span data-ttu-id="34579-127">Эта временная шкала отражает пример развертывания обучаемых классификаторов.</span><span class="sxs-lookup"><span data-stu-id="34579-127">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="34579-129">Для обучаемых классификаторов требуется в первый раз в этом случае.</span><span class="sxs-lookup"><span data-stu-id="34579-129">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="34579-130">Чтобы выполнить базовую оценку содержимого вашей организации, microsoft 365 занимает 12 дней.</span><span class="sxs-lookup"><span data-stu-id="34579-130">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="34579-131">Обратитесь к глобальному администратору, чтобы при первой же процедуре получить отказ.</span><span class="sxs-lookup"><span data-stu-id="34579-131">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="34579-132">Общий рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="34579-132">Overall workflow</span></span>

<span data-ttu-id="34579-133">Подробнее об общем процессе создания настраиваемых обучаемых классификаторов см. в процедуре создания обучаемых [классификаторов клиентов.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span><span class="sxs-lookup"><span data-stu-id="34579-133">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="34579-134">Содержимое "Seed"</span><span class="sxs-lookup"><span data-stu-id="34579-134">Seed content</span></span>

<span data-ttu-id="34579-135">Если вы хотите, чтобы обучаемый классификатор независимо и точно определял элемент как определенный классификатор, сначала необходимо представить ему множество примеров типа контента, которые находятся в этой категории.</span><span class="sxs-lookup"><span data-stu-id="34579-135">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="34579-136">Это подача образцов в обучаемый классификатор называется *засеяния.*</span><span class="sxs-lookup"><span data-stu-id="34579-136">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="34579-137">Содержимое seed выбирается человеком и представляет категорию содержимого.</span><span class="sxs-lookup"><span data-stu-id="34579-137">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="34579-138">Необходимо иметь не менее 50 положительных примеров и до 500.</span><span class="sxs-lookup"><span data-stu-id="34579-138">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="34579-139">Обучаемый классификатор обрабатывает до 500 последних созданных примеров (по отметке даты и времени, созданной файлом).</span><span class="sxs-lookup"><span data-stu-id="34579-139">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="34579-140">Чем больше примеров вы предоставляете, тем точнее прогнозы, которые будет делать классификатор.</span><span class="sxs-lookup"><span data-stu-id="34579-140">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="34579-141">Тестирование контента</span><span class="sxs-lookup"><span data-stu-id="34579-141">Testing content</span></span>

<span data-ttu-id="34579-142">После того как обучаемый классификатор обработает достаточно положительных примеров для построения модели прогнозирования, необходимо проверить прогнозы, которые он делает, чтобы проверить, может ли классификатор правильно различать элементы, которые соответствуют категории и элементы, которые не.</span><span class="sxs-lookup"><span data-stu-id="34579-142">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="34579-143">Для этого нужно выбрать другой, надеемся, больший набор содержимого, состоящего из примеров, которые должны попасть в категорию, и примеров, которые не будут.</span><span class="sxs-lookup"><span data-stu-id="34579-143">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="34579-144">Следует протестировать данные, отличались от данных начального начального уровня, которые вы предоставили.</span><span class="sxs-lookup"><span data-stu-id="34579-144">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="34579-145">После их обработки вы вручную пройдите результаты и убедитесь, что каждое прогнозирование верно, неверно или вы не уверены.</span><span class="sxs-lookup"><span data-stu-id="34579-145">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="34579-146">Обучаемый классификатор использует эту обратную связь для улучшения модели прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="34579-146">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="34579-147">Для наилучших результатов в тестовом примере установлено не менее 200 элементов с ряду положительных и отрицательных совпадений.</span><span class="sxs-lookup"><span data-stu-id="34579-147">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="34579-148">Создание обучаемого классификатора</span><span class="sxs-lookup"><span data-stu-id="34579-148">How to create a trainable classifier</span></span>

1. <span data-ttu-id="34579-149">Соберет от 50 до 500 элементов контента.</span><span class="sxs-lookup"><span data-stu-id="34579-149">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="34579-150">Это должны быть только образцы, которые строго представляют тип контента, который обучаемый классификатор должен положительно определить как в категории классификации.</span><span class="sxs-lookup"><span data-stu-id="34579-150">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="34579-151">Для поддерживаемых типов файлов см. расширения имен файлов для обхода по умолчанию и типы файлов для разлифментации в [SharePoint Server.](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)</span><span class="sxs-lookup"><span data-stu-id="34579-151">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="34579-152">Элементы образца для тестирования и их seed не должны быть зашифрованы и должны быть на английском языке.</span><span class="sxs-lookup"><span data-stu-id="34579-152">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="34579-153">Убедитесь, что элементы в наборе элементов **являются** примерами категории.</span><span class="sxs-lookup"><span data-stu-id="34579-153">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="34579-154">Обучаемый классификатор сначала создает свою модель на основе того, чем вы ее засеяли.</span><span class="sxs-lookup"><span data-stu-id="34579-154">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="34579-155">Классификатор предполагает, что все образцы данных являются положительными и не могут узнать, является ли образец слабым или отрицательным совпадением с категорией.</span><span class="sxs-lookup"><span data-stu-id="34579-155">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="34579-156">Поместите содержимое для закладки в папку SharePoint Online, выделенную для удержания *только содержимого.*</span><span class="sxs-lookup"><span data-stu-id="34579-156">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="34579-157">Заметьте сайт, библиотеку и URL-адрес папки.</span><span class="sxs-lookup"><span data-stu-id="34579-157">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="34579-158">Если вы создаете новый сайт и папку для данных о заметиве, то перед созданием обучаемого классификатора, который будет использовать эти данные, необходимо проиндексировать это расположение по крайней мере в течение часа.</span><span class="sxs-lookup"><span data-stu-id="34579-158">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="34579-159">Во sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or Microsoft **365 security center** Data  >  **classification**.</span><span class="sxs-lookup"><span data-stu-id="34579-159">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="34579-160">Выберите **вкладку "Обучаемые классификаторы".**</span><span class="sxs-lookup"><span data-stu-id="34579-160">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="34579-161">Choose **Create trainable classifier**.</span><span class="sxs-lookup"><span data-stu-id="34579-161">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="34579-162">Заполните соответствующие значения для категорий элементов и полей, которые должен определить обучаемый `Name` `Description` классификатор.</span><span class="sxs-lookup"><span data-stu-id="34579-162">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="34579-163">Выберите сайт, библиотеку и URL-адрес папки SharePoint Online для сайта контента для закладки из шага 2.</span><span class="sxs-lookup"><span data-stu-id="34579-163">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="34579-164">Выберите `Add` .</span><span class="sxs-lookup"><span data-stu-id="34579-164">Choose `Add`.</span></span>

8. <span data-ttu-id="34579-165">Просмотрите параметры и выберите `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="34579-165">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="34579-166">В течение 24 часов обучаемый классификатор обрабатывает данные о качестве и создает модель прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="34579-166">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="34579-167">Состояние классификатора находится `In progress` во время обработки данных о заметиве.</span><span class="sxs-lookup"><span data-stu-id="34579-167">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="34579-168">Когда классификатор завершит обработку данных о замечении, состояние изменится на `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="34579-168">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="34579-169">Теперь можно просмотреть страницу сведений, выбрав классификатор.</span><span class="sxs-lookup"><span data-stu-id="34579-169">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="34579-170">![обучаемый классификатор, готовый к тестированию](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="34579-170">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="34579-171">Соберет не менее 200 тестовых элементов контента (10 000 максимально) для наилучших результатов.</span><span class="sxs-lookup"><span data-stu-id="34579-171">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="34579-172">Это должен быть набор элементов, которые являются положительными, отрицательными и некоторыми, которые немного менее очевидны по своей природе.</span><span class="sxs-lookup"><span data-stu-id="34579-172">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="34579-173">Для поддерживаемых типов файлов см. расширения имен файлов для обхода по умолчанию и типы файлов для разлифментации в [SharePoint Server.](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)</span><span class="sxs-lookup"><span data-stu-id="34579-173">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="34579-174">Образцы элементов не должны быть зашифрованы и должны быть на английском языке.</span><span class="sxs-lookup"><span data-stu-id="34579-174">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="34579-175">Поместите тестовое содержимое в папку SharePoint Online, выделенную только для удержания *тестового содержимого.*</span><span class="sxs-lookup"><span data-stu-id="34579-175">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="34579-176">Заметьте URL-адрес сайта, библиотеки и папки SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="34579-176">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="34579-177">Если вы создаете новый сайт и папку для тестовых данных, перед созданием обучаемого классификатора, который будет использовать эти данные, проиндексируете это расположение по крайней мере в течение часа.</span><span class="sxs-lookup"><span data-stu-id="34579-177">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="34579-178">Выберите `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="34579-178">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="34579-179">Выберите сайт, библиотеку и URL-адрес папки SharePoint Online для тестового сайта контента на шаге 12.</span><span class="sxs-lookup"><span data-stu-id="34579-179">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="34579-180">Выберите `Add` .</span><span class="sxs-lookup"><span data-stu-id="34579-180">Choose `Add`.</span></span>

15. <span data-ttu-id="34579-181">Завершите работу мастера, выбрав `Done` .</span><span class="sxs-lookup"><span data-stu-id="34579-181">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="34579-182">Обработка тестовых файлов обучаемым классификатором займет до часа.</span><span class="sxs-lookup"><span data-stu-id="34579-182">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="34579-183">Когда обучаемый классификатор будет обрабатывать тестовые файлы, состояние на странице сведений изменится на `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="34579-183">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="34579-184">Если вам нужно увеличить размер тестового примера, выберите и разрешим обучаемой `Add items to test` классификатору обрабатывать дополнительные элементы.</span><span class="sxs-lookup"><span data-stu-id="34579-184">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="34579-185">![готовы к просмотру снимка экрана](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="34579-185">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="34579-186">Выберите `Tested items to review` вкладку для просмотра элементов.</span><span class="sxs-lookup"><span data-stu-id="34579-186">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="34579-187">Microsoft 365 будет одновременно представлять 30 элементов.</span><span class="sxs-lookup"><span data-stu-id="34579-187">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="34579-188">Просмотрите их и в поле `We predict this item is "Relevant". Do you agree?` выберите либо `Yes` либо `No` `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="34579-188">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="34579-189">Точность модели автоматически обновляется после каждого 30 элементов.</span><span class="sxs-lookup"><span data-stu-id="34579-189">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="34579-190">![поле "Просмотр элементов"](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="34579-190">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="34579-191">Просмотрите *не менее* 200 элементов.</span><span class="sxs-lookup"><span data-stu-id="34579-191">Review *at least* 200 items.</span></span> <span data-ttu-id="34579-192">После стабилизации оценки точности параметр **публикации** станет доступным и будет говорить состояние классификатора. `Ready to use`</span><span class="sxs-lookup"><span data-stu-id="34579-192">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="34579-193">![точность и готовность к публикации](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="34579-193">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="34579-194">Опубликуем классификатор.</span><span class="sxs-lookup"><span data-stu-id="34579-194">Publish the classifier.</span></span>

21. <span data-ttu-id="34579-195">После публикации классификатор будет доступен в качестве условия в автоматическом [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) применении меток [конфиденциальности Office,](apply-sensitivity-label-automatically.md)политика автоматического применения меток хранения на основе условия и соответствия [коммуникации.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="34579-195">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
