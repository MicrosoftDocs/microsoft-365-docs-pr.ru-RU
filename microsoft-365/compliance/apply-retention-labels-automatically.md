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
description: Создавайте метки хранения и политики их автоматического применения, чтобы автоматически применять метки для сохранения необходимых сведений и удаления ненужных
ms.openlocfilehash: 6b7e8f91706a9d12135069f0a6753c76eaff1fb4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920022"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="0f009-103">Автоматическое применение метки хранения для сохранения или удаления контента</span><span class="sxs-lookup"><span data-stu-id="0f009-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="0f009-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="0f009-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="0f009-105">Этот сценарий не поддерживается для [нормативных записей](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="0f009-105">This scenario is not supported for [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="0f009-106">Одно из главных преимуществ [меток хранения](retention.md) — возможность автоматически их присваивать содержимому, которое соответствует определенным условиям.</span><span class="sxs-lookup"><span data-stu-id="0f009-106">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="0f009-107">В этом случае сотрудникам вашей организации не нужно будет самостоятельно присваивать метки хранения.</span><span class="sxs-lookup"><span data-stu-id="0f009-107">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="0f009-108">Microsoft 365 все сделает за них.</span><span class="sxs-lookup"><span data-stu-id="0f009-108">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="0f009-109">Польза автоматического присваивания меток хранения в том, что:</span><span class="sxs-lookup"><span data-stu-id="0f009-109">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="0f009-110">вам не придется обучать пользователей работе со всеми категориями;</span><span class="sxs-lookup"><span data-stu-id="0f009-110">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="0f009-111">вам не нужно будет рассчитывать на то, что пользователи правильно классифицируют весь контент;</span><span class="sxs-lookup"><span data-stu-id="0f009-111">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="0f009-112">пользователям больше не нужно будет знать о политиках управления данными — они могут сосредоточиться на своей работе.</span><span class="sxs-lookup"><span data-stu-id="0f009-112">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="0f009-113">Метки хранения можно автоматически применять к контенту, если он содержит конфиденциальную информацию, ключевые слова, доступные для поиска свойства или совпадение для [обучаемых классификаторов](classifier-get-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="0f009-113">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

> [!TIP]
> <span data-ttu-id="0f009-114">Теперь в предварительной версии с помощью свойств, по которым выполняется поиск, можно найти [записи собраний в Teams](#microsoft-teams-meeting-recordings).</span><span class="sxs-lookup"><span data-stu-id="0f009-114">Now in preview, use searchable properties to identify [Teams meeting recordings](#microsoft-teams-meeting-recordings).</span></span>

<span data-ttu-id="0f009-115">Процесс автоматического применения метки хранения основан на этих условиях:</span><span class="sxs-lookup"><span data-stu-id="0f009-115">The processes to automatically apply a retention label based on these conditions:</span></span>

![Схема ролей и задач для автоматически применяемых меток](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="0f009-117">Следуйте инструкциям ниже, чтобы выполнить два действия администратора.</span><span class="sxs-lookup"><span data-stu-id="0f009-117">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="0f009-118">Автоматические политики используют метки на стороне службы в условиях для автоматического применения меток хранения.</span><span class="sxs-lookup"><span data-stu-id="0f009-118">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="0f009-119">Также можно автоматически применить метку хранения с помощью политики меток, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="0f009-119">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="0f009-120">Применение метки хранения к модели осмысления документации в SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="0f009-120">Apply a retention label to a document understanding model in SharePoint Syntex</span></span>
> - <span data-ttu-id="0f009-121">Применение стандартной метки хранения для SharePoint и Outlook</span><span class="sxs-lookup"><span data-stu-id="0f009-121">Apply a default retention label for SharePoint and Outlook</span></span>
>- <span data-ttu-id="0f009-122">Применение метки хранения к сообщению электронной почты с помощью правил Outlook</span><span class="sxs-lookup"><span data-stu-id="0f009-122">Apply a retention label to email by using Outlook rules</span></span>
>
> <span data-ttu-id="0f009-123">Дополнительные сведения см. в статье [Создание и применение меток хранения в приложениях](create-apply-retention-labels.md)</span><span class="sxs-lookup"><span data-stu-id="0f009-123">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0f009-124">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="0f009-124">Before you begin</span></span>

<span data-ttu-id="0f009-125">Глобальный администратор организации имеет все разрешения на создание и изменение меток хранения и их политик.</span><span class="sxs-lookup"><span data-stu-id="0f009-125">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="0f009-126">Если вы входите не как глобальный администратор, см. раздел [Разрешения, необходимые для создания и управления политиками хранения и метками хранения](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="0f009-126">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="0f009-127">Автоматическое применение меток хранения</span><span class="sxs-lookup"><span data-stu-id="0f009-127">How to auto-apply a retention label</span></span>

<span data-ttu-id="0f009-128">Сначала создайте метку хранения.</span><span class="sxs-lookup"><span data-stu-id="0f009-128">First, create your retention label.</span></span> <span data-ttu-id="0f009-129">После этого создайте автоматическую политику для применения метки.</span><span class="sxs-lookup"><span data-stu-id="0f009-129">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="0f009-130">Если вы уже создали метку хранения, перейдите к [созданию автоматической политики](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="0f009-130">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="0f009-131">Инструкции по переходу зависят от того, используете ли вы [управление записями](records-management.md) или нет.</span><span class="sxs-lookup"><span data-stu-id="0f009-131">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="0f009-132">В обоих случаях доступны соответствующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="0f009-132">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="0f009-133">Этап 1. Создание метки хранения</span><span class="sxs-lookup"><span data-stu-id="0f009-133">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="0f009-134">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="0f009-134">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="0f009-135">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="0f009-135">If you are using records management:</span></span>
        - <span data-ttu-id="0f009-136">**Решения** > **Управление записями** > вкладка **План хранения** > **+ Создать метку** > **Метка хранения**</span><span class="sxs-lookup"><span data-stu-id="0f009-136">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="0f009-137">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="0f009-137">If you are not using records management:</span></span>
       - <span data-ttu-id="0f009-138">**Решения** > **Управление информацией** > вкладка **Метки** > + **Создать метку**</span><span class="sxs-lookup"><span data-stu-id="0f009-138">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="0f009-139">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="0f009-139">Don't immediately see your option?</span></span> <span data-ttu-id="0f009-140">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="0f009-140">First select **Show all**.</span></span> 

2. <span data-ttu-id="0f009-141">Следуйте указаниям мастера.</span><span class="sxs-lookup"><span data-stu-id="0f009-141">Follow the prompts in the wizard.</span></span> <span data-ttu-id="0f009-142">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="0f009-142">If you are using records management:</span></span>
    
    - <span data-ttu-id="0f009-143">Дополнительные сведения о дескрипторах плана хранения, см. в статье [Использование плана хранения для управления метками хранения](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="0f009-143">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="0f009-144">Чтобы использовать метку хранения для объявления элементов записями, нажмите кнопку **Пометить элементы как записи** или **Пометить элементы как нормативные записи**.</span><span class="sxs-lookup"><span data-stu-id="0f009-144">To use the retention label to declare records, select **Mark items as records**, or **Mark items as regulatory records**.</span></span> <span data-ttu-id="0f009-145">Дополнительные сведения см. в статье [Настройка меток хранения для объявления элементов записями](declare-records.md#configuring-retention-labels-to-declare-records)</span><span class="sxs-lookup"><span data-stu-id="0f009-145">For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="0f009-146">После того, как вы создали метку и просмотрели параметры для ее публикации, автоматически примените метку или просто сохраните ее: выберите пункт **Автоматически применять эту метку к определенному типу содержимого**, а затем выберите **Готово**, чтобы запустить Мастер автоматического создания меток, который сразу переведет вас к действию 2 в процедуре ниже.</span><span class="sxs-lookup"><span data-stu-id="0f009-146">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="0f009-147">Чтобы изменить существующую метку, выберите ее и нажмите **Изменить метку** для запуска Мастера изменения хранения, который позволяет изменить описания меток и любые [доступные параметры](#updating-retention-labels-and-their-policies) на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="0f009-147">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="0f009-148">Этап 2. Создание политики автоматического применения</span><span class="sxs-lookup"><span data-stu-id="0f009-148">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="0f009-149">При создании политики автоматического применения необходимо выбрать метку хранения, которая будет автоматически применена к содержимому на основе указанных условий.</span><span class="sxs-lookup"><span data-stu-id="0f009-149">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="0f009-150">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="0f009-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="0f009-151">Если используется управление записями: **Управление информацией**:</span><span class="sxs-lookup"><span data-stu-id="0f009-151">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="0f009-152">**Решения** > **Управление записями** >  вкладка **Политики метки** > **Автоматически применить метку**</span><span class="sxs-lookup"><span data-stu-id="0f009-152">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="0f009-153">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="0f009-153">If you are not using records management:</span></span>
        - <span data-ttu-id="0f009-154">**Решения** > **Управление информацией** >  вкладка **Политики меток** > **Автоматически применить метку**</span><span class="sxs-lookup"><span data-stu-id="0f009-154">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="0f009-155">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="0f009-155">Don't immediately see your option?</span></span> <span data-ttu-id="0f009-156">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="0f009-156">First select **Show all**.</span></span> 

2. <span data-ttu-id="0f009-157">Следуйте инструкциям в Мастере автоматического создания меток.</span><span class="sxs-lookup"><span data-stu-id="0f009-157">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="0f009-158">Сведения о настройке условий для автоматического применения метки хранения, см. в разделе [Настройка условий автоматического применения меток хранения](#configuring-conditions-for-auto-apply-retention-labels) на этой странице.</span><span class="sxs-lookup"><span data-stu-id="0f009-158">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="0f009-159">Сведения о расположениях, поддерживаемых метками хранения, см. в разделе [Метки хранения и расположения](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="0f009-159">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="0f009-160">Чтобы изменить существующую политику автоматического применения меток, выберите ее для запуска Мастера изменения политики хранения, который позволяет изменить выбранную метку хранения и [любые доступные параметры](#updating-retention-labels-and-their-policies) на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="0f009-160">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>

<span data-ttu-id="0f009-161">После применения метки к содержимому с помощью политики автоматического применения меток примененную метку нельзя автоматически удалить или изменить путем изменения содержимого или политики, а также посредством новой политики автоматического применения меток.</span><span class="sxs-lookup"><span data-stu-id="0f009-161">After content is labeled by using an auto-apply label policy, the applied label can't be automatically removed or changed by changing the content or the policy, or by a new auto-apply label policy.</span></span> <span data-ttu-id="0f009-162">Дополнительные сведения см. в разделе [Метки хранения присваиваются по одной](retention.md#only-one-retention-label-at-a-time).</span><span class="sxs-lookup"><span data-stu-id="0f009-162">For more information, see [Only one retention label at a time](retention.md#only-one-retention-label-at-a-time).</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="0f009-163">Настройка условий для автоматического применения меток хранения</span><span class="sxs-lookup"><span data-stu-id="0f009-163">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="0f009-164">Автоматически применяйте метки хранения к контенту, содержащему:</span><span class="sxs-lookup"><span data-stu-id="0f009-164">You can apply retention labels to content automatically when that content contains:</span></span>

- <span data-ttu-id="0f009-165">[конфиденциальную информацию определенных типов](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information);</span><span class="sxs-lookup"><span data-stu-id="0f009-165">[Specific types of sensitive information](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)</span></span>

- <span data-ttu-id="0f009-166">[определенные ключевые слова или доступные для поиска свойства, соответствующие созданному запросу](#auto-apply-labels-to-content-with-keywords-or-searchable-properties);</span><span class="sxs-lookup"><span data-stu-id="0f009-166">[Specific keywords or searchable properties that match a query you create](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)</span></span>

- <span data-ttu-id="0f009-167">[совпадение для обучаемых классификаторов](#auto-apply-labels-to-content-by-using-trainable-classifiers).</span><span class="sxs-lookup"><span data-stu-id="0f009-167">[A match for trainable classifiers](#auto-apply-labels-to-content-by-using-trainable-classifiers)</span></span>

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="0f009-168">Автоматическое применение меток к контенту с определенными типами конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="0f009-168">Auto-apply labels to content with specific types of sensitive information</span></span>

> [!WARNING]
> <span data-ttu-id="0f009-169">В этой конфигурации сейчас присутствует известное ограничение, из-за которого ко всем письмам без меток всегда применяется выбранная метка хранения, если для выбранных типов конфиденциальной информации есть соответствие.</span><span class="sxs-lookup"><span data-stu-id="0f009-169">This configuration currently has a known limitation where all unlabeled emails always have the selected retention label applied when there is a match for your chosen sensitive information types.</span></span> <span data-ttu-id="0f009-170">Например, даже если вы ограничили область политики автоматического применения определенными пользователями или выбрали расположения, отличные от Exchange, метка всегда применяется к письмам без меток при наличии соответствия.</span><span class="sxs-lookup"><span data-stu-id="0f009-170">For example, even if you scope your auto-apply policy to specific users, or select locations other than Exchange for the policy, the label is always applied to unlabeled emails when there is a match.</span></span>

<span data-ttu-id="0f009-171">Когда вы создаете политики автоматического применения меток хранения для конфиденциальной информации, вы видите тот же список шаблонов политик, что и при создании политики защиты от потери данных (DLP).</span><span class="sxs-lookup"><span data-stu-id="0f009-171">When you create auto-apply retention label policies for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="0f009-172">Каждый шаблон предварительно настроен на поиск определенных типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="0f009-172">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="0f009-173">Например, демонстрируемый здесь шаблон ищет номера ITIN, SSN и паспорта США в категории **Конфиденциальность** и в **шаблоне Персональных данных (PII) конечного пользователя для США**:</span><span class="sxs-lookup"><span data-stu-id="0f009-173">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data** template:</span></span>

![Шаблоны политик с типами конфиденциальной информации](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="0f009-175">Для получения дополнительной информации о типах конфиденциальной информации см. [Определения объектов типа конфиденциальной информации](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="0f009-175">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="0f009-176">Выбрав шаблон политики, вы можете добавлять или удалять любые типы конфиденциальной информации, а также менять количество и точность совпадений.</span><span class="sxs-lookup"><span data-stu-id="0f009-176">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="0f009-177">В примере на снимке экрана ниже показано, что метка хранения будет автоматически применяться только в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="0f009-177">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="0f009-178">Обнаруженный тип конфиденциальной информации имеет точность совпадения (уровень доверия) не менее 75.</span><span class="sxs-lookup"><span data-stu-id="0f009-178">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="0f009-179">Многие типы конфиденциальной информации определяются с использованием нескольких шаблонов, где для шаблона с более высокой точностью совпадения требуется больше подтверждающих признаков (например, ключевые слова, даты или адреса).</span><span class="sxs-lookup"><span data-stu-id="0f009-179">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="0f009-180">Чем меньше минимальное значение точности совпадения (**мин**), тем ниже требования, определяющие соответствие содержимого условию.</span><span class="sxs-lookup"><span data-stu-id="0f009-180">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="0f009-181">В содержимом от 1 до 9 раз встречается любой из перечисленных трех типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="0f009-181">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="0f009-182">Вы можете удалить **до значения**, таким образом оно будет изменено на **Любой**.</span><span class="sxs-lookup"><span data-stu-id="0f009-182">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="0f009-183">Дополнительные сведения об этих параметрах см. в следующих руководствах в документации по защите от потери данных [Настройка более или менее строгих правил](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="0f009-183">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Параметры определения типов конфиденциальной информации](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)

<span data-ttu-id="0f009-185">Сведения, которые необходимо учитывать при использовании типов конфиденциальной информации для автоматического применения меток хранения.</span><span class="sxs-lookup"><span data-stu-id="0f009-185">To consider when using sensitive information types to auto-apply retention labels:</span></span>

- <span data-ttu-id="0f009-186">Метки можно автоматически применять к новым и измененным элементам.</span><span class="sxs-lookup"><span data-stu-id="0f009-186">New and modified items can be auto-labeled.</span></span>

#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="0f009-187">Автоматическое применение меток к контенту с ключевыми словами или доступными для поиска свойствами</span><span class="sxs-lookup"><span data-stu-id="0f009-187">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="0f009-p116">Метки можно автоматически применять к контенту с помощью запроса, содержащего определенные слова, фразы или значения доступных для поиска свойств. Вы можете уточнить запрос с помощью таких операторов поиска, как AND, OR и NOT.</span><span class="sxs-lookup"><span data-stu-id="0f009-p116">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![Редактор запросов](../media/new-retention-query-editor.png)

<span data-ttu-id="0f009-191">Дополнительные сведения о синтаксисе языка запросов по ключевым словам (KQL) см. в статье [Справочник по синтаксису языка запросов по ключевым словам (KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="0f009-191">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="0f009-192">Для поиска содержимого политики автоматического применения на основе запросов используют тот же индекс поиска, что и средство обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="0f009-192">Query-based auto-apply policies use the same search index as eDiscovery content search to identify content.</span></span> <span data-ttu-id="0f009-193">Дополнительные сведения о доступных для поиска свойствах, которые можно использовать, см. в статье [Запросы с ключевыми словами и условия для поиска содержимого](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="0f009-193">For more information about the searchable properties that you can use, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

<span data-ttu-id="0f009-194">Сведения, которые необходимо учитывать при использовании ключевых слов или доступных для поиска свойств для автоматического применения меток хранения.</span><span class="sxs-lookup"><span data-stu-id="0f009-194">Some things to consider when using keywords or searchable properties to auto-apply retention labels:</span></span>

- <span data-ttu-id="0f009-195">Метки будут автоматически применяться к новым, измененным и существующим элементам в SharePoint, OneDrive и Exchange.</span><span class="sxs-lookup"><span data-stu-id="0f009-195">New, modified, and existing items will be auto-labeled for SharePoint, OneDrive, and Exchange.</span></span>

- <span data-ttu-id="0f009-196">В SharePoint свойства для обхода и настраиваемые свойства не поддерживаются для таких запросов по ключевым словам, поэтому необходимо использовать только предварительно настроенные управляемые свойства.</span><span class="sxs-lookup"><span data-stu-id="0f009-196">For SharePoint, crawled properties and custom properties aren't supported for these KQL queries and you must use only predefined managed properties.</span></span> <span data-ttu-id="0f009-197">Однако можно использовать сопоставления на уровне клиента с предварительно настроенными управляемыми свойствами, которые по умолчанию включены как уточнения (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09 и RefinableDouble00-09).</span><span class="sxs-lookup"><span data-stu-id="0f009-197">However, you can use mappings at the tenant level with the predefined managed properties that are enabled as refiners by default (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09, and RefinableDouble00-09).</span></span> <span data-ttu-id="0f009-198">Дополнительные сведения см. в статье [Обзор свойств для обхода и управляемых свойств в SharePoint Server](/SharePoint/technical-reference/crawled-and-managed-properties-overview) и [Создание нового управляемого свойства](/sharepoint/manage-search-schema#create-a-new-managed-property).</span><span class="sxs-lookup"><span data-stu-id="0f009-198">For more information, see [Overview of crawled and managed properties in SharePoint Server](/SharePoint/technical-reference/crawled-and-managed-properties-overview), and for instructions, see [Create a new managed property](/sharepoint/manage-search-schema#create-a-new-managed-property).</span></span>

- <span data-ttu-id="0f009-199">Если настраиваемое свойство сопоставляется с одним из свойств уточнения, подождите 24 часа, прежде чем использовать его в запросе по ключевым словам для метки хранения.</span><span class="sxs-lookup"><span data-stu-id="0f009-199">If you map a custom property to one of the refiner properties, wait 24 hours before you use it in your KQL query for a retention label.</span></span>

- <span data-ttu-id="0f009-200">Хотя управляемые свойства SharePoint можно переименовывать с помощью псевдонимов, не используйте их в запросах по ключевым словам для своих меток.</span><span class="sxs-lookup"><span data-stu-id="0f009-200">Although SharePoint managed properties can be renamed by using aliases, don't use these for KQL queries in your labels.</span></span> <span data-ttu-id="0f009-201">Всегда указывайте фактическое имя управляемого свойства, например "RefinableString01".</span><span class="sxs-lookup"><span data-stu-id="0f009-201">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

- <span data-ttu-id="0f009-202">При поиске значений, содержащих пробелы или специальные символы, заключайте фразу в двойные кавычки (`" "`). Например: `subject:"Financial Statements"`.</span><span class="sxs-lookup"><span data-stu-id="0f009-202">To search for values that contain spaces or special characters, use double quotation marks (`" "`) to contain the phrase; for example, `subject:"Financial Statements"`.</span></span>

- <span data-ttu-id="0f009-203">Для сопоставления элемента на основе его URL-адреса используйте свойство *DocumentLink*, а не *Path*.</span><span class="sxs-lookup"><span data-stu-id="0f009-203">Use the *DocumentLink* property instead of *Path* to match an item based on its URL.</span></span> 

- <span data-ttu-id="0f009-204">Поиск с подстановкой суффикса (`*cat`) или подстроки (`*cat*`) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0f009-204">Suffix wildcard searches ( such as `*cat`) or substring wildcard searches (such as `*cat*`) aren't supported.</span></span> <span data-ttu-id="0f009-205">Однако поиск с подстановкой префикса (`cat*`) поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0f009-205">However, prefix wildcard searches (such as `cat*`) are supported.</span></span>

- <span data-ttu-id="0f009-206">Необходимо учитывать, что при использовании оператора NOT частично индексированные элементы могут стать причиной того, что метки не будут применяться к нужным элементам или будут применяться к элементам, которые необходимо исключить.</span><span class="sxs-lookup"><span data-stu-id="0f009-206">Be aware that partially indexed items can be responsible for not labeling items that you're expecting, or labeling items that you're expecting to be excluded from labeling when you use the NOT operator.</span></span> <span data-ttu-id="0f009-207">Дополнительные сведения см. в статье [Частично индексированные элементы в средстве "Поиск содержимого"](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="0f009-207">For more information, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>


<span data-ttu-id="0f009-208">Примеры запросов:</span><span class="sxs-lookup"><span data-stu-id="0f009-208">Examples queries:</span></span>

| <span data-ttu-id="0f009-209">Рабочая нагрузка</span><span class="sxs-lookup"><span data-stu-id="0f009-209">Workload</span></span> | <span data-ttu-id="0f009-210">Пример</span><span class="sxs-lookup"><span data-stu-id="0f009-210">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="0f009-211">Exchange</span><span class="sxs-lookup"><span data-stu-id="0f009-211">Exchange</span></span>   | `subject:"Financial Statements"` |
|<span data-ttu-id="0f009-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="0f009-212">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="0f009-213">SharePoint</span><span class="sxs-lookup"><span data-stu-id="0f009-213">SharePoint</span></span> | `contenttype:document` |
|<span data-ttu-id="0f009-214">SharePoint</span><span class="sxs-lookup"><span data-stu-id="0f009-214">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:document`|
|<span data-ttu-id="0f009-215">Exchange или SharePoint</span><span class="sxs-lookup"><span data-stu-id="0f009-215">Exchange or SharePoint</span></span> | `"customer information" OR "private"`|

<span data-ttu-id="0f009-216">Более сложные примеры.</span><span class="sxs-lookup"><span data-stu-id="0f009-216">More complex examples:</span></span>

<span data-ttu-id="0f009-217">Приведенный ниже запрос для SharePoint позволяет обнаружить документы Word и электронные таблицы Excel, содержащие ключевые слова **password**, **passwords** или **pw**:</span><span class="sxs-lookup"><span data-stu-id="0f009-217">The following query for SharePoint identifies Word documents or Excel spreadsheets when those files contain the keywords **password**, **passwords**, or **pw**:</span></span>

```
(password OR passwords OR pw) AND (filetype:doc* OR filetype:xls*)
```

<span data-ttu-id="0f009-218">Приведенный ниже запрос для Exchange позволяет обнаружить документы Word или PDF-файлы, содержащие слово **nda** или фразу **non disclosure agreement**, если эти документы вложены в сообщение электронной почты:</span><span class="sxs-lookup"><span data-stu-id="0f009-218">The following query for Exchange identifies any Word document or PDF that contains the word **nda** or the phrase **non disclosure agreement** when those documents are attached to an email:</span></span>

```
(nda OR "non disclosure agreement") AND (attachmentnames:.doc* OR attachmentnames:.pdf)
```

<span data-ttu-id="0f009-219">Приведенный ниже запрос для SharePoint позволяет обнаружить документы, содержащие номера кредитных карт:</span><span class="sxs-lookup"><span data-stu-id="0f009-219">The following query for SharePoint identifies documents that contain a credit card number:</span></span> 

```
sensitivetype:"credit card number"
```

<span data-ttu-id="0f009-220">Приведенный ниже запрос содержит несколько типичных ключевых слов, которые позволяют обнаружить документы или сообщения электронной почты, содержащие правовую информацию:</span><span class="sxs-lookup"><span data-stu-id="0f009-220">The following query contains some typical keywords to help identify documents or emails that contain legal content:</span></span>

```
ACP OR (Attorney Client Privilege*) OR (AC Privilege)
```

<span data-ttu-id="0f009-221">Приведенный ниже запрос содержит типичные ключевые слова, позволяющие обнаружить документы или сообщения электронной почты для специалистов отдела кадров:</span><span class="sxs-lookup"><span data-stu-id="0f009-221">The following query contains typical keywords to help identify documents or emails for human resources:</span></span> 

```
(resume AND staff AND employee AND salary AND recruitment AND candidate)
```

<span data-ttu-id="0f009-222">Обратите внимание, что в последнем примере используется  лучший метод, предусматривающий постоянное применение операторов между ключевыми словами.</span><span class="sxs-lookup"><span data-stu-id="0f009-222">Note that this final example uses the best practice of always including  operators between keywords.</span></span> <span data-ttu-id="0f009-223">Пробел между двумя ключевыми словами или двумя выражениями свойство:значение аналогичен оператору AND.</span><span class="sxs-lookup"><span data-stu-id="0f009-223">A space between keywords (or two property:value expressions) is the same as using AND.</span></span> <span data-ttu-id="0f009-224">Постоянное применение операторов позволяет понять, что для этого примера запроса будет найдено содержимое, включающее все эти ключевые слова, а не какое-либо из этих ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="0f009-224">By always adding operators, it's easier to see that this example query will identify only content that contains all these keywords, instead of content that contains any of the keywords.</span></span> <span data-ttu-id="0f009-225">Если нужно найти содержимое, включающее любое ключевое слово, укажите OR вместо AND.</span><span class="sxs-lookup"><span data-stu-id="0f009-225">If your intention is to identify content that contains any of the keywords, specify OR instead of AND.</span></span> <span data-ttu-id="0f009-226">Как показано в этом примере, при постоянном использовании операторов легче правильно интерпретировать запрос.</span><span class="sxs-lookup"><span data-stu-id="0f009-226">As this example shows, when you always specify the operators, it's easier to correctly interpret the query.</span></span> 

##### <a name="microsoft-teams-meeting-recordings"></a><span data-ttu-id="0f009-227">Записи собраний в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0f009-227">Microsoft Teams meeting recordings</span></span>

> [!NOTE]
> <span data-ttu-id="0f009-228">Функция хранения и удаления записей собраний в Teams доступна в предварительной версии и не работает до сохранения записей в OneDrive или SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0f009-228">The ability to retain and delete Teams meeting recordings is in preview and won't work before recordings are saved to OneDrive or SharePoint.</span></span> <span data-ttu-id="0f009-229">Дополнительные сведения см. в статье [Использование OneDrive для бизнеса, SharePoint или Stream для записи собраний](/MicrosoftTeams/tmr-meeting-recording-change)</span><span class="sxs-lookup"><span data-stu-id="0f009-229">For more information, see [Use OneDrive for Business and SharePoint Online or Stream for meeting recordings](/MicrosoftTeams/tmr-meeting-recording-change).</span></span>

<span data-ttu-id="0f009-230">Для поиска записей собраний в Microsoft Teams, хранящихся в пользовательских учетных записях OneDrive или SharePoint, укажите для **редактора запросов по ключевым словам** следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="0f009-230">To identify Microsoft Teams meeting recordings that are stored in users' OneDrive accounts or in SharePoint, specify the following for the **Keyword query editor**:</span></span>

``` 
ProgID:Media AND ProgID:Meeting
```

<span data-ttu-id="0f009-231">В большинстве случаев записи собраний сохраняются в OneDrive.</span><span class="sxs-lookup"><span data-stu-id="0f009-231">Most of the time, meeting recordings are saved to OneDrive.</span></span> <span data-ttu-id="0f009-232">Но для собраний канала они сохраняются в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0f009-232">But for channel meetings, they are saved in SharePoint.</span></span>


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="0f009-233">Автоматическое применение меток к контенту с помощью обучаемых классификаторов</span><span class="sxs-lookup"><span data-stu-id="0f009-233">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="0f009-234">При использовании варианта для обучаемого классификатора вы можете выбрать один из встроенных классификаторов или настраиваемый классификатор.</span><span class="sxs-lookup"><span data-stu-id="0f009-234">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="0f009-235">К встроенным классификаторам относятся **Резюме**, **Исходный код**, **Целенаправленное притеснение**, **Сквернословие** и **Угрозы**.</span><span class="sxs-lookup"><span data-stu-id="0f009-235">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Выбор обучаемого классификатора](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="0f009-237">Мы не рекомендуем использовать встроенный классификатор **Оскорбительная лексика**, так как он генерировал большое количество ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="0f009-237">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="0f009-238">Не используйте этот встроенный классификатор, а если вы применяете его в настоящее время, следует перенести с него свои бизнес-процессы.</span><span class="sxs-lookup"><span data-stu-id="0f009-238">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="0f009-239">Вместо него рекомендуем использовать встроенные классификаторы **Целенаправленное притеснение**, **Сквернословие** и **Угрозы**.</span><span class="sxs-lookup"><span data-stu-id="0f009-239">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="0f009-240">Для автоматического применения метки с использованием этого параметра сайты SharePoint и почтовые ящики должны иметь не менее 10 МБ данных.</span><span class="sxs-lookup"><span data-stu-id="0f009-240">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="0f009-241">Дополнительные сведения об обучаемых классификаторах см. в статье [Информация об обучаемых классификаторах](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="0f009-241">For more information about trainable classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="0f009-242">Если вы используете обучаемые классификаторы для Exchange, см. статью [Повторное обучение классификаторов в обозревателе содержимого](classifier-how-to-retrain-content-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="0f009-242">If you use trainable classifiers for Exchange, see [How to retrain a classifier in content explorer](classifier-how-to-retrain-content-explorer.md).</span></span>

<span data-ttu-id="0f009-243">Сведения, которые необходимо учитывать при использовании обучаемых классификаторов для автоматического применения меток хранения.</span><span class="sxs-lookup"><span data-stu-id="0f009-243">To consider when using trainable classifiers to auto-apply retention labels:</span></span>

- <span data-ttu-id="0f009-244">Метки можно автоматически применять к новым и измененным элементам, а также к существующим элементам за последние шесть месяцев.</span><span class="sxs-lookup"><span data-stu-id="0f009-244">New and modified items can be auto-labeled, and existing items from the last six months.</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="0f009-245">Срок вступления меток хранения в силу</span><span class="sxs-lookup"><span data-stu-id="0f009-245">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="0f009-246">Когда метки хранения применяются автоматически, может потребоваться до семи дней, чтобы метки хранения были применены ко всему существующему контенту, соответствующему условиям.</span><span class="sxs-lookup"><span data-stu-id="0f009-246">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Схема, иллюстрирующая, когда автоматически применяемые метки вступают в силу](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

<span data-ttu-id="0f009-248">Если после семи дней ожидаемые метки не появляются, проверьте **Состояние** политики автоматического применения, выбрав ее на странице **Политики меток** в Центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="0f009-248">If the expected labels don't appear after seven days, check the **Status** of the auto-apply policy by selecting it from the **Label policies** page in the compliance center.</span></span> <span data-ttu-id="0f009-249">Для повторного развертывания политики (для OneDrive) или если отображается состояние **Отключено (ошибка)**, а в сведениях расположений выводится сообщение о том, что развертывание политики (для SharePoint) занимает больше времени, чем ожидалось, попробуйте выполнить команду [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) в PowerShell, чтобы повторно распространить политику:</span><span class="sxs-lookup"><span data-stu-id="0f009-249">If you see the status of **Off (Error)** and in the details for the locations see a message that it's taking longer than expected to deploy the policy (for SharePoint) or to try redeploying the policy (for OneDrive), try running the [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell command to retry the policy distribution:</span></span>

1. <span data-ttu-id="0f009-250">[Подключение к Центру безопасности и соответствия требованиям Windows PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="0f009-250">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="0f009-251">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0f009-251">Run the following command:</span></span>
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="0f009-252">Обновление меток хранения и их политик</span><span class="sxs-lookup"><span data-stu-id="0f009-252">Updating retention labels and their policies</span></span>

<span data-ttu-id="0f009-253">При изменении меток хранения или политики авто-применения, когда метка хранения уже применена к контенту, ваши обновленные параметры автоматически применяются к этому контенту, в дополнение к уже определенному.</span><span class="sxs-lookup"><span data-stu-id="0f009-253">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="0f009-254">Некоторые параметры невозможно изменить после создания и сохранения метки или политики, в том числе:</span><span class="sxs-lookup"><span data-stu-id="0f009-254">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="0f009-255">Имя метки хранения и имя политики, а также параметры хранения, за исключением периода хранения.</span><span class="sxs-lookup"><span data-stu-id="0f009-255">The retention label and policy name, and the retention settings except the retention period.</span></span> <span data-ttu-id="0f009-256">Однако если период хранения основан на времени применения метки к элементам, его изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="0f009-256">However, you can't change the retention period when the retention period is based on when items were labeled.</span></span>
- <span data-ttu-id="0f009-257">Параметр, помечающий элементы как запись.</span><span class="sxs-lookup"><span data-stu-id="0f009-257">The option to mark items as a record.</span></span>

### <a name="deleting-retention-labels"></a><span data-ttu-id="0f009-258">Удаление меток хранения</span><span class="sxs-lookup"><span data-stu-id="0f009-258">Deleting retention labels</span></span>

<span data-ttu-id="0f009-259">Вы можете удалить метки хранения, которые в настоящее время не включены ни в одну политику меток хранения, которые не настроены на хранение на основе событий или помечают элементы как нормативные записи.</span><span class="sxs-lookup"><span data-stu-id="0f009-259">You can delete retention labels that aren't currently included in any retention label policies, that aren't configured for event-based retention, or mark items as regulatory records.</span></span> <span data-ttu-id="0f009-260">Возможность удаления меток хранения, которые помечают элементы как записи, в настоящее время развертывается в предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="0f009-260">The ability to delete retention labels that mark items as records is currently rolling out in preview.</span></span>

<span data-ttu-id="0f009-261">Для меток хранения, которые вы можете удалить, если они были применены к элементам, удаление не будет выполнено,а вы увидите ссылку на обозреватель содержимого для идентификации помеченных элементов.</span><span class="sxs-lookup"><span data-stu-id="0f009-261">For retention labels that you can delete, if they have been applied to items, the deletion fails and you see a link to content explorer to identify the labeled items.</span></span>

<span data-ttu-id="0f009-262">Однако отображение помеченных элементов в обозревателе содержимого может занять до двух дней.</span><span class="sxs-lookup"><span data-stu-id="0f009-262">However, it can take up to two days for content explorer to show the items that are labeled.</span></span> <span data-ttu-id="0f009-263">В этом сценарии возможно удаление метки хранения без отображения ссылки на обозреватель содержимого.</span><span class="sxs-lookup"><span data-stu-id="0f009-263">In this scenario, the retention label might be deleted without showing you the link to content explorer.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="0f009-264">Блокировка политики для предотвращения изменений</span><span class="sxs-lookup"><span data-stu-id="0f009-264">Locking the policy to prevent changes</span></span>

<span data-ttu-id="0f009-265">Чтобы гарантировать, что никто не сможет отключить политику, удалить ее или сделать ее менее строгой, см. раздел [Использование блокировки для сохранения для ограничения изменений политик хранения и политик меток хранения](retention-preservation-lock.md).</span><span class="sxs-lookup"><span data-stu-id="0f009-265">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0f009-266">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="0f009-266">Next steps</span></span>

<span data-ttu-id="0f009-267">Пример сценария, в котором используется политика автоматического применения меток хранения с управляемыми свойствами в SharePoint и хранение на основе событий, чтобы начать период хранения, см. в статье [Управление жизненным циклом хранящихся в SharePoint документов с помощью меток хранения](auto-apply-retention-labels-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="0f009-267">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply retention label policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>