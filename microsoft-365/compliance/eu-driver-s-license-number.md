---
title: Номер водительского удостоверения для драйвера ЕС
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации номера лицензии для драйвера ЕС. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090284"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="6e930-104">Номер водительского удостоверения для драйвера ЕС</span><span class="sxs-lookup"><span data-stu-id="6e930-104">EU Driver's License Number</span></span>

<span data-ttu-id="6e930-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации номера лицензии для драйвера ЕС.</span><span class="sxs-lookup"><span data-stu-id="6e930-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="6e930-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="6e930-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="6e930-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="6e930-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="6e930-108">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-108">Format</span></span>

<span data-ttu-id="6e930-109">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="6e930-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-110">Pattern</span></span>

<span data-ttu-id="6e930-111">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e930-112">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-112">Checksum</span></span>

<span data-ttu-id="6e930-113">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-114">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-114">Definition</span></span>

<span data-ttu-id="6e930-115">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-116">Регулярное выражение `Regex_austria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-117">Найдено ключевое `Keywords_austria_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="6e930-118">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-118">Keywords</span></span>

<span data-ttu-id="6e930-119">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-119"></span></span>
|<span data-ttu-id="6e930-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-121">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-121">dl#</span></span>  <br/> <span data-ttu-id="6e930-122">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-122">driver license</span></span>  <br/> <span data-ttu-id="6e930-123">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-123">driver license number</span></span>  <br/> <span data-ttu-id="6e930-124">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-124">driver licence</span></span>  <br/> <span data-ttu-id="6e930-125">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-125">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-126">drivers license</span></span>  <br/> <span data-ttu-id="6e930-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="6e930-127">driver's licence</span></span>  <br/> <span data-ttu-id="6e930-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-128">driver's license</span></span>  <br/> <span data-ttu-id="6e930-129">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-129">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-130">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="6e930-131">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-131">driving license number</span></span>  <br/> <span data-ttu-id="6e930-132">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-132">dlno#</span></span>  <br/> <span data-ttu-id="6e930-133">фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="6e930-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="6e930-134">фухрерсчеин Републик остерреич</span><span class="sxs-lookup"><span data-stu-id="6e930-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="6e930-135">Бельгия</span><span class="sxs-lookup"><span data-stu-id="6e930-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="6e930-136">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-136">Format</span></span>

<span data-ttu-id="6e930-137">10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="6e930-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-138">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-138">Pattern</span></span>

<span data-ttu-id="6e930-139">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e930-140">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-140">Checksum</span></span>

<span data-ttu-id="6e930-141">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-142">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-142">Definition</span></span>

<span data-ttu-id="6e930-143">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-144">Регулярное выражение `Regex_belgium_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-145">Найдено ключевое `Keywords_belgium_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="6e930-146">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-146">Keywords</span></span>

<span data-ttu-id="6e930-147">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-147"></span></span>
|<span data-ttu-id="6e930-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-149">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-149">dl#</span></span>  <br/> <span data-ttu-id="6e930-150">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-150">driver license</span></span>  <br/> <span data-ttu-id="6e930-151">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-151">driver license number</span></span>  <br/> <span data-ttu-id="6e930-152">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-152">driver licence</span></span>  <br/> <span data-ttu-id="6e930-153">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-153">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-154">drivers license</span></span>  <br/> <span data-ttu-id="6e930-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-155">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-156">driver's license</span></span>  <br/> <span data-ttu-id="6e930-157">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-157">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-158">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-158">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-159">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-159">dlno#</span></span>  <br/> <span data-ttu-id="6e930-160">рижбевижс</span><span class="sxs-lookup"><span data-stu-id="6e930-160">rijbewijs</span></span>  <br/> <span data-ttu-id="6e930-161">рижбевижснуммер</span><span class="sxs-lookup"><span data-stu-id="6e930-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="6e930-162">фüхрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="6e930-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="6e930-163">фухрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="6e930-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="6e930-164">фуехрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="6e930-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="6e930-165">фüхрерсчеин — НР</span><span class="sxs-lookup"><span data-stu-id="6e930-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="6e930-166">фуехрерсчеин — НР</span><span class="sxs-lookup"><span data-stu-id="6e930-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="6e930-167">фуехрерсчеин — НР</span><span class="sxs-lookup"><span data-stu-id="6e930-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="6e930-168">Болгария</span><span class="sxs-lookup"><span data-stu-id="6e930-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="6e930-169">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-169">Format</span></span>

<span data-ttu-id="6e930-170">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="6e930-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-171">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-171">Pattern</span></span>

<span data-ttu-id="6e930-172">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e930-173">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-173">Checksum</span></span>

<span data-ttu-id="6e930-174">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-175">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-175">Definition</span></span>

<span data-ttu-id="6e930-176">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-177">Регулярное выражение `Regex_bulgaria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-178">Найдено ключевое `Keywords_bulgaria_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="6e930-179">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-179">Keywords</span></span>

<span data-ttu-id="6e930-180">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-180"></span></span>
|<span data-ttu-id="6e930-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-182">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-182">dl#</span></span>  <br/> <span data-ttu-id="6e930-183">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-183">driver license</span></span>  <br/> <span data-ttu-id="6e930-184">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-184">driver license number</span></span>  <br/> <span data-ttu-id="6e930-185">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-185">driver licence</span></span>  <br/> <span data-ttu-id="6e930-186">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-186">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-187">drivers license</span></span>  <br/> <span data-ttu-id="6e930-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-188">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-189">driver's license</span></span>  <br/> <span data-ttu-id="6e930-190">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-190">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-191">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-191">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-192">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-192">driving license number</span></span>  <br/> <span data-ttu-id="6e930-193">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-193">dlno#</span></span>  <br/> <span data-ttu-id="6e930-194">свидетелство за управление на МПС</span><span class="sxs-lookup"><span data-stu-id="6e930-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="6e930-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="6e930-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="6e930-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="6e930-196">сумпс</span></span>  <br/> <span data-ttu-id="6e930-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="6e930-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="6e930-198">Хорватия</span><span class="sxs-lookup"><span data-stu-id="6e930-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="6e930-199">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-199">Format</span></span>

<span data-ttu-id="6e930-200">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="6e930-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-201">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-201">Pattern</span></span>

<span data-ttu-id="6e930-202">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e930-203">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-203">Checksum</span></span>

<span data-ttu-id="6e930-204">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-205">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-205">Definition</span></span>

<span data-ttu-id="6e930-206">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-207">Регулярное выражение `Regex_croatia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-208">Найдено ключевое `Keywords_croatia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="6e930-209">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-209">Keywords</span></span>

<span data-ttu-id="6e930-210">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-210"></span></span>
|<span data-ttu-id="6e930-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-212">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-212">dl#</span></span>  <br/> <span data-ttu-id="6e930-213">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-213">driver license</span></span>  <br/> <span data-ttu-id="6e930-214">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-214">driver license number</span></span>  <br/> <span data-ttu-id="6e930-215">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-215">driver licence</span></span>  <br/> <span data-ttu-id="6e930-216">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-216">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-217">drivers license</span></span>  <br/> <span data-ttu-id="6e930-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-218">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-219">driver's license</span></span>  <br/> <span data-ttu-id="6e930-220">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-220">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-221">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-221">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-222">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-222">driving license number</span></span>  <br/> <span data-ttu-id="6e930-223">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-223">dlno#</span></span>  <br/> <span data-ttu-id="6e930-224">возаčка дозвола</span><span class="sxs-lookup"><span data-stu-id="6e930-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="6e930-225">Кипр</span><span class="sxs-lookup"><span data-stu-id="6e930-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="6e930-226">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-226">Format</span></span>

<span data-ttu-id="6e930-227">12 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="6e930-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-228">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-228">Pattern</span></span>

<span data-ttu-id="6e930-229">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e930-230">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-230">Checksum</span></span>

<span data-ttu-id="6e930-231">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-232">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-232">Definition</span></span>

<span data-ttu-id="6e930-233">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-234">Регулярное выражение `Regex_cyprus_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-235">Найдено ключевое `Keywords_cyprus_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-236">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-236">Keywords</span></span>

<span data-ttu-id="6e930-237">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-237"></span></span>
|<span data-ttu-id="6e930-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-239">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-239">dl#</span></span>  <br/> <span data-ttu-id="6e930-240">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-240">driver license</span></span>  <br/> <span data-ttu-id="6e930-241">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-241">driver license number</span></span>  <br/> <span data-ttu-id="6e930-242">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-242">driver licence</span></span>  <br/> <span data-ttu-id="6e930-243">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-243">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-244">drivers license</span></span>  <br/> <span data-ttu-id="6e930-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-245">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-246">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-246">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-247">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-247">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-248">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-248">driving license number</span></span>  <br/> <span data-ttu-id="6e930-249">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-249">dlno#</span></span>  <br/> <span data-ttu-id="6e930-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="6e930-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="6e930-251">Чешская Республика</span><span class="sxs-lookup"><span data-stu-id="6e930-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="6e930-252">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-252">Format</span></span>

<span data-ttu-id="6e930-253">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-254">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-254">Pattern</span></span>

<span data-ttu-id="6e930-255">Восемь букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="6e930-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="6e930-256">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="6e930-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="6e930-257">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="6e930-257">A space (optional)</span></span>
    
- <span data-ttu-id="6e930-258">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e930-259">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-259">Checksum</span></span>

<span data-ttu-id="6e930-260">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-261">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-261">Definition</span></span>

<span data-ttu-id="6e930-262">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-263">Регулярное выражение `Regex_czech_republic_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-264">Найдено ключевое `Keywords_czech_republic_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="6e930-265">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-265">Keywords</span></span>

<span data-ttu-id="6e930-266">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-266"></span></span>
|<span data-ttu-id="6e930-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-268">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-268">dl#</span></span>  <br/> <span data-ttu-id="6e930-269">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-269">driver license</span></span>  <br/> <span data-ttu-id="6e930-270">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-270">driver license number</span></span>  <br/> <span data-ttu-id="6e930-271">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-271">driver licence</span></span>  <br/> <span data-ttu-id="6e930-272">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-272">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-273">drivers license</span></span>  <br/> <span data-ttu-id="6e930-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-274">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-275">driver's license</span></span>  <br/> <span data-ttu-id="6e930-276">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-276">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-277">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-277">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-278">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-278">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-279">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-279">driving license number</span></span>  <br/> <span data-ttu-id="6e930-280">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-280">dlno#</span></span>  <br/> <span data-ttu-id="6e930-281">řидиčскý прúказ</span><span class="sxs-lookup"><span data-stu-id="6e930-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="6e930-282">Дания</span><span class="sxs-lookup"><span data-stu-id="6e930-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="6e930-283">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-283">Format</span></span>

<span data-ttu-id="6e930-284">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="6e930-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-285">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-285">Pattern</span></span>

<span data-ttu-id="6e930-286">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e930-287">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-287">Checksum</span></span>

<span data-ttu-id="6e930-288">Да</span><span class="sxs-lookup"><span data-stu-id="6e930-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-289">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-289">Definition</span></span>

<span data-ttu-id="6e930-290">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-291">Регулярное выражение `Regex_denmark_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-292">Найдено ключевое `Keywords_denmark_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="6e930-293">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-293">Keywords</span></span>

<span data-ttu-id="6e930-294">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-294"></span></span>
|<span data-ttu-id="6e930-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-296">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-296">dl#</span></span>  <br/> <span data-ttu-id="6e930-297">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-297">driver license</span></span>  <br/> <span data-ttu-id="6e930-298">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-298">driver license number</span></span>  <br/> <span data-ttu-id="6e930-299">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-299">driver licence</span></span>  <br/> <span data-ttu-id="6e930-300">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-300">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-301">drivers license</span></span>  <br/> <span data-ttu-id="6e930-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-302">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-303">driver's license</span></span>  <br/> <span data-ttu-id="6e930-304">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-304">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-305">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-305">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-306">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-306">driving license number</span></span>  <br/> <span data-ttu-id="6e930-307">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-307">dlno#</span></span>  <br/> <span data-ttu-id="6e930-308">кøрекорт</span><span class="sxs-lookup"><span data-stu-id="6e930-308">kørekort</span></span>  <br/> <span data-ttu-id="6e930-309">кøрекортнуммер</span><span class="sxs-lookup"><span data-stu-id="6e930-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="6e930-310">Эстония</span><span class="sxs-lookup"><span data-stu-id="6e930-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="6e930-311">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-311">Format</span></span>

<span data-ttu-id="6e930-312">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-313">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-313">Pattern</span></span>

<span data-ttu-id="6e930-314">Две буквы и шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="6e930-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="6e930-315">Буквы "ET" (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="6e930-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="6e930-316">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e930-317">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-317">Checksum</span></span>

<span data-ttu-id="6e930-318">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-319">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-319">Definition</span></span>

<span data-ttu-id="6e930-320">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-321">Регулярное выражение `Regex_estonia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-322">Найдено ключевое `Keywords_estonia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-323">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-323">Keywords</span></span>

<span data-ttu-id="6e930-324">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-324"></span></span>
|<span data-ttu-id="6e930-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-326">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-326">dl#</span></span>  <br/> <span data-ttu-id="6e930-327">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-327">driver license</span></span>  <br/> <span data-ttu-id="6e930-328">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-328">driver license number</span></span>  <br/> <span data-ttu-id="6e930-329">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-329">driver license number</span></span>  <br/> <span data-ttu-id="6e930-330">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-330">driver licence</span></span>  <br/> <span data-ttu-id="6e930-331">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-331">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-332">drivers license</span></span>  <br/> <span data-ttu-id="6e930-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-333">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-334">driver's license</span></span>  <br/> <span data-ttu-id="6e930-335">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-335">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-336">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-336">driving license number</span></span>  <br/> <span data-ttu-id="6e930-337">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-337">dlno#</span></span>  <br/> <span data-ttu-id="6e930-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="6e930-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="6e930-339">Финляндия</span><span class="sxs-lookup"><span data-stu-id="6e930-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="6e930-340">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-340">Format</span></span>

<span data-ttu-id="6e930-341">10 цифр, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="6e930-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-342">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-342">Pattern</span></span>

<span data-ttu-id="6e930-343">10 цифр, содержащих дефис:</span><span class="sxs-lookup"><span data-stu-id="6e930-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="6e930-344">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="6e930-344">Six digits</span></span> 
    
- <span data-ttu-id="6e930-345">дефис;</span><span class="sxs-lookup"><span data-stu-id="6e930-345">A hyphen</span></span>
    
-  <span data-ttu-id="6e930-346">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="6e930-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="6e930-347">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-347">Checksum</span></span>

<span data-ttu-id="6e930-348">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-349">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-349">Definition</span></span>

<span data-ttu-id="6e930-350">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-351">Регулярное выражение `Regex_finland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-352">Найдено ключевое `Keywords_finland_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-353">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-353">Keywords</span></span>

<span data-ttu-id="6e930-354">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-354"></span></span>
|<span data-ttu-id="6e930-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-356">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-356">dl#</span></span>  <br/> <span data-ttu-id="6e930-357">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-357">driver license</span></span>  <br/> <span data-ttu-id="6e930-358">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-358">driver license number</span></span>  <br/> <span data-ttu-id="6e930-359">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-359">driver licence</span></span>  <br/> <span data-ttu-id="6e930-360">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-360">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-361">drivers license</span></span>  <br/> <span data-ttu-id="6e930-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-362">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-363">driver's license</span></span>  <br/> <span data-ttu-id="6e930-364">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-364">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-365">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-365">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-366">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-366">driving license number</span></span>  <br/> <span data-ttu-id="6e930-367">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-367">dlno#</span></span>  <br/> <span data-ttu-id="6e930-368">ажокортти</span><span class="sxs-lookup"><span data-stu-id="6e930-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="6e930-369">Франция</span><span class="sxs-lookup"><span data-stu-id="6e930-369">France</span></span>

<span data-ttu-id="6e930-370">Дополнительные сведения см. в разделе "номер водительского удостоверения для Франции" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6e930-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="6e930-371">Германия</span><span class="sxs-lookup"><span data-stu-id="6e930-371">Germany</span></span>

<span data-ttu-id="6e930-372">Дополнительные сведения можно найти в разделе "номер водительского удостоверения для немецкого драйвера" [, который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6e930-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="6e930-373">Греция</span><span class="sxs-lookup"><span data-stu-id="6e930-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="6e930-374">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-374">Format</span></span>

<span data-ttu-id="6e930-375">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="6e930-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-376">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-376">Pattern</span></span>

 <span data-ttu-id="6e930-377">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6e930-378">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-378">Checksum</span></span>

<span data-ttu-id="6e930-379">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-380">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-380">Definition</span></span>

<span data-ttu-id="6e930-381">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-382">Регулярное выражение `Regex_greece_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-383">Найдено ключевое `Keywords_greece_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-384">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-384">Keywords</span></span>

<span data-ttu-id="6e930-385">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-385"></span></span>
|<span data-ttu-id="6e930-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-387">Файл #</span><span class="sxs-lookup"><span data-stu-id="6e930-387">dlL#</span></span>  <br/> <span data-ttu-id="6e930-388">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-388">driver license</span></span>  <br/> <span data-ttu-id="6e930-389">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-389">driver license number</span></span>  <br/> <span data-ttu-id="6e930-390">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-390">driver licence</span></span>  <br/> <span data-ttu-id="6e930-391">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-391">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-392">drivers license</span></span>  <br/> <span data-ttu-id="6e930-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-393">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-394">driver's license</span></span>  <br/> <span data-ttu-id="6e930-395">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-395">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-396">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-396">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-397">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-397">driving license number</span></span>  <br/> <span data-ttu-id="6e930-398">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-398">dlno#</span></span>  <br/> <span data-ttu-id="6e930-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="6e930-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="6e930-400">Адеиа одигисис</span><span class="sxs-lookup"><span data-stu-id="6e930-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="6e930-401">Венгрия</span><span class="sxs-lookup"><span data-stu-id="6e930-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="6e930-402">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-402">Format</span></span>

<span data-ttu-id="6e930-403">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-404">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-404">Pattern</span></span>

<span data-ttu-id="6e930-405">Две буквы и шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="6e930-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="6e930-406">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="6e930-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="6e930-407">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e930-408">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-408">Checksum</span></span>

<span data-ttu-id="6e930-409">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-410">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-410">Definition</span></span>

<span data-ttu-id="6e930-411">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-412">Регулярное выражение `Regex_hungary_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-413">Найдено ключевое `Keywords_hungary_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-414">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-414">Keywords</span></span>

<span data-ttu-id="6e930-415">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-415"></span></span>
|<span data-ttu-id="6e930-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-417">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-417">dl#</span></span>  <br/> <span data-ttu-id="6e930-418">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-418">driver license</span></span>  <br/> <span data-ttu-id="6e930-419">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-419">driver license number</span></span>  <br/> <span data-ttu-id="6e930-420">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-420">driver licence</span></span>  <br/> <span data-ttu-id="6e930-421">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-421">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-422">drivers license</span></span>  <br/> <span data-ttu-id="6e930-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-423">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-424">driver's license</span></span>  <br/> <span data-ttu-id="6e930-425">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-425">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-426">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-426">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-427">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-427">driving license number</span></span>  <br/> <span data-ttu-id="6e930-428">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-428">dlno#</span></span>  <br/> <span data-ttu-id="6e930-429">везетои енжедели</span><span class="sxs-lookup"><span data-stu-id="6e930-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="6e930-430">Ireland (Ирландия)</span><span class="sxs-lookup"><span data-stu-id="6e930-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="6e930-431">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-431">Format</span></span>

<span data-ttu-id="6e930-432">Шесть цифр, за которыми следуют четыре буквы</span><span class="sxs-lookup"><span data-stu-id="6e930-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-433">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-433">Pattern</span></span>

<span data-ttu-id="6e930-434">Шесть цифр и четыре буквы:</span><span class="sxs-lookup"><span data-stu-id="6e930-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="6e930-435">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="6e930-435">Six digits</span></span>
    
- <span data-ttu-id="6e930-436">Четыре буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="6e930-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e930-437">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-437">Checksum</span></span>

<span data-ttu-id="6e930-438">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-439">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-439">Definition</span></span>

<span data-ttu-id="6e930-440">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-441">Регулярное выражение `Regex_ireland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-442">Найдено ключевое `Keywords_ireland_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-443">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-443">Keywords</span></span>

<span data-ttu-id="6e930-444">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-444"></span></span>
|<span data-ttu-id="6e930-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-446">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-446">dl#</span></span>  <br/> <span data-ttu-id="6e930-447">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-447">driver license</span></span>  <br/> <span data-ttu-id="6e930-448">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-448">driver license number</span></span>  <br/> <span data-ttu-id="6e930-449">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-449">driver licence</span></span>  <br/> <span data-ttu-id="6e930-450">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-450">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-451">drivers license</span></span>  <br/> <span data-ttu-id="6e930-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-452">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-453">driver's license</span></span>  <br/> <span data-ttu-id="6e930-454">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-454">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-455">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-455">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-456">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-456">driving license number</span></span>  <br/> <span data-ttu-id="6e930-457">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-457">dlno#</span></span>  <br/> <span data-ttu-id="6e930-458">цеадúнас тиомáна</span><span class="sxs-lookup"><span data-stu-id="6e930-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="6e930-459">Италия</span><span class="sxs-lookup"><span data-stu-id="6e930-459">Italy</span></span>

<span data-ttu-id="6e930-460">Дополнительные сведения см. в разделе "номер водительского удостоверения для Италии" [, который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6e930-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="6e930-461">Латвия</span><span class="sxs-lookup"><span data-stu-id="6e930-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="6e930-462">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-462">Format</span></span>

<span data-ttu-id="6e930-463">Три буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-464">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-464">Pattern</span></span>

<span data-ttu-id="6e930-465">Три буквы и шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="6e930-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="6e930-466">Три буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="6e930-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="6e930-467">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e930-468">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-468">Checksum</span></span>

<span data-ttu-id="6e930-469">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-470">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-470">Definition</span></span>

<span data-ttu-id="6e930-471">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-472">Регулярное выражение `Regex_latvia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-473">Найдено ключевое `Keywords_latvia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-474">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-474">Keywords</span></span>

<span data-ttu-id="6e930-475">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-475"></span></span>
|<span data-ttu-id="6e930-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-477">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-477">dl#</span></span>  <br/> <span data-ttu-id="6e930-478">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-478">driver license</span></span>  <br/> <span data-ttu-id="6e930-479">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-479">driver license number</span></span>  <br/> <span data-ttu-id="6e930-480">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-480">driver licence</span></span>  <br/> <span data-ttu-id="6e930-481">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-481">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-482">drivers license</span></span>  <br/> <span data-ttu-id="6e930-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-483">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-484">driver's license</span></span>  <br/> <span data-ttu-id="6e930-485">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-485">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-486">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-486">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-487">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-487">driving license number</span></span>  <br/> <span data-ttu-id="6e930-488">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-488">dlno#</span></span>  <br/> <span data-ttu-id="6e930-489">аутовадīтāжа аплиекīба</span><span class="sxs-lookup"><span data-stu-id="6e930-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="6e930-490">Литва</span><span class="sxs-lookup"><span data-stu-id="6e930-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="6e930-491">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-491">Format</span></span>

<span data-ttu-id="6e930-492">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="6e930-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-493">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-493">Pattern</span></span>

 <span data-ttu-id="6e930-494">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6e930-495">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-495">Checksum</span></span>

<span data-ttu-id="6e930-496">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-497">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-497">Definition</span></span>

<span data-ttu-id="6e930-498">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-499">Регулярное выражение `Regex_lithuania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-500">Найдено ключевое `Keywords_lithuania_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-501">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-501">Keywords</span></span>

<span data-ttu-id="6e930-502">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-502"></span></span>
|<span data-ttu-id="6e930-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-504">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-504">dl#</span></span>  <br/> <span data-ttu-id="6e930-505">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-505">driver license</span></span>  <br/> <span data-ttu-id="6e930-506">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-506">driver license number</span></span>  <br/> <span data-ttu-id="6e930-507">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-507">driver licence</span></span>  <br/> <span data-ttu-id="6e930-508">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-508">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-509">drivers license</span></span>  <br/> <span data-ttu-id="6e930-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-510">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-511">driver's license</span></span>  <br/> <span data-ttu-id="6e930-512">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-512">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-513">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-513">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-514">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-514">driving license number</span></span>  <br/> <span data-ttu-id="6e930-515">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-515">dlno#</span></span>  <br/> <span data-ttu-id="6e930-516">ваируотожо паžимėжимас</span><span class="sxs-lookup"><span data-stu-id="6e930-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="6e930-517">луксембург</span><span class="sxs-lookup"><span data-stu-id="6e930-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="6e930-518">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-518">Format</span></span>

<span data-ttu-id="6e930-519">Шесть цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="6e930-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-520">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-520">Pattern</span></span>

 <span data-ttu-id="6e930-521">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="6e930-522">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-522">Checksum</span></span>

<span data-ttu-id="6e930-523">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-524">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-524">Definition</span></span>

<span data-ttu-id="6e930-525">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-526">Регулярное выражение `Regex_luxemburg_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-527">Найдено ключевое `Keywords_luxemburg_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-528">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-528">Keywords</span></span>

<span data-ttu-id="6e930-529">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-529"></span></span>
|<span data-ttu-id="6e930-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-531">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-531">dl#</span></span>  <br/> <span data-ttu-id="6e930-532">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-532">driver license</span></span>  <br/> <span data-ttu-id="6e930-533">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-533">driver license number</span></span>  <br/> <span data-ttu-id="6e930-534">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-534">driver licence</span></span>  <br/> <span data-ttu-id="6e930-535">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-535">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-536">drivers license</span></span>  <br/> <span data-ttu-id="6e930-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-537">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-538">driver's license</span></span>  <br/> <span data-ttu-id="6e930-539">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-539">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-540">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-540">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-541">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-541">driving license number</span></span>  <br/> <span data-ttu-id="6e930-542">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-542">dlno#</span></span>  <br/> <span data-ttu-id="6e930-543">фахрерлаубнис</span><span class="sxs-lookup"><span data-stu-id="6e930-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="6e930-544">Мальта</span><span class="sxs-lookup"><span data-stu-id="6e930-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="6e930-545">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-545">Format</span></span>

<span data-ttu-id="6e930-546">Сочетание двух символов и шести цифр в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="6e930-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-547">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-547">Pattern</span></span>

<span data-ttu-id="6e930-548">Сочетание двух символов и шести цифр:</span><span class="sxs-lookup"><span data-stu-id="6e930-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="6e930-549">Два символа (цифры или буквы без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="6e930-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="6e930-550">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="6e930-550">A space (optional)</span></span>
    
- <span data-ttu-id="6e930-551">три цифры; </span><span class="sxs-lookup"><span data-stu-id="6e930-551">Three digits</span></span>
    
- <span data-ttu-id="6e930-552">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="6e930-552">A space (optional)</span></span>
    
- <span data-ttu-id="6e930-553">Три цифры</span><span class="sxs-lookup"><span data-stu-id="6e930-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e930-554">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-554">Checksum</span></span>

<span data-ttu-id="6e930-555">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-556">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-556">Definition</span></span>

<span data-ttu-id="6e930-557">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-558">Регулярное выражение `Regex_malta_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-559">Найдено ключевое `Keywords_malta_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-560">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-560">Keywords</span></span>

<span data-ttu-id="6e930-561">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-561"></span></span>
|<span data-ttu-id="6e930-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-563">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-563">dl#</span></span>  <br/> <span data-ttu-id="6e930-564">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-564">driver license</span></span>  <br/> <span data-ttu-id="6e930-565">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-565">driver license number</span></span>  <br/> <span data-ttu-id="6e930-566">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-566">driver licence</span></span>  <br/> <span data-ttu-id="6e930-567">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-567">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-568">drivers license</span></span>  <br/> <span data-ttu-id="6e930-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-569">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-570">driver's license</span></span>  <br/> <span data-ttu-id="6e930-571">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-571">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-572">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-572">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-573">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-573">driving license number</span></span>  <br/> <span data-ttu-id="6e930-574">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-574">dlno#</span></span>  <br/> <span data-ttu-id="6e930-575">лиċензжаные зада Севкан</span><span class="sxs-lookup"><span data-stu-id="6e930-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="6e930-576">Нидерланды</span><span class="sxs-lookup"><span data-stu-id="6e930-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="6e930-577">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-577">Format</span></span>

<span data-ttu-id="6e930-578">10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="6e930-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-579">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-579">Pattern</span></span>

<span data-ttu-id="6e930-580">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e930-581">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-581">Checksum</span></span>

<span data-ttu-id="6e930-582">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-583">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-583">Definition</span></span>

<span data-ttu-id="6e930-584">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-585">Регулярное выражение `Regex_netherlands_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-586">Найдено ключевое `Keywords_netherlands_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-587">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-587">Keywords</span></span>

<span data-ttu-id="6e930-588">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-588"></span></span>
|<span data-ttu-id="6e930-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-590">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-590">dl#</span></span>  <br/> <span data-ttu-id="6e930-591">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-591">driver license</span></span>  <br/> <span data-ttu-id="6e930-592">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-592">driver license number</span></span>  <br/> <span data-ttu-id="6e930-593">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-593">driver licence</span></span>  <br/> <span data-ttu-id="6e930-594">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-594">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-595">drivers license</span></span>  <br/> <span data-ttu-id="6e930-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-596">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-597">driver's license</span></span>  <br/> <span data-ttu-id="6e930-598">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-598">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-599">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-599">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-600">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-600">driving license number</span></span>  <br/> <span data-ttu-id="6e930-601">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-601">dlno#</span></span>  <br/> <span data-ttu-id="6e930-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="6e930-602">permis de conduire</span></span>  <br/> <span data-ttu-id="6e930-603">рижбевижс</span><span class="sxs-lookup"><span data-stu-id="6e930-603">rijbewijs</span></span>  <br/> <span data-ttu-id="6e930-604">рижбевижснуммер</span><span class="sxs-lookup"><span data-stu-id="6e930-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="6e930-605">Польша</span><span class="sxs-lookup"><span data-stu-id="6e930-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="6e930-606">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-606">Format</span></span>

<span data-ttu-id="6e930-607">14 цифр, содержащих 2 косых черты.</span><span class="sxs-lookup"><span data-stu-id="6e930-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-608">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-608">Pattern</span></span>

<span data-ttu-id="6e930-609">14 цифр и 2 косых черт:</span><span class="sxs-lookup"><span data-stu-id="6e930-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="6e930-610">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="6e930-610">Five digits</span></span> 
    
- <span data-ttu-id="6e930-611">косая черта;</span><span class="sxs-lookup"><span data-stu-id="6e930-611">A forward slash</span></span>
    
- <span data-ttu-id="6e930-612">Две цифры</span><span class="sxs-lookup"><span data-stu-id="6e930-612">Two digits</span></span>
    
- <span data-ttu-id="6e930-613">косая черта;</span><span class="sxs-lookup"><span data-stu-id="6e930-613">A forward slash</span></span>
    
- <span data-ttu-id="6e930-614">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e930-615">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-615">Checksum</span></span>

<span data-ttu-id="6e930-616">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-617">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-617">Definition</span></span>

<span data-ttu-id="6e930-618">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-619">Регулярное выражение `Regex_poland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-620">Найдено ключевое `Keywords_poland_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-621">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-621">Keywords</span></span>

<span data-ttu-id="6e930-622">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-622"></span></span>
|<span data-ttu-id="6e930-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-624">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-624">dl#</span></span>  <br/> <span data-ttu-id="6e930-625">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-625">driver license</span></span>  <br/> <span data-ttu-id="6e930-626">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-626">driver license number</span></span>  <br/> <span data-ttu-id="6e930-627">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-627">driver licence</span></span>  <br/> <span data-ttu-id="6e930-628">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-628">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-629">drivers license</span></span>  <br/> <span data-ttu-id="6e930-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-630">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-631">driver's license</span></span>  <br/> <span data-ttu-id="6e930-632">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-632">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-633">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-633">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-634">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-634">driving license number</span></span>  <br/> <span data-ttu-id="6e930-635">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-635">dlno#</span></span>  <br/> <span data-ttu-id="6e930-636">право жазди</span><span class="sxs-lookup"><span data-stu-id="6e930-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="6e930-637">Португалия</span><span class="sxs-lookup"><span data-stu-id="6e930-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="6e930-638">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-638">Format</span></span>

<span data-ttu-id="6e930-639">Две буквы, за которыми следуют семь чисел в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="6e930-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-640">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-640">Pattern</span></span>

<span data-ttu-id="6e930-641">Две буквы, за которыми следуют семь цифр со специальными символами:</span><span class="sxs-lookup"><span data-stu-id="6e930-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="6e930-642">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="6e930-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="6e930-643">дефис;</span><span class="sxs-lookup"><span data-stu-id="6e930-643">A hyphen</span></span>
    
- <span data-ttu-id="6e930-644">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="6e930-644">Six digits</span></span>
    
- <span data-ttu-id="6e930-645">Пробел</span><span class="sxs-lookup"><span data-stu-id="6e930-645">A space</span></span>
    
- <span data-ttu-id="6e930-646">одна цифра.</span><span class="sxs-lookup"><span data-stu-id="6e930-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e930-647">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-647">Checksum</span></span>

<span data-ttu-id="6e930-648">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-649">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-649">Definition</span></span>

<span data-ttu-id="6e930-650">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-651">Регулярное выражение `Regex_portugal_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-652">Найдено ключевое `Keywords_portugal_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-653">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-653">Keywords</span></span>

<span data-ttu-id="6e930-654">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-654"></span></span>
|<span data-ttu-id="6e930-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-656">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-656">dl#</span></span>  <br/> <span data-ttu-id="6e930-657">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-657">driver license</span></span>  <br/> <span data-ttu-id="6e930-658">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-658">driver license number</span></span>  <br/> <span data-ttu-id="6e930-659">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-659">driver licence</span></span>  <br/> <span data-ttu-id="6e930-660">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-660">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-661">drivers license</span></span>  <br/> <span data-ttu-id="6e930-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-662">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-663">driver's license</span></span>  <br/> <span data-ttu-id="6e930-664">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-664">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-665">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-665">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-666">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-666">driving license number</span></span>  <br/> <span data-ttu-id="6e930-667">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-667">dlno#</span></span>  <br/> <span data-ttu-id="6e930-668">картеира de моториста</span><span class="sxs-lookup"><span data-stu-id="6e930-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="6e930-669">Румыния</span><span class="sxs-lookup"><span data-stu-id="6e930-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="6e930-670">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-670">Format</span></span>

<span data-ttu-id="6e930-671">Один символ, за которым следуют восемь цифр</span><span class="sxs-lookup"><span data-stu-id="6e930-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-672">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-672">Pattern</span></span>

<span data-ttu-id="6e930-673">Один символ, за которым следуют восемь цифр:</span><span class="sxs-lookup"><span data-stu-id="6e930-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="6e930-674">Одна буква (без учета регистра) или цифра</span><span class="sxs-lookup"><span data-stu-id="6e930-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="6e930-675">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e930-676">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-676">Checksum</span></span>

<span data-ttu-id="6e930-677">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-678">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-678">Definition</span></span>

<span data-ttu-id="6e930-679">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-680">Регулярное выражение `Regex_romania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-681">Найдено ключевое `Keywords_romania_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-682">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-682">Keywords</span></span>

<span data-ttu-id="6e930-683">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-683"></span></span>
|<span data-ttu-id="6e930-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-685">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-685">dl#</span></span>  <br/> <span data-ttu-id="6e930-686">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-686">driver license</span></span>  <br/> <span data-ttu-id="6e930-687">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-687">driver license number</span></span>  <br/> <span data-ttu-id="6e930-688">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-688">driver licence</span></span>  <br/> <span data-ttu-id="6e930-689">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-689">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-690">drivers license</span></span>  <br/> <span data-ttu-id="6e930-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-691">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-692">driver's license</span></span>  <br/> <span data-ttu-id="6e930-693">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-693">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-694">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-694">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-695">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-695">driving license number</span></span>  <br/> <span data-ttu-id="6e930-696">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-696">dlno#</span></span>  <br/> <span data-ttu-id="6e930-697">разрешение de кондуцере</span><span class="sxs-lookup"><span data-stu-id="6e930-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="6e930-698">Словакия</span><span class="sxs-lookup"><span data-stu-id="6e930-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="6e930-699">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-699">Format</span></span>

<span data-ttu-id="6e930-700">Один символ, за которым следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-701">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-701">Pattern</span></span>

<span data-ttu-id="6e930-702">Один символ, за которым следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="6e930-703">Одна буква (без учета регистра) или цифра</span><span class="sxs-lookup"><span data-stu-id="6e930-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="6e930-704">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="6e930-705">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-705">Checksum</span></span>

<span data-ttu-id="6e930-706">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-707">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-707">Definition</span></span>

<span data-ttu-id="6e930-708">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-709">Регулярное выражение `Regex_slovakia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-710">Найдено ключевое `Keywords_slovakia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-711">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-711">Keywords</span></span>

<span data-ttu-id="6e930-712">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-712"></span></span>
|<span data-ttu-id="6e930-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-714">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-714">dl#</span></span>  <br/> <span data-ttu-id="6e930-715">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-715">driver license</span></span>  <br/> <span data-ttu-id="6e930-716">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-716">driver license number</span></span>  <br/> <span data-ttu-id="6e930-717">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-717">driver licence</span></span>  <br/> <span data-ttu-id="6e930-718">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-718">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-719">drivers license</span></span>  <br/> <span data-ttu-id="6e930-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-720">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-721">driver's license</span></span>  <br/> <span data-ttu-id="6e930-722">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-722">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-723">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-723">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-724">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-724">driving license number</span></span>  <br/> <span data-ttu-id="6e930-725">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-725">dlno#</span></span>  <br/> <span data-ttu-id="6e930-726">водиčскý преуказ</span><span class="sxs-lookup"><span data-stu-id="6e930-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="6e930-727">Словения</span><span class="sxs-lookup"><span data-stu-id="6e930-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="6e930-728">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-728">Format</span></span>

<span data-ttu-id="6e930-729">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="6e930-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-730">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-730">Pattern</span></span>

<span data-ttu-id="6e930-731">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="6e930-732">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-732">Checksum</span></span>

<span data-ttu-id="6e930-733">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-734">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-734">Definition</span></span>

<span data-ttu-id="6e930-735">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-736">Регулярное выражение `Regex_slovenia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-737">Найдено ключевое `Keywords_slovenia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-738">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-738">Keywords</span></span>

<span data-ttu-id="6e930-739">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-739"></span></span>
|<span data-ttu-id="6e930-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-741">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-741">dl#</span></span>  <br/> <span data-ttu-id="6e930-742">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-742">driver license</span></span>  <br/> <span data-ttu-id="6e930-743">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-743">driver license number</span></span>  <br/> <span data-ttu-id="6e930-744">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-744">driver licence</span></span>  <br/> <span data-ttu-id="6e930-745">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-745">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-746">drivers license</span></span>  <br/> <span data-ttu-id="6e930-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-747">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-748">driver's license</span></span>  <br/> <span data-ttu-id="6e930-749">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-749">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-750">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-750">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-751">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-751">driving license number</span></span>  <br/> <span data-ttu-id="6e930-752">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-752">dlno#</span></span>  <br/> <span data-ttu-id="6e930-753">возниšко доволженже</span><span class="sxs-lookup"><span data-stu-id="6e930-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="6e930-754">Испания</span><span class="sxs-lookup"><span data-stu-id="6e930-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="6e930-755">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-755">Format</span></span>

<span data-ttu-id="6e930-756">Восемь цифр, за которыми следует один символ</span><span class="sxs-lookup"><span data-stu-id="6e930-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-757">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-757">Pattern</span></span>

<span data-ttu-id="6e930-758">Восемь цифр, за которыми следует один символ:</span><span class="sxs-lookup"><span data-stu-id="6e930-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="6e930-759">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="6e930-759">Eight digits</span></span> 
    
- <span data-ttu-id="6e930-760">Одна цифра или буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="6e930-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e930-761">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-761">Checksum</span></span>

<span data-ttu-id="6e930-762">Да</span><span class="sxs-lookup"><span data-stu-id="6e930-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-763">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-763">Definition</span></span>

<span data-ttu-id="6e930-764">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-765">Функция `Func_spain_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-766">Найдено ключевое `Keywords_spain_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6e930-767">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-767">Keywords</span></span>

<span data-ttu-id="6e930-768">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-768"></span></span>
|<span data-ttu-id="6e930-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-770">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-770">dlno#</span></span>  <br/> <span data-ttu-id="6e930-771">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-771">dl#</span></span>  <br/> <span data-ttu-id="6e930-772">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-772">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-773">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-773">driver licence</span></span>  <br/> <span data-ttu-id="6e930-774">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-774">driver license</span></span>  <br/> <span data-ttu-id="6e930-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-775">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-776">drivers license</span></span>  <br/> <span data-ttu-id="6e930-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="6e930-777">driver's licence</span></span>  <br/> <span data-ttu-id="6e930-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-778">driver's license</span></span>  <br/> <span data-ttu-id="6e930-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="6e930-779">driving licence</span></span>  <br/> <span data-ttu-id="6e930-780">driving license</span><span class="sxs-lookup"><span data-stu-id="6e930-780">driving license</span></span>  <br/> <span data-ttu-id="6e930-781">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-781">driver licence number</span></span>  <br/> <span data-ttu-id="6e930-782">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-782">driver license number</span></span>  <br/> <span data-ttu-id="6e930-783">драйвер номер лицензии</span><span class="sxs-lookup"><span data-stu-id="6e930-783">drivers licence number</span></span>  <br/> <span data-ttu-id="6e930-784">номер лицензии на драйверы</span><span class="sxs-lookup"><span data-stu-id="6e930-784">drivers license number</span></span>  <br/> <span data-ttu-id="6e930-785">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-785">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-786">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-786">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-787">номер водительской лицензии</span><span class="sxs-lookup"><span data-stu-id="6e930-787">driving licence number</span></span>  <br/> <span data-ttu-id="6e930-788">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-788">driving license number</span></span>  <br/> <span data-ttu-id="6e930-789">движущие разрешение</span><span class="sxs-lookup"><span data-stu-id="6e930-789">driving permit</span></span>  <br/> <span data-ttu-id="6e930-790">движущие число разрешений</span><span class="sxs-lookup"><span data-stu-id="6e930-790">driving permit number</span></span>  <br/> <span data-ttu-id="6e930-791">пермисо de кондукЦиóн</span><span class="sxs-lookup"><span data-stu-id="6e930-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="6e930-792">пермисо кондукЦиóн</span><span class="sxs-lookup"><span data-stu-id="6e930-792">permiso conducción</span></span>  <br/> <span data-ttu-id="6e930-793">нúмеро лиценЦиа кондуЦир</span><span class="sxs-lookup"><span data-stu-id="6e930-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="6e930-794">нúмеро de карнет де кондуЦир</span><span class="sxs-lookup"><span data-stu-id="6e930-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="6e930-795">нúмеро карнет кондуЦир</span><span class="sxs-lookup"><span data-stu-id="6e930-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="6e930-796">лиценЦиа кондуЦир</span><span class="sxs-lookup"><span data-stu-id="6e930-796">licencia conducir</span></span>  <br/> <span data-ttu-id="6e930-797">нúмеро de пермисо де кондуЦир</span><span class="sxs-lookup"><span data-stu-id="6e930-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="6e930-798">нúмеро де пермисо кондуЦир</span><span class="sxs-lookup"><span data-stu-id="6e930-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="6e930-799">нúмеро пермисо кондуЦир</span><span class="sxs-lookup"><span data-stu-id="6e930-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="6e930-800">пермисо кондуЦир</span><span class="sxs-lookup"><span data-stu-id="6e930-800">permiso conducir</span></span>  <br/> <span data-ttu-id="6e930-801">лиценЦиа de манежо</span><span class="sxs-lookup"><span data-stu-id="6e930-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="6e930-802">El карнет de кондуЦир</span><span class="sxs-lookup"><span data-stu-id="6e930-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="6e930-803">Карнет кондуЦир</span><span class="sxs-lookup"><span data-stu-id="6e930-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="6e930-804">Швеция</span><span class="sxs-lookup"><span data-stu-id="6e930-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="6e930-805">Format</span><span class="sxs-lookup"><span data-stu-id="6e930-805">Format</span></span>

<span data-ttu-id="6e930-806">Десять цифр, содержащие дефис</span><span class="sxs-lookup"><span data-stu-id="6e930-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="6e930-807">Шаблон</span><span class="sxs-lookup"><span data-stu-id="6e930-807">Pattern</span></span>

<span data-ttu-id="6e930-808">Десять цифр, содержащих дефис:</span><span class="sxs-lookup"><span data-stu-id="6e930-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="6e930-809">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="6e930-809">Six digits</span></span> 
    
- <span data-ttu-id="6e930-810">дефис;</span><span class="sxs-lookup"><span data-stu-id="6e930-810">A hyphen</span></span>
    
- <span data-ttu-id="6e930-811">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="6e930-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="6e930-812">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="6e930-812">Checksum</span></span>

<span data-ttu-id="6e930-813">Нет</span><span class="sxs-lookup"><span data-stu-id="6e930-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="6e930-814">Определение</span><span class="sxs-lookup"><span data-stu-id="6e930-814">Definition</span></span>

<span data-ttu-id="6e930-815">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="6e930-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="6e930-816">Регулярное выражение `Regex_sweden_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="6e930-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="6e930-817">Найдено ключевое `Keywords_sweden_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="6e930-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="6e930-818">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6e930-818">Keywords</span></span>

<span data-ttu-id="6e930-819">| |</span><span class="sxs-lookup"><span data-stu-id="6e930-819"></span></span>
|<span data-ttu-id="6e930-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="6e930-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="6e930-821">DL #</span><span class="sxs-lookup"><span data-stu-id="6e930-821">dl#</span></span>  <br/> <span data-ttu-id="6e930-822">driver license</span><span class="sxs-lookup"><span data-stu-id="6e930-822">driver license</span></span>  <br/> <span data-ttu-id="6e930-823">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-823">driver license number</span></span>  <br/> <span data-ttu-id="6e930-824">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-824">driver licence</span></span>  <br/> <span data-ttu-id="6e930-825">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="6e930-825">drivers lic.</span></span>  <br/> <span data-ttu-id="6e930-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="6e930-826">drivers license</span></span>  <br/> <span data-ttu-id="6e930-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6e930-827">drivers licence</span></span>  <br/> <span data-ttu-id="6e930-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="6e930-828">driver's license</span></span>  <br/> <span data-ttu-id="6e930-829">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-829">driver's license number</span></span>  <br/> <span data-ttu-id="6e930-830">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="6e930-830">driver's licence number</span></span>  <br/> <span data-ttu-id="6e930-831">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="6e930-831">driving license number</span></span>  <br/> <span data-ttu-id="6e930-832">длно #</span><span class="sxs-lookup"><span data-stu-id="6e930-832">dlno#</span></span>  <br/> <span data-ttu-id="6e930-833">кöркорт</span><span class="sxs-lookup"><span data-stu-id="6e930-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="6e930-834">ВОЗМЕЩЕН</span><span class="sxs-lookup"><span data-stu-id="6e930-834">UK</span></span>

<span data-ttu-id="6e930-835">Дополнительные сведения см. в разделе "Великобритания</span><span class="sxs-lookup"><span data-stu-id="6e930-835">For details, see the section "U.K.</span></span> <span data-ttu-id="6e930-836">Номер водительского удостоверения, в [котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="6e930-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6e930-837">См. также</span><span class="sxs-lookup"><span data-stu-id="6e930-837">See also</span></span>

[<span data-ttu-id="6e930-838">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="6e930-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

