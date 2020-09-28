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
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>Справка по формату скос для таксономии SharePoint

Эта статья включает словарь РДФ, используемый для представления [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) и основанный на [скос](https://www.w3.org/TR/skos-primer/). Для сериализации этого синтаксиса РДФ используйте РДФ [Turtle](https://www.w3.org/TR/turtle/).

В следующей таблице приведены эквиваленты [скос](https://www.w3.org/TR/skos-primer/) для словаря [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) . SharePoint не поддерживает значения [скос](https://www.w3.org/TR/skos-primer/) , которые не имеют эквивалентов таксономии для таксономии SharePoint.

|Таксономия SharePoint|Эквивалент скос|
|:-----------------|:--------------|
|SharePoint — Таксономия: термин|Скос: концепция|
|SharePoint — Таксономия: набор терминов|Скос: Концептсчеме|
|SharePoint — Таксономия: "набор терминов"|Скос: схема|
|SharePoint — Таксономия: Хастоплевелтерм|Скос: Хастопконцепт|
|SharePoint — Таксономия: Топлевелтермоф|Скос: Топконцептоф|
|SharePoint — Таксономия: Дефаултлабел|Скос: Префлабел|
|SharePoint — Таксономия: Термсетнаме|Скос: Префлабел|
|SharePoint — Таксономия: propertyName|Скос: Префлабел|
|SharePoint — Таксономия: Осерлабел|Скос: Алтлабел|
|SharePoint — Таксономия: описание|Скос: определение|
|SharePoint — Таксономия: родительский элемент|Скос: широкий|
|SharePoint — Таксономия: дочерний элемент|Скос: более узкий|

В следующей таблице показаны сущности словаря таксономии SharePoint, полученные из [ОВЛ](https://www.w3.org/TR/owl2-primer/).

|Словарь таксономии SharePoint|Производный от ОВЛ|
|:-----------------------------|:----------------------|
|SharePoint — Таксономия: Исаваилаблефортаггинг|ОВЛ: дататипепроперти|
|SharePoint — Таксономия: Шаредкустомпропертифортерм|ОВЛ: Обжектпроперти|
|SharePoint — Таксономия: Локалкустомпропертифортерм|ОВЛ: Обжектпроперти|
|SharePoint — Таксономия: Кустомпропертифортермсет|ОВЛ: Обжектпроперти|

## <a name="sharepoint-taxonomy-vocabulary"></a>Словарь таксономии SharePoint

Таксономия это формально система классификации. Таксономия группирует слова, метки и термины, описывающие что-то, а затем упорядочивает группы в иерархию.

**SharePoint — Таксономия: термин**

Представляет термин или ключевое слово в иерархии управляемых метаданных.

[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) — это атомарная единица [банка терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)SharePoint. Каждый [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) относится к набору [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) , который принадлежит к [термграуп](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). 

Для определения [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) используется следующий синтаксис:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) компулсорили существует в наборе [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Дефаултлабел — это имя [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в том виде, в котором оно отображается в визуальном представлении. Обязательные поля для определения [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) включают:

- SharePoint — Таксономия: Дефаултлабел
- SharePoint — Таксономия: "набор терминов"

[Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) может:

- Иерархическая связь с другим [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) , при условии, что оба [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) относятся к одному и тому же набору [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Иметь несколько дочерних [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), но только один родительский [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).
- Не определен родительский [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) , если он является топлевелтермоф набором [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Один Дефаултлабел для каждого рабочего языка [банка терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .
- Не существует, если он не содержит родительских [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), а топлевелтермоф не является набором [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). 
- Иметь только уникальный Дефаултлабел на одном иерархическом уровне.

**SharePoint — Таксономия: набор терминов**

Представляет иерархический или плоский набор объектов Term, известных как "набор терминов".

Как видно из названия, набор терминов называется набором [терминов.](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) [Термин в банке](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) [терминов должен](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) принадлежать к набору [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). [Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) не может существовать независимо друг от друга. 

Для определения набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) используется следующий синтаксис:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[Термсетс](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) логически группируются в [термграупс](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). Для определения набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) необходимо обязательное поле:

- SharePoint — Таксономия: Термсетнаме

В случае указанного Термсетнаме не является уникальным в [термграуп](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint добавляет в конец имени число, чтобы поддерживать уникальность термсетнаме (s).

**SharePoint — Таксономия: Хастоплевелтерм**

SharePoint использует это свойство, чтобы сопоставить самый верхний [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в наборе [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), который является точкой входа в иерархию [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в наборе [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Это обратное отношение к SharePoint — Таксономия: Топлевелтермоф. 

Для определения используется следующий синтаксис:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> Невозможно определить [условие](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) верхнего уровня родительского [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

**SharePoint — Таксономия: Топлевелтермоф**

SharePoint — Таксономия: Топлевелтермоф — это обратное значение SharePoint — Таксономия: Хастоплевелтерм

Для определения используется следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**SharePoint — Таксономия: "набор терминов"**

Используйте этот элемент, чтобы сопоставить [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) с набором [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). [Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) может существовать только в едином наборе [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). В SharePoint это свойство требуется при [определении термина](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Обязательные метки

Прежде чем приступать к использованию управляемых метаданных, в Организации может потребоваться тщательное планирование. Предполагаемый объем планирования зависит от того, насколько формальным является таксономия. Он также зависит от того, какой элемент управления требуется применить к метаданным. На каждом уровне иерархии необходимо настроить обязательные метка для термина или набора терминов.

Термин может иметь одну или несколько меток на языке по умолчанию, а также ноль или более меток на языке, отличном от используемого по умолчанию. Если термин содержит метки на языке, одна из меток должна быть меткой по умолчанию.

**SharePoint — Таксономия: Дефаултлабел**

Используйте эту лексическую метку по умолчанию для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) , который является обязательным параметром для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Используется для визуального представления [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

Для определения Дефаултлабел используется следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Дефаултлабел содержит две части — строку и тег языка. Язык должен быть одним из рабочих языков [банка терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) . Дефаултлабел должны быть уникальными для всех [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) в одном и том же наборе [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)на том же уровне иерархии.

**SharePoint — Таксономия: Термсетнаме**

Получает и задает имя текущего объекта набора терминов.

Это лексическая подпись для набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)в рабочем языке [банка терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) . Это обязательный параметр для набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Используется для визуального представления набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).

Для определения Термсетнаме используется следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**SharePoint — Таксономия: propertyName**

Получает и задает имя свойства для текущего объекта набора терминов.

Это лексическая метка для SharePoint — Таксономия: Шаредкустомпропертифортерм, SharePoint-Таксономия: Локалкустомпропертифортерм и SharePoint-Таксономия: Кустомпропертифортермсет на рабочем языке [банка терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .

SharePoint — Таксономия: propertyName рассматривается как ключ CustomProperty.

Для определения Пропетинаме используется следующий синтаксис:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Необязательные метки

Вы также можете добавить необязательные метки в таксономию.

**SharePoint — Таксономия: Осерлабел**

Это альтернативная лексическая метка для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

Для определения Осерлабел используется следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Семантические связи

Таксономии имеют иерархию и иногда простой ассоциативной связи "связанный термин", но некоторые имеют "семантические связи" или созданные пользователем связи. 

**SharePoint — Таксономия: родительский элемент**

Это иерархически связывает [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) с другим [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). [Термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) может быть [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) верхнего уровня набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), но в случае, если он не должен иметь родительский [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

Для определения родителя используется следующий синтаксис:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Это означает, что у TermA1 есть родительский термин. Кроме того, это означает, что TermA1 является дочерним по отношению к терму Term. Связь "родитель-потомок" является отношением инверсибле.

**SharePoint — Таксономия: дочерний элемент**

Объект содержит один или несколько дочерних экземпляров набора терминов, и к ним можно получить доступ с помощью свойства Термсетс. Этот класс также предоставляет методы для создания новых дочерних объектов набора терминов. В группе заданы разрешения для редактирования дочерних терминов и экземпляров набора терминов. 

Это иерархически связывает [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) с другим [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

Синтаксис для определения дочернего элемента:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Это означает, что Term имеет дочерний TermA1. Кроме того, это означает, что термин "родитель" отношения "родитель-потомок" TermA1 является отношением инверсибле.

## <a name="documentation-notes"></a>Заметки к документации

В этом разделе рассматривается таксономия, подробно описанная в пространстве имен Microsoft. SharePoint. таксономии.

**SharePoint — Таксономия: описание**

Это подробное описание объекта словаря [таксономии SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) . 

Для добавления описания используется следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Настраиваемые свойства

Получает коллекцию объектов настраиваемых свойств для текущего объекта Term из словаря, доступного только для чтения.

Настраиваемые свойства — это пары "ключ — значение", которые могут быть определены для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), чтобы получить описание [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или набора [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint определяет ключ настраиваемого свойства с помощью параметра propertyName.

**SharePoint — Таксономия: Кустомпропертифортермсет**

Для определения используется следующий синтаксис:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**SharePoint — Таксономия: Шаредкустомпропертифортерм**

Если настраиваемое свойство [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) необходимо переносить вместе с [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), то при повторном использовании этого [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) его необходимо определить в разделе шаредкустомпропертифортерм.

Для определения используется следующий синтаксис:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**SharePoint — Таксономия: Локалкустомпропертифортерм**

Если настраиваемое свойство для [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) не требуется переносить вместе с [термином](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), то при повторном использовании этого [термина](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) необходимо определить его в локалкустомпропертифортерм.

Для определения используется следующий синтаксис:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Свойства данных

На каждом уровне иерархии можно настроить определенные свойства данных для термина или набора терминов.

**SharePoint — Таксономия: Исаваилаблефортаггинг**

Используйте этот элемент, чтобы указать, доступен ли [термин](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) или набор [терминов](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) в списках и библиотеках SharePoint.  

Для этого используется следующий синтаксис:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Домен и диапазон

В приведенной ниже таблице описывается домен и диапазон словаря таксономии SharePoint.

|Предикаты и глаголы|Смысл|Domain|Range|
|:--------------|:------|:-----|:----|
набор терминов|В наборе терминов|Term|Набор терминов|
интермграуп|В группе терминов|TermSet|термграуп|
топлевелтермоф|— Это термин верхнего уровня|Term|TermSet|
хастоплевелтерм|Имеет термин верхнего уровня|Набор терминов|Term|
термсетнаме|Имя набора терминов|Term|Обычный литерал|
дефаултлабел|Термин имеет метку по умолчанию|Term|Обычный литерал|
осерлабел|Термин содержит другую метку|Term|Обычный литерал|
propertyName|Имеет метку свойства|Шаредкустомпропертифортерм, Локалкустомпропертифортерм, Кустомпропертифортермсет |Boolean, String, Integer, Decimal, Double|
|description|Содержит описание|Все|Обычный литерал|
|родитель|Имеет родительский элемент|Term|Term|
|ребенка|Имеет дочерний элемент|Term|Term|
|исаваилаблефортаггинг|Доступна для тегирования|Термин, набор терминов|Boolean|
|шаредкустомпропертифортерм|Имеет общее настраиваемое свойство|Term|Boolean, String, Integer, Decimal, Double|
|локалкустомпропертифортерм|Имеет локальное настраиваемое свойство|Term|Boolean, String, Integer, Decimal, Double|
|кустомпропертифортермсет|Имеет настраиваемое свойство|TermSet|Boolean, String, Integer, Decimal, Double|

[Скос](https://www.w3.org/TR/skos-primer/) допустимые сценарии, которые [таксономия SharePoint](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) не поддерживает:

- Иерархическая избыточность — концепция [скос](https://www.w3.org/TR/skos-primer/) может быть прикреплена к нескольким более широким концепциям одновременно, но SharePoint — Таксономия: термин может иметь только одну таксономию SharePoint: Parent, поэтому циклическая зависимость для терминов также не разрешено.
- Не допускается использование потерянных терминов в таксономии SharePoint. Каждая SharePoint — Таксономия: термин должен иметь SharePoint — таксономию: родительский элемент или он должен быть SharePoint — Таксономия: Топлевелтермоф набор терминов.
- Таксономия SharePoint не поддерживает ассоциативные отношения.
- Таксономия SharePoint позволяет только 2 типа иерархических отношений — SharePoint — Таксономия: родители и SharePoint — Таксономия: дочерний элемент. 
- В отличие от [скос](https://www.w3.org/TR/skos-primer/) иерархической связи в словаре таксономии SharePoint, можно установить только термины, входящие в один и тот же набор терминов.

## <a name="see-also"></a>См. также

[Импорт набора терминов в формате, основанном на скос](import-term-set-skos.md)

