---
title: Номер паспорта ЕС
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
ms.openlocfilehash: 4afcf7b764eb8976e0588464515256f7cb1bdb8d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805952"
---
# <a name="eu-passport-number"></a><span data-ttu-id="35f89-104">Номер паспорта ЕС</span><span class="sxs-lookup"><span data-stu-id="35f89-104">EU Passport Number</span></span>

<span data-ttu-id="35f89-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС Passport Number.</span><span class="sxs-lookup"><span data-stu-id="35f89-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="35f89-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="35f89-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="35f89-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="35f89-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="35f89-108">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-108">Format</span></span>

<span data-ttu-id="35f89-109">Одна буква, за которой следует необязательный пробел и семь цифр</span><span class="sxs-lookup"><span data-stu-id="35f89-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-110">Pattern</span></span>

<span data-ttu-id="35f89-111">Сочетание одной буквы, семи цифр и одного пробела:</span><span class="sxs-lookup"><span data-stu-id="35f89-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="35f89-112">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="35f89-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="35f89-113">Один пробел (необязательно)</span><span class="sxs-lookup"><span data-stu-id="35f89-113">One space (optional)</span></span>
    
- <span data-ttu-id="35f89-114">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="35f89-115">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-115">Checksum</span></span>

<span data-ttu-id="35f89-116">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="35f89-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-117">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-117">Definition</span></span>

<span data-ttu-id="35f89-118">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-119">Регулярное выражение `Regex_austria_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-120">Найдено ключевое `Keywords_austria_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-121">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-121">Keywords</span></span>

<span data-ttu-id="35f89-122">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-122"></span></span>
|<span data-ttu-id="35f89-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-124">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-124">passport number</span></span>  <br/> <span data-ttu-id="35f89-125">Австрийский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="35f89-125">austrian passport number</span></span>  <br/> <span data-ttu-id="35f89-126">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-126">passport no</span></span>  <br/> <span data-ttu-id="35f89-127">реисепасс</span><span class="sxs-lookup"><span data-stu-id="35f89-127">reisepass</span></span>  <br/> <span data-ttu-id="35f89-128">öстерреичисч реисепасс</span><span class="sxs-lookup"><span data-stu-id="35f89-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="35f89-129">Бельгия</span><span class="sxs-lookup"><span data-stu-id="35f89-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="35f89-130">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-130">Format</span></span>

<span data-ttu-id="35f89-131">Две буквы, за которыми следуют шесть цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-132">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-132">Pattern</span></span>

<span data-ttu-id="35f89-133">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="35f89-134">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-134">Checksum</span></span>

<span data-ttu-id="35f89-135">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="35f89-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-136">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-136">Definition</span></span>

<span data-ttu-id="35f89-137">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-138">Регулярное выражение `Regex_belgium_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-139">Найдено ключевое `Keywords_belgium_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-140">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-140">Keywords</span></span>

<span data-ttu-id="35f89-141">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-141"></span></span>
|<span data-ttu-id="35f89-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-143">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-143">passport number</span></span>  <br/> <span data-ttu-id="35f89-144">Бельгийский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="35f89-144">belgian passport number</span></span>  <br/> <span data-ttu-id="35f89-145">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-145">passport no</span></span>  <br/> <span data-ttu-id="35f89-146">паспурт</span><span class="sxs-lookup"><span data-stu-id="35f89-146">paspoort</span></span>  <br/> <span data-ttu-id="35f89-147">паспуртнуммер</span><span class="sxs-lookup"><span data-stu-id="35f89-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="35f89-148">реисепасс Кеин</span><span class="sxs-lookup"><span data-stu-id="35f89-148">reisepass kein</span></span>  <br/> <span data-ttu-id="35f89-149">реисепасс</span><span class="sxs-lookup"><span data-stu-id="35f89-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="35f89-150">Болгария</span><span class="sxs-lookup"><span data-stu-id="35f89-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="35f89-151">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-151">Format</span></span>

<span data-ttu-id="35f89-152">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-153">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-153">Pattern</span></span>

 <span data-ttu-id="35f89-154">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="35f89-155">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-155">Checksum</span></span>

<span data-ttu-id="35f89-156">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-157">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-157">Definition</span></span>

<span data-ttu-id="35f89-158">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-159">Регулярное выражение `Regex_bulgaria_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-160">Найдено ключевое `Keywords_bulgaria_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-161">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-161">Keywords</span></span>

<span data-ttu-id="35f89-162">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-162"></span></span>
|<span data-ttu-id="35f89-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-164">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-164">passport number</span></span>  <br/> <span data-ttu-id="35f89-165">номер паспорта для болгарского языка</span><span class="sxs-lookup"><span data-stu-id="35f89-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="35f89-166">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-166">passport no</span></span>  <br/> <span data-ttu-id="35f89-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="35f89-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="35f89-168">Хорватия</span><span class="sxs-lookup"><span data-stu-id="35f89-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="35f89-169">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-169">Format</span></span>

<span data-ttu-id="35f89-170">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-171">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-171">Pattern</span></span>

 <span data-ttu-id="35f89-172">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="35f89-173">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-173">Checksum</span></span>

<span data-ttu-id="35f89-174">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-175">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-175">Definition</span></span>

<span data-ttu-id="35f89-176">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-177">Регулярное выражение `Regex_croatia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-178">Найдено ключевое `Keywords_croatia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-179">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-179">Keywords</span></span>

<span data-ttu-id="35f89-180">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-180"></span></span>
|<span data-ttu-id="35f89-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-182">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-182">passport number</span></span>  <br/> <span data-ttu-id="35f89-183">номер паспорта для хорватского языка</span><span class="sxs-lookup"><span data-stu-id="35f89-183">croatian passport number</span></span>  <br/> <span data-ttu-id="35f89-184">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-184">passport no</span></span>  <br/> <span data-ttu-id="35f89-185">Брож путовнице</span><span class="sxs-lookup"><span data-stu-id="35f89-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="35f89-186">Кипр</span><span class="sxs-lookup"><span data-stu-id="35f89-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="35f89-187">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-187">Format</span></span>

<span data-ttu-id="35f89-188">Одна буква, за которой следуют 6-8 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-189">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-189">Pattern</span></span>

<span data-ttu-id="35f89-190">Одна буква, за которой следуют шесть и восемь цифр</span><span class="sxs-lookup"><span data-stu-id="35f89-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="35f89-191">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-191">Checksum</span></span>

<span data-ttu-id="35f89-192">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-193">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-193">Definition</span></span>

<span data-ttu-id="35f89-194">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-195">Регулярное выражение `Regex_cyprus_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-196">Найдено ключевое `Keywords_cyprus_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-197">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-197">Keywords</span></span>

<span data-ttu-id="35f89-198">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-198"></span></span>
|<span data-ttu-id="35f89-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-200">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-200">passport number</span></span>  <br/> <span data-ttu-id="35f89-201">номер паспорта для Кипр</span><span class="sxs-lookup"><span data-stu-id="35f89-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="35f89-202">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-202">passport no</span></span>  <br/> <span data-ttu-id="35f89-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="35f89-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="35f89-204">Чешская Республика</span><span class="sxs-lookup"><span data-stu-id="35f89-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="35f89-205">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-205">Format</span></span>

<span data-ttu-id="35f89-206">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-207">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-207">Pattern</span></span>

<span data-ttu-id="35f89-208">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="35f89-209">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-209">Checksum</span></span>

<span data-ttu-id="35f89-210">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-211">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-211">Definition</span></span>

<span data-ttu-id="35f89-212">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-213">Регулярное выражение `Regex_czech_republic_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-214">Найдено ключевое `Keywords_czech_republic_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-215">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-215">Keywords</span></span>

<span data-ttu-id="35f89-216">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-216"></span></span>
|<span data-ttu-id="35f89-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-218">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-218">passport number</span></span>  <br/> <span data-ttu-id="35f89-219">номер паспорта для чешского языка</span><span class="sxs-lookup"><span data-stu-id="35f89-219">czech passport number</span></span>  <br/> <span data-ttu-id="35f89-220">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-220">passport no</span></span>  <br/> <span data-ttu-id="35f89-221">цестовнí PAS</span><span class="sxs-lookup"><span data-stu-id="35f89-221">cestovní pas</span></span>  <br/> <span data-ttu-id="35f89-222">соответствующий</span><span class="sxs-lookup"><span data-stu-id="35f89-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="35f89-223">Дания</span><span class="sxs-lookup"><span data-stu-id="35f89-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="35f89-224">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-224">Format</span></span>

<span data-ttu-id="35f89-225">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-226">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-226">Pattern</span></span>

 <span data-ttu-id="35f89-227">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="35f89-228">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-228">Checksum</span></span>

<span data-ttu-id="35f89-229">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-230">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-230">Definition</span></span>

<span data-ttu-id="35f89-231">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-232">Регулярное выражение `Regex_denmark_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-233">Найдено ключевое `Keywords_denmark_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-234">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-234">Keywords</span></span>

<span data-ttu-id="35f89-235">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-235"></span></span>
|<span data-ttu-id="35f89-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-237">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-237">passport number</span></span>  <br/> <span data-ttu-id="35f89-238">номер паспорта для датского языка</span><span class="sxs-lookup"><span data-stu-id="35f89-238">danish passport number</span></span>  <br/> <span data-ttu-id="35f89-239">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-239">passport no</span></span>  <br/> <span data-ttu-id="35f89-240">соответствующий</span><span class="sxs-lookup"><span data-stu-id="35f89-240">pas</span></span>  <br/> <span data-ttu-id="35f89-241">паснуммер</span><span class="sxs-lookup"><span data-stu-id="35f89-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="35f89-242">Эстония</span><span class="sxs-lookup"><span data-stu-id="35f89-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="35f89-243">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-243">Format</span></span>

<span data-ttu-id="35f89-244">Одна буква, за которой следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-245">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-245">Pattern</span></span>

<span data-ttu-id="35f89-246">Одна буква, за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="35f89-247">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-247">Checksum</span></span>

<span data-ttu-id="35f89-248">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-249">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-249">Definition</span></span>

<span data-ttu-id="35f89-250">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-251">Регулярное выражение `Regex_estonia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-252">Найдено ключевое `Keywords_estonia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-253">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-253">Keywords</span></span>

<span data-ttu-id="35f89-254">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-254"></span></span>
|<span data-ttu-id="35f89-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-256">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-256">passport number</span></span>  <br/> <span data-ttu-id="35f89-257">номер паспорта для Эстонии</span><span class="sxs-lookup"><span data-stu-id="35f89-257">estonian passport number</span></span>  <br/> <span data-ttu-id="35f89-258">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-258">passport no</span></span>  <br/> <span data-ttu-id="35f89-259">Исти коданику Pass</span><span class="sxs-lookup"><span data-stu-id="35f89-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="35f89-260">Финляндия</span><span class="sxs-lookup"><span data-stu-id="35f89-260">Finland</span></span>

<span data-ttu-id="35f89-261">Дополнительные сведения можно найти в разделе "Финляндия Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="35f89-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="35f89-262">Франция</span><span class="sxs-lookup"><span data-stu-id="35f89-262">France</span></span>

<span data-ttu-id="35f89-263">Дополнительные сведения можно найти в разделе "Франция Passport Number", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="35f89-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="35f89-264">Германия</span><span class="sxs-lookup"><span data-stu-id="35f89-264">Germany</span></span>

<span data-ttu-id="35f89-265">Дополнительные сведения можно найти в разделе "немецкий паспорт номер", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="35f89-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="35f89-266">Греция</span><span class="sxs-lookup"><span data-stu-id="35f89-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="35f89-267">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-267">Format</span></span>

<span data-ttu-id="35f89-268">Две буквы, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-269">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-269">Pattern</span></span>

<span data-ttu-id="35f89-270">Две буквы, за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="35f89-271">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-271">Checksum</span></span>

<span data-ttu-id="35f89-272">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-273">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-273">Definition</span></span>

<span data-ttu-id="35f89-274">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-275">Регулярное выражение `Regex_greece_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-276">Найдено ключевое `Keywords_greece_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-277">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-277">Keywords</span></span>

<span data-ttu-id="35f89-278">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-278"></span></span>
|<span data-ttu-id="35f89-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-280">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-280">passport number</span></span>  <br/> <span data-ttu-id="35f89-281">номер паспорта греческого алфавита</span><span class="sxs-lookup"><span data-stu-id="35f89-281">greek passport number</span></span>  <br/> <span data-ttu-id="35f89-282">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-282">passport no</span></span>  <br/> <span data-ttu-id="35f89-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="35f89-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="35f89-284">Венгрия</span><span class="sxs-lookup"><span data-stu-id="35f89-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="35f89-285">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-285">Format</span></span>

<span data-ttu-id="35f89-286">Две буквы, за которыми следуют шесть или семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-287">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-287">Pattern</span></span>

<span data-ttu-id="35f89-288">Две буквы, за которыми следуют шесть или семь цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="35f89-289">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-289">Checksum</span></span>

<span data-ttu-id="35f89-290">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-291">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-291">Definition</span></span>

<span data-ttu-id="35f89-292">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-293">Регулярное выражение `Regex_hungary_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-294">Найдено ключевое `Keywords_hungary_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-295">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-295">Keywords</span></span>

<span data-ttu-id="35f89-296">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-296"></span></span>
|<span data-ttu-id="35f89-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-298">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-298">passport number</span></span>  <br/> <span data-ttu-id="35f89-299">Венгерский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="35f89-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="35f89-300">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-300">passport no</span></span>  <br/> <span data-ttu-id="35f89-301">úтлевéл сзáма</span><span class="sxs-lookup"><span data-stu-id="35f89-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="35f89-302">Ireland (Ирландия)</span><span class="sxs-lookup"><span data-stu-id="35f89-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="35f89-303">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-303">Format</span></span>

<span data-ttu-id="35f89-304">Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-305">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-305">Pattern</span></span>

<span data-ttu-id="35f89-306">Две буквы или цифры, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="35f89-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="35f89-307">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="35f89-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="35f89-308">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="35f89-309">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-309">Checksum</span></span>

<span data-ttu-id="35f89-310">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-311">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-311">Definition</span></span>

<span data-ttu-id="35f89-312">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-313">Регулярное выражение `Regex_ireland_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-314">Найдено ключевое `Keywords_ireland_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-315">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-315">Keywords</span></span>

<span data-ttu-id="35f89-316">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-316"></span></span>
|<span data-ttu-id="35f89-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-318">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-318">passport number</span></span>  <br/> <span data-ttu-id="35f89-319">Ирландский номер паспорта</span><span class="sxs-lookup"><span data-stu-id="35f89-319">irish passport number</span></span>  <br/> <span data-ttu-id="35f89-320">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-320">passport no</span></span>  <br/> <span data-ttu-id="35f89-321">соответствующий</span><span class="sxs-lookup"><span data-stu-id="35f89-321">pas</span></span>  <br/> <span data-ttu-id="35f89-322">службу</span><span class="sxs-lookup"><span data-stu-id="35f89-322">passport</span></span>  <br/> <span data-ttu-id="35f89-323">пассепорт</span><span class="sxs-lookup"><span data-stu-id="35f89-323">passeport</span></span>  <br/> <span data-ttu-id="35f89-324">пассепорт нумеро</span><span class="sxs-lookup"><span data-stu-id="35f89-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="35f89-325">Италия</span><span class="sxs-lookup"><span data-stu-id="35f89-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="35f89-326">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-326">Format</span></span>

<span data-ttu-id="35f89-327">Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-328">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-328">Pattern</span></span>

<span data-ttu-id="35f89-329">Две буквы или цифры, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="35f89-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="35f89-330">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="35f89-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="35f89-331">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="35f89-332">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-332">Checksum</span></span>

<span data-ttu-id="35f89-333">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="35f89-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-334">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-334">Definition</span></span>

<span data-ttu-id="35f89-335">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-336">Регулярное выражение `Regex_italy_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-337">Найдено ключевое `Keywords_italy_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-338">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-338">Keywords</span></span>

<span data-ttu-id="35f89-339">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-339"></span></span>
|<span data-ttu-id="35f89-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-341">номер паспорта для итальянского языка</span><span class="sxs-lookup"><span data-stu-id="35f89-341">italian passport number</span></span>  <br/> <span data-ttu-id="35f89-342">Репубблика итальянский пассапорто</span><span class="sxs-lookup"><span data-stu-id="35f89-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="35f89-343">пассапорто</span><span class="sxs-lookup"><span data-stu-id="35f89-343">passaporto</span></span>  <br/> <span data-ttu-id="35f89-344">пассапорто итальянский</span><span class="sxs-lookup"><span data-stu-id="35f89-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="35f89-345">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-345">passport number</span></span>  <br/> <span data-ttu-id="35f89-346">Итальянский пассапорто нумеро</span><span class="sxs-lookup"><span data-stu-id="35f89-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="35f89-347">пассапорто нумеро</span><span class="sxs-lookup"><span data-stu-id="35f89-347">passaporto numero</span></span>  <br/> <span data-ttu-id="35f89-348">нумéро пассепорт италиен</span><span class="sxs-lookup"><span data-stu-id="35f89-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="35f89-349">нумéро пассепорт</span><span class="sxs-lookup"><span data-stu-id="35f89-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="35f89-350">Латвия</span><span class="sxs-lookup"><span data-stu-id="35f89-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="35f89-351">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-351">Format</span></span>

<span data-ttu-id="35f89-352">Две буквы или цифры, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-353">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-353">Pattern</span></span>

<span data-ttu-id="35f89-354">Две буквы или цифры, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="35f89-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="35f89-355">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="35f89-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="35f89-356">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="35f89-357">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-357">Checksum</span></span>

<span data-ttu-id="35f89-358">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-359">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-359">Definition</span></span>

<span data-ttu-id="35f89-360">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-361">Регулярное выражение `Regex_latvia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-362">Найдено ключевое `Keywords_latvia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-363">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-363">Keywords</span></span>

<span data-ttu-id="35f89-364">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-364"></span></span>
|<span data-ttu-id="35f89-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-366">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-366">passport number</span></span>  <br/> <span data-ttu-id="35f89-367">номер паспорта для Латвии</span><span class="sxs-lookup"><span data-stu-id="35f89-367">latvian passport number</span></span>  <br/> <span data-ttu-id="35f89-368">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-368">passport no</span></span>  <br/> <span data-ttu-id="35f89-369">ПАСЕ нумурс</span><span class="sxs-lookup"><span data-stu-id="35f89-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="35f89-370">Литва</span><span class="sxs-lookup"><span data-stu-id="35f89-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="35f89-371">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-371">Format</span></span>

<span data-ttu-id="35f89-372">Восемь цифр или букв без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-373">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-373">Pattern</span></span>

<span data-ttu-id="35f89-374">Восемь цифр или букв (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="35f89-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="35f89-375">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-375">Checksum</span></span>

<span data-ttu-id="35f89-376">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="35f89-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-377">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-377">Definition</span></span>

<span data-ttu-id="35f89-378">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-379">Регулярное выражение `Regex_lithuania_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-380">Найдено ключевое `Keywords_lithuania_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-381">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-381">Keywords</span></span>

<span data-ttu-id="35f89-382">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-382"></span></span>
|<span data-ttu-id="35f89-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-384">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-384">passport number</span></span>  <br/> <span data-ttu-id="35f89-385">номер паспорта лисуниан</span><span class="sxs-lookup"><span data-stu-id="35f89-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="35f89-386">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-386">passport no</span></span>  <br/> <span data-ttu-id="35f89-387">Пасо нумерис</span><span class="sxs-lookup"><span data-stu-id="35f89-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="35f89-388">луксембург</span><span class="sxs-lookup"><span data-stu-id="35f89-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="35f89-389">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-389">Format</span></span>

<span data-ttu-id="35f89-390">Восемь цифр или букв без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-391">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-391">Pattern</span></span>

<span data-ttu-id="35f89-392">Восемь цифр или букв (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="35f89-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="35f89-393">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-393">Checksum</span></span>

<span data-ttu-id="35f89-394">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-395">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-395">Definition</span></span>

<span data-ttu-id="35f89-396">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-397">Регулярное выражение `Regex_nation_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-398">Найдено ключевое `Keywords_nation_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-399">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-399">Keywords</span></span>

<span data-ttu-id="35f89-400">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-400"></span></span>
|<span data-ttu-id="35f89-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-402">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-402">passport number</span></span>  <br/> <span data-ttu-id="35f89-403">номер паспорта для Латвии</span><span class="sxs-lookup"><span data-stu-id="35f89-403">latvian passport number</span></span>  <br/> <span data-ttu-id="35f89-404">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-404">passport no</span></span>  <br/> <span data-ttu-id="35f89-405">пасснуммер</span><span class="sxs-lookup"><span data-stu-id="35f89-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="35f89-406">Мальта</span><span class="sxs-lookup"><span data-stu-id="35f89-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="35f89-407">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-407">Format</span></span>

<span data-ttu-id="35f89-408">Семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-409">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-409">Pattern</span></span>

 <span data-ttu-id="35f89-410">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="35f89-411">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-411">Checksum</span></span>

<span data-ttu-id="35f89-412">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-413">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-413">Definition</span></span>

<span data-ttu-id="35f89-414">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-415">Регулярное выражение `Regex_malta_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-416">Найдено ключевое `Keywords_malta_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-417">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-417">Keywords</span></span>

<span data-ttu-id="35f89-418">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-418"></span></span>
|<span data-ttu-id="35f89-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-420">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-420">passport number</span></span>  <br/> <span data-ttu-id="35f89-421">номер паспорта Мальтийский</span><span class="sxs-lookup"><span data-stu-id="35f89-421">maltese passport number</span></span>  <br/> <span data-ttu-id="35f89-422">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-422">passport no</span></span>  <br/> <span data-ttu-id="35f89-423">нумру Тал — пассапорт</span><span class="sxs-lookup"><span data-stu-id="35f89-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="35f89-424">Нидерланды</span><span class="sxs-lookup"><span data-stu-id="35f89-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="35f89-425">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-425">Format</span></span>

<span data-ttu-id="35f89-426">Девять букв или цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-427">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-427">Pattern</span></span>

<span data-ttu-id="35f89-428">Девять букв или цифр;</span><span class="sxs-lookup"><span data-stu-id="35f89-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="35f89-429">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-429">Checksum</span></span>

<span data-ttu-id="35f89-430">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="35f89-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-431">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-431">Definition</span></span>

<span data-ttu-id="35f89-432">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-433">Регулярное выражение `Regex_netherlands_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-434">Найдено ключевое `Keywords_netherlands_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-435">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-435">Keywords</span></span>

<span data-ttu-id="35f89-436">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-436"></span></span>
|<span data-ttu-id="35f89-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-438">номер паспорта для нидерландского языка</span><span class="sxs-lookup"><span data-stu-id="35f89-438">dutch passport number</span></span>  <br/> <span data-ttu-id="35f89-439">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-439">passport number</span></span>  <br/> <span data-ttu-id="35f89-440">номер паспорта Нидерландов</span><span class="sxs-lookup"><span data-stu-id="35f89-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="35f89-441">недерланден паспурт нуммер</span><span class="sxs-lookup"><span data-stu-id="35f89-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="35f89-442">паспурт</span><span class="sxs-lookup"><span data-stu-id="35f89-442">paspoort</span></span>  <br/> <span data-ttu-id="35f89-443">недерланден паспуртнуммер</span><span class="sxs-lookup"><span data-stu-id="35f89-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="35f89-444">паспуртнуммер</span><span class="sxs-lookup"><span data-stu-id="35f89-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="35f89-445">Польша</span><span class="sxs-lookup"><span data-stu-id="35f89-445">Poland</span></span>

<span data-ttu-id="35f89-446">Дополнительные сведения можно найти в разделе "Польша Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="35f89-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="35f89-447">Португалия</span><span class="sxs-lookup"><span data-stu-id="35f89-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="35f89-448">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-448">Format</span></span>

<span data-ttu-id="35f89-449">Одна буква, за которой следуют шесть цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-450">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-450">Pattern</span></span>

<span data-ttu-id="35f89-451">Одна буква, за которой следуют шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="35f89-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="35f89-452">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="35f89-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="35f89-453">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="35f89-454">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-454">Checksum</span></span>

<span data-ttu-id="35f89-455">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-456">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-456">Definition</span></span>

<span data-ttu-id="35f89-457">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-458">Регулярное выражение `Regex_portugal_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-459">Найдено ключевое `Keywords_portugal_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-460">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-460">Keywords</span></span>

<span data-ttu-id="35f89-461">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-461"></span></span>
|<span data-ttu-id="35f89-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-463">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-463">passport number</span></span>  <br/> <span data-ttu-id="35f89-464">номер паспорта для португальского языка</span><span class="sxs-lookup"><span data-stu-id="35f89-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="35f89-465">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-465">passport no</span></span>  <br/> <span data-ttu-id="35f89-466">нúмеро Do пассапорте</span><span class="sxs-lookup"><span data-stu-id="35f89-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="35f89-467">Румыния</span><span class="sxs-lookup"><span data-stu-id="35f89-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="35f89-468">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-468">Format</span></span>

<span data-ttu-id="35f89-469">Восемь или девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-470">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-470">Pattern</span></span>

<span data-ttu-id="35f89-471">Восемь или девять цифр</span><span class="sxs-lookup"><span data-stu-id="35f89-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="35f89-472">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-472">Checksum</span></span>

<span data-ttu-id="35f89-473">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-474">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-474">Definition</span></span>

<span data-ttu-id="35f89-475">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-476">Регулярное выражение `Regex_romania_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-477">Найдено ключевое `Keywords_romania_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-478">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-478">Keywords</span></span>

<span data-ttu-id="35f89-479">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-479"></span></span>
|<span data-ttu-id="35f89-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-481">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-481">passport number</span></span>  <br/> <span data-ttu-id="35f89-482">номер паспорта для румынского языка</span><span class="sxs-lookup"><span data-stu-id="35f89-482">romanian passport number</span></span>  <br/> <span data-ttu-id="35f89-483">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-483">passport no</span></span>  <br/> <span data-ttu-id="35f89-484">нумăрул паșапортулуи</span><span class="sxs-lookup"><span data-stu-id="35f89-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="35f89-485">Словакия</span><span class="sxs-lookup"><span data-stu-id="35f89-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="35f89-486">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-486">Format</span></span>

<span data-ttu-id="35f89-487">Одна цифра или буква, за которой следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-488">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-488">Pattern</span></span>

<span data-ttu-id="35f89-489">Одна цифра или буква (без учета регистра), за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="35f89-490">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-490">Checksum</span></span>

<span data-ttu-id="35f89-491">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-492">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-492">Definition</span></span>

<span data-ttu-id="35f89-493">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-494">Регулярное выражение `Regex_slovakia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-495">Найдено ключевое `Keywords_slovakia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-496">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-496">Keywords</span></span>

<span data-ttu-id="35f89-497">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-497"></span></span>
|<span data-ttu-id="35f89-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-499">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-499">passport number</span></span>  <br/> <span data-ttu-id="35f89-500">номер паспорта словакиан</span><span class="sxs-lookup"><span data-stu-id="35f89-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="35f89-501">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-501">passport no</span></span>  <br/> <span data-ttu-id="35f89-502">číсло Пасу</span><span class="sxs-lookup"><span data-stu-id="35f89-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="35f89-503">Словения</span><span class="sxs-lookup"><span data-stu-id="35f89-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="35f89-504">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-504">Format</span></span>

<span data-ttu-id="35f89-505">Две буквы, за которыми следуют семь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-506">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-506">Pattern</span></span>

<span data-ttu-id="35f89-507">Две буквы, за которыми следуют семь цифр:</span><span class="sxs-lookup"><span data-stu-id="35f89-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="35f89-508">Буква "P"</span><span class="sxs-lookup"><span data-stu-id="35f89-508">The letter "P"</span></span>
    
- <span data-ttu-id="35f89-509">Одна прописная буква</span><span class="sxs-lookup"><span data-stu-id="35f89-509">One uppercase letter</span></span>
    
- <span data-ttu-id="35f89-510">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="35f89-511">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-511">Checksum</span></span>

<span data-ttu-id="35f89-512">Нет</span><span class="sxs-lookup"><span data-stu-id="35f89-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-513">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-513">Definition</span></span>

<span data-ttu-id="35f89-514">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-515">Регулярное выражение `Regex_slovenia_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-516">Найдено ключевое `Keywords_slovenia_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-517">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-517">Keywords</span></span>

<span data-ttu-id="35f89-518">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-518"></span></span>
|<span data-ttu-id="35f89-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-520">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-520">passport number</span></span>  <br/> <span data-ttu-id="35f89-521">номер паспорта для словенского языка</span><span class="sxs-lookup"><span data-stu-id="35f89-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="35f89-522">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-522">passport no</span></span>  <br/> <span data-ttu-id="35f89-523">Список потнега šтевилка</span><span class="sxs-lookup"><span data-stu-id="35f89-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="35f89-524">Испания</span><span class="sxs-lookup"><span data-stu-id="35f89-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="35f89-525">Format</span><span class="sxs-lookup"><span data-stu-id="35f89-525">Format</span></span>

<span data-ttu-id="35f89-526">Сочетание букв и цифр из восьми или девяти символов без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="35f89-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="35f89-527">Шаблон</span><span class="sxs-lookup"><span data-stu-id="35f89-527">Pattern</span></span>

<span data-ttu-id="35f89-528">Сочетание букв и цифр из восьми или девяти символов:</span><span class="sxs-lookup"><span data-stu-id="35f89-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="35f89-529">Две цифры или буквы</span><span class="sxs-lookup"><span data-stu-id="35f89-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="35f89-530">Одна цифра или буква (необязательно)</span><span class="sxs-lookup"><span data-stu-id="35f89-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="35f89-531">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="35f89-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="35f89-532">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="35f89-532">Checksum</span></span>

<span data-ttu-id="35f89-533">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="35f89-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="35f89-534">Определение</span><span class="sxs-lookup"><span data-stu-id="35f89-534">Definition</span></span>

<span data-ttu-id="35f89-535">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="35f89-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="35f89-536">Регулярное выражение `Regex_spain_eu_passport_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="35f89-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="35f89-537">Найдено ключевое `Keywords_spain_eu_passport_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="35f89-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="35f89-538">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="35f89-538">Keywords</span></span>

<span data-ttu-id="35f89-539">| |</span><span class="sxs-lookup"><span data-stu-id="35f89-539"></span></span>
|<span data-ttu-id="35f89-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="35f89-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="35f89-541">службу</span><span class="sxs-lookup"><span data-stu-id="35f89-541">passport</span></span>  <br/> <span data-ttu-id="35f89-542">Служба Passport, Испания</span><span class="sxs-lookup"><span data-stu-id="35f89-542">spain passport</span></span>  <br/> <span data-ttu-id="35f89-543">Книга Passport</span><span class="sxs-lookup"><span data-stu-id="35f89-543">passport book</span></span>  <br/> <span data-ttu-id="35f89-544">passport number</span><span class="sxs-lookup"><span data-stu-id="35f89-544">passport number</span></span>  <br/> <span data-ttu-id="35f89-545">паспорт нет</span><span class="sxs-lookup"><span data-stu-id="35f89-545">passport no</span></span>  <br/> <span data-ttu-id="35f89-546">либрета пасапорте</span><span class="sxs-lookup"><span data-stu-id="35f89-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="35f89-547">нúмеро пасапорте</span><span class="sxs-lookup"><span data-stu-id="35f89-547">número pasaporte</span></span>  <br/> <span data-ttu-id="35f89-548">еспаñа пасапорте</span><span class="sxs-lookup"><span data-stu-id="35f89-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="35f89-549">пасапорте</span><span class="sxs-lookup"><span data-stu-id="35f89-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="35f89-550">Швеция</span><span class="sxs-lookup"><span data-stu-id="35f89-550">Sweden</span></span>

<span data-ttu-id="35f89-551">Дополнительные сведения можно найти в разделе "Швеции Passport Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="35f89-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="35f89-552">ВОЗМЕЩЕН</span><span class="sxs-lookup"><span data-stu-id="35f89-552">UK</span></span>

<span data-ttu-id="35f89-553">Дополнительные сведения см. в разделе "США/Великобритания</span><span class="sxs-lookup"><span data-stu-id="35f89-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="35f89-554">Номер паспорта [, который ищет типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="35f89-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="35f89-555">См. также</span><span class="sxs-lookup"><span data-stu-id="35f89-555">See also</span></span>

[<span data-ttu-id="35f89-556">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="35f89-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

