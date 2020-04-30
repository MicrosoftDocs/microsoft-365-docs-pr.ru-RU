---
title: Идентификационный номер налогоплательщика ЕС
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации для идентификационного номера ЕС. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: 5f779974266045d7099b599700c7168162d9d81e
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938675"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="e6672-104">Идентификационный номер налогоплательщика ЕС</span><span class="sxs-lookup"><span data-stu-id="e6672-104">EU Tax Identification Number</span></span>

<span data-ttu-id="e6672-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации налогоплательщика (TIN).</span><span class="sxs-lookup"><span data-stu-id="e6672-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="e6672-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="e6672-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="e6672-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="e6672-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="e6672-108">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-108">Format</span></span>

<span data-ttu-id="e6672-109">Девять цифр с необязательным дефисом и косой чертой.</span><span class="sxs-lookup"><span data-stu-id="e6672-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-110">Pattern</span></span>

<span data-ttu-id="e6672-111">Девять цифр с необязательным дефисом и косой чертой.</span><span class="sxs-lookup"><span data-stu-id="e6672-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="e6672-112">Две цифры</span><span class="sxs-lookup"><span data-stu-id="e6672-112">Two digits</span></span> 
    
- <span data-ttu-id="e6672-113">Дефис (необязательно)</span><span class="sxs-lookup"><span data-stu-id="e6672-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="e6672-114">Три цифры</span><span class="sxs-lookup"><span data-stu-id="e6672-114">Three digits</span></span>
    
- <span data-ttu-id="e6672-115">Косая черта (необязательно)</span><span class="sxs-lookup"><span data-stu-id="e6672-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="e6672-116">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="e6672-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-117">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-117">Checksum</span></span>

<span data-ttu-id="e6672-118">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-119">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-119">Definition</span></span>

<span data-ttu-id="e6672-120">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-121">Функция `Func_austria_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-122">Найдено ключевое `Keywords_austria_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-123">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-124">Функция `Func_austria_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-125">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="e6672-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-127">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-127">tax number</span></span>
  
<span data-ttu-id="e6672-128">число</span><span class="sxs-lookup"><span data-stu-id="e6672-128">number</span></span>
  
<span data-ttu-id="e6672-129">Регистрационный номер налогоплательщика</span><span class="sxs-lookup"><span data-stu-id="e6672-129">tax registration number</span></span>
  
<span data-ttu-id="e6672-130">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-130">tax id</span></span>
  
<span data-ttu-id="e6672-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="e6672-131">st.nr.</span></span>
  
<span data-ttu-id="e6672-132">стеуернуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="e6672-133">Бельгия</span><span class="sxs-lookup"><span data-stu-id="e6672-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="e6672-134">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-134">Format</span></span>

<span data-ttu-id="e6672-135">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-136">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-136">Pattern</span></span>

<span data-ttu-id="e6672-137">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="e6672-137">11 digits:</span></span>
  
- <span data-ttu-id="e6672-138">Две цифры</span><span class="sxs-lookup"><span data-stu-id="e6672-138">Two digits</span></span>
    
- <span data-ttu-id="e6672-139">"0" или "1"</span><span class="sxs-lookup"><span data-stu-id="e6672-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="e6672-140">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="e6672-140">One digit</span></span>
    
- <span data-ttu-id="e6672-141">"0" или "1" или "2" или "3"</span><span class="sxs-lookup"><span data-stu-id="e6672-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="e6672-142">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-143">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-143">Checksum</span></span>

<span data-ttu-id="e6672-144">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="e6672-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-145">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-145">Definition</span></span>

<span data-ttu-id="e6672-146">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-147">Регулярное выражение `Regex_belgium_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-148">Найдено ключевое `Keywords_belgium_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6672-149">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="e6672-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-151">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-151">tax number</span></span>
  
<span data-ttu-id="e6672-152">Национальный регистрационный номер</span><span class="sxs-lookup"><span data-stu-id="e6672-152">national registration number</span></span>
  
<span data-ttu-id="e6672-153">Регистрационный номер налогоплательщика</span><span class="sxs-lookup"><span data-stu-id="e6672-153">tax registration number</span></span>
  
<span data-ttu-id="e6672-154">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-154">tax id</span></span>
  
<span data-ttu-id="e6672-155">включена</span><span class="sxs-lookup"><span data-stu-id="e6672-155">nif</span></span>
  
<span data-ttu-id="e6672-156">включена #</span><span class="sxs-lookup"><span data-stu-id="e6672-156">nif#</span></span>
  
<span data-ttu-id="e6672-157">нумéро de регистре National</span><span class="sxs-lookup"><span data-stu-id="e6672-157">numéro de registre national</span></span>
  
<span data-ttu-id="e6672-158">нумéро д'идентификатион Фин.</span><span class="sxs-lookup"><span data-stu-id="e6672-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="e6672-159">Болгария</span><span class="sxs-lookup"><span data-stu-id="e6672-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="e6672-160">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-160">Format</span></span>

<span data-ttu-id="e6672-161">Десять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-162">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-162">Pattern</span></span>

<span data-ttu-id="e6672-163">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e6672-164">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-164">Checksum</span></span>

<span data-ttu-id="e6672-165">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-166">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-166">Definition</span></span>

<span data-ttu-id="e6672-167">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-168">Функция `Func_bulgaria_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-169">Найдено ключевое `Keywords_bulgaria_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-170">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-171">Функция `Func_bulgaria_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-172">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="e6672-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-174">букн</span><span class="sxs-lookup"><span data-stu-id="e6672-174">bucn</span></span>
  
<span data-ttu-id="e6672-175">единое гражданское число</span><span class="sxs-lookup"><span data-stu-id="e6672-175">uniform civil number</span></span>
  
<span data-ttu-id="e6672-176">букн #</span><span class="sxs-lookup"><span data-stu-id="e6672-176">bucn#</span></span>
  
<span data-ttu-id="e6672-177">униформЦивилнумбер #</span><span class="sxs-lookup"><span data-stu-id="e6672-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="e6672-178">унифицированный гражданский идентификатор</span><span class="sxs-lookup"><span data-stu-id="e6672-178">uniform civil id</span></span>
  
<span data-ttu-id="e6672-179">равномерный гражданский номер</span><span class="sxs-lookup"><span data-stu-id="e6672-179">uniform civil no</span></span>
  
<span data-ttu-id="e6672-180">егн</span><span class="sxs-lookup"><span data-stu-id="e6672-180">egn</span></span>
  
<span data-ttu-id="e6672-181">номер унифицированного гражданства болгарского языка</span><span class="sxs-lookup"><span data-stu-id="e6672-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="e6672-182">униформЦивилно #</span><span class="sxs-lookup"><span data-stu-id="e6672-182">uniformcivilno#</span></span>
  
<span data-ttu-id="e6672-183">егн #</span><span class="sxs-lookup"><span data-stu-id="e6672-183">egn#</span></span>
  
<span data-ttu-id="e6672-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="e6672-184">униформ граждански номер</span></span>
  
<span data-ttu-id="e6672-185">Идентификатор униформ</span><span class="sxs-lookup"><span data-stu-id="e6672-185">униформ id</span></span>
  
<span data-ttu-id="e6672-186">униформ граждански ID</span><span class="sxs-lookup"><span data-stu-id="e6672-186">униформ граждански id</span></span>
  
<span data-ttu-id="e6672-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="e6672-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="e6672-188">Хорватия</span><span class="sxs-lookup"><span data-stu-id="e6672-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="e6672-189">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-189">Format</span></span>

<span data-ttu-id="e6672-190">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-191">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-191">Pattern</span></span>

<span data-ttu-id="e6672-192">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="e6672-192">11 digits:</span></span>
  
- <span data-ttu-id="e6672-193">Десять цифр, выбран случайным образом</span><span class="sxs-lookup"><span data-stu-id="e6672-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="e6672-194">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="e6672-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-195">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-195">Checksum</span></span>

<span data-ttu-id="e6672-196">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-197">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-197">Definition</span></span>

<span data-ttu-id="e6672-198">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-199">Функция `Func_croatia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-200">Найдено ключевое `Keywords_croatia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-201">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-202">Функция `Func_croatia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-203">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="e6672-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-205">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-205">tax number</span></span>
  
<span data-ttu-id="e6672-206">см</span><span class="sxs-lookup"><span data-stu-id="e6672-206">tax</span></span>
  
<span data-ttu-id="e6672-207">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-207">tax id</span></span>
  
<span data-ttu-id="e6672-208">oid</span><span class="sxs-lookup"><span data-stu-id="e6672-208">oid</span></span>
  
<span data-ttu-id="e6672-209">идентификатора #</span><span class="sxs-lookup"><span data-stu-id="e6672-209">oid#</span></span>
  
<span data-ttu-id="e6672-210">порезни Брож</span><span class="sxs-lookup"><span data-stu-id="e6672-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="e6672-211">Кипр</span><span class="sxs-lookup"><span data-stu-id="e6672-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="e6672-212">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-212">Format</span></span>

<span data-ttu-id="e6672-213">Восемь цифр и одна буква в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="e6672-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-214">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-214">Pattern</span></span>

<span data-ttu-id="e6672-215">Восемь цифр и одна буква:</span><span class="sxs-lookup"><span data-stu-id="e6672-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="e6672-216">"0"</span><span class="sxs-lookup"><span data-stu-id="e6672-216">A "0"</span></span> 
    
- <span data-ttu-id="e6672-217">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="e6672-217">Seven digits</span></span>
    
- <span data-ttu-id="e6672-218">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="e6672-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-219">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-219">Checksum</span></span>

<span data-ttu-id="e6672-220">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="e6672-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-221">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-221">Definition</span></span>

<span data-ttu-id="e6672-222">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-223">Функция `Func_cyprus_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-224">Найдено ключевое `Keywords_cyprus_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-225">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-226">Функция `Func_cyprus_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-227">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="e6672-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-229">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-229">tax number</span></span>
  
<span data-ttu-id="e6672-230">см</span><span class="sxs-lookup"><span data-stu-id="e6672-230">tax</span></span>
  
<span data-ttu-id="e6672-231">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-231">tax id</span></span>
  
<span data-ttu-id="e6672-232">Налоговый код идентификации</span><span class="sxs-lookup"><span data-stu-id="e6672-232">tax identification code</span></span>
  
<span data-ttu-id="e6672-233">тик</span><span class="sxs-lookup"><span data-stu-id="e6672-233">tic</span></span>
  
<span data-ttu-id="e6672-234">тик #</span><span class="sxs-lookup"><span data-stu-id="e6672-234">tic#</span></span>
  
<span data-ttu-id="e6672-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="e6672-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="e6672-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="e6672-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="e6672-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="e6672-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="e6672-238">Чехия</span><span class="sxs-lookup"><span data-stu-id="e6672-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="e6672-239">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-239">Format</span></span>

<span data-ttu-id="e6672-240">Девять или десять цифр с необязательной обратной косой чертой</span><span class="sxs-lookup"><span data-stu-id="e6672-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-241">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-241">Pattern</span></span>

<span data-ttu-id="e6672-242">Девять или десять цифр с необязательной обратной косой чертой.</span><span class="sxs-lookup"><span data-stu-id="e6672-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="e6672-243">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="e6672-243">Six digits</span></span> 
    
- <span data-ttu-id="e6672-244">Обратная косая черта (необязательно)</span><span class="sxs-lookup"><span data-stu-id="e6672-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="e6672-245">Три или четыре цифры</span><span class="sxs-lookup"><span data-stu-id="e6672-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-246">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-246">Checksum</span></span>

<span data-ttu-id="e6672-247">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="e6672-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-248">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-248">Definition</span></span>

<span data-ttu-id="e6672-249">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-250">Регулярное выражение `Regex_czech_republic_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-251">Найдено ключевое `Keywords_czech_republic_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6672-252">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="e6672-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-254">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-254">tax number</span></span>
  
<span data-ttu-id="e6672-255">см</span><span class="sxs-lookup"><span data-stu-id="e6672-255">tax</span></span>
  
<span data-ttu-id="e6672-256">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-256">tax id</span></span>
  
<span data-ttu-id="e6672-257">персональный номер</span><span class="sxs-lookup"><span data-stu-id="e6672-257">personal number</span></span>
  
<span data-ttu-id="e6672-258">даňовé číсло</span><span class="sxs-lookup"><span data-stu-id="e6672-258">daňové číslo</span></span>
  
<span data-ttu-id="e6672-259">особнí číсло</span><span class="sxs-lookup"><span data-stu-id="e6672-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="e6672-260">Дания</span><span class="sxs-lookup"><span data-stu-id="e6672-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="e6672-261">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-261">Format</span></span>

<span data-ttu-id="e6672-262">Десять цифр, содержащие дефис</span><span class="sxs-lookup"><span data-stu-id="e6672-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-263">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-263">Pattern</span></span>

<span data-ttu-id="e6672-264">Десять цифр с дефисом:</span><span class="sxs-lookup"><span data-stu-id="e6672-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="e6672-265">Шесть цифр, соответствующих дате рождения (ДДММГГ —)</span><span class="sxs-lookup"><span data-stu-id="e6672-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="e6672-266">дефис;</span><span class="sxs-lookup"><span data-stu-id="e6672-266">A hyphen</span></span>
    
- <span data-ttu-id="e6672-267">Четыре цифры, которые соответствуют порядковому номеру, где первая цифра соответствует столетию рождения, а последняя цифра соответствует полу лица (нечетный для пола и даже для женщина)</span><span class="sxs-lookup"><span data-stu-id="e6672-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-268">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-268">Checksum</span></span>

<span data-ttu-id="e6672-269">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-270">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-270">Definition</span></span>

<span data-ttu-id="e6672-271">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-272">Функция `Func_denmark_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-273">Найдено ключевое `Keywords_denmark_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-274">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-275">Функция `Func_denmark_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-276">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="e6672-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-278">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-278">tax number</span></span>
  
<span data-ttu-id="e6672-279">см</span><span class="sxs-lookup"><span data-stu-id="e6672-279">tax</span></span>
  
<span data-ttu-id="e6672-280">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-280">tax id</span></span>
  
<span data-ttu-id="e6672-281">CPR Number</span><span class="sxs-lookup"><span data-stu-id="e6672-281">cpr number</span></span>
  
<span data-ttu-id="e6672-282">CPR #</span><span class="sxs-lookup"><span data-stu-id="e6672-282">cpr#</span></span>
  
<span data-ttu-id="e6672-283">Скат нуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-283">skat nummer</span></span>
  
<span data-ttu-id="e6672-284">Идентификатор Скат</span><span class="sxs-lookup"><span data-stu-id="e6672-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="e6672-285">Эстония</span><span class="sxs-lookup"><span data-stu-id="e6672-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="e6672-286">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-286">Format</span></span>

<span data-ttu-id="e6672-287">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-288">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-288">Pattern</span></span>

<span data-ttu-id="e6672-289">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="e6672-289">11 digits:</span></span>
  
-  <span data-ttu-id="e6672-290">Одна цифра, соответствующая пол и столетию рождения, где нечетное число означает "штекер", а четное число указывает на женщина следующим образом: 1, 2 для 19 века; 3, 4 — 20 века; и 5, 6 для 21 века</span><span class="sxs-lookup"><span data-stu-id="e6672-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="e6672-291">Шесть цифр, соответствующих дате рождения (ГГММДД)</span><span class="sxs-lookup"><span data-stu-id="e6672-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="e6672-292">Три цифры, которые соответствуют порядковому номеру, разделенному на одну и ту же дату.</span><span class="sxs-lookup"><span data-stu-id="e6672-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="e6672-293">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="e6672-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-294">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-294">Checksum</span></span>

<span data-ttu-id="e6672-295">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-296">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-296">Definition</span></span>

<span data-ttu-id="e6672-297">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-298">Функция `Func_estonia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-299">Найдено ключевое `Keywords_estonia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-300">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-301">Функция `Func_estonia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-302">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="e6672-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-304">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-304">tax number</span></span>
  
<span data-ttu-id="e6672-305">см</span><span class="sxs-lookup"><span data-stu-id="e6672-305">tax</span></span>
  
<span data-ttu-id="e6672-306">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-306">tax id</span></span>
  
<span data-ttu-id="e6672-307">персональный код</span><span class="sxs-lookup"><span data-stu-id="e6672-307">personal code</span></span>
  
<span data-ttu-id="e6672-308">максунумбер</span><span class="sxs-lookup"><span data-stu-id="e6672-308">maksunumber</span></span>
  
<span data-ttu-id="e6672-309">Идентификатор Максу</span><span class="sxs-lookup"><span data-stu-id="e6672-309">maksu id</span></span>
  
<span data-ttu-id="e6672-310">исикукуд</span><span class="sxs-lookup"><span data-stu-id="e6672-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="e6672-311">Финляндия</span><span class="sxs-lookup"><span data-stu-id="e6672-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="e6672-312">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-312">Format</span></span>

<span data-ttu-id="e6672-313">Сочетание цифр, букв и плюса, а также знак минуса</span><span class="sxs-lookup"><span data-stu-id="e6672-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-314">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-314">Pattern</span></span>

<span data-ttu-id="e6672-315">Сочетание цифр, букв и плюса и знака "плюс" и "минус" (11 символов).</span><span class="sxs-lookup"><span data-stu-id="e6672-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="e6672-316">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="e6672-316">Six digits</span></span>
    
- <span data-ttu-id="e6672-317">Один из следующих элементов: знак плюса, знак минуса или буква "A" (без учета регистра), где знак "плюс" (без учета регистра) означает 1900-1999, что знак "плюс" находится в диапазоне от 1 до 1800-1899, а "A" означает, что порожденный 2000 и после</span><span class="sxs-lookup"><span data-stu-id="e6672-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="e6672-318">Три цифры</span><span class="sxs-lookup"><span data-stu-id="e6672-318">Three digits</span></span>
    
- <span data-ttu-id="e6672-319">Одна буква или один номер</span><span class="sxs-lookup"><span data-stu-id="e6672-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-320">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-320">Checksum</span></span>

<span data-ttu-id="e6672-321">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-322">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-322">Definition</span></span>

<span data-ttu-id="e6672-323">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-324">Функция `Func_finland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-325">Найдено ключевое `Keywords_finland_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-326">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-327">Функция `Func_finland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-328">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="e6672-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-330">identification number</span><span class="sxs-lookup"><span data-stu-id="e6672-330">identification number</span></span>
  
<span data-ttu-id="e6672-331">личный идентификатор</span><span class="sxs-lookup"><span data-stu-id="e6672-331">personal id</span></span>
  
<span data-ttu-id="e6672-332">идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="e6672-332">identity number</span></span>
  
<span data-ttu-id="e6672-333">Финский национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="e6672-333">finnish national id number</span></span>
  
<span data-ttu-id="e6672-334">персоналиднумбер #</span><span class="sxs-lookup"><span data-stu-id="e6672-334">personalidnumber#</span></span>
  
<span data-ttu-id="e6672-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="e6672-335">national identification number</span></span>
  
<span data-ttu-id="e6672-336">идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="e6672-336">id number</span></span>
  
<span data-ttu-id="e6672-337">код страны</span><span class="sxs-lookup"><span data-stu-id="e6672-337">national id no.</span></span>
  
<span data-ttu-id="e6672-338">Национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="e6672-338">national id number</span></span>
  
<span data-ttu-id="e6672-339">ID No</span><span class="sxs-lookup"><span data-stu-id="e6672-339">id no</span></span>
  
<span data-ttu-id="e6672-340">туннистенумеро</span><span class="sxs-lookup"><span data-stu-id="e6672-340">tunnistenumero</span></span>
  
<span data-ttu-id="e6672-341">хенкилöтуннус</span><span class="sxs-lookup"><span data-stu-id="e6672-341">henkilötunnus</span></span>
  
<span data-ttu-id="e6672-342">иксилöллинен хенкилöкохтаинен туннистенумеро</span><span class="sxs-lookup"><span data-stu-id="e6672-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="e6672-343">аинутлаатуинен хенкилöкохтаинен туннус</span><span class="sxs-lookup"><span data-stu-id="e6672-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="e6672-344">идентититти нумеро</span><span class="sxs-lookup"><span data-stu-id="e6672-344">identiteetti numero</span></span>
  
<span data-ttu-id="e6672-345">Суомен кансаллинен хенкилöтуннус</span><span class="sxs-lookup"><span data-stu-id="e6672-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="e6672-346">хенкилöтуннуснумеро #</span><span class="sxs-lookup"><span data-stu-id="e6672-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="e6672-347">кансаллисен туннистенумеро</span><span class="sxs-lookup"><span data-stu-id="e6672-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="e6672-348">туннуснумеро</span><span class="sxs-lookup"><span data-stu-id="e6672-348">tunnusnumero</span></span>
  
<span data-ttu-id="e6672-349">кансаллинен туннус нумеро</span><span class="sxs-lookup"><span data-stu-id="e6672-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="e6672-350">Франция</span><span class="sxs-lookup"><span data-stu-id="e6672-350">France</span></span>

### <a name="format"></a><span data-ttu-id="e6672-351">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-351">Format</span></span>

<span data-ttu-id="e6672-352">13 цифр для отдельных пользователей и девять цифр для сущностей</span><span class="sxs-lookup"><span data-stu-id="e6672-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-353">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-353">Pattern</span></span>

<span data-ttu-id="e6672-354">13 цифр для отдельных пользователей:</span><span class="sxs-lookup"><span data-stu-id="e6672-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="e6672-355">Одна цифра, которая должна быть равна 0, 1, 2 или 3</span><span class="sxs-lookup"><span data-stu-id="e6672-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="e6672-356">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-356">12 digits</span></span>
    
<span data-ttu-id="e6672-357">Девять цифр для сущностей</span><span class="sxs-lookup"><span data-stu-id="e6672-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e6672-358">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-358">Checksum</span></span>

<span data-ttu-id="e6672-359">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="e6672-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-360">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-360">Definition</span></span>

<span data-ttu-id="e6672-361">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-362">Функция `Func_france_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-363">Найдено ключевое `Keywords_france_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-364">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-365">Функция `Func_france_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-366">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="e6672-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-368">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="e6672-368">tax identification number</span></span>
  
<span data-ttu-id="e6672-369">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-369">tax number</span></span>
  
<span data-ttu-id="e6672-370">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-370">tax id</span></span>
  
<span data-ttu-id="e6672-371">нумéро д'идентификатион Фин.</span><span class="sxs-lookup"><span data-stu-id="e6672-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="e6672-372">Германия</span><span class="sxs-lookup"><span data-stu-id="e6672-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="e6672-373">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-373">Format</span></span>

<span data-ttu-id="e6672-374">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-375">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-375">Pattern</span></span>

<span data-ttu-id="e6672-376">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="e6672-376">11 digits :</span></span>
  
-  <span data-ttu-id="e6672-377">Десять цифр</span><span class="sxs-lookup"><span data-stu-id="e6672-377">Ten digits</span></span> 
    
- <span data-ttu-id="e6672-378">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="e6672-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-379">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-379">Checksum</span></span>

<span data-ttu-id="e6672-380">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-381">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-381">Definition</span></span>

<span data-ttu-id="e6672-382">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-383">Функция `Func_germany_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-384">Найдено ключевое `Keywords_germany_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-385">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-386">Функция `Func_germany_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-387">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="e6672-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-389">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-389">tax number</span></span>
  
<span data-ttu-id="e6672-390">налог но.</span><span class="sxs-lookup"><span data-stu-id="e6672-390">tax no.</span></span>
  
<span data-ttu-id="e6672-391">таксно #</span><span class="sxs-lookup"><span data-stu-id="e6672-391">taxno#</span></span>
  
<span data-ttu-id="e6672-392">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="e6672-392">taxnumber#</span></span>
  
<span data-ttu-id="e6672-393">такснумбер</span><span class="sxs-lookup"><span data-stu-id="e6672-393">taxnumber</span></span>
  
<span data-ttu-id="e6672-394">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-394">tax id</span></span>
  
<span data-ttu-id="e6672-395">такси #</span><span class="sxs-lookup"><span data-stu-id="e6672-395">taxid#</span></span>
  
<span data-ttu-id="e6672-396">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="e6672-396">tax identification number</span></span>
  
<span data-ttu-id="e6672-397">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="e6672-397">tax identification no.</span></span>
  
<span data-ttu-id="e6672-398">стеуернуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-398">steuernummer</span></span>
  
<span data-ttu-id="e6672-399">Идентификатор стеуер</span><span class="sxs-lookup"><span data-stu-id="e6672-399">steuer id</span></span>
  
<span data-ttu-id="e6672-400">стеуеридентификатионснуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="e6672-401">Греция</span><span class="sxs-lookup"><span data-stu-id="e6672-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="e6672-402">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-402">Format</span></span>

<span data-ttu-id="e6672-403">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-404">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-404">Pattern</span></span>

<span data-ttu-id="e6672-405">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e6672-406">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-406">Checksum</span></span>

<span data-ttu-id="e6672-407">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="e6672-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-408">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-408">Definition</span></span>

<span data-ttu-id="e6672-409">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-410">Регулярное выражение `Regex_greece_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-411">Найдено ключевое `Keywords_greece_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6672-412">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="e6672-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-414">афм</span><span class="sxs-lookup"><span data-stu-id="e6672-414">afm</span></span>
  
<span data-ttu-id="e6672-415">ИНН</span><span class="sxs-lookup"><span data-stu-id="e6672-415">tin</span></span>
  
<span data-ttu-id="e6672-416">Налоговый код но.</span><span class="sxs-lookup"><span data-stu-id="e6672-416">tax id no.</span></span>
  
<span data-ttu-id="e6672-417">Налоговый код No</span><span class="sxs-lookup"><span data-stu-id="e6672-417">tax id no</span></span>
  
<span data-ttu-id="e6672-418">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="e6672-418">tax identification number</span></span>
  
<span data-ttu-id="e6672-419">Налоговый номер реестра</span><span class="sxs-lookup"><span data-stu-id="e6672-419">tax registry number</span></span>
  
<span data-ttu-id="e6672-420">реестр по номеру налога</span><span class="sxs-lookup"><span data-stu-id="e6672-420">tax registry no.</span></span>
  
<span data-ttu-id="e6672-421">афм #</span><span class="sxs-lookup"><span data-stu-id="e6672-421">afm#</span></span>
  
<span data-ttu-id="e6672-422">ИНН #</span><span class="sxs-lookup"><span data-stu-id="e6672-422">tin#</span></span>
  
<span data-ttu-id="e6672-423">таксидно #</span><span class="sxs-lookup"><span data-stu-id="e6672-423">taxidno#</span></span>
  
<span data-ttu-id="e6672-424">таксрегистрино #</span><span class="sxs-lookup"><span data-stu-id="e6672-424">taxregistryno#</span></span>
  
<span data-ttu-id="e6672-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="e6672-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="e6672-426">аφμ</span><span class="sxs-lookup"><span data-stu-id="e6672-426">aφμ</span></span>
  
<span data-ttu-id="e6672-427">аφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="e6672-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="e6672-428">φορολογικού μητρώου Νο.</span><span class="sxs-lookup"><span data-stu-id="e6672-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="e6672-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="e6672-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="e6672-430">Венгрия</span><span class="sxs-lookup"><span data-stu-id="e6672-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="e6672-431">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-431">Format</span></span>

<span data-ttu-id="e6672-432">Десять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-433">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-433">Pattern</span></span>

<span data-ttu-id="e6672-434">Десять цифр:</span><span class="sxs-lookup"><span data-stu-id="e6672-434">Ten digits:</span></span>
  
-  <span data-ttu-id="e6672-435">Одна цифра, которая должна быть "8"</span><span class="sxs-lookup"><span data-stu-id="e6672-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="e6672-436">Пять цифр, которые соответствуют количеству дней между датой 01/01/1867 и датой рождения отдельного лица.</span><span class="sxs-lookup"><span data-stu-id="e6672-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="e6672-437">Три цифры, которые соответствуют номеру, созданному шансом выделить людей, которые поставили один и тот же день.</span><span class="sxs-lookup"><span data-stu-id="e6672-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="e6672-438">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="e6672-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-439">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-439">Checksum</span></span>

<span data-ttu-id="e6672-440">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-441">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-441">Definition</span></span>

<span data-ttu-id="e6672-442">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-443">Функция `Func_hungary_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-444">Найдено ключевое `Keywords_hungary_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-445">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-446">Функция `Func_hungary_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-447">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="e6672-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-449">идентификационный номер для венгерского налога</span><span class="sxs-lookup"><span data-stu-id="e6672-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="e6672-450">Венгерский Tin</span><span class="sxs-lookup"><span data-stu-id="e6672-450">hungarian tin</span></span>
  
<span data-ttu-id="e6672-451">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="e6672-451">tax id number</span></span>
  
<span data-ttu-id="e6672-452">номер НДС</span><span class="sxs-lookup"><span data-stu-id="e6672-452">vat number</span></span>
  
<span data-ttu-id="e6672-453">Налоговый орган без</span><span class="sxs-lookup"><span data-stu-id="e6672-453">tax authority no</span></span>
  
<span data-ttu-id="e6672-454">идентификационный номер налогоплательщика для налогового кода</span><span class="sxs-lookup"><span data-stu-id="e6672-454">tax id tax identity number</span></span>
  
<span data-ttu-id="e6672-455">таксиднумбер #</span><span class="sxs-lookup"><span data-stu-id="e6672-455">taxidnumber#</span></span>
  
<span data-ttu-id="e6672-456">ИНН #</span><span class="sxs-lookup"><span data-stu-id="e6672-456">tin#</span></span>
  
<span data-ttu-id="e6672-457">хунгатиантин #</span><span class="sxs-lookup"><span data-stu-id="e6672-457">hungatiantin#</span></span>
  
<span data-ttu-id="e6672-458">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="e6672-458">tax identification no</span></span>
  
<span data-ttu-id="e6672-459">таксидно #</span><span class="sxs-lookup"><span data-stu-id="e6672-459">taxidno#</span></span>
  
<span data-ttu-id="e6672-460">адóазоносíтó сзáм</span><span class="sxs-lookup"><span data-stu-id="e6672-460">adóazonosító szám</span></span>
  
<span data-ttu-id="e6672-461">адóсзáм</span><span class="sxs-lookup"><span data-stu-id="e6672-461">adószám</span></span>
  
<span data-ttu-id="e6672-462">адóхатóсáг сзáм</span><span class="sxs-lookup"><span data-stu-id="e6672-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="e6672-463">Ирландия</span><span class="sxs-lookup"><span data-stu-id="e6672-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="e6672-464">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-464">Format</span></span>

<span data-ttu-id="e6672-465">Семь цифр, за которыми следует буква без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-466">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-466">Pattern</span></span>

<span data-ttu-id="e6672-467">Семь цифр, за которыми следует буква:</span><span class="sxs-lookup"><span data-stu-id="e6672-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="e6672-468">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="e6672-468">Seven digits</span></span> 
    
- <span data-ttu-id="e6672-469">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="e6672-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-470">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-470">Checksum</span></span>

<span data-ttu-id="e6672-471">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="e6672-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-472">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-472">Definition</span></span>

<span data-ttu-id="e6672-473">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-474">Функция `Func_ireland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-475">Найдено ключевое `Keywords_ireland_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-476">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-477">Функция `Func_ireland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-478">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="e6672-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-480">общедоступная служба</span><span class="sxs-lookup"><span data-stu-id="e6672-480">public service no</span></span>
  
<span data-ttu-id="e6672-481">Личная общедоступная служба</span><span class="sxs-lookup"><span data-stu-id="e6672-481">personal public service no</span></span>
  
<span data-ttu-id="e6672-482">PPS нет</span><span class="sxs-lookup"><span data-stu-id="e6672-482">pps no</span></span>
  
<span data-ttu-id="e6672-483">Личная служба</span><span class="sxs-lookup"><span data-stu-id="e6672-483">personal service no</span></span>
  
<span data-ttu-id="e6672-484">Служба PPS нет</span><span class="sxs-lookup"><span data-stu-id="e6672-484">pps service no</span></span>
  
<span data-ttu-id="e6672-485">ппсно #</span><span class="sxs-lookup"><span data-stu-id="e6672-485">ppsno#</span></span>
  
<span data-ttu-id="e6672-486">Ирландский PPS No</span><span class="sxs-lookup"><span data-stu-id="e6672-486">irish pps no</span></span>
  
<span data-ttu-id="e6672-487">публиксервицено #</span><span class="sxs-lookup"><span data-stu-id="e6672-487">publicserviceno#</span></span>
  
<span data-ttu-id="e6672-488">номер личной общедоступной службы</span><span class="sxs-lookup"><span data-stu-id="e6672-488">personal public service number</span></span>
  
<span data-ttu-id="e6672-489">уимхир феарсанта сеирбхíсе поиблí</span><span class="sxs-lookup"><span data-stu-id="e6672-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="e6672-490">PPS уимх</span><span class="sxs-lookup"><span data-stu-id="e6672-490">pps uimh</span></span>
  
<span data-ttu-id="e6672-491">уимхир аисеантаис феарсанта</span><span class="sxs-lookup"><span data-stu-id="e6672-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="e6672-492">Италия</span><span class="sxs-lookup"><span data-stu-id="e6672-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="e6672-493">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-493">Format</span></span>

<span data-ttu-id="e6672-494">16 букв и цифр в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="e6672-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-495">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-495">Pattern</span></span>

<span data-ttu-id="e6672-496">16 букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="e6672-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="e6672-497">Три буквы, соответствующие первым трем согласным в имени семейства</span><span class="sxs-lookup"><span data-stu-id="e6672-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="e6672-498">Три буквы, соответствующие первым, третьим и четвертым согласным в имени.</span><span class="sxs-lookup"><span data-stu-id="e6672-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="e6672-499">Две цифры, соответствующие последним цифрам года рождения</span><span class="sxs-lookup"><span data-stu-id="e6672-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="e6672-500">Одна цифра, соответствующая месяцу рождения, буквы используются в алфавитном порядке, но используются только буквы от A до E, H, L, M, P, R — T (то есть Январь — это R, а Октябрь — R)</span><span class="sxs-lookup"><span data-stu-id="e6672-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="e6672-501">Две цифры, которые соответствуют дню рождения, где 40 добавляется к дню рождения женщин, чтобы отличать от мужчин</span><span class="sxs-lookup"><span data-stu-id="e6672-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="e6672-502">Четыре цифры, соответствующие коду города, соответствующему органу государственной власти, в котором был создан пользователь, — коды уровня страны используются для иностранных стран</span><span class="sxs-lookup"><span data-stu-id="e6672-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="e6672-503">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="e6672-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-504">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-504">Checksum</span></span>

<span data-ttu-id="e6672-505">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-506">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-506">Definition</span></span>

<span data-ttu-id="e6672-507">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-508">Функция `Func_italy_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-509">Найдено ключевое `Keywords_italy_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-510">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-511">Функция `Func_italy_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-512">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="e6672-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-514">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-514">tax number</span></span>
  
<span data-ttu-id="e6672-515">налог но.</span><span class="sxs-lookup"><span data-stu-id="e6672-515">tax no.</span></span>
  
<span data-ttu-id="e6672-516">таксно #</span><span class="sxs-lookup"><span data-stu-id="e6672-516">taxno#</span></span>
  
<span data-ttu-id="e6672-517">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="e6672-517">taxnumber#</span></span>
  
<span data-ttu-id="e6672-518">такснумбер</span><span class="sxs-lookup"><span data-stu-id="e6672-518">taxnumber</span></span>
  
<span data-ttu-id="e6672-519">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-519">tax id</span></span>
  
<span data-ttu-id="e6672-520">такси #</span><span class="sxs-lookup"><span data-stu-id="e6672-520">taxid#</span></span>
  
<span data-ttu-id="e6672-521">Финансовый код</span><span class="sxs-lookup"><span data-stu-id="e6672-521">fiscal code</span></span>
  
<span data-ttu-id="e6672-522">финансовый отчет по сокостям</span><span class="sxs-lookup"><span data-stu-id="e6672-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="e6672-523">Латвия</span><span class="sxs-lookup"><span data-stu-id="e6672-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="e6672-524">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-524">Format</span></span>

<span data-ttu-id="e6672-525">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-526">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-526">Pattern</span></span>

<span data-ttu-id="e6672-527">11 цифр в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="e6672-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="e6672-528">Шесть цифр, соответствующих дате рождения (ДДММГГ —)</span><span class="sxs-lookup"><span data-stu-id="e6672-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="e6672-529">Одна цифра, соответствующая столетию рождения, где "0" соответствует 19 века, "1" соответствует 20 столетию, а "2" соответствует 21 столетию</span><span class="sxs-lookup"><span data-stu-id="e6672-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="e6672-530">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="e6672-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-531">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-531">Checksum</span></span>

<span data-ttu-id="e6672-532">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-533">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-533">Definition</span></span>

<span data-ttu-id="e6672-534">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-535">Функция `Func_latvia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-536">Найдено ключевое `Keywords_latvia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-537">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-538">Функция `Func_latvia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-539">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="e6672-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-541">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-541">tax number</span></span>
  
<span data-ttu-id="e6672-542">налог но.</span><span class="sxs-lookup"><span data-stu-id="e6672-542">tax no.</span></span>
  
<span data-ttu-id="e6672-543">таксно #</span><span class="sxs-lookup"><span data-stu-id="e6672-543">taxno#</span></span>
  
<span data-ttu-id="e6672-544">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="e6672-544">taxnumber#</span></span>
  
<span data-ttu-id="e6672-545">такснумбер</span><span class="sxs-lookup"><span data-stu-id="e6672-545">taxnumber</span></span>
  
<span data-ttu-id="e6672-546">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-546">tax id</span></span>
  
<span data-ttu-id="e6672-547">такси #</span><span class="sxs-lookup"><span data-stu-id="e6672-547">taxid#</span></span>
  
<span data-ttu-id="e6672-548">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="e6672-548">tax identification number</span></span>
  
<span data-ttu-id="e6672-549">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="e6672-549">tax identification no.</span></span>
  
<span data-ttu-id="e6672-550">нодокļа нумурс</span><span class="sxs-lookup"><span data-stu-id="e6672-550">nodokļa numurs</span></span>
  
<span data-ttu-id="e6672-551">нодокļу идентификāЦижас нумурс</span><span class="sxs-lookup"><span data-stu-id="e6672-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="e6672-552">нодокļу идентификāЦижа нумурс</span><span class="sxs-lookup"><span data-stu-id="e6672-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="e6672-553">Литва</span><span class="sxs-lookup"><span data-stu-id="e6672-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="e6672-554">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-554">Format</span></span>

<span data-ttu-id="e6672-555">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-556">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-556">Pattern</span></span>

<span data-ttu-id="e6672-557">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e6672-558">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-558">Checksum</span></span>

<span data-ttu-id="e6672-559">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="e6672-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-560">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-560">Definition</span></span>

<span data-ttu-id="e6672-561">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-562">Функция `Func_lithuania_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-563">Найдено ключевое `Keywords_lithuania_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-564">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-565">Функция `Func_lithuania_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-566">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="e6672-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-568">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-568">tax number</span></span>
  
<span data-ttu-id="e6672-569">налог но.</span><span class="sxs-lookup"><span data-stu-id="e6672-569">tax no.</span></span>
  
<span data-ttu-id="e6672-570">налог без #</span><span class="sxs-lookup"><span data-stu-id="e6672-570">tax no#</span></span>
  
<span data-ttu-id="e6672-571">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="e6672-571">taxnumber#</span></span>
  
<span data-ttu-id="e6672-572">такснумбер</span><span class="sxs-lookup"><span data-stu-id="e6672-572">taxnumber</span></span>
  
<span data-ttu-id="e6672-573">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-573">tax id</span></span>
  
<span data-ttu-id="e6672-574">такси #</span><span class="sxs-lookup"><span data-stu-id="e6672-574">taxid#</span></span>
  
<span data-ttu-id="e6672-575">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="e6672-575">tax identification number</span></span>
  
<span data-ttu-id="e6672-576">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="e6672-576">tax identification no.</span></span>
  
<span data-ttu-id="e6672-577">Идентификатор мокесčиų</span><span class="sxs-lookup"><span data-stu-id="e6672-577">mokesčių id</span></span>
  
<span data-ttu-id="e6672-578">мокесčиų нумерис</span><span class="sxs-lookup"><span data-stu-id="e6672-578">mokesčių numeris</span></span>
  
<span data-ttu-id="e6672-579">мокесčиų идентификавимас нумерис</span><span class="sxs-lookup"><span data-stu-id="e6672-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="e6672-580">луксембург</span><span class="sxs-lookup"><span data-stu-id="e6672-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="e6672-581">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-581">Format</span></span>

<span data-ttu-id="e6672-582">13 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-583">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-583">Pattern</span></span>

<span data-ttu-id="e6672-584">13 цифр:</span><span class="sxs-lookup"><span data-stu-id="e6672-584">13 digits:</span></span>
  
-  <span data-ttu-id="e6672-585">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-585">11 digits</span></span> 
    
- <span data-ttu-id="e6672-586">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="e6672-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-587">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-587">Checksum</span></span>

<span data-ttu-id="e6672-588">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-589">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-589">Definition</span></span>

<span data-ttu-id="e6672-590">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-591">Функция `Func_luxemburg_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-592">Найдено ключевое `Keywords_luxemburg_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-593">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-594">Функция `Func_luxemburg_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-595">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="e6672-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-597">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-597">tax number</span></span>
  
<span data-ttu-id="e6672-598">налог но.</span><span class="sxs-lookup"><span data-stu-id="e6672-598">tax no.</span></span>
  
<span data-ttu-id="e6672-599">таксно #</span><span class="sxs-lookup"><span data-stu-id="e6672-599">taxno#</span></span>
  
<span data-ttu-id="e6672-600">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="e6672-600">taxnumber#</span></span>
  
<span data-ttu-id="e6672-601">такснумбер</span><span class="sxs-lookup"><span data-stu-id="e6672-601">taxnumber</span></span>
  
<span data-ttu-id="e6672-602">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-602">tax id</span></span>
  
<span data-ttu-id="e6672-603">такси #</span><span class="sxs-lookup"><span data-stu-id="e6672-603">taxid#</span></span>
  
<span data-ttu-id="e6672-604">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="e6672-604">tax identification number</span></span>
  
<span data-ttu-id="e6672-605">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="e6672-605">tax identification no.</span></span>
  
<span data-ttu-id="e6672-606">стеуернуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-606">steuernummer</span></span>
  
<span data-ttu-id="e6672-607">Идентификатор стеуер</span><span class="sxs-lookup"><span data-stu-id="e6672-607">steuer id</span></span>
  
<span data-ttu-id="e6672-608">стеуеридентификатионснуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="e6672-609">Мальта</span><span class="sxs-lookup"><span data-stu-id="e6672-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="e6672-610">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-610">Format</span></span>

<span data-ttu-id="e6672-611">Для национальных замальтийский: 7 цифр и одна буква в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="e6672-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="e6672-612">Мальтийскийные страны и Мальтийский, не являющиеся субъектами: 9 цифр</span><span class="sxs-lookup"><span data-stu-id="e6672-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-613">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-613">Pattern</span></span>

<span data-ttu-id="e6672-614">Мальтийский национальные условия: 7 цифр и одна буква</span><span class="sxs-lookup"><span data-stu-id="e6672-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="e6672-615">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="e6672-615">Seven digits</span></span> 
    
- <span data-ttu-id="e6672-616">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="e6672-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="e6672-617">Мальтийскийные страны и Мальтийский, не являющиеся субъектами: 9 цифр</span><span class="sxs-lookup"><span data-stu-id="e6672-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="e6672-618">девять цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e6672-619">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-619">Checksum</span></span>

<span data-ttu-id="e6672-620">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="e6672-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-621">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-621">Definition</span></span>

<span data-ttu-id="e6672-622">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-623">Функция `Func_malta_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-624">Найдено ключевое `Keywords_malta_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-625">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-626">Функция `Func_malta_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-627">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="e6672-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-629">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-629">tax number</span></span>
  
<span data-ttu-id="e6672-630">налог но.</span><span class="sxs-lookup"><span data-stu-id="e6672-630">tax no.</span></span>
  
<span data-ttu-id="e6672-631">таксно #</span><span class="sxs-lookup"><span data-stu-id="e6672-631">taxno#</span></span>
  
<span data-ttu-id="e6672-632">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="e6672-632">taxnumber#</span></span>
  
<span data-ttu-id="e6672-633">такснумбер</span><span class="sxs-lookup"><span data-stu-id="e6672-633">taxnumber</span></span>
  
<span data-ttu-id="e6672-634">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-634">tax id</span></span>
  
<span data-ttu-id="e6672-635">такси #</span><span class="sxs-lookup"><span data-stu-id="e6672-635">taxid#</span></span>
  
<span data-ttu-id="e6672-636">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="e6672-636">tax identification number</span></span>
  
<span data-ttu-id="e6672-637">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="e6672-637">tax identification no.</span></span>
  
<span data-ttu-id="e6672-638">нумру ТАТ — такскса</span><span class="sxs-lookup"><span data-stu-id="e6672-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="e6672-639">ID ТАТ — такскса</span><span class="sxs-lookup"><span data-stu-id="e6672-639">id tat-taxxa</span></span>
  
<span data-ttu-id="e6672-640">нумру Ta ' идентификаззжони ТАТ такскса</span><span class="sxs-lookup"><span data-stu-id="e6672-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="e6672-641">Нидерланды</span><span class="sxs-lookup"><span data-stu-id="e6672-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="e6672-642">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-642">Format</span></span>

<span data-ttu-id="e6672-643">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-644">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-644">Pattern</span></span>

<span data-ttu-id="e6672-645">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e6672-646">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-646">Checksum</span></span>

<span data-ttu-id="e6672-647">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-648">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-648">Definition</span></span>

<span data-ttu-id="e6672-649">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-650">Функция `Func_netherlands_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-651">Найдено ключевое `Keywords_netherlands_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-652">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-653">Функция `Func_netherlands_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-654">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="e6672-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-656">идентификационный номер налога Нидерландов</span><span class="sxs-lookup"><span data-stu-id="e6672-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="e6672-657">Идентификация налога Нидерландов</span><span class="sxs-lookup"><span data-stu-id="e6672-657">netherlands tax identification</span></span>
  
<span data-ttu-id="e6672-658">идентификационный номер налога несерланд</span><span class="sxs-lookup"><span data-stu-id="e6672-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="e6672-659">Налоговый код несерланд</span><span class="sxs-lookup"><span data-stu-id="e6672-659">netherland's tax identification</span></span>
  
<span data-ttu-id="e6672-660">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="e6672-660">tax identification number</span></span>
  
<span data-ttu-id="e6672-661">Налоговый идентификатор голландского налога</span><span class="sxs-lookup"><span data-stu-id="e6672-661">dutch tax id</span></span>
  
<span data-ttu-id="e6672-662">идентификационный номер налога на нидерландском языке</span><span class="sxs-lookup"><span data-stu-id="e6672-662">dutch tax identification number</span></span>
  
<span data-ttu-id="e6672-663">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-663">tax id</span></span>
  
<span data-ttu-id="e6672-664">Налоговый код #</span><span class="sxs-lookup"><span data-stu-id="e6672-664">tax id#</span></span>
  
<span data-ttu-id="e6672-665">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-665">tax number</span></span>
  
<span data-ttu-id="e6672-666">налог без #</span><span class="sxs-lookup"><span data-stu-id="e6672-666">tax no#</span></span>
  
<span data-ttu-id="e6672-667">см #</span><span class="sxs-lookup"><span data-stu-id="e6672-667">tax#</span></span>
  
<span data-ttu-id="e6672-668">ИНН</span><span class="sxs-lookup"><span data-stu-id="e6672-668">tin</span></span>
  
<span data-ttu-id="e6672-669">ИНН #</span><span class="sxs-lookup"><span data-stu-id="e6672-669">tin#</span></span>
  
<span data-ttu-id="e6672-670">Tin Нидерландов</span><span class="sxs-lookup"><span data-stu-id="e6672-670">netherlands tin</span></span>
  
<span data-ttu-id="e6672-671">Tin несерланд</span><span class="sxs-lookup"><span data-stu-id="e6672-671">netherland's tin</span></span>
  
<span data-ttu-id="e6672-672">Недерландс идентификатиенуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="e6672-673">идентификатиенуммер Van</span><span class="sxs-lookup"><span data-stu-id="e6672-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="e6672-674">идентификатиенуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="e6672-675">Недерландс идентификатие</span><span class="sxs-lookup"><span data-stu-id="e6672-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="e6672-676">Недерландс — идентификатор нуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="e6672-677">Недерландс беластингнуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="e6672-678">БТВ нуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-678">btw nummer</span></span>
  
<span data-ttu-id="e6672-679">Недерландсе идентификатие</span><span class="sxs-lookup"><span data-stu-id="e6672-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="e6672-680">Польша</span><span class="sxs-lookup"><span data-stu-id="e6672-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="e6672-681">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-681">Format</span></span>

<span data-ttu-id="e6672-682">Одиннадцать цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-683">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-683">Pattern</span></span>

<span data-ttu-id="e6672-684">Одиннадцать цифр</span><span class="sxs-lookup"><span data-stu-id="e6672-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e6672-685">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-685">Checksum</span></span>

<span data-ttu-id="e6672-686">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-687">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-687">Definition</span></span>

<span data-ttu-id="e6672-688">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-689">Функция `Func_poland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-690">Найдено ключевое `Keywords_poland_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-691">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-692">Функция `Func_poland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-693">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="e6672-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-695">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-695">tax number</span></span>
  
<span data-ttu-id="e6672-696">налог но.</span><span class="sxs-lookup"><span data-stu-id="e6672-696">tax no.</span></span>
  
<span data-ttu-id="e6672-697">таксно #</span><span class="sxs-lookup"><span data-stu-id="e6672-697">taxno#</span></span>
  
<span data-ttu-id="e6672-698">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="e6672-698">taxnumber#</span></span>
  
<span data-ttu-id="e6672-699">такснумбер</span><span class="sxs-lookup"><span data-stu-id="e6672-699">taxnumber</span></span>
  
<span data-ttu-id="e6672-700">нип</span><span class="sxs-lookup"><span data-stu-id="e6672-700">nip</span></span>
  
<span data-ttu-id="e6672-701">нип #</span><span class="sxs-lookup"><span data-stu-id="e6672-701">nip#</span></span>
  
<span data-ttu-id="e6672-702">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-702">tax id</span></span>
  
<span data-ttu-id="e6672-703">Налоговый код #</span><span class="sxs-lookup"><span data-stu-id="e6672-703">tax id#</span></span>
  
<span data-ttu-id="e6672-704">Идентификатор НИП</span><span class="sxs-lookup"><span data-stu-id="e6672-704">nip id</span></span>
  
<span data-ttu-id="e6672-705">Идентификатор НИП #</span><span class="sxs-lookup"><span data-stu-id="e6672-705">nip id#</span></span>
  
<span data-ttu-id="e6672-706">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="e6672-706">tax identification number</span></span>
  
<span data-ttu-id="e6672-707">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="e6672-707">tax identification no.</span></span>
  
<span data-ttu-id="e6672-708">номер НДС</span><span class="sxs-lookup"><span data-stu-id="e6672-708">vat number</span></span>
  
<span data-ttu-id="e6672-709">НДС номер</span><span class="sxs-lookup"><span data-stu-id="e6672-709">vat no.</span></span>
  
<span data-ttu-id="e6672-710">ватно #</span><span class="sxs-lookup"><span data-stu-id="e6672-710">vatno#</span></span>
  
<span data-ttu-id="e6672-711">Код НДС</span><span class="sxs-lookup"><span data-stu-id="e6672-711">vat id</span></span>
  
<span data-ttu-id="e6672-712">Код НДС #</span><span class="sxs-lookup"><span data-stu-id="e6672-712">vat id#</span></span>
  
<span data-ttu-id="e6672-713">Нумер идентификакжи податковеж</span><span class="sxs-lookup"><span data-stu-id="e6672-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="e6672-714">полски нумер идентификакжи податковеж</span><span class="sxs-lookup"><span data-stu-id="e6672-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="e6672-715">нумеридентификакжиподатковеж #</span><span class="sxs-lookup"><span data-stu-id="e6672-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="e6672-716">Португалия</span><span class="sxs-lookup"><span data-stu-id="e6672-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="e6672-717">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-717">Format</span></span>

<span data-ttu-id="e6672-718">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-719">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-719">Pattern</span></span>

<span data-ttu-id="e6672-720">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e6672-721">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-721">Checksum</span></span>

<span data-ttu-id="e6672-722">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-723">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-723">Definition</span></span>

<span data-ttu-id="e6672-724">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-725">Функция `Func_portugal_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-726">Найдено ключевое `Keywords_portugal_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-727">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-728">Функция `Func_portugal_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-729">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="e6672-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-731">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-731">tax number</span></span>
  
<span data-ttu-id="e6672-732">налог но.</span><span class="sxs-lookup"><span data-stu-id="e6672-732">tax no.</span></span>
  
<span data-ttu-id="e6672-733">таксно #</span><span class="sxs-lookup"><span data-stu-id="e6672-733">taxno#</span></span>
  
<span data-ttu-id="e6672-734">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="e6672-734">taxnumber#</span></span>
  
<span data-ttu-id="e6672-735">такснумбер</span><span class="sxs-lookup"><span data-stu-id="e6672-735">taxnumber</span></span>
  
<span data-ttu-id="e6672-736">включена</span><span class="sxs-lookup"><span data-stu-id="e6672-736">nif</span></span>
  
<span data-ttu-id="e6672-737">включена #</span><span class="sxs-lookup"><span data-stu-id="e6672-737">nif#</span></span>
  
<span data-ttu-id="e6672-738">финансовый нумеро</span><span class="sxs-lookup"><span data-stu-id="e6672-738">numero fiscal</span></span>
  
<span data-ttu-id="e6672-739">нúмеро de идентификаçãо Фин.</span><span class="sxs-lookup"><span data-stu-id="e6672-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="e6672-740">Румыния</span><span class="sxs-lookup"><span data-stu-id="e6672-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="e6672-741">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-741">Format</span></span>

<span data-ttu-id="e6672-742">13 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-743">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-743">Pattern</span></span>

<span data-ttu-id="e6672-744">13 цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e6672-745">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-745">Checksum</span></span>

<span data-ttu-id="e6672-746">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="e6672-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-747">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-747">Definition</span></span>

<span data-ttu-id="e6672-748">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-749">Регулярное выражение `Regex_romania_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-750">Найдено ключевое `Keywords_romania_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6672-751">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="e6672-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-753">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-753">tax id</span></span>
  
<span data-ttu-id="e6672-754">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="e6672-754">tax id number</span></span>
  
<span data-ttu-id="e6672-755">Налоговый файл нет</span><span class="sxs-lookup"><span data-stu-id="e6672-755">tax file no</span></span>
  
<span data-ttu-id="e6672-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="e6672-756">tax file number</span></span>
  
<span data-ttu-id="e6672-757">налог без</span><span class="sxs-lookup"><span data-stu-id="e6672-757">tax no</span></span>
  
<span data-ttu-id="e6672-758">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-758">tax number</span></span>
  
<span data-ttu-id="e6672-759">такси #</span><span class="sxs-lookup"><span data-stu-id="e6672-759">taxid#</span></span>
  
<span data-ttu-id="e6672-760">таксно #</span><span class="sxs-lookup"><span data-stu-id="e6672-760">taxno#</span></span>
  
<span data-ttu-id="e6672-761">ID — UL таксеи</span><span class="sxs-lookup"><span data-stu-id="e6672-761">id-ul taxei</span></span>
  
<span data-ttu-id="e6672-762">нумăрул де идентификаре фискалă</span><span class="sxs-lookup"><span data-stu-id="e6672-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="e6672-763">Словакия</span><span class="sxs-lookup"><span data-stu-id="e6672-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="e6672-764">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-764">Format</span></span>

<span data-ttu-id="e6672-765">10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-766">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-766">Pattern</span></span>

<span data-ttu-id="e6672-767">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e6672-768">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-768">Checksum</span></span>

<span data-ttu-id="e6672-769">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="e6672-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-770">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-770">Definition</span></span>

<span data-ttu-id="e6672-771">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-772">Регулярное выражение `Regex_slovakia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-773">Найдено ключевое `Keywords_slovakia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6672-774">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="e6672-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-776">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-776">tax id</span></span>
  
<span data-ttu-id="e6672-777">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="e6672-777">tax id number</span></span>
  
<span data-ttu-id="e6672-778">Идентификатор Tin</span><span class="sxs-lookup"><span data-stu-id="e6672-778">tin id</span></span>
  
<span data-ttu-id="e6672-779">номер Tin</span><span class="sxs-lookup"><span data-stu-id="e6672-779">tin no</span></span>
  
<span data-ttu-id="e6672-780">Идентификатор Tin словакиан</span><span class="sxs-lookup"><span data-stu-id="e6672-780">slovakian tin id</span></span>
  
<span data-ttu-id="e6672-781">ИНН</span><span class="sxs-lookup"><span data-stu-id="e6672-781">tin</span></span>
  
<span data-ttu-id="e6672-782">Налоговый файл нет</span><span class="sxs-lookup"><span data-stu-id="e6672-782">tax file no</span></span>
  
<span data-ttu-id="e6672-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="e6672-783">tax file number</span></span>
  
<span data-ttu-id="e6672-784">налог без</span><span class="sxs-lookup"><span data-stu-id="e6672-784">tax no</span></span>
  
<span data-ttu-id="e6672-785">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-785">tax number</span></span>
  
<span data-ttu-id="e6672-786">такси #</span><span class="sxs-lookup"><span data-stu-id="e6672-786">taxid#</span></span>
  
<span data-ttu-id="e6672-787">таксно #</span><span class="sxs-lookup"><span data-stu-id="e6672-787">taxno#</span></span>
  
<span data-ttu-id="e6672-788">даňовé идентификаčнé číсло</span><span class="sxs-lookup"><span data-stu-id="e6672-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="e6672-789">даňовé číсло</span><span class="sxs-lookup"><span data-stu-id="e6672-789">daňové číslo</span></span>
  
<span data-ttu-id="e6672-790">даňовé číсло сúбору</span><span class="sxs-lookup"><span data-stu-id="e6672-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="e6672-791">Словения</span><span class="sxs-lookup"><span data-stu-id="e6672-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="e6672-792">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-792">Format</span></span>

<span data-ttu-id="e6672-793">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-794">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-794">Pattern</span></span>

<span data-ttu-id="e6672-795">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e6672-796">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-796">Checksum</span></span>

<span data-ttu-id="e6672-797">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-798">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-798">Definition</span></span>

<span data-ttu-id="e6672-799">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-800">Функция `Func_slovenia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-801">Найдено ключевое `Keywords_slovenia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-802">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-803">Функция `Func_slovenia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-804">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="e6672-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-806">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-806">tax id</span></span>
  
<span data-ttu-id="e6672-807">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="e6672-807">tax id number</span></span>
  
<span data-ttu-id="e6672-808">Идентификатор Tin</span><span class="sxs-lookup"><span data-stu-id="e6672-808">tin id</span></span>
  
<span data-ttu-id="e6672-809">номер Tin</span><span class="sxs-lookup"><span data-stu-id="e6672-809">tin no</span></span>
  
<span data-ttu-id="e6672-810">Словенский идентификатор Tin</span><span class="sxs-lookup"><span data-stu-id="e6672-810">slovenian tin id</span></span>
  
<span data-ttu-id="e6672-811">ИНН</span><span class="sxs-lookup"><span data-stu-id="e6672-811">tin</span></span>
  
<span data-ttu-id="e6672-812">Налоговый файл нет</span><span class="sxs-lookup"><span data-stu-id="e6672-812">tax file no</span></span>
  
<span data-ttu-id="e6672-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="e6672-813">tax file number</span></span>
  
<span data-ttu-id="e6672-814">налог без</span><span class="sxs-lookup"><span data-stu-id="e6672-814">tax no</span></span>
  
<span data-ttu-id="e6672-815">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-815">tax number</span></span>
  
<span data-ttu-id="e6672-816">такси #</span><span class="sxs-lookup"><span data-stu-id="e6672-816">taxid#</span></span>
  
<span data-ttu-id="e6672-817">таксно #</span><span class="sxs-lookup"><span data-stu-id="e6672-817">taxno#</span></span>
  
<span data-ttu-id="e6672-818">идентификаЦижска šтевилка Давка</span><span class="sxs-lookup"><span data-stu-id="e6672-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="e6672-819">давčна šтевилка</span><span class="sxs-lookup"><span data-stu-id="e6672-819">davčna številka</span></span>
  
<span data-ttu-id="e6672-820">šтевилка давčне датотеке</span><span class="sxs-lookup"><span data-stu-id="e6672-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="e6672-821">Испания</span><span class="sxs-lookup"><span data-stu-id="e6672-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="e6672-822">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-822">Format</span></span>

<span data-ttu-id="e6672-823">Семь или восемь цифр, а также одна или две буквы в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="e6672-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-824">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-824">Pattern</span></span>

<span data-ttu-id="e6672-825">Испанские пользователи с национальной идентификационной карточкой Испании Испания:</span><span class="sxs-lookup"><span data-stu-id="e6672-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="e6672-826">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="e6672-826">Eight digits</span></span> 
    
- <span data-ttu-id="e6672-827">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="e6672-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="e6672-828">Нерезидентские Спаниардс без национальной идентификационной карточки Испании</span><span class="sxs-lookup"><span data-stu-id="e6672-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="e6672-829">Одна прописная буква L (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="e6672-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="e6672-830">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="e6672-830">Seven digits</span></span>
    
- <span data-ttu-id="e6672-831">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="e6672-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="e6672-832">Резидентный Спаниардс в течение 14 лет без международной идентификационной карточки для Испании:</span><span class="sxs-lookup"><span data-stu-id="e6672-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="e6672-833">Одна прописная буква K (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="e6672-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="e6672-834">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="e6672-834">Seven digits</span></span> 
    
- <span data-ttu-id="e6672-835">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="e6672-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="e6672-836">Фореигнерс с идентификационным номером внешнего получателя</span><span class="sxs-lookup"><span data-stu-id="e6672-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="e6672-837">Одна прописная буква "X", "Y" или "Z" (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="e6672-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="e6672-838">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="e6672-838">Seven digits</span></span>
    
- <span data-ttu-id="e6672-839">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="e6672-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="e6672-840">Фореигнерс без идентификационного номера внешнего получателя</span><span class="sxs-lookup"><span data-stu-id="e6672-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="e6672-841">Одна прописная буква "M" (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="e6672-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="e6672-842">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="e6672-842">Seven digits</span></span>
    
- <span data-ttu-id="e6672-843">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="e6672-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e6672-844">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-844">Checksum</span></span>

<span data-ttu-id="e6672-845">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-846">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-846">Definition</span></span>

<span data-ttu-id="e6672-847">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-848">Функция `Func_spain_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-849">Найдено ключевое `Keywords_spain_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-850">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-851">Функция `Func_spain_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-852">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="e6672-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-854">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-854">tax id</span></span>
  
<span data-ttu-id="e6672-855">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="e6672-855">tax id number</span></span>
  
<span data-ttu-id="e6672-856">Идентификатор CIF</span><span class="sxs-lookup"><span data-stu-id="e6672-856">cif id</span></span>
  
<span data-ttu-id="e6672-857">CIF нет</span><span class="sxs-lookup"><span data-stu-id="e6672-857">cif no</span></span>
  
<span data-ttu-id="e6672-858">код испанского CIF</span><span class="sxs-lookup"><span data-stu-id="e6672-858">spanish cif id</span></span>
  
<span data-ttu-id="e6672-859">CIF</span><span class="sxs-lookup"><span data-stu-id="e6672-859">cif</span></span>
  
<span data-ttu-id="e6672-860">Налоговый файл нет</span><span class="sxs-lookup"><span data-stu-id="e6672-860">tax file no</span></span>
  
<span data-ttu-id="e6672-861">номер испанского CIF</span><span class="sxs-lookup"><span data-stu-id="e6672-861">spanish cif number</span></span>
  
<span data-ttu-id="e6672-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="e6672-862">tax file number</span></span>
  
<span data-ttu-id="e6672-863">Испанская CIF</span><span class="sxs-lookup"><span data-stu-id="e6672-863">spanish cif no</span></span>
  
<span data-ttu-id="e6672-864">налог без</span><span class="sxs-lookup"><span data-stu-id="e6672-864">tax no</span></span>
  
<span data-ttu-id="e6672-865">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="e6672-865">tax number</span></span>
  
<span data-ttu-id="e6672-866">такси #</span><span class="sxs-lookup"><span data-stu-id="e6672-866">taxid#</span></span>
  
<span data-ttu-id="e6672-867">таксно #</span><span class="sxs-lookup"><span data-stu-id="e6672-867">taxno#</span></span>
  
<span data-ttu-id="e6672-868">Цифид #</span><span class="sxs-lookup"><span data-stu-id="e6672-868">cifid#</span></span>
  
<span data-ttu-id="e6672-869">спанишЦифид #</span><span class="sxs-lookup"><span data-stu-id="e6672-869">spanishcifid#</span></span>
  
<span data-ttu-id="e6672-870">спанишЦифно #</span><span class="sxs-lookup"><span data-stu-id="e6672-870">spanishcifno#</span></span>
  
<span data-ttu-id="e6672-871">нúмеро de контрибуйенте</span><span class="sxs-lookup"><span data-stu-id="e6672-871">número de contribuyente</span></span>
  
<span data-ttu-id="e6672-872">нúмеро де импуесто корпоративо</span><span class="sxs-lookup"><span data-stu-id="e6672-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="e6672-873">нúмеро de идентификаЦиóн Фин.</span><span class="sxs-lookup"><span data-stu-id="e6672-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="e6672-874">CIF нúмеро</span><span class="sxs-lookup"><span data-stu-id="e6672-874">cif número</span></span>
  
<span data-ttu-id="e6672-875">Цифнúмеро #</span><span class="sxs-lookup"><span data-stu-id="e6672-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="e6672-876">Швеция</span><span class="sxs-lookup"><span data-stu-id="e6672-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="e6672-877">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-877">Format</span></span>

<span data-ttu-id="e6672-878">Десять цифр и символ в указанном шаблоне;</span><span class="sxs-lookup"><span data-stu-id="e6672-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-879">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-879">Pattern</span></span>

<span data-ttu-id="e6672-880">Десять цифр и символ:</span><span class="sxs-lookup"><span data-stu-id="e6672-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="e6672-881">Шесть цифр, соответствующих дате рождения (ГГММДД)</span><span class="sxs-lookup"><span data-stu-id="e6672-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="e6672-882">Знак плюс, знак минус или обратная косая черта</span><span class="sxs-lookup"><span data-stu-id="e6672-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="e6672-883">Три цифры, которые делают идентификационный номер уникальным, где:</span><span class="sxs-lookup"><span data-stu-id="e6672-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="e6672-884">Для номеров, выпущенных до 1990, седьмой и восьмой цифрой определяют район рождения или пользователей, порожденных иностранным пользователем.</span><span class="sxs-lookup"><span data-stu-id="e6672-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="e6672-885">Цифра в девятой позиции указывает на пол, который нечетен для пола или даже для розетки.</span><span class="sxs-lookup"><span data-stu-id="e6672-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="e6672-886">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="e6672-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e6672-887">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-887">Checksum</span></span>

<span data-ttu-id="e6672-888">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-889">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-889">Definition</span></span>

<span data-ttu-id="e6672-890">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-891">Функция `Func_sweden_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-892">Найдено ключевое `Keywords_sweden_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="e6672-893">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-894">Функция `Func_sweden_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="e6672-895">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="e6672-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-897">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-897">tax id</span></span>
  
<span data-ttu-id="e6672-898">Налоговый код но.</span><span class="sxs-lookup"><span data-stu-id="e6672-898">tax id no.</span></span>
  
<span data-ttu-id="e6672-899">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="e6672-899">tax id number</span></span>
  
<span data-ttu-id="e6672-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="e6672-900">tax identification</span></span>
  
<span data-ttu-id="e6672-901">Идентификация налога #</span><span class="sxs-lookup"><span data-stu-id="e6672-901">tax identification#</span></span>
  
<span data-ttu-id="e6672-902">налог но.</span><span class="sxs-lookup"><span data-stu-id="e6672-902">tax no.</span></span>
  
<span data-ttu-id="e6672-903">см #</span><span class="sxs-lookup"><span data-stu-id="e6672-903">tax#</span></span>
  
<span data-ttu-id="e6672-904">такси #</span><span class="sxs-lookup"><span data-stu-id="e6672-904">taxid#</span></span>
  
<span data-ttu-id="e6672-905">Налоговый файл</span><span class="sxs-lookup"><span data-stu-id="e6672-905">tax file</span></span>
  
<span data-ttu-id="e6672-906">Налоговый файл но.</span><span class="sxs-lookup"><span data-stu-id="e6672-906">tax file no.</span></span>
  
<span data-ttu-id="e6672-907">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="e6672-907">personal id number</span></span>
  
<span data-ttu-id="e6672-908">Идентификатор СКАТТ нуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-908">skatt id nummer</span></span>
  
<span data-ttu-id="e6672-909">СКАТТ идентификатион</span><span class="sxs-lookup"><span data-stu-id="e6672-909">skatt identifikation</span></span>
  
<span data-ttu-id="e6672-910">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="e6672-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="e6672-911">ВОЗМЕЩЕН</span><span class="sxs-lookup"><span data-stu-id="e6672-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="e6672-912">Format</span><span class="sxs-lookup"><span data-stu-id="e6672-912">Format</span></span>

<span data-ttu-id="e6672-913">Уникальная справочная информация о налогоплательщиках (утр): 10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="e6672-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="e6672-914">Национальный страховой номер (Нино): Дополнительные сведения см. в разделе "Великобритания</span><span class="sxs-lookup"><span data-stu-id="e6672-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="e6672-915">Национальный страховой номер (Нино) " [, чтобы найти типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="e6672-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e6672-916">Шаблон</span><span class="sxs-lookup"><span data-stu-id="e6672-916">Pattern</span></span>

<span data-ttu-id="e6672-917">Уникальная справочная информация о налогоплательщиках (утр): 10 цифр</span><span class="sxs-lookup"><span data-stu-id="e6672-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="e6672-918">Национальный страховой номер (Нино): Дополнительные сведения см. в разделе "Великобритания</span><span class="sxs-lookup"><span data-stu-id="e6672-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="e6672-919">Национальный страховой номер (Нино) " [, чтобы найти типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="e6672-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e6672-920">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="e6672-920">Checksum</span></span>

<span data-ttu-id="e6672-921">Да</span><span class="sxs-lookup"><span data-stu-id="e6672-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e6672-922">Определение</span><span class="sxs-lookup"><span data-stu-id="e6672-922">Definition</span></span>

<span data-ttu-id="e6672-923">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="e6672-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e6672-924">Функция `Func_uk_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="e6672-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e6672-925">Найдено ключевое `Keywords_uk_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="e6672-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e6672-926">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e6672-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="e6672-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="e6672-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="e6672-928">tax id</span><span class="sxs-lookup"><span data-stu-id="e6672-928">tax id</span></span>
  
<span data-ttu-id="e6672-929">Налоговый код но.</span><span class="sxs-lookup"><span data-stu-id="e6672-929">tax id no.</span></span>
  
<span data-ttu-id="e6672-930">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="e6672-930">tax id number</span></span>
  
<span data-ttu-id="e6672-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="e6672-931">tax identification</span></span>
  
<span data-ttu-id="e6672-932">Идентификация налога #</span><span class="sxs-lookup"><span data-stu-id="e6672-932">tax identification#</span></span>
  
<span data-ttu-id="e6672-933">налог но.</span><span class="sxs-lookup"><span data-stu-id="e6672-933">tax no.</span></span>
  
<span data-ttu-id="e6672-934">см #</span><span class="sxs-lookup"><span data-stu-id="e6672-934">tax#</span></span>
  
<span data-ttu-id="e6672-935">такси #</span><span class="sxs-lookup"><span data-stu-id="e6672-935">taxid#</span></span>
  
<span data-ttu-id="e6672-936">Налоговый файл</span><span class="sxs-lookup"><span data-stu-id="e6672-936">tax file</span></span>
  
<span data-ttu-id="e6672-937">Налоговый файл но.</span><span class="sxs-lookup"><span data-stu-id="e6672-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e6672-938">См. также</span><span class="sxs-lookup"><span data-stu-id="e6672-938">See also</span></span>

[<span data-ttu-id="e6672-939">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="e6672-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

