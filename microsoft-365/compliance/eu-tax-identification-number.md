---
title: Идентификационный номер налогоплательщика ЕС
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 5467db921bd518eeeab18a36ee2de473f9017358
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41591020"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="15af8-104">Идентификационный номер налогоплательщика ЕС</span><span class="sxs-lookup"><span data-stu-id="15af8-104">EU Tax Identification Number</span></span>

<span data-ttu-id="15af8-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации налогоплательщика (TIN).</span><span class="sxs-lookup"><span data-stu-id="15af8-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="15af8-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="15af8-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="15af8-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="15af8-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="15af8-108">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-108">Format</span></span>

<span data-ttu-id="15af8-109">Девять цифр с необязательным дефисом и косой чертой.</span><span class="sxs-lookup"><span data-stu-id="15af8-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-110">Pattern</span></span>

<span data-ttu-id="15af8-111">Девять цифр с необязательным дефисом и косой чертой.</span><span class="sxs-lookup"><span data-stu-id="15af8-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="15af8-112">Две цифры</span><span class="sxs-lookup"><span data-stu-id="15af8-112">Two digits</span></span> 
    
- <span data-ttu-id="15af8-113">Дефис (необязательно)</span><span class="sxs-lookup"><span data-stu-id="15af8-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="15af8-114">Три цифры</span><span class="sxs-lookup"><span data-stu-id="15af8-114">Three digits</span></span>
    
- <span data-ttu-id="15af8-115">Косая черта (необязательно)</span><span class="sxs-lookup"><span data-stu-id="15af8-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="15af8-116">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="15af8-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-117">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-117">Checksum</span></span>

<span data-ttu-id="15af8-118">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-119">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-119">Definition</span></span>

<span data-ttu-id="15af8-120">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-121">Функция `Func_austria_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-122">Найдено ключевое `Keywords_austria_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-123">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-124">Функция `Func_austria_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-125">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="15af8-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-127">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-127">tax number</span></span>
  
<span data-ttu-id="15af8-128">число</span><span class="sxs-lookup"><span data-stu-id="15af8-128">number</span></span>
  
<span data-ttu-id="15af8-129">Регистрационный номер налогоплательщика</span><span class="sxs-lookup"><span data-stu-id="15af8-129">tax registration number</span></span>
  
<span data-ttu-id="15af8-130">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-130">tax id</span></span>
  
<span data-ttu-id="15af8-131">st.nr.</span><span class="sxs-lookup"><span data-stu-id="15af8-131">st.nr.</span></span>
  
<span data-ttu-id="15af8-132">стеуернуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="15af8-133">Бельгия</span><span class="sxs-lookup"><span data-stu-id="15af8-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="15af8-134">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-134">Format</span></span>

<span data-ttu-id="15af8-135">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-136">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-136">Pattern</span></span>

<span data-ttu-id="15af8-137">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="15af8-137">11 digits:</span></span>
  
- <span data-ttu-id="15af8-138">Две цифры</span><span class="sxs-lookup"><span data-stu-id="15af8-138">Two digits</span></span>
    
- <span data-ttu-id="15af8-139">"0" или "1"</span><span class="sxs-lookup"><span data-stu-id="15af8-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="15af8-140">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="15af8-140">One digit</span></span>
    
- <span data-ttu-id="15af8-141">"0" или "1" или "2" или "3"</span><span class="sxs-lookup"><span data-stu-id="15af8-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="15af8-142">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-143">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-143">Checksum</span></span>

<span data-ttu-id="15af8-144">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="15af8-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-145">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-145">Definition</span></span>

<span data-ttu-id="15af8-146">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-147">Регулярное выражение `Regex_belgium_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-148">Найдено ключевое `Keywords_belgium_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="15af8-149">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="15af8-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-151">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-151">tax number</span></span>
  
<span data-ttu-id="15af8-152">Национальный регистрационный номер</span><span class="sxs-lookup"><span data-stu-id="15af8-152">national registration number</span></span>
  
<span data-ttu-id="15af8-153">Регистрационный номер налогоплательщика</span><span class="sxs-lookup"><span data-stu-id="15af8-153">tax registration number</span></span>
  
<span data-ttu-id="15af8-154">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-154">tax id</span></span>
  
<span data-ttu-id="15af8-155">включена</span><span class="sxs-lookup"><span data-stu-id="15af8-155">nif</span></span>
  
<span data-ttu-id="15af8-156">включена #</span><span class="sxs-lookup"><span data-stu-id="15af8-156">nif#</span></span>
  
<span data-ttu-id="15af8-157">нумéро de регистре National</span><span class="sxs-lookup"><span data-stu-id="15af8-157">numéro de registre national</span></span>
  
<span data-ttu-id="15af8-158">нумéро д'идентификатион Фин.</span><span class="sxs-lookup"><span data-stu-id="15af8-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="15af8-159">Болгария</span><span class="sxs-lookup"><span data-stu-id="15af8-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="15af8-160">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-160">Format</span></span>

<span data-ttu-id="15af8-161">Десять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-162">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-162">Pattern</span></span>

<span data-ttu-id="15af8-163">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="15af8-164">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-164">Checksum</span></span>

<span data-ttu-id="15af8-165">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-166">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-166">Definition</span></span>

<span data-ttu-id="15af8-167">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-168">Функция `Func_bulgaria_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-169">Найдено ключевое `Keywords_bulgaria_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-170">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-171">Функция `Func_bulgaria_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-172">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="15af8-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-174">букн</span><span class="sxs-lookup"><span data-stu-id="15af8-174">bucn</span></span>
  
<span data-ttu-id="15af8-175">единое гражданское число</span><span class="sxs-lookup"><span data-stu-id="15af8-175">uniform civil number</span></span>
  
<span data-ttu-id="15af8-176">букн #</span><span class="sxs-lookup"><span data-stu-id="15af8-176">bucn#</span></span>
  
<span data-ttu-id="15af8-177">униформЦивилнумбер #</span><span class="sxs-lookup"><span data-stu-id="15af8-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="15af8-178">унифицированный гражданский идентификатор</span><span class="sxs-lookup"><span data-stu-id="15af8-178">uniform civil id</span></span>
  
<span data-ttu-id="15af8-179">равномерный гражданский номер</span><span class="sxs-lookup"><span data-stu-id="15af8-179">uniform civil no</span></span>
  
<span data-ttu-id="15af8-180">егн</span><span class="sxs-lookup"><span data-stu-id="15af8-180">egn</span></span>
  
<span data-ttu-id="15af8-181">номер унифицированного гражданства болгарского языка</span><span class="sxs-lookup"><span data-stu-id="15af8-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="15af8-182">униформЦивилно #</span><span class="sxs-lookup"><span data-stu-id="15af8-182">uniformcivilno#</span></span>
  
<span data-ttu-id="15af8-183">егн #</span><span class="sxs-lookup"><span data-stu-id="15af8-183">egn#</span></span>
  
<span data-ttu-id="15af8-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="15af8-184">униформ граждански номер</span></span>
  
<span data-ttu-id="15af8-185">Идентификатор униформ</span><span class="sxs-lookup"><span data-stu-id="15af8-185">униформ id</span></span>
  
<span data-ttu-id="15af8-186">униформ граждански ID</span><span class="sxs-lookup"><span data-stu-id="15af8-186">униформ граждански id</span></span>
  
<span data-ttu-id="15af8-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="15af8-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="15af8-188">Хорватия</span><span class="sxs-lookup"><span data-stu-id="15af8-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="15af8-189">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-189">Format</span></span>

<span data-ttu-id="15af8-190">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-191">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-191">Pattern</span></span>

<span data-ttu-id="15af8-192">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="15af8-192">11 digits:</span></span>
  
- <span data-ttu-id="15af8-193">Десять цифр, выбран случайным образом</span><span class="sxs-lookup"><span data-stu-id="15af8-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="15af8-194">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="15af8-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-195">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-195">Checksum</span></span>

<span data-ttu-id="15af8-196">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-197">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-197">Definition</span></span>

<span data-ttu-id="15af8-198">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-199">Функция `Func_croatia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-200">Найдено ключевое `Keywords_croatia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-201">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-202">Функция `Func_croatia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-203">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="15af8-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-205">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-205">tax number</span></span>
  
<span data-ttu-id="15af8-206">см</span><span class="sxs-lookup"><span data-stu-id="15af8-206">tax</span></span>
  
<span data-ttu-id="15af8-207">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-207">tax id</span></span>
  
<span data-ttu-id="15af8-208">oid</span><span class="sxs-lookup"><span data-stu-id="15af8-208">oid</span></span>
  
<span data-ttu-id="15af8-209">идентификатора #</span><span class="sxs-lookup"><span data-stu-id="15af8-209">oid#</span></span>
  
<span data-ttu-id="15af8-210">порезни Брож</span><span class="sxs-lookup"><span data-stu-id="15af8-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="15af8-211">Кипр</span><span class="sxs-lookup"><span data-stu-id="15af8-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="15af8-212">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-212">Format</span></span>

<span data-ttu-id="15af8-213">Восемь цифр и одна буква в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="15af8-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-214">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-214">Pattern</span></span>

<span data-ttu-id="15af8-215">Восемь цифр и одна буква:</span><span class="sxs-lookup"><span data-stu-id="15af8-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="15af8-216">"0"</span><span class="sxs-lookup"><span data-stu-id="15af8-216">A "0"</span></span> 
    
- <span data-ttu-id="15af8-217">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="15af8-217">Seven digits</span></span>
    
- <span data-ttu-id="15af8-218">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="15af8-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-219">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-219">Checksum</span></span>

<span data-ttu-id="15af8-220">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="15af8-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-221">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-221">Definition</span></span>

<span data-ttu-id="15af8-222">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-223">Функция `Func_cyprus_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-224">Найдено ключевое `Keywords_cyprus_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-225">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-226">Функция `Func_cyprus_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-227">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="15af8-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-229">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-229">tax number</span></span>
  
<span data-ttu-id="15af8-230">см</span><span class="sxs-lookup"><span data-stu-id="15af8-230">tax</span></span>
  
<span data-ttu-id="15af8-231">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-231">tax id</span></span>
  
<span data-ttu-id="15af8-232">Налоговый код идентификации</span><span class="sxs-lookup"><span data-stu-id="15af8-232">tax identification code</span></span>
  
<span data-ttu-id="15af8-233">тик</span><span class="sxs-lookup"><span data-stu-id="15af8-233">tic</span></span>
  
<span data-ttu-id="15af8-234">тик #</span><span class="sxs-lookup"><span data-stu-id="15af8-234">tic#</span></span>
  
<span data-ttu-id="15af8-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="15af8-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="15af8-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="15af8-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="15af8-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="15af8-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="15af8-238">Чешская Республика</span><span class="sxs-lookup"><span data-stu-id="15af8-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="15af8-239">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-239">Format</span></span>

<span data-ttu-id="15af8-240">Девять или десять цифр с необязательной обратной косой чертой</span><span class="sxs-lookup"><span data-stu-id="15af8-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-241">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-241">Pattern</span></span>

<span data-ttu-id="15af8-242">Девять или десять цифр с необязательной обратной косой чертой.</span><span class="sxs-lookup"><span data-stu-id="15af8-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="15af8-243">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="15af8-243">Six digits</span></span> 
    
- <span data-ttu-id="15af8-244">Обратная косая черта (необязательно)</span><span class="sxs-lookup"><span data-stu-id="15af8-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="15af8-245">Три или четыре цифры</span><span class="sxs-lookup"><span data-stu-id="15af8-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-246">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-246">Checksum</span></span>

<span data-ttu-id="15af8-247">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="15af8-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-248">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-248">Definition</span></span>

<span data-ttu-id="15af8-249">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-250">Регулярное выражение `Regex_czech_republic_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-251">Найдено ключевое `Keywords_czech_republic_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="15af8-252">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="15af8-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-254">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-254">tax number</span></span>
  
<span data-ttu-id="15af8-255">см</span><span class="sxs-lookup"><span data-stu-id="15af8-255">tax</span></span>
  
<span data-ttu-id="15af8-256">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-256">tax id</span></span>
  
<span data-ttu-id="15af8-257">персональный номер</span><span class="sxs-lookup"><span data-stu-id="15af8-257">personal number</span></span>
  
<span data-ttu-id="15af8-258">даňовé číсло</span><span class="sxs-lookup"><span data-stu-id="15af8-258">daňové číslo</span></span>
  
<span data-ttu-id="15af8-259">особнí číсло</span><span class="sxs-lookup"><span data-stu-id="15af8-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="15af8-260">Дания</span><span class="sxs-lookup"><span data-stu-id="15af8-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="15af8-261">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-261">Format</span></span>

<span data-ttu-id="15af8-262">Десять цифр, содержащие дефис</span><span class="sxs-lookup"><span data-stu-id="15af8-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-263">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-263">Pattern</span></span>

<span data-ttu-id="15af8-264">Десять цифр с дефисом:</span><span class="sxs-lookup"><span data-stu-id="15af8-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="15af8-265">Шесть цифр, соответствующих дате рождения (ДДММГГ —)</span><span class="sxs-lookup"><span data-stu-id="15af8-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="15af8-266">дефис;</span><span class="sxs-lookup"><span data-stu-id="15af8-266">A hyphen</span></span>
    
- <span data-ttu-id="15af8-267">Четыре цифры, которые соответствуют порядковому номеру, где первая цифра соответствует столетию рождения, а последняя цифра соответствует полу лица (нечетный для пола и даже для женщина)</span><span class="sxs-lookup"><span data-stu-id="15af8-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-268">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-268">Checksum</span></span>

<span data-ttu-id="15af8-269">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-270">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-270">Definition</span></span>

<span data-ttu-id="15af8-271">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-272">Функция `Func_denmark_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-273">Найдено ключевое `Keywords_denmark_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-274">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-275">Функция `Func_denmark_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-276">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="15af8-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-278">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-278">tax number</span></span>
  
<span data-ttu-id="15af8-279">см</span><span class="sxs-lookup"><span data-stu-id="15af8-279">tax</span></span>
  
<span data-ttu-id="15af8-280">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-280">tax id</span></span>
  
<span data-ttu-id="15af8-281">CPR Number</span><span class="sxs-lookup"><span data-stu-id="15af8-281">cpr number</span></span>
  
<span data-ttu-id="15af8-282">CPR #</span><span class="sxs-lookup"><span data-stu-id="15af8-282">cpr#</span></span>
  
<span data-ttu-id="15af8-283">Скат нуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-283">skat nummer</span></span>
  
<span data-ttu-id="15af8-284">Идентификатор Скат</span><span class="sxs-lookup"><span data-stu-id="15af8-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="15af8-285">Эстония</span><span class="sxs-lookup"><span data-stu-id="15af8-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="15af8-286">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-286">Format</span></span>

<span data-ttu-id="15af8-287">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-288">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-288">Pattern</span></span>

<span data-ttu-id="15af8-289">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="15af8-289">11 digits:</span></span>
  
-  <span data-ttu-id="15af8-290">Одна цифра, соответствующая пол и столетию рождения, где нечетное число означает "штекер", а четное число указывает на женщина следующим образом: 1, 2 для 19 века; 3, 4 — 20 века; и 5, 6 для 21 века</span><span class="sxs-lookup"><span data-stu-id="15af8-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="15af8-291">Шесть цифр, соответствующих дате рождения (ГГММДД)</span><span class="sxs-lookup"><span data-stu-id="15af8-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="15af8-292">Три цифры, которые соответствуют порядковому номеру, разделенному на одну и ту же дату.</span><span class="sxs-lookup"><span data-stu-id="15af8-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="15af8-293">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="15af8-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-294">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-294">Checksum</span></span>

<span data-ttu-id="15af8-295">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-296">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-296">Definition</span></span>

<span data-ttu-id="15af8-297">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-298">Функция `Func_estonia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-299">Найдено ключевое `Keywords_estonia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-300">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-301">Функция `Func_estonia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-302">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="15af8-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-304">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-304">tax number</span></span>
  
<span data-ttu-id="15af8-305">см</span><span class="sxs-lookup"><span data-stu-id="15af8-305">tax</span></span>
  
<span data-ttu-id="15af8-306">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-306">tax id</span></span>
  
<span data-ttu-id="15af8-307">персональный код</span><span class="sxs-lookup"><span data-stu-id="15af8-307">personal code</span></span>
  
<span data-ttu-id="15af8-308">максунумбер</span><span class="sxs-lookup"><span data-stu-id="15af8-308">maksunumber</span></span>
  
<span data-ttu-id="15af8-309">Идентификатор Максу</span><span class="sxs-lookup"><span data-stu-id="15af8-309">maksu id</span></span>
  
<span data-ttu-id="15af8-310">исикукуд</span><span class="sxs-lookup"><span data-stu-id="15af8-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="15af8-311">Финляндия</span><span class="sxs-lookup"><span data-stu-id="15af8-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="15af8-312">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-312">Format</span></span>

<span data-ttu-id="15af8-313">Сочетание цифр, букв и плюса, а также знак минуса</span><span class="sxs-lookup"><span data-stu-id="15af8-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-314">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-314">Pattern</span></span>

<span data-ttu-id="15af8-315">Сочетание цифр, букв и плюса и знака "плюс" и "минус" (11 символов).</span><span class="sxs-lookup"><span data-stu-id="15af8-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="15af8-316">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="15af8-316">Six digits</span></span>
    
- <span data-ttu-id="15af8-317">Один из следующих элементов: знак плюса, знак минуса или буква "A" (без учета регистра), где знак "плюс" (без учета регистра) означает 1900-1999, что знак "плюс" находится в диапазоне от 1 до 1800-1899, а "A" означает, что порожденный 2000 и после</span><span class="sxs-lookup"><span data-stu-id="15af8-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="15af8-318">Три цифры</span><span class="sxs-lookup"><span data-stu-id="15af8-318">Three digits</span></span>
    
- <span data-ttu-id="15af8-319">Одна буква или один номер</span><span class="sxs-lookup"><span data-stu-id="15af8-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-320">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-320">Checksum</span></span>

<span data-ttu-id="15af8-321">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-322">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-322">Definition</span></span>

<span data-ttu-id="15af8-323">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-324">Функция `Func_finland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-325">Найдено ключевое `Keywords_finland_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-326">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-327">Функция `Func_finland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-328">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="15af8-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-330">identification number</span><span class="sxs-lookup"><span data-stu-id="15af8-330">identification number</span></span>
  
<span data-ttu-id="15af8-331">личный идентификатор</span><span class="sxs-lookup"><span data-stu-id="15af8-331">personal id</span></span>
  
<span data-ttu-id="15af8-332">идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="15af8-332">identity number</span></span>
  
<span data-ttu-id="15af8-333">Финский национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="15af8-333">finnish national id number</span></span>
  
<span data-ttu-id="15af8-334">персоналиднумбер #</span><span class="sxs-lookup"><span data-stu-id="15af8-334">personalidnumber#</span></span>
  
<span data-ttu-id="15af8-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="15af8-335">national identification number</span></span>
  
<span data-ttu-id="15af8-336">идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="15af8-336">id number</span></span>
  
<span data-ttu-id="15af8-337">код страны</span><span class="sxs-lookup"><span data-stu-id="15af8-337">national id no.</span></span>
  
<span data-ttu-id="15af8-338">Национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="15af8-338">national id number</span></span>
  
<span data-ttu-id="15af8-339">ID No</span><span class="sxs-lookup"><span data-stu-id="15af8-339">id no</span></span>
  
<span data-ttu-id="15af8-340">туннистенумеро</span><span class="sxs-lookup"><span data-stu-id="15af8-340">tunnistenumero</span></span>
  
<span data-ttu-id="15af8-341">хенкилöтуннус</span><span class="sxs-lookup"><span data-stu-id="15af8-341">henkilötunnus</span></span>
  
<span data-ttu-id="15af8-342">иксилöллинен хенкилöкохтаинен туннистенумеро</span><span class="sxs-lookup"><span data-stu-id="15af8-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="15af8-343">аинутлаатуинен хенкилöкохтаинен туннус</span><span class="sxs-lookup"><span data-stu-id="15af8-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="15af8-344">идентититти нумеро</span><span class="sxs-lookup"><span data-stu-id="15af8-344">identiteetti numero</span></span>
  
<span data-ttu-id="15af8-345">Суомен кансаллинен хенкилöтуннус</span><span class="sxs-lookup"><span data-stu-id="15af8-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="15af8-346">хенкилöтуннуснумеро #</span><span class="sxs-lookup"><span data-stu-id="15af8-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="15af8-347">кансаллисен туннистенумеро</span><span class="sxs-lookup"><span data-stu-id="15af8-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="15af8-348">туннуснумеро</span><span class="sxs-lookup"><span data-stu-id="15af8-348">tunnusnumero</span></span>
  
<span data-ttu-id="15af8-349">кансаллинен туннус нумеро</span><span class="sxs-lookup"><span data-stu-id="15af8-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="15af8-350">Франция</span><span class="sxs-lookup"><span data-stu-id="15af8-350">France</span></span>

### <a name="format"></a><span data-ttu-id="15af8-351">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-351">Format</span></span>

<span data-ttu-id="15af8-352">13 цифр для отдельных пользователей и девять цифр для сущностей</span><span class="sxs-lookup"><span data-stu-id="15af8-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-353">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-353">Pattern</span></span>

<span data-ttu-id="15af8-354">13 цифр для отдельных пользователей:</span><span class="sxs-lookup"><span data-stu-id="15af8-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="15af8-355">Одна цифра, которая должна быть равна 0, 1, 2 или 3</span><span class="sxs-lookup"><span data-stu-id="15af8-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="15af8-356">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-356">12 digits</span></span>
    
<span data-ttu-id="15af8-357">Девять цифр для сущностей</span><span class="sxs-lookup"><span data-stu-id="15af8-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="15af8-358">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-358">Checksum</span></span>

<span data-ttu-id="15af8-359">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="15af8-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-360">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-360">Definition</span></span>

<span data-ttu-id="15af8-361">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-362">Функция `Func_france_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-363">Найдено ключевое `Keywords_france_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-364">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-365">Функция `Func_france_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-366">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="15af8-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-368">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="15af8-368">tax identification number</span></span>
  
<span data-ttu-id="15af8-369">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-369">tax number</span></span>
  
<span data-ttu-id="15af8-370">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-370">tax id</span></span>
  
<span data-ttu-id="15af8-371">нумéро д'идентификатион Фин.</span><span class="sxs-lookup"><span data-stu-id="15af8-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="15af8-372">Германия</span><span class="sxs-lookup"><span data-stu-id="15af8-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="15af8-373">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-373">Format</span></span>

<span data-ttu-id="15af8-374">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-375">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-375">Pattern</span></span>

<span data-ttu-id="15af8-376">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="15af8-376">11 digits :</span></span>
  
-  <span data-ttu-id="15af8-377">Десять цифр</span><span class="sxs-lookup"><span data-stu-id="15af8-377">Ten digits</span></span> 
    
- <span data-ttu-id="15af8-378">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="15af8-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-379">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-379">Checksum</span></span>

<span data-ttu-id="15af8-380">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-381">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-381">Definition</span></span>

<span data-ttu-id="15af8-382">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-383">Функция `Func_germany_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-384">Найдено ключевое `Keywords_germany_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-385">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-386">Функция `Func_germany_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-387">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="15af8-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-389">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-389">tax number</span></span>
  
<span data-ttu-id="15af8-390">налог но.</span><span class="sxs-lookup"><span data-stu-id="15af8-390">tax no.</span></span>
  
<span data-ttu-id="15af8-391">таксно #</span><span class="sxs-lookup"><span data-stu-id="15af8-391">taxno#</span></span>
  
<span data-ttu-id="15af8-392">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="15af8-392">taxnumber#</span></span>
  
<span data-ttu-id="15af8-393">такснумбер</span><span class="sxs-lookup"><span data-stu-id="15af8-393">taxnumber</span></span>
  
<span data-ttu-id="15af8-394">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-394">tax id</span></span>
  
<span data-ttu-id="15af8-395">такси #</span><span class="sxs-lookup"><span data-stu-id="15af8-395">taxid#</span></span>
  
<span data-ttu-id="15af8-396">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="15af8-396">tax identification number</span></span>
  
<span data-ttu-id="15af8-397">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="15af8-397">tax identification no.</span></span>
  
<span data-ttu-id="15af8-398">стеуернуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-398">steuernummer</span></span>
  
<span data-ttu-id="15af8-399">Идентификатор стеуер</span><span class="sxs-lookup"><span data-stu-id="15af8-399">steuer id</span></span>
  
<span data-ttu-id="15af8-400">стеуеридентификатионснуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="15af8-401">Греция</span><span class="sxs-lookup"><span data-stu-id="15af8-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="15af8-402">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-402">Format</span></span>

<span data-ttu-id="15af8-403">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-404">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-404">Pattern</span></span>

<span data-ttu-id="15af8-405">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="15af8-406">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-406">Checksum</span></span>

<span data-ttu-id="15af8-407">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="15af8-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-408">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-408">Definition</span></span>

<span data-ttu-id="15af8-409">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-410">Регулярное выражение `Regex_greece_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-411">Найдено ключевое `Keywords_greece_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="15af8-412">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="15af8-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-414">афм</span><span class="sxs-lookup"><span data-stu-id="15af8-414">afm</span></span>
  
<span data-ttu-id="15af8-415">ИНН</span><span class="sxs-lookup"><span data-stu-id="15af8-415">tin</span></span>
  
<span data-ttu-id="15af8-416">Налоговый код но.</span><span class="sxs-lookup"><span data-stu-id="15af8-416">tax id no.</span></span>
  
<span data-ttu-id="15af8-417">Налоговый код No</span><span class="sxs-lookup"><span data-stu-id="15af8-417">tax id no</span></span>
  
<span data-ttu-id="15af8-418">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="15af8-418">tax identification number</span></span>
  
<span data-ttu-id="15af8-419">Налоговый номер реестра</span><span class="sxs-lookup"><span data-stu-id="15af8-419">tax registry number</span></span>
  
<span data-ttu-id="15af8-420">реестр по номеру налога</span><span class="sxs-lookup"><span data-stu-id="15af8-420">tax registry no.</span></span>
  
<span data-ttu-id="15af8-421">афм #</span><span class="sxs-lookup"><span data-stu-id="15af8-421">afm#</span></span>
  
<span data-ttu-id="15af8-422">ИНН #</span><span class="sxs-lookup"><span data-stu-id="15af8-422">tin#</span></span>
  
<span data-ttu-id="15af8-423">таксидно #</span><span class="sxs-lookup"><span data-stu-id="15af8-423">taxidno#</span></span>
  
<span data-ttu-id="15af8-424">таксрегистрино #</span><span class="sxs-lookup"><span data-stu-id="15af8-424">taxregistryno#</span></span>
  
<span data-ttu-id="15af8-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="15af8-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="15af8-426">аφμ</span><span class="sxs-lookup"><span data-stu-id="15af8-426">aφμ</span></span>
  
<span data-ttu-id="15af8-427">аφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="15af8-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="15af8-428">φορολογικού μητρώου Νο.</span><span class="sxs-lookup"><span data-stu-id="15af8-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="15af8-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="15af8-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="15af8-430">Венгрия</span><span class="sxs-lookup"><span data-stu-id="15af8-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="15af8-431">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-431">Format</span></span>

<span data-ttu-id="15af8-432">Десять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-433">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-433">Pattern</span></span>

<span data-ttu-id="15af8-434">Десять цифр:</span><span class="sxs-lookup"><span data-stu-id="15af8-434">Ten digits:</span></span>
  
-  <span data-ttu-id="15af8-435">Одна цифра, которая должна быть "8"</span><span class="sxs-lookup"><span data-stu-id="15af8-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="15af8-436">Пять цифр, которые соответствуют количеству дней между датой 01/01/1867 и датой рождения отдельного лица.</span><span class="sxs-lookup"><span data-stu-id="15af8-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="15af8-437">Три цифры, которые соответствуют номеру, созданному шансом выделить людей, которые поставили один и тот же день.</span><span class="sxs-lookup"><span data-stu-id="15af8-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="15af8-438">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="15af8-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-439">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-439">Checksum</span></span>

<span data-ttu-id="15af8-440">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-441">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-441">Definition</span></span>

<span data-ttu-id="15af8-442">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-443">Функция `Func_hungary_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-444">Найдено ключевое `Keywords_hungary_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-445">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-446">Функция `Func_hungary_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-447">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="15af8-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-449">идентификационный номер для венгерского налога</span><span class="sxs-lookup"><span data-stu-id="15af8-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="15af8-450">Венгерский Tin</span><span class="sxs-lookup"><span data-stu-id="15af8-450">hungarian tin</span></span>
  
<span data-ttu-id="15af8-451">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="15af8-451">tax id number</span></span>
  
<span data-ttu-id="15af8-452">номер НДС</span><span class="sxs-lookup"><span data-stu-id="15af8-452">vat number</span></span>
  
<span data-ttu-id="15af8-453">Налоговый орган без</span><span class="sxs-lookup"><span data-stu-id="15af8-453">tax authority no</span></span>
  
<span data-ttu-id="15af8-454">идентификационный номер налогоплательщика для налогового кода</span><span class="sxs-lookup"><span data-stu-id="15af8-454">tax id tax identity number</span></span>
  
<span data-ttu-id="15af8-455">таксиднумбер #</span><span class="sxs-lookup"><span data-stu-id="15af8-455">taxidnumber#</span></span>
  
<span data-ttu-id="15af8-456">ИНН #</span><span class="sxs-lookup"><span data-stu-id="15af8-456">tin#</span></span>
  
<span data-ttu-id="15af8-457">хунгатиантин #</span><span class="sxs-lookup"><span data-stu-id="15af8-457">hungatiantin#</span></span>
  
<span data-ttu-id="15af8-458">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="15af8-458">tax identification no</span></span>
  
<span data-ttu-id="15af8-459">таксидно #</span><span class="sxs-lookup"><span data-stu-id="15af8-459">taxidno#</span></span>
  
<span data-ttu-id="15af8-460">адóазоносíтó сзáм</span><span class="sxs-lookup"><span data-stu-id="15af8-460">adóazonosító szám</span></span>
  
<span data-ttu-id="15af8-461">адóсзáм</span><span class="sxs-lookup"><span data-stu-id="15af8-461">adószám</span></span>
  
<span data-ttu-id="15af8-462">адóхатóсáг сзáм</span><span class="sxs-lookup"><span data-stu-id="15af8-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="15af8-463">Ireland (Ирландия)</span><span class="sxs-lookup"><span data-stu-id="15af8-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="15af8-464">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-464">Format</span></span>

<span data-ttu-id="15af8-465">Семь цифр, за которыми следует буква без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-466">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-466">Pattern</span></span>

<span data-ttu-id="15af8-467">Семь цифр, за которыми следует буква:</span><span class="sxs-lookup"><span data-stu-id="15af8-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="15af8-468">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="15af8-468">Seven digits</span></span> 
    
- <span data-ttu-id="15af8-469">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="15af8-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-470">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-470">Checksum</span></span>

<span data-ttu-id="15af8-471">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="15af8-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-472">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-472">Definition</span></span>

<span data-ttu-id="15af8-473">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-474">Функция `Func_ireland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-475">Найдено ключевое `Keywords_ireland_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-476">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-477">Функция `Func_ireland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-478">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="15af8-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-480">общедоступная служба</span><span class="sxs-lookup"><span data-stu-id="15af8-480">public service no</span></span>
  
<span data-ttu-id="15af8-481">Личная общедоступная служба</span><span class="sxs-lookup"><span data-stu-id="15af8-481">personal public service no</span></span>
  
<span data-ttu-id="15af8-482">PPS нет</span><span class="sxs-lookup"><span data-stu-id="15af8-482">pps no</span></span>
  
<span data-ttu-id="15af8-483">Личная служба</span><span class="sxs-lookup"><span data-stu-id="15af8-483">personal service no</span></span>
  
<span data-ttu-id="15af8-484">Служба PPS нет</span><span class="sxs-lookup"><span data-stu-id="15af8-484">pps service no</span></span>
  
<span data-ttu-id="15af8-485">ппсно #</span><span class="sxs-lookup"><span data-stu-id="15af8-485">ppsno#</span></span>
  
<span data-ttu-id="15af8-486">Ирландский PPS No</span><span class="sxs-lookup"><span data-stu-id="15af8-486">irish pps no</span></span>
  
<span data-ttu-id="15af8-487">публиксервицено #</span><span class="sxs-lookup"><span data-stu-id="15af8-487">publicserviceno#</span></span>
  
<span data-ttu-id="15af8-488">номер личной общедоступной службы</span><span class="sxs-lookup"><span data-stu-id="15af8-488">personal public service number</span></span>
  
<span data-ttu-id="15af8-489">уимхир феарсанта сеирбхíсе поиблí</span><span class="sxs-lookup"><span data-stu-id="15af8-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="15af8-490">PPS уимх</span><span class="sxs-lookup"><span data-stu-id="15af8-490">pps uimh</span></span>
  
<span data-ttu-id="15af8-491">уимхир аисеантаис феарсанта</span><span class="sxs-lookup"><span data-stu-id="15af8-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="15af8-492">Италия</span><span class="sxs-lookup"><span data-stu-id="15af8-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="15af8-493">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-493">Format</span></span>

<span data-ttu-id="15af8-494">16 букв и цифр в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="15af8-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-495">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-495">Pattern</span></span>

<span data-ttu-id="15af8-496">16 букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="15af8-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="15af8-497">Три буквы, соответствующие первым трем согласным в имени семейства</span><span class="sxs-lookup"><span data-stu-id="15af8-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="15af8-498">Три буквы, соответствующие первым, третьим и четвертым согласным в имени.</span><span class="sxs-lookup"><span data-stu-id="15af8-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="15af8-499">Две цифры, соответствующие последним цифрам года рождения</span><span class="sxs-lookup"><span data-stu-id="15af8-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="15af8-500">Одна цифра, соответствующая месяцу рождения, буквы используются в алфавитном порядке, но используются только буквы от A до E, H, L, M, P, R — T (то есть Январь — это R, а Октябрь — R)</span><span class="sxs-lookup"><span data-stu-id="15af8-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="15af8-501">Две цифры, которые соответствуют дню рождения, где 40 добавляется к дню рождения женщин, чтобы отличать от мужчин</span><span class="sxs-lookup"><span data-stu-id="15af8-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="15af8-502">Четыре цифры, соответствующие коду города, соответствующему органу государственной власти, в котором был создан пользователь, — коды уровня страны используются для иностранных стран</span><span class="sxs-lookup"><span data-stu-id="15af8-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="15af8-503">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="15af8-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-504">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-504">Checksum</span></span>

<span data-ttu-id="15af8-505">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-506">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-506">Definition</span></span>

<span data-ttu-id="15af8-507">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-508">Функция `Func_italy_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-509">Найдено ключевое `Keywords_italy_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-510">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-511">Функция `Func_italy_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-512">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="15af8-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-514">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-514">tax number</span></span>
  
<span data-ttu-id="15af8-515">налог но.</span><span class="sxs-lookup"><span data-stu-id="15af8-515">tax no.</span></span>
  
<span data-ttu-id="15af8-516">таксно #</span><span class="sxs-lookup"><span data-stu-id="15af8-516">taxno#</span></span>
  
<span data-ttu-id="15af8-517">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="15af8-517">taxnumber#</span></span>
  
<span data-ttu-id="15af8-518">такснумбер</span><span class="sxs-lookup"><span data-stu-id="15af8-518">taxnumber</span></span>
  
<span data-ttu-id="15af8-519">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-519">tax id</span></span>
  
<span data-ttu-id="15af8-520">такси #</span><span class="sxs-lookup"><span data-stu-id="15af8-520">taxid#</span></span>
  
<span data-ttu-id="15af8-521">Финансовый код</span><span class="sxs-lookup"><span data-stu-id="15af8-521">fiscal code</span></span>
  
<span data-ttu-id="15af8-522">финансовый отчет по сокостям</span><span class="sxs-lookup"><span data-stu-id="15af8-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="15af8-523">Латвия</span><span class="sxs-lookup"><span data-stu-id="15af8-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="15af8-524">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-524">Format</span></span>

<span data-ttu-id="15af8-525">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-526">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-526">Pattern</span></span>

<span data-ttu-id="15af8-527">11 цифр в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="15af8-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="15af8-528">Шесть цифр, соответствующих дате рождения (ДДММГГ —)</span><span class="sxs-lookup"><span data-stu-id="15af8-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="15af8-529">Одна цифра, соответствующая столетию рождения, где "0" соответствует 19 века, "1" соответствует 20 столетию, а "2" соответствует 21 столетию</span><span class="sxs-lookup"><span data-stu-id="15af8-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="15af8-530">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="15af8-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-531">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-531">Checksum</span></span>

<span data-ttu-id="15af8-532">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-533">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-533">Definition</span></span>

<span data-ttu-id="15af8-534">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-535">Функция `Func_latvia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-536">Найдено ключевое `Keywords_latvia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-537">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-538">Функция `Func_latvia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-539">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="15af8-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-541">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-541">tax number</span></span>
  
<span data-ttu-id="15af8-542">налог но.</span><span class="sxs-lookup"><span data-stu-id="15af8-542">tax no.</span></span>
  
<span data-ttu-id="15af8-543">таксно #</span><span class="sxs-lookup"><span data-stu-id="15af8-543">taxno#</span></span>
  
<span data-ttu-id="15af8-544">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="15af8-544">taxnumber#</span></span>
  
<span data-ttu-id="15af8-545">такснумбер</span><span class="sxs-lookup"><span data-stu-id="15af8-545">taxnumber</span></span>
  
<span data-ttu-id="15af8-546">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-546">tax id</span></span>
  
<span data-ttu-id="15af8-547">такси #</span><span class="sxs-lookup"><span data-stu-id="15af8-547">taxid#</span></span>
  
<span data-ttu-id="15af8-548">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="15af8-548">tax identification number</span></span>
  
<span data-ttu-id="15af8-549">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="15af8-549">tax identification no.</span></span>
  
<span data-ttu-id="15af8-550">нодокļа нумурс</span><span class="sxs-lookup"><span data-stu-id="15af8-550">nodokļa numurs</span></span>
  
<span data-ttu-id="15af8-551">нодокļу идентификāЦижас нумурс</span><span class="sxs-lookup"><span data-stu-id="15af8-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="15af8-552">нодокļу идентификāЦижа нумурс</span><span class="sxs-lookup"><span data-stu-id="15af8-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="15af8-553">Литва</span><span class="sxs-lookup"><span data-stu-id="15af8-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="15af8-554">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-554">Format</span></span>

<span data-ttu-id="15af8-555">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-556">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-556">Pattern</span></span>

<span data-ttu-id="15af8-557">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="15af8-558">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-558">Checksum</span></span>

<span data-ttu-id="15af8-559">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="15af8-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-560">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-560">Definition</span></span>

<span data-ttu-id="15af8-561">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-562">Функция `Func_lithuania_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-563">Найдено ключевое `Keywords_lithuania_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-564">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-565">Функция `Func_lithuania_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-566">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="15af8-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-568">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-568">tax number</span></span>
  
<span data-ttu-id="15af8-569">налог но.</span><span class="sxs-lookup"><span data-stu-id="15af8-569">tax no.</span></span>
  
<span data-ttu-id="15af8-570">налог без #</span><span class="sxs-lookup"><span data-stu-id="15af8-570">tax no#</span></span>
  
<span data-ttu-id="15af8-571">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="15af8-571">taxnumber#</span></span>
  
<span data-ttu-id="15af8-572">такснумбер</span><span class="sxs-lookup"><span data-stu-id="15af8-572">taxnumber</span></span>
  
<span data-ttu-id="15af8-573">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-573">tax id</span></span>
  
<span data-ttu-id="15af8-574">такси #</span><span class="sxs-lookup"><span data-stu-id="15af8-574">taxid#</span></span>
  
<span data-ttu-id="15af8-575">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="15af8-575">tax identification number</span></span>
  
<span data-ttu-id="15af8-576">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="15af8-576">tax identification no.</span></span>
  
<span data-ttu-id="15af8-577">Идентификатор мокесčиų</span><span class="sxs-lookup"><span data-stu-id="15af8-577">mokesčių id</span></span>
  
<span data-ttu-id="15af8-578">мокесčиų нумерис</span><span class="sxs-lookup"><span data-stu-id="15af8-578">mokesčių numeris</span></span>
  
<span data-ttu-id="15af8-579">мокесčиų идентификавимас нумерис</span><span class="sxs-lookup"><span data-stu-id="15af8-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="15af8-580">луксембург</span><span class="sxs-lookup"><span data-stu-id="15af8-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="15af8-581">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-581">Format</span></span>

<span data-ttu-id="15af8-582">13 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-583">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-583">Pattern</span></span>

<span data-ttu-id="15af8-584">13 цифр:</span><span class="sxs-lookup"><span data-stu-id="15af8-584">13 digits:</span></span>
  
-  <span data-ttu-id="15af8-585">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-585">11 digits</span></span> 
    
- <span data-ttu-id="15af8-586">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="15af8-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-587">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-587">Checksum</span></span>

<span data-ttu-id="15af8-588">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-589">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-589">Definition</span></span>

<span data-ttu-id="15af8-590">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-591">Функция `Func_luxemburg_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-592">Найдено ключевое `Keywords_luxemburg_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-593">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-594">Функция `Func_luxemburg_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-595">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="15af8-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-597">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-597">tax number</span></span>
  
<span data-ttu-id="15af8-598">налог но.</span><span class="sxs-lookup"><span data-stu-id="15af8-598">tax no.</span></span>
  
<span data-ttu-id="15af8-599">таксно #</span><span class="sxs-lookup"><span data-stu-id="15af8-599">taxno#</span></span>
  
<span data-ttu-id="15af8-600">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="15af8-600">taxnumber#</span></span>
  
<span data-ttu-id="15af8-601">такснумбер</span><span class="sxs-lookup"><span data-stu-id="15af8-601">taxnumber</span></span>
  
<span data-ttu-id="15af8-602">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-602">tax id</span></span>
  
<span data-ttu-id="15af8-603">такси #</span><span class="sxs-lookup"><span data-stu-id="15af8-603">taxid#</span></span>
  
<span data-ttu-id="15af8-604">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="15af8-604">tax identification number</span></span>
  
<span data-ttu-id="15af8-605">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="15af8-605">tax identification no.</span></span>
  
<span data-ttu-id="15af8-606">стеуернуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-606">steuernummer</span></span>
  
<span data-ttu-id="15af8-607">Идентификатор стеуер</span><span class="sxs-lookup"><span data-stu-id="15af8-607">steuer id</span></span>
  
<span data-ttu-id="15af8-608">стеуеридентификатионснуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="15af8-609">Мальта</span><span class="sxs-lookup"><span data-stu-id="15af8-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="15af8-610">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-610">Format</span></span>

<span data-ttu-id="15af8-611">Для национальных замальтийский: 7 цифр и одна буква в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="15af8-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="15af8-612">Мальтийскийные страны и Мальтийский, не являющиеся субъектами: 9 цифр</span><span class="sxs-lookup"><span data-stu-id="15af8-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-613">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-613">Pattern</span></span>

<span data-ttu-id="15af8-614">Мальтийский национальные условия: 7 цифр и одна буква</span><span class="sxs-lookup"><span data-stu-id="15af8-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="15af8-615">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="15af8-615">Seven digits</span></span> 
    
- <span data-ttu-id="15af8-616">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="15af8-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="15af8-617">Мальтийскийные страны и Мальтийский, не являющиеся субъектами: 9 цифр</span><span class="sxs-lookup"><span data-stu-id="15af8-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="15af8-618">девять цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="15af8-619">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-619">Checksum</span></span>

<span data-ttu-id="15af8-620">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="15af8-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-621">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-621">Definition</span></span>

<span data-ttu-id="15af8-622">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-623">Функция `Func_malta_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-624">Найдено ключевое `Keywords_malta_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-625">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-626">Функция `Func_malta_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-627">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="15af8-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-629">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-629">tax number</span></span>
  
<span data-ttu-id="15af8-630">налог но.</span><span class="sxs-lookup"><span data-stu-id="15af8-630">tax no.</span></span>
  
<span data-ttu-id="15af8-631">таксно #</span><span class="sxs-lookup"><span data-stu-id="15af8-631">taxno#</span></span>
  
<span data-ttu-id="15af8-632">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="15af8-632">taxnumber#</span></span>
  
<span data-ttu-id="15af8-633">такснумбер</span><span class="sxs-lookup"><span data-stu-id="15af8-633">taxnumber</span></span>
  
<span data-ttu-id="15af8-634">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-634">tax id</span></span>
  
<span data-ttu-id="15af8-635">такси #</span><span class="sxs-lookup"><span data-stu-id="15af8-635">taxid#</span></span>
  
<span data-ttu-id="15af8-636">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="15af8-636">tax identification number</span></span>
  
<span data-ttu-id="15af8-637">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="15af8-637">tax identification no.</span></span>
  
<span data-ttu-id="15af8-638">нумру ТАТ — такскса</span><span class="sxs-lookup"><span data-stu-id="15af8-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="15af8-639">ID ТАТ — такскса</span><span class="sxs-lookup"><span data-stu-id="15af8-639">id tat-taxxa</span></span>
  
<span data-ttu-id="15af8-640">нумру Ta ' идентификаззжони ТАТ такскса</span><span class="sxs-lookup"><span data-stu-id="15af8-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="15af8-641">Нидерланды</span><span class="sxs-lookup"><span data-stu-id="15af8-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="15af8-642">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-642">Format</span></span>

<span data-ttu-id="15af8-643">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-644">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-644">Pattern</span></span>

<span data-ttu-id="15af8-645">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="15af8-646">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-646">Checksum</span></span>

<span data-ttu-id="15af8-647">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-648">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-648">Definition</span></span>

<span data-ttu-id="15af8-649">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-650">Функция `Func_netherlands_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-651">Найдено ключевое `Keywords_netherlands_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-652">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-653">Функция `Func_netherlands_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-654">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="15af8-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-656">идентификационный номер налога Нидерландов</span><span class="sxs-lookup"><span data-stu-id="15af8-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="15af8-657">Идентификация налога Нидерландов</span><span class="sxs-lookup"><span data-stu-id="15af8-657">netherlands tax identification</span></span>
  
<span data-ttu-id="15af8-658">идентификационный номер налога несерланд</span><span class="sxs-lookup"><span data-stu-id="15af8-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="15af8-659">Налоговый код несерланд</span><span class="sxs-lookup"><span data-stu-id="15af8-659">netherland's tax identification</span></span>
  
<span data-ttu-id="15af8-660">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="15af8-660">tax identification number</span></span>
  
<span data-ttu-id="15af8-661">Налоговый идентификатор голландского налога</span><span class="sxs-lookup"><span data-stu-id="15af8-661">dutch tax id</span></span>
  
<span data-ttu-id="15af8-662">идентификационный номер налога на нидерландском языке</span><span class="sxs-lookup"><span data-stu-id="15af8-662">dutch tax identification number</span></span>
  
<span data-ttu-id="15af8-663">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-663">tax id</span></span>
  
<span data-ttu-id="15af8-664">Налоговый код #</span><span class="sxs-lookup"><span data-stu-id="15af8-664">tax id#</span></span>
  
<span data-ttu-id="15af8-665">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-665">tax number</span></span>
  
<span data-ttu-id="15af8-666">налог без #</span><span class="sxs-lookup"><span data-stu-id="15af8-666">tax no#</span></span>
  
<span data-ttu-id="15af8-667">см #</span><span class="sxs-lookup"><span data-stu-id="15af8-667">tax#</span></span>
  
<span data-ttu-id="15af8-668">ИНН</span><span class="sxs-lookup"><span data-stu-id="15af8-668">tin</span></span>
  
<span data-ttu-id="15af8-669">ИНН #</span><span class="sxs-lookup"><span data-stu-id="15af8-669">tin#</span></span>
  
<span data-ttu-id="15af8-670">Tin Нидерландов</span><span class="sxs-lookup"><span data-stu-id="15af8-670">netherlands tin</span></span>
  
<span data-ttu-id="15af8-671">Tin несерланд</span><span class="sxs-lookup"><span data-stu-id="15af8-671">netherland's tin</span></span>
  
<span data-ttu-id="15af8-672">Недерландс идентификатиенуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="15af8-673">идентификатиенуммер Van</span><span class="sxs-lookup"><span data-stu-id="15af8-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="15af8-674">идентификатиенуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="15af8-675">Недерландс идентификатие</span><span class="sxs-lookup"><span data-stu-id="15af8-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="15af8-676">Недерландс — идентификатор нуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="15af8-677">Недерландс беластингнуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="15af8-678">БТВ нуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-678">btw nummer</span></span>
  
<span data-ttu-id="15af8-679">Недерландсе идентификатие</span><span class="sxs-lookup"><span data-stu-id="15af8-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="15af8-680">Польша</span><span class="sxs-lookup"><span data-stu-id="15af8-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="15af8-681">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-681">Format</span></span>

<span data-ttu-id="15af8-682">Одиннадцать цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-683">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-683">Pattern</span></span>

<span data-ttu-id="15af8-684">Одиннадцать цифр</span><span class="sxs-lookup"><span data-stu-id="15af8-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="15af8-685">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-685">Checksum</span></span>

<span data-ttu-id="15af8-686">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-687">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-687">Definition</span></span>

<span data-ttu-id="15af8-688">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-689">Функция `Func_poland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-690">Найдено ключевое `Keywords_poland_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-691">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-692">Функция `Func_poland_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-693">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="15af8-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-695">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-695">tax number</span></span>
  
<span data-ttu-id="15af8-696">налог но.</span><span class="sxs-lookup"><span data-stu-id="15af8-696">tax no.</span></span>
  
<span data-ttu-id="15af8-697">таксно #</span><span class="sxs-lookup"><span data-stu-id="15af8-697">taxno#</span></span>
  
<span data-ttu-id="15af8-698">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="15af8-698">taxnumber#</span></span>
  
<span data-ttu-id="15af8-699">такснумбер</span><span class="sxs-lookup"><span data-stu-id="15af8-699">taxnumber</span></span>
  
<span data-ttu-id="15af8-700">нип</span><span class="sxs-lookup"><span data-stu-id="15af8-700">nip</span></span>
  
<span data-ttu-id="15af8-701">нип #</span><span class="sxs-lookup"><span data-stu-id="15af8-701">nip#</span></span>
  
<span data-ttu-id="15af8-702">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-702">tax id</span></span>
  
<span data-ttu-id="15af8-703">Налоговый код #</span><span class="sxs-lookup"><span data-stu-id="15af8-703">tax id#</span></span>
  
<span data-ttu-id="15af8-704">Идентификатор НИП</span><span class="sxs-lookup"><span data-stu-id="15af8-704">nip id</span></span>
  
<span data-ttu-id="15af8-705">Идентификатор НИП #</span><span class="sxs-lookup"><span data-stu-id="15af8-705">nip id#</span></span>
  
<span data-ttu-id="15af8-706">идентификационный номер налога</span><span class="sxs-lookup"><span data-stu-id="15af8-706">tax identification number</span></span>
  
<span data-ttu-id="15af8-707">Налоговый идентификатор</span><span class="sxs-lookup"><span data-stu-id="15af8-707">tax identification no.</span></span>
  
<span data-ttu-id="15af8-708">номер НДС</span><span class="sxs-lookup"><span data-stu-id="15af8-708">vat number</span></span>
  
<span data-ttu-id="15af8-709">НДС номер</span><span class="sxs-lookup"><span data-stu-id="15af8-709">vat no.</span></span>
  
<span data-ttu-id="15af8-710">ватно #</span><span class="sxs-lookup"><span data-stu-id="15af8-710">vatno#</span></span>
  
<span data-ttu-id="15af8-711">Код НДС</span><span class="sxs-lookup"><span data-stu-id="15af8-711">vat id</span></span>
  
<span data-ttu-id="15af8-712">Код НДС #</span><span class="sxs-lookup"><span data-stu-id="15af8-712">vat id#</span></span>
  
<span data-ttu-id="15af8-713">Нумер идентификакжи податковеж</span><span class="sxs-lookup"><span data-stu-id="15af8-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="15af8-714">полски нумер идентификакжи податковеж</span><span class="sxs-lookup"><span data-stu-id="15af8-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="15af8-715">нумеридентификакжиподатковеж #</span><span class="sxs-lookup"><span data-stu-id="15af8-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="15af8-716">Португалия</span><span class="sxs-lookup"><span data-stu-id="15af8-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="15af8-717">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-717">Format</span></span>

<span data-ttu-id="15af8-718">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-719">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-719">Pattern</span></span>

<span data-ttu-id="15af8-720">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="15af8-721">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-721">Checksum</span></span>

<span data-ttu-id="15af8-722">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-723">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-723">Definition</span></span>

<span data-ttu-id="15af8-724">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-725">Функция `Func_portugal_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-726">Найдено ключевое `Keywords_portugal_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-727">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-728">Функция `Func_portugal_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-729">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="15af8-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-731">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-731">tax number</span></span>
  
<span data-ttu-id="15af8-732">налог но.</span><span class="sxs-lookup"><span data-stu-id="15af8-732">tax no.</span></span>
  
<span data-ttu-id="15af8-733">таксно #</span><span class="sxs-lookup"><span data-stu-id="15af8-733">taxno#</span></span>
  
<span data-ttu-id="15af8-734">такснумбер #</span><span class="sxs-lookup"><span data-stu-id="15af8-734">taxnumber#</span></span>
  
<span data-ttu-id="15af8-735">такснумбер</span><span class="sxs-lookup"><span data-stu-id="15af8-735">taxnumber</span></span>
  
<span data-ttu-id="15af8-736">включена</span><span class="sxs-lookup"><span data-stu-id="15af8-736">nif</span></span>
  
<span data-ttu-id="15af8-737">включена #</span><span class="sxs-lookup"><span data-stu-id="15af8-737">nif#</span></span>
  
<span data-ttu-id="15af8-738">финансовый нумеро</span><span class="sxs-lookup"><span data-stu-id="15af8-738">numero fiscal</span></span>
  
<span data-ttu-id="15af8-739">нúмеро de идентификаçãо Фин.</span><span class="sxs-lookup"><span data-stu-id="15af8-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="15af8-740">Румыния</span><span class="sxs-lookup"><span data-stu-id="15af8-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="15af8-741">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-741">Format</span></span>

<span data-ttu-id="15af8-742">13 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-743">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-743">Pattern</span></span>

<span data-ttu-id="15af8-744">13 цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="15af8-745">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-745">Checksum</span></span>

<span data-ttu-id="15af8-746">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="15af8-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-747">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-747">Definition</span></span>

<span data-ttu-id="15af8-748">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-749">Регулярное выражение `Regex_romania_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-750">Найдено ключевое `Keywords_romania_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="15af8-751">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="15af8-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-753">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-753">tax id</span></span>
  
<span data-ttu-id="15af8-754">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="15af8-754">tax id number</span></span>
  
<span data-ttu-id="15af8-755">Налоговый файл нет</span><span class="sxs-lookup"><span data-stu-id="15af8-755">tax file no</span></span>
  
<span data-ttu-id="15af8-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="15af8-756">tax file number</span></span>
  
<span data-ttu-id="15af8-757">налог без</span><span class="sxs-lookup"><span data-stu-id="15af8-757">tax no</span></span>
  
<span data-ttu-id="15af8-758">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-758">tax number</span></span>
  
<span data-ttu-id="15af8-759">такси #</span><span class="sxs-lookup"><span data-stu-id="15af8-759">taxid#</span></span>
  
<span data-ttu-id="15af8-760">таксно #</span><span class="sxs-lookup"><span data-stu-id="15af8-760">taxno#</span></span>
  
<span data-ttu-id="15af8-761">ID — UL таксеи</span><span class="sxs-lookup"><span data-stu-id="15af8-761">id-ul taxei</span></span>
  
<span data-ttu-id="15af8-762">нумăрул де идентификаре фискалă</span><span class="sxs-lookup"><span data-stu-id="15af8-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="15af8-763">Словакия</span><span class="sxs-lookup"><span data-stu-id="15af8-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="15af8-764">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-764">Format</span></span>

<span data-ttu-id="15af8-765">10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-766">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-766">Pattern</span></span>

<span data-ttu-id="15af8-767">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="15af8-768">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-768">Checksum</span></span>

<span data-ttu-id="15af8-769">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="15af8-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-770">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-770">Definition</span></span>

<span data-ttu-id="15af8-771">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-772">Регулярное выражение `Regex_slovakia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-773">Найдено ключевое `Keywords_slovakia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="15af8-774">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="15af8-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-776">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-776">tax id</span></span>
  
<span data-ttu-id="15af8-777">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="15af8-777">tax id number</span></span>
  
<span data-ttu-id="15af8-778">Идентификатор Tin</span><span class="sxs-lookup"><span data-stu-id="15af8-778">tin id</span></span>
  
<span data-ttu-id="15af8-779">номер Tin</span><span class="sxs-lookup"><span data-stu-id="15af8-779">tin no</span></span>
  
<span data-ttu-id="15af8-780">Идентификатор Tin словакиан</span><span class="sxs-lookup"><span data-stu-id="15af8-780">slovakian tin id</span></span>
  
<span data-ttu-id="15af8-781">ИНН</span><span class="sxs-lookup"><span data-stu-id="15af8-781">tin</span></span>
  
<span data-ttu-id="15af8-782">Налоговый файл нет</span><span class="sxs-lookup"><span data-stu-id="15af8-782">tax file no</span></span>
  
<span data-ttu-id="15af8-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="15af8-783">tax file number</span></span>
  
<span data-ttu-id="15af8-784">налог без</span><span class="sxs-lookup"><span data-stu-id="15af8-784">tax no</span></span>
  
<span data-ttu-id="15af8-785">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-785">tax number</span></span>
  
<span data-ttu-id="15af8-786">такси #</span><span class="sxs-lookup"><span data-stu-id="15af8-786">taxid#</span></span>
  
<span data-ttu-id="15af8-787">таксно #</span><span class="sxs-lookup"><span data-stu-id="15af8-787">taxno#</span></span>
  
<span data-ttu-id="15af8-788">даňовé идентификаčнé číсло</span><span class="sxs-lookup"><span data-stu-id="15af8-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="15af8-789">даňовé číсло</span><span class="sxs-lookup"><span data-stu-id="15af8-789">daňové číslo</span></span>
  
<span data-ttu-id="15af8-790">даňовé číсло сúбору</span><span class="sxs-lookup"><span data-stu-id="15af8-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="15af8-791">Словения</span><span class="sxs-lookup"><span data-stu-id="15af8-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="15af8-792">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-792">Format</span></span>

<span data-ttu-id="15af8-793">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-794">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-794">Pattern</span></span>

<span data-ttu-id="15af8-795">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="15af8-796">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-796">Checksum</span></span>

<span data-ttu-id="15af8-797">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-798">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-798">Definition</span></span>

<span data-ttu-id="15af8-799">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-800">Функция `Func_slovenia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-801">Найдено ключевое `Keywords_slovenia_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-802">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-803">Функция `Func_slovenia_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-804">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="15af8-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-806">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-806">tax id</span></span>
  
<span data-ttu-id="15af8-807">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="15af8-807">tax id number</span></span>
  
<span data-ttu-id="15af8-808">Идентификатор Tin</span><span class="sxs-lookup"><span data-stu-id="15af8-808">tin id</span></span>
  
<span data-ttu-id="15af8-809">номер Tin</span><span class="sxs-lookup"><span data-stu-id="15af8-809">tin no</span></span>
  
<span data-ttu-id="15af8-810">Словенский идентификатор Tin</span><span class="sxs-lookup"><span data-stu-id="15af8-810">slovenian tin id</span></span>
  
<span data-ttu-id="15af8-811">ИНН</span><span class="sxs-lookup"><span data-stu-id="15af8-811">tin</span></span>
  
<span data-ttu-id="15af8-812">Налоговый файл нет</span><span class="sxs-lookup"><span data-stu-id="15af8-812">tax file no</span></span>
  
<span data-ttu-id="15af8-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="15af8-813">tax file number</span></span>
  
<span data-ttu-id="15af8-814">налог без</span><span class="sxs-lookup"><span data-stu-id="15af8-814">tax no</span></span>
  
<span data-ttu-id="15af8-815">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-815">tax number</span></span>
  
<span data-ttu-id="15af8-816">такси #</span><span class="sxs-lookup"><span data-stu-id="15af8-816">taxid#</span></span>
  
<span data-ttu-id="15af8-817">таксно #</span><span class="sxs-lookup"><span data-stu-id="15af8-817">taxno#</span></span>
  
<span data-ttu-id="15af8-818">идентификаЦижска šтевилка Давка</span><span class="sxs-lookup"><span data-stu-id="15af8-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="15af8-819">давčна šтевилка</span><span class="sxs-lookup"><span data-stu-id="15af8-819">davčna številka</span></span>
  
<span data-ttu-id="15af8-820">šтевилка давčне датотеке</span><span class="sxs-lookup"><span data-stu-id="15af8-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="15af8-821">Испания</span><span class="sxs-lookup"><span data-stu-id="15af8-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="15af8-822">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-822">Format</span></span>

<span data-ttu-id="15af8-823">Семь или восемь цифр, а также одна или две буквы в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="15af8-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-824">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-824">Pattern</span></span>

<span data-ttu-id="15af8-825">Испанские пользователи с национальной идентификационной карточкой Испании Испания:</span><span class="sxs-lookup"><span data-stu-id="15af8-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="15af8-826">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="15af8-826">Eight digits</span></span> 
    
- <span data-ttu-id="15af8-827">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="15af8-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="15af8-828">Нерезидентские Спаниардс без национальной идентификационной карточки Испании</span><span class="sxs-lookup"><span data-stu-id="15af8-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="15af8-829">Одна прописная буква L (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="15af8-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="15af8-830">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="15af8-830">Seven digits</span></span>
    
- <span data-ttu-id="15af8-831">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="15af8-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="15af8-832">Резидентный Спаниардс в течение 14 лет без международной идентификационной карточки для Испании:</span><span class="sxs-lookup"><span data-stu-id="15af8-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="15af8-833">Одна прописная буква K (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="15af8-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="15af8-834">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="15af8-834">Seven digits</span></span> 
    
- <span data-ttu-id="15af8-835">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="15af8-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="15af8-836">Фореигнерс с идентификационным номером внешнего получателя</span><span class="sxs-lookup"><span data-stu-id="15af8-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="15af8-837">Одна прописная буква "X", "Y" или "Z" (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="15af8-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="15af8-838">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="15af8-838">Seven digits</span></span>
    
- <span data-ttu-id="15af8-839">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="15af8-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="15af8-840">Фореигнерс без идентификационного номера внешнего получателя</span><span class="sxs-lookup"><span data-stu-id="15af8-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="15af8-841">Одна прописная буква "M" (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="15af8-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="15af8-842">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="15af8-842">Seven digits</span></span>
    
- <span data-ttu-id="15af8-843">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="15af8-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="15af8-844">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-844">Checksum</span></span>

<span data-ttu-id="15af8-845">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-846">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-846">Definition</span></span>

<span data-ttu-id="15af8-847">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-848">Функция `Func_spain_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-849">Найдено ключевое `Keywords_spain_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-850">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-851">Функция `Func_spain_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-852">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="15af8-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-854">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-854">tax id</span></span>
  
<span data-ttu-id="15af8-855">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="15af8-855">tax id number</span></span>
  
<span data-ttu-id="15af8-856">Идентификатор CIF</span><span class="sxs-lookup"><span data-stu-id="15af8-856">cif id</span></span>
  
<span data-ttu-id="15af8-857">CIF нет</span><span class="sxs-lookup"><span data-stu-id="15af8-857">cif no</span></span>
  
<span data-ttu-id="15af8-858">код испанского CIF</span><span class="sxs-lookup"><span data-stu-id="15af8-858">spanish cif id</span></span>
  
<span data-ttu-id="15af8-859">CIF</span><span class="sxs-lookup"><span data-stu-id="15af8-859">cif</span></span>
  
<span data-ttu-id="15af8-860">Налоговый файл нет</span><span class="sxs-lookup"><span data-stu-id="15af8-860">tax file no</span></span>
  
<span data-ttu-id="15af8-861">номер испанского CIF</span><span class="sxs-lookup"><span data-stu-id="15af8-861">spanish cif number</span></span>
  
<span data-ttu-id="15af8-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="15af8-862">tax file number</span></span>
  
<span data-ttu-id="15af8-863">Испанская CIF</span><span class="sxs-lookup"><span data-stu-id="15af8-863">spanish cif no</span></span>
  
<span data-ttu-id="15af8-864">налог без</span><span class="sxs-lookup"><span data-stu-id="15af8-864">tax no</span></span>
  
<span data-ttu-id="15af8-865">Налоговый номер</span><span class="sxs-lookup"><span data-stu-id="15af8-865">tax number</span></span>
  
<span data-ttu-id="15af8-866">такси #</span><span class="sxs-lookup"><span data-stu-id="15af8-866">taxid#</span></span>
  
<span data-ttu-id="15af8-867">таксно #</span><span class="sxs-lookup"><span data-stu-id="15af8-867">taxno#</span></span>
  
<span data-ttu-id="15af8-868">Цифид #</span><span class="sxs-lookup"><span data-stu-id="15af8-868">cifid#</span></span>
  
<span data-ttu-id="15af8-869">спанишЦифид #</span><span class="sxs-lookup"><span data-stu-id="15af8-869">spanishcifid#</span></span>
  
<span data-ttu-id="15af8-870">спанишЦифно #</span><span class="sxs-lookup"><span data-stu-id="15af8-870">spanishcifno#</span></span>
  
<span data-ttu-id="15af8-871">нúмеро de контрибуйенте</span><span class="sxs-lookup"><span data-stu-id="15af8-871">número de contribuyente</span></span>
  
<span data-ttu-id="15af8-872">нúмеро де импуесто корпоративо</span><span class="sxs-lookup"><span data-stu-id="15af8-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="15af8-873">нúмеро de идентификаЦиóн Фин.</span><span class="sxs-lookup"><span data-stu-id="15af8-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="15af8-874">CIF нúмеро</span><span class="sxs-lookup"><span data-stu-id="15af8-874">cif número</span></span>
  
<span data-ttu-id="15af8-875">Цифнúмеро #</span><span class="sxs-lookup"><span data-stu-id="15af8-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="15af8-876">Швеция</span><span class="sxs-lookup"><span data-stu-id="15af8-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="15af8-877">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-877">Format</span></span>

<span data-ttu-id="15af8-878">Десять цифр и символ в указанном шаблоне;</span><span class="sxs-lookup"><span data-stu-id="15af8-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-879">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-879">Pattern</span></span>

<span data-ttu-id="15af8-880">Десять цифр и символ:</span><span class="sxs-lookup"><span data-stu-id="15af8-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="15af8-881">Шесть цифр, соответствующих дате рождения (ГГММДД)</span><span class="sxs-lookup"><span data-stu-id="15af8-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="15af8-882">Знак плюс, знак минус или обратная косая черта</span><span class="sxs-lookup"><span data-stu-id="15af8-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="15af8-883">Три цифры, которые делают идентификационный номер уникальным, где:</span><span class="sxs-lookup"><span data-stu-id="15af8-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="15af8-884">Для номеров, выпущенных до 1990, седьмой и восьмой цифрой определяют район рождения или пользователей, порожденных иностранным пользователем.</span><span class="sxs-lookup"><span data-stu-id="15af8-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="15af8-885">Цифра в девятой позиции указывает на пол, который нечетен для пола или даже для розетки.</span><span class="sxs-lookup"><span data-stu-id="15af8-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="15af8-886">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="15af8-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="15af8-887">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-887">Checksum</span></span>

<span data-ttu-id="15af8-888">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-889">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-889">Definition</span></span>

<span data-ttu-id="15af8-890">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-891">Функция `Func_sweden_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-892">Найдено ключевое `Keywords_sweden_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="15af8-893">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-894">Функция `Func_sweden_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="15af8-895">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="15af8-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-897">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-897">tax id</span></span>
  
<span data-ttu-id="15af8-898">Налоговый код но.</span><span class="sxs-lookup"><span data-stu-id="15af8-898">tax id no.</span></span>
  
<span data-ttu-id="15af8-899">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="15af8-899">tax id number</span></span>
  
<span data-ttu-id="15af8-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="15af8-900">tax identification</span></span>
  
<span data-ttu-id="15af8-901">Идентификация налога #</span><span class="sxs-lookup"><span data-stu-id="15af8-901">tax identification#</span></span>
  
<span data-ttu-id="15af8-902">налог но.</span><span class="sxs-lookup"><span data-stu-id="15af8-902">tax no.</span></span>
  
<span data-ttu-id="15af8-903">см #</span><span class="sxs-lookup"><span data-stu-id="15af8-903">tax#</span></span>
  
<span data-ttu-id="15af8-904">такси #</span><span class="sxs-lookup"><span data-stu-id="15af8-904">taxid#</span></span>
  
<span data-ttu-id="15af8-905">Налоговый файл</span><span class="sxs-lookup"><span data-stu-id="15af8-905">tax file</span></span>
  
<span data-ttu-id="15af8-906">Налоговый файл но.</span><span class="sxs-lookup"><span data-stu-id="15af8-906">tax file no.</span></span>
  
<span data-ttu-id="15af8-907">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="15af8-907">personal id number</span></span>
  
<span data-ttu-id="15af8-908">Идентификатор СКАТТ нуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-908">skatt id nummer</span></span>
  
<span data-ttu-id="15af8-909">СКАТТ идентификатион</span><span class="sxs-lookup"><span data-stu-id="15af8-909">skatt identifikation</span></span>
  
<span data-ttu-id="15af8-910">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="15af8-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="15af8-911">ВОЗМЕЩЕН</span><span class="sxs-lookup"><span data-stu-id="15af8-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="15af8-912">Format</span><span class="sxs-lookup"><span data-stu-id="15af8-912">Format</span></span>

<span data-ttu-id="15af8-913">Уникальная справочная информация о налогоплательщиках (утр): 10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="15af8-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="15af8-914">Национальный страховой номер (Нино): Дополнительные сведения см. в разделе "Великобритания</span><span class="sxs-lookup"><span data-stu-id="15af8-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="15af8-915">Национальный страховой номер (Нино) " [, чтобы найти типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="15af8-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="15af8-916">Шаблон</span><span class="sxs-lookup"><span data-stu-id="15af8-916">Pattern</span></span>

<span data-ttu-id="15af8-917">Уникальная справочная информация о налогоплательщиках (утр): 10 цифр</span><span class="sxs-lookup"><span data-stu-id="15af8-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="15af8-918">Национальный страховой номер (Нино): Дополнительные сведения см. в разделе "Великобритания</span><span class="sxs-lookup"><span data-stu-id="15af8-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="15af8-919">Национальный страховой номер (Нино) " [, чтобы найти типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="15af8-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="15af8-920">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="15af8-920">Checksum</span></span>

<span data-ttu-id="15af8-921">Да</span><span class="sxs-lookup"><span data-stu-id="15af8-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="15af8-922">Определение</span><span class="sxs-lookup"><span data-stu-id="15af8-922">Definition</span></span>

<span data-ttu-id="15af8-923">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="15af8-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="15af8-924">Функция `Func_uk_eu_tax_file_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="15af8-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="15af8-925">Найдено ключевое `Keywords_uk_eu_tax_file_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="15af8-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="15af8-926">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="15af8-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="15af8-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="15af8-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="15af8-928">tax id</span><span class="sxs-lookup"><span data-stu-id="15af8-928">tax id</span></span>
  
<span data-ttu-id="15af8-929">Налоговый код но.</span><span class="sxs-lookup"><span data-stu-id="15af8-929">tax id no.</span></span>
  
<span data-ttu-id="15af8-930">номер налогового удостоверения</span><span class="sxs-lookup"><span data-stu-id="15af8-930">tax id number</span></span>
  
<span data-ttu-id="15af8-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="15af8-931">tax identification</span></span>
  
<span data-ttu-id="15af8-932">Идентификация налога #</span><span class="sxs-lookup"><span data-stu-id="15af8-932">tax identification#</span></span>
  
<span data-ttu-id="15af8-933">налог но.</span><span class="sxs-lookup"><span data-stu-id="15af8-933">tax no.</span></span>
  
<span data-ttu-id="15af8-934">см #</span><span class="sxs-lookup"><span data-stu-id="15af8-934">tax#</span></span>
  
<span data-ttu-id="15af8-935">такси #</span><span class="sxs-lookup"><span data-stu-id="15af8-935">taxid#</span></span>
  
<span data-ttu-id="15af8-936">Налоговый файл</span><span class="sxs-lookup"><span data-stu-id="15af8-936">tax file</span></span>
  
<span data-ttu-id="15af8-937">Налоговый файл но.</span><span class="sxs-lookup"><span data-stu-id="15af8-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="15af8-938">См. также</span><span class="sxs-lookup"><span data-stu-id="15af8-938">See also</span></span>

[<span data-ttu-id="15af8-939">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="15af8-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

