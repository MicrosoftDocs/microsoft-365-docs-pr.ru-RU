---
title: Справка по формату скос для таксономии SharePoint
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: Справка по формату скос для таксономии SharePoint
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296083"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="268b0-103">Справка по формату скос для таксономии SharePoint</span><span class="sxs-lookup"><span data-stu-id="268b0-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="268b0-104">Эта статья включает словарь РДФ, используемый для представления [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) и основанный на [скос](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="268b0-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="268b0-105">Для сериализации этого синтаксиса РДФ используйте РДФ [Turtle](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="268b0-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="268b0-106">В следующей таблице приведены эквиваленты [скос](https://www.w3.org/TR/skos-primer/) для словаря [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) .</span><span class="sxs-lookup"><span data-stu-id="268b0-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="268b0-107">SharePoint не поддерживает значения [скос](https://www.w3.org/TR/skos-primer/) , которые не имеют эквивалентов таксономии для таксономии SharePoint.</span><span class="sxs-lookup"><span data-stu-id="268b0-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="268b0-108">Таксономия SharePoint</span><span class="sxs-lookup"><span data-stu-id="268b0-108">SharePoint taxonomy</span></span>|<span data-ttu-id="268b0-109">Эквивалент скос</span><span class="sxs-lookup"><span data-stu-id="268b0-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="268b0-110">SharePoint — Таксономия: термин</span><span class="sxs-lookup"><span data-stu-id="268b0-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="268b0-111">Скос: концепция</span><span class="sxs-lookup"><span data-stu-id="268b0-111">skos:Concept</span></span>|
|<span data-ttu-id="268b0-112">SharePoint — Таксономия: набор терминов</span><span class="sxs-lookup"><span data-stu-id="268b0-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="268b0-113">Скос: Концептсчеме</span><span class="sxs-lookup"><span data-stu-id="268b0-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="268b0-114">SharePoint — Таксономия: "набор терминов"</span><span class="sxs-lookup"><span data-stu-id="268b0-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="268b0-115">Скос: схема</span><span class="sxs-lookup"><span data-stu-id="268b0-115">skos:inScheme</span></span>|
|<span data-ttu-id="268b0-116">SharePoint — Таксономия: Хастоплевелтерм</span><span class="sxs-lookup"><span data-stu-id="268b0-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="268b0-117">Скос: Хастопконцепт</span><span class="sxs-lookup"><span data-stu-id="268b0-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="268b0-118">SharePoint — Таксономия: Топлевелтермоф</span><span class="sxs-lookup"><span data-stu-id="268b0-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="268b0-119">Скос: Топконцептоф</span><span class="sxs-lookup"><span data-stu-id="268b0-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="268b0-120">SharePoint — Таксономия: Дефаултлабел</span><span class="sxs-lookup"><span data-stu-id="268b0-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="268b0-121">Скос: Префлабел</span><span class="sxs-lookup"><span data-stu-id="268b0-121">skos:prefLabel</span></span>|
|<span data-ttu-id="268b0-122">SharePoint — Таксономия: Термсетнаме</span><span class="sxs-lookup"><span data-stu-id="268b0-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="268b0-123">Скос: Префлабел</span><span class="sxs-lookup"><span data-stu-id="268b0-123">skos:prefLabel</span></span>|
|<span data-ttu-id="268b0-124">SharePoint — Таксономия: propertyName</span><span class="sxs-lookup"><span data-stu-id="268b0-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="268b0-125">Скос: Префлабел</span><span class="sxs-lookup"><span data-stu-id="268b0-125">skos:prefLabel</span></span>|
|<span data-ttu-id="268b0-126">SharePoint — Таксономия: Осерлабел</span><span class="sxs-lookup"><span data-stu-id="268b0-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="268b0-127">Скос: Алтлабел</span><span class="sxs-lookup"><span data-stu-id="268b0-127">skos:altLabel</span></span>|
|<span data-ttu-id="268b0-128">SharePoint — Таксономия: описание</span><span class="sxs-lookup"><span data-stu-id="268b0-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="268b0-129">Скос: определение</span><span class="sxs-lookup"><span data-stu-id="268b0-129">skos:definition</span></span>|
|<span data-ttu-id="268b0-130">SharePoint — Таксономия: родительский элемент</span><span class="sxs-lookup"><span data-stu-id="268b0-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="268b0-131">Скос: широкий</span><span class="sxs-lookup"><span data-stu-id="268b0-131">skos:broader</span></span>|
|<span data-ttu-id="268b0-132">SharePoint — Таксономия: дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="268b0-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="268b0-133">Скос: более узкий</span><span class="sxs-lookup"><span data-stu-id="268b0-133">skos:narrower</span></span>|

<span data-ttu-id="268b0-134">В следующей таблице показаны сущности словаря таксономии SharePoint, полученные из [ОВЛ](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="268b0-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="268b0-135">Словарь таксономии SharePoint</span><span class="sxs-lookup"><span data-stu-id="268b0-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="268b0-136">Производный от ОВЛ</span><span class="sxs-lookup"><span data-stu-id="268b0-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="268b0-137">SharePoint — Таксономия: Исаваилаблефортаггинг</span><span class="sxs-lookup"><span data-stu-id="268b0-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="268b0-138">ОВЛ: дататипепроперти</span><span class="sxs-lookup"><span data-stu-id="268b0-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="268b0-139">SharePoint — Таксономия: Шаредкустомпропертифортерм</span><span class="sxs-lookup"><span data-stu-id="268b0-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="268b0-140">ОВЛ: Обжектпроперти</span><span class="sxs-lookup"><span data-stu-id="268b0-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="268b0-141">SharePoint — Таксономия: Локалкустомпропертифортерм</span><span class="sxs-lookup"><span data-stu-id="268b0-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="268b0-142">ОВЛ: Обжектпроперти</span><span class="sxs-lookup"><span data-stu-id="268b0-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="268b0-143">SharePoint — Таксономия: Кустомпропертифортермсет</span><span class="sxs-lookup"><span data-stu-id="268b0-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="268b0-144">ОВЛ: Обжектпроперти</span><span class="sxs-lookup"><span data-stu-id="268b0-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="268b0-145">Словарь таксономии SharePoint</span><span class="sxs-lookup"><span data-stu-id="268b0-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="268b0-146">Таксономия это формально система классификации.</span><span class="sxs-lookup"><span data-stu-id="268b0-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="268b0-147">Таксономия группирует слова, метки и термины, описывающие что-то, а затем упорядочивает группы в иерархию.</span><span class="sxs-lookup"><span data-stu-id="268b0-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="268b0-148">**SharePoint — Таксономия: термин**</span><span class="sxs-lookup"><span data-stu-id="268b0-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="268b0-149">Представляет термин или ключевое слово в иерархии управляемых метаданных.</span><span class="sxs-lookup"><span data-stu-id="268b0-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="268b0-150">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) — это атомарная единица [банка терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)SharePoint.</span><span class="sxs-lookup"><span data-stu-id="268b0-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="268b0-151">Каждый [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) относится к набору [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) , который принадлежит к [термграуп](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="268b0-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="268b0-152">Для определения [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="268b0-153">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) компулсорили существует в наборе [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="268b0-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="268b0-154">Дефаултлабел — это имя [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в том виде, в котором оно отображается в визуальном представлении.</span><span class="sxs-lookup"><span data-stu-id="268b0-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="268b0-155">Обязательные поля для определения [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) включают:</span><span class="sxs-lookup"><span data-stu-id="268b0-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="268b0-156">SharePoint — Таксономия: Дефаултлабел</span><span class="sxs-lookup"><span data-stu-id="268b0-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="268b0-157">SharePoint — Таксономия: "набор терминов"</span><span class="sxs-lookup"><span data-stu-id="268b0-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="268b0-158">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) может:</span><span class="sxs-lookup"><span data-stu-id="268b0-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="268b0-159">Иерархическая связь с другим [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) , при условии, что оба [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) относятся к одному и тому же набору [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="268b0-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="268b0-160">Иметь несколько дочерних [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), но только один родительский [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="268b0-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="268b0-161">Не определен родительский [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) , если он является топлевелтермоф набором [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="268b0-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="268b0-162">Один Дефаултлабел для каждого рабочего языка [банка терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="268b0-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="268b0-163">Не существует, если он не содержит родительских [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), а топлевелтермоф не является набором [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="268b0-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="268b0-164">Иметь только уникальный Дефаултлабел на одном иерархическом уровне.</span><span class="sxs-lookup"><span data-stu-id="268b0-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="268b0-165">**SharePoint — Таксономия: набор терминов**</span><span class="sxs-lookup"><span data-stu-id="268b0-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="268b0-166">Представляет иерархический или плоский набор объектов Term, известных как "набор терминов".</span><span class="sxs-lookup"><span data-stu-id="268b0-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="268b0-167">Как видно из названия, набор терминов называется набором [терминов.](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)</span><span class="sxs-lookup"><span data-stu-id="268b0-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="268b0-168">[Термин в банке](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) [терминов должен](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) принадлежать к набору [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="268b0-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="268b0-169">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) не может существовать независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="268b0-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="268b0-170">Для определения набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="268b0-171">[Термсетс](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) логически группируются в [термграупс](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="268b0-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="268b0-172">Для определения набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) необходимо обязательное поле:</span><span class="sxs-lookup"><span data-stu-id="268b0-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="268b0-173">SharePoint — Таксономия: Термсетнаме</span><span class="sxs-lookup"><span data-stu-id="268b0-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="268b0-174">В случае указанного Термсетнаме не является уникальным в [термграуп](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint добавляет в конец имени число, чтобы поддерживать уникальность термсетнаме (s).</span><span class="sxs-lookup"><span data-stu-id="268b0-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharPoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="268b0-175">**SharePoint — Таксономия: Хастоплевелтерм**</span><span class="sxs-lookup"><span data-stu-id="268b0-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="268b0-176">SharePoint использует это свойство, чтобы сопоставить самый верхний [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в наборе [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), который является точкой входа в иерархию [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в наборе [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="268b0-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="268b0-177">Это обратное отношение к SharePoint — Таксономия: Топлевелтермоф.</span><span class="sxs-lookup"><span data-stu-id="268b0-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="268b0-178">Для определения используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="268b0-179">Невозможно определить [условие](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) верхнего уровня родительского [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="268b0-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="268b0-180">**SharePoint — Таксономия: Топлевелтермоф**</span><span class="sxs-lookup"><span data-stu-id="268b0-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="268b0-181">SharePoint — Таксономия: Топлевелтермоф — это обратное значение SharePoint — Таксономия: Хастоплевелтерм</span><span class="sxs-lookup"><span data-stu-id="268b0-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="268b0-182">Для определения используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="268b0-183">**SharePoint — Таксономия: "набор терминов"**</span><span class="sxs-lookup"><span data-stu-id="268b0-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="268b0-184">Используйте этот элемент, чтобы сопоставить [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) с набором [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="268b0-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="268b0-185">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) может существовать только в едином наборе [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="268b0-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="268b0-186">В SharePoint это свойство требуется при [определении термина](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="268b0-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="268b0-187">Обязательные метки</span><span class="sxs-lookup"><span data-stu-id="268b0-187">Required labels</span></span>

<span data-ttu-id="268b0-188">Прежде чем приступать к использованию управляемых метаданных, в Организации может потребоваться тщательное планирование.</span><span class="sxs-lookup"><span data-stu-id="268b0-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="268b0-189">Предполагаемый объем планирования зависит от того, насколько формальным является таксономия.</span><span class="sxs-lookup"><span data-stu-id="268b0-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="268b0-190">Он также зависит от того, какой элемент управления требуется применить к метаданным.</span><span class="sxs-lookup"><span data-stu-id="268b0-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="268b0-191">На каждом уровне иерархии необходимо настроить обязательные метка для термина или набора терминов.</span><span class="sxs-lookup"><span data-stu-id="268b0-191">At each level of the hierarchy, you need to configure required lables for a Term or TermSet.</span></span>

<span data-ttu-id="268b0-192">Термин может иметь одну или несколько меток на языке по умолчанию, а также ноль или более меток на языке, отличном от используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="268b0-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="268b0-193">Если термин содержит метки на языке, одна из меток должна быть меткой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="268b0-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="268b0-194">**SharePoint — Таксономия: Дефаултлабел**</span><span class="sxs-lookup"><span data-stu-id="268b0-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="268b0-195">Используйте эту лексическую метку по умолчанию для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) , который является обязательным параметром для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="268b0-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="268b0-196">Используется для визуального представления [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="268b0-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="268b0-197">Для определения Дефаултлабел используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="268b0-198">Дефаултлабел содержит две части — строку и тег языка.</span><span class="sxs-lookup"><span data-stu-id="268b0-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="268b0-199">Язык должен быть одним из рабочих языков [банка терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="268b0-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="268b0-200">Дефаултлабел должны быть уникальными для всех [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в одном и том же наборе [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)на том же уровне иерархии.</span><span class="sxs-lookup"><span data-stu-id="268b0-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="268b0-201">**SharePoint — Таксономия: Термсетнаме**</span><span class="sxs-lookup"><span data-stu-id="268b0-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="268b0-202">Получает и задает имя текущего объекта набора терминов.</span><span class="sxs-lookup"><span data-stu-id="268b0-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="268b0-203">Это лексическая подпись для набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)в рабочем языке [банка терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="268b0-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="268b0-204">Это обязательный параметр для набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="268b0-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="268b0-205">Используется для визуального представления набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="268b0-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="268b0-206">Для определения Термсетнаме используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="268b0-207">**SharePoint — Таксономия: propertyName**</span><span class="sxs-lookup"><span data-stu-id="268b0-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="268b0-208">Получает и задает имя свойства для текущего объекта набора терминов.</span><span class="sxs-lookup"><span data-stu-id="268b0-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="268b0-209">Это лексическая метка для SharePoint — Таксономия: Шаредкустомпропертифортерм, SharePoint-Таксономия: Локалкустомпропертифортерм и SharePoint-Таксономия: Кустомпропертифортермсет на рабочем языке [банка терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .</span><span class="sxs-lookup"><span data-stu-id="268b0-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="268b0-210">SharePoint — Таксономия: propertyName рассматривается как ключ CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="268b0-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="268b0-211">Для определения Пропетинаме используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="268b0-212">Необязательные метки</span><span class="sxs-lookup"><span data-stu-id="268b0-212">Optional labels</span></span>

<span data-ttu-id="268b0-213">Вы также можете добавить необязательные метки в таксономию.</span><span class="sxs-lookup"><span data-stu-id="268b0-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="268b0-214">**SharePoint — Таксономия: Осерлабел**</span><span class="sxs-lookup"><span data-stu-id="268b0-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="268b0-215">Это альтернативная лексическая метка для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="268b0-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="268b0-216">Для определения Осерлабел используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="268b0-217">Семантические связи</span><span class="sxs-lookup"><span data-stu-id="268b0-217">Semantic relationships</span></span>

<span data-ttu-id="268b0-218">Таксономии имеют иерархию и иногда простой ассоциативной связи "связанный термин", но некоторые имеют "семантические связи" или созданные пользователем связи.</span><span class="sxs-lookup"><span data-stu-id="268b0-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="268b0-219">**SharePoint — Таксономия: родительский элемент**</span><span class="sxs-lookup"><span data-stu-id="268b0-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="268b0-220">Это иерархически связывает [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) с другим [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="268b0-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="268b0-221">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) может быть [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) верхнего уровня набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), но в случае, если он не должен иметь родительский [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="268b0-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="268b0-222">Для определения родителя используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="268b0-223">Это означает, что у TermA1 есть родительский термин.</span><span class="sxs-lookup"><span data-stu-id="268b0-223">This means that TermA1 has parent TermA.</span></span> <span data-ttu-id="268b0-224">Кроме того, это означает, что TermA1 является дочерним по отношению к терму Term.</span><span class="sxs-lookup"><span data-stu-id="268b0-224">Inversely it also means that TermA1 is the child of TermA.</span></span> <span data-ttu-id="268b0-225">Связь "родитель-потомок" является отношением инверсибле.</span><span class="sxs-lookup"><span data-stu-id="268b0-225">Parent-child relationship is an inversible relationship.</span></span>

<span data-ttu-id="268b0-226">**SharePoint — Таксономия: дочерний элемент**</span><span class="sxs-lookup"><span data-stu-id="268b0-226">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="268b0-227">Объект содержит один или несколько дочерних экземпляров набора терминов, и к ним можно получить доступ с помощью свойства Термсетс.</span><span class="sxs-lookup"><span data-stu-id="268b0-227">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="268b0-228">Этот класс также предоставляет методы для создания новых дочерних объектов набора терминов.</span><span class="sxs-lookup"><span data-stu-id="268b0-228">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="268b0-229">В группе заданы разрешения для редактирования дочерних терминов и экземпляров набора терминов.</span><span class="sxs-lookup"><span data-stu-id="268b0-229">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="268b0-230">Это иерархически связывает [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) с другим [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="268b0-230">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="268b0-231">Синтаксис для определения дочернего элемента:</span><span class="sxs-lookup"><span data-stu-id="268b0-231">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="268b0-232">Это означает, что Term имеет дочерний TermA1.</span><span class="sxs-lookup"><span data-stu-id="268b0-232">This means that TermA has child TermA1.</span></span> <span data-ttu-id="268b0-233">Кроме того, это означает, что термин "родитель" отношения "родитель-потомок" TermA1 является отношением инверсибле.</span><span class="sxs-lookup"><span data-stu-id="268b0-233">Inversely it also means that TermA is the parent of TermA1 parent-child relationship is an inversible relationship.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="268b0-234">Заметки к документации</span><span class="sxs-lookup"><span data-stu-id="268b0-234">Documentation notes</span></span>

<span data-ttu-id="268b0-235">В этом разделе рассматривается таксономия, подробно описанная в пространстве имен Microsoft. SharePoint. таксономии.</span><span class="sxs-lookup"><span data-stu-id="268b0-235">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="268b0-236">**SharePoint — Таксономия: описание**</span><span class="sxs-lookup"><span data-stu-id="268b0-236">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="268b0-237">Это подробное описание объекта словаря [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) .</span><span class="sxs-lookup"><span data-stu-id="268b0-237">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="268b0-238">Для добавления описания используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-238">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="268b0-239">Настраиваемые свойства</span><span class="sxs-lookup"><span data-stu-id="268b0-239">Custom properties</span></span>

<span data-ttu-id="268b0-240">Получает коллекцию объектов настраиваемых свойств для текущего объекта Term из словаря, доступного только для чтения.</span><span class="sxs-lookup"><span data-stu-id="268b0-240">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="268b0-241">Настраиваемые свойства — это пары "ключ — значение", которые могут быть определены для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), чтобы получить описание [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="268b0-241">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="268b0-242">SharePoint определяет ключ настраиваемого свойства с помощью параметра propertyName.</span><span class="sxs-lookup"><span data-stu-id="268b0-242">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="268b0-243">**SharePoint — Таксономия: Кустомпропертифортермсет**</span><span class="sxs-lookup"><span data-stu-id="268b0-243">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="268b0-244">Для определения используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-244">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="268b0-245">**SharePoint — Таксономия: Шаредкустомпропертифортерм**</span><span class="sxs-lookup"><span data-stu-id="268b0-245">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="268b0-246">Если настраиваемое свойство [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) необходимо переносить вместе с [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), то при повторном использовании этого [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) его необходимо определить в разделе шаредкустомпропертифортерм.</span><span class="sxs-lookup"><span data-stu-id="268b0-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="268b0-247">Для определения используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-247">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="268b0-248">**SharePoint — Таксономия: Локалкустомпропертифортерм**</span><span class="sxs-lookup"><span data-stu-id="268b0-248">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="268b0-249">Если настраиваемое свойство для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) не требуется переносить вместе с [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), то при повторном использовании этого [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) необходимо определить его в локалкустомпропертифортерм.</span><span class="sxs-lookup"><span data-stu-id="268b0-249">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="268b0-250">Для определения используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-250">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="268b0-251">Свойства данных</span><span class="sxs-lookup"><span data-stu-id="268b0-251">Data properties</span></span>

<span data-ttu-id="268b0-252">На каждом уровне иерархии можно настроить определенные свойства данных для термина или набора терминов.</span><span class="sxs-lookup"><span data-stu-id="268b0-252">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="268b0-253">**SharePoint — Таксономия: Исаваилаблефортаггинг**</span><span class="sxs-lookup"><span data-stu-id="268b0-253">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="268b0-254">Используйте этот элемент, чтобы указать, доступен ли [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или набор [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) в списках и библиотеках SharePoint.</span><span class="sxs-lookup"><span data-stu-id="268b0-254">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="268b0-255">Для этого используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="268b0-255">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="268b0-256">Домен и диапазон</span><span class="sxs-lookup"><span data-stu-id="268b0-256">Domain and range</span></span>

<span data-ttu-id="268b0-257">В приведенной ниже таблице описывается домен и диапазон словаря таксономии SharePoint.</span><span class="sxs-lookup"><span data-stu-id="268b0-257">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="268b0-258">Предикаты и глаголы</span><span class="sxs-lookup"><span data-stu-id="268b0-258">Predicates/verb</span></span>|<span data-ttu-id="268b0-259">Смысл</span><span class="sxs-lookup"><span data-stu-id="268b0-259">Meaning</span></span>|<span data-ttu-id="268b0-260">Domain</span><span class="sxs-lookup"><span data-stu-id="268b0-260">Domain</span></span>|<span data-ttu-id="268b0-261">Range</span><span class="sxs-lookup"><span data-stu-id="268b0-261">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="268b0-262">набор терминов</span><span class="sxs-lookup"><span data-stu-id="268b0-262">inTermSet</span></span>|<span data-ttu-id="268b0-263">В наборе терминов</span><span class="sxs-lookup"><span data-stu-id="268b0-263">In term set</span></span>|<span data-ttu-id="268b0-264">Term</span><span class="sxs-lookup"><span data-stu-id="268b0-264">Term</span></span>|<span data-ttu-id="268b0-265">Набор терминов</span><span class="sxs-lookup"><span data-stu-id="268b0-265">Term Set</span></span>|
<span data-ttu-id="268b0-266">интермграуп</span><span class="sxs-lookup"><span data-stu-id="268b0-266">inTermGroup</span></span>|<span data-ttu-id="268b0-267">В группе терминов</span><span class="sxs-lookup"><span data-stu-id="268b0-267">In term group</span></span>|<span data-ttu-id="268b0-268">TermSet</span><span class="sxs-lookup"><span data-stu-id="268b0-268">TermSet</span></span>|<span data-ttu-id="268b0-269">термграуп</span><span class="sxs-lookup"><span data-stu-id="268b0-269">TermGroup</span></span>|
<span data-ttu-id="268b0-270">топлевелтермоф</span><span class="sxs-lookup"><span data-stu-id="268b0-270">topLevelTermOf</span></span>|<span data-ttu-id="268b0-271">— Это термин верхнего уровня</span><span class="sxs-lookup"><span data-stu-id="268b0-271">Is Top Level Term Of</span></span>|<span data-ttu-id="268b0-272">Term</span><span class="sxs-lookup"><span data-stu-id="268b0-272">Term</span></span>|<span data-ttu-id="268b0-273">TermSet</span><span class="sxs-lookup"><span data-stu-id="268b0-273">TermSet</span></span>|
<span data-ttu-id="268b0-274">хастоплевелтерм</span><span class="sxs-lookup"><span data-stu-id="268b0-274">hasTopLevelTerm</span></span>|<span data-ttu-id="268b0-275">Имеет термин верхнего уровня</span><span class="sxs-lookup"><span data-stu-id="268b0-275">Has top level term</span></span>|<span data-ttu-id="268b0-276">Набор терминов</span><span class="sxs-lookup"><span data-stu-id="268b0-276">Term Set</span></span>|<span data-ttu-id="268b0-277">Term</span><span class="sxs-lookup"><span data-stu-id="268b0-277">Term</span></span>|
<span data-ttu-id="268b0-278">термсетнаме</span><span class="sxs-lookup"><span data-stu-id="268b0-278">termSetName</span></span>|<span data-ttu-id="268b0-279">Имя набора терминов</span><span class="sxs-lookup"><span data-stu-id="268b0-279">Term set has Name</span></span>|<span data-ttu-id="268b0-280">Term</span><span class="sxs-lookup"><span data-stu-id="268b0-280">Term</span></span>|<span data-ttu-id="268b0-281">Обычный литерал</span><span class="sxs-lookup"><span data-stu-id="268b0-281">Plain literal</span></span>|
<span data-ttu-id="268b0-282">дефаултлабел</span><span class="sxs-lookup"><span data-stu-id="268b0-282">defaultLabel</span></span>|<span data-ttu-id="268b0-283">Термин имеет метку по умолчанию</span><span class="sxs-lookup"><span data-stu-id="268b0-283">Term has default label</span></span>|<span data-ttu-id="268b0-284">Term</span><span class="sxs-lookup"><span data-stu-id="268b0-284">Term</span></span>|<span data-ttu-id="268b0-285">Обычный литерал</span><span class="sxs-lookup"><span data-stu-id="268b0-285">Plain literal</span></span>|
<span data-ttu-id="268b0-286">осерлабел</span><span class="sxs-lookup"><span data-stu-id="268b0-286">otherLabel</span></span>|<span data-ttu-id="268b0-287">Термин содержит другую метку</span><span class="sxs-lookup"><span data-stu-id="268b0-287">Term has other label</span></span>|<span data-ttu-id="268b0-288">Term</span><span class="sxs-lookup"><span data-stu-id="268b0-288">Term</span></span>|<span data-ttu-id="268b0-289">Обычный литерал</span><span class="sxs-lookup"><span data-stu-id="268b0-289">Plain literal</span></span>|
<span data-ttu-id="268b0-290">propertyName</span><span class="sxs-lookup"><span data-stu-id="268b0-290">propertyName</span></span>|<span data-ttu-id="268b0-291">Имеет метку свойства</span><span class="sxs-lookup"><span data-stu-id="268b0-291">Has Property Label</span></span>|<span data-ttu-id="268b0-292">Шаредкустомпропертифортерм, Локалкустомпропертифортерм, Кустомпропертифортермсет</span><span class="sxs-lookup"><span data-stu-id="268b0-292">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="268b0-293">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="268b0-293">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="268b0-294">description</span><span class="sxs-lookup"><span data-stu-id="268b0-294">description</span></span>|<span data-ttu-id="268b0-295">Содержит описание</span><span class="sxs-lookup"><span data-stu-id="268b0-295">Has Description</span></span>|<span data-ttu-id="268b0-296">Все</span><span class="sxs-lookup"><span data-stu-id="268b0-296">All</span></span>|<span data-ttu-id="268b0-297">Обычный литерал</span><span class="sxs-lookup"><span data-stu-id="268b0-297">Plain literal</span></span>|
|<span data-ttu-id="268b0-298">родитель</span><span class="sxs-lookup"><span data-stu-id="268b0-298">parent</span></span>|<span data-ttu-id="268b0-299">Имеет родительский элемент</span><span class="sxs-lookup"><span data-stu-id="268b0-299">Has parent</span></span>|<span data-ttu-id="268b0-300">Term</span><span class="sxs-lookup"><span data-stu-id="268b0-300">Term</span></span>|<span data-ttu-id="268b0-301">Term</span><span class="sxs-lookup"><span data-stu-id="268b0-301">Term</span></span>|
|<span data-ttu-id="268b0-302">ребенка</span><span class="sxs-lookup"><span data-stu-id="268b0-302">child</span></span>|<span data-ttu-id="268b0-303">Имеет дочерний элемент</span><span class="sxs-lookup"><span data-stu-id="268b0-303">Has Child</span></span>|<span data-ttu-id="268b0-304">Term</span><span class="sxs-lookup"><span data-stu-id="268b0-304">Term</span></span>|<span data-ttu-id="268b0-305">Term</span><span class="sxs-lookup"><span data-stu-id="268b0-305">Term</span></span>|
|<span data-ttu-id="268b0-306">исаваилаблефортаггинг</span><span class="sxs-lookup"><span data-stu-id="268b0-306">isAvailableForTagging</span></span>|<span data-ttu-id="268b0-307">Доступна для тегирования</span><span class="sxs-lookup"><span data-stu-id="268b0-307">Is available for tagging</span></span>|<span data-ttu-id="268b0-308">Термин, набор терминов</span><span class="sxs-lookup"><span data-stu-id="268b0-308">Term, Term Set</span></span>|<span data-ttu-id="268b0-309">Boolean</span><span class="sxs-lookup"><span data-stu-id="268b0-309">Boolean</span></span>|
|<span data-ttu-id="268b0-310">шаредкустомпропертифортерм</span><span class="sxs-lookup"><span data-stu-id="268b0-310">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="268b0-311">Имеет общее настраиваемое свойство</span><span class="sxs-lookup"><span data-stu-id="268b0-311">Has shared custom property</span></span>|<span data-ttu-id="268b0-312">Term</span><span class="sxs-lookup"><span data-stu-id="268b0-312">Term</span></span>|<span data-ttu-id="268b0-313">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="268b0-313">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="268b0-314">локалкустомпропертифортерм</span><span class="sxs-lookup"><span data-stu-id="268b0-314">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="268b0-315">Имеет локальное настраиваемое свойство</span><span class="sxs-lookup"><span data-stu-id="268b0-315">Has local custom property</span></span>|<span data-ttu-id="268b0-316">Term</span><span class="sxs-lookup"><span data-stu-id="268b0-316">Term</span></span>|<span data-ttu-id="268b0-317">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="268b0-317">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="268b0-318">кустомпропертифортермсет</span><span class="sxs-lookup"><span data-stu-id="268b0-318">CustomPropertyForTermSet</span></span>|<span data-ttu-id="268b0-319">Имеет настраиваемое свойство</span><span class="sxs-lookup"><span data-stu-id="268b0-319">Has Custom Property</span></span>|<span data-ttu-id="268b0-320">TermSet</span><span class="sxs-lookup"><span data-stu-id="268b0-320">TermSet</span></span>|<span data-ttu-id="268b0-321">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="268b0-321">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="268b0-322">[Скос](https://www.w3.org/TR/skos-primer/) допустимые сценарии, которые [таксономия SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) не поддерживает:</span><span class="sxs-lookup"><span data-stu-id="268b0-322">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="268b0-323">Иерархическая избыточность — концепция [скос](https://www.w3.org/TR/skos-primer/) может быть прикреплена к нескольким более широким концепциям одновременно, но SharePoint — Таксономия: термин может иметь только одну таксономию SharePoint: Parent, поэтому циклическая зависимость для терминов также не разрешено.</span><span class="sxs-lookup"><span data-stu-id="268b0-323">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="268b0-324">Не допускается использование потерянных терминов в таксономии SharePoint.</span><span class="sxs-lookup"><span data-stu-id="268b0-324">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="268b0-325">Каждая SharePoint — Таксономия: термин должен иметь SharePoint — таксономию: родительский элемент или он должен быть SharePoint — Таксономия: Топлевелтермоф набор терминов.</span><span class="sxs-lookup"><span data-stu-id="268b0-325">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="268b0-326">Таксономия SharePoint не поддерживает ассоциативные отношения.</span><span class="sxs-lookup"><span data-stu-id="268b0-326">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="268b0-327">Таксономия SharePoint позволяет только 2 типа иерархических отношений — SharePoint — Таксономия: родители и SharePoint — Таксономия: дочерний элемент.</span><span class="sxs-lookup"><span data-stu-id="268b0-327">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="268b0-328">В отличие от [скос](https://www.w3.org/TR/skos-primer/) иерархической связи в словаре таксономии SharePoint, можно установить только термины, входящие в один и тот же набор терминов.</span><span class="sxs-lookup"><span data-stu-id="268b0-328">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="268b0-329">См. также</span><span class="sxs-lookup"><span data-stu-id="268b0-329">See also</span></span>

[<span data-ttu-id="268b0-330">Импорт набора терминов в формате, основанном на скос</span><span class="sxs-lookup"><span data-stu-id="268b0-330">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

