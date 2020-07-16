---
title: Автоматическое применение метки хранения для сохранения или удаления контента
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Создавайте и автоматически публикуйте метки хранения для их автоматического применения в приложениях для сохранения необходимых сведений и удаления ненужных
ms.openlocfilehash: eb29a846f6a7352eec02683c70dad1b0a423bdfa
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127622"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="30d7c-103">Автоматическое применение метки хранения для сохранения или удаления контента</span><span class="sxs-lookup"><span data-stu-id="30d7c-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="30d7c-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="30d7c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="30d7c-105">Одно из главных преимуществ [меток хранения](retention.md) — возможность автоматически их присваивать содержимому, которое соответствует определенным условиям.</span><span class="sxs-lookup"><span data-stu-id="30d7c-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="30d7c-106">В этом случае сотрудникам вашей организации не нужно будет самостоятельно присваивать метки хранения.</span><span class="sxs-lookup"><span data-stu-id="30d7c-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="30d7c-107">Microsoft 365 все сделает за них.</span><span class="sxs-lookup"><span data-stu-id="30d7c-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="30d7c-108">Польза автоматического присваивания меток хранения в том, что:</span><span class="sxs-lookup"><span data-stu-id="30d7c-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="30d7c-109">вам не придется обучать пользователей работе со всеми категориями;</span><span class="sxs-lookup"><span data-stu-id="30d7c-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="30d7c-110">вам не нужно будет рассчитывать на то, что пользователи правильно классифицируют весь контент;</span><span class="sxs-lookup"><span data-stu-id="30d7c-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="30d7c-111">пользователям больше не нужно будет знать о политиках управления данными — они могут сосредоточиться на своей работе.</span><span class="sxs-lookup"><span data-stu-id="30d7c-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="30d7c-112">Метки хранения можно автоматически применять к содержимому, если оно содержит конфиденциальную информацию, ключевые слова или [совпадение для обучаемых классификаторов](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="30d7c-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords, or a match for [trainable classifiers](classifier-getting-started-with.md).</span></span>
    
<span data-ttu-id="30d7c-113">Процесс автоматического применения метки хранения основан на этих условиях:</span><span class="sxs-lookup"><span data-stu-id="30d7c-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![Схема ролей и задач для автоматически применяемых меток](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="30d7c-115">Следуйте инструкциям ниже, чтобы выполнить два действия администратора.</span><span class="sxs-lookup"><span data-stu-id="30d7c-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="30d7c-116">Автоматические политики используют метки на стороне службы в условиях для автоматического применения меток хранения.</span><span class="sxs-lookup"><span data-stu-id="30d7c-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="30d7c-117">Также можно автоматически применить метку хранения с помощью политики меток, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="30d7c-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="30d7c-118">Применение метки хранения по умолчанию к библиотеке SharePoint, папке или набору документов таким образом, чтобы контент без меток помечался автоматически.</span><span class="sxs-lookup"><span data-stu-id="30d7c-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="30d7c-119">Автоматическое применение метки хранения к электронному сообщению с помощью правил</span><span class="sxs-lookup"><span data-stu-id="30d7c-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="30d7c-120">Дополнительные сведения см. в статье [Создание и применение меток хранения в приложениях](create-apply-retention-labels.md)</span><span class="sxs-lookup"><span data-stu-id="30d7c-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="30d7c-121">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="30d7c-121">Before you begin</span></span>

<span data-ttu-id="30d7c-122">Глобальный администратор организации имеет все разрешения на создание и изменение меток хранения и их политик.</span><span class="sxs-lookup"><span data-stu-id="30d7c-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="30d7c-123">Если вы входите не как глобальный администратор, см. раздел [Разрешения, необходимые для создания и управления политиками хранения и метками хранения](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="30d7c-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="30d7c-124">Автоматическое применение меток хранения</span><span class="sxs-lookup"><span data-stu-id="30d7c-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="30d7c-125">Сначала создайте метку хранения.</span><span class="sxs-lookup"><span data-stu-id="30d7c-125">First, create your retention label.</span></span> <span data-ttu-id="30d7c-126">После этого создайте автоматическую политику для применения метки.</span><span class="sxs-lookup"><span data-stu-id="30d7c-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="30d7c-127">Если вы уже создали метку хранения, перейдите к [созданию автоматической политики](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="30d7c-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="30d7c-128">Инструкции по переходу зависят от того, используете ли вы [управление записями](records-management.md) или нет.</span><span class="sxs-lookup"><span data-stu-id="30d7c-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="30d7c-129">В обоих случаях доступны соответствующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="30d7c-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="30d7c-130">Этап 1. Создание метки хранения</span><span class="sxs-lookup"><span data-stu-id="30d7c-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="30d7c-131">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="30d7c-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="30d7c-132">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="30d7c-132">If you are using records management:</span></span>
        - <span data-ttu-id="30d7c-133">**Решения** > **Управление записями** > вкладка **План хранения** > **+ Создать метку** > **Метка хранения**</span><span class="sxs-lookup"><span data-stu-id="30d7c-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="30d7c-134">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="30d7c-134">If you are not using records management:</span></span>
       - <span data-ttu-id="30d7c-135">**Решения** > **Управление информацией** > вкладка **Метки** > + **Создать метку**</span><span class="sxs-lookup"><span data-stu-id="30d7c-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="30d7c-136">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="30d7c-136">Don't immediately see your option?</span></span> <span data-ttu-id="30d7c-137">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="30d7c-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="30d7c-138">Следуйте указаниям мастера.</span><span class="sxs-lookup"><span data-stu-id="30d7c-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="30d7c-139">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="30d7c-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="30d7c-140">Дополнительные сведения о дескрипторах плана хранения, см. в статье [Использование плана хранения для управления метками хранения](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="30d7c-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="30d7c-141">Чтобы использовать метку хранения для объявления содержимого записью, включите флажок **Использовать метку, чтобы классифицировать содержимое как "Запись"**.</span><span class="sxs-lookup"><span data-stu-id="30d7c-141">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

<span data-ttu-id="30d7c-142">Чтобы изменить существующую метку, выберите ее и нажмите **Изменить метку**, чтобы запустить тот же мастер, который позволяет изменить описания меток и любые [доступные параметры](#updating-retention-labels-and-their-policies) на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="30d7c-142">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="30d7c-143">Вместо этого можно выбрать любой из доступных параметров **Редактирования**, чтобы перейти непосредственно на соответствующую страницу для обновления.</span><span class="sxs-lookup"><span data-stu-id="30d7c-143">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="30d7c-144">Этап 2. Создание политики автоматического применения</span><span class="sxs-lookup"><span data-stu-id="30d7c-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="30d7c-145">При создании политики автоматического применения необходимо выбрать метку хранения, которая будет автоматически применена к содержимому на основе указанных условий.</span><span class="sxs-lookup"><span data-stu-id="30d7c-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="30d7c-146">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="30d7c-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="30d7c-147">Если используется управление записями: **Управление информацией**:</span><span class="sxs-lookup"><span data-stu-id="30d7c-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="30d7c-148">**Решения** > **Управление записями** >  вкладка **Политики меток** > **Автоматически применить метку**</span><span class="sxs-lookup"><span data-stu-id="30d7c-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="30d7c-149">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="30d7c-149">If you are not using records management:</span></span>
        - <span data-ttu-id="30d7c-150">**Решения** > **Управление информацией** >  вкладка **Политики меток** > **Автоматически применить метку**</span><span class="sxs-lookup"><span data-stu-id="30d7c-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="30d7c-151">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="30d7c-151">Don't immediately see your option?</span></span> <span data-ttu-id="30d7c-152">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="30d7c-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="30d7c-153">Следуйте указаниям мастера.</span><span class="sxs-lookup"><span data-stu-id="30d7c-153">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="30d7c-154">Сведения о настройке условий для автоматического применения метки хранения, см. в разделе [Настройка условий автоматического применения меток хранения](#configuring-conditions-for-auto-apply-retention-labels) на этой странице.</span><span class="sxs-lookup"><span data-stu-id="30d7c-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="30d7c-155">Сведения о расположениях, поддерживаемых метками хранения, см. в разделе [Метки хранения и расположения](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="30d7c-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="30d7c-156">Чтобы изменить существующую политику автоматического применения меток, выберите ее и нажмите **Изменить политику**, чтобы запустить тот же мастер, который позволяет изменить описание политики и любые [доступные параметры](#updating-retention-labels-and-their-policies) на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="30d7c-156">To edit an existing auto-apply label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="30d7c-157">Вместо этого можно выбрать любой из доступных параметров **Редактирования**, чтобы перейти непосредственно на соответствующую страницу для обновления.</span><span class="sxs-lookup"><span data-stu-id="30d7c-157">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="30d7c-158">Настройка условий для автоматического применения меток хранения</span><span class="sxs-lookup"><span data-stu-id="30d7c-158">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="30d7c-159">Автоматически применяйте метки хранения к контенту, содержащему:</span><span class="sxs-lookup"><span data-stu-id="30d7c-159">You can apply retention labels to content automatically when that content contains:</span></span>

- <span data-ttu-id="30d7c-160">[конфиденциальную информацию определенных типов](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information);</span><span class="sxs-lookup"><span data-stu-id="30d7c-160">[Specific types of sensitive information](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)</span></span>

- <span data-ttu-id="30d7c-161">[определенные ключевые слова, соответствующие созданному запросу](#auto-apply-labels-to-content-with-keywords-or-searchable-properties);</span><span class="sxs-lookup"><span data-stu-id="30d7c-161">[Specific keywords that match a query you create](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)</span></span>

- <span data-ttu-id="30d7c-162">[совпадение для обучаемых классификаторов](#auto-apply-labels-to-content-by-using-trainable-classifiers).</span><span class="sxs-lookup"><span data-stu-id="30d7c-162">[A match for trainable classifiers](#auto-apply-labels-to-content-by-using-trainable-classifiers)</span></span>

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="30d7c-163">Автоматическое применение меток к контенту с определенными типами конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="30d7c-163">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="30d7c-164">Когда вы создаете автоматически присваиваемые метки хранения для конфиденциальной информации, вы видите тот же список шаблонов политик, что и при создании политики защиты от потери данных (DLP) .</span><span class="sxs-lookup"><span data-stu-id="30d7c-164">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="30d7c-165">Каждый шаблон политик настроен для поиска определенных типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="30d7c-165">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="30d7c-166">Например, показанный здесь шаблон служит для выявления идентификационного номера налогоплательщика (ITIN), номера социального страхования (SSN) и номера паспорта в американском формате.</span><span class="sxs-lookup"><span data-stu-id="30d7c-166">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="30d7c-167">Дополнительные сведения см. в статье [Обзор политик защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="30d7c-167">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![Шаблоны политик с типами конфиденциальной информации](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="30d7c-p112">Выбрав шаблон политики, вы можете добавлять или удалять конфиденциальную информацию любых типов, а также менять количество экземпляров и точность совпадения. В приведенном ниже примере метка хранения будет автоматически применяться, только если:</span><span class="sxs-lookup"><span data-stu-id="30d7c-p112">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="30d7c-p113">контент содержит от 1 до 9 экземпляров любого из этих трех типов конфиденциальной информации. Вы можете удалить **максимальное** значение, чтобы оно изменилось на **Любое**;</span><span class="sxs-lookup"><span data-stu-id="30d7c-p113">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="30d7c-173">Обнаруженный тип конфиденциальной информации имеет точность совпадения (уровень доверия) не менее 75.</span><span class="sxs-lookup"><span data-stu-id="30d7c-173">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="30d7c-174">Многие типы конфиденциальной информации определяются с использованием нескольких шаблонов, где для шаблона с более высокой точностью совпадения требуется больше подтверждающих признаков (например, ключевые слова, даты или адреса).</span><span class="sxs-lookup"><span data-stu-id="30d7c-174">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="30d7c-175">Чем меньше минимальное значение точности совпадения (**мин**), тем ниже требования, определяющие соответствие содержимого условию.</span><span class="sxs-lookup"><span data-stu-id="30d7c-175">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="30d7c-176">Дополнительные сведения об этих параметрах см. в разделе [Настройка правил для упрощения или усложнения сопоставления](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="30d7c-176">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Параметры определения типов конфиденциальной информации](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="30d7c-178">Автоматическое применение меток к контенту с ключевыми словами или доступными для поиска свойствами</span><span class="sxs-lookup"><span data-stu-id="30d7c-178">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="30d7c-p115">Вы можете автоматически применять метки к контенту, соответствующему определенным условиям. Имеющиеся в данный момент условия поддерживают применение метки к контенту, содержащему определенные слова, фразы или значения доступных для поиска свойств. Вы можете уточнить запрос с помощью таких операторов поиска, как AND, OR и NOT.</span><span class="sxs-lookup"><span data-stu-id="30d7c-p115">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="30d7c-182">Дополнительные сведения о синтаксисе запросов см. в статье:</span><span class="sxs-lookup"><span data-stu-id="30d7c-182">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="30d7c-183">Руководство по синтаксису языка запросов по ключевым словам (KQL)</span><span class="sxs-lookup"><span data-stu-id="30d7c-183">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="30d7c-p116">Метки на основе запросов используют индекс поиска для определения контента. Дополнительные сведения о допустимых свойствах, доступных для поиска, см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="30d7c-p116">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="30d7c-186">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="30d7c-186">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="30d7c-187">Обзор свойств для обхода и управляемых свойств в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="30d7c-187">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="30d7c-188">Примеры запросов:</span><span class="sxs-lookup"><span data-stu-id="30d7c-188">Examples queries:</span></span>

- <span data-ttu-id="30d7c-189">Exchange</span><span class="sxs-lookup"><span data-stu-id="30d7c-189">Exchange</span></span>
    - <span data-ttu-id="30d7c-190">subject:"Квартальное финансирование"</span><span class="sxs-lookup"><span data-stu-id="30d7c-190">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="30d7c-191">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="30d7c-191">recipients:garthf</span></span><!--nolink--><span data-ttu-id="30d7c-192">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="30d7c-192">@contoso.com</span></span>
- <span data-ttu-id="30d7c-193">SharePoint и OneDrive</span><span class="sxs-lookup"><span data-stu-id="30d7c-193">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="30d7c-194">contenttype:контракт</span><span class="sxs-lookup"><span data-stu-id="30d7c-194">contenttype:contract</span></span>
    - <span data-ttu-id="30d7c-195">site:https</span><span class="sxs-lookup"><span data-stu-id="30d7c-195">site:https</span></span><!--nolink--><span data-ttu-id="30d7c-196">://contoso.sharepoint.com/sites/teams/procurement И contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="30d7c-196">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![Редактор запросов](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="30d7c-198">Автоматическое применение меток к контенту с помощью обучаемых классификаторов</span><span class="sxs-lookup"><span data-stu-id="30d7c-198">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="30d7c-199">При использовании варианта для обучаемого классификатора вы можете выбрать один из встроенных классификаторов или настраиваемый классификатор.</span><span class="sxs-lookup"><span data-stu-id="30d7c-199">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="30d7c-200">К встроенным классификаторам относятся **Резюме**, **Исходный код**, **Целенаправленное притеснение**, **Сквернословие** и **Угрозы**.</span><span class="sxs-lookup"><span data-stu-id="30d7c-200">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Выбор обучаемого классификатора](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="30d7c-202">Мы не рекомендуем использовать встроенный классификатор **Оскорбительная лексика**, так как он генерировал большое количество ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="30d7c-202">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="30d7c-203">Не используйте этот встроенный классификатор, а если вы применяете его в настоящее время, следует перенести с него свои бизнес-процессы.</span><span class="sxs-lookup"><span data-stu-id="30d7c-203">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="30d7c-204">Вместо него рекомендуем использовать встроенные классификаторы **Целенаправленное притеснение**, **Сквернословие** и **Угрозы**.</span><span class="sxs-lookup"><span data-stu-id="30d7c-204">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="30d7c-205">Для автоматического применения меток с помощью классификатора на сайтах и в почтовых ящиках SharePoint Online должно быть не менее 10 МБ данных.</span><span class="sxs-lookup"><span data-stu-id="30d7c-205">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="30d7c-206">Дополнительные сведения об обучаемых классификаторах см. в статье [Начало работы с обучаемыми классификаторами (предварительная версия)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="30d7c-206">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="30d7c-207">Пример конфигурации см. в статье [Подготовка к использованию и использование встроенных классификаторов](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span><span class="sxs-lookup"><span data-stu-id="30d7c-207">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="30d7c-208">Срок вступления меток хранения в силу</span><span class="sxs-lookup"><span data-stu-id="30d7c-208">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="30d7c-209">Когда метки хранения применяются автоматически, может потребоваться до семи дней, чтобы метки хранения были применены ко всему существующему контенту, соответствующему условиям.</span><span class="sxs-lookup"><span data-stu-id="30d7c-209">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Схема, иллюстрирующая, когда автоматически применяемые метки вступают в силу](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="30d7c-211">Обновление меток хранения и их политик</span><span class="sxs-lookup"><span data-stu-id="30d7c-211">Updating retention labels and their policies</span></span>

<span data-ttu-id="30d7c-212">При изменении меток хранения или политики авто-применения, когда метка хранения уже применена к контенту, ваши обновленные параметры автоматически применяются к этому контенту, в дополнение к уже определенному.</span><span class="sxs-lookup"><span data-stu-id="30d7c-212">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="30d7c-213">Некоторые параметры невозможно изменить после создания и сохранения метки или политики, в том числе:</span><span class="sxs-lookup"><span data-stu-id="30d7c-213">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="30d7c-214">Параметры хранения, за исключением срока хранения, если только метка не настроена на хранение или удаление содержимого в зависимости от момента его создания.</span><span class="sxs-lookup"><span data-stu-id="30d7c-214">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="30d7c-215">Параметр классификации в качестве записи.</span><span class="sxs-lookup"><span data-stu-id="30d7c-215">The option to classify as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="30d7c-216">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="30d7c-216">Next steps</span></span>

<span data-ttu-id="30d7c-217">Используйте метки хранения с другой формой автоматизации, [хранением, зависящим от возникновения события](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="30d7c-217">Consider using retention labels with another form of automation, [event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="30d7c-218">При использовании этой конфигурации старт хранения активируется событием, которое вы определяете.</span><span class="sxs-lookup"><span data-stu-id="30d7c-218">When you use this configuration, the start of retention is triggered by an event that you identify.</span></span> <span data-ttu-id="30d7c-219">Можно использовать хранение, зависящее от возникновения событий с помощью автоматической политики или политики меток.</span><span class="sxs-lookup"><span data-stu-id="30d7c-219">You can use event-driven retention with an auto-policy or a label policy.</span></span>

<span data-ttu-id="30d7c-220">Подробный сценарий использования управляемых свойств в SharePoint для автоматического применения меток хранения и реализации хранения, зависящего от возникновения события, см. в статье [Управление жизненным циклом документов SharePoint с метками хранения](auto-apply-retention-labels-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="30d7c-220">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>