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
# <a name="custom-sensitive-information-type-filters-reference"></a><span data-ttu-id="9f739-103">Ссылка на настраиваемые типы фильтров конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="9f739-103">Custom sensitive information type filters reference</span></span>

<span data-ttu-id="9f739-104">В Microsoft можно определить фильтры или дополнительные проверки при создании настраиваемой конфиденциальной информации (SIT).</span><span class="sxs-lookup"><span data-stu-id="9f739-104">In Microsoft you can define filters or additional checks while creating a custom sensitive information types (SIT).</span></span>

## <a name="list-of-supported-filters-and-use-cases"></a><span data-ttu-id="9f739-105">Список поддерживаемых фильтров и случаев использования</span><span class="sxs-lookup"><span data-stu-id="9f739-105">List of supported filters and use cases</span></span>

### <a name="alldigitssame-exclude"></a><span data-ttu-id="9f739-106">Исключение AllDigitsSame</span><span class="sxs-lookup"><span data-stu-id="9f739-106">AllDigitsSame Exclude</span></span>

<span data-ttu-id="9f739-107">Описание. Позволяет исключить совпадения со всеми цифрами в качестве дублирующих цифр, например 11111111 или 111-111-111</span><span class="sxs-lookup"><span data-stu-id="9f739-107">Description: Allows you to exclude matches which have all digits as duplicate digits, like 111111111 or 111-111-111</span></span>

<span data-ttu-id="9f739-108">Определение фильтров</span><span class="sxs-lookup"><span data-stu-id="9f739-108">Defining filters</span></span>
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

<span data-ttu-id="9f739-109">Использование его в пакете правил на уровне сущности</span><span class="sxs-lookup"><span data-stu-id="9f739-109">Using it in rule package at the entity level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

<span data-ttu-id="9f739-110">Использование его в пакете правил на уровне шаблона</span><span class="sxs-lookup"><span data-stu-id="9f739-110">Using it in rule package at the pattern level</span></span>
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a><span data-ttu-id="9f739-111">TextMatchFilter StartsWith</span><span class="sxs-lookup"><span data-stu-id="9f739-111">TextMatchFilter StartsWith</span></span> 

<span data-ttu-id="9f739-112">Описание. Позволяет определить начальные символы для объекта.</span><span class="sxs-lookup"><span data-stu-id="9f739-112">Description: Allows you to define the starting characters for the entity.</span></span> <span data-ttu-id="9f739-113">Он имеет два варианта, включив и исключив.</span><span class="sxs-lookup"><span data-stu-id="9f739-113">It has two variants, include and exclude.</span></span>

<span data-ttu-id="9f739-114">Например, чтобы исключить номера, начиная с 0500, 91, 091, 010 в списке, как это:</span><span class="sxs-lookup"><span data-stu-id="9f739-114">For example to exclude the numbers starting with 0500, 91, 091, 010 in a list like this:</span></span>

- <span data-ttu-id="9f739-115">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="9f739-115">0500-4500-027</span></span>
- <span data-ttu-id="9f739-116">91564721450</span><span class="sxs-lookup"><span data-stu-id="9f739-116">91564721450</span></span>
- <span data-ttu-id="9f739-117">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="9f739-117">91-8523697410</span></span>
- <span data-ttu-id="9f739-118">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="9f739-118">700-8956-7844</span></span>
- <span data-ttu-id="9f739-119">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="9f739-119">1000-3265-9874</span></span>
- <span data-ttu-id="9f739-120">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="9f739-120">0100-7892-3012</span></span>

<span data-ttu-id="9f739-121">вы можете использовать этот xml</span><span class="sxs-lookup"><span data-stu-id="9f739-121">you can use this xml</span></span>

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
<span data-ttu-id="9f739-122">Например, чтобы включить номера, начиная с 0500, 91, 091, 0100 в списке, как это:</span><span class="sxs-lookup"><span data-stu-id="9f739-122">For example, to include the numbers starting with 0500, 91, 091, 0100 in a list like this:</span></span> 

- <span data-ttu-id="9f739-123">0500-4500-027</span><span class="sxs-lookup"><span data-stu-id="9f739-123">0500-4500-027</span></span>
- <span data-ttu-id="9f739-124">91564721450</span><span class="sxs-lookup"><span data-stu-id="9f739-124">91564721450</span></span>
- <span data-ttu-id="9f739-125">91-8523697410</span><span class="sxs-lookup"><span data-stu-id="9f739-125">91-8523697410</span></span>
- <span data-ttu-id="9f739-126">700-8956-7844</span><span class="sxs-lookup"><span data-stu-id="9f739-126">700-8956-7844</span></span>
- <span data-ttu-id="9f739-127">1000-3265-9874</span><span class="sxs-lookup"><span data-stu-id="9f739-127">1000-3265-9874</span></span>
- <span data-ttu-id="9f739-128">0100-7892-3012</span><span class="sxs-lookup"><span data-stu-id="9f739-128">0100-7892-3012</span></span>

<span data-ttu-id="9f739-129">вы можете использовать этот xml</span><span class="sxs-lookup"><span data-stu-id="9f739-129">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a><span data-ttu-id="9f739-130">TextMatchFilter EndsWith</span><span class="sxs-lookup"><span data-stu-id="9f739-130">TextMatchFilter EndsWith</span></span> 

<span data-ttu-id="9f739-131">Описание. Позволяет определить завершающий символ для объекта.</span><span class="sxs-lookup"><span data-stu-id="9f739-131">Description: Allows you to define the ending characters for the entity.</span></span> 

<span data-ttu-id="9f739-132">Например, чтобы исключить номера, заканчивающийся 0500,91,091, 0100 в списке, как это:</span><span class="sxs-lookup"><span data-stu-id="9f739-132">For example, to exclude the numbers ending with 0500,91,091, 0100 in a list like this:</span></span>

- <span data-ttu-id="9f739-133">1234567891</span><span class="sxs-lookup"><span data-stu-id="9f739-133">1234567891</span></span>
- <span data-ttu-id="9f739-134">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="9f739-134">1234-5678-0091</span></span>
- <span data-ttu-id="9f739-135">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="9f739-135">1234.4567.7091</span></span>
- <span data-ttu-id="9f739-136">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="9f739-136">1234-8091-4564</span></span>

<span data-ttu-id="9f739-137">вы можете использовать этот xml</span><span class="sxs-lookup"><span data-stu-id="9f739-137">you can use this xml</span></span>

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

<span data-ttu-id="9f739-138">Например, чтобы включить номера, заканчивающийся 0500, 91, 091, 0100, в список, как это:</span><span class="sxs-lookup"><span data-stu-id="9f739-138">For example, to include the numbers ending with 0500, 91, 091, 0100, in a list like this:</span></span>

- <span data-ttu-id="9f739-139">1234567891</span><span class="sxs-lookup"><span data-stu-id="9f739-139">1234567891</span></span>
- <span data-ttu-id="9f739-140">1234-5678-0091</span><span class="sxs-lookup"><span data-stu-id="9f739-140">1234-5678-0091</span></span>
- <span data-ttu-id="9f739-141">1234.4567.7091</span><span class="sxs-lookup"><span data-stu-id="9f739-141">1234.4567.7091</span></span>
- <span data-ttu-id="9f739-142">1234-8091-4564</span><span class="sxs-lookup"><span data-stu-id="9f739-142">1234-8091-4564</span></span>

<span data-ttu-id="9f739-143">вы можете использовать этот xml</span><span class="sxs-lookup"><span data-stu-id="9f739-143">you can use this xml</span></span>

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a><span data-ttu-id="9f739-144">TextMatchFilter Full</span><span class="sxs-lookup"><span data-stu-id="9f739-144">TextMatchFilter Full</span></span>

<span data-ttu-id="9f739-145">Описание. Позволяет запретить определенные совпадения, чтобы запретить им запускать правило.</span><span class="sxs-lookup"><span data-stu-id="9f739-145">Description: Allows you to prohibit certain matches to prevent them from triggering the rule.</span></span> <span data-ttu-id="9f739-146">Например, исключить 411111111111111 из списка действительных совпадений кредитных карт.</span><span class="sxs-lookup"><span data-stu-id="9f739-146">For example, exclude 4111111111111111 from the list of valid credit card matches.</span></span>

<span data-ttu-id="9f739-147">Например, чтобы исключить номера кредитных карт, например 41111111111111 и 3241891031111111 в списке, подобном этому:</span><span class="sxs-lookup"><span data-stu-id="9f739-147">For example, to exclude credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="9f739-148">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="9f739-148">4485 3647 3952 7352</span></span>
- <span data-ttu-id="9f739-149">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="9f739-149">4111111111111111</span></span>
- <span data-ttu-id="9f739-150">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="9f739-150">3241891031113111</span></span>

<span data-ttu-id="9f739-151">вы можете использовать этот xml</span><span class="sxs-lookup"><span data-stu-id="9f739-151">you can use this xml</span></span>

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

<span data-ttu-id="9f739-152">Например, включить номера кредитных карт, например 411111111111111 и 3241891031111111 в таком списке:</span><span class="sxs-lookup"><span data-stu-id="9f739-152">For example, to include credit card numbers like 4111111111111111 and 3241891031113111 in a list like this:</span></span>

- <span data-ttu-id="9f739-153">4485 3647 3952 7352</span><span class="sxs-lookup"><span data-stu-id="9f739-153">4485 3647 3952 7352</span></span>
- <span data-ttu-id="9f739-154">4111111111111111</span><span class="sxs-lookup"><span data-stu-id="9f739-154">4111111111111111</span></span>
- <span data-ttu-id="9f739-155">3241891031113111</span><span class="sxs-lookup"><span data-stu-id="9f739-155">3241891031113111</span></span>

<span data-ttu-id="9f739-156">вы можете использовать этот xml</span><span class="sxs-lookup"><span data-stu-id="9f739-156">you can use this xml</span></span>

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a><span data-ttu-id="9f739-157">Префикс TextMatchFilter</span><span class="sxs-lookup"><span data-stu-id="9f739-157">TextMatchFilter Prefix</span></span>

<span data-ttu-id="9f739-158">Описание. Позволяет определить предшествующие символы, которые всегда должны быть включены или исключены.</span><span class="sxs-lookup"><span data-stu-id="9f739-158">Description: Allows you to define the preceding characters that should be always included or excluded.</span></span> <span data-ttu-id="9f739-159">Например, если номеру кредитной карты предшествует "Order ID:", удалите совпадение из действительных совпадений.</span><span class="sxs-lookup"><span data-stu-id="9f739-159">For example, if Credit card number is preceded by ‘Order ID:’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="9f739-160">Например, чтобы исключить случаи появления  номеров телефонов  с Телефон номером и вызвать меня на строках перед номером телефона, в списке, как это:</span><span class="sxs-lookup"><span data-stu-id="9f739-160">For example, to exclude occurrences of phone numbers which have **Phone number** and **call me at** strings before the phone number, in a list like this:</span></span>

- <span data-ttu-id="9f739-161">номер телефона 091-8974-653278</span><span class="sxs-lookup"><span data-stu-id="9f739-161">phone number 091-8974-653278</span></span>
- <span data-ttu-id="9f739-162">Телефон 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="9f739-162">Phone 45-124576532-123</span></span>
- <span data-ttu-id="9f739-163">45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="9f739-163">45-124576532-123</span></span>

<span data-ttu-id="9f739-164">вы можете использовать этот xml</span><span class="sxs-lookup"><span data-stu-id="9f739-164">you can use this xml</span></span>

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

<span data-ttu-id="9f739-165">Например, чтобы включить в  список такие случаи, как кредитные карты и строки **#** карты перед номером кредитной карты:</span><span class="sxs-lookup"><span data-stu-id="9f739-165">For example, to include occurrences that have **credit card** and **card #** strings before the credit card number, in a list like this:</span></span>

- <span data-ttu-id="9f739-166">Кредитная карта 45-124576532-123</span><span class="sxs-lookup"><span data-stu-id="9f739-166">Credit card 45-124576532-123</span></span> 
- <span data-ttu-id="9f739-167">45-124576532-123 (может быть номер телефона)</span><span class="sxs-lookup"><span data-stu-id="9f739-167">45-124576532-123  (which could be phone number)</span></span>

<span data-ttu-id="9f739-168">вы можете использовать этот xml</span><span class="sxs-lookup"><span data-stu-id="9f739-168">you can use this xml</span></span>

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

### <a name="textmatchfilter-suffix"></a><span data-ttu-id="9f739-169">TextMatchFilter Suffix</span><span class="sxs-lookup"><span data-stu-id="9f739-169">TextMatchFilter Suffix</span></span>

<span data-ttu-id="9f739-170">Описание. Позволяет определить следующие символы, которые всегда должны быть включены или исключены.</span><span class="sxs-lookup"><span data-stu-id="9f739-170">Description: Allows you to define the following characters that should be always included or excluded.</span></span> <span data-ttu-id="9f739-171">Например, если за номером кредитной карты следует "/xuid", снимите совпадение из допустимого совпадения.</span><span class="sxs-lookup"><span data-stu-id="9f739-171">For example, if Credit card number is followed by ‘/xuid’ then remove the match from the valid matches.</span></span>

<span data-ttu-id="9f739-172">Например, верхний список исключений, если в списке есть еще 5 экземпляров из четырех цифр в качестве суффикса:</span><span class="sxs-lookup"><span data-stu-id="9f739-172">For example, top exclude occurrences if there are 5 more instances of four digits as suffix in a list like this:</span></span>

- <span data-ttu-id="9f739-173">1234-5678-9321 4500 9870 6321 48925566</span><span class="sxs-lookup"><span data-stu-id="9f739-173">1234-5678-9321 4500 9870 6321 48925566</span></span>
- <span data-ttu-id="9f739-174">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="9f739-174">1234-5678-9321</span></span>

<span data-ttu-id="9f739-175">вы можете использовать этот xml</span><span class="sxs-lookup"><span data-stu-id="9f739-175">you can use this xml</span></span>

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
<span data-ttu-id="9f739-176">Например, исключить случаи, если за ними следует **/xuidsuffix,** как и в этом списке:</span><span class="sxs-lookup"><span data-stu-id="9f739-176">For example, to exclude occurrences if they are followed by **/xuidsuffix**, like one in this list:</span></span>

- <span data-ttu-id="9f739-177">1234-5678-9321 /xuid</span><span class="sxs-lookup"><span data-stu-id="9f739-177">1234-5678-9321 /xuid</span></span>
- <span data-ttu-id="9f739-178">1234-5678-9321</span><span class="sxs-lookup"><span data-stu-id="9f739-178">1234-5678-9321</span></span>

<span data-ttu-id="9f739-179">вы можете использовать этот xml</span><span class="sxs-lookup"><span data-stu-id="9f739-179">you can use this xml</span></span>

<span data-ttu-id="9f739-180">''xml <Filters id="cc_number_filters_exc"></span><span class="sxs-lookup"><span data-stu-id="9f739-180">\`\`xml <Filters id="cc_number_filters_exc"></span></span>
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <span data-ttu-id="9f739-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span><span class="sxs-lookup"><span data-stu-id="9f739-181"><Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      </span></span><Term><span data-ttu-id="9f739-182">/xuid</span><span class="sxs-lookup"><span data-stu-id="9f739-182">/xuid</span></span></Term>
    <span data-ttu-id="9f739-183"></Group> </Keyword></span><span class="sxs-lookup"><span data-stu-id="9f739-183"></Group> </Keyword></span></span>
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

## <a name="using-filters-in-rule-packages"></a><span data-ttu-id="9f739-184">Использование фильтров в пакетах правил</span><span class="sxs-lookup"><span data-stu-id="9f739-184">Using filters in rule packages</span></span>

<span data-ttu-id="9f739-185">Фильтры можно определить на всем СИТ или по шаблону.</span><span class="sxs-lookup"><span data-stu-id="9f739-185">Filters can be defined on the entire SIT or on a pattern.</span></span> <span data-ttu-id="9f739-186">Вот некоторые примеры фрагментов кода.</span><span class="sxs-lookup"><span data-stu-id="9f739-186">Here are some code snippets examples.</span></span> 

### <a name="at-sensitive-information-type-level"></a><span data-ttu-id="9f739-187">На уровне типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="9f739-187">At sensitive information type level</span></span>

<span data-ttu-id="9f739-188">Фильтры в Entity — будут охватывать все детские шаблоны</span><span class="sxs-lookup"><span data-stu-id="9f739-188">Filters at Entity - will cover all child patterns</span></span>

<span data-ttu-id="9f739-189">Фильтры будут применяться  во всех экземплярах, классифицированных любыми шаблонами в этом объекте/ конфиденциальном типе.</span><span class="sxs-lookup"><span data-stu-id="9f739-189">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a><span data-ttu-id="9f739-190">В индивидуальном шаблоне уровня типа конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="9f739-190">At the individual pattern of the sensitive information type level</span></span>

<span data-ttu-id="9f739-191">Фильтрует только на уровне шаблона.</span><span class="sxs-lookup"><span data-stu-id="9f739-191">Filters only at the pattern level.</span></span>

<span data-ttu-id="9f739-192">Фильтр будет применяться в экземплярах, которые соответствуют шаблону.</span><span class="sxs-lookup"><span data-stu-id="9f739-192">The filter will be applied on the instances matched by the pattern.</span></span>

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a><span data-ttu-id="9f739-193">На уровне типа конфиденциальной информации и дополнительного фильтра для некоторых шаблонов этого объекта</span><span class="sxs-lookup"><span data-stu-id="9f739-193">At sensitive information type level and an additional filter on some of the patterns of that entity</span></span>

<span data-ttu-id="9f739-194">Фильтры в шаблоне Entity +</span><span class="sxs-lookup"><span data-stu-id="9f739-194">Filters at Entity + pattern</span></span>

<span data-ttu-id="9f739-195">Фильтры будут применяться  во всех экземплярах, классифицируются по любым шаблонам в этом объекте / конфиденциальном типе.</span><span class="sxs-lookup"><span data-stu-id="9f739-195">The filters will be applied on **all** the instances classified by any of the patterns in that entity / sensitive type.</span></span> <span data-ttu-id="9f739-196">Фильтр уровня шаблона будет фильтровать экземпляры, которые соответствуют этому шаблону.</span><span class="sxs-lookup"><span data-stu-id="9f739-196">The pattern level filter will filter the instances matched by that pattern.</span></span>

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a><span data-ttu-id="9f739-197">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="9f739-197">More information</span></span>

- [<span data-ttu-id="9f739-198">Сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="9f739-198">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="9f739-199">Определения объектов типов конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="9f739-199">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="9f739-200">Сведения, для обнаружения которых используются функции защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="9f739-200">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
