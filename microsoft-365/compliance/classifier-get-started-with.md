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
description: Классификатор Microsoft 365 — это средство, которое можно обучить распознавать различные типы контента, предоставляя ему образцы для анализа. В этой статье показано, как создать и обучить настраиваемый классификатор и как их переобучить для повышения точности.
ms.openlocfilehash: 90e47ec94528bbadeb98dc9eb590929e25ae6ff1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918183"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="08e93-104">Начало работы с обучаемыми классификаторами</span><span class="sxs-lookup"><span data-stu-id="08e93-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="08e93-105">Классификатор Microsoft 365 — это средство, которое можно обучить распознавать различные типы контента, предоставляя ему примеры для анализа.</span><span class="sxs-lookup"><span data-stu-id="08e93-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="08e93-106">После обучения вы можете использовать его для определения элемента для применения меток конфиденциальности Office, политик соответствия требованиям к коммуникациям и политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="08e93-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="08e93-107">Создание настраиваемого классификатора, который можно обучить, сначала включает в себя предоставление ему образцов, которые были выбрали люди и положительно совпадали с этой категорией.</span><span class="sxs-lookup"><span data-stu-id="08e93-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="08e93-108">Затем, после обработки этих данных, вы тестируете способность классификаторов предсказывать, предоставляя ему сочетание положительных и отрицательных образцов.</span><span class="sxs-lookup"><span data-stu-id="08e93-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="08e93-109">В этой статье показано, как создать и обучить настраиваемый классификатор и повысить производительность настраиваемых классификаторов и предварительно подготовленных классификаторов за время их жизни путем переподготовки.</span><span class="sxs-lookup"><span data-stu-id="08e93-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="08e93-110">Дополнительные новости о различных типах классификаторов см. в дополнительных подробной информации о [классификаторах,](classifier-learn-about.md)которые можно обучить.</span><span class="sxs-lookup"><span data-stu-id="08e93-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="08e93-111">Просмотрите это видео для краткой сводки создания классификатора, который можно обучить.</span><span class="sxs-lookup"><span data-stu-id="08e93-111">Watch this video for a quick summary of creating a trainable classifier.</span></span> <span data-ttu-id="08e93-112">Вам по-прежнему необходимо прочитать эту полную статью, чтобы получить подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="08e93-112">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a><span data-ttu-id="08e93-113">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="08e93-113">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="08e93-114">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="08e93-114">Licensing requirements</span></span>

<span data-ttu-id="08e93-115">Классификаторы — это функция соответствия требованиям Microsoft 365 E5 или E5.</span><span class="sxs-lookup"><span data-stu-id="08e93-115">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="08e93-116">Вы должны иметь одну из этих подписок, чтобы использовать их.</span><span class="sxs-lookup"><span data-stu-id="08e93-116">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="08e93-117">Разрешения</span><span class="sxs-lookup"><span data-stu-id="08e93-117">Permissions</span></span>

<span data-ttu-id="08e93-118">Чтобы получить доступ к классификаторам в пользовательском интерфейсе:</span><span class="sxs-lookup"><span data-stu-id="08e93-118">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="08e93-119">Глобальный администратор должен выбрать для клиента создание настраиваемые классификаторы.</span><span class="sxs-lookup"><span data-stu-id="08e93-119">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="08e93-120">Для подготовки классификатора требуется роль администратора соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="08e93-120">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="08e93-121">Для использования классификаторов в этих сценариях потребуется учетная запись с этими разрешениями:</span><span class="sxs-lookup"><span data-stu-id="08e93-121">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="08e93-122">Сценарий политики меток хранения: роли управления записями и управления хранением</span><span class="sxs-lookup"><span data-stu-id="08e93-122">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="08e93-123">Сценарий политики меток конфиденциальности: администратор безопасности, администратор соответствия требованиям, администратор данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="08e93-123">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="08e93-124">Сценарий политики соответствия требованиям к коммуникации: администратор управления рисками изнутри, администратор надзорных обзоров</span><span class="sxs-lookup"><span data-stu-id="08e93-124">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="08e93-125">По умолчанию только пользователь, создавший настраиваемый классификатор, может обучить и просмотреть прогнозы, сделанные этим классификатором.</span><span class="sxs-lookup"><span data-stu-id="08e93-125">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="08e93-126">Подготовка настраиваемого классификатора для обучения</span><span class="sxs-lookup"><span data-stu-id="08e93-126">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="08e93-127">Перед погружением в нее полезно понять, что необходимо сделать для создания настраиваемого классификатора для обучения.</span><span class="sxs-lookup"><span data-stu-id="08e93-127">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="08e93-128">Временная шкала</span><span class="sxs-lookup"><span data-stu-id="08e93-128">Timeline</span></span>

<span data-ttu-id="08e93-129">Эта временная шкала отражает пример развертывания обучаемых классификаторов.</span><span class="sxs-lookup"><span data-stu-id="08e93-129">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="08e93-131">Для обучаемых классификаторов требуется первый раз.</span><span class="sxs-lookup"><span data-stu-id="08e93-131">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="08e93-132">Для выполнения базовой оценки контента организаций для Microsoft 365 требуется двенадцать дней.</span><span class="sxs-lookup"><span data-stu-id="08e93-132">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="08e93-133">Обратитесь к глобальному администратору, чтобы приработать процедуру выбора.</span><span class="sxs-lookup"><span data-stu-id="08e93-133">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="08e93-134">Общий рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="08e93-134">Overall workflow</span></span>

<span data-ttu-id="08e93-135">Дополнительные данные об общем процессе создания настраиваемых классификаторов, которые можно обучить, см. в дополнительных данных о процессе создания классификаторов, которые можно обучить [клиента.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)</span><span class="sxs-lookup"><span data-stu-id="08e93-135">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="08e93-136">Содержимое seed</span><span class="sxs-lookup"><span data-stu-id="08e93-136">Seed content</span></span>

<span data-ttu-id="08e93-137">Если вы хотите, чтобы классификатор, с помощью подготовки, мог самостоятельно и точно определить элемент как определенный классификатор, сначала необходимо представить ему множество примеров типа контента, который находится в этой категории.</span><span class="sxs-lookup"><span data-stu-id="08e93-137">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="08e93-138">Это кормление образцов в обучаемый классификатор называется *посевом.*</span><span class="sxs-lookup"><span data-stu-id="08e93-138">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="08e93-139">Содержимое семени выбирается человеком и, по мнению экспертов, представляет категорию контента.</span><span class="sxs-lookup"><span data-stu-id="08e93-139">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="08e93-140">Необходимо иметь не менее 50 положительных примеров и до 500.</span><span class="sxs-lookup"><span data-stu-id="08e93-140">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="08e93-141">Классификатор, который можно обучить, будет обрабатывать до 500 последних созданных образцов (по созданному файлу дата/время).</span><span class="sxs-lookup"><span data-stu-id="08e93-141">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="08e93-142">Чем больше примеров вы предоставите, тем точнее будут прогнозы, которые будет делать классификатор.</span><span class="sxs-lookup"><span data-stu-id="08e93-142">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="08e93-143">Тестирование контента</span><span class="sxs-lookup"><span data-stu-id="08e93-143">Testing content</span></span>

<span data-ttu-id="08e93-144">После обработки классификатором для обучения достаточно положительных образцов для создания модели прогнозирования необходимо проверить прогнозы, которые он делает, чтобы проверить, может ли классификатор правильно различать элементы, которые соответствуют категории, и элементы, которые этого не делают.</span><span class="sxs-lookup"><span data-stu-id="08e93-144">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="08e93-145">Вы делаете это, выбрав другой, мы надеемся, больший набор выбранных людьми контента, который состоит из образцов, которые должны попасть в категорию и образцы, которые не будут.</span><span class="sxs-lookup"><span data-stu-id="08e93-145">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="08e93-146">Вы должны протестировать с помощью различных данных, чем исходные исходные данные семян, которые вы впервые предоставили.</span><span class="sxs-lookup"><span data-stu-id="08e93-146">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="08e93-147">После обработки этих результатов вы вручную проверяете, является ли каждый прогноз правильным, неправильным или вы не уверены.</span><span class="sxs-lookup"><span data-stu-id="08e93-147">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="08e93-148">Классификатор, который можно обучить, использует эту обратную связь для улучшения модели прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="08e93-148">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="08e93-149">Для наилучших результатов в тестовом наборе имеется не менее 200 элементов с ряду положительных и отрицательных совпадений.</span><span class="sxs-lookup"><span data-stu-id="08e93-149">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="08e93-150">Создание классификатора, который можно обучить</span><span class="sxs-lookup"><span data-stu-id="08e93-150">How to create a trainable classifier</span></span>

1. <span data-ttu-id="08e93-151">Сбор между 50-500 элементами контента для семян.</span><span class="sxs-lookup"><span data-stu-id="08e93-151">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="08e93-152">Это должны быть только образцы, которые сильно представляют тип контента, который необходимо классификатору, который можно использовать для положительного определения в категории классификации.</span><span class="sxs-lookup"><span data-stu-id="08e93-152">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="08e93-153">См., расширения имен файлов по умолчанию и раздельные типы файлов [в SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) для поддерживаемых типов файлов.</span><span class="sxs-lookup"><span data-stu-id="08e93-153">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="08e93-154">Элементы семенного и тестового образцов не должны быть зашифрованы и должны быть на английском языке.</span><span class="sxs-lookup"><span data-stu-id="08e93-154">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="08e93-155">Убедитесь, что элементы в наборе семян **являются** сильными примерами категории.</span><span class="sxs-lookup"><span data-stu-id="08e93-155">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="08e93-156">Классификатор, который можно обучить, сначала создает свою модель на основе того, с чем вы ее сеяли.</span><span class="sxs-lookup"><span data-stu-id="08e93-156">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="08e93-157">Классификатор предполагает, что все образцы семян являются сильными позитивами и не могут узнать, является ли образец слабым или отрицательным.</span><span class="sxs-lookup"><span data-stu-id="08e93-157">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="08e93-158">Поместите содержимое семени в папку SharePoint Online, посвященную только содержанию *семян.*</span><span class="sxs-lookup"><span data-stu-id="08e93-158">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="08e93-159">Обратите внимание на URL-адрес сайта, библиотеки и папки.</span><span class="sxs-lookup"><span data-stu-id="08e93-159">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="08e93-160">Если вы создаете новый сайт и папку для семенных данных, то перед созданием классификатора, который будет использовать эти данные, необходимо проиндексировать это расположение по крайней мере за час.</span><span class="sxs-lookup"><span data-stu-id="08e93-160">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="08e93-161">Во входе в Центр соответствия требованиям Microsoft 365 с доступом к роли администратора или администратора безопасности и откройте центр соответствия требованиям **Microsoft 365** или классификацию центра данных Центра безопасности **Microsoft 365.**  >  </span><span class="sxs-lookup"><span data-stu-id="08e93-161">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="08e93-162">Выберите **вкладку Классификаторы,** которые можно обучить.</span><span class="sxs-lookup"><span data-stu-id="08e93-162">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="08e93-163">Выберите **Создание классификатора, который можно обучить.**</span><span class="sxs-lookup"><span data-stu-id="08e93-163">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="08e93-164">Заполните соответствующие значения для и полей категории элементов, которые необходимо определить этому `Name` `Description` классификатору для обучения.</span><span class="sxs-lookup"><span data-stu-id="08e93-164">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="08e93-165">Выберите URL-адрес сайта, библиотеки и папки SharePoint Online для сайта контента для семян с шага 2.</span><span class="sxs-lookup"><span data-stu-id="08e93-165">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="08e93-166">Выберите `Add` .</span><span class="sxs-lookup"><span data-stu-id="08e93-166">Choose `Add`.</span></span>

8. <span data-ttu-id="08e93-167">Просмотрите параметры и выберите `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="08e93-167">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="08e93-168">В течение 24 часов обучаемый классификатор обработать данные семян и создать модель прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="08e93-168">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="08e93-169">Состояние классификатора — `In progress` это процесс обработки данных семян.</span><span class="sxs-lookup"><span data-stu-id="08e93-169">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="08e93-170">Когда классификатор завершает обработку данных семян, состояние меняется на `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="08e93-170">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="08e93-171">Теперь вы можете просмотреть страницу сведений, выбрав классификатор.</span><span class="sxs-lookup"><span data-stu-id="08e93-171">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="08e93-172">![классификатор, готовый к тестированию](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="08e93-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="08e93-173">Сбор по крайней мере 200 элементов тестового контента (10 000 макс) для наилучших результатов.</span><span class="sxs-lookup"><span data-stu-id="08e93-173">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="08e93-174">Это должно быть сочетание элементов, которые являются сильными позитивами, сильными негативами и некоторыми, которые немного менее очевидны по своей природе.</span><span class="sxs-lookup"><span data-stu-id="08e93-174">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="08e93-175">См., расширения имен файлов по умолчанию и раздельные типы файлов [в SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) для поддерживаемых типов файлов.</span><span class="sxs-lookup"><span data-stu-id="08e93-175">See, [Default crawled file name extensions and parsed file types in SharePoint Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="08e93-176">Образцы элементов не должны быть зашифрованы и должны быть на английском языке.</span><span class="sxs-lookup"><span data-stu-id="08e93-176">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="08e93-177">Поместите тестовый контент в папку SharePoint Online, предназначенную только для проведения *тестового контента.*</span><span class="sxs-lookup"><span data-stu-id="08e93-177">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="08e93-178">Обратите внимание на URL-адрес сайта, библиотеки и папки SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="08e93-178">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="08e93-179">Если вы создаете новый сайт и папку для тестовых данных, то перед созданием классификатора, который будет использовать эти семенные данные, необходимо проиндексировать это расположение по крайней мере за час.</span><span class="sxs-lookup"><span data-stu-id="08e93-179">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="08e93-180">Выберите `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="08e93-180">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="08e93-181">Выберите URL-адрес сайта, библиотеки и папки SharePoint Online для сайта тестового контента с шага 12.</span><span class="sxs-lookup"><span data-stu-id="08e93-181">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="08e93-182">Выберите `Add` .</span><span class="sxs-lookup"><span data-stu-id="08e93-182">Choose `Add`.</span></span>

15. <span data-ttu-id="08e93-183">Завершите мастер, выбрав `Done` .</span><span class="sxs-lookup"><span data-stu-id="08e93-183">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="08e93-184">Процесс обработки тестовых файлов для классификатора, который можно обучить, займет до часа.</span><span class="sxs-lookup"><span data-stu-id="08e93-184">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="08e93-185">Когда обучаемый классификатор будет обрабатывать тестовые файлы, состояние на странице сведений изменится на `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="08e93-185">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="08e93-186">Если необходимо увеличить размер тестового образца, выберите и разрешим классификатору обучить `Add items to test` дополнительные элементы.</span><span class="sxs-lookup"><span data-stu-id="08e93-186">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="08e93-187">![готовый к просмотру скриншота](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="08e93-187">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="08e93-188">Выберите `Tested items to review` вкладку для просмотра элементов.</span><span class="sxs-lookup"><span data-stu-id="08e93-188">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="08e93-189">Microsoft 365 представит одновременно 30 элементов.</span><span class="sxs-lookup"><span data-stu-id="08e93-189">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="08e93-190">Просмотрите их и в `We predict this item is "Relevant". Do you agree?` поле выберите либо или `Yes` `No` `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="08e93-190">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="08e93-191">Точность модели автоматически обновляется после каждого 30 элементов.</span><span class="sxs-lookup"><span data-stu-id="08e93-191">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="08e93-192">![поле элементов просмотра](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="08e93-192">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="08e93-193">Просмотрите *не менее* 200 элементов.</span><span class="sxs-lookup"><span data-stu-id="08e93-193">Review *at least* 200 items.</span></span> <span data-ttu-id="08e93-194">Как только оценка точности стабилизируется, будет доступен вариант **публикации** и будет говориться состояние классификатора `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="08e93-194">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="08e93-195">![оценка точности и готов к публикации](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="08e93-195">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="08e93-196">Опубликуй классификатор.</span><span class="sxs-lookup"><span data-stu-id="08e93-196">Publish the classifier.</span></span>

21. <span data-ttu-id="08e93-197">После публикации классификатор будет доступен в качестве условия автозаметки [Office](apply-sensitivity-label-automatically.md)с метами чувствительности, [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) политики автоматического применения меток хранения на основе условия и соответствия требованиям [связи.](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="08e93-197">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>