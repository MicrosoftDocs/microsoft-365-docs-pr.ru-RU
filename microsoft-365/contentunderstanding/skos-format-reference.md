---
title: Справка по формату SKOS для таксономии SharePoint
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Справка по формату SKOS для таксономии SharePoint
ms.openlocfilehash: f81b618a7c302ce033c4e8ce2f7400e9616f2de0
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321329"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>Справка по формату SKOS для таксономии SharePoint

В этой статье приведен словарь RDF, используемый для представления [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) на основе модели [SKOS](https://www.w3.org/TR/skos-primer/). Для сериализации данного синтаксиса RDF следует использовать язык RDF [TURTLE](https://www.w3.org/TR/turtle/).

В следующей таблице показаны эквиваленты [SKOS](https://www.w3.org/TR/skos-primer/) для словаря [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy). В SharePoint не поддерживаются значения [SKOS](https://www.w3.org/TR/skos-primer/), у которых нет эквивалента в таксономии SharePoint.

|Таксономия SharePoint|Эквивалент SKOS|
|:-----------------|:--------------|
|sharepoint-taxonomy:Term|skos:Concept|
|sharepoint-taxonomy:TermSet|skos:ConceptScheme|
|sharepoint-taxonomy:inTermSet|skos:inScheme|
|sharepoint-taxonomy:hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-taxonomy:topLevelTermOf|skos:topConceptOf|
|sharepoint-taxonomy:defaultLabel|skos:prefLabel|
|sharepoint-taxonomy:termSetName|skos:prefLabel|
|sharepoint-taxonomy:propertyName|skos:prefLabel|
|sharepoint-taxonomy:otherLabel|skos:altLabel|
|sharepoint-taxonomy:description|skos:definition|
|sharepoint-taxonomy:parent|skos:broader|
|sharepoint-taxonomy:child|skos:narrower|

В следующей таблице показаны сущности словаря таксономии SharePoint, производные от [OWL](https://www.w3.org/TR/owl2-primer/).

|Словарь таксономии SharePoint|Производные от OWL|
|:-----------------------------|:----------------------|
|sharepoint-taxonomy:isAvailableForTagging|owl:datatypeproperty|
|sharepoint-taxonomy:SharedCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:LocalCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:CustomPropertyForTermSet|owl:ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>Словарь таксономии SharePoint

Таксономия — это формальная система классификации. При таксономии описательные слова, метки и термины объединяются в группы, упорядоченные в виде иерархии.

**sharepoint-taxonomy:Term**

Представляет термин или ключевое слово в иерархии управляемых метаданных.

[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) (объект Term) — это неделимая единица хранилища терминов SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Каждый [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) принадлежит к набору [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), который, в свою очередь, принадлежит к группе терминов [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). 

[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) имеет следующий синтаксис:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) обязательно находится в наборе [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). DefaultLabel — это имя [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), отображаемое при визуальном представлении. Обязательные поля при определении [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term):

- sharepoint-taxonomy:defaultLabel
- sharepoint-taxonomy:inTermSet

[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) может:

- иерархически относиться к другому [термину](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) при условии, что оба [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) принадлежат к одному и тому же набору [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset);
- иметь несколько дочерних [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), но только один родительский [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term);
- не иметь родительского [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), если этот термин находится на уровне topLevelTermOf объекта [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset);
- иметь одно имя defaultLabel на каждый рабочий язык [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore);
- не существовать, если у него нет родительского [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или он не находится на уровне topLevelTermOf набора [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset); 
- иметь уникальное имя defaultLabel на своем уровне иерархии.

**sharepoint-taxonomy:TermSet**

Представляет иерархический или плоский набор объектов Term, называемый также «набором терминов».

Как видно из названия, TermSet — это набор [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). [Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в хранилище [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) должен принадлежать к набору [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). [Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) не может существовать независимо. 

[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) имеет следующий синтаксис:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

Наборы [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) логически объединяются в группу [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). Обязательные поля при определении [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset):

- sharepoint-taxonomy:termSetName

Если указанное имя termSetName не является уникальным в группе [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint дописывает номер в конец имени, чтобы обеспечить уникальность termSetName.

**sharepoint-taxonomy:hasTopLevelTerm**

В SharePoint это свойство используется для обозначения [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) наивысшего уровня в наборе [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) — исходной точки иерархии [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Оно представляет собой отношение, обратное к sharepoint-taxonomy:topLevelTermOf. 

Это свойство имеет следующий синтаксис:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> Нельзя задать [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) высшего уровня для родительского [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

**sharepoint-taxonomy:topLevelTermOf**

Sharepoint-taxonomy:topLevelTermOf обратно свойству sharepoint-taxonomy:hasTopLevelTerm

Это свойство имеет следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomy:inTermSet**

Используется для сопоставления [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) с набором [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). [Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) может принадлежать только к одному набору [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Это свойство обязательно указывать в SharePoint при [определении термина](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Обязательные метки

Перед использованием управляемых метаданных в организации может потребоваться тщательное планирование. Объем необходимого планирования зависит от того, насколько формальной является таксономия. Он также зависит от требуемой степени контролирования метаданных. На каждом уровне иерархии необходимо задать обязательные метки для терминов и наборов терминов.

Каждый термин может иметь одну или несколько меток на языке по умолчанию и ноль или более меток на языке, не используемом по умолчанию. Если у термина есть метки на определенном языке, одна из них должна быть меткой по умолчанию.

**sharepoint-taxonomy:defaultLabel**

Эта лексическая метка по умолчанию используется для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) и является обязательным параметром [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Она служит для визуального представления [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

defaultLabel имеет следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

defaultLabel состоит из двух частей — строки и тега языка. Язык должен быть одним из рабочих языков [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Значение defaultLabel должно быть уникальным для всех [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в одном наборе [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) на том же уровне иерархии.

**sharepoint-taxonomy:termSetName**

Возвращает или задает имя текущего объекта TermSet.

Это лексическая метка для набора [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) на рабочем языке [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Это обязательный параметр [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Он служит для визуального представления [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).

termSetName имеет следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomy:propertyName**

Возвращает или задает имя свойства текущего объекта TermSet.

Это лексическая метка для sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm и sharepoint-taxonomy:CustomPropertyForTermSet на рабочем языке [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).

sharepoint-taxonomy:propertyName рассматривается как ключ свойства CustomProperty.

propetyName имеет следующий синтаксис:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Необязательные метки

В таксономию также можно добавить необязательные метки.

**sharepoint-taxonomy:otherLabel**

Это альтернативная лексическая метка для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

otherLabel имеет следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Семантические отношения

В таксономиях применяется иерархическое, а иногда — ассоциативное отношение "связанный термин", но некоторые из них также содержат семантические или пользовательские отношения. 

**sharepoint-taxonomy:parent**

Это отношение иерархически связывает [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) с другим [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). [Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) может быть [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) наивысшего уровня в наборе [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset); в противном случае у него должен быть родительский [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

Для определения родительского объекта используется следующий синтаксис:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Это означает, что TermA — родительский термин, а TermB — дочерний.

**sharepoint-taxonomy:child**

Объект содержит один или несколько дочерних экземпляров TermSet, к которым можно обратиться через свойство TermSets. Этот класс также содержит методы для создания новых дочерних объектов TermSet. Разрешения на редактирование дочерних экземпляров Term и TermSet указываются в группе. 

Это отношение иерархически связывает [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) с другим [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

Для определения дочернего объекта используется следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Это означает, что TermA — родительский термин, а TermB — дочерний.

## <a name="documentation-notes"></a>Примечания для документации

В этом разделе описываются таксономии, определенные в пространстве имен Microsoft.SharePoint.Taxonomy.

**sharepoint-taxonomy:description**

Это подробное описание любой сущности словаря [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy). 

Для описания используется следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Настраиваемые свойства

Возвращает коллекцию объектов настраиваемых свойств для текущего объекта Term из словаря, доступного только для чтения.

Настраиваемые свойства — это пары "ключ-значение", которые можно задать для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или набора [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) в дополнение к описанию [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или набора [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). В SharePoint ключ настраиваемого свойства указывается с помощью propertyName.

**sharepoint-taxonomy:CustomPropertyForTermSet**

Это свойство имеет следующий синтаксис:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomy:SharedCustomPropertyForTerm**

Если настраиваемое свойство [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) требуется переносить вместе с [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), при повторном использовании [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в другом месте необходимо определить его в SharedCustomPropertyForTerm.

Это свойство имеет следующий синтаксис:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomy:LocalCustomPropertyForTerm**

Если настраиваемое свойство [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) не нужно переносить вместе с [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), при повторном использовании [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в другом месте необходимо определить его в LocalCustomPropertyForTerm.

Это свойство имеет следующий синтаксис:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Свойства данных

На каждом уровне иерархии можно задать особые свойства данных для термина или набора TermSet.

**sharepoint-taxonomy:isAvailableForTagging**

Это свойство указывает, доступен ли [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или набор [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) в списках и библиотеках SharePoint.  

Используется следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Домен и диапазон

В следующей таблице описаны домен и диапазон словаря таксономии SharePoint.

|Предикаты/глагол|Смысл|Домен|Диапазон|
|:--------------|:------|:-----|:----|
inTermSet|В наборе терминов|Term|TermSet|
inTermGroup|В группе терминов|TermSet|TermGroup|
topLevelTermOf|Является термином высшего уровня|Term|TermSet|
hasTopLevelTerm|Содержит термин высшего уровня|TermSet|Term|
termSetName|Имя набора терминов|Term|Обычный литерал|
defaultLabel|У термина есть метка по умолчанию|Term|Обычный литерал|
otherLabel|У термина есть другая метка|Term|Обычный литерал|
propertyName|Есть метка свойства|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolean, String, Integer, Decimal, Double|
|description|Есть описание|Все|Обычный литерал|
|parent|Есть родительский объект|Term|Term|
|child|Есть дочерний объект|Term|Term|
|isAvailableForTagging|Доступен для расстановки тегов|Term, TermSet|Boolean|
|SharedCustomPropertyForTerm|Есть общее настраиваемое свойство|Term|Boolean, String, Integer, Decimal, Double|
|LocalCustomPropertyForTerm|Есть локальное настраиваемое свойство|Term|Boolean, String, Integer, Decimal, Double|
|CustomPropertyForTermSet|Есть настраиваемое свойство|TermSet|Boolean, String, Integer, Decimal, Double|

Допустимые в [SKOS](https://www.w3.org/TR/skos-primer/) сценарии, не разрешенные в [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy):

- Иерархическая избыточность: концепцию [SKOS](https://www.w3.org/TR/skos-primer/) можно одновременно присоединить к нескольким более широким концепциям, но sharepoint-taxonomy:Term может иметь только одно свойство sharepoint-taxonomy:parent, поэтому циклическая зависимость терминов также не разрешена.
- В таксономии SharePoint не допускаются термины, не имеющие родительских терминов. У каждого объекта sharepoint-taxonomy:Term должен быть sharepoint-taxonomy:parent, или он должен быть sharepoint-taxonomy:topLevelTermOf в TermSet.
- Таксономия SharePoint не поддерживает ассоциативные отношения.
- Таксономия SharePoint поддерживает только 2 типа иерархических отношений — sharepoint-taxonomy:parent и sharepoint-Taxonomy:child. 
- В отличие от [SKOS](https://www.w3.org/TR/skos-primer/), иерархическое отношение в словаре таксономии SharePoint можно установить только между терминами из одного набора TermSet.

## <a name="see-also"></a>См. также

[Импорт набора терминов в формате SKOS](import-term-set-skos.md)

