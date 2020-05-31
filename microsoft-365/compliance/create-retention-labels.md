---
title: Создание, публикация и автоматическое применение меток хранения
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
description: Инструкции по созданию, публикации и автоматическому применению меток хранения для сохранения необходимых или удаления ненужных данных, и объявления элемента записью в среде Office 365.
ms.openlocfilehash: 65319baa0fd238ebdc403307fb8bb91a59d87cd6
ms.sourcegitcommit: 3cd487476efe4138d1b42499fbffbbe4bacfe5b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "44408471"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a><span data-ttu-id="87c87-103">Создание, публикация и автоматическое применение меток хранения</span><span class="sxs-lookup"><span data-stu-id="87c87-103">Create, publish, and auto-apply retention labels</span></span>

><span data-ttu-id="87c87-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="87c87-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="87c87-105">Используйте сведения ниже, чтобы создать [метки хранения](labels.md), а затем автоматически применять их к документам и электронным сообщениям, или публиковать их, чтобы пользователи могли применить их вручную.</span><span class="sxs-lookup"><span data-stu-id="87c87-105">Use the following information to help you create [retention labels](labels.md), and then automatically apply them to documents and emails, or publish them so that users can manually apply them.</span></span>

<span data-ttu-id="87c87-106">Метки хранения помогают сохранить необходимые и удалить ненужные данные.</span><span class="sxs-lookup"><span data-stu-id="87c87-106">Retention labels help you retain what you need and delete what you don't.</span></span> <span data-ttu-id="87c87-107">Они также используются для объявления элемента записью в роли метода [управления записями](records-management.md) для данных Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87c87-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="87c87-108">Место создания и настройки меток хранения, зависит от того, используете ли вы управление записями.</span><span class="sxs-lookup"><span data-stu-id="87c87-108">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="87c87-109">В обоих случаях доступны соответствующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="87c87-109">Instructions are provided for both scenarios.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="87c87-110">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="87c87-110">Before you begin</span></span>

<span data-ttu-id="87c87-111">Участникам команды по обеспечению соответствия требованиям, которые будут создавать метки хранения, потребуются разрешения для Центра безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="87c87-111">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="87c87-112">По умолчанию администратор клиента обладает доступом к этому расположению и может предоставить ответственным за обеспечение соответствия требованиям и другим лицам доступ к Центру безопасности и соответствия требованиям, не предоставляя им все разрешения администратора клиента. Для этого рекомендуем вам перейти на страницу **Разрешения** в Центре безопасности и соответствия требованиям, изменить группу ролей **Администратор соответствия требованиям** и добавить участников в эту группу ролей.</span><span class="sxs-lookup"><span data-stu-id="87c87-112">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="87c87-113">Дополнительные сведения см. в статье [Предоставление пользователям доступа к Центру безопасности и соответствия требованиям Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="87c87-113">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="87c87-p104">Эти разрешения необходимы только для создания и применения меток хранения и соответствующей политики. Для применения политики не требуется доступ к контенту.</span><span class="sxs-lookup"><span data-stu-id="87c87-p104">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>

## <a name="create-and-configure-retention-labels"></a><span data-ttu-id="87c87-116">Создание и настройка меток хранения</span><span class="sxs-lookup"><span data-stu-id="87c87-116">Create and configure retention labels</span></span>

1. <span data-ttu-id="87c87-117">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="87c87-117">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="87c87-118">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="87c87-118">If you are using records management:</span></span>
        - <span data-ttu-id="87c87-119">**Решения** > **Управление записями** > вкладка **План хранения** > **+ Создать метку** > **Метка хранения**</span><span class="sxs-lookup"><span data-stu-id="87c87-119">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="87c87-120">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="87c87-120">If you are not using records management:</span></span>
       - <span data-ttu-id="87c87-121">**Решения** > **Управление информацией** > вкладка **Метки** > + **Создать метку**</span><span class="sxs-lookup"><span data-stu-id="87c87-121">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="87c87-122">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="87c87-122">Don't immediately see your option?</span></span> <span data-ttu-id="87c87-123">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="87c87-123">First select **Show all**.</span></span> 

2. <span data-ttu-id="87c87-124">Следуйте указаниям мастера.</span><span class="sxs-lookup"><span data-stu-id="87c87-124">Follow the prompts in the wizard.</span></span> <span data-ttu-id="87c87-125">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="87c87-125">If you are using records management:</span></span>
    
    - <span data-ttu-id="87c87-126">Дополнительные сведения о дескрипторах плана хранения, см. в статье [Общие сведения о диспетчере плана хранения](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="87c87-126">For information about the file plan descriptors, see [Overview of file plan manager](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="87c87-127">Чтобы использовать метку хранения для объявления содержимого записью, включите флажок **Использовать метку, чтобы классифицировать содержимое как "Запись"**.</span><span class="sxs-lookup"><span data-stu-id="87c87-127">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="87c87-128">Повторите эти действия для создания дополнительных меток.</span><span class="sxs-lookup"><span data-stu-id="87c87-128">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="87c87-129">Чтобы изменить существующую метку, выберите ее и нажмите **Изменить метку**.</span><span class="sxs-lookup"><span data-stu-id="87c87-129">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="87c87-130">При этом запускается тот же мастер, который позволяет изменить описания и параметры метки на шаге 2.</span><span class="sxs-lookup"><span data-stu-id="87c87-130">This starts the same wizard, which lets you change the label descriptions and settings in step 2.</span></span>

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a><span data-ttu-id="87c87-131">Публикуйте метки хранения, создавая их политику</span><span class="sxs-lookup"><span data-stu-id="87c87-131">Publish retention labels by creating a retention label policy</span></span>

<span data-ttu-id="87c87-132">Публикуйте метки хранения, чтобы пользователи могли применить их вручную.</span><span class="sxs-lookup"><span data-stu-id="87c87-132">Publish retention labels so that they can be manually applied by users.</span></span>

1. <span data-ttu-id="87c87-133">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="87c87-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="87c87-134">Если используется управление записями:</span><span class="sxs-lookup"><span data-stu-id="87c87-134">If you are using records management:</span></span>
        - <span data-ttu-id="87c87-135">**Решения** > **Управление записями** > > вкладка**Политики меток** > **Опубликовать метки**</span><span class="sxs-lookup"><span data-stu-id="87c87-135">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="87c87-136">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="87c87-136">If you are not using records management:</span></span>
        - <span data-ttu-id="87c87-137">**Решения** > **Управление информацией** >  вкладка **Политики меток** > **Опубликовать метки**</span><span class="sxs-lookup"><span data-stu-id="87c87-137">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="87c87-138">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="87c87-138">Don't immediately see your option?</span></span> <span data-ttu-id="87c87-139">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="87c87-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="87c87-140">Следуйте указаниям мастера.</span><span class="sxs-lookup"><span data-stu-id="87c87-140">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="87c87-141">Сведения о расположениях, поддерживаемых метками хранения, см. в разделе [Метки хранения и расположения](labels.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="87c87-141">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span> 

## <a name="auto-apply-a-retention-label"></a><span data-ttu-id="87c87-142">Автоматическое применение меток хранения</span><span class="sxs-lookup"><span data-stu-id="87c87-142">Auto-apply a retention label</span></span>

<span data-ttu-id="87c87-143">Применяйте метки хранения автоматически на основе указанных условий.</span><span class="sxs-lookup"><span data-stu-id="87c87-143">Auto-apply a retention label, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="87c87-144">В [Центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com/) перейдите в одно из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="87c87-144">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="87c87-145">Если используется управление записями: **Управление информацией**:</span><span class="sxs-lookup"><span data-stu-id="87c87-145">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="87c87-146">**Решения** > **Управление записями** >  вкладка **Политики меток** > **Автоматически применить метку**</span><span class="sxs-lookup"><span data-stu-id="87c87-146">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="87c87-147">Если управление записями не используется:</span><span class="sxs-lookup"><span data-stu-id="87c87-147">If you are not using records management:</span></span>
        - <span data-ttu-id="87c87-148">**Решения** > **Управление информацией** >  вкладка **Политики меток** > **Автоматически применить метку**</span><span class="sxs-lookup"><span data-stu-id="87c87-148">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="87c87-149">Не отображается необходимый параметр?</span><span class="sxs-lookup"><span data-stu-id="87c87-149">Don't immediately see your option?</span></span> <span data-ttu-id="87c87-150">Сначала выберите **Показать все**.</span><span class="sxs-lookup"><span data-stu-id="87c87-150">First select **Show all**.</span></span> 

2. <span data-ttu-id="87c87-151">Следуйте указаниям мастера.</span><span class="sxs-lookup"><span data-stu-id="87c87-151">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="87c87-152">Сведения о настройке условий для автоматического применения метки хранения, см. в разделе [Настройка условий автоматического применения меток хранения](#configuring-conditions-for-auto-apply-retention-labels) на этой странице.</span><span class="sxs-lookup"><span data-stu-id="87c87-152">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="87c87-153">Сведения о расположениях, поддерживаемых метками хранения, см. в разделе [Метки хранения и расположения](labels.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="87c87-153">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span>


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="87c87-154">Настройка условий для автоматического применения меток хранения</span><span class="sxs-lookup"><span data-stu-id="87c87-154">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="87c87-155">Автоматически применяйте метки хранения к контенту, содержащему:</span><span class="sxs-lookup"><span data-stu-id="87c87-155">You can apply retention labels to content automatically when that content contains:</span></span>
  
- <span data-ttu-id="87c87-156">[конфиденциальную информацию определенных типов](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information);</span><span class="sxs-lookup"><span data-stu-id="87c87-156">[Specific types of sensitive information](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)</span></span>
    
- <span data-ttu-id="87c87-157">[определенные ключевые слова, соответствующие созданному запросу](#auto-apply-labels-to-content-with-keywords-or-searchable-properties);</span><span class="sxs-lookup"><span data-stu-id="87c87-157">[Specific keywords that match a query you create](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)</span></span>

- <span data-ttu-id="87c87-158">[совпадение для обучаемых классификаторов](#auto-apply-labels-to-content-by-using-trainable-classifiers).</span><span class="sxs-lookup"><span data-stu-id="87c87-158">[A match for trainable classifiers](#auto-apply-labels-to-content-by-using-trainable-classifiers)</span></span>
    
![Страница выбора условий для автоматически применяемых меток](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="87c87-160">Автоматическое применение меток хранения к контенту, соответствующему заданным условиям, может занять до семи дней.</span><span class="sxs-lookup"><span data-stu-id="87c87-160">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="87c87-161">Автоматическое применение меток к контенту с определенными типами конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="87c87-161">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="87c87-162">Когда вы создаете автоматически присваиваемые метки хранения для конфиденциальной информации, вы видите тот же список шаблонов политик, что и при создании политики защиты от потери данных (DLP) .</span><span class="sxs-lookup"><span data-stu-id="87c87-162">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="87c87-163">Каждый шаблон политик настроен для поиска определенных типов конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="87c87-163">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="87c87-164">Например, показанный здесь шаблон служит для выявления идентификационного номера налогоплательщика (ITIN), номера социального страхования (SSN) и номера паспорта в американском формате.</span><span class="sxs-lookup"><span data-stu-id="87c87-164">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="87c87-165">Дополнительные сведения см. в статье [Обзор политик защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="87c87-165">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![Шаблоны политик с типами конфиденциальной информации](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="87c87-p111">Выбрав шаблон политики, вы можете добавлять или удалять конфиденциальную информацию любых типов, а также менять количество экземпляров и точность совпадения. В приведенном ниже примере метка хранения будет автоматически применяться, только если:</span><span class="sxs-lookup"><span data-stu-id="87c87-p111">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="87c87-p112">контент содержит от 1 до 9 экземпляров любого из этих трех типов конфиденциальной информации. Вы можете удалить **максимальное** значение, чтобы оно изменилось на **Любое**;</span><span class="sxs-lookup"><span data-stu-id="87c87-p112">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="87c87-p113">для определяемого типа конфиденциальной информации задана точность совпадения (или уровень надежности) не менее 75. Для многих типов конфиденциальной информации определяется несколько шаблонов. Чем выше точность совпадения, тем больше признаков (например, ключевых слов, дат или адресов) нужно для обнаружения шаблона. Проще говоря, чем ниже **минимальная** точность совпадения, тем проще сопоставить контент с условием.</span><span class="sxs-lookup"><span data-stu-id="87c87-p113">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="87c87-174">Дополнительные сведения об этих параметрах см. в разделе [Настройка правил для упрощения или усложнения сопоставления](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="87c87-174">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Параметры определения типов конфиденциальной информации](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="87c87-176">Автоматическое применение меток к контенту с ключевыми словами или доступными для поиска свойствами</span><span class="sxs-lookup"><span data-stu-id="87c87-176">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="87c87-p114">Вы можете автоматически применять метки к контенту, соответствующему определенным условиям. Имеющиеся в данный момент условия поддерживают применение метки к контенту, содержащему определенные слова, фразы или значения доступных для поиска свойств. Вы можете уточнить запрос с помощью таких операторов поиска, как AND, OR и NOT.</span><span class="sxs-lookup"><span data-stu-id="87c87-p114">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="87c87-180">Дополнительные сведения о синтаксисе запросов см. в статье:</span><span class="sxs-lookup"><span data-stu-id="87c87-180">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="87c87-181">Руководство по синтаксису языка запросов по ключевым словам (KQL)</span><span class="sxs-lookup"><span data-stu-id="87c87-181">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="87c87-p115">Метки на основе запросов используют индекс поиска для определения контента. Дополнительные сведения о допустимых свойствах, доступных для поиска, см. в статьях:</span><span class="sxs-lookup"><span data-stu-id="87c87-p115">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="87c87-184">Запросы ключевых слов и условия поиска контента</span><span class="sxs-lookup"><span data-stu-id="87c87-184">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="87c87-185">Обзор свойств для обхода и управляемых свойств в SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="87c87-185">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="87c87-186">Примеры запросов:</span><span class="sxs-lookup"><span data-stu-id="87c87-186">Examples queries:</span></span>

- <span data-ttu-id="87c87-187">Exchange</span><span class="sxs-lookup"><span data-stu-id="87c87-187">Exchange</span></span>
    - <span data-ttu-id="87c87-188">subject:"Квартальное финансирование"</span><span class="sxs-lookup"><span data-stu-id="87c87-188">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="87c87-189">recipients:garthf</span><span class="sxs-lookup"><span data-stu-id="87c87-189">recipients:garthf</span></span><!--nolink--><span data-ttu-id="87c87-190">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="87c87-190">@contoso.com</span></span>
- <span data-ttu-id="87c87-191">SharePoint и OneDrive</span><span class="sxs-lookup"><span data-stu-id="87c87-191">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="87c87-192">contenttype:контракт</span><span class="sxs-lookup"><span data-stu-id="87c87-192">contenttype:contract</span></span>
    - <span data-ttu-id="87c87-193">site:https</span><span class="sxs-lookup"><span data-stu-id="87c87-193">site:https</span></span><!--nolink--><span data-ttu-id="87c87-194">://contoso.sharepoint.com/sites/teams/procurement И contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="87c87-194">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![Редактор запросов](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="87c87-196">Автоматическое применение меток к контенту с помощью обучаемых классификаторов</span><span class="sxs-lookup"><span data-stu-id="87c87-196">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="87c87-197">При использовании варианта для обучаемого классификатора вы можете выбрать один из встроенных классификаторов или настраиваемый классификатор.</span><span class="sxs-lookup"><span data-stu-id="87c87-197">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="87c87-198">К встроенным классификаторам относятся **Резюме**, **Исходный код**, **Целенаправленное притеснение**, **Сквернословие** и **Угрозы**.</span><span class="sxs-lookup"><span data-stu-id="87c87-198">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Выбор обучаемого классификатора](../media/retention-label-classifers.png)

<span data-ttu-id="87c87-200">Для автоматического применения меток с помощью классификатора на сайтах и в почтовых ящиках SharePoint Online должно быть не менее 10 МБ данных.</span><span class="sxs-lookup"><span data-stu-id="87c87-200">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="87c87-201">Дополнительные сведения об обучаемых классификаторах см. в статье [Начало работы с обучаемыми классификаторами (предварительная версия)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="87c87-201">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="87c87-202">Пример конфигурации см. в статье [Подготовка к использованию и использование встроенных классификаторов](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span><span class="sxs-lookup"><span data-stu-id="87c87-202">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="87c87-203">Срок вступления меток хранения в силу</span><span class="sxs-lookup"><span data-stu-id="87c87-203">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="87c87-204">При публикации автоматически применяемые метки хранения не сразу вступают в силу.</span><span class="sxs-lookup"><span data-stu-id="87c87-204">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="87c87-205">Для начала необходимо синхронизировать политику меток с расположениями при помощи Центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="87c87-205">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="87c87-206">Затем в расположении может потребоваться некоторое время, чтобы опубликованные метки хранения стали доступными конечным пользователям или чтобы содержимому были автоматически присвоены соответствующие метки.</span><span class="sxs-lookup"><span data-stu-id="87c87-206">Then the location might require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="87c87-207">Необходимое для этого время зависит от расположения и типа метки хранения.</span><span class="sxs-lookup"><span data-stu-id="87c87-207">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="87c87-208">Опубликованные метки хранения</span><span class="sxs-lookup"><span data-stu-id="87c87-208">Published retention labels</span></span>

<span data-ttu-id="87c87-p118">При публикации меток хранения в SharePoint или OneDrive могут потребоваться сутки, чтобы эти метки хранения стали видны пользователям. Кроме того, при публикации меток хранения в Exchange может потребоваться 7 дней, чтобы эти метки хранения стали видны пользователям, а почтовый ящик должен содержать не менее 10 МБ данных.</span><span class="sxs-lookup"><span data-stu-id="87c87-p118">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![Схема, иллюстрирующая, когда вручную применяемые метки вступают в силу](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="87c87-212">Метки хранения, применяемые автоматически</span><span class="sxs-lookup"><span data-stu-id="87c87-212">Auto-apply retention labels</span></span>

<span data-ttu-id="87c87-213">Если метки хранения автоматически применяются к контенту, соответствующему определенным условиям, может потребоваться семь дней, чтобы метки хранения были применены ко всему существующему контенту, соответствующему условиям.</span><span class="sxs-lookup"><span data-stu-id="87c87-213">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Схема, иллюстрирующая, когда автоматически применяемые метки вступают в силу](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="87c87-215">Проверка состояния меток хранения, опубликованных в Exchange</span><span class="sxs-lookup"><span data-stu-id="87c87-215">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="87c87-216">В Exchange Online метки хранения доступны конечным пользователям благодаря процессу, который выполняется каждые семь дней.</span><span class="sxs-lookup"><span data-stu-id="87c87-216">In Exchange Online, retention labels are made available to end users by a process that runs every seven days.</span></span> <span data-ttu-id="87c87-217">С помощью Powershell вы можете узнать, когда этот процесс запускался в последний раз и, соответственно, когда он будет запущен снова.</span><span class="sxs-lookup"><span data-stu-id="87c87-217">By using Powershell, you can see when this process last ran and therefore identify when it will run again.</span></span>
  
1. <span data-ttu-id="87c87-218">[Подключение к Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span><span class="sxs-lookup"><span data-stu-id="87c87-218">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="87c87-219">Выполните следующие команды:</span><span class="sxs-lookup"><span data-stu-id="87c87-219">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

<span data-ttu-id="87c87-220">В результатах свойство `ELCLastSuccessTimeStamp` (UTC) показывает, когда система в последний раз обрабатывала ваш почтовый ящик.</span><span class="sxs-lookup"><span data-stu-id="87c87-220">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="87c87-221">Если этого не происходило с момента создания политики, метки не будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="87c87-221">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="87c87-222">Для принудительной обработки выполните команду `Start-ManagedFolderAssistant -Identity <user>`.</span><span class="sxs-lookup"><span data-stu-id="87c87-222">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="87c87-223">Если метки не отображаются в Outlook в Интернете, хотя они должны быть видны, очистите кэш браузера (CTRL+F5).</span><span class="sxs-lookup"><span data-stu-id="87c87-223">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="87c87-224">Обновление меток хранения и их политик</span><span class="sxs-lookup"><span data-stu-id="87c87-224">Updating retention labels and their policies</span></span>

<span data-ttu-id="87c87-225">При изменении меток хранения, их политику или политику авто-применения когда метка хранения уже применена к контенту, ваши обновленные параметры автоматически применяются к этому контенту, в дополнение к уже помеченному.</span><span class="sxs-lookup"><span data-stu-id="87c87-225">If you edit a retention label, retention label policy, or auto-apply policy and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly labeled.</span></span>

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a><span data-ttu-id="87c87-226">Поиск командлетов PowerShell для меток хранения</span><span class="sxs-lookup"><span data-stu-id="87c87-226">Find the PowerShell cmdlets for retention labels</span></span>

<span data-ttu-id="87c87-227">Для использования командлетов меток хранения:</span><span class="sxs-lookup"><span data-stu-id="87c87-227">To use the retention label cmdlets:</span></span>
  
1. [<span data-ttu-id="87c87-228">Подключение к PowerShell Центра безопасности и соответствия требованиям Office 365</span><span class="sxs-lookup"><span data-stu-id="87c87-228">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="87c87-229">Используйте эти командлеты Центра безопасности и соответствия требованиям Office 365:</span><span class="sxs-lookup"><span data-stu-id="87c87-229">Use these Office 365 Security & Compliance Center cmdlets:</span></span>
    
    - [<span data-ttu-id="87c87-230">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="87c87-230">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [<span data-ttu-id="87c87-231">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="87c87-231">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [<span data-ttu-id="87c87-232">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="87c87-232">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [<span data-ttu-id="87c87-233">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="87c87-233">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [<span data-ttu-id="87c87-234">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="87c87-234">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [<span data-ttu-id="87c87-235">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="87c87-235">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [<span data-ttu-id="87c87-236">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="87c87-236">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [<span data-ttu-id="87c87-237">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="87c87-237">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [<span data-ttu-id="87c87-238">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="87c87-238">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [<span data-ttu-id="87c87-239">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="87c87-239">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [<span data-ttu-id="87c87-240">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="87c87-240">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [<span data-ttu-id="87c87-241">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="87c87-241">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [<span data-ttu-id="87c87-242">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="87c87-242">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [<span data-ttu-id="87c87-243">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="87c87-243">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
