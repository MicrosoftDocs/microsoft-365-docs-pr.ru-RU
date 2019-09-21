---
title: Настройка обнаружения доверенных прав клиентов в Advanced eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: Используйте модель обнаружения доверенных прав клиентов, чтобы использовать определение привилегированного содержимого на основе машинного обучения при просмотре контента в расширенном случае обнаружения электронных данных.
ms.openlocfilehash: 943b788dfea62433f0f6c1dca3b6b105cf92bae8
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089882"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a><span data-ttu-id="ecfeb-103">Настройка обнаружения доверенных прав клиентов в Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ecfeb-103">Set up attorney-client privilege detection in Advanced eDiscovery</span></span>

<span data-ttu-id="ecfeb-104">Основной и дорогостоящий аспект фазы проверки любого обнаружения электронных данных — рецензирование документов для привилегированного контента.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-104">A major and costly aspect of the review phase of any eDiscovery process is reviewing documents for privileged content.</span></span> <span data-ttu-id="ecfeb-105">Advanced eDiscovery обеспечивает обнаружение привилегированного содержимого с учетом машинного обучения, чтобы повысить эффективность этого процесса.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-105">Advanced eDiscovery provides machine learning-based detection of privileged content to make this process more efficient.</span></span> <span data-ttu-id="ecfeb-106">Эта функция называется *обнаружением доверенности клиентов*.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-106">This feature is called *attorney-client privilege detection*.</span></span>

> [!NOTE]
> <span data-ttu-id="ecfeb-107">Прежде чем можно будет использовать модель обнаружения доверенных прав клиентов, необходимо согласиться с ней.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-107">You must opt in to the attorney-client privilege detection model before you can use it.</span></span> <span data-ttu-id="ecfeb-108">Для получения инструкций посетите [Шаг 1](#step-1-opt-in-to-attorney-client-privilege-detection) .</span><span class="sxs-lookup"><span data-stu-id="ecfeb-108">See [Step 1](#step-1-opt-in-to-attorney-client-privilege-detection) for instructions.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="ecfeb-109">Как это работает?</span><span class="sxs-lookup"><span data-stu-id="ecfeb-109">How does it work?</span></span>

<span data-ttu-id="ecfeb-110">Когда обнаружение доверенности клиентов включено, все документы в наборе проверки будут обрабатываться моделью обнаружения доверенности клиента, при [анализе данных](analyzing-data-in-review-set.md) в наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-110">When attorney-client privilege detection is enabled, all documents in a review set will be processed by the attorney-client privilege detection model when you [analyze the data](analyzing-data-in-review-set.md) in the review set.</span></span> <span data-ttu-id="ecfeb-111">Модель выполняет две вещи:</span><span class="sxs-lookup"><span data-stu-id="ecfeb-111">The model looks for two things:</span></span>

- <span data-ttu-id="ecfeb-112">Привилегированный контент — модель использует машинное обучение, чтобы определить вероятность того, что документ содержит контент, который является юридическим по природе.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-112">Privileged content – The model uses machine learning to determine the likelihood that the document contains content that is legal in nature.</span></span>

- <span data-ttu-id="ecfeb-113">Участники: в рамках настройки обнаружения доверенности клиентов необходимо предоставить список юристов для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-113">Participants – As part of setting up attorney-client privilege detection, you have to submit a list of attorneys for your organization.</span></span> <span data-ttu-id="ecfeb-114">Затем модель сравнивает участников документа со списком юриста, чтобы определить, имеет ли документ по крайней мере один участник юриста.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-114">The model then compares the participants of the document with the attorney list to determine if a document has at least one attorney participant.</span></span>

<span data-ttu-id="ecfeb-115">Модель создает следующие три свойства для каждого документа:</span><span class="sxs-lookup"><span data-stu-id="ecfeb-115">The model produces the following three properties for every document:</span></span>

- <span data-ttu-id="ecfeb-116">**Атторнэйклиентпривилежескоре** — вероятность того, что документ является юридическим по природе; значения для оценки находятся в диапазоне от **0** до **1**.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-116">**AttorneyClientPrivilegeScore** – The likelihood the document is legal in nature; the values for the score are between **0** and **1**.</span></span>

- <span data-ttu-id="ecfeb-117">**Хасатторнэй** — для этого свойства задано **значение true** , если один из участников документа указан в списке юрист; в противном случае — значение **false**.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-117">**HasAttorney** – This property is set to **true** if one of the document participants is listed in the attorney list; otherwise the value is **false**.</span></span> <span data-ttu-id="ecfeb-118">Значение также задается равным **false** , если ваша организация не отправит список доверенности.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-118">The value is also set to **false** if your organization didn't upload an attorney list.</span></span>

- <span data-ttu-id="ecfeb-119">GetProperty **— для** этого свойства задано значение **true** , если значение для **атторнэйклиентпривилежескоре** превышает пороговое значение, *или* если документ имеет доверенного участника; в противном случае задано значение **false**.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-119">**IsPrivilege** – This property is set to **true** if the value for **AttorneyClientPrivilegeScore** is above the threshold *or* if the document has an attorney participant; otherwise the value is set to **false**.</span></span>

<span data-ttu-id="ecfeb-120">Эти свойства (и соответствующие им значения) добавляются в метаданные файлов документов в наборе рецензирования, как показано на следующем снимке экрана:</span><span class="sxs-lookup"><span data-stu-id="ecfeb-120">These properties (and their corresponding values) are added to the file metadata of the documents in a review set, as shown in the following screenshot:</span></span>

![Юрист — свойства полномочий клиентов, показанные в метаданных файла](media/AeDAttorneyClientPrivilegeMetadata.png)

<span data-ttu-id="ecfeb-122">Эти три свойства также можно искать в наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-122">These three properties are also searchable within a review set.</span></span> <span data-ttu-id="ecfeb-123">Дополнительные сведения см в разделе [Query Data в наборе рецензирования](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="ecfeb-123">For more information, see [Query the data in a review set](review-set-search.md).</span></span>

## <a name="set-up-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="ecfeb-124">Настройка модели обнаружения доверенных прав клиентов</span><span class="sxs-lookup"><span data-stu-id="ecfeb-124">Set up the attorney-client privilege detection model</span></span>

<span data-ttu-id="ecfeb-125">Чтобы включить модель обнаружения доверенности для клиентов, ваша организация должна согласиться и отправить список доверенности.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-125">To enable the attorney-client privilege detection model, your organization has to opt-in and then upload an attorney list.</span></span>

### <a name="step-1-opt-in-to-attorney-client-privilege-detection"></a><span data-ttu-id="ecfeb-126">Шаг 1: согласие на обнаружение доверенности для клиентского доступа</span><span class="sxs-lookup"><span data-stu-id="ecfeb-126">Step 1: Opt-in to attorney-client privilege detection</span></span>

<span data-ttu-id="ecfeb-127">Как было сказано ранее, модель обнаружения доверенных прав клиента в предварительной версии находится в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-127">As previously stated, the attorney-client privilege detection model is in Preview.</span></span> <span data-ttu-id="ecfeb-128">Таким образом, пользователь в Организации обнаружения электронных данных в Организации (член группы администраторов обнаружения электронных данных в группе ролей "Диспетчер eDiscovery") должен принять участие в модели, доступной в расширенных случаях обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-128">Therefore a person in your organization eDiscovery Administrator (a member of the eDiscovery Administrator subgroup in the eDiscovery Manager role group) must opt in to make the model available in your Advanced eDiscovery cases.</span></span>

1. <span data-ttu-id="ecfeb-129">В центре безопасности & соответствия требованиям перейдите на **Обнаружение электронных данных > Advanced eDiscovery**.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-129">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery**.</span></span>

2. <span data-ttu-id="ecfeb-130">На странице " **Расширенное расположение электронных** данных" в разделе **Параметры** выберите пункт **Настройка экспериментальных функций**.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-130">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure experimental features**.</span></span>

   ![Щелкните "Настройка экспериментальных функций"](media/AeDExperimentalFeatures.png)

3. <span data-ttu-id="ecfeb-132">На вкладке **экспериментальные функции** выберите пункт **Управление уровнем доверенности — Клиент**.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-132">On the **Experimental features** tab, click **Manage attorney-client privilege setting**.</span></span>

4. <span data-ttu-id="ecfeb-133">В раскрывающемся списке **права доверенного клиента** щелкните переключатель, чтобы включить компонент, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-133">On the **Attorney-client privilege** flyout page, click the toggle to turn on the feature and then click **Save**.</span></span>

### <a name="step-2-upload-a-list-of-attorneys-optional"></a><span data-ttu-id="ecfeb-134">Шаг 2: Отправка списка юристов (необязательно)</span><span class="sxs-lookup"><span data-stu-id="ecfeb-134">Step 2: Upload a list of attorneys (optional)</span></span>

<span data-ttu-id="ecfeb-135">Чтобы воспользоваться всеми преимуществами модели обнаружения доверенных прав **клиентов и использовать** **результаты, описанные ранее в этой** статье, рекомендуется отправить список адресов электронной почты для юристам и юридические сотрудники, которые работают в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-135">To take full advantage of the attorney-client privilege detection model and use the results of the **Has Attorney** or **Potentially Privileged** detection that was previously described, we recommend that you upload a list of email addresses for the lawyers and legal personnel who work for your organization.</span></span> 

<span data-ttu-id="ecfeb-136">Чтобы отправить список доверенности для использования моделью обнаружения доверенных прав клиента, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ecfeb-136">To upload an attorney list for use by the attorney-client privilege detection model:</span></span>

1. <span data-ttu-id="ecfeb-137">Создайте CSV-файл (без строки заголовка) и добавьте адрес электронной почты для каждого пользователя в отдельной строке.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-137">Create a .csv file (without a header row) and add the email address for each appropriate person on a separate line.</span></span> <span data-ttu-id="ecfeb-138">Сохраните этот файл на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-138">Save this file to your local computer.</span></span>

2. <span data-ttu-id="ecfeb-139">На вкладке " **Расширенное обнаружение электронных** данных" в разделе **Параметры** выберите пункт **Настройка экспериментальных функций**, а затем выберите пункт **Управление юристом — Настройка прав клиента**.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-139">On the **Advanced eDiscovery** home page, in the **Settings** tile, click **Configure experimental features**, and then click **Manage attorney-client privilege setting**.</span></span>

   <span data-ttu-id="ecfeb-140">Отображается страница " **юрист-клиент** ", а также включен переключатель **обнаружения доверенных клиентских прав** .</span><span class="sxs-lookup"><span data-stu-id="ecfeb-140">The **Attorney-client privilege** page is displayed, and the **Attorney-client privilege detection** toggle is turned on.</span></span>

   ![Юрист — всплывающая страница прав клиента](media/AeDUploadAttorneyList.png)

3. <span data-ttu-id="ecfeb-142">Нажмите кнопку **Обзор** , а затем найдите и выберите CSV-файл, созданный в шаге 1.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-142">Click **Browse** and then find and select the .csv file that you created in step 1.</span></span>

4. <span data-ttu-id="ecfeb-143">Нажмите кнопку **сохранить** , чтобы отправить список доверенности.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-143">Click **Save** to upload the attorney list.</span></span>

## <a name="use-the-attorney-client-privilege-detection-model"></a><span data-ttu-id="ecfeb-144">Использование модели обнаружения доверенных прав клиентов</span><span class="sxs-lookup"><span data-stu-id="ecfeb-144">Use the attorney-client privilege detection model</span></span>

<span data-ttu-id="ecfeb-145">Выполните действия, описанные в этом разделе, чтобы использовать обнаружение доверенности клиентов для документов в наборе рецензирования.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-145">Follow the steps in this section to use attorney-client privilege detection for documents in a review set.</span></span>

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a><span data-ttu-id="ecfeb-146">Шаг 1: создание группы смарт-тегов с доверенной моделью обнаружения прав клиентов</span><span class="sxs-lookup"><span data-stu-id="ecfeb-146">Step 1: Create a smart tag group with attorney-client privilege detection model</span></span>

<span data-ttu-id="ecfeb-147">Один из основных способов просмотра результатов обнаружения доверенности клиентов в процессе проверки заключается в использовании группы смарт-тегов.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-147">One of the primary ways to see the results of attorney-client privilege detection in your review process is by using a smart tag group.</span></span> <span data-ttu-id="ecfeb-148">Группа смарт-тегов указывает на результаты обнаружения доверенности клиентов и отображает результаты в виде строки рядом с тегами в группе смарт-тегов.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-148">A smart tag group indicates the results of the attorney-client privilege detection and shows the results in-line next to the tags in a smart tag group.</span></span> <span data-ttu-id="ecfeb-149">Это позволяет быстро определять потенциально привилегированные документы во время рецензирования документов.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-149">This lets you quickly identify potentially privileged documents during document review.</span></span> <span data-ttu-id="ecfeb-150">Кроме того, вы можете использовать теги в группе смарт-тегов, чтобы отмечать документы как привилегированные или непривилегированные.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-150">Additionally, you can also use the tags in the smart tag group to tag documents as privileged or non-privileged.</span></span> <span data-ttu-id="ecfeb-151">Дополнительные сведения о смарт-тегах приведены [в разделе Настройка смарт-тегов в Advanced eDiscovery](smart-tags.md).</span><span class="sxs-lookup"><span data-stu-id="ecfeb-151">For more information about smart tags, see [Set up smart tags in Advanced eDiscovery](smart-tags.md).</span></span>

1. <span data-ttu-id="ecfeb-152">В наборе проверки, содержащем документы, проанализированные на этапе 1, щелкните **Управление набором проверки** , а затем щелкните **Управление тегами**.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-152">In the review set that contains the documents that you analyzed in Step 1, click **Manage review set** and then click **Manage tags**.</span></span>
 
2. <span data-ttu-id="ecfeb-153">В разделе **теги**щелкните раскрывающийся список **Добавить группу** , а затем щелкните **Добавить группу смарт-тегов**.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-153">Under **Tags**, click the pull-down next to **Add group** and then click **Add smart tag group**.</span></span>

   ![Нажмите кнопку "добавить группу смарт-тегов"](media/AeDCreateSmartTag.png)

3. <span data-ttu-id="ecfeb-155">На странице **Выбор модели для смарт-тега** нажмите кнопку **выбрать** рядом с полем **привилегия доверенности клиента**.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-155">On the **Choose a model for your smart tag** page, click **Select** next to **Attorney-client privilege**.</span></span>

   <span data-ttu-id="ecfeb-156">Отображается группа тегов с именем **юрист — клиент** .</span><span class="sxs-lookup"><span data-stu-id="ecfeb-156">A tag group named **Attorney-client privilege** is displayed.</span></span> <span data-ttu-id="ecfeb-157">Он содержит два дочерних тега с именами " **положительный** " и " **отрицательный**", которые соответствуют возможным результатам, получаемым моделью.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-157">It contains two child tags named **Positive** and **Negative**, which correspond to the possible results produced by the model.</span></span>

   ![Юрист — группа смарт-тегов "права клиентов"](media/AeDAttorneyClientSmartTagGroup.png)

3. <span data-ttu-id="ecfeb-159">Переименуйте группу тегов и теги в соответствии с проверкой.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-159">Rename the tag group and tags as appropriate for your review.</span></span> <span data-ttu-id="ecfeb-160">Например, вы можете переименование **положительных** и **отрицательных** **в** **непривилегированные**.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-160">For example, you can rename **Positive** to **Privileged** and **Negative** to **Not privileged**.</span></span>

### <a name="step-2-analyze-a-review-set"></a><span data-ttu-id="ecfeb-161">Шаг 2: анализ набора проверки</span><span class="sxs-lookup"><span data-stu-id="ecfeb-161">Step 2: Analyze a review set</span></span>

<span data-ttu-id="ecfeb-162">При анализе документов в наборе рецензирования также будет выполняться модель обнаружения доверенных прав клиентов и соответствующие свойства (описанные в разделе[как работает?](#how-does-it-work) будет добавлен в каждый документ в наборе проверки.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-162">When you analyze the documents in a review set, the attorney-client privilege detection model will also be run and the corresponding properties (described in[How does it work?](#how-does-it-work) will be added to every document in the review set.</span></span> <span data-ttu-id="ecfeb-163">Более подробную информацию об анализе данных в наборе рецензирования можно узнать в статье [анализ данных в наборе проверки в Advanced eDiscovery](analyzing-data-in-review-set.md).</span><span class="sxs-lookup"><span data-stu-id="ecfeb-163">For more information about analyzing data in review set, see [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).</span></span>

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a><span data-ttu-id="ecfeb-164">Шаг 3: использование группы смарт-тегов для проверки привилегированного контента</span><span class="sxs-lookup"><span data-stu-id="ecfeb-164">Step 3: Use the smart tag group for review of privileged content</span></span>

<span data-ttu-id="ecfeb-165">После анализа набора проверки и настройки смарт-тегов необходимо просмотреть документы.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-165">After analyzing the review set and setting up smart tags, the next step is to review the documents.</span></span> <span data-ttu-id="ecfeb-166">Если модель определила, что документ является потенциально привилегированным, соответствующий смарт-тег в **панели маркировки** будет указывать на следующие результаты, полученные с помощью обнаружения прав клиента.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-166">If the model has determined the document is potentially privileged, the corresponding smart tag in the **Tagging panel** will indicate the following results produced by the attorney-client privilege detection:</span></span>

- <span data-ttu-id="ecfeb-167">Если в документе есть контент, который может быть юридическим **, подпись будет** отображаться рядом с соответствующим смарт-тегом (в данном случае это **положительный** тег по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ecfeb-167">If the document has content that may be legal in nature, the label **Legal content** is displayed next to the corresponding smart tag (which in this case is the default **Positive** tag).</span></span>

- <span data-ttu-id="ecfeb-168">Если в документе есть участник, найденный в списке юриста Организации, то **доверенность** метки отображается рядом с соответствующим смарт-тегом (в данном случае это также **положительный** тег по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ecfeb-168">If the document has a participant who is found in your organization's attorney list, the label **Attorney** is displayed next to the corresponding smart tag (which in this case is also the default **Positive** tag).</span></span>

- <span data-ttu-id="ecfeb-169">Если документ содержит контент, который может быть юридическим в природе *и* содержит участника, найденного в списке юрист, отображаются как **юридические сведения** , так и метки **доверенности** .</span><span class="sxs-lookup"><span data-stu-id="ecfeb-169">If the document has content that may be legal in nature *and* has a participant found in the attorney list, both the **Legal content**  and **Attorney** labels are displayed.</span></span> 

<span data-ttu-id="ecfeb-170">Если модель определяет, что документ не содержит контент, который является юридическим или не содержит участника из списка доверенности, то ни одна из этих меток не отображается в панели маркировки.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-170">If the model determines that a document doesn't contain content that is legal in nature or doesn't contain a participant from the attorney list, then neither label is displayed in the tagging panel.</span></span>

<span data-ttu-id="ecfeb-171">Например, на следующих снимках экрана показаны два документа; Первый из них содержит контент, который является юридическим и содержит участника, найденного в списке юристов; Вторая не содержит ни одной метки.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-171">For example, the following screenshots show two documents; the first one contains content that is legal in nature and has a participant found in the list of attorneys; the second contains neither and therefore doesn't display any labels.</span></span>

![Документ с метками юриста и юридических материалов](media/AeDTaggingPanelLegalContentAttorney.png)

![Документ без меток](media/AeDTaggingPanelNegative.png)

<span data-ttu-id="ecfeb-174">После просмотра документа, чтобы узнать, содержит ли он привилегированный контент, можно пометить документ с помощью соответствующего тега.</span><span class="sxs-lookup"><span data-stu-id="ecfeb-174">After you review a document to see if it contains privileged content, you can tag the document with the appropriate tag.</span></span>