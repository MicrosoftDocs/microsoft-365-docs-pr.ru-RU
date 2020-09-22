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
ms.openlocfilehash: dc525a9f7a2ea97f61f03320495eea737465cfd9
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171307"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="827a7-103">Автоматическое применение метки хранения для сохранения или удаления контента</span><span class="sxs-lookup"><span data-stu-id="827a7-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="827a7-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="827a7-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="827a7-105">Одно из главных преимуществ [меток хранения](retention.md) — возможность автоматически их присваивать содержимому, которое соответствует определенным условиям.</span><span class="sxs-lookup"><span data-stu-id="827a7-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="827a7-106">В этом случае сотрудникам вашей организации не нужно будет самостоятельно присваивать метки хранения.</span><span class="sxs-lookup"><span data-stu-id="827a7-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="827a7-107">Microsoft 365 все сделает за них.</span><span class="sxs-lookup"><span data-stu-id="827a7-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="827a7-108">Польза автоматического присваивания меток хранения в том, что:</span><span class="sxs-lookup"><span data-stu-id="827a7-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="827a7-109">вам не придется обучать пользователей работе со всеми категориями;</span><span class="sxs-lookup"><span data-stu-id="827a7-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="827a7-110">вам не нужно будет рассчитывать на то, что пользователи правильно классифицируют весь контент;</span><span class="sxs-lookup"><span data-stu-id="827a7-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="827a7-111">пользователям больше не нужно будет знать о политиках управления данными — они могут сосредоточиться на своей работе.</span><span class="sxs-lookup"><span data-stu-id="827a7-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="827a7-112">Метки хранения можно автоматически применять к контенту, если он содержит конфиденциальную информацию, ключевые слова, доступные для поиска свойства или совпадение для [обучаемых классификаторов](classifier-get-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="827a7-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

<span data-ttu-id="827a7-113">Процесс автоматического применения метки хранения основан на этих условиях:</span><span class="sxs-lookup"><span data-stu-id="827a7-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![Схема ролей и задач для автоматически применяемых меток](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="827a7-115">Следуйте инструкциям ниже, чтобы выполнить два действия администратора.</span><span class="sxs-lookup"><span data-stu-id="827a7-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="827a7-116">Автоматические политики используют метки на стороне службы в условиях для автоматического применения меток хранения.</span><span class="sxs-lookup"><span data-stu-id="827a7-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="827a7-117">Также можно автоматически применить метку хранения с помощью политики меток, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="827a7-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="827a7-118">Применение метки хранения по умолчанию к библиотеке SharePoint, папке или набору документов таким образом, чтобы контент без меток помечался автоматически.</span><span class="sxs-lookup"><span data-stu-id="827a7-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="827a7-119">Автоматическое применение метки хранения к электронному сообщению с помощью правил</span><span class="sxs-lookup"><span data-stu-id="827a7-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="827a7-120">Дополнительные сведения см. в статье [Создание и применение меток хранения в приложениях](create-apply-retention-labels.md)</span><span class="sxs-lookup"><span data-stu-id="827a7-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="827a7-121">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="827a7-121">Before you begin</span></span>

<span data-ttu-id="827a7-122">Глобальный администратор организации имеет все разрешения на создание и изменение меток хранения и их политик.</span><span class="sxs-lookup"><span data-stu-id="827a7-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="827a7-123">Если вы входите не как глобальный администратор, см. раздел [Разрешения, необходимые для создания и управления политиками хранения и метками хранения](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="827a7-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="827a7-124">Автоматическое применение меток хранения</span><span class="sxs-lookup"><span data-stu-id="827a7-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="827a7-125">Сначала создайте метку хранения.</span><span class="sxs-lookup"><span data-stu-id="827a7-125">First, create your retention label.</span></span> <span data-ttu-id="827a7-126">После этого создайте автоматическую политику для применения метки.</span><span class="sxs-lookup"><span data-stu-id="827a7-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="827a7-127">Если вы уже создали метку хранения, перейдите к [созданию автоматической политики](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="827a7-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="827a7-128">Инструкции по переходу зависят от того, используете ли вы [управление записями](records-management.md) или нет.</span><span class="sxs-lookup"><span data-stu-id="827a7-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="827a7-129">В обоих случаях доступны соответствующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="827a7-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="827a7-130">Этап 1. Создание метки хранения</span><span class="sxs-lookup"><span data-stu-id="827a7-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="827a7-131">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="827a7-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="827a7-132">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="827a7-132">If you are using records management:</span></span>
        - <span data-ttu-id="827a7-133">**Решения** > **Управление записями** > вкладка **План хранения** > **+ Создать метку** > **Метка хранения**</span><span class="sxs-lookup"><span data-stu-id="827a7-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="827a7-134">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="827a7-134">If you are not using records management:</span></span>
       - <span data-ttu-id="827a7-135">**Решения** > **Управление информацией** > вкладка **Метки** > + **Создать метку**</span><span class="sxs-lookup"><span data-stu-id="827a7-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="827a7-136">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="827a7-136">Don't immediately see your option?</span></span> <span data-ttu-id="827a7-137">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="827a7-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="827a7-138">Следуйте указаниям мастера.</span><span class="sxs-lookup"><span data-stu-id="827a7-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="827a7-139">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="827a7-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="827a7-140">Дополнительные сведения о дескрипторах плана хранения, см. в статье [Использование плана хранения для управления метками хранения](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="827a7-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="827a7-141">Для использования метки хранения, чтобы объявить [запись](records-management.md#records), включите параметр **Пометить элементы как записи**.</span><span class="sxs-lookup"><span data-stu-id="827a7-141">To use the retention label to declare a [record](records-management.md#records), enable the option **Mark items as a record**.</span></span>

3. <span data-ttu-id="827a7-142">После того, как вы создали метку и просмотрели параметры для ее публикации, автоматически примените метку или просто сохраните ее: выберите пункт \*\*Автоматически применять эту метку к определенному типу содержимого \*\*, а затем выберите **Готово**, чтобы запустить Мастер автоматического создания меток, который сразу переведет вас к действию 2 в процедуре ниже.</span><span class="sxs-lookup"><span data-stu-id="827a7-142">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="827a7-143">Чтобы изменить существующую метку, выберите ее и нажмите **Изменить метку** для запуска Мастера изменения хранения, который позволяет изменить описания меток и любые [доступные параметры](#updating-retention-labels-and-their-policies) на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="827a7-143">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="827a7-144">Этап 2. Создание политики автоматического применения</span><span class="sxs-lookup"><span data-stu-id="827a7-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="827a7-145">При создании политики автоматического применения необходимо выбрать метку хранения, которая будет автоматически применена к содержимому на основе указанных условий.</span><span class="sxs-lookup"><span data-stu-id="827a7-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="827a7-146">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="827a7-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="827a7-147">Если используется управление записями: **Управление информацией**:</span><span class="sxs-lookup"><span data-stu-id="827a7-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="827a7-148">**Решения** > **Управление записями** >  вкладка **Политики метки** > **Автоматически применить метку**</span><span class="sxs-lookup"><span data-stu-id="827a7-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="827a7-149">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="827a7-149">If you are not using records management:</span></span>
        - <span data-ttu-id="827a7-150">**Решения** > **Управление информацией** >  вкладка **Политики меток** > **Автоматически применить метку**</span><span class="sxs-lookup"><span data-stu-id="827a7-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="827a7-151">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="827a7-151">Don't immediately see your option?</span></span> <span data-ttu-id="827a7-152">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="827a7-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="827a7-153">Следуйте инструкциям в Мастере автоматического создания меток.</span><span class="sxs-lookup"><span data-stu-id="827a7-153">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="827a7-154">Сведения о настройке условий для автоматического применения метки хранения, см. в разделе [Настройка условий автоматического применения меток хранения](#configuring-conditions-for-auto-apply-retention-labels) на этой странице.</span><span class="sxs-lookup"><span data-stu-id="827a7-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="827a7-155">Сведения о расположениях, поддерживаемых метками хранения, см. в разделе [Метки хранения и расположения](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="827a7-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="827a7-156">Чтобы изменить существующую политику автоматического применения меток, выберите ее для запуска Мастера изменения политики хранения, который позволяет изменить выбранную метку хранения и [любые доступные параметры](#updating-retention-labels-and-their-policies) на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="827a7-156">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="827a7-157">Настройка условий для автоматического применения меток хранения</span><span class="sxs-lookup"><span data-stu-id="827a7-157">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="827a7-158">Автоматически применяйте метки хранения к контенту, содержащему:</span><span class="sxs-lookup"><span data-stu-id="827a7-158">You can apply retention labels to content automatically when that content contains:</span></span>

- <span data-ttu-id="827a7-159">[конфиденциальную информацию определенных типов](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information);</span><span class="sxs-lookup"><span data-stu-id="827a7-159">[Specific types of sensitive information](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)</span></span>

- <span data-ttu-id="827a7-160">[определенные ключевые слова или доступные для поиска свойства, соответствующие созданному запросу](#auto-apply-labels-to-content-with-keywords-or-searchable-properties);</span><span class="sxs-lookup"><span data-stu-id="827a7-160">[Specific keywords or searchable properties that match a query you create](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)</span></span>

- <span data-ttu-id="827a7-161">[совпадение для обучаемых классификаторов](#auto-apply-labels-to-content-by-using-trainable-classifiers).</span><span class="sxs-lookup"><span data-stu-id="827a7-161">[A match for trainable classifiers](#auto-apply-labels-to-content-by-using-trainable-classifiers)</span></span>

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="827a7-162">Автоматическое применение меток к контенту с определенными типами конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="827a7-162">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="827a7-163">Когда вы создаете автоматически присваиваемые метки хранения для конфиденциальной информации, вы видите тот же список шаблонов политик, что и при создании политики защиты от потери данных (DLP) .</span><span class="sxs-lookup"><span data-stu-id="827a7-163">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="827a7-164">Каждый шаблон предварительно настроен на поиск определенных типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="827a7-164">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="827a7-165">Например, шаблон, показанный здесь, ищет номера ITIN, SSN и паспорта США в категории **Конфиденциальность** и в **шаблоне Персональных данных (PII) конечного пользователя для США**:</span><span class="sxs-lookup"><span data-stu-id="827a7-165">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template**:</span></span>

![Шаблоны политик с типами конфиденциальной информации](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="827a7-167">Для получения дополнительной информации о типах конфиденциальной информации см. [Определения объектов типа конфиденциальной информации](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="827a7-167">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="827a7-168">Выбрав шаблон политики, вы можете добавлять или удалять любые типы конфиденциальной информации, а также менять количество и точность совпадений.</span><span class="sxs-lookup"><span data-stu-id="827a7-168">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="827a7-169">В примере на снимке экрана ниже показано, что метка хранения будет автоматически применяться только в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="827a7-169">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="827a7-170">Обнаруженный тип конфиденциальной информации имеет точность совпадения (уровень доверия) не менее 75.</span><span class="sxs-lookup"><span data-stu-id="827a7-170">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="827a7-171">Многие типы конфиденциальной информации определяются с использованием нескольких шаблонов, где для шаблона с более высокой точностью совпадения требуется больше подтверждающих признаков (например, ключевые слова, даты или адреса).</span><span class="sxs-lookup"><span data-stu-id="827a7-171">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="827a7-172">Чем меньше минимальное значение точности совпадения (**мин**), тем ниже требования, определяющие соответствие содержимого условию.</span><span class="sxs-lookup"><span data-stu-id="827a7-172">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="827a7-173">В содержимом от 1 до 9 раз встречается любой из перечисленных трех типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="827a7-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="827a7-174">Вы можете удалить **до значения**, таким образом оно будет изменено на **Любой**.</span><span class="sxs-lookup"><span data-stu-id="827a7-174">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="827a7-175">Дополнительные сведения об этих параметрах см. в следующих руководствах в документации по защите от потери данных [Настройка более или менее строгих правил](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="827a7-175">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Параметры определения типов конфиденциальной информации](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="827a7-177">Автоматическое применение меток к контенту с ключевыми словами или доступными для поиска свойствами</span><span class="sxs-lookup"><span data-stu-id="827a7-177">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="827a7-p113">Метки можно автоматически применять к контенту с помощью запроса, содержащего определенные слова, фразы или значения доступных для поиска свойств. Вы можете уточнить запрос с помощью таких операторов поиска, как AND, OR и NOT.</span><span class="sxs-lookup"><span data-stu-id="827a7-p113">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![Редактор запросов](../media/new-retention-query-editor.png)

<span data-ttu-id="827a7-181">Дополнительные сведения о синтаксисе языка запросов по ключевым словам (KQL) см. в статье [Справочник по синтаксису языка запросов по ключевым словам (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="827a7-181">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="827a7-182">Метки на основе запросов используют индекс поиска для определения контента.</span><span class="sxs-lookup"><span data-stu-id="827a7-182">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="827a7-183">Дополнительные сведения о доступных для поиска свойствах, которые можно использовать, см. в статье:</span><span class="sxs-lookup"><span data-stu-id="827a7-183">For more information about the searchable properties that you can use, see:</span></span>

- [<span data-ttu-id="827a7-184">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="827a7-184">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="827a7-185">Обзор свойств для обхода и управляемых свойств в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="827a7-185">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> <span data-ttu-id="827a7-186">Хотя управляемые свойства SharePoint поддерживают псевдонимы, не используйте их при настройке меток хранения.</span><span class="sxs-lookup"><span data-stu-id="827a7-186">Although SharePoint managed properties support aliases, don't use these when you configure your retention labels.</span></span> <span data-ttu-id="827a7-187">Всегда указывайте фактическое имя управляемого свойства, например RefinableString01.</span><span class="sxs-lookup"><span data-stu-id="827a7-187">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

<span data-ttu-id="827a7-188">Примеры запросов:</span><span class="sxs-lookup"><span data-stu-id="827a7-188">Examples queries:</span></span>

| <span data-ttu-id="827a7-189">Рабочая нагрузка</span><span class="sxs-lookup"><span data-stu-id="827a7-189">Workload</span></span> | <span data-ttu-id="827a7-190">Пример</span><span class="sxs-lookup"><span data-stu-id="827a7-190">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="827a7-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="827a7-191">Exchange</span></span>   | `subject:"Quarterly Financials"` |
|<span data-ttu-id="827a7-192">Exchange</span><span class="sxs-lookup"><span data-stu-id="827a7-192">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="827a7-193">SharePoint</span><span class="sxs-lookup"><span data-stu-id="827a7-193">SharePoint</span></span> | `contenttype:contract` |
|<span data-ttu-id="827a7-194">SharePoint</span><span class="sxs-lookup"><span data-stu-id="827a7-194">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="827a7-195">Автоматическое применение меток к контенту с помощью обучаемых классификаторов</span><span class="sxs-lookup"><span data-stu-id="827a7-195">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="827a7-196">При использовании варианта для обучаемого классификатора вы можете выбрать один из встроенных классификаторов или настраиваемый классификатор.</span><span class="sxs-lookup"><span data-stu-id="827a7-196">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="827a7-197">К встроенным классификаторам относятся **Резюме**, **Исходный код**, **Целенаправленное притеснение**, **Сквернословие** и **Угрозы**.</span><span class="sxs-lookup"><span data-stu-id="827a7-197">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Выбор обучаемого классификатора](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="827a7-199">Мы не рекомендуем использовать встроенный классификатор **Оскорбительная лексика**, так как он генерировал большое количество ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="827a7-199">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="827a7-200">Не используйте этот встроенный классификатор, а если вы применяете его в настоящее время, следует перенести с него свои бизнес-процессы.</span><span class="sxs-lookup"><span data-stu-id="827a7-200">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="827a7-201">Вместо него рекомендуем использовать встроенные классификаторы **Целенаправленное притеснение**, **Сквернословие** и **Угрозы**.</span><span class="sxs-lookup"><span data-stu-id="827a7-201">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="827a7-202">Для автоматического применения метки с использованием этого параметра сайты SharePoint и почтовые ящики должны иметь не менее 10 МБ данных.</span><span class="sxs-lookup"><span data-stu-id="827a7-202">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="827a7-203">Дополнительные сведения об обучаемых классификаторах см. в статье [Информация об обучаемых классификаторах (предварительная версия)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="827a7-203">For more information about trainable classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="827a7-204">Если вы используете обучаемые классификаторы для Exchange, см. недавно выпущенную статью [Повторное обучение классификаторов в обозревателе содержимого (предварительная версия)](classifier-how-to-retrain-content-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="827a7-204">If you use trainable classifiers for Exchange, see the recently released [How to retrain a classifier in content explorer (preview)](classifier-how-to-retrain-content-explorer.md).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="827a7-205">Срок вступления меток хранения в силу</span><span class="sxs-lookup"><span data-stu-id="827a7-205">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="827a7-206">Когда метки хранения применяются автоматически, может потребоваться до семи дней, чтобы метки хранения были применены ко всему существующему контенту, соответствующему условиям.</span><span class="sxs-lookup"><span data-stu-id="827a7-206">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Схема, иллюстрирующая, когда автоматически применяемые метки вступают в силу](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="827a7-208">Обновление меток хранения и их политик</span><span class="sxs-lookup"><span data-stu-id="827a7-208">Updating retention labels and their policies</span></span>

<span data-ttu-id="827a7-209">При изменении меток хранения или политики авто-применения, когда метка хранения уже применена к контенту, ваши обновленные параметры автоматически применяются к этому контенту, в дополнение к уже определенному.</span><span class="sxs-lookup"><span data-stu-id="827a7-209">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="827a7-210">Некоторые параметры невозможно изменить после создания и сохранения метки или политики, в том числе:</span><span class="sxs-lookup"><span data-stu-id="827a7-210">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="827a7-211">Параметры хранения, за исключением срока хранения, если только метка не настроена на хранение или удаление содержимого в зависимости от момента его создания.</span><span class="sxs-lookup"><span data-stu-id="827a7-211">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="827a7-212">Параметр, помечающий элементы как запись.</span><span class="sxs-lookup"><span data-stu-id="827a7-212">The option to mark items as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="827a7-213">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="827a7-213">Next steps</span></span>

<span data-ttu-id="827a7-214">Пример сценария, в котором используется политика автоматического применения с управляемыми свойствами в SharePoint и хранение на основе событий, чтобы начать период хранения, см. в статье [Управление жизненным циклом хранящихся в SharePoint документов с помощью меток хранения](auto-apply-retention-labels-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="827a7-214">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
