---
title: Настройка обнаружения привилегий между адвокатом и клиентом в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Используйте модель обнаружения привилегий между адвокатом и клиентом для обнаружения привилегированного контента на основе машинного обучения при просмотре контента в Advanced eDiscovery случае.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358045"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="d5002-103">Настройка обнаружения привилегий между адвокатом и клиентом в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d5002-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="d5002-104">Основным и дорогостоящим аспектом на этапе проверки любого процесса проверки электронных документов является проверка документов для привилегированного контента.</span><span class="sxs-lookup"><span data-stu-id="d5002-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="d5002-105">Advanced eDiscovery обеспечивает обнаружение привилегированного контента на основе машинного обучения, чтобы сделать этот процесс более эффективным.</span><span class="sxs-lookup"><span data-stu-id="d5002-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="d5002-106">Эта функция называется *обнаружением привилегий между адвокатом и клиентом.*</span><span class="sxs-lookup"><span data-stu-id="d5002-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="d5002-107">Как это работает?</span><span class="sxs-lookup"><span data-stu-id="d5002-107">How does it work?</span></span>

<span data-ttu-id="d5002-108">Когда будет включено обнаружение привилегий между адвокатом и клиентом, все документы в [](analyzing-data-in-review-set.md) наборе отзывов будут обрабатываться моделью обнаружения привилегий между адвокатом и клиентом при анализе данных в наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="d5002-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="d5002-109">Модель ищет две вещи:</span><span class="sxs-lookup"><span data-stu-id="d5002-109">The model looks for two things:</span></span>

- <span data-ttu-id="d5002-110">Привилегированное содержимое — модель использует машинное обучение для определения вероятности того, что документ содержит легальный по своему характеру контент.</span><span class="sxs-lookup"><span data-stu-id="d5002-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="d5002-111">Участники . В рамках настройки обнаружения привилегий между адвокатом и клиентом необходимо представить список адвокатов для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d5002-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="d5002-112">Затем модель сравнивает соавторов документа со списком юристов, чтобы определить, есть ли среди соавторов хотя бы один адвокат.</span><span class="sxs-lookup"><span data-stu-id="d5002-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="d5002-113">Модель создает следующие три свойства для каждого документа:</span><span class="sxs-lookup"><span data-stu-id="d5002-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="d5002-114">**AttorneyClientPrivilegeScore:** Вероятность того, что документ является юридическим по своему характеру; значения для оценки от **0** до **1**.</span><span class="sxs-lookup"><span data-stu-id="d5002-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="d5002-115">**HasAttorney:** Это свойство имеет свойство **true,** если один из участников документа указан в списке адвоката; в противном случае значение является **ложным**.</span><span class="sxs-lookup"><span data-stu-id="d5002-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="d5002-116">Значение также равно **false**, если ваша организация не определила список юристов.</span><span class="sxs-lookup"><span data-stu-id="d5002-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="d5002-117">**IsPrivilege:** Это свойство имеет значение **true,** если значение **для AttorneyClientPrivilegeScore** превышает пороговое значение или если в документе есть участник адвокатского процесса;  в противном случае значение заведомо **ложное.**</span><span class="sxs-lookup"><span data-stu-id="d5002-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="d5002-118">Эти свойства (и их соответствующие значения) добавляются в метаданные файлов документов в наборе отзывов, как показано на следующем скриншоте:</span><span class="sxs-lookup"><span data-stu-id="d5002-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![Свойства привилегий адвоката и клиента, показанные в метаданных файлов](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="d5002-120">Эти три свойства также можно искать в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="d5002-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="d5002-121">Дополнительные сведения см. в обзоре Запрос данных в [наборе обзоров.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="d5002-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="d5002-122">Настройка модели обнаружения привилегий между адвокатом и клиентом</span><span class="sxs-lookup"><span data-stu-id="d5002-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="d5002-123">Чтобы включить модель обнаружения привилегий между адвокатом и клиентом, организации необходимо включить ее и загрузить список адвокатов.</span><span class="sxs-lookup"><span data-stu-id="d5002-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="d5002-124">Шаг 1. Включив обнаружение привилегий между адвокатом и клиентом</span><span class="sxs-lookup"><span data-stu-id="d5002-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="d5002-125">Человек, который является администратором по обнаружению электронных данных в вашей организации (член подгруппы администратора по обнаружению электронных данных в группе ролей диспетчера электронных данных), должен сделать модель доступной в Advanced eDiscovery случаях.</span><span class="sxs-lookup"><span data-stu-id="d5002-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="d5002-126">В Центре & безопасности перейдите в **центр eDiscovery > Advanced eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="d5002-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="d5002-127">На **домашней Advanced eDiscovery** на Параметры  нажмите кнопку Настройка **параметров глобальной аналитики.**</span><span class="sxs-lookup"><span data-stu-id="d5002-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![Выберите "Настройка экспериментальных функций"](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="d5002-129">На **вкладке Параметры аналитики** выберите **параметр Управление привилегиями адвоката и клиента.**</span><span class="sxs-lookup"><span data-stu-id="d5002-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="d5002-130">На странице **Адвокатская тайна** включите эту функцию, а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d5002-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="d5002-131">Шаг 2. Upload список адвокатов (необязательно)</span><span class="sxs-lookup"><span data-stu-id="d5002-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="d5002-132">Чтобы в полной мере использовать модель обнаружения привилегий между адвокатом и клиентом и использовать результаты ранее описанного обнаружения has **attorney** или **Potentially Privileged,** рекомендуем загрузить список адресов электронной почты для юристов и юристов, которые работают в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d5002-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="d5002-133">Чтобы загрузить список адвокатов для использования моделью обнаружения привилегий между адвокатом и клиентом:</span><span class="sxs-lookup"><span data-stu-id="d5002-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="d5002-p106">Создайте CSV-файл (без строки заголовка) и добавьте каждый адрес электронной почты для каждого нужного человека в отдельной строке. Сохраните этот файл на своем компьютере.</span><span class="sxs-lookup"><span data-stu-id="d5002-p106">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line. Save this file to your local computer.</span></span>

2. <span data-ttu-id="d5002-136">На **домашней Advanced eDiscovery** на Параметры  выберите параметр **Configure experimental features**, а затем выберите параметр **Manage attorney-client privilege setting**.</span><span class="sxs-lookup"><span data-stu-id="d5002-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="d5002-137">Отображается **страница привилегий "Адвокат-клиент"** и включена возможность обнаружения привилегий между адвокатом и клиентом. </span><span class="sxs-lookup"><span data-stu-id="d5002-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Страница вылетов привилегий "Адвокат-клиент"](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="d5002-139">Выберите **Обзор,** а затем найдите .csv файл, созданный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="d5002-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="d5002-140">Выберите **Сохранить,** чтобы загрузить список адвокатов.</span><span class="sxs-lookup"><span data-stu-id="d5002-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="d5002-141">Использование модели обнаружения привилегий между адвокатом и клиентом</span><span class="sxs-lookup"><span data-stu-id="d5002-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="d5002-142">Следуйте шагам в этом разделе, чтобы использовать обнаружение привилегий адвоката и клиента для документов в наборе отзывов.</span><span class="sxs-lookup"><span data-stu-id="d5002-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="d5002-143">Шаг 1. Создание группы смарт-тегов с моделью обнаружения привилегий между адвокатом и клиентом</span><span class="sxs-lookup"><span data-stu-id="d5002-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="d5002-144">Один из основных способов увидеть результаты обнаружения адвокатской тайны в ходе проверки — использование группы смарт-тегов.</span><span class="sxs-lookup"><span data-stu-id="d5002-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="d5002-145">Группа смарт-тегов указывает результаты обнаружения адвокатской тайны и выводит их построчно рядом с тегами в группе смарт-тегов.</span><span class="sxs-lookup"><span data-stu-id="d5002-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="d5002-146">Это позволяет быстро выявлять потенциально привилегированные документы во время проверки документов.</span><span class="sxs-lookup"><span data-stu-id="d5002-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="d5002-147">Кроме того, теги в группе смарт-тегов можно использовать для пометки документов как конфиденциальных или не конфиденциальных.</span><span class="sxs-lookup"><span data-stu-id="d5002-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="d5002-148">Дополнительные сведения о смарт-тегах см. в дополнительных сведениях о настройках [смарт-тегов в Advanced eDiscovery.](smart-tags.md)</span><span class="sxs-lookup"><span data-stu-id="d5002-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="d5002-149">В наборе обзоров, который содержит документы, проанализированые  в шаге 1, выберите управляйте набором обзоров и выберите **теги Manage**.</span><span class="sxs-lookup"><span data-stu-id="d5002-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="d5002-150">В **тегах** выберите тягу рядом с **группой Добавить,** а затем **выберите добавить группу смарт-тегов.**</span><span class="sxs-lookup"><span data-stu-id="d5002-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![Выберите "Добавить группу смарт-тегов"](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="d5002-152">На странице **Выбор модели для умной** страницы тегов выберите **Выберите** рядом с привилегией **"Адвокат-клиент".**</span><span class="sxs-lookup"><span data-stu-id="d5002-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="d5002-153">Отображается группа тегов **с именем "Адвокат-клиент".**</span><span class="sxs-lookup"><span data-stu-id="d5002-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="d5002-154">Он содержит два детских тега **с именем Positive** и **Negative**, которые соответствуют возможным результатам, полученным моделью.</span><span class="sxs-lookup"><span data-stu-id="d5002-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Группа смарт-тегов привилегий "Адвокат-клиент"](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="d5002-156">Переименуйте группу тегов и теги, соответствующие вашему обзору.</span><span class="sxs-lookup"><span data-stu-id="d5002-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="d5002-157">Например, можно переименовать Positive в **Privileged** и **Negative** to **Not privileged**. </span><span class="sxs-lookup"><span data-stu-id="d5002-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="d5002-158">Шаг 2. Анализ набора отзывов</span><span class="sxs-lookup"><span data-stu-id="d5002-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="d5002-159">При анализе документов в наборе отзывов будет также работать модель обнаружения привилегий между адвокатом и клиентом, а соответствующие свойства (описанные в описании How [does it work?](#how-does-it-work) будут добавлены к каждому документу в наборе обзоров.</span><span class="sxs-lookup"><span data-stu-id="d5002-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="d5002-160">Дополнительные сведения об анализе данных в наборе обзоров см. в обзоре Анализ данных в наборе [Advanced eDiscovery.](analyzing-data-in-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="d5002-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="d5002-161">Шаг 3. Используйте группу смарт-тегов для просмотра привилегированного контента</span><span class="sxs-lookup"><span data-stu-id="d5002-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="d5002-162">После анализа набора отзывов и настройки смарт-тегов следующим шагом является проверка документов.</span><span class="sxs-lookup"><span data-stu-id="d5002-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="d5002-163">Если модель определила, что документ потенциально привилегированный, соответствующий смарт-тег на панели тегов будет указывать следующие результаты, полученные при обнаружении привилегий между адвокатом и клиентом: </span><span class="sxs-lookup"><span data-stu-id="d5002-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="d5002-164">Если в документе есть содержимое, которое может быть законным по своему характеру, метка **Legal content** отображается рядом с соответствующим смарт-тегом (который в данном случае является тегом **Positive по** умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d5002-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="d5002-165">Если в документе есть участник, найденный в списке  адвоката организации, метка Attorney отображается рядом с соответствующим  смарт-тегом (который в данном случае также является положительным тегом по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d5002-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="d5002-166">Если в документе содержится содержимое, которое может быть законным по  своему характеру и имеет участника, найденного в списке адвоката, отображаются как юридический контент, так и метки Attorney.  </span><span class="sxs-lookup"><span data-stu-id="d5002-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="d5002-167">Если модель определяет, что документ не содержит содержимого, которое является законным по своему характеру или не содержит участника из списка адвокатов, то ни одна метка не отображается на панели тегов.</span><span class="sxs-lookup"><span data-stu-id="d5002-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="d5002-168">Например, на следующих скриншотах покажут два документа.</span><span class="sxs-lookup"><span data-stu-id="d5002-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="d5002-169">Первый содержит содержимое, которое является законным по своему характеру и содержит участника в списке адвокатов.</span><span class="sxs-lookup"><span data-stu-id="d5002-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="d5002-170">Второй не содержит ни того, ни другго, и поэтому не отображает метки.</span><span class="sxs-lookup"><span data-stu-id="d5002-170">The second contains neither and therefore doesn't display any labels.</span></span>

![Документ с метами адвокатского и юридического контента](../media/AeDTaggingPanelLegalContentAttorney.png)

![Документ без меток](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="d5002-173">После просмотра документа, чтобы узнать, содержится ли в нем привилегированное содержимое, можно пометить документ соответствующим тегом.</span><span class="sxs-lookup"><span data-stu-id="d5002-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
