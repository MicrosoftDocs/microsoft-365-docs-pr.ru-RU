---
title: Номер паспорта ЕС
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС Passport Number. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090272"
---
# <a name="eu-passport-number"></a><span data-ttu-id="79f5e-104">Номер паспорта ЕС</span><span class="sxs-lookup"><span data-stu-id="79f5e-104">EU Passport Number</span></span>

<span data-ttu-id="79f5e-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС Passport Number.</span><span class="sxs-lookup"><span data-stu-id="79f5e-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="79f5e-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="79f5e-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="79f5e-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="79f5e-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-108">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-108">Format</span></span>

<span data-ttu-id="79f5e-109">Одна буква, за которой следует необязательный пробел и семь цифр</span><span class="sxs-lookup"><span data-stu-id="79f5e-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-110">Pattern</span></span>

<span data-ttu-id="79f5e-111">Сочетание одной буквы, семи цифр и одного пробела:</span><span class="sxs-lookup"><span data-stu-id="79f5e-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="79f5e-112">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="79f5e-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="79f5e-113">Один пробел (необязательно)</span><span class="sxs-lookup"><span data-stu-id="79f5e-113">One space (optional)</span></span>
    
- <span data-ttu-id="79f5e-114">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79f5e-115">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-115">Checksum</span></span>

<span data-ttu-id="79f5e-116">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="79f5e-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-117">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-117">Definition</span></span>

<span data-ttu-id="79f5e-118">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-119">Регулярное выражение `Regex_austria_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-120">Найдено ключевое `Keywords_austria_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-121">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-121">Keywords</span></span>

<span data-ttu-id="79f5e-122">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-122"></span></span>
|<span data-ttu-id="79f5e-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-124">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-124">passport number</span></span>  <br/> <span data-ttu-id="79f5e-125">Австрийский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="79f5e-125">austrian passport number</span></span>  <br/> <span data-ttu-id="79f5e-126">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-126">passport no</span></span>  <br/> <span data-ttu-id="79f5e-127">реисепасс</span><span class="sxs-lookup"><span data-stu-id="79f5e-127">reisepass</span></span>  <br/> <span data-ttu-id="79f5e-128">öстерреичисч реисепасс</span><span class="sxs-lookup"><span data-stu-id="79f5e-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="79f5e-129">Бельгия</span><span class="sxs-lookup"><span data-stu-id="79f5e-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-130">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-130">Format</span></span>

<span data-ttu-id="79f5e-131">Две буквы, за которыми следуют шесть цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-132">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-132">Pattern</span></span>

<span data-ttu-id="79f5e-133">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79f5e-134">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-134">Checksum</span></span>

<span data-ttu-id="79f5e-135">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="79f5e-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-136">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-136">Definition</span></span>

<span data-ttu-id="79f5e-137">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-138">Регулярное выражение `Regex_belgium_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-139">Найдено ключевое `Keywords_belgium_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-140">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-140">Keywords</span></span>

<span data-ttu-id="79f5e-141">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-141"></span></span>
|<span data-ttu-id="79f5e-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-143">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-143">passport number</span></span>  <br/> <span data-ttu-id="79f5e-144">Бельгийский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="79f5e-144">belgian passport number</span></span>  <br/> <span data-ttu-id="79f5e-145">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-145">passport no</span></span>  <br/> <span data-ttu-id="79f5e-146">паспурт</span><span class="sxs-lookup"><span data-stu-id="79f5e-146">paspoort</span></span>  <br/> <span data-ttu-id="79f5e-147">паспуртнуммер</span><span class="sxs-lookup"><span data-stu-id="79f5e-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="79f5e-148">реисепасс Кеин</span><span class="sxs-lookup"><span data-stu-id="79f5e-148">reisepass kein</span></span>  <br/> <span data-ttu-id="79f5e-149">реисепасс</span><span class="sxs-lookup"><span data-stu-id="79f5e-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="79f5e-150">Болгария</span><span class="sxs-lookup"><span data-stu-id="79f5e-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-151">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-151">Format</span></span>

<span data-ttu-id="79f5e-152">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-153">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-153">Pattern</span></span>

 <span data-ttu-id="79f5e-154">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="79f5e-155">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-155">Checksum</span></span>

<span data-ttu-id="79f5e-156">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-157">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-157">Definition</span></span>

<span data-ttu-id="79f5e-158">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-159">Регулярное выражение `Regex_bulgaria_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-160">Найдено ключевое `Keywords_bulgaria_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-161">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-161">Keywords</span></span>

<span data-ttu-id="79f5e-162">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-162"></span></span>
|<span data-ttu-id="79f5e-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-164">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-164">passport number</span></span>  <br/> <span data-ttu-id="79f5e-165">номер паспорта для болгарского языка</span><span class="sxs-lookup"><span data-stu-id="79f5e-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="79f5e-166">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-166">passport no</span></span>  <br/> <span data-ttu-id="79f5e-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="79f5e-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="79f5e-168">Хорватия</span><span class="sxs-lookup"><span data-stu-id="79f5e-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-169">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-169">Format</span></span>

<span data-ttu-id="79f5e-170">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-171">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-171">Pattern</span></span>

 <span data-ttu-id="79f5e-172">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="79f5e-173">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-173">Checksum</span></span>

<span data-ttu-id="79f5e-174">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-175">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-175">Definition</span></span>

<span data-ttu-id="79f5e-176">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-177">Регулярное выражение `Regex_croatia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-178">Найдено ключевое `Keywords_croatia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-179">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-179">Keywords</span></span>

<span data-ttu-id="79f5e-180">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-180"></span></span>
|<span data-ttu-id="79f5e-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-182">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-182">passport number</span></span>  <br/> <span data-ttu-id="79f5e-183">номер паспорта для хорватского языка</span><span class="sxs-lookup"><span data-stu-id="79f5e-183">croatian passport number</span></span>  <br/> <span data-ttu-id="79f5e-184">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-184">passport no</span></span>  <br/> <span data-ttu-id="79f5e-185">Брож путовнице</span><span class="sxs-lookup"><span data-stu-id="79f5e-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="79f5e-186">Кипр</span><span class="sxs-lookup"><span data-stu-id="79f5e-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-187">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-187">Format</span></span>

<span data-ttu-id="79f5e-188">Одна буква, за которой следуют 6-8 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-189">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-189">Pattern</span></span>

<span data-ttu-id="79f5e-190">Одна буква, за которой следуют шесть и восемь цифр</span><span class="sxs-lookup"><span data-stu-id="79f5e-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79f5e-191">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-191">Checksum</span></span>

<span data-ttu-id="79f5e-192">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-193">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-193">Definition</span></span>

<span data-ttu-id="79f5e-194">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-195">Регулярное выражение `Regex_cyprus_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-196">Найдено ключевое `Keywords_cyprus_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-197">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-197">Keywords</span></span>

<span data-ttu-id="79f5e-198">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-198"></span></span>
|<span data-ttu-id="79f5e-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-200">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-200">passport number</span></span>  <br/> <span data-ttu-id="79f5e-201">номер паспорта для Кипр</span><span class="sxs-lookup"><span data-stu-id="79f5e-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="79f5e-202">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-202">passport no</span></span>  <br/> <span data-ttu-id="79f5e-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="79f5e-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="79f5e-204">Чешская Республика</span><span class="sxs-lookup"><span data-stu-id="79f5e-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-205">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-205">Format</span></span>

<span data-ttu-id="79f5e-206">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-207">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-207">Pattern</span></span>

<span data-ttu-id="79f5e-208">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79f5e-209">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-209">Checksum</span></span>

<span data-ttu-id="79f5e-210">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-211">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-211">Definition</span></span>

<span data-ttu-id="79f5e-212">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-213">Регулярное выражение `Regex_czech_republic_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-214">Найдено ключевое `Keywords_czech_republic_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-215">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-215">Keywords</span></span>

<span data-ttu-id="79f5e-216">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-216"></span></span>
|<span data-ttu-id="79f5e-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-218">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-218">passport number</span></span>  <br/> <span data-ttu-id="79f5e-219">номер паспорта для чешского языка</span><span class="sxs-lookup"><span data-stu-id="79f5e-219">czech passport number</span></span>  <br/> <span data-ttu-id="79f5e-220">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-220">passport no</span></span>  <br/> <span data-ttu-id="79f5e-221">цестовнí PAS</span><span class="sxs-lookup"><span data-stu-id="79f5e-221">cestovní pas</span></span>  <br/> <span data-ttu-id="79f5e-222">соответствующий</span><span class="sxs-lookup"><span data-stu-id="79f5e-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="79f5e-223">Дания</span><span class="sxs-lookup"><span data-stu-id="79f5e-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-224">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-224">Format</span></span>

<span data-ttu-id="79f5e-225">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-226">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-226">Pattern</span></span>

 <span data-ttu-id="79f5e-227">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="79f5e-228">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-228">Checksum</span></span>

<span data-ttu-id="79f5e-229">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-230">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-230">Definition</span></span>

<span data-ttu-id="79f5e-231">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-232">Регулярное выражение `Regex_denmark_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-233">Найдено ключевое `Keywords_denmark_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-234">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-234">Keywords</span></span>

<span data-ttu-id="79f5e-235">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-235"></span></span>
|<span data-ttu-id="79f5e-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-237">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-237">passport number</span></span>  <br/> <span data-ttu-id="79f5e-238">номер паспорта для датского языка</span><span class="sxs-lookup"><span data-stu-id="79f5e-238">danish passport number</span></span>  <br/> <span data-ttu-id="79f5e-239">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-239">passport no</span></span>  <br/> <span data-ttu-id="79f5e-240">соответствующий</span><span class="sxs-lookup"><span data-stu-id="79f5e-240">pas</span></span>  <br/> <span data-ttu-id="79f5e-241">паснуммер</span><span class="sxs-lookup"><span data-stu-id="79f5e-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="79f5e-242">Эстония</span><span class="sxs-lookup"><span data-stu-id="79f5e-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-243">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-243">Format</span></span>

<span data-ttu-id="79f5e-244">Одна буква, за которой следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-245">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-245">Pattern</span></span>

<span data-ttu-id="79f5e-246">Одна буква, за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79f5e-247">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-247">Checksum</span></span>

<span data-ttu-id="79f5e-248">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-249">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-249">Definition</span></span>

<span data-ttu-id="79f5e-250">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-251">Регулярное выражение `Regex_estonia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-252">Найдено ключевое `Keywords_estonia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-253">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-253">Keywords</span></span>

<span data-ttu-id="79f5e-254">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-254"></span></span>
|<span data-ttu-id="79f5e-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-256">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-256">passport number</span></span>  <br/> <span data-ttu-id="79f5e-257">номер паспорта для Эстонии</span><span class="sxs-lookup"><span data-stu-id="79f5e-257">estonian passport number</span></span>  <br/> <span data-ttu-id="79f5e-258">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-258">passport no</span></span>  <br/> <span data-ttu-id="79f5e-259">Исти коданику Pass</span><span class="sxs-lookup"><span data-stu-id="79f5e-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="79f5e-260">Финляндия</span><span class="sxs-lookup"><span data-stu-id="79f5e-260">Finland</span></span>

<span data-ttu-id="79f5e-261">Дополнительные сведения можно найти в разделе "Финляндия Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79f5e-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="79f5e-262">Франция</span><span class="sxs-lookup"><span data-stu-id="79f5e-262">France</span></span>

<span data-ttu-id="79f5e-263">Дополнительные сведения можно найти в разделе "Франция Passport Number", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79f5e-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="79f5e-264">Германия</span><span class="sxs-lookup"><span data-stu-id="79f5e-264">Germany</span></span>

<span data-ttu-id="79f5e-265">Дополнительные сведения можно найти в разделе "Германия Passport Number", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79f5e-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="79f5e-266">Греция</span><span class="sxs-lookup"><span data-stu-id="79f5e-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-267">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-267">Format</span></span>

<span data-ttu-id="79f5e-268">Две буквы, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-269">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-269">Pattern</span></span>

<span data-ttu-id="79f5e-270">Две буквы, за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79f5e-271">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-271">Checksum</span></span>

<span data-ttu-id="79f5e-272">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-273">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-273">Definition</span></span>

<span data-ttu-id="79f5e-274">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-275">Регулярное выражение `Regex_greece_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-276">Найдено ключевое `Keywords_greece_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-277">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-277">Keywords</span></span>

<span data-ttu-id="79f5e-278">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-278"></span></span>
|<span data-ttu-id="79f5e-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-280">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-280">passport number</span></span>  <br/> <span data-ttu-id="79f5e-281">номер паспорта греческого алфавита</span><span class="sxs-lookup"><span data-stu-id="79f5e-281">greek passport number</span></span>  <br/> <span data-ttu-id="79f5e-282">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-282">passport no</span></span>  <br/> <span data-ttu-id="79f5e-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="79f5e-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="79f5e-284">Венгрия</span><span class="sxs-lookup"><span data-stu-id="79f5e-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-285">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-285">Format</span></span>

<span data-ttu-id="79f5e-286">Две буквы, за которыми следуют шесть или семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-287">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-287">Pattern</span></span>

<span data-ttu-id="79f5e-288">Две буквы, за которыми следуют шесть или семь цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79f5e-289">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-289">Checksum</span></span>

<span data-ttu-id="79f5e-290">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-291">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-291">Definition</span></span>

<span data-ttu-id="79f5e-292">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-293">Регулярное выражение `Regex_hungary_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-294">Найдено ключевое `Keywords_hungary_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-295">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-295">Keywords</span></span>

<span data-ttu-id="79f5e-296">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-296"></span></span>
|<span data-ttu-id="79f5e-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-298">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-298">passport number</span></span>  <br/> <span data-ttu-id="79f5e-299">Венгерский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="79f5e-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="79f5e-300">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-300">passport no</span></span>  <br/> <span data-ttu-id="79f5e-301">úтлевéл сзáма</span><span class="sxs-lookup"><span data-stu-id="79f5e-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="79f5e-302">Ireland (Ирландия)</span><span class="sxs-lookup"><span data-stu-id="79f5e-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-303">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-303">Format</span></span>

<span data-ttu-id="79f5e-304">Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-305">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-305">Pattern</span></span>

<span data-ttu-id="79f5e-306">Две буквы или цифры, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="79f5e-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="79f5e-307">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="79f5e-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="79f5e-308">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79f5e-309">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-309">Checksum</span></span>

<span data-ttu-id="79f5e-310">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-311">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-311">Definition</span></span>

<span data-ttu-id="79f5e-312">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-313">Регулярное выражение `Regex_ireland_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-314">Найдено ключевое `Keywords_ireland_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-315">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-315">Keywords</span></span>

<span data-ttu-id="79f5e-316">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-316"></span></span>
|<span data-ttu-id="79f5e-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-318">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-318">passport number</span></span>  <br/> <span data-ttu-id="79f5e-319">Ирландский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="79f5e-319">irish passport number</span></span>  <br/> <span data-ttu-id="79f5e-320">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-320">passport no</span></span>  <br/> <span data-ttu-id="79f5e-321">соответствующий</span><span class="sxs-lookup"><span data-stu-id="79f5e-321">pas</span></span>  <br/> <span data-ttu-id="79f5e-322">службу</span><span class="sxs-lookup"><span data-stu-id="79f5e-322">passport</span></span>  <br/> <span data-ttu-id="79f5e-323">пассепорт</span><span class="sxs-lookup"><span data-stu-id="79f5e-323">passeport</span></span>  <br/> <span data-ttu-id="79f5e-324">пассепорт нумеро</span><span class="sxs-lookup"><span data-stu-id="79f5e-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="79f5e-325">Италия</span><span class="sxs-lookup"><span data-stu-id="79f5e-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-326">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-326">Format</span></span>

<span data-ttu-id="79f5e-327">Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-328">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-328">Pattern</span></span>

<span data-ttu-id="79f5e-329">Две буквы или цифры, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="79f5e-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="79f5e-330">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="79f5e-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="79f5e-331">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79f5e-332">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-332">Checksum</span></span>

<span data-ttu-id="79f5e-333">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="79f5e-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-334">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-334">Definition</span></span>

<span data-ttu-id="79f5e-335">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-336">Регулярное выражение `Regex_italy_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-337">Найдено ключевое `Keywords_italy_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-338">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-338">Keywords</span></span>

<span data-ttu-id="79f5e-339">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-339"></span></span>
|<span data-ttu-id="79f5e-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-341">номер паспорта для итальянского языка</span><span class="sxs-lookup"><span data-stu-id="79f5e-341">italian passport number</span></span>  <br/> <span data-ttu-id="79f5e-342">Репубблика итальянский пассапорто</span><span class="sxs-lookup"><span data-stu-id="79f5e-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="79f5e-343">пассапорто</span><span class="sxs-lookup"><span data-stu-id="79f5e-343">passaporto</span></span>  <br/> <span data-ttu-id="79f5e-344">пассапорто итальянский</span><span class="sxs-lookup"><span data-stu-id="79f5e-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="79f5e-345">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-345">passport number</span></span>  <br/> <span data-ttu-id="79f5e-346">Итальянский пассапорто нумеро</span><span class="sxs-lookup"><span data-stu-id="79f5e-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="79f5e-347">пассапорто нумеро</span><span class="sxs-lookup"><span data-stu-id="79f5e-347">passaporto numero</span></span>  <br/> <span data-ttu-id="79f5e-348">нумéро пассепорт италиен</span><span class="sxs-lookup"><span data-stu-id="79f5e-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="79f5e-349">нумéро пассепорт</span><span class="sxs-lookup"><span data-stu-id="79f5e-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="79f5e-350">Латвия</span><span class="sxs-lookup"><span data-stu-id="79f5e-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-351">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-351">Format</span></span>

<span data-ttu-id="79f5e-352">Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-353">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-353">Pattern</span></span>

<span data-ttu-id="79f5e-354">Две буквы или цифры, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="79f5e-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="79f5e-355">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="79f5e-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="79f5e-356">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79f5e-357">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-357">Checksum</span></span>

<span data-ttu-id="79f5e-358">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-359">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-359">Definition</span></span>

<span data-ttu-id="79f5e-360">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-361">Регулярное выражение `Regex_latvia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-362">Найдено ключевое `Keywords_latvia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-363">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-363">Keywords</span></span>

<span data-ttu-id="79f5e-364">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-364"></span></span>
|<span data-ttu-id="79f5e-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-366">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-366">passport number</span></span>  <br/> <span data-ttu-id="79f5e-367">номер паспорта для Латвии</span><span class="sxs-lookup"><span data-stu-id="79f5e-367">latvian passport number</span></span>  <br/> <span data-ttu-id="79f5e-368">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-368">passport no</span></span>  <br/> <span data-ttu-id="79f5e-369">ПАСЕ нумурс</span><span class="sxs-lookup"><span data-stu-id="79f5e-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="79f5e-370">Литва</span><span class="sxs-lookup"><span data-stu-id="79f5e-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-371">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-371">Format</span></span>

<span data-ttu-id="79f5e-372">Восемь цифр или букв без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-373">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-373">Pattern</span></span>

<span data-ttu-id="79f5e-374">Восемь цифр или букв (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="79f5e-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79f5e-375">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-375">Checksum</span></span>

<span data-ttu-id="79f5e-376">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="79f5e-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-377">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-377">Definition</span></span>

<span data-ttu-id="79f5e-378">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-379">Регулярное выражение `Regex_lithuania_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-380">Найдено ключевое `Keywords_lithuania_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-381">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-381">Keywords</span></span>

<span data-ttu-id="79f5e-382">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-382"></span></span>
|<span data-ttu-id="79f5e-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-384">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-384">passport number</span></span>  <br/> <span data-ttu-id="79f5e-385">номер паспорта лисуниан</span><span class="sxs-lookup"><span data-stu-id="79f5e-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="79f5e-386">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-386">passport no</span></span>  <br/> <span data-ttu-id="79f5e-387">Пасо нумерис</span><span class="sxs-lookup"><span data-stu-id="79f5e-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="79f5e-388">луксембург</span><span class="sxs-lookup"><span data-stu-id="79f5e-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-389">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-389">Format</span></span>

<span data-ttu-id="79f5e-390">Восемь цифр или букв без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-391">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-391">Pattern</span></span>

<span data-ttu-id="79f5e-392">Восемь цифр или букв (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="79f5e-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79f5e-393">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-393">Checksum</span></span>

<span data-ttu-id="79f5e-394">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-395">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-395">Definition</span></span>

<span data-ttu-id="79f5e-396">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-397">Регулярное выражение `Regex_nation_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-398">Найдено ключевое `Keywords_nation_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-399">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-399">Keywords</span></span>

<span data-ttu-id="79f5e-400">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-400"></span></span>
|<span data-ttu-id="79f5e-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-402">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-402">passport number</span></span>  <br/> <span data-ttu-id="79f5e-403">номер паспорта для Латвии</span><span class="sxs-lookup"><span data-stu-id="79f5e-403">latvian passport number</span></span>  <br/> <span data-ttu-id="79f5e-404">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-404">passport no</span></span>  <br/> <span data-ttu-id="79f5e-405">пасснуммер</span><span class="sxs-lookup"><span data-stu-id="79f5e-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="79f5e-406">Мальта</span><span class="sxs-lookup"><span data-stu-id="79f5e-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-407">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-407">Format</span></span>

<span data-ttu-id="79f5e-408">Семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-409">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-409">Pattern</span></span>

 <span data-ttu-id="79f5e-410">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="79f5e-411">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-411">Checksum</span></span>

<span data-ttu-id="79f5e-412">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-413">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-413">Definition</span></span>

<span data-ttu-id="79f5e-414">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-415">Регулярное выражение `Regex_malta_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-416">Найдено ключевое `Keywords_malta_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-417">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-417">Keywords</span></span>

<span data-ttu-id="79f5e-418">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-418"></span></span>
|<span data-ttu-id="79f5e-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-420">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-420">passport number</span></span>  <br/> <span data-ttu-id="79f5e-421">номер паспорта Мальтийский</span><span class="sxs-lookup"><span data-stu-id="79f5e-421">maltese passport number</span></span>  <br/> <span data-ttu-id="79f5e-422">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-422">passport no</span></span>  <br/> <span data-ttu-id="79f5e-423">нумру Тал — пассапорт</span><span class="sxs-lookup"><span data-stu-id="79f5e-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="79f5e-424">Нидерланды</span><span class="sxs-lookup"><span data-stu-id="79f5e-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-425">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-425">Format</span></span>

<span data-ttu-id="79f5e-426">Девять букв или цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-427">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-427">Pattern</span></span>

<span data-ttu-id="79f5e-428">Девять букв или цифр;</span><span class="sxs-lookup"><span data-stu-id="79f5e-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79f5e-429">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-429">Checksum</span></span>

<span data-ttu-id="79f5e-430">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="79f5e-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-431">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-431">Definition</span></span>

<span data-ttu-id="79f5e-432">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-433">Регулярное выражение `Regex_netherlands_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-434">Найдено ключевое `Keywords_netherlands_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-435">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-435">Keywords</span></span>

<span data-ttu-id="79f5e-436">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-436"></span></span>
|<span data-ttu-id="79f5e-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-438">номер паспорта для нидерландского языка</span><span class="sxs-lookup"><span data-stu-id="79f5e-438">dutch passport number</span></span>  <br/> <span data-ttu-id="79f5e-439">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-439">passport number</span></span>  <br/> <span data-ttu-id="79f5e-440">номер паспорта Нидерландов</span><span class="sxs-lookup"><span data-stu-id="79f5e-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="79f5e-441">недерланден паспурт нуммер</span><span class="sxs-lookup"><span data-stu-id="79f5e-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="79f5e-442">паспурт</span><span class="sxs-lookup"><span data-stu-id="79f5e-442">paspoort</span></span>  <br/> <span data-ttu-id="79f5e-443">недерланден паспуртнуммер</span><span class="sxs-lookup"><span data-stu-id="79f5e-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="79f5e-444">паспуртнуммер</span><span class="sxs-lookup"><span data-stu-id="79f5e-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="79f5e-445">Польша</span><span class="sxs-lookup"><span data-stu-id="79f5e-445">Poland</span></span>

<span data-ttu-id="79f5e-446">Дополнительные сведения можно найти в разделе "Польша Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79f5e-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="79f5e-447">Португалия</span><span class="sxs-lookup"><span data-stu-id="79f5e-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-448">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-448">Format</span></span>

<span data-ttu-id="79f5e-449">Одна буква, за которой следуют шесть цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-450">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-450">Pattern</span></span>

<span data-ttu-id="79f5e-451">Одна буква, за которой следуют шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="79f5e-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="79f5e-452">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="79f5e-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="79f5e-453">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79f5e-454">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-454">Checksum</span></span>

<span data-ttu-id="79f5e-455">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-456">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-456">Definition</span></span>

<span data-ttu-id="79f5e-457">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-458">Регулярное выражение `Regex_portugal_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-459">Найдено ключевое `Keywords_portugal_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-460">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-460">Keywords</span></span>

<span data-ttu-id="79f5e-461">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-461"></span></span>
|<span data-ttu-id="79f5e-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-463">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-463">passport number</span></span>  <br/> <span data-ttu-id="79f5e-464">номер паспорта для португальского языка</span><span class="sxs-lookup"><span data-stu-id="79f5e-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="79f5e-465">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-465">passport no</span></span>  <br/> <span data-ttu-id="79f5e-466">нúмеро Do пассапорте</span><span class="sxs-lookup"><span data-stu-id="79f5e-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="79f5e-467">Румыния</span><span class="sxs-lookup"><span data-stu-id="79f5e-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-468">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-468">Format</span></span>

<span data-ttu-id="79f5e-469">Восемь или девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-470">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-470">Pattern</span></span>

<span data-ttu-id="79f5e-471">Восемь или девять цифр</span><span class="sxs-lookup"><span data-stu-id="79f5e-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79f5e-472">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-472">Checksum</span></span>

<span data-ttu-id="79f5e-473">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-474">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-474">Definition</span></span>

<span data-ttu-id="79f5e-475">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-476">Регулярное выражение `Regex_romania_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-477">Найдено ключевое `Keywords_romania_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-478">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-478">Keywords</span></span>

<span data-ttu-id="79f5e-479">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-479"></span></span>
|<span data-ttu-id="79f5e-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-481">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-481">passport number</span></span>  <br/> <span data-ttu-id="79f5e-482">номер паспорта для румынского языка</span><span class="sxs-lookup"><span data-stu-id="79f5e-482">romanian passport number</span></span>  <br/> <span data-ttu-id="79f5e-483">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-483">passport no</span></span>  <br/> <span data-ttu-id="79f5e-484">нумăрул паșапортулуи</span><span class="sxs-lookup"><span data-stu-id="79f5e-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="79f5e-485">Словакия</span><span class="sxs-lookup"><span data-stu-id="79f5e-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-486">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-486">Format</span></span>

<span data-ttu-id="79f5e-487">Одна цифра или буква, за которой следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-488">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-488">Pattern</span></span>

<span data-ttu-id="79f5e-489">Одна цифра или буква (без учета регистра), за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="79f5e-490">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-490">Checksum</span></span>

<span data-ttu-id="79f5e-491">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-492">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-492">Definition</span></span>

<span data-ttu-id="79f5e-493">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-494">Регулярное выражение `Regex_slovakia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-495">Найдено ключевое `Keywords_slovakia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-496">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-496">Keywords</span></span>

<span data-ttu-id="79f5e-497">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-497"></span></span>
|<span data-ttu-id="79f5e-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-499">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-499">passport number</span></span>  <br/> <span data-ttu-id="79f5e-500">номер паспорта словакиан</span><span class="sxs-lookup"><span data-stu-id="79f5e-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="79f5e-501">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-501">passport no</span></span>  <br/> <span data-ttu-id="79f5e-502">číсло Пасу</span><span class="sxs-lookup"><span data-stu-id="79f5e-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="79f5e-503">Словения</span><span class="sxs-lookup"><span data-stu-id="79f5e-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-504">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-504">Format</span></span>

<span data-ttu-id="79f5e-505">Две буквы, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-506">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-506">Pattern</span></span>

<span data-ttu-id="79f5e-507">Две буквы, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="79f5e-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="79f5e-508">Буква "P"</span><span class="sxs-lookup"><span data-stu-id="79f5e-508">The letter "P"</span></span>
    
- <span data-ttu-id="79f5e-509">Одна прописная буква</span><span class="sxs-lookup"><span data-stu-id="79f5e-509">One uppercase letter</span></span>
    
- <span data-ttu-id="79f5e-510">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79f5e-511">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-511">Checksum</span></span>

<span data-ttu-id="79f5e-512">Нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-513">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-513">Definition</span></span>

<span data-ttu-id="79f5e-514">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-515">Регулярное выражение `Regex_slovenia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-516">Найдено ключевое `Keywords_slovenia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-517">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-517">Keywords</span></span>

<span data-ttu-id="79f5e-518">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-518"></span></span>
|<span data-ttu-id="79f5e-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-520">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-520">passport number</span></span>  <br/> <span data-ttu-id="79f5e-521">номер паспорта для словенского языка</span><span class="sxs-lookup"><span data-stu-id="79f5e-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="79f5e-522">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-522">passport no</span></span>  <br/> <span data-ttu-id="79f5e-523">Список потнега šтевилка</span><span class="sxs-lookup"><span data-stu-id="79f5e-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="79f5e-524">Испания</span><span class="sxs-lookup"><span data-stu-id="79f5e-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="79f5e-525">Format</span><span class="sxs-lookup"><span data-stu-id="79f5e-525">Format</span></span>

<span data-ttu-id="79f5e-526">Сочетание букв и цифр из восьми или девяти символов без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="79f5e-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="79f5e-527">Шаблон</span><span class="sxs-lookup"><span data-stu-id="79f5e-527">Pattern</span></span>

<span data-ttu-id="79f5e-528">Сочетание букв и цифр из восьми или девяти символов:</span><span class="sxs-lookup"><span data-stu-id="79f5e-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="79f5e-529">Две цифры или буквы</span><span class="sxs-lookup"><span data-stu-id="79f5e-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="79f5e-530">Одна цифра или буква (необязательно)</span><span class="sxs-lookup"><span data-stu-id="79f5e-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="79f5e-531">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="79f5e-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="79f5e-532">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="79f5e-532">Checksum</span></span>

<span data-ttu-id="79f5e-533">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="79f5e-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="79f5e-534">Определение</span><span class="sxs-lookup"><span data-stu-id="79f5e-534">Definition</span></span>

<span data-ttu-id="79f5e-535">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="79f5e-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="79f5e-536">Регулярное выражение `Regex_spain_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="79f5e-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="79f5e-537">Найдено ключевое `Keywords_spain_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="79f5e-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="79f5e-538">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="79f5e-538">Keywords</span></span>

<span data-ttu-id="79f5e-539">| |</span><span class="sxs-lookup"><span data-stu-id="79f5e-539"></span></span>
|<span data-ttu-id="79f5e-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="79f5e-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="79f5e-541">службу</span><span class="sxs-lookup"><span data-stu-id="79f5e-541">passport</span></span>  <br/> <span data-ttu-id="79f5e-542">Служба Passport, Испания</span><span class="sxs-lookup"><span data-stu-id="79f5e-542">spain passport</span></span>  <br/> <span data-ttu-id="79f5e-543">Книга Passport</span><span class="sxs-lookup"><span data-stu-id="79f5e-543">passport book</span></span>  <br/> <span data-ttu-id="79f5e-544">passport number</span><span class="sxs-lookup"><span data-stu-id="79f5e-544">passport number</span></span>  <br/> <span data-ttu-id="79f5e-545">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="79f5e-545">passport no</span></span>  <br/> <span data-ttu-id="79f5e-546">либрета пасапорте</span><span class="sxs-lookup"><span data-stu-id="79f5e-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="79f5e-547">нúмеро пасапорте</span><span class="sxs-lookup"><span data-stu-id="79f5e-547">número pasaporte</span></span>  <br/> <span data-ttu-id="79f5e-548">еспаñа пасапорте</span><span class="sxs-lookup"><span data-stu-id="79f5e-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="79f5e-549">пасапорте</span><span class="sxs-lookup"><span data-stu-id="79f5e-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="79f5e-550">Швеция</span><span class="sxs-lookup"><span data-stu-id="79f5e-550">Sweden</span></span>

<span data-ttu-id="79f5e-551">Дополнительные сведения можно найти в разделе "Швеции Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79f5e-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="79f5e-552">ВОЗМЕЩЕН</span><span class="sxs-lookup"><span data-stu-id="79f5e-552">UK</span></span>

<span data-ttu-id="79f5e-553">Дополнительные сведения см. в разделе "США/Великобритания</span><span class="sxs-lookup"><span data-stu-id="79f5e-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="79f5e-554">Номер паспорта [, который ищет типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="79f5e-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="79f5e-555">См. также</span><span class="sxs-lookup"><span data-stu-id="79f5e-555">See also</span></span>

[<span data-ttu-id="79f5e-556">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="79f5e-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

