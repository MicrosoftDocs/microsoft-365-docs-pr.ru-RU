---
title: Общие сведения о хранении, зависящем от возникновения события
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: Как правило, в рамках решения для управления записями можно настроить метку хранения, чтобы начать период хранения, который зависит от возникновения указанного вами события.
ms.openlocfilehash: 7286e65be2313f5716bfc59399c1755cadb9f6d6
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778529"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="a9042-103">Общие сведения о хранении, зависящем от возникновения события</span><span class="sxs-lookup"><span data-stu-id="a9042-103">Start retention when an event occurs</span></span>

><span data-ttu-id="a9042-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="a9042-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a9042-p101">Срок хранения контента часто определяется его возрастом. Например, вы можете хранить документы в течение семи лет после их создания, а затем удалять их. Однако, настроив [метки хранения](labels.md), вы также можете задать период хранения исходя из того, когда происходит событие определенного типа. Событие становится началом периода хранения, а ко всему контенту с меткой, относящейся к этому типу события, применяются предусмотренные ею действия.</span><span class="sxs-lookup"><span data-stu-id="a9042-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="a9042-109">Примеры использования хранения на основе событий.</span><span class="sxs-lookup"><span data-stu-id="a9042-109">Examples for using event-driven retention:</span></span>
  
- <span data-ttu-id="a9042-110">**Сотрудники, покидающие организацию**. Предположим, что записи сотрудников нужно хранить в течение 10 лет с того момента, когда они покинули организацию.</span><span class="sxs-lookup"><span data-stu-id="a9042-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="a9042-111">По истечении 10 лет все документы, связанные с наймом, результатами работы и увольнением сотрудника необходимо ликвидировать.</span><span class="sxs-lookup"><span data-stu-id="a9042-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="a9042-112">Событием, которое активирует 10-летний период хранения, является уход сотрудника из организации.</span><span class="sxs-lookup"><span data-stu-id="a9042-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="a9042-113">**Окончание срока действия договора**. Предположим, что все записи, связанные с договорами, нужно хранить в течение пяти лет с момента окончания срока действия договора.</span><span class="sxs-lookup"><span data-stu-id="a9042-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="a9042-114">Событием, активирующим пятилетний период хранения, будет окончание срока действия договора.</span><span class="sxs-lookup"><span data-stu-id="a9042-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="a9042-p104">**Время существования продукта.** У вашей организации могут быть требования к хранению, связанные с датой последнего выпуска продуктов, в отношении такого контента, как технические спецификации. В таком случае последний выпуск — это событие, активирующее начало периода хранения.</span><span class="sxs-lookup"><span data-stu-id="a9042-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="a9042-p105">Хранение, зависящее от возникновения события, обычно используется в процессе управления записями. Это означает следующее:</span><span class="sxs-lookup"><span data-stu-id="a9042-p105">Event-driven retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="a9042-119">Метки на основе событий также обычно классифицируют содержимое как запись в рамках решения управления записями.</span><span class="sxs-lookup"><span data-stu-id="a9042-119">Labels based on events also usually classify content as a record, as a part of a records management solution.</span></span> <span data-ttu-id="a9042-120">Дополнительную информацию см. в статье [Сведения об управлении записями](records-management.md).</span><span class="sxs-lookup"><span data-stu-id="a9042-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="a9042-121">Документ, который был обозначен как запись, но для которого активирующее событие еще не наступило, хранится в течение неограниченного времени (окончательно удалить записи невозможно), пока некоторое событие не активирует период его хранения.</span><span class="sxs-lookup"><span data-stu-id="a9042-121">A document that's been classified as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="a9042-122">Метки хранения на основе события в конце периода хранения обычно активируют проверку перед ликвидацией, что позволяет лицу, ответственному за управление записями, вручную просмотреть и ликвидировать контент.</span><span class="sxs-lookup"><span data-stu-id="a9042-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="a9042-123">Дополнительные сведения см. в статье [Ликвидация контента](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="a9042-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="a9042-124">Метки на основе событий обладают теми же возможностями, что и другие метки хранения в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a9042-124">A label based on an event has the same capabilities as any retention label in Microsoft  365.</span></span> <span data-ttu-id="a9042-125">Дополнительные сведения см. в статье [Сведения о политиках и метках хранения](retention.md).</span><span class="sxs-lookup"><span data-stu-id="a9042-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="a9042-126">Взаимосвязь между типами событий, метками, событиями и идентификаторами ресурсов</span><span class="sxs-lookup"><span data-stu-id="a9042-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="a9042-127">Чтобы успешно использовать управляемое событиями хранение, важно понимать взаимосвязь между типами событий, метками хранения, событиями и идентификаторами активов, как показано на диаграммах и в следующем пояснении:</span><span class="sxs-lookup"><span data-stu-id="a9042-127">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![Схема взаимосвязей между типами событий, метками, событиями и идентификаторами ресурсов](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Схема взаимосвязей между типами событий, метками, событиями и идентификаторами ресурсов](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="a9042-130">Вы создаете метки хранения для разных типов контента, а затем связываете их с типом события.</span><span class="sxs-lookup"><span data-stu-id="a9042-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="a9042-131">Например, метки хранения для различных типов файлов и записей продукта связаны с типом события с именем Product Lifetime, поскольку эти записи должны храниться в течение 10 лет с момента окончания срока действия продукта.</span><span class="sxs-lookup"><span data-stu-id="a9042-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="a9042-132">Пользователи (обычно менеджеры записей) применяют эти метки хранения к контенту и (для документов SharePoint и OneDrive) вводят идентификатор ресурса для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="a9042-132">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="a9042-133">В этом примере идентификатор актива - это название продукта или код, используемый организацией.</span><span class="sxs-lookup"><span data-stu-id="a9042-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="a9042-134">Таким образом, каждой записи продукта присваивается метка хранения, и каждая запись имеет свойство, которое содержит идентификатор актива.</span><span class="sxs-lookup"><span data-stu-id="a9042-134">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="a9042-135">Диаграмма представляет **весь контент** для всех записей продукта в организации, и каждый элемент имеет идентификатор актива продукта, чья запись это.</span><span class="sxs-lookup"><span data-stu-id="a9042-135">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="a9042-p111">"Время существования продукта" — это тип события, которое наступает при завершении существования продукта. Когда возникает такого рода события, т. е. когда время существования продукта заканчивается, создается событие, для которого указывается следующее:</span><span class="sxs-lookup"><span data-stu-id="a9042-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="a9042-138">Идентификатор ресурса (для документов SharePoint и OneDrive).</span><span class="sxs-lookup"><span data-stu-id="a9042-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="a9042-p112">Ключевые слова (для элементов Exchange). В этом примере организация использует код продукта в сообщениях, содержащих записи продукта, поэтому ключевое слово для элементов Exchange совпадает с идентификатором ресурса для документов SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a9042-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="a9042-p113">Дата возникновения события. С этой даты начинается период хранения, она может быть текущей, прошедшей или будущей.</span><span class="sxs-lookup"><span data-stu-id="a9042-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="a9042-144">После создания события эта дата события синхронизируется со всем контентом, который имеет метку хранения этого типа и которая содержит указанный идентификатор актива или ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="a9042-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="a9042-145">Как и в случае любой другой метки хранения, эта синхронизация может занять до 7 дней.</span><span class="sxs-lookup"><span data-stu-id="a9042-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="a9042-146">На предыдущей схеме все элементы, обведенные красным, имеют период хранения, активированный этим событием.</span><span class="sxs-lookup"><span data-stu-id="a9042-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="a9042-147">Другими словами, когда срок действия этого продукта истекает, это событие запускает период хранения для записей этого продукта.</span><span class="sxs-lookup"><span data-stu-id="a9042-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="a9042-148">Важно понимать, что если вы не укажете идентификатор ресурса или ключевые слова для события, у **всего содержимого**, которому присвоена метка события такого типа, будет период хранения, определяемый событием.</span><span class="sxs-lookup"><span data-stu-id="a9042-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="a9042-149">Это означает, что на предыдущей диаграмме все содержимое начало бы сохраняться.</span><span class="sxs-lookup"><span data-stu-id="a9042-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="a9042-150">Это может быть не то, что вы намерены.</span><span class="sxs-lookup"><span data-stu-id="a9042-150">This might not be what you intend.</span></span> 

<span data-ttu-id="a9042-151">Наконец, помните, что каждая метка хранения имеет свои собственные настройки хранения.</span><span class="sxs-lookup"><span data-stu-id="a9042-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="a9042-152">В этом примере все они указывают 10 лет, но для события возможно инициировать метки хранения, где каждая метка имеет свой период хранения.</span><span class="sxs-lookup"><span data-stu-id="a9042-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="a9042-153">Настройка хранения, зависящего от возникновения события</span><span class="sxs-lookup"><span data-stu-id="a9042-153">How to set up event-driven retention</span></span>

<span data-ttu-id="a9042-154">Рабочий процесс высокого уровня для удержания на основе событий:</span><span class="sxs-lookup"><span data-stu-id="a9042-154">High-level workflow for event-driven retention:</span></span>
  
![Схема, иллюстрирующая рабочий процесс для настройки хранения, зависящего от возникновения события](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="a9042-156">Подробный сценарий использования управляемых свойств в SharePoint для автоматического применения меток хранения и реализации хранения, зависящего от возникновения события, см. в статье [Управление жизненным циклом хранящихся в SharePoint документов с помощью меток хранения](auto-apply-retention-labels-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="a9042-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="a9042-157">Шаг 1. Создайте метку, период хранения которой зависит от возникновения события</span><span class="sxs-lookup"><span data-stu-id="a9042-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="a9042-158">Чтобы создать и настроить метку хранения, следуйте инструкциям, приведенным в статье [Создание и настройка меток хранения](create-retention-labels.md#create-and-configure-retention-labels), а при включении хранения выберите вариант действия с контентом исходя из события — сохранение или удаление.</span><span class="sxs-lookup"><span data-stu-id="a9042-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels) and when you turn on retention, choose the option to retain or delete the content based on an event.</span></span> <span data-ttu-id="a9042-159">Этот параметр означает, что параметры хранения вступят в силу только после создания вами на шаге 5 события на странице **События**.</span><span class="sxs-lookup"><span data-stu-id="a9042-159">This setting means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="a9042-160">Хранение на основе событий обычно используется для контента, обозначенного как запись, поэтому рекомендуется также проверить, не нужно ли выбрать параметр, помечающий контент как запись.</span><span class="sxs-lookup"><span data-stu-id="a9042-160">Event-driven retention is typically used for content that's classified as a record, so this is a good time to check whether you also need to select the option that marks content as a record.</span></span>
  
<span data-ttu-id="a9042-161">Для хранения на основе событий требуются настройки хранения, согласно которым будет выполняться следующее:</span><span class="sxs-lookup"><span data-stu-id="a9042-161">Event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="a9042-162">хранение содержимого;</span><span class="sxs-lookup"><span data-stu-id="a9042-162">Retain the content.</span></span>
    
- <span data-ttu-id="a9042-163">автоматическое удаление содержимого или активация проверки перед ликвидацией в конце периода хранения.</span><span class="sxs-lookup"><span data-stu-id="a9042-163">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![Возможность создать метку на основе события](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="a9042-165">Шаг 2. Выберите тип события для такой метки</span><span class="sxs-lookup"><span data-stu-id="a9042-165">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="a9042-166">После того как вы выберете для метки параметр, позволяющий связать ее с **событием**, вы увидите команду **Выбрать тип события**.</span><span class="sxs-lookup"><span data-stu-id="a9042-166">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="a9042-167">Тип события — это просто общее описание события, которое нужно связать с меткой.</span><span class="sxs-lookup"><span data-stu-id="a9042-167">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="a9042-168">Например, если вы создадите тип события с именем Product Lifetime, вы создадите метки хранения на основе событий с именами, которые описывают, к каким типам контента вы хотите применить метки, например «Файлы разработки продукта» или «Бизнес продукта». записи решений ".</span><span class="sxs-lookup"><span data-stu-id="a9042-168">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>

<span data-ttu-id="a9042-169">Выберите один из встроенных типов событий или создайте собственный тип и выберите его.</span><span class="sxs-lookup"><span data-stu-id="a9042-169">Select one of the built-in event types, or create your own and then select it.</span></span>

<span data-ttu-id="a9042-170">После выбора типа события и создания метки хранения тип события не изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="a9042-170">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>
  
![Возможности создания или выбора типа события](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="a9042-172">Шаг 3. Публикация или автоматическое применение меток хранения на основе событий</span><span class="sxs-lookup"><span data-stu-id="a9042-172">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="a9042-173">Метку хранения на основе события, как и любую другую метку хранения, необходимо автоматически применить к событию или опубликовать, чтобы ее можно было вручную или автоматически применять.</span><span class="sxs-lookup"><span data-stu-id="a9042-173">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="a9042-174">Создание меток хранения и их применение в приложениях</span><span class="sxs-lookup"><span data-stu-id="a9042-174">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="a9042-175">Автоматическое применение метки хранения к контенту</span><span class="sxs-lookup"><span data-stu-id="a9042-175">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)


> [!NOTE]
> <span data-ttu-id="a9042-176">Если выбрать метку хранения на основе событий на вкладке **Управление записями** > **План хранения** или **Управление данными** > **Метки**, то кнопка **Автоматически применить метку** будет недоступна.</span><span class="sxs-lookup"><span data-stu-id="a9042-176">If you select an event-based retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="a9042-177">Вместо этой кнопки используйте параметр **Автоматически применить метку**, расположенный над списком меток или политик в одном из следующих расположений:</span><span class="sxs-lookup"><span data-stu-id="a9042-177">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="a9042-178">**Управление записями** >  вкладка **Политики меток**</span><span class="sxs-lookup"><span data-stu-id="a9042-178">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="a9042-179">**Управление информацией** >  вкладка **Метки** или вкладка **Политики меток**</span><span class="sxs-lookup"><span data-stu-id="a9042-179">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![Возможности публиковать или автоматически применять метки хранения](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="a9042-181">Шаг 4. Введите идентификатор ресурса</span><span class="sxs-lookup"><span data-stu-id="a9042-181">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="a9042-182">После применения метки на основе событий к содержимому можно ввести ИД ресурса для каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="a9042-182">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="a9042-183">Например, в вашей организации могут использоваться:</span><span class="sxs-lookup"><span data-stu-id="a9042-183">For example, your organization might use:</span></span>
  
- <span data-ttu-id="a9042-184">коды продуктов для хранения содержимого, касающегося только определенного продукта;</span><span class="sxs-lookup"><span data-stu-id="a9042-184">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="a9042-185">коды проектов для хранения содержимого, касающегося только определенного проекта;</span><span class="sxs-lookup"><span data-stu-id="a9042-185">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="a9042-186">идентификаторы сотрудников для хранения содержимого, касающегося только конкретного лица.</span><span class="sxs-lookup"><span data-stu-id="a9042-186">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="a9042-187">Идентификатор ресурса — это еще одно свойство документа, доступное в SharePoint и OneDrive.</span><span class="sxs-lookup"><span data-stu-id="a9042-187">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="a9042-188">Ваша организация может уже использовать другие свойства и идентификаторы документов для классификации содержимого.</span><span class="sxs-lookup"><span data-stu-id="a9042-188">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="a9042-189">В этом случае также можно использовать эти свойства и значения при создании события — см. следующий шаг 6.</span><span class="sxs-lookup"><span data-stu-id="a9042-189">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="a9042-190">Важно использовать какое-либо сочетание*свойство:значение* в свойствах документа, чтобы сопоставить элемент с каким-либо типом событий.</span><span class="sxs-lookup"><span data-stu-id="a9042-190">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![Текстовое поле для ввода идентификатора ресурса](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="a9042-192">Шаг 5. Создайте событие</span><span class="sxs-lookup"><span data-stu-id="a9042-192">Step 5: Create an event</span></span>

<span data-ttu-id="a9042-193">Когда возникнет конкретное событие такого типа (например, когда завершится срок службы продукта), перейдите на страницу **Управление записями** > **События** в Центре соответствия требованиям Microsoft 365 и создайте событие.</span><span class="sxs-lookup"><span data-stu-id="a9042-193">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="a9042-194">Можно инициировать событие, создав его.</span><span class="sxs-lookup"><span data-stu-id="a9042-194">You trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="a9042-195">Шаг 6. Выберите тип события, который использовался для метки из описания шага 2</span><span class="sxs-lookup"><span data-stu-id="a9042-195">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="a9042-196">Когда вы создаете событие, выберите тот же тип события, который используется меткой хранения на шаге 2, например "Время существования продукта".</span><span class="sxs-lookup"><span data-stu-id="a9042-196">When you create the event, choose the same event type used by the retention label in step 2—for example, Product Lifetime.</span></span> <span data-ttu-id="a9042-197">Период хранения будет инициирован только для контента с метками хранения, примененными к нему с таким типом события.</span><span class="sxs-lookup"><span data-stu-id="a9042-197">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![Возможность выбора типа события в параметрах события](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="a9042-199">Шаг 7. Введите ключевые слова или идентификатор ресурса</span><span class="sxs-lookup"><span data-stu-id="a9042-199">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="a9042-200">Теперь можно ограничить область содержимого, указав идентификаторы ресурсов для содержимого SharePoint и OneDrive или ключевые слова для содержимого Exchange.</span><span class="sxs-lookup"><span data-stu-id="a9042-200">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="a9042-201">Для идентификаторов ресурсов хранение будет применяться только к содержимому, для которого указана пара *свойство:значение*.</span><span class="sxs-lookup"><span data-stu-id="a9042-201">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="a9042-202">Если идентификатор ресурса не указан, ко всему содержимому с метками для такого типа событий будет применена одна и та же дата хранения.</span><span class="sxs-lookup"><span data-stu-id="a9042-202">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="a9042-203">Например, если используется свойство "ИД ресурса", введите `ComplianceAssetID:<value>` в поле идентификаторов ресурсов, показанное ниже.</span><span class="sxs-lookup"><span data-stu-id="a9042-203">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="a9042-204">Возможно, к документам, связанным с этим типом события, в вашей организации применяются другие идентификаторы и свойства.</span><span class="sxs-lookup"><span data-stu-id="a9042-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="a9042-205">Например, если вам нужно найти записи, относящиеся к конкретному продукту, вы можете использовать в качестве идентификатора сочетание настраиваемого свойства ProductID и значения XYZ.</span><span class="sxs-lookup"><span data-stu-id="a9042-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="a9042-206">В этом случае следует ввести `ProductID:XYZ` в поле идентификаторов ресурсов, показанное на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="a9042-206">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="a9042-207">Для элементов Exchange нужно использовать ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="a9042-207">For Exchange items, use keywords.</span></span> <span data-ttu-id="a9042-208">Можно использовать запрос с логическими операторами поиска, такими как "И", "ИЛИ" или "НЕ".</span><span class="sxs-lookup"><span data-stu-id="a9042-208">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="a9042-209">Дополнительные сведения см. в статье [Запросы по ключевым словам и условия для поиска содержимого](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="a9042-209">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="a9042-210">Наконец, выберите дату, когда произошло событие; эта дата используется как начало срока хранения.</span><span class="sxs-lookup"><span data-stu-id="a9042-210">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="a9042-211">После создания события эта дата события синхронизируется со всем содержимым с меткой хранения этого типа события, идентификатором ресурса и ключевыми словами.</span><span class="sxs-lookup"><span data-stu-id="a9042-211">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="a9042-212">Такая синхронизация, как и для любых других меток хранения, может занять до 7 дней.</span><span class="sxs-lookup"><span data-stu-id="a9042-212">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![Страница параметров события](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="a9042-214">После создания события параметры хранения вступят в силу для контента, который уже снабжен метками и индексирован.</span><span class="sxs-lookup"><span data-stu-id="a9042-214">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="a9042-215">Если метка хранения добавляется к новому контенту после создания события, необходимо создать другое событие с теми же данными.</span><span class="sxs-lookup"><span data-stu-id="a9042-215">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="a9042-216">Удаление события не отменяет параметры хранения, которые вступили в действие в отношении контента, который уже снабжен меткой.</span><span class="sxs-lookup"><span data-stu-id="a9042-216">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="a9042-217">Чтобы сделать это, создайте событие с теми же данными, но оставьте поле даты пустым.</span><span class="sxs-lookup"><span data-stu-id="a9042-217">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="a9042-218">Использование средства "Поиск контента" для поиска всего контента с определенной меткой или определенным идентификатором ресурса</span><span class="sxs-lookup"><span data-stu-id="a9042-218">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="a9042-219">После назначения меток хранения контенту можно использовать поиск контента, чтобы найти весь контент, обозначенный определенной меткой хранения или содержащий определенный идентификатор ресурса.</span><span class="sxs-lookup"><span data-stu-id="a9042-219">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="a9042-220">Чтобы найти весь контент с определенной меткой хранения, выберите условие **Метка хранения**, а затем введите полное имя метки или его часть с использованием подстановочного знака.</span><span class="sxs-lookup"><span data-stu-id="a9042-220">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="a9042-221">Чтобы найти весь контент с определенным идентификатором ресурса, введите свойство **ComplianceAssetID** и значение, используя формат `ComplianceAssetID:<value>`.</span><span class="sxs-lookup"><span data-stu-id="a9042-221">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="a9042-222">Дополнительные сведения см. в статье [Запросы по ключевым словам и условия для средства "Поиск контента"](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="a9042-222">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="a9042-223">Разрешения</span><span class="sxs-lookup"><span data-stu-id="a9042-223">Permissions</span></span>

<span data-ttu-id="a9042-p129">Чтобы получить доступ к странице **События**, проверяющие должны быть членами группы ролей, включающей роли **Управление ликвидацией** и **Журналы аудита только для просмотра**. Рекомендуем создать новую группу ролей под названием "Проверяющие ликвидацию" и добавить в нее сначала эти две роли, а затем членов.</span><span class="sxs-lookup"><span data-stu-id="a9042-p129">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="a9042-226">Дополнительные сведения см. в статье [Предоставление пользователям доступа к Центру безопасности и соответствия требованиям Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a9042-226">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="a9042-227">Автоматизация событий с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="a9042-227">Automate events by using PowerShell</span></span>

<span data-ttu-id="a9042-228">Для автоматизации хранения на основе событий в бизнес-приложениях можно использовать сценарий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a9042-228">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="a9042-229">Командлеты PowerShell, доступные для хранения на основе событий:</span><span class="sxs-lookup"><span data-stu-id="a9042-229">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="a9042-230">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="a9042-230">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="a9042-231">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="a9042-231">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="a9042-232">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="a9042-232">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="a9042-233">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="a9042-233">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="a9042-234">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="a9042-234">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="a9042-235">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="a9042-235">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="a9042-236">Автоматизация событий с помощью REST API</span><span class="sxs-lookup"><span data-stu-id="a9042-236">Automate events by using a REST API</span></span>

<span data-ttu-id="a9042-237">Можно использовать REST API для автоматического создания событий, инициирующих начало срока хранения.</span><span class="sxs-lookup"><span data-stu-id="a9042-237">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="a9042-238">REST API — это конечная точка службы, поддерживающая наборы операций HTTP (методы), которые обеспечивают создание, получение, обновление и удаление доступа к ресурсам службы.</span><span class="sxs-lookup"><span data-stu-id="a9042-238">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="a9042-239">Дополнительные сведения см. в статье [Компоненты запросов и откликов REST API](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="a9042-239">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="a9042-240">С помощью REST API Microsoft 365 можно создавать и получать события методами POST и GET.</span><span class="sxs-lookup"><span data-stu-id="a9042-240">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="a9042-241">Существует два способа использования REST API:</span><span class="sxs-lookup"><span data-stu-id="a9042-241">There are two options for using the REST API:</span></span>

- <span data-ttu-id="a9042-242">**Microsoft Power Automate или аналогичное приложение** для автоматического запуска события.</span><span class="sxs-lookup"><span data-stu-id="a9042-242">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="a9042-243">Microsoft Power Automate — это оркестратор для подключения к другим системам, поэтому не потребуется создавать собственное настраиваемое решение.</span><span class="sxs-lookup"><span data-stu-id="a9042-243">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="a9042-244">Дополнительные сведения см. на [веб-сайте Power Automate](https://flow.microsoft.com/ru-RU/).</span><span class="sxs-lookup"><span data-stu-id="a9042-244">For more information, see the [Power Automate website](https://flow.microsoft.com/ru-RU/).</span></span>

- <span data-ttu-id="a9042-245">**PowerShell или HTTP-клиент, вызывающий REST API** для создания событий с помощью PowerShell (версии 6 или более поздней), входящего в состав настраиваемого решения.</span><span class="sxs-lookup"><span data-stu-id="a9042-245">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="a9042-246">Перед использованием REST API пользователю, имеющему права глобального администратора, необходимо подтвердить URL-адрес, используемый для вызова события хранения.</span><span class="sxs-lookup"><span data-stu-id="a9042-246">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="a9042-247">Для этого выполните вызов события хранения GET, используя URL-адрес REST API:</span><span class="sxs-lookup"><span data-stu-id="a9042-247">To do this, run a GET retention event call by using the REST API URL:</span></span>

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="a9042-248">Проверьте код отклика.</span><span class="sxs-lookup"><span data-stu-id="a9042-248">Check the response code.</span></span> <span data-ttu-id="a9042-249">Если это 302, получите перенаправленный URL-адрес в свойстве "Location" заголовка отклика и используйте этот URL-адрес вместо `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` в приведенных ниже инструкциях.</span><span class="sxs-lookup"><span data-stu-id="a9042-249">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="a9042-250">События, создающиеся автоматически, можно проверить: откройте Центр соответствия требованиям Microsoft 365 > **Управление записями** >  **События**.</span><span class="sxs-lookup"><span data-stu-id="a9042-250">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="a9042-251">Используйте Microsoft Power Automate для создания события</span><span class="sxs-lookup"><span data-stu-id="a9042-251">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="a9042-252">Создайте процесс, создающий событие с помощью REST API Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="a9042-252">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Использование Flow для создания события](../media/automate-event-driven-retention-flow-1.png)

![Использование Flow для вызова REST API](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="a9042-255">Создание события</span><span class="sxs-lookup"><span data-stu-id="a9042-255">Create an event</span></span>

<span data-ttu-id="a9042-256">Пример кода для вызова REST API:</span><span class="sxs-lookup"><span data-stu-id="a9042-256">Sample code to call the REST API:</span></span>

- <span data-ttu-id="a9042-257">**Метод**: POST</span><span class="sxs-lookup"><span data-stu-id="a9042-257">**Method**: POST</span></span>
- <span data-ttu-id="a9042-258">**URL-адрес**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="a9042-258">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="a9042-259">**Заголовки**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="a9042-259">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="a9042-260">**Текст**:</span><span class="sxs-lookup"><span data-stu-id="a9042-260">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- <span data-ttu-id="a9042-261">**Проверка подлинности**: обычная</span><span class="sxs-lookup"><span data-stu-id="a9042-261">**Authentication**: Basic</span></span>
- <span data-ttu-id="a9042-262">**Имя пользователя**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="a9042-262">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="a9042-263">**Пароль**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="a9042-263">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="a9042-264">Доступные параметры</span><span class="sxs-lookup"><span data-stu-id="a9042-264">Available parameters</span></span>


|<span data-ttu-id="a9042-265">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9042-265">Parameters</span></span>|<span data-ttu-id="a9042-266">Описание</span><span class="sxs-lookup"><span data-stu-id="a9042-266">Description</span></span>|<span data-ttu-id="a9042-267">Примечания</span><span class="sxs-lookup"><span data-stu-id="a9042-267">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="a9042-268"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="a9042-268"><d:Name></d:Name></span></span>|<span data-ttu-id="a9042-269">Указание уникального имени события.</span><span class="sxs-lookup"><span data-stu-id="a9042-269">Provide a unique name for the event,</span></span>|<span data-ttu-id="a9042-270">Нельзя использовать конечные пробелы и следующие символы: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="a9042-270">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="a9042-271">, : ;</span><span class="sxs-lookup"><span data-stu-id="a9042-271">, : ;</span></span>|
|<span data-ttu-id="a9042-272"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="a9042-272"><d:EventType></d:EventType></span></span>|<span data-ttu-id="a9042-273">Введите название типа события (или Guid).</span><span class="sxs-lookup"><span data-stu-id="a9042-273">Enter event type name (or Guid),</span></span>|<span data-ttu-id="a9042-274">Пример: "Увольнение сотрудника".</span><span class="sxs-lookup"><span data-stu-id="a9042-274">Example: "Employee termination".</span></span> <span data-ttu-id="a9042-275">Тип событий должен быть связан с меткой хранения.</span><span class="sxs-lookup"><span data-stu-id="a9042-275">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="a9042-276"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="a9042-276"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="a9042-277">Введите "ComplianceAssetId:" + идентификатор сотрудника</span><span class="sxs-lookup"><span data-stu-id="a9042-277">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="a9042-278">Пример: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="a9042-278">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="a9042-279"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="a9042-279"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="a9042-280">Дата и время события</span><span class="sxs-lookup"><span data-stu-id="a9042-280">Event Date and Time</span></span>|<span data-ttu-id="a9042-281">Формат: ГГГГ-ММ-ДДTчч:мм:ссZ. Пример: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="a9042-281">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="a9042-282">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="a9042-282">Response codes</span></span>

| <span data-ttu-id="a9042-283">Код ответа</span><span class="sxs-lookup"><span data-stu-id="a9042-283">Response Code</span></span> | <span data-ttu-id="a9042-284">Описание</span><span class="sxs-lookup"><span data-stu-id="a9042-284">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="a9042-285">302</span><span class="sxs-lookup"><span data-stu-id="a9042-285">302</span></span>               | <span data-ttu-id="a9042-286">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="a9042-286">Redirect</span></span>              |
| <span data-ttu-id="a9042-287">201</span><span class="sxs-lookup"><span data-stu-id="a9042-287">201</span></span>               | <span data-ttu-id="a9042-288">Создано</span><span class="sxs-lookup"><span data-stu-id="a9042-288">Created</span></span>               |
| <span data-ttu-id="a9042-289">403</span><span class="sxs-lookup"><span data-stu-id="a9042-289">403</span></span>               | <span data-ttu-id="a9042-290">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="a9042-290">Authorization Failed</span></span>  |
| <span data-ttu-id="a9042-291">401</span><span class="sxs-lookup"><span data-stu-id="a9042-291">401</span></span>               | <span data-ttu-id="a9042-292">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a9042-292">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="a9042-293">Получение событий на основе диапазона времени</span><span class="sxs-lookup"><span data-stu-id="a9042-293">Get events based on a time range</span></span>

- <span data-ttu-id="a9042-294">**Метод**: GET</span><span class="sxs-lookup"><span data-stu-id="a9042-294">**Method**: GET</span></span>

- <span data-ttu-id="a9042-295">**URL-адрес**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="a9042-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="a9042-296">**Заголовки**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="a9042-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="a9042-297">**Проверка подлинности**: обычная</span><span class="sxs-lookup"><span data-stu-id="a9042-297">**Authentication**: Basic</span></span>

- <span data-ttu-id="a9042-298">**Имя пользователя**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="a9042-298">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="a9042-299">**Пароль**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="a9042-299">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="a9042-300">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="a9042-300">Response codes</span></span>

| <span data-ttu-id="a9042-301">Код ответа</span><span class="sxs-lookup"><span data-stu-id="a9042-301">Response Code</span></span> | <span data-ttu-id="a9042-302">Описание</span><span class="sxs-lookup"><span data-stu-id="a9042-302">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="a9042-303">200</span><span class="sxs-lookup"><span data-stu-id="a9042-303">200</span></span>               | <span data-ttu-id="a9042-304">Все в порядке, список событий в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="a9042-304">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="a9042-305">404</span><span class="sxs-lookup"><span data-stu-id="a9042-305">404</span></span>               | <span data-ttu-id="a9042-306">Не найдено</span><span class="sxs-lookup"><span data-stu-id="a9042-306">Not found</span></span>                         |
| <span data-ttu-id="a9042-307">302</span><span class="sxs-lookup"><span data-stu-id="a9042-307">302</span></span>               | <span data-ttu-id="a9042-308">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="a9042-308">Redirect</span></span>                          |
| <span data-ttu-id="a9042-309">401</span><span class="sxs-lookup"><span data-stu-id="a9042-309">401</span></span>               | <span data-ttu-id="a9042-310">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="a9042-310">Authorization Failed</span></span>              |
| <span data-ttu-id="a9042-311">403</span><span class="sxs-lookup"><span data-stu-id="a9042-311">403</span></span>               | <span data-ttu-id="a9042-312">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a9042-312">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="a9042-313">Получение события по идентификатору</span><span class="sxs-lookup"><span data-stu-id="a9042-313">Get an event by ID</span></span>

- <span data-ttu-id="a9042-314">**Метод**: GET</span><span class="sxs-lookup"><span data-stu-id="a9042-314">**Method**: GET</span></span>

- <span data-ttu-id="a9042-315">**URL-адрес**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="a9042-315">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="a9042-316">**Заголовки**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="a9042-316">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="a9042-317">**Проверка подлинности**: обычная</span><span class="sxs-lookup"><span data-stu-id="a9042-317">**Authentication**: Basic</span></span>

- <span data-ttu-id="a9042-318">**Имя пользователя**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="a9042-318">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="a9042-319">**Пароль**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="a9042-319">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="a9042-320">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="a9042-320">Response codes</span></span>

| <span data-ttu-id="a9042-321">Код ответа</span><span class="sxs-lookup"><span data-stu-id="a9042-321">Response Code</span></span> | <span data-ttu-id="a9042-322">Описание</span><span class="sxs-lookup"><span data-stu-id="a9042-322">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="a9042-323">200</span><span class="sxs-lookup"><span data-stu-id="a9042-323">200</span></span>               | <span data-ttu-id="a9042-324">Все в порядке, текст ответа содержит событие в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="a9042-324">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="a9042-325">404</span><span class="sxs-lookup"><span data-stu-id="a9042-325">404</span></span>               | <span data-ttu-id="a9042-326">Не найдено</span><span class="sxs-lookup"><span data-stu-id="a9042-326">Not found</span></span>                                            |
| <span data-ttu-id="a9042-327">302</span><span class="sxs-lookup"><span data-stu-id="a9042-327">302</span></span>               | <span data-ttu-id="a9042-328">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="a9042-328">Redirect</span></span>                                             |
| <span data-ttu-id="a9042-329">401</span><span class="sxs-lookup"><span data-stu-id="a9042-329">401</span></span>               | <span data-ttu-id="a9042-330">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="a9042-330">Authorization Failed</span></span>                                 |
| <span data-ttu-id="a9042-331">403</span><span class="sxs-lookup"><span data-stu-id="a9042-331">403</span></span>               | <span data-ttu-id="a9042-332">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a9042-332">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="a9042-333">Получение события по имени</span><span class="sxs-lookup"><span data-stu-id="a9042-333">Get an event by name</span></span>

- <span data-ttu-id="a9042-334">**Метод**: GET</span><span class="sxs-lookup"><span data-stu-id="a9042-334">**Method**: GET</span></span>

- <span data-ttu-id="a9042-335">**URL-адрес**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="a9042-335">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="a9042-336">**Заголовки**: Key = Content-Type, Value = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="a9042-336">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="a9042-337">**Проверка подлинности**: обычная</span><span class="sxs-lookup"><span data-stu-id="a9042-337">**Authentication**: Basic</span></span>

- <span data-ttu-id="a9042-338">**Имя пользователя**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="a9042-338">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="a9042-339">**Пароль**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="a9042-339">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="a9042-340">Коды ответа</span><span class="sxs-lookup"><span data-stu-id="a9042-340">Response codes</span></span>

| <span data-ttu-id="a9042-341">Код ответа</span><span class="sxs-lookup"><span data-stu-id="a9042-341">Response Code</span></span> | <span data-ttu-id="a9042-342">Описание</span><span class="sxs-lookup"><span data-stu-id="a9042-342">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="a9042-343">200</span><span class="sxs-lookup"><span data-stu-id="a9042-343">200</span></span>               | <span data-ttu-id="a9042-344">Все в порядке, текст ответа содержит событие в формате atom+xml</span><span class="sxs-lookup"><span data-stu-id="a9042-344">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="a9042-345">404</span><span class="sxs-lookup"><span data-stu-id="a9042-345">404</span></span>               | <span data-ttu-id="a9042-346">Не найдено</span><span class="sxs-lookup"><span data-stu-id="a9042-346">Not found</span></span>                                            |
| <span data-ttu-id="a9042-347">302</span><span class="sxs-lookup"><span data-stu-id="a9042-347">302</span></span>               | <span data-ttu-id="a9042-348">Перенаправление</span><span class="sxs-lookup"><span data-stu-id="a9042-348">Redirect</span></span>                                             |
| <span data-ttu-id="a9042-349">401</span><span class="sxs-lookup"><span data-stu-id="a9042-349">401</span></span>               | <span data-ttu-id="a9042-350">Сбой авторизации</span><span class="sxs-lookup"><span data-stu-id="a9042-350">Authorization Failed</span></span>                                 |
| <span data-ttu-id="a9042-351">403</span><span class="sxs-lookup"><span data-stu-id="a9042-351">403</span></span>               | <span data-ttu-id="a9042-352">Сбой проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="a9042-352">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="a9042-353">Используйте PowerShell или любой HTTP-клиент для создания события</span><span class="sxs-lookup"><span data-stu-id="a9042-353">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="a9042-354">Требуется PowerShell версии 6 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="a9042-354">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="a9042-355">В сеансе PowerShell выполните следующий сценарий:</span><span class="sxs-lookup"><span data-stu-id="a9042-355">In a PowerShell session, run the following script:</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```

