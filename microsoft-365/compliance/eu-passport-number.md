---
title: Номер паспорта ЕС
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС Passport Number. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: 44ee6e7b46d79772bcd3aec0fd26265f58f6c4c6
ms.sourcegitcommit: 3fd6d175c1954ce463198e835d1d8f2f91d80d79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2019
ms.locfileid: "39662804"
---
# <a name="eu-passport-number"></a><span data-ttu-id="a4c8f-104">Номер паспорта ЕС</span><span class="sxs-lookup"><span data-stu-id="a4c8f-104">EU Passport Number</span></span>

<span data-ttu-id="a4c8f-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС Passport Number.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="a4c8f-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="a4c8f-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="a4c8f-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-108">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-108">Format</span></span>

<span data-ttu-id="a4c8f-109">Одна буква, за которой следует необязательный пробел и семь цифр</span><span class="sxs-lookup"><span data-stu-id="a4c8f-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-110">Pattern</span></span>

<span data-ttu-id="a4c8f-111">Сочетание одной буквы, семи цифр и одного пробела:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="a4c8f-112">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="a4c8f-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="a4c8f-113">Один пробел (необязательно)</span><span class="sxs-lookup"><span data-stu-id="a4c8f-113">One space (optional)</span></span>
    
- <span data-ttu-id="a4c8f-114">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a4c8f-115">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-115">Checksum</span></span>

<span data-ttu-id="a4c8f-116">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="a4c8f-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-117">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-117">Definition</span></span>

<span data-ttu-id="a4c8f-118">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-119">Регулярное выражение `Regex_austria_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-120">Найдено ключевое `Keywords_austria_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-121">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-121">Keywords</span></span>

<span data-ttu-id="a4c8f-122">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-122"></span></span>
|<span data-ttu-id="a4c8f-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-124">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-124">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-125">Австрийский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="a4c8f-125">austrian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-126">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-126">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-127">реисепасс</span><span class="sxs-lookup"><span data-stu-id="a4c8f-127">reisepass</span></span>  <br/> <span data-ttu-id="a4c8f-128">öстерреичисч реисепасс</span><span class="sxs-lookup"><span data-stu-id="a4c8f-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="a4c8f-129">Бельгия</span><span class="sxs-lookup"><span data-stu-id="a4c8f-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-130">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-130">Format</span></span>

<span data-ttu-id="a4c8f-131">Две буквы, за которыми следуют шесть цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-132">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-132">Pattern</span></span>

<span data-ttu-id="a4c8f-133">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-134">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-134">Checksum</span></span>

<span data-ttu-id="a4c8f-135">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="a4c8f-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-136">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-136">Definition</span></span>

<span data-ttu-id="a4c8f-137">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-138">Регулярное выражение `Regex_belgium_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-139">Найдено ключевое `Keywords_belgium_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-140">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-140">Keywords</span></span>

<span data-ttu-id="a4c8f-141">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-141"></span></span>
|<span data-ttu-id="a4c8f-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-143">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-143">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-144">Бельгийский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="a4c8f-144">belgian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-145">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-145">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-146">паспурт</span><span class="sxs-lookup"><span data-stu-id="a4c8f-146">paspoort</span></span>  <br/> <span data-ttu-id="a4c8f-147">паспуртнуммер</span><span class="sxs-lookup"><span data-stu-id="a4c8f-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="a4c8f-148">реисепасс Кеин</span><span class="sxs-lookup"><span data-stu-id="a4c8f-148">reisepass kein</span></span>  <br/> <span data-ttu-id="a4c8f-149">реисепасс</span><span class="sxs-lookup"><span data-stu-id="a4c8f-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="a4c8f-150">Болгария</span><span class="sxs-lookup"><span data-stu-id="a4c8f-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-151">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-151">Format</span></span>

<span data-ttu-id="a4c8f-152">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-153">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-153">Pattern</span></span>

 <span data-ttu-id="a4c8f-154">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-155">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-155">Checksum</span></span>

<span data-ttu-id="a4c8f-156">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-157">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-157">Definition</span></span>

<span data-ttu-id="a4c8f-158">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-159">Регулярное выражение `Regex_bulgaria_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-160">Найдено ключевое `Keywords_bulgaria_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-161">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-161">Keywords</span></span>

<span data-ttu-id="a4c8f-162">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-162"></span></span>
|<span data-ttu-id="a4c8f-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-164">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-164">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-165">номер паспорта для болгарского языка</span><span class="sxs-lookup"><span data-stu-id="a4c8f-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-166">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-166">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="a4c8f-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="a4c8f-168">Хорватия</span><span class="sxs-lookup"><span data-stu-id="a4c8f-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-169">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-169">Format</span></span>

<span data-ttu-id="a4c8f-170">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-171">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-171">Pattern</span></span>

 <span data-ttu-id="a4c8f-172">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-173">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-173">Checksum</span></span>

<span data-ttu-id="a4c8f-174">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-175">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-175">Definition</span></span>

<span data-ttu-id="a4c8f-176">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-177">Регулярное выражение `Regex_croatia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-178">Найдено ключевое `Keywords_croatia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-179">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-179">Keywords</span></span>

<span data-ttu-id="a4c8f-180">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-180"></span></span>
|<span data-ttu-id="a4c8f-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-182">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-182">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-183">номер паспорта для хорватского языка</span><span class="sxs-lookup"><span data-stu-id="a4c8f-183">croatian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-184">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-184">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-185">Брож путовнице</span><span class="sxs-lookup"><span data-stu-id="a4c8f-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="a4c8f-186">Кипр</span><span class="sxs-lookup"><span data-stu-id="a4c8f-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-187">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-187">Format</span></span>

<span data-ttu-id="a4c8f-188">Одна буква, за которой следуют 6-8 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-189">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-189">Pattern</span></span>

<span data-ttu-id="a4c8f-190">Одна буква, за которой следуют шесть и восемь цифр</span><span class="sxs-lookup"><span data-stu-id="a4c8f-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-191">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-191">Checksum</span></span>

<span data-ttu-id="a4c8f-192">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-193">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-193">Definition</span></span>

<span data-ttu-id="a4c8f-194">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-195">Регулярное выражение `Regex_cyprus_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-196">Найдено ключевое `Keywords_cyprus_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-197">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-197">Keywords</span></span>

<span data-ttu-id="a4c8f-198">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-198"></span></span>
|<span data-ttu-id="a4c8f-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-200">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-200">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-201">номер паспорта для Кипр</span><span class="sxs-lookup"><span data-stu-id="a4c8f-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="a4c8f-202">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-202">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="a4c8f-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="a4c8f-204">Чешская Республика</span><span class="sxs-lookup"><span data-stu-id="a4c8f-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-205">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-205">Format</span></span>

<span data-ttu-id="a4c8f-206">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-207">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-207">Pattern</span></span>

<span data-ttu-id="a4c8f-208">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-209">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-209">Checksum</span></span>

<span data-ttu-id="a4c8f-210">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-211">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-211">Definition</span></span>

<span data-ttu-id="a4c8f-212">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-213">Регулярное выражение `Regex_czech_republic_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-214">Найдено ключевое `Keywords_czech_republic_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-215">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-215">Keywords</span></span>

<span data-ttu-id="a4c8f-216">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-216"></span></span>
|<span data-ttu-id="a4c8f-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-218">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-218">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-219">номер паспорта для чешского языка</span><span class="sxs-lookup"><span data-stu-id="a4c8f-219">czech passport number</span></span>  <br/> <span data-ttu-id="a4c8f-220">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-220">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-221">цестовнí PAS</span><span class="sxs-lookup"><span data-stu-id="a4c8f-221">cestovní pas</span></span>  <br/> <span data-ttu-id="a4c8f-222">соответствующий</span><span class="sxs-lookup"><span data-stu-id="a4c8f-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="a4c8f-223">Дания</span><span class="sxs-lookup"><span data-stu-id="a4c8f-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-224">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-224">Format</span></span>

<span data-ttu-id="a4c8f-225">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-226">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-226">Pattern</span></span>

 <span data-ttu-id="a4c8f-227">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-228">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-228">Checksum</span></span>

<span data-ttu-id="a4c8f-229">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-230">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-230">Definition</span></span>

<span data-ttu-id="a4c8f-231">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-232">Регулярное выражение `Regex_denmark_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-233">Найдено ключевое `Keywords_denmark_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-234">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-234">Keywords</span></span>

<span data-ttu-id="a4c8f-235">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-235"></span></span>
|<span data-ttu-id="a4c8f-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-237">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-237">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-238">номер паспорта для датского языка</span><span class="sxs-lookup"><span data-stu-id="a4c8f-238">danish passport number</span></span>  <br/> <span data-ttu-id="a4c8f-239">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-239">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-240">соответствующий</span><span class="sxs-lookup"><span data-stu-id="a4c8f-240">pas</span></span>  <br/> <span data-ttu-id="a4c8f-241">паснуммер</span><span class="sxs-lookup"><span data-stu-id="a4c8f-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="a4c8f-242">Эстония</span><span class="sxs-lookup"><span data-stu-id="a4c8f-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-243">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-243">Format</span></span>

<span data-ttu-id="a4c8f-244">Одна буква, за которой следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-245">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-245">Pattern</span></span>

<span data-ttu-id="a4c8f-246">Одна буква, за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-247">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-247">Checksum</span></span>

<span data-ttu-id="a4c8f-248">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-249">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-249">Definition</span></span>

<span data-ttu-id="a4c8f-250">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-251">Регулярное выражение `Regex_estonia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-252">Найдено ключевое `Keywords_estonia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-253">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-253">Keywords</span></span>

<span data-ttu-id="a4c8f-254">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-254"></span></span>
|<span data-ttu-id="a4c8f-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-256">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-256">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-257">номер паспорта для Эстонии</span><span class="sxs-lookup"><span data-stu-id="a4c8f-257">estonian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-258">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-258">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-259">Исти коданику Pass</span><span class="sxs-lookup"><span data-stu-id="a4c8f-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="a4c8f-260">Финляндия</span><span class="sxs-lookup"><span data-stu-id="a4c8f-260">Finland</span></span>

<span data-ttu-id="a4c8f-261">Дополнительные сведения можно найти в разделе "Финляндия Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a4c8f-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="a4c8f-262">Франция</span><span class="sxs-lookup"><span data-stu-id="a4c8f-262">France</span></span>

<span data-ttu-id="a4c8f-263">Дополнительные сведения можно найти в разделе "Франция Passport Number", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a4c8f-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="a4c8f-264">Германия</span><span class="sxs-lookup"><span data-stu-id="a4c8f-264">Germany</span></span>

<span data-ttu-id="a4c8f-265">Дополнительные сведения можно найти в разделе "немецкий паспорт номер", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a4c8f-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="a4c8f-266">Греция</span><span class="sxs-lookup"><span data-stu-id="a4c8f-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-267">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-267">Format</span></span>

<span data-ttu-id="a4c8f-268">Две буквы, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-269">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-269">Pattern</span></span>

<span data-ttu-id="a4c8f-270">Две буквы, за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-271">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-271">Checksum</span></span>

<span data-ttu-id="a4c8f-272">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-273">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-273">Definition</span></span>

<span data-ttu-id="a4c8f-274">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-275">Регулярное выражение `Regex_greece_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-276">Найдено ключевое `Keywords_greece_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-277">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-277">Keywords</span></span>

<span data-ttu-id="a4c8f-278">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-278"></span></span>
|<span data-ttu-id="a4c8f-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-280">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-280">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-281">номер паспорта греческого алфавита</span><span class="sxs-lookup"><span data-stu-id="a4c8f-281">greek passport number</span></span>  <br/> <span data-ttu-id="a4c8f-282">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-282">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="a4c8f-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="a4c8f-284">Венгрия</span><span class="sxs-lookup"><span data-stu-id="a4c8f-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-285">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-285">Format</span></span>

<span data-ttu-id="a4c8f-286">Две буквы, за которыми следуют шесть или семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-287">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-287">Pattern</span></span>

<span data-ttu-id="a4c8f-288">Две буквы, за которыми следуют шесть или семь цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-289">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-289">Checksum</span></span>

<span data-ttu-id="a4c8f-290">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-291">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-291">Definition</span></span>

<span data-ttu-id="a4c8f-292">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-293">Регулярное выражение `Regex_hungary_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-294">Найдено ключевое `Keywords_hungary_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-295">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-295">Keywords</span></span>

<span data-ttu-id="a4c8f-296">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-296"></span></span>
|<span data-ttu-id="a4c8f-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-298">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-298">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-299">Венгерский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="a4c8f-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-300">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-300">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-301">úтлевéл сзáма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="a4c8f-302">Ireland (Ирландия)</span><span class="sxs-lookup"><span data-stu-id="a4c8f-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-303">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-303">Format</span></span>

<span data-ttu-id="a4c8f-304">Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-305">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-305">Pattern</span></span>

<span data-ttu-id="a4c8f-306">Две буквы или цифры, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="a4c8f-307">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="a4c8f-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="a4c8f-308">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a4c8f-309">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-309">Checksum</span></span>

<span data-ttu-id="a4c8f-310">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-311">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-311">Definition</span></span>

<span data-ttu-id="a4c8f-312">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-313">Регулярное выражение `Regex_ireland_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-314">Найдено ключевое `Keywords_ireland_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-315">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-315">Keywords</span></span>

<span data-ttu-id="a4c8f-316">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-316"></span></span>
|<span data-ttu-id="a4c8f-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-318">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-318">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-319">Ирландский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="a4c8f-319">irish passport number</span></span>  <br/> <span data-ttu-id="a4c8f-320">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-320">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-321">соответствующий</span><span class="sxs-lookup"><span data-stu-id="a4c8f-321">pas</span></span>  <br/> <span data-ttu-id="a4c8f-322">службу</span><span class="sxs-lookup"><span data-stu-id="a4c8f-322">passport</span></span>  <br/> <span data-ttu-id="a4c8f-323">пассепорт</span><span class="sxs-lookup"><span data-stu-id="a4c8f-323">passeport</span></span>  <br/> <span data-ttu-id="a4c8f-324">пассепорт нумеро</span><span class="sxs-lookup"><span data-stu-id="a4c8f-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="a4c8f-325">Италия</span><span class="sxs-lookup"><span data-stu-id="a4c8f-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-326">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-326">Format</span></span>

<span data-ttu-id="a4c8f-327">Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-328">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-328">Pattern</span></span>

<span data-ttu-id="a4c8f-329">Две буквы или цифры, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="a4c8f-330">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="a4c8f-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="a4c8f-331">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a4c8f-332">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-332">Checksum</span></span>

<span data-ttu-id="a4c8f-333">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="a4c8f-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-334">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-334">Definition</span></span>

<span data-ttu-id="a4c8f-335">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-336">Регулярное выражение `Regex_italy_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-337">Найдено ключевое `Keywords_italy_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-338">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-338">Keywords</span></span>

<span data-ttu-id="a4c8f-339">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-339"></span></span>
|<span data-ttu-id="a4c8f-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-341">номер паспорта для итальянского языка</span><span class="sxs-lookup"><span data-stu-id="a4c8f-341">italian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-342">Репубблика итальянский пассапорто</span><span class="sxs-lookup"><span data-stu-id="a4c8f-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="a4c8f-343">пассапорто</span><span class="sxs-lookup"><span data-stu-id="a4c8f-343">passaporto</span></span>  <br/> <span data-ttu-id="a4c8f-344">пассапорто итальянский</span><span class="sxs-lookup"><span data-stu-id="a4c8f-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="a4c8f-345">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-345">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-346">Итальянский пассапорто нумеро</span><span class="sxs-lookup"><span data-stu-id="a4c8f-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="a4c8f-347">пассапорто нумеро</span><span class="sxs-lookup"><span data-stu-id="a4c8f-347">passaporto numero</span></span>  <br/> <span data-ttu-id="a4c8f-348">нумéро пассепорт италиен</span><span class="sxs-lookup"><span data-stu-id="a4c8f-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="a4c8f-349">нумéро пассепорт</span><span class="sxs-lookup"><span data-stu-id="a4c8f-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="a4c8f-350">Латвия</span><span class="sxs-lookup"><span data-stu-id="a4c8f-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-351">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-351">Format</span></span>

<span data-ttu-id="a4c8f-352">Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-353">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-353">Pattern</span></span>

<span data-ttu-id="a4c8f-354">Две буквы или цифры, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="a4c8f-355">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="a4c8f-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="a4c8f-356">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a4c8f-357">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-357">Checksum</span></span>

<span data-ttu-id="a4c8f-358">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-359">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-359">Definition</span></span>

<span data-ttu-id="a4c8f-360">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-361">Регулярное выражение `Regex_latvia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-362">Найдено ключевое `Keywords_latvia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-363">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-363">Keywords</span></span>

<span data-ttu-id="a4c8f-364">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-364"></span></span>
|<span data-ttu-id="a4c8f-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-366">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-366">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-367">номер паспорта для Латвии</span><span class="sxs-lookup"><span data-stu-id="a4c8f-367">latvian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-368">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-368">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-369">ПАСЕ нумурс</span><span class="sxs-lookup"><span data-stu-id="a4c8f-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="a4c8f-370">Литва</span><span class="sxs-lookup"><span data-stu-id="a4c8f-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-371">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-371">Format</span></span>

<span data-ttu-id="a4c8f-372">Восемь цифр или букв без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-373">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-373">Pattern</span></span>

<span data-ttu-id="a4c8f-374">Восемь цифр или букв (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="a4c8f-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-375">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-375">Checksum</span></span>

<span data-ttu-id="a4c8f-376">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="a4c8f-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-377">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-377">Definition</span></span>

<span data-ttu-id="a4c8f-378">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-379">Регулярное выражение `Regex_lithuania_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-380">Найдено ключевое `Keywords_lithuania_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-381">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-381">Keywords</span></span>

<span data-ttu-id="a4c8f-382">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-382"></span></span>
|<span data-ttu-id="a4c8f-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-384">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-384">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-385">номер паспорта лисуниан</span><span class="sxs-lookup"><span data-stu-id="a4c8f-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-386">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-386">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-387">Пасо нумерис</span><span class="sxs-lookup"><span data-stu-id="a4c8f-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="a4c8f-388">луксембург</span><span class="sxs-lookup"><span data-stu-id="a4c8f-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-389">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-389">Format</span></span>

<span data-ttu-id="a4c8f-390">Восемь цифр или букв без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-391">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-391">Pattern</span></span>

<span data-ttu-id="a4c8f-392">Восемь цифр или букв (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="a4c8f-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-393">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-393">Checksum</span></span>

<span data-ttu-id="a4c8f-394">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-395">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-395">Definition</span></span>

<span data-ttu-id="a4c8f-396">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-397">Регулярное выражение `Regex_nation_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-398">Найдено ключевое `Keywords_nation_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-399">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-399">Keywords</span></span>

<span data-ttu-id="a4c8f-400">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-400"></span></span>
|<span data-ttu-id="a4c8f-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-402">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-402">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-403">номер паспорта для Латвии</span><span class="sxs-lookup"><span data-stu-id="a4c8f-403">latvian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-404">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-404">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-405">пасснуммер</span><span class="sxs-lookup"><span data-stu-id="a4c8f-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="a4c8f-406">Мальта</span><span class="sxs-lookup"><span data-stu-id="a4c8f-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-407">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-407">Format</span></span>

<span data-ttu-id="a4c8f-408">Семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-409">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-409">Pattern</span></span>

 <span data-ttu-id="a4c8f-410">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-411">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-411">Checksum</span></span>

<span data-ttu-id="a4c8f-412">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-413">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-413">Definition</span></span>

<span data-ttu-id="a4c8f-414">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-415">Регулярное выражение `Regex_malta_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-416">Найдено ключевое `Keywords_malta_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-417">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-417">Keywords</span></span>

<span data-ttu-id="a4c8f-418">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-418"></span></span>
|<span data-ttu-id="a4c8f-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-420">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-420">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-421">номер паспорта Мальтийский</span><span class="sxs-lookup"><span data-stu-id="a4c8f-421">maltese passport number</span></span>  <br/> <span data-ttu-id="a4c8f-422">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-422">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-423">нумру Тал — пассапорт</span><span class="sxs-lookup"><span data-stu-id="a4c8f-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="a4c8f-424">Нидерланды</span><span class="sxs-lookup"><span data-stu-id="a4c8f-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-425">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-425">Format</span></span>

<span data-ttu-id="a4c8f-426">Девять букв или цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-427">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-427">Pattern</span></span>

<span data-ttu-id="a4c8f-428">Девять букв или цифр;</span><span class="sxs-lookup"><span data-stu-id="a4c8f-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-429">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-429">Checksum</span></span>

<span data-ttu-id="a4c8f-430">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="a4c8f-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-431">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-431">Definition</span></span>

<span data-ttu-id="a4c8f-432">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-433">Регулярное выражение `Regex_netherlands_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-434">Найдено ключевое `Keywords_netherlands_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-435">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-435">Keywords</span></span>

<span data-ttu-id="a4c8f-436">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-436"></span></span>
|<span data-ttu-id="a4c8f-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-438">номер паспорта для нидерландского языка</span><span class="sxs-lookup"><span data-stu-id="a4c8f-438">dutch passport number</span></span>  <br/> <span data-ttu-id="a4c8f-439">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-439">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-440">номер паспорта Нидерландов</span><span class="sxs-lookup"><span data-stu-id="a4c8f-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="a4c8f-441">недерланден паспурт нуммер</span><span class="sxs-lookup"><span data-stu-id="a4c8f-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="a4c8f-442">паспурт</span><span class="sxs-lookup"><span data-stu-id="a4c8f-442">paspoort</span></span>  <br/> <span data-ttu-id="a4c8f-443">недерланден паспуртнуммер</span><span class="sxs-lookup"><span data-stu-id="a4c8f-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="a4c8f-444">паспуртнуммер</span><span class="sxs-lookup"><span data-stu-id="a4c8f-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="a4c8f-445">Польша</span><span class="sxs-lookup"><span data-stu-id="a4c8f-445">Poland</span></span>

<span data-ttu-id="a4c8f-446">Дополнительные сведения можно найти в разделе "Польша Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a4c8f-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="a4c8f-447">Португалия</span><span class="sxs-lookup"><span data-stu-id="a4c8f-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-448">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-448">Format</span></span>

<span data-ttu-id="a4c8f-449">Одна буква, за которой следуют шесть цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-450">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-450">Pattern</span></span>

<span data-ttu-id="a4c8f-451">Одна буква, за которой следуют шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="a4c8f-452">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="a4c8f-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="a4c8f-453">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a4c8f-454">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-454">Checksum</span></span>

<span data-ttu-id="a4c8f-455">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-456">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-456">Definition</span></span>

<span data-ttu-id="a4c8f-457">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-458">Регулярное выражение `Regex_portugal_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-459">Найдено ключевое `Keywords_portugal_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-460">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-460">Keywords</span></span>

<span data-ttu-id="a4c8f-461">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-461"></span></span>
|<span data-ttu-id="a4c8f-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-463">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-463">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-464">номер паспорта для португальского языка</span><span class="sxs-lookup"><span data-stu-id="a4c8f-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="a4c8f-465">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-465">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-466">нúмеро Do пассапорте</span><span class="sxs-lookup"><span data-stu-id="a4c8f-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="a4c8f-467">Румыния</span><span class="sxs-lookup"><span data-stu-id="a4c8f-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-468">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-468">Format</span></span>

<span data-ttu-id="a4c8f-469">Восемь или девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-470">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-470">Pattern</span></span>

<span data-ttu-id="a4c8f-471">Восемь или девять цифр</span><span class="sxs-lookup"><span data-stu-id="a4c8f-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-472">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-472">Checksum</span></span>

<span data-ttu-id="a4c8f-473">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-474">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-474">Definition</span></span>

<span data-ttu-id="a4c8f-475">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-476">Регулярное выражение `Regex_romania_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-477">Найдено ключевое `Keywords_romania_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-478">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-478">Keywords</span></span>

<span data-ttu-id="a4c8f-479">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-479"></span></span>
|<span data-ttu-id="a4c8f-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-481">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-481">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-482">номер паспорта для румынского языка</span><span class="sxs-lookup"><span data-stu-id="a4c8f-482">romanian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-483">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-483">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-484">нумăрул паșапортулуи</span><span class="sxs-lookup"><span data-stu-id="a4c8f-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="a4c8f-485">Словакия</span><span class="sxs-lookup"><span data-stu-id="a4c8f-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-486">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-486">Format</span></span>

<span data-ttu-id="a4c8f-487">Одна цифра или буква, за которой следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-488">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-488">Pattern</span></span>

<span data-ttu-id="a4c8f-489">Одна цифра или буква (без учета регистра), за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a4c8f-490">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-490">Checksum</span></span>

<span data-ttu-id="a4c8f-491">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-492">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-492">Definition</span></span>

<span data-ttu-id="a4c8f-493">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-494">Регулярное выражение `Regex_slovakia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-495">Найдено ключевое `Keywords_slovakia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-496">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-496">Keywords</span></span>

<span data-ttu-id="a4c8f-497">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-497"></span></span>
|<span data-ttu-id="a4c8f-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-499">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-499">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-500">номер паспорта словакиан</span><span class="sxs-lookup"><span data-stu-id="a4c8f-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-501">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-501">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-502">číсло Пасу</span><span class="sxs-lookup"><span data-stu-id="a4c8f-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="a4c8f-503">Словения</span><span class="sxs-lookup"><span data-stu-id="a4c8f-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-504">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-504">Format</span></span>

<span data-ttu-id="a4c8f-505">Две буквы, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-506">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-506">Pattern</span></span>

<span data-ttu-id="a4c8f-507">Две буквы, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="a4c8f-508">Буква "P"</span><span class="sxs-lookup"><span data-stu-id="a4c8f-508">The letter "P"</span></span>
    
- <span data-ttu-id="a4c8f-509">Одна прописная буква</span><span class="sxs-lookup"><span data-stu-id="a4c8f-509">One uppercase letter</span></span>
    
- <span data-ttu-id="a4c8f-510">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a4c8f-511">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-511">Checksum</span></span>

<span data-ttu-id="a4c8f-512">Нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-513">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-513">Definition</span></span>

<span data-ttu-id="a4c8f-514">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-515">Регулярное выражение `Regex_slovenia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-516">Найдено ключевое `Keywords_slovenia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-517">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-517">Keywords</span></span>

<span data-ttu-id="a4c8f-518">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-518"></span></span>
|<span data-ttu-id="a4c8f-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-520">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-520">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-521">номер паспорта для словенского языка</span><span class="sxs-lookup"><span data-stu-id="a4c8f-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="a4c8f-522">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-522">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-523">Список потнега šтевилка</span><span class="sxs-lookup"><span data-stu-id="a4c8f-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="a4c8f-524">Испания</span><span class="sxs-lookup"><span data-stu-id="a4c8f-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="a4c8f-525">Format</span><span class="sxs-lookup"><span data-stu-id="a4c8f-525">Format</span></span>

<span data-ttu-id="a4c8f-526">Сочетание букв и цифр из восьми или девяти символов без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="a4c8f-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a4c8f-527">Шаблон</span><span class="sxs-lookup"><span data-stu-id="a4c8f-527">Pattern</span></span>

<span data-ttu-id="a4c8f-528">Сочетание букв и цифр из восьми или девяти символов:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="a4c8f-529">Две цифры или буквы</span><span class="sxs-lookup"><span data-stu-id="a4c8f-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="a4c8f-530">Одна цифра или буква (необязательно)</span><span class="sxs-lookup"><span data-stu-id="a4c8f-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="a4c8f-531">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a4c8f-532">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="a4c8f-532">Checksum</span></span>

<span data-ttu-id="a4c8f-533">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="a4c8f-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a4c8f-534">Определение</span><span class="sxs-lookup"><span data-stu-id="a4c8f-534">Definition</span></span>

<span data-ttu-id="a4c8f-535">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="a4c8f-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a4c8f-536">Регулярное выражение `Regex_spain_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a4c8f-537">Найдено ключевое `Keywords_spain_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="a4c8f-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a4c8f-538">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="a4c8f-538">Keywords</span></span>

<span data-ttu-id="a4c8f-539">| |</span><span class="sxs-lookup"><span data-stu-id="a4c8f-539"></span></span>
|<span data-ttu-id="a4c8f-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="a4c8f-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="a4c8f-541">службу</span><span class="sxs-lookup"><span data-stu-id="a4c8f-541">passport</span></span>  <br/> <span data-ttu-id="a4c8f-542">Служба Passport, Испания</span><span class="sxs-lookup"><span data-stu-id="a4c8f-542">spain passport</span></span>  <br/> <span data-ttu-id="a4c8f-543">Книга Passport</span><span class="sxs-lookup"><span data-stu-id="a4c8f-543">passport book</span></span>  <br/> <span data-ttu-id="a4c8f-544">passport number</span><span class="sxs-lookup"><span data-stu-id="a4c8f-544">passport number</span></span>  <br/> <span data-ttu-id="a4c8f-545">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="a4c8f-545">passport no</span></span>  <br/> <span data-ttu-id="a4c8f-546">либрета пасапорте</span><span class="sxs-lookup"><span data-stu-id="a4c8f-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="a4c8f-547">нúмеро пасапорте</span><span class="sxs-lookup"><span data-stu-id="a4c8f-547">número pasaporte</span></span>  <br/> <span data-ttu-id="a4c8f-548">еспаñа пасапорте</span><span class="sxs-lookup"><span data-stu-id="a4c8f-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="a4c8f-549">пасапорте</span><span class="sxs-lookup"><span data-stu-id="a4c8f-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="a4c8f-550">Швеция</span><span class="sxs-lookup"><span data-stu-id="a4c8f-550">Sweden</span></span>

<span data-ttu-id="a4c8f-551">Дополнительные сведения можно найти в разделе "Швеции Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a4c8f-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="a4c8f-552">ВОЗМЕЩЕН</span><span class="sxs-lookup"><span data-stu-id="a4c8f-552">UK</span></span>

<span data-ttu-id="a4c8f-553">Дополнительные сведения см. в разделе "США/Великобритания</span><span class="sxs-lookup"><span data-stu-id="a4c8f-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="a4c8f-554">Номер паспорта [, который ищет типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="a4c8f-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a4c8f-555">См. также</span><span class="sxs-lookup"><span data-stu-id="a4c8f-555">See also</span></span>

[<span data-ttu-id="a4c8f-556">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="a4c8f-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

