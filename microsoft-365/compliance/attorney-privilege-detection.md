---
title: Настройка обнаружения адвокатских прав в Advanced eDiscovery
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
description: Используйте модель обнаружения адвокатских привилегий, чтобы использовать обнаружение привилегированного содержимого на основе машинного обучения при просмотре контента в случае Advanced eDiscovery.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358045"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="0ed5a-103">Настройка обнаружения адвокатских прав в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0ed5a-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="0ed5a-104">Основным и дорогостоящим аспектом на этапе проверки любого процесса eDiscovery является проверка документов на привилегированный контент.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="0ed5a-105">Advanced eDiscovery обеспечивает обнаружение привилегированного содержимого на основе машинного обучения, чтобы сделать этот процесс более эффективным.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="0ed5a-106">Эта функция называется *обнаружением адвокатских привилегий.*</span><span class="sxs-lookup"><span data-stu-id="0ed5a-106">This feature is called *attorney-client privilege detection*.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="0ed5a-107">Как это работает?</span><span class="sxs-lookup"><span data-stu-id="0ed5a-107">How does it work?</span></span>

<span data-ttu-id="0ed5a-108">Если обнаружение адвокатских прав включено, все документы в наборе для проверки будут [](analyzing-data-in-review-set.md) обрабатываться моделью обнаружения адвокатских привилегий при анализе данных в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-108">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="0ed5a-109">Модель ищет два вещи:</span><span class="sxs-lookup"><span data-stu-id="0ed5a-109">The model looks for two things:</span></span>

- <span data-ttu-id="0ed5a-110">Привилегированное содержимое — модель использует машинное обучение для определения вероятности того, что документ содержит содержимое, которое является юридическим.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-110">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="0ed5a-111">Участники — в рамках настройки обнаружения адвокатских прав необходимо отправить список юристов для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-111">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="0ed5a-112">Затем модель сравнивает участников документа со списком адвокатов, чтобы определить, имеется ли в документе хотя бы один адвокат.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-112">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="0ed5a-113">Модель создает следующие три свойства для каждого документа:</span><span class="sxs-lookup"><span data-stu-id="0ed5a-113">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="0ed5a-114">**AttorneyClientPrivilegeScore:** Вероятность того, что документ имеет юридический характер; значения для оценки находятся в от **0** до **1**.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-114">**AttorneyClientPrivilegeScore:** The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="0ed5a-115">**HasAttorney:** Это свойство имеет свойство **true,** если один из участников документа указан в списке адвокатов; в противном случае значение **false.**</span><span class="sxs-lookup"><span data-stu-id="0ed5a-115">**HasAttorney:** This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="0ed5a-116">Кроме того, если ваша организация не отправила список адвокатов, ему также за установлено значение **false.**</span><span class="sxs-lookup"><span data-stu-id="0ed5a-116">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="0ed5a-117">**IsPrivilege:** Это свойство имеет значение **true,** если значение **Свойства AttorneyClientPrivilegeScore** превышает пороговое значение или если документ имеет участника-юриста;  в противном случае значение будет установлено как **false**.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-117">**IsPrivilege:** This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="0ed5a-118">Эти свойства (и соответствующие им значения) добавляются в метаданные файлов в наборе для проверки, как показано на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="0ed5a-118">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![Свойства привилегий клиента-юриста, показанные в метаданных файла](../media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="0ed5a-120">Эти три свойства также можно найти в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-120">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="0ed5a-121">Дополнительные сведения [см. в запросе данных в наборе для проверки.](review-set-search.md)</span><span class="sxs-lookup"><span data-stu-id="0ed5a-121">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="0ed5a-122">Настройка модели обнаружения адвокатских прав</span><span class="sxs-lookup"><span data-stu-id="0ed5a-122">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="0ed5a-123">Чтобы включить модель обнаружения адвокатских прав, ваша организация должна включить ее и отправить список адвокатов.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-123">To enable the attorney-client privilege detection model, your organization has to turn it on and then upload an attorney list.</span></span>

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a><span data-ttu-id="0ed5a-124">Шаг 1. Включив обнаружение адвокатских прав</span><span class="sxs-lookup"><span data-stu-id="0ed5a-124">Step 1: Turn on attorney-client privilege detection</span></span>

<span data-ttu-id="0ed5a-125">Лицо, управляющего eDiscovery в вашей организации (участник подгруппы администратора eDiscovery в группе ролей "Менеджер по обнаружению электронных данных"), должно сделать модель доступной в ваших случаях Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-125">A person who is an eDiscovery Administrator in your organization (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="0ed5a-126">В Центре безопасности & соответствия требованиям перейдите в > **Advanced eDiscovery.**</span><span class="sxs-lookup"><span data-stu-id="0ed5a-126">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="0ed5a-127">На **домашней странице Advanced eDiscovery** на плитке  "Параметры" щелкните "Настройка глобальных **параметров аналитики".**</span><span class="sxs-lookup"><span data-stu-id="0ed5a-127">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure global analytics settings**.</span></span>

   ![Выберите "Настройка экспериментальных функций"](../media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="0ed5a-129">На **вкладке "Параметры аналитики"** выберите "Управление привилегиями **юриста".**</span><span class="sxs-lookup"><span data-stu-id="0ed5a-129">On the **Analytics settings** tab, select **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="0ed5a-130">На странице **"Адвокатская привилегия"** включите функцию с помощью выключата и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="0ed5a-130">On the **Attorney-client privilege** flyout page, use the toggle to turn on the feature and then select **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="0ed5a-131">Шаг 2. Отправка списка адвокатов (необязательно)</span><span class="sxs-lookup"><span data-stu-id="0ed5a-131">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="0ed5a-132">Чтобы в полной мере воспользоваться моделью обнаружения адвокатских прав и использовать результаты ранее описанного определения "Has **Attorney** or **Potentially Privileged",** рекомендуется отправить список адресов электронной почты юристам и юристам, которые работают в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-132">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="0ed5a-133">Чтобы отправить список адвокатов для использования с помощью модели обнаружения адвокатских привилегий:</span><span class="sxs-lookup"><span data-stu-id="0ed5a-133">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="0ed5a-134">Создайте CSV-файл (без строки header) и добавьте адрес электронной почты для каждого соответствующего человека в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-134">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="0ed5a-135">Сохраните этот файл на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-135">Save this file to your local computer.</span></span>

2. <span data-ttu-id="0ed5a-136">На **домашней странице Advanced eDiscovery** на плитке "Параметры" выберите "Настройка экспериментальных функций", а затем выберите параметр "Управление адвокатской привилегией **клиента".**  </span><span class="sxs-lookup"><span data-stu-id="0ed5a-136">On the **Advanced eDiscovery** home page, in the **Settings** tile, select **Configure experimental features**, and then select **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="0ed5a-137">**Отобразилась страница "Адвокат-клиент"** и включено переключение обнаружения адвокатских прав. </span><span class="sxs-lookup"><span data-stu-id="0ed5a-137">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Страница "Адвокатская привилегия"](../media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="0ed5a-139">Выберите  "Обзор", а затем найдите CSV-файл, созданный на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-139">Select **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="0ed5a-140">Выберите **"Сохранить",** чтобы отправить список адвокатов.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-140">Select **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="0ed5a-141">Использование модели обнаружения адвокатских прав</span><span class="sxs-lookup"><span data-stu-id="0ed5a-141">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="0ed5a-142">Выполните действия в этом разделе, чтобы использовать обнаружение адвокатских прав для документов в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-142">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="0ed5a-143">Шаг 1. Создание интеллектуальной группы тегов с моделью обнаружения адвокатских привилегий</span><span class="sxs-lookup"><span data-stu-id="0ed5a-143">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="0ed5a-144">Одним из основных способов просмотра результатов обнаружения адвокатских прав в процессе проверки является использование группы смарт-тегов.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-144">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="0ed5a-145">Группа смарт-тегов указывает результаты обнаружения адвокатской привилегии и отображает результаты в строке рядом с тегами в группе смарт-тегов.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-145">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="0ed5a-146">Это позволяет быстро определить потенциально привилегированные документы во время проверки документов.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-146">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="0ed5a-147">Кроме того, вы можете использовать теги в группе смарт-тегов, чтобы пометить документы как привилегированные или непривименные.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-147">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="0ed5a-148">Дополнительные сведения о смарт-тегах см. в подстройке ["Настройка смарт-тегов в Advanced eDiscovery".](smart-tags.md)</span><span class="sxs-lookup"><span data-stu-id="0ed5a-148">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="0ed5a-149">В наборе для проверки, который содержит документы, проанализированы в шаге 1, выберите "Управление набором для **проверки",** а затем выберите **"Управление тегами".**</span><span class="sxs-lookup"><span data-stu-id="0ed5a-149">In the review set that contains the documents that you analyzed in Step 1, select **Manage review set** and then select **Manage tags**.</span></span>
 
2. <span data-ttu-id="0ed5a-150">В **группе "Теги"** выберите оттягивку рядом с "Добавить группу",  а затем выберите **"Добавить группу смарт-тегов".**</span><span class="sxs-lookup"><span data-stu-id="0ed5a-150">Under **Tags**, select the pull-down next to **Add group** and then select **Add smart tag group**.</span></span>

   ![Выберите "Добавить группу смарт-тегов"](../media/AeDCreateSmartTag.png)

3. <span data-ttu-id="0ed5a-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-152">On the **Choose a model for your smart tag** page, choose **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="0ed5a-153">Отображается группа тегов **с именем "Адвокат-клиент".**</span><span class="sxs-lookup"><span data-stu-id="0ed5a-153">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="0ed5a-154">Он содержит два child тега **с именами Positive** и **Negative**, которые соответствуют возможным результатам, полученным моделью.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-154">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Группа смарт-тегов для привилегий юриста](../media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="0ed5a-156">Переименуйте группу тегов и теги соответствующим образом для проверки.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-156">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="0ed5a-157">Например, можно переименовать **положительное** на **Privileged,** а **отрицательное** — **на "Не привилегированное".**</span><span class="sxs-lookup"><span data-stu-id="0ed5a-157">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="0ed5a-158">Шаг 2. Анализ набора для проверки</span><span class="sxs-lookup"><span data-stu-id="0ed5a-158">Step 2: Analyze a review set</span></span>

<span data-ttu-id="0ed5a-159">При анализе документов в наборе для проверки также будет запускаться модель обнаружения адвокатских прав и соответствующие свойства (описанные в описании ее [работы?](#how-does-it-work) будут добавлены в каждый документ в наборе для проверки.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-159">When you analyze the documents in a review set, the attorney-client privilege detection model will also run and the corresponding properties (described in [How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="0ed5a-160">Дополнительные сведения об анализе данных в наборе для проверки см. в анализе данных в наборе для проверки [в Advanced eDiscovery.](analyzing-data-in-review-set.md)</span><span class="sxs-lookup"><span data-stu-id="0ed5a-160">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="0ed5a-161">Шаг 3. Использование группы смарт-тегов для проверки привилегированного содержимого</span><span class="sxs-lookup"><span data-stu-id="0ed5a-161">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="0ed5a-162">После анализа настройки проверки и настройки смарт-тегов необходимо просмотреть документы.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-162">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="0ed5a-163">Если модель определила, что документ потенциально привилегированный, соответствующий смарт-тег на панели тегов будет указывать следующие результаты, полученные при обнаружении адвокатской привилегии: </span><span class="sxs-lookup"><span data-stu-id="0ed5a-163">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="0ed5a-164">Если документ содержит содержимое, которое может быть  юридическим, метка "Юридическое содержимое" отображается рядом с соответствующим смарт-тегом (в данном случае это положительный тег по **умолчанию).**</span><span class="sxs-lookup"><span data-stu-id="0ed5a-164">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="0ed5a-165">Если в документе есть участник, который находится в списке адвокатов вашей организации, метка **"Адвокат"** отображается рядом с соответствующим смарт-тегом (который в данном случае также является положительным тегом по **умолчанию).**</span><span class="sxs-lookup"><span data-stu-id="0ed5a-165">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="0ed5a-166">Если документ содержит содержимое, которое может быть юридическим по своей сути  и  содержит участника в списке адвокатов, отображаются как юридическое содержимое, так и метки "Адвокат". </span><span class="sxs-lookup"><span data-stu-id="0ed5a-166">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="0ed5a-167">Если модель определяет, что документ не содержит содержимого, которое является юридическим или не содержит участника из списка адвокатов, то ни одна метка не отображается на панели тегов.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-167">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="0ed5a-168">Например, на следующих снимках экрана представлены два документа.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-168">For example, the following screenshots show two documents.</span></span> <span data-ttu-id="0ed5a-169">Первый содержит юридическое содержимое, которое содержит участника в списке адвокатов.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-169">The first one contains content that is legal in nature and has a participant found in the list of attorneys.</span></span> <span data-ttu-id="0ed5a-170">Вторая не содержит ни одной из них, поэтому не отображает метки.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-170">The second contains neither and therefore doesn't display any labels.</span></span>

![Документ с подписями адвокатского и юридического содержимого](../media/AeDTaggingPanelLegalContentAttorney.png)

![Документ без меток](../media/AeDTaggingPanelNegative.png)

<span data-ttu-id="0ed5a-173">После просмотра документа, чтобы узнать, содержит ли он привилегированное содержимое, можно пометить документ соответствующим тегом.</span><span class="sxs-lookup"><span data-stu-id="0ed5a-173">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>
