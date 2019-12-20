---
title: Идентификационный номер налогоплательщика ЕС
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации для идентификационного номера ЕС. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: 0ee76fa46bb22b2754098d053ab769b862fdd3f2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805852"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="62fcd-104">Идентификационный номер налогоплательщика ЕС</span><span class="sxs-lookup"><span data-stu-id="62fcd-104">EU Tax Identification Number</span></span>

<span data-ttu-id="62fcd-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации налогоплательщика (TIN).</span><span class="sxs-lookup"><span data-stu-id="62fcd-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="62fcd-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="62fcd-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="62fcd-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="62fcd-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-108">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-108">Format</span></span>

<span data-ttu-id="62fcd-109">Девять цифр с необязательным дефисом и косой чертой.</span><span class="sxs-lookup"><span data-stu-id="62fcd-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-110">Pattern</span></span>

<span data-ttu-id="62fcd-111">Девять цифр с необязательным дефисом и косой чертой.</span><span class="sxs-lookup"><span data-stu-id="62fcd-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="62fcd-112">Две цифры</span><span class="sxs-lookup"><span data-stu-id="62fcd-112">Two digits</span></span> 
    
- <span data-ttu-id="62fcd-113">Дефис (необязательно)</span><span class="sxs-lookup"><span data-stu-id="62fcd-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="62fcd-114">Три цифры</span><span class="sxs-lookup"><span data-stu-id="62fcd-114">Three digits</span></span>
    
- <span data-ttu-id="62fcd-115">Косая черта (необязательно)</span><span class="sxs-lookup"><span data-stu-id="62fcd-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="62fcd-116">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="62fcd-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-117">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-117">Checksum</span></span>

<span data-ttu-id="62fcd-118">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-119">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-119">Definition</span></span>

<span data-ttu-id="62fcd-120">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-121">Функция `Func_austria_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-122">Найдено ключевое `Keywords_austria_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-123">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-124">Функция `Func_austria_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-125">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="62fcd-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-127">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-127">tax number</span></span>
  
<span data-ttu-id="62fcd-128">число</span><span class="sxs-lookup"><span data-stu-id="62fcd-128">number</span></span>
  
<span data-ttu-id="62fcd-129">Регистрационный номер налогоплательщика</span><span class="sxs-lookup"><span data-stu-id="62fcd-129">tax registration number</span></span>
  
<span data-ttu-id="62fcd-130">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-130">tax id</span></span>
  
<span data-ttu-id="62fcd-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="62fcd-131">st.nr.</span></span>
  
<span data-ttu-id="62fcd-132">стеуернуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="62fcd-133">Бельгия</span><span class="sxs-lookup"><span data-stu-id="62fcd-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-134">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-134">Format</span></span>

<span data-ttu-id="62fcd-135">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-136">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-136">Pattern</span></span>

<span data-ttu-id="62fcd-137">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="62fcd-137">11 digits:</span></span>
  
- <span data-ttu-id="62fcd-138">Две цифры</span><span class="sxs-lookup"><span data-stu-id="62fcd-138">Two digits</span></span>
    
- <span data-ttu-id="62fcd-139">"0" или "1"</span><span class="sxs-lookup"><span data-stu-id="62fcd-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="62fcd-140">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="62fcd-140">One digit</span></span>
    
- <span data-ttu-id="62fcd-141">"0" или "1" или "2" или "3"</span><span class="sxs-lookup"><span data-stu-id="62fcd-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="62fcd-142">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-143">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-143">Checksum</span></span>

<span data-ttu-id="62fcd-144">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="62fcd-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-145">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-145">Definition</span></span>

<span data-ttu-id="62fcd-146">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-147">Регулярное выражение `Regex_belgium_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-148">Найдено ключевое `Keywords_belgium_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-149">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="62fcd-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-151">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-151">tax number</span></span>
  
<span data-ttu-id="62fcd-152">Национальный регистрационный номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-152">national registration number</span></span>
  
<span data-ttu-id="62fcd-153">Регистрационный номер налогоплательщика</span><span class="sxs-lookup"><span data-stu-id="62fcd-153">tax registration number</span></span>
  
<span data-ttu-id="62fcd-154">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-154">tax id</span></span>
  
<span data-ttu-id="62fcd-155">включена</span><span class="sxs-lookup"><span data-stu-id="62fcd-155">nif</span></span>
  
<span data-ttu-id="62fcd-156">включена #</span><span class="sxs-lookup"><span data-stu-id="62fcd-156">nif#</span></span>
  
<span data-ttu-id="62fcd-157">нумéро de регистре National</span><span class="sxs-lookup"><span data-stu-id="62fcd-157">numéro de registre national</span></span>
  
<span data-ttu-id="62fcd-158">нумéро д'идентификатион Фин.</span><span class="sxs-lookup"><span data-stu-id="62fcd-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="62fcd-159">Болгария</span><span class="sxs-lookup"><span data-stu-id="62fcd-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-160">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-160">Format</span></span>

<span data-ttu-id="62fcd-161">Десять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-162">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-162">Pattern</span></span>

<span data-ttu-id="62fcd-163">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62fcd-164">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-164">Checksum</span></span>

<span data-ttu-id="62fcd-165">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-166">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-166">Definition</span></span>

<span data-ttu-id="62fcd-167">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-168">Функция `Func_bulgaria_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-169">Найдено ключевое `Keywords_bulgaria_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-170">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-171">Функция `Func_bulgaria_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-172">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="62fcd-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-174">букн</span><span class="sxs-lookup"><span data-stu-id="62fcd-174">bucn</span></span>
  
<span data-ttu-id="62fcd-175">единое гражданское число</span><span class="sxs-lookup"><span data-stu-id="62fcd-175">uniform civil number</span></span>
  
<span data-ttu-id="62fcd-176">букн #</span><span class="sxs-lookup"><span data-stu-id="62fcd-176">bucn#</span></span>
  
<span data-ttu-id="62fcd-177">униформЦивилнумбер #</span><span class="sxs-lookup"><span data-stu-id="62fcd-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="62fcd-178">унифицированный гражданский идентификатор</span><span class="sxs-lookup"><span data-stu-id="62fcd-178">uniform civil id</span></span>
  
<span data-ttu-id="62fcd-179">равномерный гражданский номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-179">uniform civil no</span></span>
  
<span data-ttu-id="62fcd-180">егн</span><span class="sxs-lookup"><span data-stu-id="62fcd-180">egn</span></span>
  
<span data-ttu-id="62fcd-181">номер унифицированного гражданства болгарского языка</span><span class="sxs-lookup"><span data-stu-id="62fcd-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="62fcd-182">униформЦивилно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-182">uniformcivilno#</span></span>
  
<span data-ttu-id="62fcd-183">егн #</span><span class="sxs-lookup"><span data-stu-id="62fcd-183">egn#</span></span>
  
<span data-ttu-id="62fcd-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-184">униформ граждански номер</span></span>
  
<span data-ttu-id="62fcd-185">Идентификатор униформ</span><span class="sxs-lookup"><span data-stu-id="62fcd-185">униформ id</span></span>
  
<span data-ttu-id="62fcd-186">униформ граждански ID</span><span class="sxs-lookup"><span data-stu-id="62fcd-186">униформ граждански id</span></span>
  
<span data-ttu-id="62fcd-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="62fcd-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="62fcd-188">Хорватия</span><span class="sxs-lookup"><span data-stu-id="62fcd-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-189">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-189">Format</span></span>

<span data-ttu-id="62fcd-190">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-191">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-191">Pattern</span></span>

<span data-ttu-id="62fcd-192">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="62fcd-192">11 digits:</span></span>
  
- <span data-ttu-id="62fcd-193">Десять цифр, выбран случайным образом</span><span class="sxs-lookup"><span data-stu-id="62fcd-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="62fcd-194">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="62fcd-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-195">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-195">Checksum</span></span>

<span data-ttu-id="62fcd-196">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-197">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-197">Definition</span></span>

<span data-ttu-id="62fcd-198">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-199">Функция `Func_croatia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-200">Найдено ключевое `Keywords_croatia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-201">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-202">Функция `Func_croatia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-203">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="62fcd-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-205">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-205">tax number</span></span>
  
<span data-ttu-id="62fcd-206">см</span><span class="sxs-lookup"><span data-stu-id="62fcd-206">tax</span></span>
  
<span data-ttu-id="62fcd-207">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-207">tax id</span></span>
  
<span data-ttu-id="62fcd-208">oid</span><span class="sxs-lookup"><span data-stu-id="62fcd-208">oid</span></span>
  
<span data-ttu-id="62fcd-209">идентификатора #</span><span class="sxs-lookup"><span data-stu-id="62fcd-209">oid#</span></span>
  
<span data-ttu-id="62fcd-210">порезни Брож</span><span class="sxs-lookup"><span data-stu-id="62fcd-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="62fcd-211">Кипр</span><span class="sxs-lookup"><span data-stu-id="62fcd-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-212">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-212">Format</span></span>

<span data-ttu-id="62fcd-213">Восемь цифр и одна буква в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="62fcd-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-214">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-214">Pattern</span></span>

<span data-ttu-id="62fcd-215">Восемь цифр и одна буква:</span><span class="sxs-lookup"><span data-stu-id="62fcd-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="62fcd-216">"0"</span><span class="sxs-lookup"><span data-stu-id="62fcd-216">A "0"</span></span> 
    
- <span data-ttu-id="62fcd-217">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="62fcd-217">Seven digits</span></span>
    
- <span data-ttu-id="62fcd-218">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="62fcd-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-219">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-219">Checksum</span></span>

<span data-ttu-id="62fcd-220">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="62fcd-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-221">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-221">Definition</span></span>

<span data-ttu-id="62fcd-222">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-223">Функция `Func_cyprus_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-224">Найдено ключевое `Keywords_cyprus_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-225">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-226">Функция `Func_cyprus_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-227">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="62fcd-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-229">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-229">tax number</span></span>
  
<span data-ttu-id="62fcd-230">см</span><span class="sxs-lookup"><span data-stu-id="62fcd-230">tax</span></span>
  
<span data-ttu-id="62fcd-231">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-231">tax id</span></span>
  
<span data-ttu-id="62fcd-232">Налоговый код идентификации</span><span class="sxs-lookup"><span data-stu-id="62fcd-232">tax identification code</span></span>
  
<span data-ttu-id="62fcd-233">тик</span><span class="sxs-lookup"><span data-stu-id="62fcd-233">tic</span></span>
  
<span data-ttu-id="62fcd-234">тик #</span><span class="sxs-lookup"><span data-stu-id="62fcd-234">tic#</span></span>
  
<span data-ttu-id="62fcd-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="62fcd-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="62fcd-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="62fcd-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="62fcd-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="62fcd-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="62fcd-238">Чешская Республика</span><span class="sxs-lookup"><span data-stu-id="62fcd-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-239">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-239">Format</span></span>

<span data-ttu-id="62fcd-240">Девять или десять цифр с необязательной обратной косой чертой</span><span class="sxs-lookup"><span data-stu-id="62fcd-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-241">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-241">Pattern</span></span>

<span data-ttu-id="62fcd-242">Девять или десять цифр с необязательной обратной косой чертой.</span><span class="sxs-lookup"><span data-stu-id="62fcd-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="62fcd-243">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="62fcd-243">Six digits</span></span> 
    
- <span data-ttu-id="62fcd-244">Обратная косая черта (необязательно)</span><span class="sxs-lookup"><span data-stu-id="62fcd-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="62fcd-245">Три или четыре цифры</span><span class="sxs-lookup"><span data-stu-id="62fcd-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-246">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-246">Checksum</span></span>

<span data-ttu-id="62fcd-247">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="62fcd-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-248">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-248">Definition</span></span>

<span data-ttu-id="62fcd-249">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-250">Регулярное выражение `Regex_czech_republic_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-251">Найдено ключевое `Keywords_czech_republic_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-252">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="62fcd-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-254">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-254">tax number</span></span>
  
<span data-ttu-id="62fcd-255">см</span><span class="sxs-lookup"><span data-stu-id="62fcd-255">tax</span></span>
  
<span data-ttu-id="62fcd-256">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-256">tax id</span></span>
  
<span data-ttu-id="62fcd-257">персональный номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-257">personal number</span></span>
  
<span data-ttu-id="62fcd-258">даňовé číсло</span><span class="sxs-lookup"><span data-stu-id="62fcd-258">daňové číslo</span></span>
  
<span data-ttu-id="62fcd-259">особнí číсло</span><span class="sxs-lookup"><span data-stu-id="62fcd-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="62fcd-260">Дания</span><span class="sxs-lookup"><span data-stu-id="62fcd-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-261">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-261">Format</span></span>

<span data-ttu-id="62fcd-262">Десять цифр, содержащие дефис</span><span class="sxs-lookup"><span data-stu-id="62fcd-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-263">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-263">Pattern</span></span>

<span data-ttu-id="62fcd-264">Десять цифр с дефисом:</span><span class="sxs-lookup"><span data-stu-id="62fcd-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="62fcd-265">Шесть цифр, соответствующих дате рождения (ДДММГГ —)</span><span class="sxs-lookup"><span data-stu-id="62fcd-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="62fcd-266">дефис;</span><span class="sxs-lookup"><span data-stu-id="62fcd-266">A hyphen</span></span>
    
- <span data-ttu-id="62fcd-267">Четыре цифры, которые соответствуют порядковому номеру, где первая цифра соответствует столетию рождения, а последняя цифра соответствует полу лица (нечетный для пола и даже для женщина)</span><span class="sxs-lookup"><span data-stu-id="62fcd-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-268">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-268">Checksum</span></span>

<span data-ttu-id="62fcd-269">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-270">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-270">Definition</span></span>

<span data-ttu-id="62fcd-271">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-272">Функция `Func_denmark_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-273">Найдено ключевое `Keywords_denmark_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-274">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-275">Функция `Func_denmark_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-276">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="62fcd-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-278">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-278">tax number</span></span>
  
<span data-ttu-id="62fcd-279">см</span><span class="sxs-lookup"><span data-stu-id="62fcd-279">tax</span></span>
  
<span data-ttu-id="62fcd-280">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-280">tax id</span></span>
  
<span data-ttu-id="62fcd-281">CPR Number</span><span class="sxs-lookup"><span data-stu-id="62fcd-281">cpr number</span></span>
  
<span data-ttu-id="62fcd-282">CPR #</span><span class="sxs-lookup"><span data-stu-id="62fcd-282">cpr#</span></span>
  
<span data-ttu-id="62fcd-283">Скат нуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-283">skat nummer</span></span>
  
<span data-ttu-id="62fcd-284">Идентификатор Скат</span><span class="sxs-lookup"><span data-stu-id="62fcd-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="62fcd-285">Эстония</span><span class="sxs-lookup"><span data-stu-id="62fcd-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-286">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-286">Format</span></span>

<span data-ttu-id="62fcd-287">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-288">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-288">Pattern</span></span>

<span data-ttu-id="62fcd-289">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="62fcd-289">11 digits:</span></span>
  
-  <span data-ttu-id="62fcd-290">Одна цифра, соответствующая пол и столетию рождения, где нечетное число означает "штекер", а четное число указывает на женщина следующим образом: 1, 2 для 19 века; 3, 4 — 20 века; и 5, 6 для 21 века</span><span class="sxs-lookup"><span data-stu-id="62fcd-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="62fcd-291">Шесть цифр, соответствующих дате рождения (ГГММДД)</span><span class="sxs-lookup"><span data-stu-id="62fcd-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="62fcd-292">Три цифры, которые соответствуют порядковому номеру, разделенному на одну и ту же дату.</span><span class="sxs-lookup"><span data-stu-id="62fcd-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="62fcd-293">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="62fcd-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-294">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-294">Checksum</span></span>

<span data-ttu-id="62fcd-295">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-296">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-296">Definition</span></span>

<span data-ttu-id="62fcd-297">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-298">Функция `Func_estonia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-299">Найдено ключевое `Keywords_estonia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-300">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-301">Функция `Func_estonia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-302">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="62fcd-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-304">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-304">tax number</span></span>
  
<span data-ttu-id="62fcd-305">см</span><span class="sxs-lookup"><span data-stu-id="62fcd-305">tax</span></span>
  
<span data-ttu-id="62fcd-306">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-306">tax id</span></span>
  
<span data-ttu-id="62fcd-307">персональный код</span><span class="sxs-lookup"><span data-stu-id="62fcd-307">personal code</span></span>
  
<span data-ttu-id="62fcd-308">максунумбер</span><span class="sxs-lookup"><span data-stu-id="62fcd-308">maksunumber</span></span>
  
<span data-ttu-id="62fcd-309">Идентификатор Максу</span><span class="sxs-lookup"><span data-stu-id="62fcd-309">maksu id</span></span>
  
<span data-ttu-id="62fcd-310">исикукуд</span><span class="sxs-lookup"><span data-stu-id="62fcd-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="62fcd-311">Финляндия</span><span class="sxs-lookup"><span data-stu-id="62fcd-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-312">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-312">Format</span></span>

<span data-ttu-id="62fcd-313">Сочетание цифр, букв и плюса, а также знак минуса</span><span class="sxs-lookup"><span data-stu-id="62fcd-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-314">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-314">Pattern</span></span>

<span data-ttu-id="62fcd-315">Сочетание цифр, букв и плюса и знака "плюс" и "минус" (11 символов).</span><span class="sxs-lookup"><span data-stu-id="62fcd-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="62fcd-316">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="62fcd-316">Six digits</span></span>
    
- <span data-ttu-id="62fcd-317">Один из следующих элементов: знак плюса, знак минуса или буква "A" (без учета регистра), где знак "плюс" (без учета регистра) означает 1900-1999, что знак "плюс" находится в диапазоне от 1 до 1800-1899, а "A" означает, что порожденный 2000 и после</span><span class="sxs-lookup"><span data-stu-id="62fcd-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="62fcd-318">Три цифры</span><span class="sxs-lookup"><span data-stu-id="62fcd-318">Three digits</span></span>
    
- <span data-ttu-id="62fcd-319">Одна буква или один номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-320">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-320">Checksum</span></span>

<span data-ttu-id="62fcd-321">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-322">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-322">Definition</span></span>

<span data-ttu-id="62fcd-323">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-324">Функция `Func_finland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-325">Найдено ключевое `Keywords_finland_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-326">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-327">Функция `Func_finland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-328">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="62fcd-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-330">identification number</span><span class="sxs-lookup"><span data-stu-id="62fcd-330">identification number</span></span>
  
<span data-ttu-id="62fcd-331">личный идентификатор</span><span class="sxs-lookup"><span data-stu-id="62fcd-331">personal id</span></span>
  
<span data-ttu-id="62fcd-332">идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-332">identity number</span></span>
  
<span data-ttu-id="62fcd-333">Финский национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-333">finnish national id number</span></span>
  
<span data-ttu-id="62fcd-334">персоналиднумбер #</span><span class="sxs-lookup"><span data-stu-id="62fcd-334">personalidnumber#</span></span>
  
<span data-ttu-id="62fcd-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="62fcd-335">national identification number</span></span>
  
<span data-ttu-id="62fcd-336">идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-336">id number</span></span>
  
<span data-ttu-id="62fcd-337">код страны</span><span class="sxs-lookup"><span data-stu-id="62fcd-337">national id no.</span></span>
  
<span data-ttu-id="62fcd-338">Национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-338">national id number</span></span>
  
<span data-ttu-id="62fcd-339">ID No</span><span class="sxs-lookup"><span data-stu-id="62fcd-339">id no</span></span>
  
<span data-ttu-id="62fcd-340">туннистенумеро</span><span class="sxs-lookup"><span data-stu-id="62fcd-340">tunnistenumero</span></span>
  
<span data-ttu-id="62fcd-341">хенкилöтуннус</span><span class="sxs-lookup"><span data-stu-id="62fcd-341">henkilötunnus</span></span>
  
<span data-ttu-id="62fcd-342">иксилöллинен хенкилöкохтаинен туннистенумеро</span><span class="sxs-lookup"><span data-stu-id="62fcd-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="62fcd-343">аинутлаатуинен хенкилöкохтаинен туннус</span><span class="sxs-lookup"><span data-stu-id="62fcd-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="62fcd-344">идентититти нумеро</span><span class="sxs-lookup"><span data-stu-id="62fcd-344">identiteetti numero</span></span>
  
<span data-ttu-id="62fcd-345">Суомен кансаллинен хенкилöтуннус</span><span class="sxs-lookup"><span data-stu-id="62fcd-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="62fcd-346">хенкилöтуннуснумеро #</span><span class="sxs-lookup"><span data-stu-id="62fcd-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="62fcd-347">кансаллисен туннистенумеро</span><span class="sxs-lookup"><span data-stu-id="62fcd-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="62fcd-348">туннуснумеро</span><span class="sxs-lookup"><span data-stu-id="62fcd-348">tunnusnumero</span></span>
  
<span data-ttu-id="62fcd-349">кансаллинен туннус нумеро</span><span class="sxs-lookup"><span data-stu-id="62fcd-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="62fcd-350">Франция</span><span class="sxs-lookup"><span data-stu-id="62fcd-350">France</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-351">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-351">Format</span></span>

<span data-ttu-id="62fcd-352">13 цифр для отдельных пользователей и девять цифр для сущностей</span><span class="sxs-lookup"><span data-stu-id="62fcd-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-353">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-353">Pattern</span></span>

<span data-ttu-id="62fcd-354">13 цифр для отдельных пользователей:</span><span class="sxs-lookup"><span data-stu-id="62fcd-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="62fcd-355">Одна цифра, которая должна быть равна 0, 1, 2 или 3</span><span class="sxs-lookup"><span data-stu-id="62fcd-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="62fcd-356">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-356">12 digits</span></span>
    
<span data-ttu-id="62fcd-357">Девять цифр для сущностей</span><span class="sxs-lookup"><span data-stu-id="62fcd-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62fcd-358">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-358">Checksum</span></span>

<span data-ttu-id="62fcd-359">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="62fcd-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-360">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-360">Definition</span></span>

<span data-ttu-id="62fcd-361">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-362">Функция `Func_france_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-363">Найдено ключевое `Keywords_france_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-364">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-365">Функция `Func_france_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-366">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="62fcd-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-368">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="62fcd-368">tax identification number</span></span>
  
<span data-ttu-id="62fcd-369">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-369">tax number</span></span>
  
<span data-ttu-id="62fcd-370">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-370">tax id</span></span>
  
<span data-ttu-id="62fcd-371">нумéро д'идентификатион Фин.</span><span class="sxs-lookup"><span data-stu-id="62fcd-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="62fcd-372">Германия</span><span class="sxs-lookup"><span data-stu-id="62fcd-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-373">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-373">Format</span></span>

<span data-ttu-id="62fcd-374">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-375">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-375">Pattern</span></span>

<span data-ttu-id="62fcd-376">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="62fcd-376">11 digits :</span></span>
  
-  <span data-ttu-id="62fcd-377">Десять цифр</span><span class="sxs-lookup"><span data-stu-id="62fcd-377">Ten digits</span></span> 
    
- <span data-ttu-id="62fcd-378">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="62fcd-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-379">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-379">Checksum</span></span>

<span data-ttu-id="62fcd-380">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-381">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-381">Definition</span></span>

<span data-ttu-id="62fcd-382">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-383">Функция `Func_germany_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-384">Найдено ключевое `Keywords_germany_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-385">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-386">Функция `Func_germany_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-387">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="62fcd-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-389">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-389">tax number</span></span>
  
<span data-ttu-id="62fcd-390">налог но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-390">tax no.</span></span>
  
<span data-ttu-id="62fcd-391">таксно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-391">taxno#</span></span>
  
<span data-ttu-id="62fcd-392">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="62fcd-392">taxnumber#</span></span>
  
<span data-ttu-id="62fcd-393">такснумбер</span><span class="sxs-lookup"><span data-stu-id="62fcd-393">taxnumber</span></span>
  
<span data-ttu-id="62fcd-394">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-394">tax id</span></span>
  
<span data-ttu-id="62fcd-395">такси #</span><span class="sxs-lookup"><span data-stu-id="62fcd-395">taxid#</span></span>
  
<span data-ttu-id="62fcd-396">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="62fcd-396">tax identification number</span></span>
  
<span data-ttu-id="62fcd-397">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="62fcd-397">tax identification no.</span></span>
  
<span data-ttu-id="62fcd-398">стеуернуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-398">steuernummer</span></span>
  
<span data-ttu-id="62fcd-399">Идентификатор стеуер</span><span class="sxs-lookup"><span data-stu-id="62fcd-399">steuer id</span></span>
  
<span data-ttu-id="62fcd-400">стеуеридентификатионснуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="62fcd-401">Греция</span><span class="sxs-lookup"><span data-stu-id="62fcd-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-402">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-402">Format</span></span>

<span data-ttu-id="62fcd-403">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-404">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-404">Pattern</span></span>

<span data-ttu-id="62fcd-405">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62fcd-406">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-406">Checksum</span></span>

<span data-ttu-id="62fcd-407">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="62fcd-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-408">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-408">Definition</span></span>

<span data-ttu-id="62fcd-409">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-410">Регулярное выражение `Regex_greece_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-411">Найдено ключевое `Keywords_greece_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-412">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="62fcd-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-414">афм</span><span class="sxs-lookup"><span data-stu-id="62fcd-414">afm</span></span>
  
<span data-ttu-id="62fcd-415">ИНН</span><span class="sxs-lookup"><span data-stu-id="62fcd-415">tin</span></span>
  
<span data-ttu-id="62fcd-416">Налоговый код но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-416">tax id no.</span></span>
  
<span data-ttu-id="62fcd-417">Налоговый код No</span><span class="sxs-lookup"><span data-stu-id="62fcd-417">tax id no</span></span>
  
<span data-ttu-id="62fcd-418">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="62fcd-418">tax identification number</span></span>
  
<span data-ttu-id="62fcd-419">Налоговый номер реестра</span><span class="sxs-lookup"><span data-stu-id="62fcd-419">tax registry number</span></span>
  
<span data-ttu-id="62fcd-420">реестр по номеру налога</span><span class="sxs-lookup"><span data-stu-id="62fcd-420">tax registry no.</span></span>
  
<span data-ttu-id="62fcd-421">афм #</span><span class="sxs-lookup"><span data-stu-id="62fcd-421">afm#</span></span>
  
<span data-ttu-id="62fcd-422">ИНН #</span><span class="sxs-lookup"><span data-stu-id="62fcd-422">tin#</span></span>
  
<span data-ttu-id="62fcd-423">таксидно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-423">taxidno#</span></span>
  
<span data-ttu-id="62fcd-424">таксрегистрино #</span><span class="sxs-lookup"><span data-stu-id="62fcd-424">taxregistryno#</span></span>
  
<span data-ttu-id="62fcd-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="62fcd-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="62fcd-426">аφμ</span><span class="sxs-lookup"><span data-stu-id="62fcd-426">aφμ</span></span>
  
<span data-ttu-id="62fcd-427">аφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="62fcd-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="62fcd-428">φορολογικού μητρώου Νο.</span><span class="sxs-lookup"><span data-stu-id="62fcd-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="62fcd-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="62fcd-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="62fcd-430">Венгрия</span><span class="sxs-lookup"><span data-stu-id="62fcd-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-431">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-431">Format</span></span>

<span data-ttu-id="62fcd-432">Десять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-433">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-433">Pattern</span></span>

<span data-ttu-id="62fcd-434">Десять цифр:</span><span class="sxs-lookup"><span data-stu-id="62fcd-434">Ten digits:</span></span>
  
-  <span data-ttu-id="62fcd-435">Одна цифра, которая должна быть "8"</span><span class="sxs-lookup"><span data-stu-id="62fcd-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="62fcd-436">Пять цифр, которые соответствуют количеству дней между датой 01/01/1867 и датой рождения отдельного лица.</span><span class="sxs-lookup"><span data-stu-id="62fcd-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="62fcd-437">Три цифры, которые соответствуют номеру, созданному шансом выделить людей, которые поставили один и тот же день.</span><span class="sxs-lookup"><span data-stu-id="62fcd-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="62fcd-438">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="62fcd-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-439">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-439">Checksum</span></span>

<span data-ttu-id="62fcd-440">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-441">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-441">Definition</span></span>

<span data-ttu-id="62fcd-442">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-443">Функция `Func_hungary_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-444">Найдено ключевое `Keywords_hungary_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-445">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-446">Функция `Func_hungary_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-447">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="62fcd-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-449">идентификационный номер для венгерского налога</span><span class="sxs-lookup"><span data-stu-id="62fcd-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="62fcd-450">Венгерский Tin</span><span class="sxs-lookup"><span data-stu-id="62fcd-450">hungarian tin</span></span>
  
<span data-ttu-id="62fcd-451">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="62fcd-451">tax id number</span></span>
  
<span data-ttu-id="62fcd-452">номер НДС</span><span class="sxs-lookup"><span data-stu-id="62fcd-452">vat number</span></span>
  
<span data-ttu-id="62fcd-453">Налоговый орган без</span><span class="sxs-lookup"><span data-stu-id="62fcd-453">tax authority no</span></span>
  
<span data-ttu-id="62fcd-454">идентификационный номер налогоплательщика для налогового кода</span><span class="sxs-lookup"><span data-stu-id="62fcd-454">tax id tax identity number</span></span>
  
<span data-ttu-id="62fcd-455">таксиднумбер #</span><span class="sxs-lookup"><span data-stu-id="62fcd-455">taxidnumber#</span></span>
  
<span data-ttu-id="62fcd-456">ИНН #</span><span class="sxs-lookup"><span data-stu-id="62fcd-456">tin#</span></span>
  
<span data-ttu-id="62fcd-457">хунгатиантин #</span><span class="sxs-lookup"><span data-stu-id="62fcd-457">hungatiantin#</span></span>
  
<span data-ttu-id="62fcd-458">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="62fcd-458">tax identification no</span></span>
  
<span data-ttu-id="62fcd-459">таксидно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-459">taxidno#</span></span>
  
<span data-ttu-id="62fcd-460">адóазоносíтó сзáм</span><span class="sxs-lookup"><span data-stu-id="62fcd-460">adóazonosító szám</span></span>
  
<span data-ttu-id="62fcd-461">адóсзáм</span><span class="sxs-lookup"><span data-stu-id="62fcd-461">adószám</span></span>
  
<span data-ttu-id="62fcd-462">адóхатóсáг сзáм</span><span class="sxs-lookup"><span data-stu-id="62fcd-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="62fcd-463">Ireland (Ирландия)</span><span class="sxs-lookup"><span data-stu-id="62fcd-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-464">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-464">Format</span></span>

<span data-ttu-id="62fcd-465">Семь цифр, за которыми следует буква без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-466">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-466">Pattern</span></span>

<span data-ttu-id="62fcd-467">Семь цифр, за которыми следует буква:</span><span class="sxs-lookup"><span data-stu-id="62fcd-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="62fcd-468">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="62fcd-468">Seven digits</span></span> 
    
- <span data-ttu-id="62fcd-469">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="62fcd-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-470">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-470">Checksum</span></span>

<span data-ttu-id="62fcd-471">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="62fcd-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-472">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-472">Definition</span></span>

<span data-ttu-id="62fcd-473">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-474">Функция `Func_ireland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-475">Найдено ключевое `Keywords_ireland_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-476">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-477">Функция `Func_ireland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-478">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="62fcd-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-480">общедоступная служба</span><span class="sxs-lookup"><span data-stu-id="62fcd-480">public service no</span></span>
  
<span data-ttu-id="62fcd-481">Личная общедоступная служба</span><span class="sxs-lookup"><span data-stu-id="62fcd-481">personal public service no</span></span>
  
<span data-ttu-id="62fcd-482">PPS нет</span><span class="sxs-lookup"><span data-stu-id="62fcd-482">pps no</span></span>
  
<span data-ttu-id="62fcd-483">Личная служба</span><span class="sxs-lookup"><span data-stu-id="62fcd-483">personal service no</span></span>
  
<span data-ttu-id="62fcd-484">Служба PPS нет</span><span class="sxs-lookup"><span data-stu-id="62fcd-484">pps service no</span></span>
  
<span data-ttu-id="62fcd-485">ппсно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-485">ppsno#</span></span>
  
<span data-ttu-id="62fcd-486">Ирландский PPS No</span><span class="sxs-lookup"><span data-stu-id="62fcd-486">irish pps no</span></span>
  
<span data-ttu-id="62fcd-487">публиксервицено #</span><span class="sxs-lookup"><span data-stu-id="62fcd-487">publicserviceno#</span></span>
  
<span data-ttu-id="62fcd-488">номер личной общедоступной службы</span><span class="sxs-lookup"><span data-stu-id="62fcd-488">personal public service number</span></span>
  
<span data-ttu-id="62fcd-489">уимхир феарсанта сеирбхíсе поиблí</span><span class="sxs-lookup"><span data-stu-id="62fcd-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="62fcd-490">PPS уимх</span><span class="sxs-lookup"><span data-stu-id="62fcd-490">pps uimh</span></span>
  
<span data-ttu-id="62fcd-491">уимхир аисеантаис феарсанта</span><span class="sxs-lookup"><span data-stu-id="62fcd-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="62fcd-492">Италия</span><span class="sxs-lookup"><span data-stu-id="62fcd-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-493">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-493">Format</span></span>

<span data-ttu-id="62fcd-494">16 букв и цифр в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="62fcd-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-495">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-495">Pattern</span></span>

<span data-ttu-id="62fcd-496">16 букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="62fcd-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="62fcd-497">Три буквы, соответствующие первым трем согласным в имени семейства</span><span class="sxs-lookup"><span data-stu-id="62fcd-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="62fcd-498">Три буквы, соответствующие первым, третьим и четвертым согласным в имени.</span><span class="sxs-lookup"><span data-stu-id="62fcd-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="62fcd-499">Две цифры, соответствующие последним цифрам года рождения</span><span class="sxs-lookup"><span data-stu-id="62fcd-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="62fcd-500">Одна цифра, соответствующая месяцу рождения, буквы используются в алфавитном порядке, но используются только буквы от A до E, H, L, M, P, R — T (то есть Январь — это R, а Октябрь — R)</span><span class="sxs-lookup"><span data-stu-id="62fcd-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="62fcd-501">Две цифры, которые соответствуют дню рождения, где 40 добавляется к дню рождения женщин, чтобы отличать от мужчин</span><span class="sxs-lookup"><span data-stu-id="62fcd-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="62fcd-502">Четыре цифры, соответствующие коду города, соответствующему органу государственной власти, в котором был создан пользователь, — коды уровня страны используются для иностранных стран</span><span class="sxs-lookup"><span data-stu-id="62fcd-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="62fcd-503">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="62fcd-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-504">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-504">Checksum</span></span>

<span data-ttu-id="62fcd-505">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-506">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-506">Definition</span></span>

<span data-ttu-id="62fcd-507">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-508">Функция `Func_italy_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-509">Найдено ключевое `Keywords_italy_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-510">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-511">Функция `Func_italy_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-512">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="62fcd-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-514">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-514">tax number</span></span>
  
<span data-ttu-id="62fcd-515">налог но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-515">tax no.</span></span>
  
<span data-ttu-id="62fcd-516">таксно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-516">taxno#</span></span>
  
<span data-ttu-id="62fcd-517">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="62fcd-517">taxnumber#</span></span>
  
<span data-ttu-id="62fcd-518">такснумбер</span><span class="sxs-lookup"><span data-stu-id="62fcd-518">taxnumber</span></span>
  
<span data-ttu-id="62fcd-519">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-519">tax id</span></span>
  
<span data-ttu-id="62fcd-520">такси #</span><span class="sxs-lookup"><span data-stu-id="62fcd-520">taxid#</span></span>
  
<span data-ttu-id="62fcd-521">Финансовый код</span><span class="sxs-lookup"><span data-stu-id="62fcd-521">fiscal code</span></span>
  
<span data-ttu-id="62fcd-522">финансовый отчет по сокостям</span><span class="sxs-lookup"><span data-stu-id="62fcd-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="62fcd-523">Латвия</span><span class="sxs-lookup"><span data-stu-id="62fcd-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-524">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-524">Format</span></span>

<span data-ttu-id="62fcd-525">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-526">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-526">Pattern</span></span>

<span data-ttu-id="62fcd-527">11 цифр в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="62fcd-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="62fcd-528">Шесть цифр, соответствующих дате рождения (ДДММГГ —)</span><span class="sxs-lookup"><span data-stu-id="62fcd-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="62fcd-529">Одна цифра, соответствующая столетию рождения, где "0" соответствует 19 века, "1" соответствует 20 столетию, а "2" соответствует 21 столетию</span><span class="sxs-lookup"><span data-stu-id="62fcd-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="62fcd-530">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="62fcd-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-531">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-531">Checksum</span></span>

<span data-ttu-id="62fcd-532">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-533">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-533">Definition</span></span>

<span data-ttu-id="62fcd-534">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-535">Функция `Func_latvia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-536">Найдено ключевое `Keywords_latvia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-537">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-538">Функция `Func_latvia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-539">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="62fcd-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-541">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-541">tax number</span></span>
  
<span data-ttu-id="62fcd-542">налог но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-542">tax no.</span></span>
  
<span data-ttu-id="62fcd-543">таксно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-543">taxno#</span></span>
  
<span data-ttu-id="62fcd-544">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="62fcd-544">taxnumber#</span></span>
  
<span data-ttu-id="62fcd-545">такснумбер</span><span class="sxs-lookup"><span data-stu-id="62fcd-545">taxnumber</span></span>
  
<span data-ttu-id="62fcd-546">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-546">tax id</span></span>
  
<span data-ttu-id="62fcd-547">такси #</span><span class="sxs-lookup"><span data-stu-id="62fcd-547">taxid#</span></span>
  
<span data-ttu-id="62fcd-548">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="62fcd-548">tax identification number</span></span>
  
<span data-ttu-id="62fcd-549">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="62fcd-549">tax identification no.</span></span>
  
<span data-ttu-id="62fcd-550">нодокļа нумурс</span><span class="sxs-lookup"><span data-stu-id="62fcd-550">nodokļa numurs</span></span>
  
<span data-ttu-id="62fcd-551">нодокļу идентификāЦижас нумурс</span><span class="sxs-lookup"><span data-stu-id="62fcd-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="62fcd-552">нодокļу идентификāЦижа нумурс</span><span class="sxs-lookup"><span data-stu-id="62fcd-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="62fcd-553">Литва</span><span class="sxs-lookup"><span data-stu-id="62fcd-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-554">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-554">Format</span></span>

<span data-ttu-id="62fcd-555">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-556">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-556">Pattern</span></span>

<span data-ttu-id="62fcd-557">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62fcd-558">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-558">Checksum</span></span>

<span data-ttu-id="62fcd-559">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="62fcd-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-560">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-560">Definition</span></span>

<span data-ttu-id="62fcd-561">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-562">Функция `Func_lithuania_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-563">Найдено ключевое `Keywords_lithuania_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-564">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-565">Функция `Func_lithuania_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-566">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="62fcd-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-568">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-568">tax number</span></span>
  
<span data-ttu-id="62fcd-569">налог но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-569">tax no.</span></span>
  
<span data-ttu-id="62fcd-570">налог без #</span><span class="sxs-lookup"><span data-stu-id="62fcd-570">tax no#</span></span>
  
<span data-ttu-id="62fcd-571">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="62fcd-571">taxnumber#</span></span>
  
<span data-ttu-id="62fcd-572">такснумбер</span><span class="sxs-lookup"><span data-stu-id="62fcd-572">taxnumber</span></span>
  
<span data-ttu-id="62fcd-573">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-573">tax id</span></span>
  
<span data-ttu-id="62fcd-574">такси #</span><span class="sxs-lookup"><span data-stu-id="62fcd-574">taxid#</span></span>
  
<span data-ttu-id="62fcd-575">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="62fcd-575">tax identification number</span></span>
  
<span data-ttu-id="62fcd-576">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="62fcd-576">tax identification no.</span></span>
  
<span data-ttu-id="62fcd-577">Идентификатор мокесčиų</span><span class="sxs-lookup"><span data-stu-id="62fcd-577">mokesčių id</span></span>
  
<span data-ttu-id="62fcd-578">мокесčиų нумерис</span><span class="sxs-lookup"><span data-stu-id="62fcd-578">mokesčių numeris</span></span>
  
<span data-ttu-id="62fcd-579">мокесčиų идентификавимас нумерис</span><span class="sxs-lookup"><span data-stu-id="62fcd-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="62fcd-580">луксембург</span><span class="sxs-lookup"><span data-stu-id="62fcd-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-581">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-581">Format</span></span>

<span data-ttu-id="62fcd-582">13 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-583">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-583">Pattern</span></span>

<span data-ttu-id="62fcd-584">13 цифр:</span><span class="sxs-lookup"><span data-stu-id="62fcd-584">13 digits:</span></span>
  
-  <span data-ttu-id="62fcd-585">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-585">11 digits</span></span> 
    
- <span data-ttu-id="62fcd-586">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="62fcd-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-587">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-587">Checksum</span></span>

<span data-ttu-id="62fcd-588">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-589">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-589">Definition</span></span>

<span data-ttu-id="62fcd-590">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-591">Функция `Func_luxemburg_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-592">Найдено ключевое `Keywords_luxemburg_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-593">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-594">Функция `Func_luxemburg_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-595">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="62fcd-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-597">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-597">tax number</span></span>
  
<span data-ttu-id="62fcd-598">налог но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-598">tax no.</span></span>
  
<span data-ttu-id="62fcd-599">таксно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-599">taxno#</span></span>
  
<span data-ttu-id="62fcd-600">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="62fcd-600">taxnumber#</span></span>
  
<span data-ttu-id="62fcd-601">такснумбер</span><span class="sxs-lookup"><span data-stu-id="62fcd-601">taxnumber</span></span>
  
<span data-ttu-id="62fcd-602">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-602">tax id</span></span>
  
<span data-ttu-id="62fcd-603">такси #</span><span class="sxs-lookup"><span data-stu-id="62fcd-603">taxid#</span></span>
  
<span data-ttu-id="62fcd-604">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="62fcd-604">tax identification number</span></span>
  
<span data-ttu-id="62fcd-605">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="62fcd-605">tax identification no.</span></span>
  
<span data-ttu-id="62fcd-606">стеуернуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-606">steuernummer</span></span>
  
<span data-ttu-id="62fcd-607">Идентификатор стеуер</span><span class="sxs-lookup"><span data-stu-id="62fcd-607">steuer id</span></span>
  
<span data-ttu-id="62fcd-608">стеуеридентификатионснуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="62fcd-609">Мальта</span><span class="sxs-lookup"><span data-stu-id="62fcd-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-610">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-610">Format</span></span>

<span data-ttu-id="62fcd-611">Для национальных замальтийский: 7 цифр и одна буква в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="62fcd-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="62fcd-612">Мальтийскийные страны и Мальтийский, не являющиеся субъектами: 9 цифр</span><span class="sxs-lookup"><span data-stu-id="62fcd-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-613">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-613">Pattern</span></span>

<span data-ttu-id="62fcd-614">Мальтийский национальные условия: 7 цифр и одна буква</span><span class="sxs-lookup"><span data-stu-id="62fcd-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="62fcd-615">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="62fcd-615">Seven digits</span></span> 
    
- <span data-ttu-id="62fcd-616">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="62fcd-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="62fcd-617">Мальтийскийные страны и Мальтийский, не являющиеся субъектами: 9 цифр</span><span class="sxs-lookup"><span data-stu-id="62fcd-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="62fcd-618">девять цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="62fcd-619">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-619">Checksum</span></span>

<span data-ttu-id="62fcd-620">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="62fcd-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-621">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-621">Definition</span></span>

<span data-ttu-id="62fcd-622">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-623">Функция `Func_malta_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-624">Найдено ключевое `Keywords_malta_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-625">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-626">Функция `Func_malta_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-627">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="62fcd-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-629">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-629">tax number</span></span>
  
<span data-ttu-id="62fcd-630">налог но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-630">tax no.</span></span>
  
<span data-ttu-id="62fcd-631">таксно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-631">taxno#</span></span>
  
<span data-ttu-id="62fcd-632">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="62fcd-632">taxnumber#</span></span>
  
<span data-ttu-id="62fcd-633">такснумбер</span><span class="sxs-lookup"><span data-stu-id="62fcd-633">taxnumber</span></span>
  
<span data-ttu-id="62fcd-634">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-634">tax id</span></span>
  
<span data-ttu-id="62fcd-635">такси #</span><span class="sxs-lookup"><span data-stu-id="62fcd-635">taxid#</span></span>
  
<span data-ttu-id="62fcd-636">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="62fcd-636">tax identification number</span></span>
  
<span data-ttu-id="62fcd-637">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="62fcd-637">tax identification no.</span></span>
  
<span data-ttu-id="62fcd-638">нумру ТАТ — такскса</span><span class="sxs-lookup"><span data-stu-id="62fcd-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="62fcd-639">ID ТАТ — такскса</span><span class="sxs-lookup"><span data-stu-id="62fcd-639">id tat-taxxa</span></span>
  
<span data-ttu-id="62fcd-640">нумру Ta ' идентификаззжони ТАТ такскса</span><span class="sxs-lookup"><span data-stu-id="62fcd-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="62fcd-641">Нидерланды</span><span class="sxs-lookup"><span data-stu-id="62fcd-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-642">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-642">Format</span></span>

<span data-ttu-id="62fcd-643">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-644">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-644">Pattern</span></span>

<span data-ttu-id="62fcd-645">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="62fcd-646">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-646">Checksum</span></span>

<span data-ttu-id="62fcd-647">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-648">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-648">Definition</span></span>

<span data-ttu-id="62fcd-649">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-650">Функция `Func_netherlands_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-651">Найдено ключевое `Keywords_netherlands_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-652">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-653">Функция `Func_netherlands_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-654">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="62fcd-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-656">идентификационный номер налога Нидерландов</span><span class="sxs-lookup"><span data-stu-id="62fcd-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="62fcd-657">Идентификация налога Нидерландов</span><span class="sxs-lookup"><span data-stu-id="62fcd-657">netherlands tax identification</span></span>
  
<span data-ttu-id="62fcd-658">идентификационный номер налога несерланд</span><span class="sxs-lookup"><span data-stu-id="62fcd-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="62fcd-659">Налоговый код несерланд</span><span class="sxs-lookup"><span data-stu-id="62fcd-659">netherland's tax identification</span></span>
  
<span data-ttu-id="62fcd-660">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="62fcd-660">tax identification number</span></span>
  
<span data-ttu-id="62fcd-661">Налоговый идентификатор голландского налога</span><span class="sxs-lookup"><span data-stu-id="62fcd-661">dutch tax id</span></span>
  
<span data-ttu-id="62fcd-662">идентификационный номер налога на нидерландском языке</span><span class="sxs-lookup"><span data-stu-id="62fcd-662">dutch tax identification number</span></span>
  
<span data-ttu-id="62fcd-663">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-663">tax id</span></span>
  
<span data-ttu-id="62fcd-664">Налоговый код #</span><span class="sxs-lookup"><span data-stu-id="62fcd-664">tax id#</span></span>
  
<span data-ttu-id="62fcd-665">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-665">tax number</span></span>
  
<span data-ttu-id="62fcd-666">налог без #</span><span class="sxs-lookup"><span data-stu-id="62fcd-666">tax no#</span></span>
  
<span data-ttu-id="62fcd-667">см #</span><span class="sxs-lookup"><span data-stu-id="62fcd-667">tax#</span></span>
  
<span data-ttu-id="62fcd-668">ИНН</span><span class="sxs-lookup"><span data-stu-id="62fcd-668">tin</span></span>
  
<span data-ttu-id="62fcd-669">ИНН #</span><span class="sxs-lookup"><span data-stu-id="62fcd-669">tin#</span></span>
  
<span data-ttu-id="62fcd-670">Tin Нидерландов</span><span class="sxs-lookup"><span data-stu-id="62fcd-670">netherlands tin</span></span>
  
<span data-ttu-id="62fcd-671">Tin несерланд</span><span class="sxs-lookup"><span data-stu-id="62fcd-671">netherland's tin</span></span>
  
<span data-ttu-id="62fcd-672">Недерландс идентификатиенуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="62fcd-673">идентификатиенуммер Van</span><span class="sxs-lookup"><span data-stu-id="62fcd-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="62fcd-674">идентификатиенуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="62fcd-675">Недерландс идентификатие</span><span class="sxs-lookup"><span data-stu-id="62fcd-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="62fcd-676">Недерландс — идентификатор нуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="62fcd-677">Недерландс беластингнуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="62fcd-678">БТВ нуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-678">btw nummer</span></span>
  
<span data-ttu-id="62fcd-679">Недерландсе идентификатие</span><span class="sxs-lookup"><span data-stu-id="62fcd-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="62fcd-680">Польша</span><span class="sxs-lookup"><span data-stu-id="62fcd-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-681">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-681">Format</span></span>

<span data-ttu-id="62fcd-682">Одиннадцать цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-683">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-683">Pattern</span></span>

<span data-ttu-id="62fcd-684">Одиннадцать цифр</span><span class="sxs-lookup"><span data-stu-id="62fcd-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62fcd-685">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-685">Checksum</span></span>

<span data-ttu-id="62fcd-686">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-687">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-687">Definition</span></span>

<span data-ttu-id="62fcd-688">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-689">Функция `Func_poland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-690">Найдено ключевое `Keywords_poland_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-691">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-692">Функция `Func_poland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-693">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="62fcd-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-695">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-695">tax number</span></span>
  
<span data-ttu-id="62fcd-696">налог но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-696">tax no.</span></span>
  
<span data-ttu-id="62fcd-697">таксно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-697">taxno#</span></span>
  
<span data-ttu-id="62fcd-698">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="62fcd-698">taxnumber#</span></span>
  
<span data-ttu-id="62fcd-699">такснумбер</span><span class="sxs-lookup"><span data-stu-id="62fcd-699">taxnumber</span></span>
  
<span data-ttu-id="62fcd-700">нип</span><span class="sxs-lookup"><span data-stu-id="62fcd-700">nip</span></span>
  
<span data-ttu-id="62fcd-701">нип #</span><span class="sxs-lookup"><span data-stu-id="62fcd-701">nip#</span></span>
  
<span data-ttu-id="62fcd-702">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-702">tax id</span></span>
  
<span data-ttu-id="62fcd-703">Налоговый код #</span><span class="sxs-lookup"><span data-stu-id="62fcd-703">tax id#</span></span>
  
<span data-ttu-id="62fcd-704">Идентификатор НИП</span><span class="sxs-lookup"><span data-stu-id="62fcd-704">nip id</span></span>
  
<span data-ttu-id="62fcd-705">Идентификатор НИП #</span><span class="sxs-lookup"><span data-stu-id="62fcd-705">nip id#</span></span>
  
<span data-ttu-id="62fcd-706">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="62fcd-706">tax identification number</span></span>
  
<span data-ttu-id="62fcd-707">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="62fcd-707">tax identification no.</span></span>
  
<span data-ttu-id="62fcd-708">номер НДС</span><span class="sxs-lookup"><span data-stu-id="62fcd-708">vat number</span></span>
  
<span data-ttu-id="62fcd-709">НДС номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-709">vat no.</span></span>
  
<span data-ttu-id="62fcd-710">ватно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-710">vatno#</span></span>
  
<span data-ttu-id="62fcd-711">Код НДС</span><span class="sxs-lookup"><span data-stu-id="62fcd-711">vat id</span></span>
  
<span data-ttu-id="62fcd-712">Код НДС #</span><span class="sxs-lookup"><span data-stu-id="62fcd-712">vat id#</span></span>
  
<span data-ttu-id="62fcd-713">Нумер идентификакжи податковеж</span><span class="sxs-lookup"><span data-stu-id="62fcd-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="62fcd-714">полски нумер идентификакжи податковеж</span><span class="sxs-lookup"><span data-stu-id="62fcd-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="62fcd-715">нумеридентификакжиподатковеж #</span><span class="sxs-lookup"><span data-stu-id="62fcd-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="62fcd-716">Португалия</span><span class="sxs-lookup"><span data-stu-id="62fcd-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-717">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-717">Format</span></span>

<span data-ttu-id="62fcd-718">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-719">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-719">Pattern</span></span>

<span data-ttu-id="62fcd-720">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62fcd-721">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-721">Checksum</span></span>

<span data-ttu-id="62fcd-722">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-723">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-723">Definition</span></span>

<span data-ttu-id="62fcd-724">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-725">Функция `Func_portugal_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-726">Найдено ключевое `Keywords_portugal_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-727">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-728">Функция `Func_portugal_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-729">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="62fcd-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-731">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-731">tax number</span></span>
  
<span data-ttu-id="62fcd-732">налог но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-732">tax no.</span></span>
  
<span data-ttu-id="62fcd-733">таксно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-733">taxno#</span></span>
  
<span data-ttu-id="62fcd-734">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="62fcd-734">taxnumber#</span></span>
  
<span data-ttu-id="62fcd-735">такснумбер</span><span class="sxs-lookup"><span data-stu-id="62fcd-735">taxnumber</span></span>
  
<span data-ttu-id="62fcd-736">включена</span><span class="sxs-lookup"><span data-stu-id="62fcd-736">nif</span></span>
  
<span data-ttu-id="62fcd-737">включена #</span><span class="sxs-lookup"><span data-stu-id="62fcd-737">nif#</span></span>
  
<span data-ttu-id="62fcd-738">финансовый нумеро</span><span class="sxs-lookup"><span data-stu-id="62fcd-738">numero fiscal</span></span>
  
<span data-ttu-id="62fcd-739">нúмеро de идентификаçãо Фин.</span><span class="sxs-lookup"><span data-stu-id="62fcd-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="62fcd-740">Румыния</span><span class="sxs-lookup"><span data-stu-id="62fcd-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-741">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-741">Format</span></span>

<span data-ttu-id="62fcd-742">13 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-743">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-743">Pattern</span></span>

<span data-ttu-id="62fcd-744">13 цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62fcd-745">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-745">Checksum</span></span>

<span data-ttu-id="62fcd-746">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="62fcd-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-747">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-747">Definition</span></span>

<span data-ttu-id="62fcd-748">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-749">Регулярное выражение `Regex_romania_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-750">Найдено ключевое `Keywords_romania_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-751">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="62fcd-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-753">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-753">tax id</span></span>
  
<span data-ttu-id="62fcd-754">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="62fcd-754">tax id number</span></span>
  
<span data-ttu-id="62fcd-755">Налоговый файл нет</span><span class="sxs-lookup"><span data-stu-id="62fcd-755">tax file no</span></span>
  
<span data-ttu-id="62fcd-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="62fcd-756">tax file number</span></span>
  
<span data-ttu-id="62fcd-757">налог без</span><span class="sxs-lookup"><span data-stu-id="62fcd-757">tax no</span></span>
  
<span data-ttu-id="62fcd-758">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-758">tax number</span></span>
  
<span data-ttu-id="62fcd-759">такси #</span><span class="sxs-lookup"><span data-stu-id="62fcd-759">taxid#</span></span>
  
<span data-ttu-id="62fcd-760">таксно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-760">taxno#</span></span>
  
<span data-ttu-id="62fcd-761">ID — UL таксеи</span><span class="sxs-lookup"><span data-stu-id="62fcd-761">id-ul taxei</span></span>
  
<span data-ttu-id="62fcd-762">нумăрул де идентификаре фискалă</span><span class="sxs-lookup"><span data-stu-id="62fcd-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="62fcd-763">Словакия</span><span class="sxs-lookup"><span data-stu-id="62fcd-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-764">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-764">Format</span></span>

<span data-ttu-id="62fcd-765">10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-766">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-766">Pattern</span></span>

<span data-ttu-id="62fcd-767">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62fcd-768">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-768">Checksum</span></span>

<span data-ttu-id="62fcd-769">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="62fcd-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-770">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-770">Definition</span></span>

<span data-ttu-id="62fcd-771">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-772">Регулярное выражение `Regex_slovakia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-773">Найдено ключевое `Keywords_slovakia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-774">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="62fcd-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-776">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-776">tax id</span></span>
  
<span data-ttu-id="62fcd-777">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="62fcd-777">tax id number</span></span>
  
<span data-ttu-id="62fcd-778">Идентификатор Tin</span><span class="sxs-lookup"><span data-stu-id="62fcd-778">tin id</span></span>
  
<span data-ttu-id="62fcd-779">номер Tin</span><span class="sxs-lookup"><span data-stu-id="62fcd-779">tin no</span></span>
  
<span data-ttu-id="62fcd-780">Идентификатор Tin словакиан</span><span class="sxs-lookup"><span data-stu-id="62fcd-780">slovakian tin id</span></span>
  
<span data-ttu-id="62fcd-781">ИНН</span><span class="sxs-lookup"><span data-stu-id="62fcd-781">tin</span></span>
  
<span data-ttu-id="62fcd-782">Налоговый файл нет</span><span class="sxs-lookup"><span data-stu-id="62fcd-782">tax file no</span></span>
  
<span data-ttu-id="62fcd-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="62fcd-783">tax file number</span></span>
  
<span data-ttu-id="62fcd-784">налог без</span><span class="sxs-lookup"><span data-stu-id="62fcd-784">tax no</span></span>
  
<span data-ttu-id="62fcd-785">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-785">tax number</span></span>
  
<span data-ttu-id="62fcd-786">такси #</span><span class="sxs-lookup"><span data-stu-id="62fcd-786">taxid#</span></span>
  
<span data-ttu-id="62fcd-787">таксно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-787">taxno#</span></span>
  
<span data-ttu-id="62fcd-788">даňовé идентификаčнé číсло</span><span class="sxs-lookup"><span data-stu-id="62fcd-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="62fcd-789">даňовé číсло</span><span class="sxs-lookup"><span data-stu-id="62fcd-789">daňové číslo</span></span>
  
<span data-ttu-id="62fcd-790">даňовé číсло сúбору</span><span class="sxs-lookup"><span data-stu-id="62fcd-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="62fcd-791">Словения</span><span class="sxs-lookup"><span data-stu-id="62fcd-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-792">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-792">Format</span></span>

<span data-ttu-id="62fcd-793">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-794">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-794">Pattern</span></span>

<span data-ttu-id="62fcd-795">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62fcd-796">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-796">Checksum</span></span>

<span data-ttu-id="62fcd-797">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-798">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-798">Definition</span></span>

<span data-ttu-id="62fcd-799">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-800">Функция `Func_slovenia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-801">Найдено ключевое `Keywords_slovenia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-802">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-803">Функция `Func_slovenia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-804">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="62fcd-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-806">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-806">tax id</span></span>
  
<span data-ttu-id="62fcd-807">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="62fcd-807">tax id number</span></span>
  
<span data-ttu-id="62fcd-808">Идентификатор Tin</span><span class="sxs-lookup"><span data-stu-id="62fcd-808">tin id</span></span>
  
<span data-ttu-id="62fcd-809">номер Tin</span><span class="sxs-lookup"><span data-stu-id="62fcd-809">tin no</span></span>
  
<span data-ttu-id="62fcd-810">Словенский идентификатор Tin</span><span class="sxs-lookup"><span data-stu-id="62fcd-810">slovenian tin id</span></span>
  
<span data-ttu-id="62fcd-811">ИНН</span><span class="sxs-lookup"><span data-stu-id="62fcd-811">tin</span></span>
  
<span data-ttu-id="62fcd-812">Налоговый файл нет</span><span class="sxs-lookup"><span data-stu-id="62fcd-812">tax file no</span></span>
  
<span data-ttu-id="62fcd-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="62fcd-813">tax file number</span></span>
  
<span data-ttu-id="62fcd-814">налог без</span><span class="sxs-lookup"><span data-stu-id="62fcd-814">tax no</span></span>
  
<span data-ttu-id="62fcd-815">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-815">tax number</span></span>
  
<span data-ttu-id="62fcd-816">такси #</span><span class="sxs-lookup"><span data-stu-id="62fcd-816">taxid#</span></span>
  
<span data-ttu-id="62fcd-817">таксно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-817">taxno#</span></span>
  
<span data-ttu-id="62fcd-818">идентификаЦижска šтевилка Давка</span><span class="sxs-lookup"><span data-stu-id="62fcd-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="62fcd-819">давčна šтевилка</span><span class="sxs-lookup"><span data-stu-id="62fcd-819">davčna številka</span></span>
  
<span data-ttu-id="62fcd-820">šтевилка давčне датотеке</span><span class="sxs-lookup"><span data-stu-id="62fcd-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="62fcd-821">Испания</span><span class="sxs-lookup"><span data-stu-id="62fcd-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-822">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-822">Format</span></span>

<span data-ttu-id="62fcd-823">Семь или восемь цифр, а также одна или две буквы в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="62fcd-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-824">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-824">Pattern</span></span>

<span data-ttu-id="62fcd-825">Испанские пользователи с национальной идентификационной карточкой Испании Испания:</span><span class="sxs-lookup"><span data-stu-id="62fcd-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="62fcd-826">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="62fcd-826">Eight digits</span></span> 
    
- <span data-ttu-id="62fcd-827">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="62fcd-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="62fcd-828">Нерезидентские Спаниардс без национальной идентификационной карточки Испании</span><span class="sxs-lookup"><span data-stu-id="62fcd-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="62fcd-829">Одна прописная буква L (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="62fcd-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="62fcd-830">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="62fcd-830">Seven digits</span></span>
    
- <span data-ttu-id="62fcd-831">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="62fcd-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="62fcd-832">Резидентный Спаниардс в течение 14 лет без международной идентификационной карточки для Испании:</span><span class="sxs-lookup"><span data-stu-id="62fcd-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="62fcd-833">Одна прописная буква K (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="62fcd-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="62fcd-834">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="62fcd-834">Seven digits</span></span> 
    
- <span data-ttu-id="62fcd-835">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="62fcd-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="62fcd-836">Фореигнерс с идентификационным номером внешнего получателя</span><span class="sxs-lookup"><span data-stu-id="62fcd-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="62fcd-837">Одна прописная буква "X", "Y" или "Z" (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="62fcd-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="62fcd-838">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="62fcd-838">Seven digits</span></span>
    
- <span data-ttu-id="62fcd-839">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="62fcd-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="62fcd-840">Фореигнерс без идентификационного номера внешнего получателя</span><span class="sxs-lookup"><span data-stu-id="62fcd-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="62fcd-841">Одна прописная буква "M" (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="62fcd-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="62fcd-842">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="62fcd-842">Seven digits</span></span>
    
- <span data-ttu-id="62fcd-843">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="62fcd-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="62fcd-844">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-844">Checksum</span></span>

<span data-ttu-id="62fcd-845">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-846">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-846">Definition</span></span>

<span data-ttu-id="62fcd-847">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-848">Функция `Func_spain_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-849">Найдено ключевое `Keywords_spain_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-850">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-851">Функция `Func_spain_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-852">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="62fcd-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-854">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-854">tax id</span></span>
  
<span data-ttu-id="62fcd-855">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="62fcd-855">tax id number</span></span>
  
<span data-ttu-id="62fcd-856">Идентификатор CIF</span><span class="sxs-lookup"><span data-stu-id="62fcd-856">cif id</span></span>
  
<span data-ttu-id="62fcd-857">CIF нет</span><span class="sxs-lookup"><span data-stu-id="62fcd-857">cif no</span></span>
  
<span data-ttu-id="62fcd-858">код испанского CIF</span><span class="sxs-lookup"><span data-stu-id="62fcd-858">spanish cif id</span></span>
  
<span data-ttu-id="62fcd-859">CIF</span><span class="sxs-lookup"><span data-stu-id="62fcd-859">cif</span></span>
  
<span data-ttu-id="62fcd-860">Налоговый файл нет</span><span class="sxs-lookup"><span data-stu-id="62fcd-860">tax file no</span></span>
  
<span data-ttu-id="62fcd-861">номер испанского CIF</span><span class="sxs-lookup"><span data-stu-id="62fcd-861">spanish cif number</span></span>
  
<span data-ttu-id="62fcd-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="62fcd-862">tax file number</span></span>
  
<span data-ttu-id="62fcd-863">Испанская CIF</span><span class="sxs-lookup"><span data-stu-id="62fcd-863">spanish cif no</span></span>
  
<span data-ttu-id="62fcd-864">налог без</span><span class="sxs-lookup"><span data-stu-id="62fcd-864">tax no</span></span>
  
<span data-ttu-id="62fcd-865">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-865">tax number</span></span>
  
<span data-ttu-id="62fcd-866">такси #</span><span class="sxs-lookup"><span data-stu-id="62fcd-866">taxid#</span></span>
  
<span data-ttu-id="62fcd-867">таксно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-867">taxno#</span></span>
  
<span data-ttu-id="62fcd-868">Цифид #</span><span class="sxs-lookup"><span data-stu-id="62fcd-868">cifid#</span></span>
  
<span data-ttu-id="62fcd-869">спанишЦифид #</span><span class="sxs-lookup"><span data-stu-id="62fcd-869">spanishcifid#</span></span>
  
<span data-ttu-id="62fcd-870">спанишЦифно #</span><span class="sxs-lookup"><span data-stu-id="62fcd-870">spanishcifno#</span></span>
  
<span data-ttu-id="62fcd-871">нúмеро de контрибуйенте</span><span class="sxs-lookup"><span data-stu-id="62fcd-871">número de contribuyente</span></span>
  
<span data-ttu-id="62fcd-872">нúмеро де импуесто корпоративо</span><span class="sxs-lookup"><span data-stu-id="62fcd-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="62fcd-873">нúмеро de идентификаЦиóн Фин.</span><span class="sxs-lookup"><span data-stu-id="62fcd-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="62fcd-874">CIF нúмеро</span><span class="sxs-lookup"><span data-stu-id="62fcd-874">cif número</span></span>
  
<span data-ttu-id="62fcd-875">Цифнúмеро #</span><span class="sxs-lookup"><span data-stu-id="62fcd-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="62fcd-876">Швеция</span><span class="sxs-lookup"><span data-stu-id="62fcd-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-877">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-877">Format</span></span>

<span data-ttu-id="62fcd-878">Десять цифр и символ в указанном шаблоне;</span><span class="sxs-lookup"><span data-stu-id="62fcd-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-879">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-879">Pattern</span></span>

<span data-ttu-id="62fcd-880">Десять цифр и символ:</span><span class="sxs-lookup"><span data-stu-id="62fcd-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="62fcd-881">Шесть цифр, соответствующих дате рождения (ГГММДД)</span><span class="sxs-lookup"><span data-stu-id="62fcd-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="62fcd-882">Знак плюс, знак минус или обратная косая черта</span><span class="sxs-lookup"><span data-stu-id="62fcd-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="62fcd-883">Три цифры, которые делают идентификационный номер уникальным, где:</span><span class="sxs-lookup"><span data-stu-id="62fcd-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="62fcd-884">Для номеров, выпущенных до 1990, седьмой и восьмой цифрой определяют район рождения или пользователей, порожденных иностранным пользователем.</span><span class="sxs-lookup"><span data-stu-id="62fcd-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="62fcd-885">Цифра в девятой позиции указывает на пол, который нечетен для пола или даже для розетки.</span><span class="sxs-lookup"><span data-stu-id="62fcd-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="62fcd-886">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="62fcd-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="62fcd-887">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-887">Checksum</span></span>

<span data-ttu-id="62fcd-888">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-889">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-889">Definition</span></span>

<span data-ttu-id="62fcd-890">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-891">Функция `Func_sweden_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-892">Найдено ключевое `Keywords_sweden_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="62fcd-893">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-894">Функция `Func_sweden_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-895">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="62fcd-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-897">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-897">tax id</span></span>
  
<span data-ttu-id="62fcd-898">Налоговый код но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-898">tax id no.</span></span>
  
<span data-ttu-id="62fcd-899">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="62fcd-899">tax id number</span></span>
  
<span data-ttu-id="62fcd-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="62fcd-900">tax identification</span></span>
  
<span data-ttu-id="62fcd-901">Идентификация налога #</span><span class="sxs-lookup"><span data-stu-id="62fcd-901">tax identification#</span></span>
  
<span data-ttu-id="62fcd-902">налог но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-902">tax no.</span></span>
  
<span data-ttu-id="62fcd-903">см #</span><span class="sxs-lookup"><span data-stu-id="62fcd-903">tax#</span></span>
  
<span data-ttu-id="62fcd-904">такси #</span><span class="sxs-lookup"><span data-stu-id="62fcd-904">taxid#</span></span>
  
<span data-ttu-id="62fcd-905">Налоговый файл</span><span class="sxs-lookup"><span data-stu-id="62fcd-905">tax file</span></span>
  
<span data-ttu-id="62fcd-906">Налоговый файл но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-906">tax file no.</span></span>
  
<span data-ttu-id="62fcd-907">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="62fcd-907">personal id number</span></span>
  
<span data-ttu-id="62fcd-908">Идентификатор СКАТТ нуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-908">skatt id nummer</span></span>
  
<span data-ttu-id="62fcd-909">СКАТТ идентификатион</span><span class="sxs-lookup"><span data-stu-id="62fcd-909">skatt identifikation</span></span>
  
<span data-ttu-id="62fcd-910">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="62fcd-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="62fcd-911">ВОЗМЕЩЕН</span><span class="sxs-lookup"><span data-stu-id="62fcd-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="62fcd-912">Format</span><span class="sxs-lookup"><span data-stu-id="62fcd-912">Format</span></span>

<span data-ttu-id="62fcd-913">Уникальная справочная информация о налогоплательщиках (утр): 10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="62fcd-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="62fcd-914">Национальный страховой номер (Нино): Дополнительные сведения см. в разделе "Великобритания</span><span class="sxs-lookup"><span data-stu-id="62fcd-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="62fcd-915">Национальный страховой номер (Нино) " [, чтобы найти типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="62fcd-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="62fcd-916">Шаблон</span><span class="sxs-lookup"><span data-stu-id="62fcd-916">Pattern</span></span>

<span data-ttu-id="62fcd-917">Уникальная справочная информация о налогоплательщиках (утр): 10 цифр</span><span class="sxs-lookup"><span data-stu-id="62fcd-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="62fcd-918">Национальный страховой номер (Нино): Дополнительные сведения см. в разделе "Великобритания</span><span class="sxs-lookup"><span data-stu-id="62fcd-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="62fcd-919">Национальный страховой номер (Нино) " [, чтобы найти типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="62fcd-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="62fcd-920">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="62fcd-920">Checksum</span></span>

<span data-ttu-id="62fcd-921">Да</span><span class="sxs-lookup"><span data-stu-id="62fcd-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="62fcd-922">Определение</span><span class="sxs-lookup"><span data-stu-id="62fcd-922">Definition</span></span>

<span data-ttu-id="62fcd-923">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="62fcd-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="62fcd-924">Функция `Func_uk_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="62fcd-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="62fcd-925">Найдено ключевое `Keywords_uk_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="62fcd-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="62fcd-926">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="62fcd-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="62fcd-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="62fcd-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="62fcd-928">tax id</span><span class="sxs-lookup"><span data-stu-id="62fcd-928">tax id</span></span>
  
<span data-ttu-id="62fcd-929">Налоговый код но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-929">tax id no.</span></span>
  
<span data-ttu-id="62fcd-930">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="62fcd-930">tax id number</span></span>
  
<span data-ttu-id="62fcd-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="62fcd-931">tax identification</span></span>
  
<span data-ttu-id="62fcd-932">Идентификация налога #</span><span class="sxs-lookup"><span data-stu-id="62fcd-932">tax identification#</span></span>
  
<span data-ttu-id="62fcd-933">налог но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-933">tax no.</span></span>
  
<span data-ttu-id="62fcd-934">см #</span><span class="sxs-lookup"><span data-stu-id="62fcd-934">tax#</span></span>
  
<span data-ttu-id="62fcd-935">такси #</span><span class="sxs-lookup"><span data-stu-id="62fcd-935">taxid#</span></span>
  
<span data-ttu-id="62fcd-936">Налоговый файл</span><span class="sxs-lookup"><span data-stu-id="62fcd-936">tax file</span></span>
  
<span data-ttu-id="62fcd-937">Налоговый файл но.</span><span class="sxs-lookup"><span data-stu-id="62fcd-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="62fcd-938">См. также</span><span class="sxs-lookup"><span data-stu-id="62fcd-938">See also</span></span>

[<span data-ttu-id="62fcd-939">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="62fcd-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

