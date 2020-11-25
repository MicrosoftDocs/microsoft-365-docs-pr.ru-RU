---
title: Автоматическое применение меток хранения для сохранения или удаления содержимого
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
ms.openlocfilehash: ebfd088dd6dc3205f02e563e31f6fb25372608ad
ms.sourcegitcommit: 26b35012c42fef935d6c4a6509dde6c22a9b922a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2020
ms.locfileid: "49385265"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="7a269-103">Автоматическое применение меток хранения для сохранения или удаления содержимого</span><span class="sxs-lookup"><span data-stu-id="7a269-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="7a269-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="7a269-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

> [!NOTE]
> <span data-ttu-id="7a269-105">Этот сценарий не поддерживается для [нормативных записей](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="7a269-105">This scenario is not supported for [regulatory records](records-management.md#records).</span></span>

<span data-ttu-id="7a269-p101">Одно из главных преимуществ [меток хранения](retention.md) — возможность автоматически применять их к содержимому, соответствующему определенным условиям. В этом случае пользователям в организации не требуется применять метки хранения — Microsoft 365 делает это за них.</span><span class="sxs-lookup"><span data-stu-id="7a269-p101">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions. In this case, people in your organization don't need to apply the retention labels. Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="7a269-109">Преимущества автоматического применения меток хранения:</span><span class="sxs-lookup"><span data-stu-id="7a269-109">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="7a269-110">вам не придется обучать пользователей работе со всеми категориями;</span><span class="sxs-lookup"><span data-stu-id="7a269-110">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="7a269-111">вам не нужно будет рассчитывать на то, что пользователи правильно классифицируют весь контент;</span><span class="sxs-lookup"><span data-stu-id="7a269-111">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="7a269-112">пользователям больше не нужно будет знать о политиках управления данными — они могут сосредоточиться на своей работе.</span><span class="sxs-lookup"><span data-stu-id="7a269-112">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="7a269-113">Метки хранения можно автоматически применять к контенту, если он содержит конфиденциальную информацию, ключевые слова, доступные для поиска свойства или совпадение для [обучаемых классификаторов](classifier-get-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="7a269-113">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-get-started-with.md).</span></span>

> [!TIP]
> <span data-ttu-id="7a269-114">Теперь в предварительной версии с помощью свойств, по которым выполняется поиск, можно найти [записи собраний в Teams](#microsoft-teams-meeting-recordings).</span><span class="sxs-lookup"><span data-stu-id="7a269-114">Now in preview, use searchable properties to identify [Teams meeting recordings](#microsoft-teams-meeting-recordings).</span></span>

<span data-ttu-id="7a269-115">Процесс автоматического применения метки хранения основан на этих условиях:</span><span class="sxs-lookup"><span data-stu-id="7a269-115">The processes to automatically apply a retention label based on these conditions:</span></span>

![Схема ролей и задач для автоматически применяемых меток](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="7a269-117">Следуйте инструкциям ниже, чтобы выполнить два действия администратора.</span><span class="sxs-lookup"><span data-stu-id="7a269-117">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="7a269-p102">Автоматические политики используют метки на стороне службы в условиях для автоматического применения меток хранения. Также можно автоматически применить метку хранения с помощью политики меток, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="7a269-p102">Auto-policies use service-side labeling with conditions to automatically apply retention labels. You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="7a269-120">Применение метки хранения по умолчанию к библиотеке SharePoint, папке или набору документов таким образом, чтобы содержимое без меток помечалось автоматически</span><span class="sxs-lookup"><span data-stu-id="7a269-120">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="7a269-121">Автоматическое применение метки хранения к электронному сообщению с помощью правил</span><span class="sxs-lookup"><span data-stu-id="7a269-121">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="7a269-122">Дополнительные сведения см. в статье [Создание и применение меток хранения в приложениях](create-apply-retention-labels.md)</span><span class="sxs-lookup"><span data-stu-id="7a269-122">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7a269-123">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="7a269-123">Before you begin</span></span>

<span data-ttu-id="7a269-p103">Глобальный администратор организации имеет все разрешения на создание и изменение меток хранения и их политик. Если вы входите не как глобальный администратор, см. раздел [Разрешения, необходимые для создания и управления политиками хранения и метками хранения](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="7a269-p103">The global admin for your organization has full permissions to create and edit retention labels and their policies. If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="7a269-126">Автоматическое применение меток хранения</span><span class="sxs-lookup"><span data-stu-id="7a269-126">How to auto-apply a retention label</span></span>

<span data-ttu-id="7a269-p104">Сначала создайте метку хранения. После этого создайте автоматическую политику для применения метки. Если вы уже создали метку хранения, перейдите к [созданию автоматической политики](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="7a269-p104">First, create your retention label. Then create an auto-policy to apply that label. If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="7a269-p105">Инструкции по переходу зависят от того, используете ли вы [управление записями](records-management.md) или нет. В обоих случаях доступны соответствующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="7a269-p105">Navigation instructions depend on whether you're using [records management](records-management.md) or not. Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="7a269-132">Этап 1. Создание метки хранения</span><span class="sxs-lookup"><span data-stu-id="7a269-132">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="7a269-133">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="7a269-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="7a269-134">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="7a269-134">If you are using records management:</span></span>
        - <span data-ttu-id="7a269-135">**Решения** > **Управление записями** > вкладка **План хранения** > **+ Создать метку** > **Метка хранения**</span><span class="sxs-lookup"><span data-stu-id="7a269-135">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="7a269-136">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="7a269-136">If you are not using records management:</span></span>
       - <span data-ttu-id="7a269-137">**Решения** > **Управление информацией** > вкладка **Метки** > + **Создать метку**</span><span class="sxs-lookup"><span data-stu-id="7a269-137">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="7a269-p106">Не отображается необходимый параметр? Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="7a269-p106">Don't immediately see your option? First select **Show all**.</span></span> 

2. <span data-ttu-id="7a269-p107">Следуйте указаниям мастера. Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="7a269-p107">Follow the prompts in the wizard. If you are using records management:</span></span>
    
    - <span data-ttu-id="7a269-142">Дополнительные сведения о дескрипторах плана хранения, см. в статье [Использование плана хранения для управления метками хранения](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="7a269-142">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="7a269-p108">Чтобы использовать метку хранения для объявления элементов записями, нажмите кнопку **Пометить элементы как записи** или **Пометить элементы как нормативные записи**. Дополнительные сведения см. в статье [Настройка меток хранения для объявления элементов записями](declare-records.md#configuring-retention-labels-to-declare-records).</span><span class="sxs-lookup"><span data-stu-id="7a269-p108">To use the retention label to declare records, select **Mark items as records**, or **Mark items as regulatory records**. For more information, see [Configuring retention labels to declare records](declare-records.md#configuring-retention-labels-to-declare-records).</span></span>

3. <span data-ttu-id="7a269-145">После создания метки отобразятся параметры для ее публикации, автоматического применения или сохранения. Выберите пункт **Автоматически применять эту метку к определенному типу содержимого**, а затем выберите **Готово**, чтобы запустить Мастер автоматического создания меток, который сразу направит вас к действию 2 в процедуре ниже.</span><span class="sxs-lookup"><span data-stu-id="7a269-145">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="7a269-146">Чтобы изменить существующую метку, выберите ее и нажмите **Изменить метку** для запуска Мастера изменения хранения, который позволяет изменить описания меток и любые [доступные параметры](#updating-retention-labels-and-their-policies) на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="7a269-146">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="7a269-147">Этап 2. Создание политики автоматического применения</span><span class="sxs-lookup"><span data-stu-id="7a269-147">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="7a269-148">При создании политики автоматического применения необходимо выбрать метку хранения, которая будет автоматически применена к содержимому на основе указанных условий.</span><span class="sxs-lookup"><span data-stu-id="7a269-148">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="7a269-149">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="7a269-149">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="7a269-150">Если используется управление записями: **Управление информацией**:</span><span class="sxs-lookup"><span data-stu-id="7a269-150">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="7a269-151">**Решения** > **Управление записями** >  вкладка **Политики метки** > **Автоматически применить метку**</span><span class="sxs-lookup"><span data-stu-id="7a269-151">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="7a269-152">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="7a269-152">If you are not using records management:</span></span>
        - <span data-ttu-id="7a269-153">**Решения** > **Управление информацией** >  вкладка **Политики меток** > **Автоматически применить метку**</span><span class="sxs-lookup"><span data-stu-id="7a269-153">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="7a269-p109">Не отображается необходимый параметр? Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="7a269-p109">Don't immediately see your option? First select **Show all**.</span></span> 

2. <span data-ttu-id="7a269-156">Следуйте инструкциям в Мастере автоматического создания меток.</span><span class="sxs-lookup"><span data-stu-id="7a269-156">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="7a269-157">Сведения о настройке условий для автоматического применения метки хранения, см. в разделе [Настройка условий автоматического применения меток хранения](#configuring-conditions-for-auto-apply-retention-labels) на этой странице.</span><span class="sxs-lookup"><span data-stu-id="7a269-157">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="7a269-158">Сведения о расположениях, поддерживаемых метками хранения, см. в разделе [Метки хранения и расположения](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="7a269-158">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="7a269-159">Чтобы изменить существующую политику автоматического применения меток, выберите ее для запуска Мастера изменения политики хранения, который позволяет изменить выбранную метку хранения и [любые доступные параметры](#updating-retention-labels-and-their-policies) на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="7a269-159">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="7a269-160">Настройка условий для автоматического применения меток хранения</span><span class="sxs-lookup"><span data-stu-id="7a269-160">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="7a269-161">Автоматически применяйте метки хранения к контенту, содержащему:</span><span class="sxs-lookup"><span data-stu-id="7a269-161">You can apply retention labels to content automatically when that content contains:</span></span>

- <span data-ttu-id="7a269-162">[конфиденциальную информацию определенных типов](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information);</span><span class="sxs-lookup"><span data-stu-id="7a269-162">[Specific types of sensitive information](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)</span></span>

- <span data-ttu-id="7a269-163">[определенные ключевые слова или доступные для поиска свойства, соответствующие созданному запросу](#auto-apply-labels-to-content-with-keywords-or-searchable-properties);</span><span class="sxs-lookup"><span data-stu-id="7a269-163">[Specific keywords or searchable properties that match a query you create](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)</span></span>

- <span data-ttu-id="7a269-164">[совпадение для обучаемых классификаторов](#auto-apply-labels-to-content-by-using-trainable-classifiers).</span><span class="sxs-lookup"><span data-stu-id="7a269-164">[A match for trainable classifiers](#auto-apply-labels-to-content-by-using-trainable-classifiers)</span></span>

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="7a269-165">Автоматическое применение меток к содержимому с определенными типами конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="7a269-165">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="7a269-p110">При создании политик автоматического применения меток хранения для конфиденциальной информации отображается тот же список шаблонов политик, что и при создании политики защиты от потери данных (DLP). Каждый шаблон предварительно настроен для поиска определенных типов конфиденциальной информации. Например, приводимый ниже шаблон ищет индивидуальные идентификационные номера налогоплательщиков, номера социального страхования и номера паспортов граждан США в категории **Конфиденциальность** и в **шаблоне персональных данных (PII) конечного пользователя США**:</span><span class="sxs-lookup"><span data-stu-id="7a269-p110">When you create auto-apply retention label policies for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy. Each template is preconfigured to look for specific types of sensitive information. For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template**:</span></span>

![Шаблоны политик с типами конфиденциальной информации](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="7a269-170">Дополнительные сведения о типах конфиденциальной информации см. в статье [Определения типов конфиденциальной информации](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="7a269-170">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="7a269-p111">После выбора шаблона политики можно добавлять или удалять любые типы конфиденциальной информации, а также менять количество экземпляров и точность совпадения. В приведенном ниже примере метка хранения будет автоматически применяться, только если:</span><span class="sxs-lookup"><span data-stu-id="7a269-p111">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="7a269-p112">для определяемого типа конфиденциальной информации задана точность совпадения (или уровень надежности) не менее 75. Для многих типов конфиденциальной информации определяется несколько шаблонов. Чем выше точность совпадения, тем больше признаков (например, ключевых слов, дат или адресов) нужно для обнаружения шаблона. Чем ниже **минимальная** точность совпадения, тем проще сопоставить контент с условием;</span><span class="sxs-lookup"><span data-stu-id="7a269-p112">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="7a269-p113">контент содержит от 1 до 9 примеров любого из этих трех типов конфиденциальной информации. Вы можете удалить значение **до**, изменив его на **любое**.</span><span class="sxs-lookup"><span data-stu-id="7a269-p113">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="7a269-178">Дополнительные сведения об этих параметрах см. в следующем руководстве в документации по защите от потери данных [Настройка более или менее строгих правил](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="7a269-178">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Параметры определения типов конфиденциальной информации](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)

<span data-ttu-id="7a269-180">Сведения, которые необходимо учитывать при использовании типов конфиденциальной информации для автоматического применения меток хранения.</span><span class="sxs-lookup"><span data-stu-id="7a269-180">To consider when using sensitive information types to auto-apply retention labels:</span></span>

- <span data-ttu-id="7a269-181">Метки можно автоматически применять к новым и измененным элементам.</span><span class="sxs-lookup"><span data-stu-id="7a269-181">New and modified items can be auto-labeled.</span></span>

#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="7a269-182">Автоматическое применение меток к содержимому с ключевыми словами или доступными для поиска свойствами</span><span class="sxs-lookup"><span data-stu-id="7a269-182">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="7a269-p114">Метки можно автоматически применять к контенту с помощью запроса, содержащего определенные слова, фразы или значения доступных для поиска свойств. Вы можете уточнить запрос с помощью таких операторов поиска, как AND, OR и NOT.</span><span class="sxs-lookup"><span data-stu-id="7a269-p114">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![Редактор запросов](../media/new-retention-query-editor.png)

<span data-ttu-id="7a269-186">Дополнительные сведения о синтаксисе языка запросов по ключевым словам (KQL) см. в статье [Справочник по синтаксису языка запросов по ключевым словам (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="7a269-186">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="7a269-187">Для поиска содержимого политики автоматического применения на основе запросов используют тот же индекс поиска, что и средство обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="7a269-187">Query-based auto-apply policies use the same search index as eDiscovery content search to identify content.</span></span> <span data-ttu-id="7a269-188">Дополнительные сведения о доступных для поиска свойствах, которые можно использовать, см. в статье [Запросы с ключевыми словами и условия для поиска содержимого](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="7a269-188">For more information about the searchable properties that you can use, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

<span data-ttu-id="7a269-189">Сведения, которые необходимо учитывать при использовании ключевых слов или доступных для поиска свойств для автоматического применения меток хранения.</span><span class="sxs-lookup"><span data-stu-id="7a269-189">Some things to consider when using keywords or searchable properties to auto-apply retention labels:</span></span>

- <span data-ttu-id="7a269-190">Метки будут автоматически применяться к новым, измененным и существующим элементам в SharePoint, OneDrive и Exchange.</span><span class="sxs-lookup"><span data-stu-id="7a269-190">New, modified, and existing items will be auto-labeled for SharePoint, OneDrive, and Exchange.</span></span>

- <span data-ttu-id="7a269-191">В SharePoint свойства для обхода и настраиваемые свойства не поддерживаются для таких запросов по ключевым словам, поэтому необходимо использовать только предварительно настроенные управляемые свойства.</span><span class="sxs-lookup"><span data-stu-id="7a269-191">For SharePoint, crawled properties and custom properties aren't supported for these KQL queries and you must use only predefined managed properties.</span></span> <span data-ttu-id="7a269-192">Однако можно использовать сопоставления на уровне клиента с предварительно настроенными управляемыми свойствами, которые по умолчанию включены как уточнения (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09 и RefinableDouble00-09).</span><span class="sxs-lookup"><span data-stu-id="7a269-192">However, you can use mappings at the tenant level with the predefined managed properties that are enabled as refiners by default (RefinableDate00-19, RefinableString00-99, RefinableInt00-49, RefinableDecimals00-09, and RefinableDouble00-09).</span></span> <span data-ttu-id="7a269-193">Дополнительные сведения см. в статье [Обзор свойств для обхода и управляемых свойств в SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview) и [Создание нового управляемого свойства](https://docs.microsoft.com/sharepoint/manage-search-schema#create-a-new-managed-property).</span><span class="sxs-lookup"><span data-stu-id="7a269-193">For more information, see [Overview of crawled and managed properties in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview), and for instructions, see [Create a new managed property](https://docs.microsoft.com/sharepoint/manage-search-schema#create-a-new-managed-property).</span></span>

- <span data-ttu-id="7a269-194">Если настраиваемое свойство сопоставляется с одним из свойств уточнения, подождите 24 часа, прежде чем использовать его в запросе по ключевым словам для метки хранения.</span><span class="sxs-lookup"><span data-stu-id="7a269-194">If you map a custom property to one of the refiner properties, wait 24 hours before you use it in your KQL query for a retention label.</span></span>

- <span data-ttu-id="7a269-195">Хотя управляемые свойства SharePoint можно переименовывать с помощью псевдонимов, не используйте их в запросах по ключевым словам для своих меток.</span><span class="sxs-lookup"><span data-stu-id="7a269-195">Although SharePoint managed properties can be renamed by using aliases, don't use these for KQL queries in your labels.</span></span> <span data-ttu-id="7a269-196">Всегда указывайте фактическое имя управляемого свойства, например "RefinableString01".</span><span class="sxs-lookup"><span data-stu-id="7a269-196">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

- <span data-ttu-id="7a269-197">При поиске значений, содержащих пробелы или специальные символы, заключайте фразу в двойные кавычки (`" "`). Например: `subject:"Financial Statements"`.</span><span class="sxs-lookup"><span data-stu-id="7a269-197">To search for values that contain spaces or special characters, use double quotation marks (`" "`) to contain the phrase; for example, `subject:"Financial Statements"`.</span></span>

- <span data-ttu-id="7a269-198">Для сопоставления элемента на основе его URL-адреса используйте свойство *DocumentLink*, а не *Path*.</span><span class="sxs-lookup"><span data-stu-id="7a269-198">Use the *DocumentLink* property instead of *Path* to match an item based on its URL.</span></span> 

- <span data-ttu-id="7a269-199">Поиск с подстановкой суффикса (`*cat`) или подстроки (`*cat*`) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="7a269-199">Suffix wildcard searches ( such as `*cat`) or substring wildcard searches (such as `*cat*`) aren't supported.</span></span> <span data-ttu-id="7a269-200">Однако поиск с подстановкой префикса (`cat*`) поддерживается.</span><span class="sxs-lookup"><span data-stu-id="7a269-200">However, prefix wildcard searches (such as `cat*`) are supported.</span></span>

- <span data-ttu-id="7a269-201">Необходимо учитывать, что при использовании оператора NOT частично индексированные элементы могут стать причиной того, что метки не будут применяться к нужным элементам или будут применяться к элементам, которые необходимо исключить.</span><span class="sxs-lookup"><span data-stu-id="7a269-201">Be aware that partially indexed items can be responsible for not labeling items that you're expecting, or labeling items that you're expecting to be excluded from labeling when you use the NOT operator.</span></span> <span data-ttu-id="7a269-202">Дополнительные сведения см. в статье [Частично индексированные элементы в средстве "Поиск содержимого"](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="7a269-202">For more information, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>


<span data-ttu-id="7a269-203">Примеры запросов:</span><span class="sxs-lookup"><span data-stu-id="7a269-203">Examples queries:</span></span>

| <span data-ttu-id="7a269-204">Рабочая нагрузка</span><span class="sxs-lookup"><span data-stu-id="7a269-204">Workload</span></span> | <span data-ttu-id="7a269-205">Пример</span><span class="sxs-lookup"><span data-stu-id="7a269-205">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="7a269-206">Exchange</span><span class="sxs-lookup"><span data-stu-id="7a269-206">Exchange</span></span>   | `subject:"Financial Statements"` |
|<span data-ttu-id="7a269-207">Exchange</span><span class="sxs-lookup"><span data-stu-id="7a269-207">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="7a269-208">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7a269-208">SharePoint</span></span> | `contenttype:document` |
|<span data-ttu-id="7a269-209">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7a269-209">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:document`|
|<span data-ttu-id="7a269-210">Exchange или SharePoint</span><span class="sxs-lookup"><span data-stu-id="7a269-210">Exchange or SharePoint</span></span> | `"customer information" OR "private"`|

<span data-ttu-id="7a269-211">Более сложные примеры.</span><span class="sxs-lookup"><span data-stu-id="7a269-211">More complex examples:</span></span>

<span data-ttu-id="7a269-212">Приведенный ниже запрос для SharePoint позволяет обнаружить документы Word и электронные таблицы Excel, содержащие ключевые слова **password**, **passwords** или **pw**:</span><span class="sxs-lookup"><span data-stu-id="7a269-212">The following query for SharePoint identifies Word documents or Excel spreadsheets when those files contain the keywords **password**, **passwords**, or **pw**:</span></span>

```
(password OR passwords OR pw) AND (filetype:doc* OR filetype:xls*)
```

<span data-ttu-id="7a269-213">Приведенный ниже запрос для Exchange позволяет обнаружить документы Word или PDF-файлы, содержащие слово **nda** или фразу **non disclosure agreement**, если эти документы вложены в сообщение электронной почты:</span><span class="sxs-lookup"><span data-stu-id="7a269-213">The following query for Exchange identifies any Word document or PDF that contains the word **nda** or the phrase **non disclosure agreement** when those documents are attached to an email:</span></span>

```
(nda OR "non disclosure agreement") AND (attachmentnames:.doc* OR attachmentnames:.pdf)
```

<span data-ttu-id="7a269-214">Приведенный ниже запрос для SharePoint позволяет обнаружить документы, содержащие номера кредитных карт:</span><span class="sxs-lookup"><span data-stu-id="7a269-214">The following query for SharePoint identifies documents that contain a credit card number:</span></span> 

```
sensitivetype:"credit card number"
```

<span data-ttu-id="7a269-215">Приведенный ниже запрос содержит несколько типичных ключевых слов, которые позволяют обнаружить документы или сообщения электронной почты, содержащие правовую информацию:</span><span class="sxs-lookup"><span data-stu-id="7a269-215">The following query contains some typical keywords to help identify documents or emails that contain legal content:</span></span>

```
ACP OR (Attorney Client Privilege*) OR (AC Privilege)
```

<span data-ttu-id="7a269-216">Приведенный ниже запрос содержит типичные ключевые слова, позволяющие обнаружить документы или сообщения электронной почты для специалистов отдела кадров:</span><span class="sxs-lookup"><span data-stu-id="7a269-216">The following query contains typical keywords to help identify documents or emails for human resources:</span></span> 

```
(resume AND staff AND employee AND salary AND recruitment AND candidate)
```

<span data-ttu-id="7a269-217">Обратите внимание, что в последнем примере используется  лучший метод, предусматривающий постоянное применение операторов между ключевыми словами.</span><span class="sxs-lookup"><span data-stu-id="7a269-217">Note that this final example uses the best practice of always including  operators between keywords.</span></span> <span data-ttu-id="7a269-218">Пробел между двумя ключевыми словами или двумя выражениями свойство:значение аналогичен оператору AND.</span><span class="sxs-lookup"><span data-stu-id="7a269-218">A space between keywords (or two property:value expressions) is the same as using AND.</span></span> <span data-ttu-id="7a269-219">Постоянное применение операторов позволяет понять, что для этого примера запроса будет найдено содержимое, включающее все эти ключевые слова, а не какое-либо из этих ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="7a269-219">By always adding operators, it's easier to see that this example query will identify only content that contains all these keywords, instead of content that contains any of the keywords.</span></span> <span data-ttu-id="7a269-220">Если нужно найти содержимое, включающее любое ключевое слово, укажите OR вместо AND.</span><span class="sxs-lookup"><span data-stu-id="7a269-220">If your intention is to identify content that contains any of the keywords, specify OR instead of AND.</span></span> <span data-ttu-id="7a269-221">Как показано в этом примере, при постоянном использовании операторов легче правильно интерпретировать запрос.</span><span class="sxs-lookup"><span data-stu-id="7a269-221">As this example shows, when you always specify the operators, it's easier to correctly interpret the query.</span></span> 

##### <a name="microsoft-teams-meeting-recordings"></a><span data-ttu-id="7a269-222">Записи собраний в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a269-222">Microsoft Teams meeting recordings</span></span>

> [!NOTE]
> <span data-ttu-id="7a269-223">Функция хранения и удаления записей собраний в Teams доступна в предварительной версии и не работает до сохранения записей в OneDrive или SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7a269-223">The ability to retain and delete Teams meeting recordings is in preview and won't work before recordings are saved to OneDrive or SharePoint.</span></span> <span data-ttu-id="7a269-224">Дополнительные сведения см. в статье [Использование OneDrive для бизнеса, SharePoint Online или Stream для записи собраний](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change)</span><span class="sxs-lookup"><span data-stu-id="7a269-224">For more information, see [Use OneDrive for Business and SharePoint Online or Stream for meeting recordings](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change).</span></span>

<span data-ttu-id="7a269-225">Для поиска записей собраний в Microsoft Teams, хранящихся в пользовательских учетных записях OneDrive или SharePoint, укажите для **редактора запросов по ключевым словам** следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="7a269-225">To identify Microsoft Teams meeting recordings that are stored in users' OneDrive accounts or in SharePoint, specify the following for the **Keyword query editor**:</span></span>

``` 
ProgID:Media AND ProgID:Meeting
```

<span data-ttu-id="7a269-226">В большинстве случаев записи собраний сохраняются в OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7a269-226">Most of the time, meeting recordings are saved to OneDrive.</span></span> <span data-ttu-id="7a269-227">Но для собраний канала они сохраняются в SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7a269-227">But for channel meetings, they are saved in SharePoint.</span></span>


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="7a269-228">Автоматическое применение меток к контенту с помощью обучаемых классификаторов</span><span class="sxs-lookup"><span data-stu-id="7a269-228">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="7a269-229">При использовании варианта для обучаемого классификатора вы можете выбрать один из встроенных классификаторов или настраиваемый классификатор.</span><span class="sxs-lookup"><span data-stu-id="7a269-229">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="7a269-230">К встроенным классификаторам относятся **Резюме**, **Исходный код**, **Целенаправленное притеснение**, **Сквернословие** и **Угрозы**.</span><span class="sxs-lookup"><span data-stu-id="7a269-230">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Выбор обучаемого классификатора](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="7a269-232">Мы не рекомендуем использовать встроенный классификатор **Оскорбительная лексика**, так как он генерировал большое количество ложных срабатываний.</span><span class="sxs-lookup"><span data-stu-id="7a269-232">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="7a269-233">Не используйте этот встроенный классификатор, а если вы применяете его в настоящее время, следует перенести с него свои бизнес-процессы.</span><span class="sxs-lookup"><span data-stu-id="7a269-233">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="7a269-234">Вместо него рекомендуем использовать встроенные классификаторы **Целенаправленное притеснение**, **Сквернословие** и **Угрозы**.</span><span class="sxs-lookup"><span data-stu-id="7a269-234">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="7a269-235">Для автоматического применения метки с использованием этого параметра сайты SharePoint и почтовые ящики должны иметь не менее 10 МБ данных.</span><span class="sxs-lookup"><span data-stu-id="7a269-235">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="7a269-236">Дополнительные сведения об обучаемых классификаторах см. в статье [Информация об обучаемых классификаторах (предварительная версия)](classifier-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="7a269-236">For more information about trainable classifiers, see [Learn about trainable classifiers (preview)](classifier-learn-about.md).</span></span>

> [!TIP]
> <span data-ttu-id="7a269-237">Если вы используете обучаемые классификаторы для Exchange, см. недавно выпущенную статью [Повторное обучение классификаторов в обозревателе содержимого (предварительная версия)](classifier-how-to-retrain-content-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="7a269-237">If you use trainable classifiers for Exchange, see the recently released [How to retrain a classifier in content explorer (preview)](classifier-how-to-retrain-content-explorer.md).</span></span>

<span data-ttu-id="7a269-238">Сведения, которые необходимо учитывать при использовании обучаемых классификаторов для автоматического применения меток хранения.</span><span class="sxs-lookup"><span data-stu-id="7a269-238">To consider when using trainable classifiers to auto-apply retention labels:</span></span>

- <span data-ttu-id="7a269-239">Метки можно автоматически применять к новым и измененным элементам, а также к существующим элементам за последние шесть месяцев.</span><span class="sxs-lookup"><span data-stu-id="7a269-239">New and modified items can be auto-labeled, and existing items from the last six months.</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="7a269-240">Срок вступления меток хранения в силу</span><span class="sxs-lookup"><span data-stu-id="7a269-240">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="7a269-241">Когда метки хранения применяются автоматически, может потребоваться до семи дней, чтобы метки хранения были применены ко всему существующему контенту, соответствующему условиям.</span><span class="sxs-lookup"><span data-stu-id="7a269-241">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Схема, иллюстрирующая, когда автоматически применяемые метки вступают в силу](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)

<span data-ttu-id="7a269-243">Если после семи дней ожидаемые метки не появляются, проверьте **Состояние** политики автоматического применения, выбрав ее на странице **Политики меток** в Центре соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="7a269-243">If the expected labels don't appear after seven days, check the **Status** of the auto-apply policy by selecting it from the **Label policies** page in the compliance center.</span></span> <span data-ttu-id="7a269-244">Для повторного развертывания политики (для OneDrive) или если отображается состояние **Отключено (ошибка)**, а в сведениях расположений выводится сообщение о том, что развертывание политики (для SharePoint) занимает больше времени, чем ожидалось, попробуйте выполнить команду [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) в PowerShell, чтобы повторно распространить политику:</span><span class="sxs-lookup"><span data-stu-id="7a269-244">If you see the status of **Off (Error)** and in the details for the locations see a message that it's taking longer than expected to deploy the policy (for SharePoint) or to try redeploying the policy (for OneDrive), try running the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) PowerShell command to retry the policy distribution:</span></span>

1. <span data-ttu-id="7a269-245">[Подключение к Центру безопасности и соответствия требованиям Windows PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="7a269-245">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="7a269-246">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7a269-246">Run the following command:</span></span>
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="7a269-247">Обновление меток хранения и их политик</span><span class="sxs-lookup"><span data-stu-id="7a269-247">Updating retention labels and their policies</span></span>

<span data-ttu-id="7a269-248">При изменении меток хранения или политики авто-применения, когда метка хранения уже применена к контенту, ваши обновленные параметры автоматически применяются к этому контенту, в дополнение к уже определенному.</span><span class="sxs-lookup"><span data-stu-id="7a269-248">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="7a269-249">Некоторые параметры невозможно изменить после создания и сохранения метки или политики, в том числе:</span><span class="sxs-lookup"><span data-stu-id="7a269-249">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="7a269-250">Имя метки хранения и имя политики, а также параметры хранения, за исключением периода хранения.</span><span class="sxs-lookup"><span data-stu-id="7a269-250">The retention label and policy name, and the retention settings except the retention period.</span></span> <span data-ttu-id="7a269-251">Однако если период хранения основан на времени применения метки к элементам, его изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="7a269-251">However, you can't change the retention period when the retention period is based on when items were labeled.</span></span>
- <span data-ttu-id="7a269-252">Параметр, помечающий элементы как запись.</span><span class="sxs-lookup"><span data-stu-id="7a269-252">The option to mark items as a record.</span></span>

## <a name="locking-the-policy-to-prevent-changes"></a><span data-ttu-id="7a269-253">Блокировка политики для предотвращения изменений</span><span class="sxs-lookup"><span data-stu-id="7a269-253">Locking the policy to prevent changes</span></span>

<span data-ttu-id="7a269-254">Чтобы гарантировать, что никто не сможет отключить политику, удалить ее или сделать ее менее строгой, см. раздел [Использование блокировки для сохранения для ограничения изменений политик хранения и политик меток хранения](retention-preservation-lock.md).</span><span class="sxs-lookup"><span data-stu-id="7a269-254">If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7a269-255">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7a269-255">Next steps</span></span>

<span data-ttu-id="7a269-256">Пример сценария, в котором используется политика автоматического применения меток хранения с управляемыми свойствами в SharePoint и хранение на основе событий, чтобы начать период хранения, см. в статье [Управление жизненным циклом хранящихся в SharePoint документов с помощью меток хранения](auto-apply-retention-labels-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="7a269-256">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply retention label policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
