---
title: Номер социального страхования ЕС или эквивалентный идентификатор
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
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает номер социального страхования ЕС или эквивалентный тип конфиденциальной информации. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: 1f2d1d9c61f27fb47b0c7ac0ce544b17175d4254
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "41591230"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="95cdc-104">Номер социального страхования ЕС или эквивалентный идентификатор</span><span class="sxs-lookup"><span data-stu-id="95cdc-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="95cdc-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС или эквивалентный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="95cdc-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="95cdc-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="95cdc-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="95cdc-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="95cdc-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="95cdc-108">Format</span><span class="sxs-lookup"><span data-stu-id="95cdc-108">Format</span></span>

<span data-ttu-id="95cdc-109">10 цифр в указанном формате</span><span class="sxs-lookup"><span data-stu-id="95cdc-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="95cdc-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="95cdc-110">Pattern</span></span>

<span data-ttu-id="95cdc-111">10 цифр:</span><span class="sxs-lookup"><span data-stu-id="95cdc-111">10 digits:</span></span>
  
-  <span data-ttu-id="95cdc-112">Три цифры, соответствующие серийному номеру.</span><span class="sxs-lookup"><span data-stu-id="95cdc-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="95cdc-113">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="95cdc-113">One check digit</span></span>
    
- <span data-ttu-id="95cdc-114">Шесть цифр, соответствующих дате рождения (ДДММГГ —)</span><span class="sxs-lookup"><span data-stu-id="95cdc-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="95cdc-115">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="95cdc-115">Checksum</span></span>

<span data-ttu-id="95cdc-116">Да</span><span class="sxs-lookup"><span data-stu-id="95cdc-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="95cdc-117">Определение</span><span class="sxs-lookup"><span data-stu-id="95cdc-117">Definition</span></span>

<span data-ttu-id="95cdc-118">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-119">Функция `Func_austria_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="95cdc-120">Найдено ключевое `Keywords_austria_eu_ssn_or_equivalent` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="95cdc-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="95cdc-121">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-122">Функция `Func_austria_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cdc-123">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="95cdc-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="95cdc-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="95cdc-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="95cdc-125">социальное страхование нет</span><span class="sxs-lookup"><span data-stu-id="95cdc-125">social security no</span></span>
  
<span data-ttu-id="95cdc-126">social security number</span><span class="sxs-lookup"><span data-stu-id="95cdc-126">social security number</span></span>
  
<span data-ttu-id="95cdc-127">social security code</span><span class="sxs-lookup"><span data-stu-id="95cdc-127">social security code</span></span>
  
<span data-ttu-id="95cdc-128">страховой номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-128">insurance number</span></span>
  
<span data-ttu-id="95cdc-129">Австрийский SSN</span><span class="sxs-lookup"><span data-stu-id="95cdc-129">austrian ssn</span></span>
  
<span data-ttu-id="95cdc-130">SSN #</span><span class="sxs-lookup"><span data-stu-id="95cdc-130">ssn#</span></span>
  
<span data-ttu-id="95cdc-131">SSN</span><span class="sxs-lookup"><span data-stu-id="95cdc-131">ssn</span></span>
  
<span data-ttu-id="95cdc-132">код страхования</span><span class="sxs-lookup"><span data-stu-id="95cdc-132">insurance code</span></span>
  
<span data-ttu-id="95cdc-133">код страхования #</span><span class="sxs-lookup"><span data-stu-id="95cdc-133">insurance code#</span></span>
  
<span data-ttu-id="95cdc-134">соЦиалсекуритино #</span><span class="sxs-lookup"><span data-stu-id="95cdc-134">socialsecurityno#</span></span>
  
<span data-ttu-id="95cdc-135">созиалверсичерунгснуммер</span><span class="sxs-lookup"><span data-stu-id="95cdc-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="95cdc-136">созиале сичерхеит Кеин</span><span class="sxs-lookup"><span data-stu-id="95cdc-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="95cdc-137">версичерунгснуммер</span><span class="sxs-lookup"><span data-stu-id="95cdc-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="95cdc-138">Бельгия</span><span class="sxs-lookup"><span data-stu-id="95cdc-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="95cdc-139">Format</span><span class="sxs-lookup"><span data-stu-id="95cdc-139">Format</span></span>

<span data-ttu-id="95cdc-140">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="95cdc-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="95cdc-141">Шаблон</span><span class="sxs-lookup"><span data-stu-id="95cdc-141">Pattern</span></span>

<span data-ttu-id="95cdc-142">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="95cdc-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="95cdc-143">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="95cdc-143">Checksum</span></span>

<span data-ttu-id="95cdc-144">Да</span><span class="sxs-lookup"><span data-stu-id="95cdc-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="95cdc-145">Определение</span><span class="sxs-lookup"><span data-stu-id="95cdc-145">Definition</span></span>

<span data-ttu-id="95cdc-146">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-147">Функция `Func_belgium_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="95cdc-148">Найдено ключевое `Keywords_belgium_eu_ssn_or_equivalent` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="95cdc-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="95cdc-149">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-150">Функция `Func_belgium_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cdc-151">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="95cdc-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="95cdc-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="95cdc-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="95cdc-153">Бельгийский национальный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-153">belgian national number</span></span>
  
<span data-ttu-id="95cdc-154">номер страны</span><span class="sxs-lookup"><span data-stu-id="95cdc-154">national number</span></span>
  
<span data-ttu-id="95cdc-155">social security number</span><span class="sxs-lookup"><span data-stu-id="95cdc-155">social security number</span></span>
  
<span data-ttu-id="95cdc-156">натионалнумбер #</span><span class="sxs-lookup"><span data-stu-id="95cdc-156">nationalnumber#</span></span>
  
<span data-ttu-id="95cdc-157">SSN #</span><span class="sxs-lookup"><span data-stu-id="95cdc-157">ssn#</span></span>
  
<span data-ttu-id="95cdc-158">SSN</span><span class="sxs-lookup"><span data-stu-id="95cdc-158">ssn</span></span>
  
<span data-ttu-id="95cdc-159">натионалнумбер</span><span class="sxs-lookup"><span data-stu-id="95cdc-159">nationalnumber</span></span>
  
<span data-ttu-id="95cdc-160">бнн #</span><span class="sxs-lookup"><span data-stu-id="95cdc-160">bnn#</span></span>
  
<span data-ttu-id="95cdc-161">бнн</span><span class="sxs-lookup"><span data-stu-id="95cdc-161">bnn</span></span>
  
<span data-ttu-id="95cdc-162">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-162">personal id number</span></span>
  
<span data-ttu-id="95cdc-163">персоналиднумбер #</span><span class="sxs-lookup"><span data-stu-id="95cdc-163">personalidnumber#</span></span>
  
<span data-ttu-id="95cdc-164">Национальный нумéро</span><span class="sxs-lookup"><span data-stu-id="95cdc-164">numéro national</span></span>
  
<span data-ttu-id="95cdc-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="95cdc-165">numéro de sécurité</span></span>
  
<span data-ttu-id="95cdc-166">нумéро д'ассурé</span><span class="sxs-lookup"><span data-stu-id="95cdc-166">numéro d'assuré</span></span>
  
<span data-ttu-id="95cdc-167">Идентификация National</span><span class="sxs-lookup"><span data-stu-id="95cdc-167">identifiant national</span></span>
  
<span data-ttu-id="95cdc-168">идентифиантнатионал #</span><span class="sxs-lookup"><span data-stu-id="95cdc-168">identifiantnational#</span></span>
  
<span data-ttu-id="95cdc-169">нумéронатионал #</span><span class="sxs-lookup"><span data-stu-id="95cdc-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="95cdc-170">Хорватия</span><span class="sxs-lookup"><span data-stu-id="95cdc-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="95cdc-171">Format</span><span class="sxs-lookup"><span data-stu-id="95cdc-171">Format</span></span>

<span data-ttu-id="95cdc-172">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="95cdc-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="95cdc-173">Шаблон</span><span class="sxs-lookup"><span data-stu-id="95cdc-173">Pattern</span></span>

 <span data-ttu-id="95cdc-174">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="95cdc-174">11 digits:</span></span> 
  
-  <span data-ttu-id="95cdc-175">Десять цифр</span><span class="sxs-lookup"><span data-stu-id="95cdc-175">Ten digits</span></span> 
    
- <span data-ttu-id="95cdc-176">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="95cdc-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="95cdc-177">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="95cdc-177">Checksum</span></span>

<span data-ttu-id="95cdc-178">Да</span><span class="sxs-lookup"><span data-stu-id="95cdc-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="95cdc-179">Определение</span><span class="sxs-lookup"><span data-stu-id="95cdc-179">Definition</span></span>

<span data-ttu-id="95cdc-180">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-181">Функция `Func_croatia_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="95cdc-182">Найдено ключевое `Keywords_croatia_eu_ssn_or_equivalent` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="95cdc-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="95cdc-183">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-184">Функция `Func_croatia_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cdc-185">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="95cdc-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="95cdc-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="95cdc-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="95cdc-187">персональный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-187">personal identification number</span></span>
  
<span data-ttu-id="95cdc-188">основной номер в соотношении</span><span class="sxs-lookup"><span data-stu-id="95cdc-188">master citizen number</span></span>
  
<span data-ttu-id="95cdc-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="95cdc-189">national identification number</span></span>
  
<span data-ttu-id="95cdc-190">social security number</span><span class="sxs-lookup"><span data-stu-id="95cdc-190">social security number</span></span>
  
<span data-ttu-id="95cdc-191">натионалнумбер #</span><span class="sxs-lookup"><span data-stu-id="95cdc-191">nationalnumber#</span></span>
  
<span data-ttu-id="95cdc-192">SSN #</span><span class="sxs-lookup"><span data-stu-id="95cdc-192">ssn#</span></span>
  
<span data-ttu-id="95cdc-193">SSN</span><span class="sxs-lookup"><span data-stu-id="95cdc-193">ssn</span></span>
  
<span data-ttu-id="95cdc-194">натионалнумбер</span><span class="sxs-lookup"><span data-stu-id="95cdc-194">nationalnumber</span></span>
  
<span data-ttu-id="95cdc-195">бнн #</span><span class="sxs-lookup"><span data-stu-id="95cdc-195">bnn#</span></span>
  
<span data-ttu-id="95cdc-196">бнн</span><span class="sxs-lookup"><span data-stu-id="95cdc-196">bnn</span></span>
  
<span data-ttu-id="95cdc-197">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-197">personal id number</span></span>
  
<span data-ttu-id="95cdc-198">персоналиднумбер #</span><span class="sxs-lookup"><span data-stu-id="95cdc-198">personalidnumber#</span></span>
  
<span data-ttu-id="95cdc-199">OIB</span><span class="sxs-lookup"><span data-stu-id="95cdc-199">oib</span></span>
  
<span data-ttu-id="95cdc-200">особни идентификаЦижски Брож</span><span class="sxs-lookup"><span data-stu-id="95cdc-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="95cdc-201">Чехия</span><span class="sxs-lookup"><span data-stu-id="95cdc-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="95cdc-202">Format</span><span class="sxs-lookup"><span data-stu-id="95cdc-202">Format</span></span>

<span data-ttu-id="95cdc-203">Десять цифр и обратная косая черта в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="95cdc-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="95cdc-204">Шаблон</span><span class="sxs-lookup"><span data-stu-id="95cdc-204">Pattern</span></span>

<span data-ttu-id="95cdc-205">Десять цифр и обратная косая черта:</span><span class="sxs-lookup"><span data-stu-id="95cdc-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="95cdc-206">Шесть цифр, соответствующих дате рождения (ГГММДД):</span><span class="sxs-lookup"><span data-stu-id="95cdc-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="95cdc-207">Обратная косая черта</span><span class="sxs-lookup"><span data-stu-id="95cdc-207">A backslash</span></span>
    
- <span data-ttu-id="95cdc-208">Три цифры, которые соответствуют серийному номеру, которые отделяют пользователей на одну и ту же дату.</span><span class="sxs-lookup"><span data-stu-id="95cdc-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="95cdc-209">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="95cdc-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="95cdc-210">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="95cdc-210">Checksum</span></span>

<span data-ttu-id="95cdc-211">Да</span><span class="sxs-lookup"><span data-stu-id="95cdc-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="95cdc-212">Определение</span><span class="sxs-lookup"><span data-stu-id="95cdc-212">Definition</span></span>

<span data-ttu-id="95cdc-213">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-214">Функция `Func_czech_republic_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="95cdc-215">Найдено ключевое `Keywords_czech_republic_eu_ssn_or_equivalent` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="95cdc-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="95cdc-216">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-217">Функция `Func_czech_republic_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cdc-218">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="95cdc-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="95cdc-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="95cdc-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="95cdc-220">номер рождения</span><span class="sxs-lookup"><span data-stu-id="95cdc-220">birth number</span></span>
  
<span data-ttu-id="95cdc-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="95cdc-221">national identification number</span></span>
  
<span data-ttu-id="95cdc-222">персональный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-222">personal identification number</span></span>
  
<span data-ttu-id="95cdc-223">social security number</span><span class="sxs-lookup"><span data-stu-id="95cdc-223">social security number</span></span>
  
<span data-ttu-id="95cdc-224">натионалнумбер #</span><span class="sxs-lookup"><span data-stu-id="95cdc-224">nationalnumber#</span></span>
  
<span data-ttu-id="95cdc-225">SSN #</span><span class="sxs-lookup"><span data-stu-id="95cdc-225">ssn#</span></span>
  
<span data-ttu-id="95cdc-226">SSN</span><span class="sxs-lookup"><span data-stu-id="95cdc-226">ssn</span></span>
  
<span data-ttu-id="95cdc-227">номер страны</span><span class="sxs-lookup"><span data-stu-id="95cdc-227">national number</span></span>
  
<span data-ttu-id="95cdc-228">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-228">personal id number</span></span>
  
<span data-ttu-id="95cdc-229">персоналиднумбер #</span><span class="sxs-lookup"><span data-stu-id="95cdc-229">personalidnumber#</span></span>
  
<span data-ttu-id="95cdc-230">рč</span><span class="sxs-lookup"><span data-stu-id="95cdc-230">rč</span></span>
  
<span data-ttu-id="95cdc-231">роднé číсло</span><span class="sxs-lookup"><span data-stu-id="95cdc-231">rodné číslo</span></span>
  
<span data-ttu-id="95cdc-232">родне Цисло</span><span class="sxs-lookup"><span data-stu-id="95cdc-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="95cdc-233">Дания</span><span class="sxs-lookup"><span data-stu-id="95cdc-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="95cdc-234">Format</span><span class="sxs-lookup"><span data-stu-id="95cdc-234">Format</span></span>

<span data-ttu-id="95cdc-235">Десять цифр и дефис в заданном шаблоне</span><span class="sxs-lookup"><span data-stu-id="95cdc-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="95cdc-236">Шаблон</span><span class="sxs-lookup"><span data-stu-id="95cdc-236">Pattern</span></span>

<span data-ttu-id="95cdc-237">Десять цифр и дефис:</span><span class="sxs-lookup"><span data-stu-id="95cdc-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="95cdc-238">Шесть цифр, соответствующих дате рождения (ДДММГГ —)</span><span class="sxs-lookup"><span data-stu-id="95cdc-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="95cdc-239">дефис;</span><span class="sxs-lookup"><span data-stu-id="95cdc-239">A hyphen</span></span>
    
- <span data-ttu-id="95cdc-240">Четыре цифры, которые соответствуют порядковому номеру</span><span class="sxs-lookup"><span data-stu-id="95cdc-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="95cdc-241">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="95cdc-241">Checksum</span></span>

<span data-ttu-id="95cdc-242">Да</span><span class="sxs-lookup"><span data-stu-id="95cdc-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="95cdc-243">Определение</span><span class="sxs-lookup"><span data-stu-id="95cdc-243">Definition</span></span>

<span data-ttu-id="95cdc-244">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-245">Функция `Func_denmark_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="95cdc-246">Найдено ключевое `Keywords_denmark_eu_ssn_or_equivalent` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="95cdc-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="95cdc-247">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-248">Функция `Func_denmark_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cdc-249">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="95cdc-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="95cdc-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="95cdc-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="95cdc-251">персональный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-251">personal identification number</span></span>
  
<span data-ttu-id="95cdc-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="95cdc-252">national identification number</span></span>
  
<span data-ttu-id="95cdc-253">social security number</span><span class="sxs-lookup"><span data-stu-id="95cdc-253">social security number</span></span>
  
<span data-ttu-id="95cdc-254">натионалнумбер #</span><span class="sxs-lookup"><span data-stu-id="95cdc-254">nationalnumber#</span></span>
  
<span data-ttu-id="95cdc-255">SSN #</span><span class="sxs-lookup"><span data-stu-id="95cdc-255">ssn#</span></span>
  
<span data-ttu-id="95cdc-256">SSN</span><span class="sxs-lookup"><span data-stu-id="95cdc-256">ssn</span></span>
  
<span data-ttu-id="95cdc-257">номер страны</span><span class="sxs-lookup"><span data-stu-id="95cdc-257">national number</span></span>
  
<span data-ttu-id="95cdc-258">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-258">personal id number</span></span>
  
<span data-ttu-id="95cdc-259">персоналиднумбер #</span><span class="sxs-lookup"><span data-stu-id="95cdc-259">personalidnumber#</span></span>
  
<span data-ttu-id="95cdc-260">CPR — нуммер</span><span class="sxs-lookup"><span data-stu-id="95cdc-260">cpr-nummer</span></span>
  
<span data-ttu-id="95cdc-261">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="95cdc-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="95cdc-262">Финляндия</span><span class="sxs-lookup"><span data-stu-id="95cdc-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="95cdc-263">Format</span><span class="sxs-lookup"><span data-stu-id="95cdc-263">Format</span></span>

<span data-ttu-id="95cdc-264">11 символов в указанном формате.</span><span class="sxs-lookup"><span data-stu-id="95cdc-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="95cdc-265">Шаблон</span><span class="sxs-lookup"><span data-stu-id="95cdc-265">Pattern</span></span>

<span data-ttu-id="95cdc-266">Сочетание из 11 символов в указанном формате:</span><span class="sxs-lookup"><span data-stu-id="95cdc-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="95cdc-267">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="95cdc-267">Six digits</span></span> 
    
- <span data-ttu-id="95cdc-268">Один из следующих экземпляров:</span><span class="sxs-lookup"><span data-stu-id="95cdc-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="95cdc-269">Символ "плюс"</span><span class="sxs-lookup"><span data-stu-id="95cdc-269">Plus symbol</span></span>
    
  - <span data-ttu-id="95cdc-270">Символ "минус"</span><span class="sxs-lookup"><span data-stu-id="95cdc-270">Minus symbol</span></span>
    
  - <span data-ttu-id="95cdc-271">Буква "A" (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="95cdc-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="95cdc-272">Три цифры</span><span class="sxs-lookup"><span data-stu-id="95cdc-272">Three digits</span></span>
    
- <span data-ttu-id="95cdc-273">Одна буква или одна цифра</span><span class="sxs-lookup"><span data-stu-id="95cdc-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="95cdc-274">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="95cdc-274">Checksum</span></span>

<span data-ttu-id="95cdc-275">Да</span><span class="sxs-lookup"><span data-stu-id="95cdc-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="95cdc-276">Определение</span><span class="sxs-lookup"><span data-stu-id="95cdc-276">Definition</span></span>

<span data-ttu-id="95cdc-277">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-278">Функция `Func_finland_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="95cdc-279">Найдено ключевое `Keywords_finland_eu_ssn_or_equivalent` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="95cdc-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="95cdc-280">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-281">Функция `Func_finland_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cdc-282">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="95cdc-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="95cdc-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="95cdc-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="95cdc-284">identification number</span><span class="sxs-lookup"><span data-stu-id="95cdc-284">identification number</span></span>
  
<span data-ttu-id="95cdc-285">личный идентификатор</span><span class="sxs-lookup"><span data-stu-id="95cdc-285">personal id</span></span>
  
<span data-ttu-id="95cdc-286">идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-286">identity number</span></span>
  
<span data-ttu-id="95cdc-287">Финский национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-287">finnish national id number</span></span>
  
<span data-ttu-id="95cdc-288">персоналиднумбер #</span><span class="sxs-lookup"><span data-stu-id="95cdc-288">personalidnumber#</span></span>
  
<span data-ttu-id="95cdc-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="95cdc-289">national identification number</span></span>
  
<span data-ttu-id="95cdc-290">идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-290">id number</span></span>
  
<span data-ttu-id="95cdc-291">код страны</span><span class="sxs-lookup"><span data-stu-id="95cdc-291">national id no.</span></span>
  
<span data-ttu-id="95cdc-292">Национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-292">national id number</span></span>
  
<span data-ttu-id="95cdc-293">ID No</span><span class="sxs-lookup"><span data-stu-id="95cdc-293">id no</span></span>
  
<span data-ttu-id="95cdc-294">туннистенумеро</span><span class="sxs-lookup"><span data-stu-id="95cdc-294">tunnistenumero</span></span>
  
<span data-ttu-id="95cdc-295">хенкилöтуннус</span><span class="sxs-lookup"><span data-stu-id="95cdc-295">henkilötunnus</span></span>
  
<span data-ttu-id="95cdc-296">иксилöллинен хенкилöкохтаинен туннистенумеро</span><span class="sxs-lookup"><span data-stu-id="95cdc-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="95cdc-297">аинутлаатуинен хенкилöкохтаинен туннус</span><span class="sxs-lookup"><span data-stu-id="95cdc-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="95cdc-298">идентититти нумеро</span><span class="sxs-lookup"><span data-stu-id="95cdc-298">identiteetti numero</span></span>
  
<span data-ttu-id="95cdc-299">Суомен кансаллинен хенкилöтуннус</span><span class="sxs-lookup"><span data-stu-id="95cdc-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="95cdc-300">хенкилöтуннуснумеро #</span><span class="sxs-lookup"><span data-stu-id="95cdc-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="95cdc-301">кансаллисен туннистенумеро</span><span class="sxs-lookup"><span data-stu-id="95cdc-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="95cdc-302">туннуснумеро</span><span class="sxs-lookup"><span data-stu-id="95cdc-302">tunnusnumero</span></span>
  
<span data-ttu-id="95cdc-303">кансаллинен туннус нумеро</span><span class="sxs-lookup"><span data-stu-id="95cdc-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="95cdc-304">хету</span><span class="sxs-lookup"><span data-stu-id="95cdc-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="95cdc-305">Франция</span><span class="sxs-lookup"><span data-stu-id="95cdc-305">France</span></span>

<span data-ttu-id="95cdc-306">Дополнительные сведения см. в разделе "номер социального страхования для Франции (INSEE)" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="95cdc-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="95cdc-307">Германия</span><span class="sxs-lookup"><span data-stu-id="95cdc-307">Germany</span></span>

<span data-ttu-id="95cdc-308">Дополнительные сведения можно найти в разделе "номер идентификационной карточки для Германии" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="95cdc-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="95cdc-309">Греция</span><span class="sxs-lookup"><span data-stu-id="95cdc-309">Greece</span></span>

<span data-ttu-id="95cdc-310">Дополнительные сведения можно найти в разделе "Греция National ID Card", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="95cdc-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="95cdc-311">Венгрия</span><span class="sxs-lookup"><span data-stu-id="95cdc-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="95cdc-312">Format</span><span class="sxs-lookup"><span data-stu-id="95cdc-312">Format</span></span>

<span data-ttu-id="95cdc-313">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="95cdc-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="95cdc-314">Шаблон</span><span class="sxs-lookup"><span data-stu-id="95cdc-314">Pattern</span></span>

<span data-ttu-id="95cdc-315">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="95cdc-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="95cdc-316">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="95cdc-316">Checksum</span></span>

<span data-ttu-id="95cdc-317">Да</span><span class="sxs-lookup"><span data-stu-id="95cdc-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="95cdc-318">Определение</span><span class="sxs-lookup"><span data-stu-id="95cdc-318">Definition</span></span>

<span data-ttu-id="95cdc-319">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-320">Функция `Func_hungary_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="95cdc-321">Найдено ключевое `Keywords_hungary_eu_ssn_or_equivalent` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="95cdc-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="95cdc-322">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-323">Функция `Func_hungary_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cdc-324">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="95cdc-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="95cdc-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="95cdc-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="95cdc-326">Венгерский номер социального страхования</span><span class="sxs-lookup"><span data-stu-id="95cdc-326">hungarian social security number</span></span>
  
<span data-ttu-id="95cdc-327">social security number</span><span class="sxs-lookup"><span data-stu-id="95cdc-327">social security number</span></span>
  
<span data-ttu-id="95cdc-328">соЦиалсекуритинумбер #</span><span class="sxs-lookup"><span data-stu-id="95cdc-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="95cdc-329">хссн #</span><span class="sxs-lookup"><span data-stu-id="95cdc-329">hssn#</span></span>
  
<span data-ttu-id="95cdc-330">соЦиалсекуритинно</span><span class="sxs-lookup"><span data-stu-id="95cdc-330">socialsecuritynno</span></span>
  
<span data-ttu-id="95cdc-331">хссн</span><span class="sxs-lookup"><span data-stu-id="95cdc-331">hssn</span></span>
  
<span data-ttu-id="95cdc-332">таж</span><span class="sxs-lookup"><span data-stu-id="95cdc-332">taj</span></span>
  
<span data-ttu-id="95cdc-333">таж #</span><span class="sxs-lookup"><span data-stu-id="95cdc-333">taj#</span></span>
  
<span data-ttu-id="95cdc-334">SSN</span><span class="sxs-lookup"><span data-stu-id="95cdc-334">ssn</span></span>
  
<span data-ttu-id="95cdc-335">SSN #</span><span class="sxs-lookup"><span data-stu-id="95cdc-335">ssn#</span></span>
  
<span data-ttu-id="95cdc-336">социальное страхование нет</span><span class="sxs-lookup"><span data-stu-id="95cdc-336">social security no</span></span>
  
<span data-ttu-id="95cdc-337">áфа</span><span class="sxs-lookup"><span data-stu-id="95cdc-337">áfa</span></span>
  
<span data-ttu-id="95cdc-338">кöзöссéги адóсзáм</span><span class="sxs-lookup"><span data-stu-id="95cdc-338">közösségi adószám</span></span>
  
<span data-ttu-id="95cdc-339">áлталáнос форгалми адó сзáм</span><span class="sxs-lookup"><span data-stu-id="95cdc-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="95cdc-340">хоззáадоттéртéк адó</span><span class="sxs-lookup"><span data-stu-id="95cdc-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="95cdc-341">áфа сзáм</span><span class="sxs-lookup"><span data-stu-id="95cdc-341">áfa szám</span></span>
  
<span data-ttu-id="95cdc-342">магяр áфа сзáм</span><span class="sxs-lookup"><span data-stu-id="95cdc-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="95cdc-343">Португалия</span><span class="sxs-lookup"><span data-stu-id="95cdc-343">Portugal</span></span>

<span data-ttu-id="95cdc-344">Дополнительные сведения можно найти в разделе "номер карты для Португалия" в разделе [сведения о типах конфиденциальной информации для поиска](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="95cdc-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="95cdc-345">Испания</span><span class="sxs-lookup"><span data-stu-id="95cdc-345">Spain</span></span>

<span data-ttu-id="95cdc-346">Дополнительные сведения см. в разделе "номер социального страхования для Испании (SSN)" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="95cdc-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="95cdc-347">Швеция</span><span class="sxs-lookup"><span data-stu-id="95cdc-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="95cdc-348">Format</span><span class="sxs-lookup"><span data-stu-id="95cdc-348">Format</span></span>

<span data-ttu-id="95cdc-349">12 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="95cdc-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="95cdc-350">Шаблон</span><span class="sxs-lookup"><span data-stu-id="95cdc-350">Pattern</span></span>

<span data-ttu-id="95cdc-351">12 цифр:</span><span class="sxs-lookup"><span data-stu-id="95cdc-351">12 digits:</span></span>
  
-  <span data-ttu-id="95cdc-352">Восемь цифр, которые соответствуют дате рождения (ГГГГММДД)</span><span class="sxs-lookup"><span data-stu-id="95cdc-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="95cdc-353">Три цифры, которые соответствуют серийному номеру, где:</span><span class="sxs-lookup"><span data-stu-id="95cdc-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="95cdc-354">Последняя цифра в числовом номере указывает на пол, назначая нечетное число для пола и четное число для розетки.</span><span class="sxs-lookup"><span data-stu-id="95cdc-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="95cdc-355">До 1990, назначение серийного номера соответствует району, в котором был выпущен номер, или (если он родился до 1947), где он был удален, в соответствии с налоговыми записями на 1 января 1947 с особым кодом (как правило, 9 в седьмой цифре) для иммигрантс</span><span class="sxs-lookup"><span data-stu-id="95cdc-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="95cdc-356">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="95cdc-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="95cdc-357">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="95cdc-357">Checksum</span></span>

<span data-ttu-id="95cdc-358">Да</span><span class="sxs-lookup"><span data-stu-id="95cdc-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="95cdc-359">Определение</span><span class="sxs-lookup"><span data-stu-id="95cdc-359">Definition</span></span>

<span data-ttu-id="95cdc-360">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-361">Функция `Func_sweden_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="95cdc-362">Найдено ключевое `Keywords_sweden_eu_ssn_or_equivalent` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="95cdc-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="95cdc-363">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="95cdc-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="95cdc-364">Функция `Func_sweden_eu_ssn_or_equivalent` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="95cdc-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="95cdc-365">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="95cdc-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="95cdc-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="95cdc-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="95cdc-367">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-367">personal id number</span></span>
  
<span data-ttu-id="95cdc-368">identification number</span><span class="sxs-lookup"><span data-stu-id="95cdc-368">identification number</span></span>
  
<span data-ttu-id="95cdc-369">личный идентификатор</span><span class="sxs-lookup"><span data-stu-id="95cdc-369">personal id no</span></span>
  
<span data-ttu-id="95cdc-370">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="95cdc-370">identity no</span></span>
  
<span data-ttu-id="95cdc-371">Идентификация нет</span><span class="sxs-lookup"><span data-stu-id="95cdc-371">identification no</span></span>
  
<span data-ttu-id="95cdc-372">персональный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="95cdc-372">personal identification no</span></span>
  
<span data-ttu-id="95cdc-373">Идентификатор персоннуммер</span><span class="sxs-lookup"><span data-stu-id="95cdc-373">personnummer id</span></span>
  
<span data-ttu-id="95cdc-374">Идентификатор персонлигт — нуммер</span><span class="sxs-lookup"><span data-stu-id="95cdc-374">personligt id-nummer</span></span>
  
<span data-ttu-id="95cdc-375">Идентификатор уникт — нуммер</span><span class="sxs-lookup"><span data-stu-id="95cdc-375">unikt id-nummer</span></span>
  
<span data-ttu-id="95cdc-376">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="95cdc-376">personnummer</span></span>
  
<span data-ttu-id="95cdc-377">идентификатионснумрет</span><span class="sxs-lookup"><span data-stu-id="95cdc-377">identifikationsnumret</span></span>
  
<span data-ttu-id="95cdc-378">персоннуммер #</span><span class="sxs-lookup"><span data-stu-id="95cdc-378">personnummer#</span></span>
  
<span data-ttu-id="95cdc-379">идентификатионснумрет #</span><span class="sxs-lookup"><span data-stu-id="95cdc-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="95cdc-380">См. также</span><span class="sxs-lookup"><span data-stu-id="95cdc-380">See also</span></span>

[<span data-ttu-id="95cdc-381">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="95cdc-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

