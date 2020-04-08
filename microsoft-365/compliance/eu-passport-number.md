---
title: Номер паспорта ЕС
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС Passport Number. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: 0032d3e50d7dab0b696d9000242e70956469052e
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "41592120"
---
# <a name="eu-passport-number"></a><span data-ttu-id="41738-104">Номер паспорта ЕС</span><span class="sxs-lookup"><span data-stu-id="41738-104">EU Passport Number</span></span>

<span data-ttu-id="41738-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС Passport Number.</span><span class="sxs-lookup"><span data-stu-id="41738-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="41738-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="41738-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="41738-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="41738-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="41738-108">Format</span><span class="sxs-lookup"><span data-stu-id="41738-108">Format</span></span>

<span data-ttu-id="41738-109">Одна буква, за которой следует необязательный пробел и семь цифр</span><span class="sxs-lookup"><span data-stu-id="41738-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-110">Pattern</span></span>

<span data-ttu-id="41738-111">Сочетание одной буквы, семи цифр и одного пробела:</span><span class="sxs-lookup"><span data-stu-id="41738-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="41738-112">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="41738-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="41738-113">Один пробел (необязательно)</span><span class="sxs-lookup"><span data-stu-id="41738-113">One space (optional)</span></span>
    
- <span data-ttu-id="41738-114">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="41738-115">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-115">Checksum</span></span>

<span data-ttu-id="41738-116">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="41738-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-117">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-117">Definition</span></span>

<span data-ttu-id="41738-118">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-119">Регулярное выражение `Regex_austria_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-120">Найдено ключевое `Keywords_austria_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-121">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-121">Keywords</span></span>

<span data-ttu-id="41738-122">| |</span><span class="sxs-lookup"><span data-stu-id="41738-122">| |</span></span>
|<span data-ttu-id="41738-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-124">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-124">passport number</span></span>  <br/> <span data-ttu-id="41738-125">Австрийский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="41738-125">austrian passport number</span></span>  <br/> <span data-ttu-id="41738-126">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-126">passport no</span></span>  <br/> <span data-ttu-id="41738-127">реисепасс</span><span class="sxs-lookup"><span data-stu-id="41738-127">reisepass</span></span>  <br/> <span data-ttu-id="41738-128">öстерреичисч реисепасс</span><span class="sxs-lookup"><span data-stu-id="41738-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="41738-129">Бельгия</span><span class="sxs-lookup"><span data-stu-id="41738-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="41738-130">Format</span><span class="sxs-lookup"><span data-stu-id="41738-130">Format</span></span>

<span data-ttu-id="41738-131">Две буквы, за которыми следуют шесть цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-132">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-132">Pattern</span></span>

<span data-ttu-id="41738-133">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="41738-134">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-134">Checksum</span></span>

<span data-ttu-id="41738-135">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="41738-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-136">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-136">Definition</span></span>

<span data-ttu-id="41738-137">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-138">Регулярное выражение `Regex_belgium_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-139">Найдено ключевое `Keywords_belgium_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-140">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-140">Keywords</span></span>

<span data-ttu-id="41738-141">| |</span><span class="sxs-lookup"><span data-stu-id="41738-141">| |</span></span>
|<span data-ttu-id="41738-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-143">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-143">passport number</span></span>  <br/> <span data-ttu-id="41738-144">Бельгийский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="41738-144">belgian passport number</span></span>  <br/> <span data-ttu-id="41738-145">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-145">passport no</span></span>  <br/> <span data-ttu-id="41738-146">паспурт</span><span class="sxs-lookup"><span data-stu-id="41738-146">paspoort</span></span>  <br/> <span data-ttu-id="41738-147">паспуртнуммер</span><span class="sxs-lookup"><span data-stu-id="41738-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="41738-148">реисепасс Кеин</span><span class="sxs-lookup"><span data-stu-id="41738-148">reisepass kein</span></span>  <br/> <span data-ttu-id="41738-149">реисепасс</span><span class="sxs-lookup"><span data-stu-id="41738-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="41738-150">Болгария</span><span class="sxs-lookup"><span data-stu-id="41738-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="41738-151">Format</span><span class="sxs-lookup"><span data-stu-id="41738-151">Format</span></span>

<span data-ttu-id="41738-152">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-153">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-153">Pattern</span></span>

 <span data-ttu-id="41738-154">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="41738-155">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-155">Checksum</span></span>

<span data-ttu-id="41738-156">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-157">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-157">Definition</span></span>

<span data-ttu-id="41738-158">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-159">Регулярное выражение `Regex_bulgaria_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-160">Найдено ключевое `Keywords_bulgaria_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-161">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-161">Keywords</span></span>

<span data-ttu-id="41738-162">| |</span><span class="sxs-lookup"><span data-stu-id="41738-162">| |</span></span>
|<span data-ttu-id="41738-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-164">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-164">passport number</span></span>  <br/> <span data-ttu-id="41738-165">номер паспорта для болгарского языка</span><span class="sxs-lookup"><span data-stu-id="41738-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="41738-166">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-166">passport no</span></span>  <br/> <span data-ttu-id="41738-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="41738-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="41738-168">Хорватия</span><span class="sxs-lookup"><span data-stu-id="41738-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="41738-169">Format</span><span class="sxs-lookup"><span data-stu-id="41738-169">Format</span></span>

<span data-ttu-id="41738-170">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-171">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-171">Pattern</span></span>

 <span data-ttu-id="41738-172">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="41738-173">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-173">Checksum</span></span>

<span data-ttu-id="41738-174">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-175">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-175">Definition</span></span>

<span data-ttu-id="41738-176">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-177">Регулярное выражение `Regex_croatia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-178">Найдено ключевое `Keywords_croatia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-179">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-179">Keywords</span></span>

<span data-ttu-id="41738-180">| |</span><span class="sxs-lookup"><span data-stu-id="41738-180">| |</span></span>
|<span data-ttu-id="41738-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-182">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-182">passport number</span></span>  <br/> <span data-ttu-id="41738-183">номер паспорта для хорватского языка</span><span class="sxs-lookup"><span data-stu-id="41738-183">croatian passport number</span></span>  <br/> <span data-ttu-id="41738-184">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-184">passport no</span></span>  <br/> <span data-ttu-id="41738-185">Брож путовнице</span><span class="sxs-lookup"><span data-stu-id="41738-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="41738-186">Кипр</span><span class="sxs-lookup"><span data-stu-id="41738-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="41738-187">Format</span><span class="sxs-lookup"><span data-stu-id="41738-187">Format</span></span>

<span data-ttu-id="41738-188">Одна буква, за которой следуют 6-8 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-189">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-189">Pattern</span></span>

<span data-ttu-id="41738-190">Одна буква, за которой следуют шесть и восемь цифр</span><span class="sxs-lookup"><span data-stu-id="41738-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="41738-191">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-191">Checksum</span></span>

<span data-ttu-id="41738-192">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-193">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-193">Definition</span></span>

<span data-ttu-id="41738-194">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-195">Регулярное выражение `Regex_cyprus_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-196">Найдено ключевое `Keywords_cyprus_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-197">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-197">Keywords</span></span>

<span data-ttu-id="41738-198">| |</span><span class="sxs-lookup"><span data-stu-id="41738-198">| |</span></span>
|<span data-ttu-id="41738-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-200">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-200">passport number</span></span>  <br/> <span data-ttu-id="41738-201">номер паспорта для Кипр</span><span class="sxs-lookup"><span data-stu-id="41738-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="41738-202">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-202">passport no</span></span>  <br/> <span data-ttu-id="41738-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="41738-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="41738-204">Чехия</span><span class="sxs-lookup"><span data-stu-id="41738-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="41738-205">Format</span><span class="sxs-lookup"><span data-stu-id="41738-205">Format</span></span>

<span data-ttu-id="41738-206">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-207">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-207">Pattern</span></span>

<span data-ttu-id="41738-208">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="41738-209">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-209">Checksum</span></span>

<span data-ttu-id="41738-210">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-211">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-211">Definition</span></span>

<span data-ttu-id="41738-212">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-213">Регулярное выражение `Regex_czech_republic_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-214">Найдено ключевое `Keywords_czech_republic_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-215">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-215">Keywords</span></span>

<span data-ttu-id="41738-216">| |</span><span class="sxs-lookup"><span data-stu-id="41738-216">| |</span></span>
|<span data-ttu-id="41738-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-218">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-218">passport number</span></span>  <br/> <span data-ttu-id="41738-219">номер паспорта для чешского языка</span><span class="sxs-lookup"><span data-stu-id="41738-219">czech passport number</span></span>  <br/> <span data-ttu-id="41738-220">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-220">passport no</span></span>  <br/> <span data-ttu-id="41738-221">цестовнí PAS</span><span class="sxs-lookup"><span data-stu-id="41738-221">cestovní pas</span></span>  <br/> <span data-ttu-id="41738-222">соответствующий</span><span class="sxs-lookup"><span data-stu-id="41738-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="41738-223">Дания</span><span class="sxs-lookup"><span data-stu-id="41738-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="41738-224">Format</span><span class="sxs-lookup"><span data-stu-id="41738-224">Format</span></span>

<span data-ttu-id="41738-225">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-226">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-226">Pattern</span></span>

 <span data-ttu-id="41738-227">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="41738-228">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-228">Checksum</span></span>

<span data-ttu-id="41738-229">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-230">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-230">Definition</span></span>

<span data-ttu-id="41738-231">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-232">Регулярное выражение `Regex_denmark_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-233">Найдено ключевое `Keywords_denmark_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-234">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-234">Keywords</span></span>

<span data-ttu-id="41738-235">| |</span><span class="sxs-lookup"><span data-stu-id="41738-235">| |</span></span>
|<span data-ttu-id="41738-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-237">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-237">passport number</span></span>  <br/> <span data-ttu-id="41738-238">номер паспорта для датского языка</span><span class="sxs-lookup"><span data-stu-id="41738-238">danish passport number</span></span>  <br/> <span data-ttu-id="41738-239">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-239">passport no</span></span>  <br/> <span data-ttu-id="41738-240">соответствующий</span><span class="sxs-lookup"><span data-stu-id="41738-240">pas</span></span>  <br/> <span data-ttu-id="41738-241">паснуммер</span><span class="sxs-lookup"><span data-stu-id="41738-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="41738-242">Эстония</span><span class="sxs-lookup"><span data-stu-id="41738-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="41738-243">Format</span><span class="sxs-lookup"><span data-stu-id="41738-243">Format</span></span>

<span data-ttu-id="41738-244">Одна буква, за которой следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-245">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-245">Pattern</span></span>

<span data-ttu-id="41738-246">Одна буква, за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="41738-247">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-247">Checksum</span></span>

<span data-ttu-id="41738-248">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-249">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-249">Definition</span></span>

<span data-ttu-id="41738-250">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-251">Регулярное выражение `Regex_estonia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-252">Найдено ключевое `Keywords_estonia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-253">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-253">Keywords</span></span>

<span data-ttu-id="41738-254">| |</span><span class="sxs-lookup"><span data-stu-id="41738-254">| |</span></span>
|<span data-ttu-id="41738-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-256">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-256">passport number</span></span>  <br/> <span data-ttu-id="41738-257">номер паспорта для Эстонии</span><span class="sxs-lookup"><span data-stu-id="41738-257">estonian passport number</span></span>  <br/> <span data-ttu-id="41738-258">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-258">passport no</span></span>  <br/> <span data-ttu-id="41738-259">Исти коданику Pass</span><span class="sxs-lookup"><span data-stu-id="41738-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="41738-260">Финляндия</span><span class="sxs-lookup"><span data-stu-id="41738-260">Finland</span></span>

<span data-ttu-id="41738-261">Дополнительные сведения можно найти в разделе "Финляндия Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="41738-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="41738-262">Франция</span><span class="sxs-lookup"><span data-stu-id="41738-262">France</span></span>

<span data-ttu-id="41738-263">Дополнительные сведения можно найти в разделе "Франция Passport Number", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="41738-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="41738-264">Германия</span><span class="sxs-lookup"><span data-stu-id="41738-264">Germany</span></span>

<span data-ttu-id="41738-265">Дополнительные сведения можно найти в разделе "немецкий паспорт номер", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="41738-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="41738-266">Греция</span><span class="sxs-lookup"><span data-stu-id="41738-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="41738-267">Format</span><span class="sxs-lookup"><span data-stu-id="41738-267">Format</span></span>

<span data-ttu-id="41738-268">Две буквы, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-269">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-269">Pattern</span></span>

<span data-ttu-id="41738-270">Две буквы, за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="41738-271">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-271">Checksum</span></span>

<span data-ttu-id="41738-272">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-273">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-273">Definition</span></span>

<span data-ttu-id="41738-274">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-275">Регулярное выражение `Regex_greece_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-276">Найдено ключевое `Keywords_greece_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-277">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-277">Keywords</span></span>

<span data-ttu-id="41738-278">| |</span><span class="sxs-lookup"><span data-stu-id="41738-278">| |</span></span>
|<span data-ttu-id="41738-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-280">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-280">passport number</span></span>  <br/> <span data-ttu-id="41738-281">номер паспорта греческого алфавита</span><span class="sxs-lookup"><span data-stu-id="41738-281">greek passport number</span></span>  <br/> <span data-ttu-id="41738-282">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-282">passport no</span></span>  <br/> <span data-ttu-id="41738-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="41738-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="41738-284">Венгрия</span><span class="sxs-lookup"><span data-stu-id="41738-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="41738-285">Format</span><span class="sxs-lookup"><span data-stu-id="41738-285">Format</span></span>

<span data-ttu-id="41738-286">Две буквы, за которыми следуют шесть или семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-287">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-287">Pattern</span></span>

<span data-ttu-id="41738-288">Две буквы, за которыми следуют шесть или семь цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="41738-289">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-289">Checksum</span></span>

<span data-ttu-id="41738-290">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-291">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-291">Definition</span></span>

<span data-ttu-id="41738-292">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-293">Регулярное выражение `Regex_hungary_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-294">Найдено ключевое `Keywords_hungary_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-295">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-295">Keywords</span></span>

<span data-ttu-id="41738-296">| |</span><span class="sxs-lookup"><span data-stu-id="41738-296">| |</span></span>
|<span data-ttu-id="41738-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-298">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-298">passport number</span></span>  <br/> <span data-ttu-id="41738-299">Венгерский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="41738-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="41738-300">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-300">passport no</span></span>  <br/> <span data-ttu-id="41738-301">úтлевéл сзáма</span><span class="sxs-lookup"><span data-stu-id="41738-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="41738-302">Ирландия</span><span class="sxs-lookup"><span data-stu-id="41738-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="41738-303">Format</span><span class="sxs-lookup"><span data-stu-id="41738-303">Format</span></span>

<span data-ttu-id="41738-304">Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-305">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-305">Pattern</span></span>

<span data-ttu-id="41738-306">Две буквы или цифры, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="41738-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="41738-307">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="41738-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="41738-308">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="41738-309">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-309">Checksum</span></span>

<span data-ttu-id="41738-310">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-311">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-311">Definition</span></span>

<span data-ttu-id="41738-312">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-313">Регулярное выражение `Regex_ireland_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-314">Найдено ключевое `Keywords_ireland_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-315">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-315">Keywords</span></span>

<span data-ttu-id="41738-316">| |</span><span class="sxs-lookup"><span data-stu-id="41738-316">| |</span></span>
|<span data-ttu-id="41738-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-318">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-318">passport number</span></span>  <br/> <span data-ttu-id="41738-319">Ирландский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="41738-319">irish passport number</span></span>  <br/> <span data-ttu-id="41738-320">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-320">passport no</span></span>  <br/> <span data-ttu-id="41738-321">соответствующий</span><span class="sxs-lookup"><span data-stu-id="41738-321">pas</span></span>  <br/> <span data-ttu-id="41738-322">службу</span><span class="sxs-lookup"><span data-stu-id="41738-322">passport</span></span>  <br/> <span data-ttu-id="41738-323">пассепорт</span><span class="sxs-lookup"><span data-stu-id="41738-323">passeport</span></span>  <br/> <span data-ttu-id="41738-324">пассепорт нумеро</span><span class="sxs-lookup"><span data-stu-id="41738-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="41738-325">Италия</span><span class="sxs-lookup"><span data-stu-id="41738-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="41738-326">Format</span><span class="sxs-lookup"><span data-stu-id="41738-326">Format</span></span>

<span data-ttu-id="41738-327">Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-328">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-328">Pattern</span></span>

<span data-ttu-id="41738-329">Две буквы или цифры, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="41738-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="41738-330">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="41738-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="41738-331">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="41738-332">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-332">Checksum</span></span>

<span data-ttu-id="41738-333">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="41738-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-334">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-334">Definition</span></span>

<span data-ttu-id="41738-335">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-336">Регулярное выражение `Regex_italy_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-337">Найдено ключевое `Keywords_italy_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-338">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-338">Keywords</span></span>

<span data-ttu-id="41738-339">| |</span><span class="sxs-lookup"><span data-stu-id="41738-339">| |</span></span>
|<span data-ttu-id="41738-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-341">номер паспорта для итальянского языка</span><span class="sxs-lookup"><span data-stu-id="41738-341">italian passport number</span></span>  <br/> <span data-ttu-id="41738-342">Репубблика итальянский пассапорто</span><span class="sxs-lookup"><span data-stu-id="41738-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="41738-343">пассапорто</span><span class="sxs-lookup"><span data-stu-id="41738-343">passaporto</span></span>  <br/> <span data-ttu-id="41738-344">пассапорто итальянский</span><span class="sxs-lookup"><span data-stu-id="41738-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="41738-345">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-345">passport number</span></span>  <br/> <span data-ttu-id="41738-346">Итальянский пассапорто нумеро</span><span class="sxs-lookup"><span data-stu-id="41738-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="41738-347">пассапорто нумеро</span><span class="sxs-lookup"><span data-stu-id="41738-347">passaporto numero</span></span>  <br/> <span data-ttu-id="41738-348">нумéро пассепорт италиен</span><span class="sxs-lookup"><span data-stu-id="41738-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="41738-349">нумéро пассепорт</span><span class="sxs-lookup"><span data-stu-id="41738-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="41738-350">Латвия</span><span class="sxs-lookup"><span data-stu-id="41738-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="41738-351">Format</span><span class="sxs-lookup"><span data-stu-id="41738-351">Format</span></span>

<span data-ttu-id="41738-352">Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-353">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-353">Pattern</span></span>

<span data-ttu-id="41738-354">Две буквы или цифры, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="41738-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="41738-355">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="41738-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="41738-356">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="41738-357">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-357">Checksum</span></span>

<span data-ttu-id="41738-358">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-359">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-359">Definition</span></span>

<span data-ttu-id="41738-360">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-361">Регулярное выражение `Regex_latvia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-362">Найдено ключевое `Keywords_latvia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-363">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-363">Keywords</span></span>

<span data-ttu-id="41738-364">| |</span><span class="sxs-lookup"><span data-stu-id="41738-364">| |</span></span>
|<span data-ttu-id="41738-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-366">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-366">passport number</span></span>  <br/> <span data-ttu-id="41738-367">номер паспорта для Латвии</span><span class="sxs-lookup"><span data-stu-id="41738-367">latvian passport number</span></span>  <br/> <span data-ttu-id="41738-368">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-368">passport no</span></span>  <br/> <span data-ttu-id="41738-369">ПАСЕ нумурс</span><span class="sxs-lookup"><span data-stu-id="41738-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="41738-370">Литва</span><span class="sxs-lookup"><span data-stu-id="41738-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="41738-371">Format</span><span class="sxs-lookup"><span data-stu-id="41738-371">Format</span></span>

<span data-ttu-id="41738-372">Восемь цифр или букв без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-373">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-373">Pattern</span></span>

<span data-ttu-id="41738-374">Восемь цифр или букв (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="41738-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="41738-375">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-375">Checksum</span></span>

<span data-ttu-id="41738-376">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="41738-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-377">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-377">Definition</span></span>

<span data-ttu-id="41738-378">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-379">Регулярное выражение `Regex_lithuania_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-380">Найдено ключевое `Keywords_lithuania_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-381">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-381">Keywords</span></span>

<span data-ttu-id="41738-382">| |</span><span class="sxs-lookup"><span data-stu-id="41738-382">| |</span></span>
|<span data-ttu-id="41738-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-384">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-384">passport number</span></span>  <br/> <span data-ttu-id="41738-385">номер паспорта лисуниан</span><span class="sxs-lookup"><span data-stu-id="41738-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="41738-386">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-386">passport no</span></span>  <br/> <span data-ttu-id="41738-387">Пасо нумерис</span><span class="sxs-lookup"><span data-stu-id="41738-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="41738-388">луксембург</span><span class="sxs-lookup"><span data-stu-id="41738-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="41738-389">Format</span><span class="sxs-lookup"><span data-stu-id="41738-389">Format</span></span>

<span data-ttu-id="41738-390">Восемь цифр или букв без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-391">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-391">Pattern</span></span>

<span data-ttu-id="41738-392">Восемь цифр или букв (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="41738-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="41738-393">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-393">Checksum</span></span>

<span data-ttu-id="41738-394">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-395">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-395">Definition</span></span>

<span data-ttu-id="41738-396">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-397">Регулярное выражение `Regex_nation_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-398">Найдено ключевое `Keywords_nation_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-399">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-399">Keywords</span></span>

<span data-ttu-id="41738-400">| |</span><span class="sxs-lookup"><span data-stu-id="41738-400">| |</span></span>
|<span data-ttu-id="41738-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-402">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-402">passport number</span></span>  <br/> <span data-ttu-id="41738-403">номер паспорта для Латвии</span><span class="sxs-lookup"><span data-stu-id="41738-403">latvian passport number</span></span>  <br/> <span data-ttu-id="41738-404">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-404">passport no</span></span>  <br/> <span data-ttu-id="41738-405">пасснуммер</span><span class="sxs-lookup"><span data-stu-id="41738-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="41738-406">Мальта</span><span class="sxs-lookup"><span data-stu-id="41738-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="41738-407">Format</span><span class="sxs-lookup"><span data-stu-id="41738-407">Format</span></span>

<span data-ttu-id="41738-408">Семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-409">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-409">Pattern</span></span>

 <span data-ttu-id="41738-410">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="41738-411">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-411">Checksum</span></span>

<span data-ttu-id="41738-412">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-413">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-413">Definition</span></span>

<span data-ttu-id="41738-414">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-415">Регулярное выражение `Regex_malta_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-416">Найдено ключевое `Keywords_malta_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-417">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-417">Keywords</span></span>

<span data-ttu-id="41738-418">| |</span><span class="sxs-lookup"><span data-stu-id="41738-418">| |</span></span>
|<span data-ttu-id="41738-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-420">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-420">passport number</span></span>  <br/> <span data-ttu-id="41738-421">номер паспорта Мальтийский</span><span class="sxs-lookup"><span data-stu-id="41738-421">maltese passport number</span></span>  <br/> <span data-ttu-id="41738-422">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-422">passport no</span></span>  <br/> <span data-ttu-id="41738-423">нумру Тал — пассапорт</span><span class="sxs-lookup"><span data-stu-id="41738-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="41738-424">Нидерланды</span><span class="sxs-lookup"><span data-stu-id="41738-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="41738-425">Format</span><span class="sxs-lookup"><span data-stu-id="41738-425">Format</span></span>

<span data-ttu-id="41738-426">Девять букв или цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-427">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-427">Pattern</span></span>

<span data-ttu-id="41738-428">Девять букв или цифр;</span><span class="sxs-lookup"><span data-stu-id="41738-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="41738-429">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-429">Checksum</span></span>

<span data-ttu-id="41738-430">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="41738-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-431">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-431">Definition</span></span>

<span data-ttu-id="41738-432">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-433">Регулярное выражение `Regex_netherlands_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-434">Найдено ключевое `Keywords_netherlands_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-435">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-435">Keywords</span></span>

<span data-ttu-id="41738-436">| |</span><span class="sxs-lookup"><span data-stu-id="41738-436">| |</span></span>
|<span data-ttu-id="41738-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-438">номер паспорта для нидерландского языка</span><span class="sxs-lookup"><span data-stu-id="41738-438">dutch passport number</span></span>  <br/> <span data-ttu-id="41738-439">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-439">passport number</span></span>  <br/> <span data-ttu-id="41738-440">номер паспорта Нидерландов</span><span class="sxs-lookup"><span data-stu-id="41738-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="41738-441">недерланден паспурт нуммер</span><span class="sxs-lookup"><span data-stu-id="41738-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="41738-442">паспурт</span><span class="sxs-lookup"><span data-stu-id="41738-442">paspoort</span></span>  <br/> <span data-ttu-id="41738-443">недерланден паспуртнуммер</span><span class="sxs-lookup"><span data-stu-id="41738-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="41738-444">паспуртнуммер</span><span class="sxs-lookup"><span data-stu-id="41738-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="41738-445">Польша</span><span class="sxs-lookup"><span data-stu-id="41738-445">Poland</span></span>

<span data-ttu-id="41738-446">Дополнительные сведения можно найти в разделе "Польша Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="41738-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="41738-447">Португалия</span><span class="sxs-lookup"><span data-stu-id="41738-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="41738-448">Format</span><span class="sxs-lookup"><span data-stu-id="41738-448">Format</span></span>

<span data-ttu-id="41738-449">Одна буква, за которой следуют шесть цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-450">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-450">Pattern</span></span>

<span data-ttu-id="41738-451">Одна буква, за которой следуют шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="41738-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="41738-452">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="41738-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="41738-453">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="41738-454">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-454">Checksum</span></span>

<span data-ttu-id="41738-455">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-456">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-456">Definition</span></span>

<span data-ttu-id="41738-457">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-458">Регулярное выражение `Regex_portugal_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-459">Найдено ключевое `Keywords_portugal_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-460">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-460">Keywords</span></span>

<span data-ttu-id="41738-461">| |</span><span class="sxs-lookup"><span data-stu-id="41738-461">| |</span></span>
|<span data-ttu-id="41738-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-463">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-463">passport number</span></span>  <br/> <span data-ttu-id="41738-464">номер паспорта для португальского языка</span><span class="sxs-lookup"><span data-stu-id="41738-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="41738-465">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-465">passport no</span></span>  <br/> <span data-ttu-id="41738-466">нúмеро Do пассапорте</span><span class="sxs-lookup"><span data-stu-id="41738-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="41738-467">Румыния</span><span class="sxs-lookup"><span data-stu-id="41738-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="41738-468">Format</span><span class="sxs-lookup"><span data-stu-id="41738-468">Format</span></span>

<span data-ttu-id="41738-469">Восемь или девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-470">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-470">Pattern</span></span>

<span data-ttu-id="41738-471">Восемь или девять цифр</span><span class="sxs-lookup"><span data-stu-id="41738-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="41738-472">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-472">Checksum</span></span>

<span data-ttu-id="41738-473">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-474">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-474">Definition</span></span>

<span data-ttu-id="41738-475">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-476">Регулярное выражение `Regex_romania_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-477">Найдено ключевое `Keywords_romania_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-478">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-478">Keywords</span></span>

<span data-ttu-id="41738-479">| |</span><span class="sxs-lookup"><span data-stu-id="41738-479">| |</span></span>
|<span data-ttu-id="41738-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-481">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-481">passport number</span></span>  <br/> <span data-ttu-id="41738-482">номер паспорта для румынского языка</span><span class="sxs-lookup"><span data-stu-id="41738-482">romanian passport number</span></span>  <br/> <span data-ttu-id="41738-483">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-483">passport no</span></span>  <br/> <span data-ttu-id="41738-484">нумăрул паșапортулуи</span><span class="sxs-lookup"><span data-stu-id="41738-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="41738-485">Словакия</span><span class="sxs-lookup"><span data-stu-id="41738-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="41738-486">Format</span><span class="sxs-lookup"><span data-stu-id="41738-486">Format</span></span>

<span data-ttu-id="41738-487">Одна цифра или буква, за которой следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-488">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-488">Pattern</span></span>

<span data-ttu-id="41738-489">Одна цифра или буква (без учета регистра), за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="41738-490">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-490">Checksum</span></span>

<span data-ttu-id="41738-491">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-492">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-492">Definition</span></span>

<span data-ttu-id="41738-493">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-494">Регулярное выражение `Regex_slovakia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-495">Найдено ключевое `Keywords_slovakia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-496">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-496">Keywords</span></span>

<span data-ttu-id="41738-497">| |</span><span class="sxs-lookup"><span data-stu-id="41738-497">| |</span></span>
|<span data-ttu-id="41738-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-499">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-499">passport number</span></span>  <br/> <span data-ttu-id="41738-500">номер паспорта словакиан</span><span class="sxs-lookup"><span data-stu-id="41738-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="41738-501">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-501">passport no</span></span>  <br/> <span data-ttu-id="41738-502">číсло Пасу</span><span class="sxs-lookup"><span data-stu-id="41738-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="41738-503">Словения</span><span class="sxs-lookup"><span data-stu-id="41738-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="41738-504">Format</span><span class="sxs-lookup"><span data-stu-id="41738-504">Format</span></span>

<span data-ttu-id="41738-505">Две буквы, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-506">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-506">Pattern</span></span>

<span data-ttu-id="41738-507">Две буквы, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="41738-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="41738-508">Буква "P"</span><span class="sxs-lookup"><span data-stu-id="41738-508">The letter "P"</span></span>
    
- <span data-ttu-id="41738-509">Одна прописная буква</span><span class="sxs-lookup"><span data-stu-id="41738-509">One uppercase letter</span></span>
    
- <span data-ttu-id="41738-510">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="41738-511">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-511">Checksum</span></span>

<span data-ttu-id="41738-512">Нет</span><span class="sxs-lookup"><span data-stu-id="41738-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-513">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-513">Definition</span></span>

<span data-ttu-id="41738-514">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-515">Регулярное выражение `Regex_slovenia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-516">Найдено ключевое `Keywords_slovenia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-517">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-517">Keywords</span></span>

<span data-ttu-id="41738-518">| |</span><span class="sxs-lookup"><span data-stu-id="41738-518">| |</span></span>
|<span data-ttu-id="41738-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-520">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-520">passport number</span></span>  <br/> <span data-ttu-id="41738-521">номер паспорта для словенского языка</span><span class="sxs-lookup"><span data-stu-id="41738-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="41738-522">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-522">passport no</span></span>  <br/> <span data-ttu-id="41738-523">Список потнега šтевилка</span><span class="sxs-lookup"><span data-stu-id="41738-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="41738-524">Испания</span><span class="sxs-lookup"><span data-stu-id="41738-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="41738-525">Format</span><span class="sxs-lookup"><span data-stu-id="41738-525">Format</span></span>

<span data-ttu-id="41738-526">Сочетание букв и цифр из восьми или девяти символов без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="41738-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="41738-527">Шаблон</span><span class="sxs-lookup"><span data-stu-id="41738-527">Pattern</span></span>

<span data-ttu-id="41738-528">Сочетание букв и цифр из восьми или девяти символов:</span><span class="sxs-lookup"><span data-stu-id="41738-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="41738-529">Две цифры или буквы</span><span class="sxs-lookup"><span data-stu-id="41738-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="41738-530">Одна цифра или буква (необязательно)</span><span class="sxs-lookup"><span data-stu-id="41738-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="41738-531">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="41738-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="41738-532">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="41738-532">Checksum</span></span>

<span data-ttu-id="41738-533">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="41738-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="41738-534">Определение</span><span class="sxs-lookup"><span data-stu-id="41738-534">Definition</span></span>

<span data-ttu-id="41738-535">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="41738-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="41738-536">Регулярное выражение `Regex_spain_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="41738-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="41738-537">Найдено ключевое `Keywords_spain_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="41738-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="41738-538">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="41738-538">Keywords</span></span>

<span data-ttu-id="41738-539">| |</span><span class="sxs-lookup"><span data-stu-id="41738-539">| |</span></span>
|<span data-ttu-id="41738-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="41738-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="41738-541">службу</span><span class="sxs-lookup"><span data-stu-id="41738-541">passport</span></span>  <br/> <span data-ttu-id="41738-542">Служба Passport, Испания</span><span class="sxs-lookup"><span data-stu-id="41738-542">spain passport</span></span>  <br/> <span data-ttu-id="41738-543">Книга Passport</span><span class="sxs-lookup"><span data-stu-id="41738-543">passport book</span></span>  <br/> <span data-ttu-id="41738-544">passport number</span><span class="sxs-lookup"><span data-stu-id="41738-544">passport number</span></span>  <br/> <span data-ttu-id="41738-545">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="41738-545">passport no</span></span>  <br/> <span data-ttu-id="41738-546">либрета пасапорте</span><span class="sxs-lookup"><span data-stu-id="41738-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="41738-547">нúмеро пасапорте</span><span class="sxs-lookup"><span data-stu-id="41738-547">número pasaporte</span></span>  <br/> <span data-ttu-id="41738-548">еспаñа пасапорте</span><span class="sxs-lookup"><span data-stu-id="41738-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="41738-549">пасапорте</span><span class="sxs-lookup"><span data-stu-id="41738-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="41738-550">Швеция</span><span class="sxs-lookup"><span data-stu-id="41738-550">Sweden</span></span>

<span data-ttu-id="41738-551">Дополнительные сведения можно найти в разделе "Швеции Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="41738-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="41738-552">ВОЗМЕЩЕН</span><span class="sxs-lookup"><span data-stu-id="41738-552">UK</span></span>

<span data-ttu-id="41738-553">Дополнительные сведения см. в разделе "США/Великобритания</span><span class="sxs-lookup"><span data-stu-id="41738-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="41738-554">Номер паспорта [, который ищет типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="41738-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="41738-555">См. также</span><span class="sxs-lookup"><span data-stu-id="41738-555">See also</span></span>

[<span data-ttu-id="41738-556">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="41738-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

