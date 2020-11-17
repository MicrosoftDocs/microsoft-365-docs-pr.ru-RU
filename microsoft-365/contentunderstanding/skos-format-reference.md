---
title: Справка по формату SKOS для таксономии SharePoint
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Справка по формату SKOS для таксономии SharePoint
ms.openlocfilehash: 90c20ddb440e216941a5ea06f1aa815cb80102a9
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087287"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="ed4a2-103">Справка по формату SKOS для таксономии SharePoint</span><span class="sxs-lookup"><span data-stu-id="ed4a2-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="ed4a2-104">В этой статье приведен словарь RDF, используемый для представления [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) на основе модели [SKOS](https://www.w3.org/TR/skos-primer/).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="ed4a2-105">Для сериализации данного синтаксиса RDF следует использовать язык RDF [TURTLE](https://www.w3.org/TR/turtle/).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="ed4a2-106">В следующей таблице показаны эквиваленты [SKOS](https://www.w3.org/TR/skos-primer/) для словаря [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="ed4a2-107">В SharePoint не поддерживаются значения [SKOS](https://www.w3.org/TR/skos-primer/), у которых нет эквивалента в таксономии SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="ed4a2-108">Таксономия SharePoint</span><span class="sxs-lookup"><span data-stu-id="ed4a2-108">SharePoint taxonomy</span></span>|<span data-ttu-id="ed4a2-109">Эквивалент SKOS</span><span class="sxs-lookup"><span data-stu-id="ed4a2-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="ed4a2-110">sharepoint-taxonomy:Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="ed4a2-111">skos:Concept</span><span class="sxs-lookup"><span data-stu-id="ed4a2-111">skos:Concept</span></span>|
|<span data-ttu-id="ed4a2-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="ed4a2-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="ed4a2-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="ed4a2-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="ed4a2-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="ed4a2-115">skos:inScheme</span></span>|
|<span data-ttu-id="ed4a2-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="ed4a2-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="ed4a2-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="ed4a2-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="ed4a2-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="ed4a2-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="ed4a2-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="ed4a2-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="ed4a2-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="ed4a2-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="ed4a2-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="ed4a2-121">skos:prefLabel</span></span>|
|<span data-ttu-id="ed4a2-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="ed4a2-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="ed4a2-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="ed4a2-123">skos:prefLabel</span></span>|
|<span data-ttu-id="ed4a2-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="ed4a2-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="ed4a2-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="ed4a2-125">skos:prefLabel</span></span>|
|<span data-ttu-id="ed4a2-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="ed4a2-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="ed4a2-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="ed4a2-127">skos:altLabel</span></span>|
|<span data-ttu-id="ed4a2-128">sharepoint-taxonomy:description</span><span class="sxs-lookup"><span data-stu-id="ed4a2-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="ed4a2-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="ed4a2-129">skos:definition</span></span>|
|<span data-ttu-id="ed4a2-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="ed4a2-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="ed4a2-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="ed4a2-131">skos:broader</span></span>|
|<span data-ttu-id="ed4a2-132">sharepoint-taxonomy:child</span><span class="sxs-lookup"><span data-stu-id="ed4a2-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="ed4a2-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="ed4a2-133">skos:narrower</span></span>|

<span data-ttu-id="ed4a2-134">В следующей таблице показаны сущности словаря таксономии SharePoint, производные от [OWL](https://www.w3.org/TR/owl2-primer/).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="ed4a2-135">Словарь таксономии SharePoint</span><span class="sxs-lookup"><span data-stu-id="ed4a2-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="ed4a2-136">Производные от OWL</span><span class="sxs-lookup"><span data-stu-id="ed4a2-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="ed4a2-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="ed4a2-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="ed4a2-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="ed4a2-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="ed4a2-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="ed4a2-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="ed4a2-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="ed4a2-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="ed4a2-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="ed4a2-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="ed4a2-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="ed4a2-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="ed4a2-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="ed4a2-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="ed4a2-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="ed4a2-145">Словарь таксономии SharePoint</span><span class="sxs-lookup"><span data-stu-id="ed4a2-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="ed4a2-146">Таксономия — это формальная система классификации.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="ed4a2-147">При таксономии описательные слова, метки и термины объединяются в группы, упорядоченные в виде иерархии.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="ed4a2-148">**sharepoint-taxonomy:Term**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="ed4a2-149">Представляет термин или ключевое слово в иерархии управляемых метаданных.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="ed4a2-150">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) (объект Term) — это неделимая единица хранилища терминов SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="ed4a2-151">Каждый [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) принадлежит к набору [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), который, в свою очередь, принадлежит к группе терминов [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="ed4a2-152">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="ed4a2-153">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) обязательно находится в наборе [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ed4a2-154">DefaultLabel — это имя [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), отображаемое при визуальном представлении.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="ed4a2-155">Обязательные поля при определении [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term):</span><span class="sxs-lookup"><span data-stu-id="ed4a2-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="ed4a2-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="ed4a2-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="ed4a2-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="ed4a2-158">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) может:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="ed4a2-159">иерархически относиться к другому [термину](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) при условии, что оба [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) принадлежат к одному и тому же набору [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset);</span><span class="sxs-lookup"><span data-stu-id="ed4a2-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="ed4a2-160">иметь несколько дочерних [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), но только один родительский [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term);</span><span class="sxs-lookup"><span data-stu-id="ed4a2-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="ed4a2-161">не иметь родительского [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), если этот термин находится на уровне topLevelTermOf объекта [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset);</span><span class="sxs-lookup"><span data-stu-id="ed4a2-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="ed4a2-162">иметь одно имя defaultLabel на каждый рабочий язык [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore);</span><span class="sxs-lookup"><span data-stu-id="ed4a2-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="ed4a2-163">не существовать, если у него нет родительского [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или он не находится на уровне topLevelTermOf набора [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset);</span><span class="sxs-lookup"><span data-stu-id="ed4a2-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="ed4a2-164">иметь уникальное имя defaultLabel на своем уровне иерархии.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="ed4a2-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="ed4a2-166">Представляет иерархический или плоский набор объектов Term, называемый также «набором терминов».</span><span class="sxs-lookup"><span data-stu-id="ed4a2-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="ed4a2-167">Как видно из названия, TermSet — это набор [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="ed4a2-168">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в хранилище [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) должен принадлежать к набору [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ed4a2-169">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) не может существовать независимо.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="ed4a2-170">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="ed4a2-171">Наборы [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) логически объединяются в группу [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="ed4a2-172">Обязательные поля при определении [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset):</span><span class="sxs-lookup"><span data-stu-id="ed4a2-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="ed4a2-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="ed4a2-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="ed4a2-174">Если указанное имя termSetName не является уникальным в группе [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint дописывает номер в конец имени, чтобы обеспечить уникальность termSetName.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="ed4a2-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="ed4a2-176">В SharePoint это свойство используется для обозначения [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) наивысшего уровня в наборе [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) — исходной точки иерархии [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ed4a2-177">Оно представляет собой отношение, обратное к sharepoint-taxonomy:topLevelTermOf.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="ed4a2-178">Это свойство имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="ed4a2-179">Нельзя задать [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) высшего уровня для родительского [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="ed4a2-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="ed4a2-181">Sharepoint-taxonomy:topLevelTermOf обратно свойству sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="ed4a2-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="ed4a2-182">Это свойство имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="ed4a2-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="ed4a2-184">Используется для сопоставления [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) с набором [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ed4a2-185">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) может принадлежать только к одному набору [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ed4a2-186">Это свойство обязательно указывать в SharePoint при [определении термина](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="ed4a2-187">Обязательные метки</span><span class="sxs-lookup"><span data-stu-id="ed4a2-187">Required labels</span></span>

<span data-ttu-id="ed4a2-188">Перед использованием управляемых метаданных в организации может потребоваться тщательное планирование.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="ed4a2-189">Объем необходимого планирования зависит от того, насколько формальной является таксономия.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="ed4a2-190">Он также зависит от требуемой степени контролирования метаданных.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="ed4a2-191">На каждом уровне иерархии необходимо задать обязательные метки для терминов и наборов терминов.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="ed4a2-192">Каждый термин может иметь одну или несколько меток на языке по умолчанию и ноль или более меток на языке, не используемом по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="ed4a2-193">Если у термина есть метки на определенном языке, одна из них должна быть меткой по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="ed4a2-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="ed4a2-195">Эта лексическая метка по умолчанию используется для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) и является обязательным параметром [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="ed4a2-196">Она служит для визуального представления [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="ed4a2-197">defaultLabel имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="ed4a2-198">defaultLabel состоит из двух частей — строки и тега языка.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="ed4a2-199">Язык должен быть одним из рабочих языков [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="ed4a2-200">Значение defaultLabel должно быть уникальным для всех [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в одном наборе [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) на том же уровне иерархии.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="ed4a2-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="ed4a2-202">Возвращает или задает имя текущего объекта TermSet.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="ed4a2-203">Это лексическая метка для набора [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) на рабочем языке [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="ed4a2-204">Это обязательный параметр [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ed4a2-205">Он служит для визуального представления [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="ed4a2-206">termSetName имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="ed4a2-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="ed4a2-208">Возвращает или задает имя свойства текущего объекта TermSet.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="ed4a2-209">Это лексическая метка для sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm и sharepoint-taxonomy:CustomPropertyForTermSet на рабочем языке [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="ed4a2-210">sharepoint-taxonomy:propertyName рассматривается как ключ свойства CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="ed4a2-211">propetyName имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="ed4a2-212">Необязательные метки</span><span class="sxs-lookup"><span data-stu-id="ed4a2-212">Optional labels</span></span>

<span data-ttu-id="ed4a2-213">В таксономию также можно добавить необязательные метки.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="ed4a2-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="ed4a2-215">Это альтернативная лексическая метка для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="ed4a2-216">otherLabel имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="ed4a2-217">Семантические отношения</span><span class="sxs-lookup"><span data-stu-id="ed4a2-217">Semantic relationships</span></span>

<span data-ttu-id="ed4a2-218">В таксономиях применяется иерархическое, а иногда — ассоциативное отношение "связанный термин", но некоторые из них также содержат семантические или пользовательские отношения.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="ed4a2-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="ed4a2-220">Это отношение иерархически связывает [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) с другим [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="ed4a2-221">[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) может быть [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) наивысшего уровня в наборе [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset); в противном случае у него должен быть родительский [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="ed4a2-222">Для определения родительского объекта используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="ed4a2-223">Это означает, что TermA — родительский термин, а TermB — дочерний.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="ed4a2-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="ed4a2-225">Объект содержит один или несколько дочерних экземпляров TermSet, к которым можно обратиться через свойство TermSets.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="ed4a2-226">Этот класс также содержит методы для создания новых дочерних объектов TermSet.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="ed4a2-227">Разрешения на редактирование дочерних экземпляров Term и TermSet указываются в группе.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="ed4a2-228">Это отношение иерархически связывает [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) с другим [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-228">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="ed4a2-229">Для определения дочернего объекта используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="ed4a2-230">Это означает, что TermA — родительский термин, а TermB — дочерний.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="ed4a2-231">Примечания для документации</span><span class="sxs-lookup"><span data-stu-id="ed4a2-231">Documentation notes</span></span>

<span data-ttu-id="ed4a2-232">В этом разделе описываются таксономии, определенные в пространстве имен Microsoft.SharePoint.Taxonomy.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="ed4a2-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="ed4a2-234">Это подробное описание любой сущности словаря [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-234">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="ed4a2-235">Для описания используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="ed4a2-236">Настраиваемые свойства</span><span class="sxs-lookup"><span data-stu-id="ed4a2-236">Custom properties</span></span>

<span data-ttu-id="ed4a2-237">Возвращает коллекцию объектов настраиваемых свойств для текущего объекта Term из словаря, доступного только для чтения.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="ed4a2-238">Настраиваемые свойства — это пары "ключ-значение", которые можно задать для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или набора [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) в дополнение к описанию [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или набора [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span><span class="sxs-lookup"><span data-stu-id="ed4a2-238">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="ed4a2-239">В SharePoint ключ настраиваемого свойства указывается с помощью propertyName.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="ed4a2-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="ed4a2-241">Это свойство имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="ed4a2-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="ed4a2-243">Если настраиваемое свойство [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) требуется переносить вместе с [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), при повторном использовании [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в другом месте необходимо определить его в SharedCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-243">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="ed4a2-244">Это свойство имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="ed4a2-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="ed4a2-246">Если настраиваемое свойство [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) не нужно переносить вместе с [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), при повторном использовании [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в другом месте необходимо определить его в LocalCustomPropertyForTerm.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="ed4a2-247">Это свойство имеет следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="ed4a2-248">Свойства данных</span><span class="sxs-lookup"><span data-stu-id="ed4a2-248">Data properties</span></span>

<span data-ttu-id="ed4a2-249">На каждом уровне иерархии можно задать особые свойства данных для термина или набора TermSet.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="ed4a2-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="ed4a2-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="ed4a2-251">Это свойство указывает, доступен ли [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или набор [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) в списках и библиотеках SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-251">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="ed4a2-252">Используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="ed4a2-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="ed4a2-253">Домен и диапазон</span><span class="sxs-lookup"><span data-stu-id="ed4a2-253">Domain and range</span></span>

<span data-ttu-id="ed4a2-254">В следующей таблице описаны домен и диапазон словаря таксономии SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="ed4a2-255">Предикаты/глагол</span><span class="sxs-lookup"><span data-stu-id="ed4a2-255">Predicates/verb</span></span>|<span data-ttu-id="ed4a2-256">Смысл</span><span class="sxs-lookup"><span data-stu-id="ed4a2-256">Meaning</span></span>|<span data-ttu-id="ed4a2-257">Домен</span><span class="sxs-lookup"><span data-stu-id="ed4a2-257">Domain</span></span>|<span data-ttu-id="ed4a2-258">Диапазон</span><span class="sxs-lookup"><span data-stu-id="ed4a2-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="ed4a2-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-259">inTermSet</span></span>|<span data-ttu-id="ed4a2-260">В наборе терминов</span><span class="sxs-lookup"><span data-stu-id="ed4a2-260">In term set</span></span>|<span data-ttu-id="ed4a2-261">Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-261">Term</span></span>|<span data-ttu-id="ed4a2-262">TermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-262">Term Set</span></span>|
<span data-ttu-id="ed4a2-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="ed4a2-263">inTermGroup</span></span>|<span data-ttu-id="ed4a2-264">В группе терминов</span><span class="sxs-lookup"><span data-stu-id="ed4a2-264">In term group</span></span>|<span data-ttu-id="ed4a2-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-265">TermSet</span></span>|<span data-ttu-id="ed4a2-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="ed4a2-266">TermGroup</span></span>|
<span data-ttu-id="ed4a2-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="ed4a2-267">topLevelTermOf</span></span>|<span data-ttu-id="ed4a2-268">Является термином высшего уровня</span><span class="sxs-lookup"><span data-stu-id="ed4a2-268">Is Top Level Term Of</span></span>|<span data-ttu-id="ed4a2-269">Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-269">Term</span></span>|<span data-ttu-id="ed4a2-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-270">TermSet</span></span>|
<span data-ttu-id="ed4a2-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="ed4a2-271">hasTopLevelTerm</span></span>|<span data-ttu-id="ed4a2-272">Содержит термин высшего уровня</span><span class="sxs-lookup"><span data-stu-id="ed4a2-272">Has top level term</span></span>|<span data-ttu-id="ed4a2-273">TermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-273">Term Set</span></span>|<span data-ttu-id="ed4a2-274">Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-274">Term</span></span>|
<span data-ttu-id="ed4a2-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="ed4a2-275">termSetName</span></span>|<span data-ttu-id="ed4a2-276">Имя набора терминов</span><span class="sxs-lookup"><span data-stu-id="ed4a2-276">Term set has Name</span></span>|<span data-ttu-id="ed4a2-277">Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-277">Term</span></span>|<span data-ttu-id="ed4a2-278">Обычный литерал</span><span class="sxs-lookup"><span data-stu-id="ed4a2-278">Plain literal</span></span>|
<span data-ttu-id="ed4a2-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="ed4a2-279">defaultLabel</span></span>|<span data-ttu-id="ed4a2-280">У термина есть метка по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ed4a2-280">Term has default label</span></span>|<span data-ttu-id="ed4a2-281">Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-281">Term</span></span>|<span data-ttu-id="ed4a2-282">Обычный литерал</span><span class="sxs-lookup"><span data-stu-id="ed4a2-282">Plain literal</span></span>|
<span data-ttu-id="ed4a2-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="ed4a2-283">otherLabel</span></span>|<span data-ttu-id="ed4a2-284">У термина есть другая метка</span><span class="sxs-lookup"><span data-stu-id="ed4a2-284">Term has other label</span></span>|<span data-ttu-id="ed4a2-285">Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-285">Term</span></span>|<span data-ttu-id="ed4a2-286">Обычный литерал</span><span class="sxs-lookup"><span data-stu-id="ed4a2-286">Plain literal</span></span>|
<span data-ttu-id="ed4a2-287">propertyName</span><span class="sxs-lookup"><span data-stu-id="ed4a2-287">propertyName</span></span>|<span data-ttu-id="ed4a2-288">Есть метка свойства</span><span class="sxs-lookup"><span data-stu-id="ed4a2-288">Has Property Label</span></span>|<span data-ttu-id="ed4a2-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="ed4a2-290">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="ed4a2-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="ed4a2-291">description</span><span class="sxs-lookup"><span data-stu-id="ed4a2-291">description</span></span>|<span data-ttu-id="ed4a2-292">Есть описание</span><span class="sxs-lookup"><span data-stu-id="ed4a2-292">Has Description</span></span>|<span data-ttu-id="ed4a2-293">Все</span><span class="sxs-lookup"><span data-stu-id="ed4a2-293">All</span></span>|<span data-ttu-id="ed4a2-294">Обычный литерал</span><span class="sxs-lookup"><span data-stu-id="ed4a2-294">Plain literal</span></span>|
|<span data-ttu-id="ed4a2-295">parent</span><span class="sxs-lookup"><span data-stu-id="ed4a2-295">parent</span></span>|<span data-ttu-id="ed4a2-296">Есть родительский объект</span><span class="sxs-lookup"><span data-stu-id="ed4a2-296">Has parent</span></span>|<span data-ttu-id="ed4a2-297">Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-297">Term</span></span>|<span data-ttu-id="ed4a2-298">Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-298">Term</span></span>|
|<span data-ttu-id="ed4a2-299">child</span><span class="sxs-lookup"><span data-stu-id="ed4a2-299">child</span></span>|<span data-ttu-id="ed4a2-300">Есть дочерний объект</span><span class="sxs-lookup"><span data-stu-id="ed4a2-300">Has Child</span></span>|<span data-ttu-id="ed4a2-301">Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-301">Term</span></span>|<span data-ttu-id="ed4a2-302">Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-302">Term</span></span>|
|<span data-ttu-id="ed4a2-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="ed4a2-303">isAvailableForTagging</span></span>|<span data-ttu-id="ed4a2-304">Доступен для расстановки тегов</span><span class="sxs-lookup"><span data-stu-id="ed4a2-304">Is available for tagging</span></span>|<span data-ttu-id="ed4a2-305">Term, TermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-305">Term, Term Set</span></span>|<span data-ttu-id="ed4a2-306">Boolean</span><span class="sxs-lookup"><span data-stu-id="ed4a2-306">Boolean</span></span>|
|<span data-ttu-id="ed4a2-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="ed4a2-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="ed4a2-308">Есть общее настраиваемое свойство</span><span class="sxs-lookup"><span data-stu-id="ed4a2-308">Has shared custom property</span></span>|<span data-ttu-id="ed4a2-309">Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-309">Term</span></span>|<span data-ttu-id="ed4a2-310">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="ed4a2-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="ed4a2-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="ed4a2-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="ed4a2-312">Есть локальное настраиваемое свойство</span><span class="sxs-lookup"><span data-stu-id="ed4a2-312">Has local custom property</span></span>|<span data-ttu-id="ed4a2-313">Term</span><span class="sxs-lookup"><span data-stu-id="ed4a2-313">Term</span></span>|<span data-ttu-id="ed4a2-314">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="ed4a2-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="ed4a2-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="ed4a2-316">Есть настраиваемое свойство</span><span class="sxs-lookup"><span data-stu-id="ed4a2-316">Has Custom Property</span></span>|<span data-ttu-id="ed4a2-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="ed4a2-317">TermSet</span></span>|<span data-ttu-id="ed4a2-318">Boolean, String, Integer, Decimal, Double</span><span class="sxs-lookup"><span data-stu-id="ed4a2-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="ed4a2-319">Допустимые в [SKOS](https://www.w3.org/TR/skos-primer/) сценарии, не разрешенные в [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy):</span><span class="sxs-lookup"><span data-stu-id="ed4a2-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="ed4a2-320">Иерархическая избыточность: концепцию [SKOS](https://www.w3.org/TR/skos-primer/) можно одновременно присоединить к нескольким более широким концепциям, но sharepoint-taxonomy:Term может иметь только одно свойство sharepoint-taxonomy:parent, поэтому циклическая зависимость терминов также не разрешена.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="ed4a2-321">В таксономии SharePoint не допускаются термины, не имеющие родительских терминов.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-321">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="ed4a2-322">У каждого объекта sharepoint-taxonomy:Term должен быть sharepoint-taxonomy:parent, или он должен быть sharepoint-taxonomy:topLevelTermOf в TermSet.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-322">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="ed4a2-323">Таксономия SharePoint не поддерживает ассоциативные отношения.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="ed4a2-324">Таксономия SharePoint поддерживает только 2 типа иерархических отношений — sharepoint-taxonomy:parent и sharepoint-Taxonomy:child.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="ed4a2-325">В отличие от [SKOS](https://www.w3.org/TR/skos-primer/), иерархическое отношение в словаре таксономии SharePoint можно установить только между терминами из одного набора TermSet.</span><span class="sxs-lookup"><span data-stu-id="ed4a2-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed4a2-326">См. также</span><span class="sxs-lookup"><span data-stu-id="ed4a2-326">See also</span></span>

[<span data-ttu-id="ed4a2-327">Импорт набора терминов в формате SKOS</span><span class="sxs-lookup"><span data-stu-id="ed4a2-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

