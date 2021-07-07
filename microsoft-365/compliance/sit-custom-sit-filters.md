---
title: Настраиваемые ссылки типа фильтров конфиденциальной информации
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: В этой статье представлен список фильтров, которые можно закодировать в настраиваемые типы конфиденциальной информации.
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322969"
---
# <a name="custom-sensitive-information-type-filters-reference"></a>Ссылка на настраиваемые типы фильтров конфиденциальной информации

В Microsoft можно определить фильтры или дополнительные проверки при создании настраиваемой конфиденциальной информации (SIT).

## <a name="list-of-supported-filters-and-use-cases"></a>Список поддерживаемых фильтров и случаев использования

### <a name="alldigitssame-exclude"></a>Исключение AllDigitsSame

Описание. Позволяет исключить совпадения со всеми цифрами в качестве дублирующих цифр, например 11111111 или 111-111-111

Определение фильтров
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

Использование его в пакете правил на уровне сущности
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

Использование его в пакете правил на уровне шаблона
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a>TextMatchFilter StartsWith 

Описание. Позволяет определить начальные символы для объекта. Он имеет два варианта, включив и исключив.

Например, чтобы исключить номера, начиная с 0500, 91, 091, 010 в списке, как это:

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

вы можете использовать этот xml

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
Например, чтобы включить номера, начиная с 0500, 91, 091, 0100 в списке, как это: 

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

вы можете использовать этот xml

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a>TextMatchFilter EndsWith 

Описание. Позволяет определить завершающий символ для объекта. 

Например, чтобы исключить номера, заканчивающийся 0500,91,091, 0100 в списке, как это:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

вы можете использовать этот xml

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

Например, чтобы включить номера, заканчивающийся 0500, 91, 091, 0100, в список, как это:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

вы можете использовать этот xml

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a>TextMatchFilter Full

Описание. Позволяет запретить определенные совпадения, чтобы запретить им запускать правило. Например, исключить 411111111111111 из списка действительных совпадений кредитных карт.

Например, чтобы исключить номера кредитных карт, например 41111111111111 и 3241891031111111 в списке, подобном этому:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

вы можете использовать этот xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

Например, включить номера кредитных карт, например 411111111111111 и 3241891031111111 в таком списке:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

вы можете использовать этот xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a>Префикс TextMatchFilter

Описание. Позволяет определить предшествующие символы, которые всегда должны быть включены или исключены. Например, если номеру кредитной карты предшествует "Order ID:", удалите совпадение из действительных совпадений.

Например, чтобы исключить случаи появления  номеров телефонов  с Телефон номером и вызвать меня на строках перед номером телефона, в списке, как это:

- номер телефона 091-8974-653278
- Телефон 45-124576532-123
- 45-124576532-123

вы можете использовать этот xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

Например, чтобы включить в  список такие случаи, как кредитные карты и строки **#** карты перед номером кредитной карты:

- Кредитная карта 45-124576532-123 
- 45-124576532-123 (может быть номер телефона)

вы можете использовать этот xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a>TextMatchFilter Suffix

Описание. Позволяет определить следующие символы, которые всегда должны быть включены или исключены. Например, если за номером кредитной карты следует "/xuid", снимите совпадение из допустимого совпадения.

Например, верхний список исключений, если в списке есть еще 5 экземпляров из четырех цифр в качестве суффикса:

- 1234-5678-9321 4500 9870 6321 48925566
- 1234-5678-9321

вы можете использовать этот xml

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
Например, исключить случаи, если за ними следует **/xuidsuffix,** как и в этом списке:

- 1234-5678-9321 /xuid
- 1234-5678-9321

вы можете использовать этот xml

''xml <Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      <Term>/xuid</Term>
    </Group> </Keyword>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a>Использование фильтров в пакетах правил

Фильтры можно определить на всем СИТ или по шаблону. Вот некоторые примеры фрагментов кода. 

### <a name="at-sensitive-information-type-level"></a>На уровне типа конфиденциальной информации

Фильтры в Entity — будут охватывать все детские шаблоны

Фильтры будут применяться  во всех экземплярах, классифицированных любыми шаблонами в этом объекте/ конфиденциальном типе.

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a>В индивидуальном шаблоне уровня типа конфиденциальной информации

Фильтрует только на уровне шаблона.

Фильтр будет применяться в экземплярах, которые соответствуют шаблону.

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a>На уровне типа конфиденциальной информации и дополнительного фильтра для некоторых шаблонов этого объекта

Фильтры в шаблоне Entity +

Фильтры будут применяться  во всех экземплярах, классифицируются по любым шаблонам в этом объекте / конфиденциальном типе. Фильтр уровня шаблона будет фильтровать экземпляры, которые соответствуют этому шаблону.

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a>Дополнительные сведения

- [Сведения о защите от потери данных](dlp-learn-about-dlp.md)

- [Определения объектов типов конфиденциальной информации](sensitive-information-type-entity-definitions.md)

- [Сведения, для обнаружения которых используются функции защиты от потери данных](what-the-dlp-functions-look-for.md)
