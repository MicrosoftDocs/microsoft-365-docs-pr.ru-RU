---
title: Начало работы с обучаемыми классификаторами (предварительная версия)
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
description: Классификатор Microsoft 365 — это инструмент, который можно обучить для распознавания различных типов контента, предоставляя им примеры для поиска. В этой статье описывается создание и обучение настраиваемого классификатора и его реобучение для повышения точности.
ms.openlocfilehash: f0d3659c1ee03fe69a5513f24d15b295400a24dc
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906350"
---
# <a name="get-started-with-trainable-classifiers-preview"></a><span data-ttu-id="80ea4-104">Начало работы с обучаемыми классификаторами (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="80ea4-104">Get started with trainable classifiers (preview)</span></span>

<span data-ttu-id="80ea4-105">Классификатор Microsoft 365, предназначенный для обучения, — это средство, которое можно обучить для распознавания различных типов контента, предоставляя ИТ-примерам возможность взглянуть на.</span><span class="sxs-lookup"><span data-stu-id="80ea4-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="80ea4-106">После обучения вы можете использовать его для определения элемента для применения меток конфиденциальности Office, политик соответствия требованиям и политик меток хранения.</span><span class="sxs-lookup"><span data-stu-id="80ea4-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="80ea4-107">Сначала Создание настраиваемого классификатора, который будет подобран для человеческого восприятия, и он будет однозначно сопоставлен категории.</span><span class="sxs-lookup"><span data-stu-id="80ea4-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="80ea4-108">Затем, после того, как она будет обработана, можно протестировать возможность прогнозирования, предоставляя им смесь положительных и отрицательных образцов.</span><span class="sxs-lookup"><span data-stu-id="80ea4-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="80ea4-109">В этой статье показано, как создать и обучить настраиваемый классификатор и как увеличить производительность настраиваемых классификаторов и предварительно обученных классификаторов за время их проведения.</span><span class="sxs-lookup"><span data-stu-id="80ea4-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="80ea4-110">Чтобы узнать больше о различных типах классификаторов, ознакомьтесь со статьей [сведения о классификаторах (Предварительная версия)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="80ea4-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80ea4-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="80ea4-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="80ea4-112">Требования к лицензированию</span><span class="sxs-lookup"><span data-stu-id="80ea4-112">Licensing requirements</span></span>

<span data-ttu-id="80ea4-113">Классификаторы — это функция соответствия корпорации Майкрософт 365 в</span><span class="sxs-lookup"><span data-stu-id="80ea4-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="80ea4-114">Для их использования необходима одна из этих подписок.</span><span class="sxs-lookup"><span data-stu-id="80ea4-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="80ea4-115">Разрешения</span><span class="sxs-lookup"><span data-stu-id="80ea4-115">Permissions</span></span>

<span data-ttu-id="80ea4-116">Чтобы получить доступ к классификаторам в пользовательском интерфейсе:</span><span class="sxs-lookup"><span data-stu-id="80ea4-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="80ea4-117">Глобальному администратору необходимо согласиться на создание настраиваемых классификаторов для клиента.</span><span class="sxs-lookup"><span data-stu-id="80ea4-117">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="80ea4-118">Для обучения классификатора требуется администратор соответствия требованиям или роль расследования данных.</span><span class="sxs-lookup"><span data-stu-id="80ea4-118">Compliance Administrator or Data Investigation role is required to train a classifier.</span></span>

<span data-ttu-id="80ea4-119">Учетные записи с этими разрешениями потребуются для использования классификаторов в следующих сценариях:</span><span class="sxs-lookup"><span data-stu-id="80ea4-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="80ea4-120">Сценарий политики меток хранения: Управление записями и роли управления хранением</span><span class="sxs-lookup"><span data-stu-id="80ea4-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="80ea4-121">Сценарий политики меток конфиденциальности: администратор безопасности, администратор соответствия требованиям, администратор данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="80ea4-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="80ea4-122">Политика соответствия требованиям к общению: администратору управления рисками для участников программы, администратору Супервизорной проверки</span><span class="sxs-lookup"><span data-stu-id="80ea4-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="80ea4-123">По умолчанию только пользователь, создающий настраиваемый классификатор, может обучать и просматривать прогнозы, выполненные этим классификатором.</span><span class="sxs-lookup"><span data-stu-id="80ea4-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span> <span data-ttu-id="80ea4-124">Если вы хотите, чтобы другие пользователи могли обучать и просматривать прогнозы классификаторов, ознакомьтесь со статьей [предоставление другим пользователям прав на обучение и изучение](#give-others-train-and-review-rights).</span><span class="sxs-lookup"><span data-stu-id="80ea4-124">If you want others to be able to train and review classifier predictions, see [Give others train and review rights](#give-others-train-and-review-rights).</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="80ea4-125">Подготовка к созданию настраиваемого классификатора для обучения</span><span class="sxs-lookup"><span data-stu-id="80ea4-125">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="80ea4-126">Полезно знать, что нужно для создания настраиваемого классификатора для обучения, прежде чем приступать к работе.</span><span class="sxs-lookup"><span data-stu-id="80ea4-126">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="80ea4-127">Временная шкала</span><span class="sxs-lookup"><span data-stu-id="80ea4-127">Timeline</span></span>

<span data-ttu-id="80ea4-128">Эта временная шкала отражает пример развертывания выученных классификаторов.</span><span class="sxs-lookup"><span data-stu-id="80ea4-128">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![обучение — классификатор — временная шкала](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="80ea4-130">В первый раз для обучения классификаторам необходим явный запрос.</span><span class="sxs-lookup"><span data-stu-id="80ea4-130">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="80ea4-131">Для выполнения базовой оценки контента организации в Microsoft 365 требуется 12 дней.</span><span class="sxs-lookup"><span data-stu-id="80ea4-131">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="80ea4-132">Обратитесь к глобальному администратору, чтобы отказаться от участия в этой процедуре.</span><span class="sxs-lookup"><span data-stu-id="80ea4-132">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="80ea4-133">Общий рабочий процесс</span><span class="sxs-lookup"><span data-stu-id="80ea4-133">Overall workflow</span></span>

<span data-ttu-id="80ea4-134">Чтобы узнать больше об общем рабочем процессе по созданию настраиваемых классификаторов, ознакомьтесь со статьей [поток обработки для создания классификаторов](classifier-learn-about.md#process-flow-for-creating-custom-classifiers), которые можно научить клиентов.</span><span class="sxs-lookup"><span data-stu-id="80ea4-134">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="80ea4-135">Начальное содержимое</span><span class="sxs-lookup"><span data-stu-id="80ea4-135">Seed content</span></span>

<span data-ttu-id="80ea4-136">Если вы хотите, чтобы предназначенный для обучения классификатор был независимым и точно определить элемент в определенной категории контента, сначала необходимо предоставить ему множество образцов типа контента, находящиеся в категории.</span><span class="sxs-lookup"><span data-stu-id="80ea4-136">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="80ea4-137">Такое подача образцов классификатору, предназначенному для обучения, называется *Заполнение*.</span><span class="sxs-lookup"><span data-stu-id="80ea4-137">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="80ea4-138">Начальное содержимое выбирается человеком и определяется для представления категории контента.</span><span class="sxs-lookup"><span data-stu-id="80ea4-138">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="80ea4-139">Необходимо иметь по крайней мере 50 положительные примеры и до 500.</span><span class="sxs-lookup"><span data-stu-id="80ea4-139">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="80ea4-140">Классификатор, который будет обучаться, будет обрабатываться в 500 самых последних созданных примеров (по дате создания файла или метки времени).</span><span class="sxs-lookup"><span data-stu-id="80ea4-140">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="80ea4-141">Чем больше предоставленных примеров, тем точнее прогнозы, которые будет выполнять классификатор.</span><span class="sxs-lookup"><span data-stu-id="80ea4-141">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="80ea4-142">Тестирование содержимого</span><span class="sxs-lookup"><span data-stu-id="80ea4-142">Testing content</span></span>

<span data-ttu-id="80ea4-143">После того как классификатор обработал достаточное количество положительных образцов для создания прогнозной модели, необходимо протестировать прогноз, чтобы определить, может ли классификатор правильно различать элементы, которые совпадают со категорией и элементами.</span><span class="sxs-lookup"><span data-stu-id="80ea4-143">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="80ea4-144">Это можно сделать, выбрав другой, надеюсь, более крупный набор собраний, который включает в себя примеры, которые должны относиться к категории и примерам.</span><span class="sxs-lookup"><span data-stu-id="80ea4-144">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="80ea4-145">Необходимо протестировать данные, отличные от исходных данных, которые вы предоставили.</span><span class="sxs-lookup"><span data-stu-id="80ea4-145">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="80ea4-146">После обработки этих результатов вручную пройдите по результатам и убедитесь, что каждый прогноз является правильным, неверным или нет.</span><span class="sxs-lookup"><span data-stu-id="80ea4-146">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="80ea4-147">Классификатор для обучения использует этот отзыв для усовершенствования модели прогнозирования.</span><span class="sxs-lookup"><span data-stu-id="80ea4-147">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="80ea4-148">Для достижения лучших результатов необходимо иметь по крайней мере 200 элементов в примере тестового набора с четным распределением положительных и отрицательных совпадений.</span><span class="sxs-lookup"><span data-stu-id="80ea4-148">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="80ea4-149">Создание классификатора для обучения</span><span class="sxs-lookup"><span data-stu-id="80ea4-149">How to create a trainable classifier</span></span>

1. <span data-ttu-id="80ea4-150">Сбор данных между начальными элементами содержимого 50-500.</span><span class="sxs-lookup"><span data-stu-id="80ea4-150">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="80ea4-151">Они должны быть только примерами, которые строго представляют тип контента, который классификатор должен указать в категории классификации.</span><span class="sxs-lookup"><span data-stu-id="80ea4-151">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="80ea4-152">В SharePoint Server для поддерживаемых типов файлов вы найдете файлы с [расширениями для обхода по умолчанию и проанализированные типы файлов](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) .</span><span class="sxs-lookup"><span data-stu-id="80ea4-152">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="80ea4-153">Начальные и проверочные элементы примеров не должны быть зашифрованы и должны быть на английском языке.</span><span class="sxs-lookup"><span data-stu-id="80ea4-153">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="80ea4-154">Убедитесь, что элементы в наборе начального значения являются **надежными** примерами категории.</span><span class="sxs-lookup"><span data-stu-id="80ea4-154">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="80ea4-155">Классификатор, для которого выполняется обучение, изначально создает свою модель в зависимости от того, что вы инициализируем.</span><span class="sxs-lookup"><span data-stu-id="80ea4-155">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="80ea4-156">Классификатор предполагает, что все примеры начального значения являются надежными и не позволяют узнать, является ли пример слабым или отрицательным для категории.</span><span class="sxs-lookup"><span data-stu-id="80ea4-156">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="80ea4-157">Поместите начальное содержимое в папку SharePoint Online, предназначенную для хранения *только начального контента*.</span><span class="sxs-lookup"><span data-stu-id="80ea4-157">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="80ea4-158">Запишите URL-адрес сайта, библиотеки и папки.</span><span class="sxs-lookup"><span data-stu-id="80ea4-158">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="80ea4-159">Если вы создаете новый сайт и папку для своих начальных данных, разрешите индексирование этого расположения по крайней мере в течение часа, прежде чем создавать предназначенный для обучения классификатор, который будет использовать эти начальные данные.</span><span class="sxs-lookup"><span data-stu-id="80ea4-159">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="80ea4-160">Войдите в центр соответствия требованиям Microsoft 365, используя доступ к роли администратора безопасности или администратора безопасности, и откройте **центр соответствия требованиям Microsoft 365** или **Майкрософт 365 Data Center Security Center**  >  **Data classification**.</span><span class="sxs-lookup"><span data-stu-id="80ea4-160">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="80ea4-161">Выберите вкладку **классификаторы для обучения** .</span><span class="sxs-lookup"><span data-stu-id="80ea4-161">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="80ea4-162">Выберите **создать классификатор для обучения**.</span><span class="sxs-lookup"><span data-stu-id="80ea4-162">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="80ea4-163">Заполните нужные значения `Name` `Description` полей и категорий элементов, которые должны быть идентифицированы этим классификатором для обучения.</span><span class="sxs-lookup"><span data-stu-id="80ea4-163">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="80ea4-164">Выберите сайт SharePoint Online, библиотеку и URL-адрес папки начального контента на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="80ea4-164">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="80ea4-165">Выберите `Add` .</span><span class="sxs-lookup"><span data-stu-id="80ea4-165">Choose `Add`.</span></span>

8. <span data-ttu-id="80ea4-166">Проверьте параметры и нажмите кнопку `Create trainable classifier` .</span><span class="sxs-lookup"><span data-stu-id="80ea4-166">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="80ea4-167">В течение 24 часов классификатор с обучением будет обрабатывать начальные данные и создавать прогнозную модель.</span><span class="sxs-lookup"><span data-stu-id="80ea4-167">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="80ea4-168">Состояние классификатора это `In progress` время обработки начального значения.</span><span class="sxs-lookup"><span data-stu-id="80ea4-168">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="80ea4-169">Когда классификатор закончит обработку начальных данных, состояние изменится на `Need test items` .</span><span class="sxs-lookup"><span data-stu-id="80ea4-169">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="80ea4-170">Теперь вы можете просмотреть страницу сведений, выбрав классификатор.</span><span class="sxs-lookup"><span data-stu-id="80ea4-170">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="80ea4-171">![подготовленный классификатор для тестирования](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="80ea4-171">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="80ea4-172">Соберите по крайней мере 200 тестовых элементов контента (максимум 10 000), чтобы получить наилучшие результаты.</span><span class="sxs-lookup"><span data-stu-id="80ea4-172">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="80ea4-173">Они должны быть смесью элементов, которые являются надежными положительными значениями, а некоторые — небольшими очевидными причинами.</span><span class="sxs-lookup"><span data-stu-id="80ea4-173">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="80ea4-174">В SharePoint Server для поддерживаемых типов файлов вы найдете файлы с [расширениями для обхода по умолчанию и проанализированные типы файлов](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) .</span><span class="sxs-lookup"><span data-stu-id="80ea4-174">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="80ea4-175">Элементы примера не должны быть зашифрованы и должны быть на английском языке.</span><span class="sxs-lookup"><span data-stu-id="80ea4-175">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="80ea4-176">Поместите тестовый контент в папку SharePoint Online, предназначенную для хранения *только тестового контента*.</span><span class="sxs-lookup"><span data-stu-id="80ea4-176">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="80ea4-177">Запишите URL-адрес сайта, библиотеки и папки SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="80ea4-177">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="80ea4-178">Если вы создаете новый сайт и папку для тестовых данных, разрешите индексирование этого расположения по крайней мере в течение часа перед созданием классификатора, который будет использовать эти начальные данные.</span><span class="sxs-lookup"><span data-stu-id="80ea4-178">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="80ea4-179">Выберите `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="80ea4-179">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="80ea4-180">На шаге 12 выберите сайт SharePoint Online, библиотеку и URL-адрес папки тестового контента.</span><span class="sxs-lookup"><span data-stu-id="80ea4-180">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="80ea4-181">Выберите `Add` .</span><span class="sxs-lookup"><span data-stu-id="80ea4-181">Choose `Add`.</span></span>

15. <span data-ttu-id="80ea4-182">Завершите работу мастера, нажав кнопку `Done` .</span><span class="sxs-lookup"><span data-stu-id="80ea4-182">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="80ea4-183">Для обработки тестовых файлов классификатор должен пройти до часа.</span><span class="sxs-lookup"><span data-stu-id="80ea4-183">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="80ea4-184">Когда предназначенный для обучения классификатор обрабатывает тестовые файлы, состояние на странице сведений изменится на `Ready to review` .</span><span class="sxs-lookup"><span data-stu-id="80ea4-184">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="80ea4-185">Если требуется увеличить размер образца теста, выберите `Add items to test` и разрешите классификатору обрабатывать дополнительные элементы.</span><span class="sxs-lookup"><span data-stu-id="80ea4-185">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="80ea4-186">![готовность к просмотру снимка экрана](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="80ea4-186">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="80ea4-187">Нажмите `Tested items to review` клавишу TAB для просмотра элементов.</span><span class="sxs-lookup"><span data-stu-id="80ea4-187">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="80ea4-188">В Microsoft 365 в каждый момент времени будет находиться 30 элементов.</span><span class="sxs-lookup"><span data-stu-id="80ea4-188">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="80ea4-189">Просмотрите их и в `We predict this item is "Relevant". Do you agree?` поле выберите либо `Yes` или `No` `Not sure, skip to next item` .</span><span class="sxs-lookup"><span data-stu-id="80ea4-189">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="80ea4-190">Точность модели автоматически обновляется после каждых 30 элементов.</span><span class="sxs-lookup"><span data-stu-id="80ea4-190">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="80ea4-191">![поле "Просмотр элементов"](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="80ea4-191">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="80ea4-192">Просмотрите *по крайней мере* 200 элементов.</span><span class="sxs-lookup"><span data-stu-id="80ea4-192">Review *at least* 200 items.</span></span> <span data-ttu-id="80ea4-193">После того как показатель точности будет стабилизироваться, параметр **Publish** станет доступным, а состояние классификатора будет говорить `Ready to use` .</span><span class="sxs-lookup"><span data-stu-id="80ea4-193">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="80ea4-194">![Оценка точности и готовность к публикации](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="80ea4-194">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="80ea4-195">Опубликуйте классификатор.</span><span class="sxs-lookup"><span data-stu-id="80ea4-195">Publish the classifier.</span></span>

21. <span data-ttu-id="80ea4-196">После публикации классификатор будет доступен в качестве условия [автоматической метки в Office с метками чувствительности](apply-sensitivity-label-automatically.md), [автоматически применять политику меток хранения на основе условия](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) и в [соответствии с соответствием связью](communication-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="80ea4-196">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>

## <a name="give-others-train-and-review-rights"></a><span data-ttu-id="80ea4-197">Предоставление другим пользователям прав на обучение и пересмотр</span><span class="sxs-lookup"><span data-stu-id="80ea4-197">Give others train and review rights</span></span>

<span data-ttu-id="80ea4-198">Используйте эту процедуру, чтобы предоставить другим пользователям разрешения на обучение, просмотр и настройка настраиваемого классификатора для обучения.</span><span class="sxs-lookup"><span data-stu-id="80ea4-198">Use this procedure to give others permissions to train, review and tune your custom trainable classifier.</span></span>  
 
1. <span data-ttu-id="80ea4-199">Создатель классификатора глобальному администратору или администратору обнаружения электронных данных подключается к центру соответствия требованиям с помощью PowerShell с помощью процедур, описанных в разделе [Connect to Security to Security & Center соответствия требованиям PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="80ea4-199">As the creator of the classifier, a global admin or eDiscovery admin connect to the Compliance center using PowerShell using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps&preserve-view=true).</span></span>

2. <span data-ttu-id="80ea4-200">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="80ea4-200">Run this command:</span></span>

   ```powershell
   Add-ComplianceCaseMember -Case "<classifier name>" -Member "<user or role group>"
   ```
   
   <span data-ttu-id="80ea4-201">Примеры:</span><span class="sxs-lookup"><span data-stu-id="80ea4-201">For example:</span></span>
   
   `Add-ComplianceCaseMember -Case "Financial Contract Classifier" -Member johnevans@contoso.com`

   <span data-ttu-id="80ea4-202">Эту команду можно выполнить несколько раз, чтобы добавить нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="80ea4-202">You can run this command multiple times to add multiple users.</span></span> <span data-ttu-id="80ea4-203">Обратите внимание, что вы можете добавлять только группы ролей Exchange Online Protection (EOP), а не группы ролей Azure.</span><span class="sxs-lookup"><span data-stu-id="80ea4-203">Note that you can only add Exchange Online Protection (EOP) Role Groups and not Azure Role Groups.</span></span>
