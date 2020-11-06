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
ms.openlocfilehash: c1c18f5445b326ad7353d8c534940d3db69a3f24
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931983"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="d1f96-103">Автоматическое применение метки хранения для сохранения или удаления контента</span><span class="sxs-lookup"><span data-stu-id="d1f96-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="d1f96-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="d1f96-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

> [!NOTE]
> <span data-ttu-id="d1f96-105">Этот сценарий не поддерживается для [нормативных записей](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="d1f96-105">This scenario is not supported for [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="d1f96-106">Одно из главных преимуществ [меток хранения](retention.md) — возможность автоматически их присваивать содержимому, которое соответствует определенным условиям.</span><span class="sxs-lookup"><span data-stu-id="d1f96-106">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="d1f96-107">В этом случае сотрудникам вашей организации не нужно будет самостоятельно присваивать метки хранения.</span><span class="sxs-lookup"><span data-stu-id="d1f96-107">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="d1f96-108">Microsoft 365 все сделает за них.</span><span class="sxs-lookup"><span data-stu-id="d1f96-108">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="d1f96-109">Польза автоматического присваивания меток хранения в том, что:</span><span class="sxs-lookup"><span data-stu-id="d1f96-109">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="d1f96-110">вам не придется обучать пользователей работе со всеми категориями;</span><span class="sxs-lookup"><span data-stu-id="d1f96-110">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="d1f96-111">вам не нужно будет рассчитывать на то, что пользователи правильно классифицируют весь контент;</span><span class="sxs-lookup"><span data-stu-id="d1f96-111">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="d1f96-112">пользователям больше не нужно будет знать о политиках управления данными — они могут сосредоточиться на своей работе.</span><span class="sxs-lookup"><span data-stu-id="d1f96-112">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="d1f96-113">Метки хранения можно автоматически применять к контенту, если он содержит конфиденциальную информацию, ключевые слова, доступные для поиска свойства или совпадение для [обучаемых классификаторов](classifier-get-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="d1f96-113">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

> [!TIP]
> <span data-ttu-id="d1f96-114">Теперь в предварительной версии с помощью свойств, по которым выполняется поиск, можно найти [записи собраний в Teams](#microsoft-teams-meeting-recordings).</span><span class="sxs-lookup"><span data-stu-id="d1f96-114">Now in preview, use searchable properties to identify [Teams meeting recordings](#microsoft-teams-meeting-recordings).</span></span>

<span data-ttu-id="d1f96-115">Процесс автоматического применения метки хранения основан на этих условиях:</span><span class="sxs-lookup"><span data-stu-id="d1f96-115">The processes to automatically apply a retention label based on these conditions:</span></span>

![Схема ролей и задач для автоматически применяемых меток](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="d1f96-117">Следуйте инструкциям ниже, чтобы выполнить два действия администратора.</span><span class="sxs-lookup"><span data-stu-id="d1f96-117">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="d1f96-118">Автоматические политики используют метки на стороне службы в условиях для автоматического применения меток хранения.</span><span class="sxs-lookup"><span data-stu-id="d1f96-118">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="d1f96-119">Также можно автоматически применить метку хранения с помощью политики меток, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="d1f96-119">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="d1f96-120">Применение метки хранения по умолчанию к библиотеке SharePoint, папке или набору документов таким образом, чтобы контент без меток помечался автоматически.</span><span class="sxs-lookup"><span data-stu-id="d1f96-120">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="d1f96-121">Автоматическое применение метки хранения к электронному сообщению с помощью правил</span><span class="sxs-lookup"><span data-stu-id="d1f96-121">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="d1f96-122">Дополнительные сведения см. в статье [Создание и применение меток хранения в приложениях](create-apply-retention-labels.md)</span><span class="sxs-lookup"><span data-stu-id="d1f96-122">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d1f96-123">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="d1f96-123">Before you begin</span></span>

<span data-ttu-id="d1f96-124">Глобальный администратор организации имеет все разрешения на создание и изменение меток хранения и их политик.</span><span class="sxs-lookup"><span data-stu-id="d1f96-124">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="d1f96-125">Если вы входите не как глобальный администратор, см. раздел [Разрешения, необходимые для создания и управления политиками хранения и метками хранения](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="d1f96-125">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="d1f96-126">Автоматическое применение меток хранения</span><span class="sxs-lookup"><span data-stu-id="d1f96-126">How to auto-apply a retention label</span></span>

<span data-ttu-id="d1f96-127">Сначала создайте метку хранения.</span><span class="sxs-lookup"><span data-stu-id="d1f96-127">First, create your retention label.</span></span> <span data-ttu-id="d1f96-128">После этого создайте автоматическую политику для применения метки.</span><span class="sxs-lookup"><span data-stu-id="d1f96-128">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="d1f96-129">Если вы уже создали метку хранения, перейдите к [созданию автоматической политики](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="d1f96-129">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="d1f96-130">Инструкции по переходу зависят от того, используете ли вы [управление записями](records-management.md) или нет.</span><span class="sxs-lookup"><span data-stu-id="d1f96-130">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="d1f96-131">В обоих случаях доступны соответствующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="d1f96-131">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="d1f96-132">Этап 1. Создание метки хранения</span><span class="sxs-lookup"><span data-stu-id="d1f96-132">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="d1f96-133">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="d1f96-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="d1f96-134">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="d1f96-134">If you are using records management:</span></span>
        - <span data-ttu-id="d1f96-135">**Решения** > **Управление записями** > вкладка **План хранения** > **+ Создать метку** > **Метка хранения**</span><span class="sxs-lookup"><span data-stu-id="d1f96-135">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="d1f96-136">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="d1f96-136">If you are not using records management:</span></span>
       - <span data-ttu-id="d1f96-137">**Решения** > **Управление информацией** > вкладка **Метки** > + **Создать метку**</span><span class="sxs-lookup"><span data-stu-id="d1f96-137">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="d1f96-138">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="d1f96-138">Don't immediately see your option?</span></span> <span data-ttu-id="d1f96-139">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="d1f96-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="d1f96-140">Следуйте указаниям мастера.</span><span class="sxs-lookup"><span data-stu-id="d1f96-140">Follow the prompts in the wizard.</span></span> <span data-ttu-id="d1f96-141">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="d1f96-141">If you are using records management:</span></span>
    
    - <span data-ttu-id="d1f96-142">Дополнительные сведения о дескрипторах плана хранения, см. в статье [Использование плана хранения для управления метками хранения](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="d1f96-142">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="d1f96-143">Чтобы использовать метку хранения для объявления элементов записями, нажмите кнопку **Пометить элементы как записи** или **Пометить элементы как нормативные записи**.</span><span class="sxs-lookup"><span data-stu-id="d1f96-143">To use the retention label to declare records, select **Mark items as records** , or **Mark items as regulatory records**.</span></span> <span data-ttu-id="d1f96-144">Дополнительные сведения см. в статье [Настройка меток хранения для объявления элементов записями](declare-records.md#configuring-retention-labels-to-declare-records)</span><span class="sxs-lookup"><span data-stu-id="d1f96-144">For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="d1f96-145">После того, как вы создали метку и просмотрели параметры для ее публикации, автоматически примените метку или просто сохраните ее: выберите пункт **Автоматически применять эту метку к определенному типу содержимого** , а затем выберите **Готово** , чтобы запустить Мастер автоматического создания меток, который сразу переведет вас к действию 2 в процедуре ниже.</span><span class="sxs-lookup"><span data-stu-id="d1f96-145">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content** , and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="d1f96-146">Чтобы изменить существующую метку, выберите ее и нажмите **Изменить метку** для запуска Мастера изменения хранения, который позволяет изменить описания меток и любые [доступные параметры](#updating-retention-labels-and-their-policies) на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="d1f96-146">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="d1f96-147">Этап 2. Создание политики автоматического применения</span><span class="sxs-lookup"><span data-stu-id="d1f96-147">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="d1f96-148">При создании политики автоматического применения необходимо выбрать метку хранения, которая будет автоматически применена к содержимому на основе указанных условий.</span><span class="sxs-lookup"><span data-stu-id="d1f96-148">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="d1f96-149">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="d1f96-149">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="d1f96-150">Если используется управление записями: **Управление информацией** :</span><span class="sxs-lookup"><span data-stu-id="d1f96-150">If you are using records management: **Information governance** :</span></span>
        - <span data-ttu-id="d1f96-151">**Решения** > **Управление записями** >  вкладка **Политики метки** > **Автоматически применить метку**</span><span class="sxs-lookup"><span data-stu-id="d1f96-151">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="d1f96-152">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="d1f96-152">If you are not using records management:</span></span>
        - <span data-ttu-id="d1f96-153">**Решения** > **Управление информацией** >  вкладка **Политики меток** > **Автоматически применить метку**</span><span class="sxs-lookup"><span data-stu-id="d1f96-153">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="d1f96-154">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="d1f96-154">Don't immediately see your option?</span></span> <span data-ttu-id="d1f96-155">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="d1f96-155">First select **Show all**.</span></span> 

2. <span data-ttu-id="d1f96-156">Следуйте инструкциям в Мастере автоматического создания меток.</span><span class="sxs-lookup"><span data-stu-id="d1f96-156">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="d1f96-157">Сведения о настройке условий для автоматического применения метки хранения, см. в разделе [Настройка условий автоматического применения меток хранения](#configuring-conditions-for-auto-apply-retention-labels) на этой странице.</span><span class="sxs-lookup"><span data-stu-id="d1f96-157">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="d1f96-158">Сведения о расположениях, поддерживаемых метками хранения, см. в разделе [Метки хранения и расположения](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="d1f96-158">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="d1f96-159">Чтобы изменить существующую политику автоматического применения меток, выберите ее для запуска Мастера изменения политики хранения, который позволяет изменить выбранную метку хранения и [любые доступные параметры](#updating-retention-labels-and-their-policies) на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="d1f96-159">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="d1f96-160">Настройка условий для автоматического применения меток хранения</span><span class="sxs-lookup"><span data-stu-id="d1f96-160">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="d1f96-161">Автоматически применяйте метки хранения к контенту, содержащему:</span><span class="sxs-lookup"><span data-stu-id="d1f96-161">You can apply retention labels to content automatically when that content contains:</span></span>

- <span data-ttu-id="d1f96-162">[конфиденциальную информацию определенных типов](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information);</span><span class="sxs-lookup"><span data-stu-id="d1f96-162">[Specific types of sensitive information](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)</span></span>

- <span data-ttu-id="d1f96-163">[определенные ключевые слова или доступные для поиска свойства, соответствующие созданному запросу](#auto-apply-labels-to-content-with-keywords-or-searchable-properties);</span><span class="sxs-lookup"><span data-stu-id="d1f96-163">[Specific keywords or searchable properties that match a query you create](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)</span></span>

- <span data-ttu-id="d1f96-164">[совпадение для обучаемых классификаторов](#auto-apply-labels-to-content-by-using-trainable-classifiers).</span><span class="sxs-lookup"><span data-stu-id="d1f96-164">[A match for trainable classifiers](#auto-apply-labels-to-content-by-using-trainable-classifiers)</span></span>

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="d1f96-165">Автоматическое применение меток к контенту с определенными типами конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="d1f96-165">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="d1f96-166">Когда вы создаете политики автоматического применения меток хранения для конфиденциальной информации, вы видите тот же список шаблонов политик, что и при создании политики защиты от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="d1f96-166">When you create auto-apply retention label policies for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="d1f96-167">Каждый шаблон предварительно настроен на поиск определенных типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="d1f96-167">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="d1f96-168">Например, шаблон, показанный здесь, ищет номера ITIN, SSN и паспорта США в категории **Конфиденциальность** и в **шаблоне Персональных данных (PII) конечного пользователя для США** :</span><span class="sxs-lookup"><span data-stu-id="d1f96-168">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template** :</span></span>

![Шаблоны политик с типами конфиденциальной информации](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="d1f96-170">Для получения дополнительной информации о типах конфиденциальной информации см. [Определения объектов типа конфиденциальной информации](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="d1f96-170">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="d1f96-171">Выбрав шаблон политики, вы можете добавлять или удалять любые типы конфиденциальной информации, а также менять количество и точность совпадений.</span><span class="sxs-lookup"><span data-stu-id="d1f96-171">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="d1f96-172">В примере на снимке экрана ниже показано, что метка хранения будет автоматически применяться только в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="d1f96-172">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="d1f96-173">Обнаруженный тип конфиденциальной информации имеет точность совпадения (уровень доверия) не менее 75.</span><span class="sxs-lookup"><span data-stu-id="d1f96-173">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="d1f96-174">Многие типы конфиденциальной информации определяются с использованием нескольких шаблонов, где для шаблона с более высокой точностью совпадения требуется больше подтверждающих признаков (например, ключевые слова, даты или адреса).</span><span class="sxs-lookup"><span data-stu-id="d1f96-174">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="d1f96-175">Чем меньше минимальное значение точности совпадения ( **мин** ), тем ниже требования, определяющие соответствие содержимого условию.</span><span class="sxs-lookup"><span data-stu-id="d1f96-175">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="d1f96-176">В содержимом от 1 до 9 раз встречается любой из перечисленных трех типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="d1f96-176">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="d1f96-177">Вы можете удалить **до значения** , таким образом оно будет изменено на **Любой**.</span><span class="sxs-lookup"><span data-stu-id="d1f96-177">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="d1f96-178">Дополнительные сведения об этих параметрах см. в следующих руководствах в документации по защите от потери данных [Настройка более или менее строгих правил](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="d1f96-178">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Параметры определения типов конфиденциальной информации](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="d1f96-180">Автоматическое применение меток к контенту с ключевыми словами или доступными для поиска свойствами</span><span class="sxs-lookup"><span data-stu-id="d1f96-180">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="d1f96-p114">Метки можно автоматически применять к контенту с помощью запроса, содержащего определенные слова, фразы или значения доступных для поиска свойств. Вы можете уточнить запрос с помощью таких операторов поиска, как AND, OR и NOT.</span><span class="sxs-lookup"><span data-stu-id="d1f96-p114">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![Редактор запросов](../media/new-retention-query-editor.png)

<span data-ttu-id="d1f96-184">Дополнительные сведения о синтаксисе языка запросов по ключевым словам (KQL) см. в статье [Справочник по синтаксису языка запросов по ключевым словам (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="d1f96-184">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="d1f96-185">Метки на основе запросов используют индекс поиска для определения контента.</span><span class="sxs-lookup"><span data-stu-id="d1f96-185">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="d1f96-186">Дополнительные сведения о доступных для поиска свойствах, которые можно использовать, см. в статье:</span><span class="sxs-lookup"><span data-stu-id="d1f96-186">For more information about the searchable properties that you can use, see:</span></span>

- [<span data-ttu-id="d1f96-187">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="d1f96-187">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="d1f96-188">Обзор свойств для обхода и управляемых свойств в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="d1f96-188">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> <span data-ttu-id="d1f96-189">Хотя управляемые свойства SharePoint поддерживают псевдонимы, не используйте их при настройке меток хранения.</span><span class="sxs-lookup"><span data-stu-id="d1f96-189">Although SharePoint managed properties support aliases, don't use these when you configure your retention labels.</span></span> <span data-ttu-id="d1f96-190">Всегда указывайте фактическое имя управляемого свойства, например RefinableString01.</span><span class="sxs-lookup"><span data-stu-id="d1f96-190">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

<span data-ttu-id="d1f96-191">Примеры запросов:</span><span class="sxs-lookup"><span data-stu-id="d1f96-191">Examples queries:</span></span>

| <span data-ttu-id="d1f96-192">Рабочая нагрузка</span><span class="sxs-lookup"><span data-stu-id="d1f96-192">Workload</span></span> | <span data-ttu-id="d1f96-193">Пример</span><span class="sxs-lookup"><span data-stu-id="d1f96-193">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="d1f96-194">Exchange</span><span class="sxs-lookup"><span data-stu-id="d1f96-194">Exchange</span></span>   | `subject:"Quarterly Financials"` |
|<span data-ttu-id="d1f96-195">Exchange</span><span class="sxs-lookup"><span data-stu-id="d1f96-195">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="d1f96-196">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d1f96-196">SharePoint</span></span> | `contenttype:contract` |
|<span data-ttu-id="d1f96-197">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d1f96-197">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

##### <a name="microsoft-teams-meeting-recordings"></a><span data-ttu-id="d1f96-198">Записи собраний в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1f96-198">Microsoft Teams meeting recordings</span></span>

> [!NOTE]
> <span data-ttu-id="d1f96-199">Функция хранения и удаления записей собраний в Teams развертывается в предварительной версии и не работает до сохранения записей в OneDrive или SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d1f96-199">The ability to retain and delete Teams meeting recordings is rolling out in preview and won't work before recordings are saved to OneDrive or SharePoint.</span></span> <span data-ttu-id="d1f96-200">Дополнительные сведения см. в статье [Использование OneDrive для бизнеса, SharePoint или Stream для записи собраний](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change)</span><span class="sxs-lookup"><span data-stu-id="d1f96-200">For more information, see [Use OneDrive for Business and SharePoint Online or Stream for meeting recordings](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change).</span></span>

<span data-ttu-id="d1f96-201">Для поиска записей собраний в Microsoft Teams, хранящихся в пользовательских учетных записях OneDrive или SharePoint, укажите для **редактора запросов по ключевым словам** следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="d1f96-201">To identify Microsoft Teams meeting recordings that are stored in users' OneDrive accounts or in SharePoint, specify the following for the **Keyword query editor** :</span></span>

``` 
ProgID:Media AND ProgID:Meeting
```

<span data-ttu-id="d1f96-202">В большинстве случаев записи собраний сохраняются в OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d1f96-202">Most of the time, meeting recordings are saved to OneDrive.</span></span> <span data-ttu-id="d1f96-203">Но для собраний канала они сохраняются в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d1f96-203">But for channel meetings, they are saved in SharePoint.</span></span>


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="d1f96-204">Автоматическое применение меток к контенту с помощью обучаемых классификаторов</span><span class="sxs-lookup"><span data-stu-id="d1f96-204">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="d1f96-205">При использовании варианта для обучаемого классификатора вы можете выбрать один из встроенных классификаторов или настраиваемый классификатор.</span><span class="sxs-lookup"><span data-stu-id="d1f96-205">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="d1f96-206">К встроенным классификаторам относятся **Резюме** , **Исходный код** , **Целенаправленное притеснение** , **Сквернословие** и **Угрозы**.</span><span class="sxs-lookup"><span data-stu-id="d1f96-206">The built-in classifiers include **Resumes** , **SourceCode** , **Targeted Harassment** , **Profanity** , and **Threat** :</span></span>

![Выбор обучаемого классификатора](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="d1f96-208">Мы не рекомендуем использовать встроенный классификатор **Оскорбительная лексика** , так как он генерировал большое количество ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="d1f96-208">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="d1f96-209">Не используйте этот встроенный классификатор, а если вы применяете его в настоящее время, следует перенести с него свои бизнес-процессы.</span><span class="sxs-lookup"><span data-stu-id="d1f96-209">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="d1f96-210">Вместо него рекомендуем использовать встроенные классификаторы **Целенаправленное притеснение** , **Сквернословие** и **Угрозы**.</span><span class="sxs-lookup"><span data-stu-id="d1f96-210">We recommend using the **Targeted Harassment** , **Profanity** , and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="d1f96-211">Для автоматического применения метки с использованием этого параметра сайты SharePoint и почтовые ящики должны иметь не менее 10 МБ данных.</span><span class="sxs-lookup"><span data-stu-id="d1f96-211">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="d1f96-212">Дополнительные сведения об обучаемых классификаторах см. в статье [Информация об обучаемых классификаторах (предварительная версия)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="d1f96-212">For more information about trainable classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="d1f96-213">Если вы используете обучаемые классификаторы для Exchange, см. недавно выпущенную статью [Повторное обучение классификаторов в обозревателе содержимого (предварительная версия)](classifier-how-to-retrain-content-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="d1f96-213">If you use trainable classifiers for Exchange, see the recently released [How to retrain a classifier in content explorer (preview)](classifier-how-to-retrain-content-explorer.md).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="d1f96-214">Срок вступления меток хранения в силу</span><span class="sxs-lookup"><span data-stu-id="d1f96-214">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="d1f96-215">Когда метки хранения применяются автоматически, может потребоваться до семи дней, чтобы метки хранения были применены ко всему существующему контенту, соответствующему условиям.</span><span class="sxs-lookup"><span data-stu-id="d1f96-215">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Схема, иллюстрирующая, когда автоматически применяемые метки вступают в силу](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

<span data-ttu-id="d1f96-217">Если после семи дней ожидаемые метки не появляются, проверьте **Состояние** политики автоматического применения, выбрав ее на странице **Политики меток** в Центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d1f96-217">If the expected labels don't appear after seven days, check the **Status** of the auto-apply policy by selecting it from the **Label policies** page in the compliance center.</span></span> <span data-ttu-id="d1f96-218">Для повторного развертывания политики (для OneDrive) или если отображается состояние **Отключено (ошибка)** , а в сведениях расположений выводится сообщение о том, что развертывание политики (для SharePoint) занимает больше времени, чем ожидалось, попробуйте выполнить команду [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) в PowerShell, чтобы повторно распространить политику:</span><span class="sxs-lookup"><span data-stu-id="d1f96-218">If you see the status of **Off (Error)** and in the details for the locations see a message that it's taking longer than expected to deploy the policy (for SharePoint) or to try redeploying the policy (for OneDrive), try running the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell command to retry the policy distribution:</span></span>

1. <span data-ttu-id="d1f96-219">[Подключение к Центру безопасности и соответствия требованиям Windows PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="d1f96-219">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="d1f96-220">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d1f96-220">Run the following command:</span></span>
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="d1f96-221">Обновление меток хранения и их политик</span><span class="sxs-lookup"><span data-stu-id="d1f96-221">Updating retention labels and their policies</span></span>

<span data-ttu-id="d1f96-222">При изменении меток хранения или политики авто-применения, когда метка хранения уже применена к контенту, ваши обновленные параметры автоматически применяются к этому контенту, в дополнение к уже определенному.</span><span class="sxs-lookup"><span data-stu-id="d1f96-222">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="d1f96-223">Некоторые параметры невозможно изменить после создания и сохранения метки или политики, в том числе:</span><span class="sxs-lookup"><span data-stu-id="d1f96-223">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="d1f96-224">Параметры хранения, за исключением срока хранения, если только метка не настроена на хранение или удаление содержимого в зависимости от момента его создания.</span><span class="sxs-lookup"><span data-stu-id="d1f96-224">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="d1f96-225">Параметр, помечающий элементы как запись.</span><span class="sxs-lookup"><span data-stu-id="d1f96-225">The option to mark items as a record.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="d1f96-226">Блокировка политики для предотвращения изменений</span><span class="sxs-lookup"><span data-stu-id="d1f96-226">Locking the policy to prevent changes</span></span>

<span data-ttu-id="d1f96-227">Чтобы гарантировать, что никто не сможет отключить политику, удалить ее или сделать ее менее строгой, см. раздел [Использование блокировки для сохранения для ограничения изменений политик хранения и политик меток хранения](retention-preservation-lock.md).</span><span class="sxs-lookup"><span data-stu-id="d1f96-227">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1f96-228">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="d1f96-228">Next steps</span></span>

<span data-ttu-id="d1f96-229">Пример сценария, в котором используется политика автоматического применения меток хранения с управляемыми свойствами в SharePoint и хранение на основе событий, чтобы начать период хранения, см. в статье [Управление жизненным циклом хранящихся в SharePoint документов с помощью меток хранения](auto-apply-retention-labels-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="d1f96-229">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply retention label policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
