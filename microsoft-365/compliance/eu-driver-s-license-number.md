---
title: Номер водительского удостоверения для драйвера ЕС
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации номера лицензии для драйвера ЕС. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: 2e75a8724dc91ef2d895c977fdd5fcc21e7a1da4
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938833"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="3ff6f-104">Номер водительского удостоверения для драйвера ЕС</span><span class="sxs-lookup"><span data-stu-id="3ff6f-104">EU Driver's License Number</span></span>

<span data-ttu-id="3ff6f-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации номера лицензии для драйвера ЕС.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="3ff6f-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="3ff6f-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="3ff6f-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-108">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-108">Format</span></span>

<span data-ttu-id="3ff6f-109">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="3ff6f-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-110">Pattern</span></span>

<span data-ttu-id="3ff6f-111">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3ff6f-112">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-112">Checksum</span></span>

<span data-ttu-id="3ff6f-113">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-114">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-114">Definition</span></span>

<span data-ttu-id="3ff6f-115">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-116">Регулярное выражение `Regex_austria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-117">Найдено ключевое `Keywords_austria_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="3ff6f-118">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-118">Keywords</span></span>

<span data-ttu-id="3ff6f-119">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-119">| |</span></span>
|<span data-ttu-id="3ff6f-120">**Keywords_austria_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-121">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-121">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-122">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-122">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-123">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-123">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-124">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-124">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-125">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-125">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-126">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-127">driver's licence</span></span>  <br/> <span data-ttu-id="3ff6f-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-128">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-129">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-129">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-130">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="3ff6f-131">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-131">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-132">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-132">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-133">фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="3ff6f-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="3ff6f-134">фухрерсчеин Републик остерреич</span><span class="sxs-lookup"><span data-stu-id="3ff6f-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="3ff6f-135">Бельгия</span><span class="sxs-lookup"><span data-stu-id="3ff6f-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-136">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-136">Format</span></span>

<span data-ttu-id="3ff6f-137">10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="3ff6f-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-138">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-138">Pattern</span></span>

<span data-ttu-id="3ff6f-139">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3ff6f-140">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-140">Checksum</span></span>

<span data-ttu-id="3ff6f-141">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-142">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-142">Definition</span></span>

<span data-ttu-id="3ff6f-143">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-144">Регулярное выражение `Regex_belgium_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-145">Найдено ключевое `Keywords_belgium_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="3ff6f-146">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-146">Keywords</span></span>

<span data-ttu-id="3ff6f-147">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-147">| |</span></span>
|<span data-ttu-id="3ff6f-148">**Keywords__belgium_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-149">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-149">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-150">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-150">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-151">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-151">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-152">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-152">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-153">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-153">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-154">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-155">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-156">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-157">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-157">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-158">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-158">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-159">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-159">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-160">рижбевижс</span><span class="sxs-lookup"><span data-stu-id="3ff6f-160">rijbewijs</span></span>  <br/> <span data-ttu-id="3ff6f-161">рижбевижснуммер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="3ff6f-162">фüхрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="3ff6f-163">фухрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="3ff6f-164">фуехрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="3ff6f-165">фüхрерсчеин — НР</span><span class="sxs-lookup"><span data-stu-id="3ff6f-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="3ff6f-166">фуехрерсчеин — НР</span><span class="sxs-lookup"><span data-stu-id="3ff6f-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="3ff6f-167">фуехрерсчеин — НР</span><span class="sxs-lookup"><span data-stu-id="3ff6f-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="3ff6f-168">Болгария</span><span class="sxs-lookup"><span data-stu-id="3ff6f-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-169">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-169">Format</span></span>

<span data-ttu-id="3ff6f-170">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="3ff6f-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-171">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-171">Pattern</span></span>

<span data-ttu-id="3ff6f-172">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3ff6f-173">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-173">Checksum</span></span>

<span data-ttu-id="3ff6f-174">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-175">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-175">Definition</span></span>

<span data-ttu-id="3ff6f-176">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-177">Регулярное выражение `Regex_bulgaria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-178">Найдено ключевое `Keywords_bulgaria_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="3ff6f-179">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-179">Keywords</span></span>

<span data-ttu-id="3ff6f-180">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-180">| |</span></span>
|<span data-ttu-id="3ff6f-181">**Keywords_bulgaria_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-182">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-182">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-183">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-183">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-184">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-184">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-185">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-185">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-186">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-186">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-187">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-188">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-189">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-190">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-190">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-191">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-191">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-192">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-192">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-193">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-193">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-194">свидетелство за управление на МПС</span><span class="sxs-lookup"><span data-stu-id="3ff6f-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="3ff6f-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="3ff6f-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="3ff6f-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="3ff6f-196">сумпс</span></span>  <br/> <span data-ttu-id="3ff6f-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="3ff6f-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="3ff6f-198">Хорватия</span><span class="sxs-lookup"><span data-stu-id="3ff6f-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-199">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-199">Format</span></span>

<span data-ttu-id="3ff6f-200">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="3ff6f-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-201">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-201">Pattern</span></span>

<span data-ttu-id="3ff6f-202">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3ff6f-203">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-203">Checksum</span></span>

<span data-ttu-id="3ff6f-204">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-205">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-205">Definition</span></span>

<span data-ttu-id="3ff6f-206">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-207">Регулярное выражение `Regex_croatia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-208">Найдено ключевое `Keywords_croatia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="3ff6f-209">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-209">Keywords</span></span>

<span data-ttu-id="3ff6f-210">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-210">| |</span></span>
|<span data-ttu-id="3ff6f-211">**Keywords_croatia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-212">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-212">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-213">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-213">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-214">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-214">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-215">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-215">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-216">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-216">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-217">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-218">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-219">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-220">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-220">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-221">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-221">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-222">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-222">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-223">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-223">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-224">возаčка дозвола</span><span class="sxs-lookup"><span data-stu-id="3ff6f-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="3ff6f-225">Кипр</span><span class="sxs-lookup"><span data-stu-id="3ff6f-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-226">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-226">Format</span></span>

<span data-ttu-id="3ff6f-227">12 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="3ff6f-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-228">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-228">Pattern</span></span>

<span data-ttu-id="3ff6f-229">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3ff6f-230">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-230">Checksum</span></span>

<span data-ttu-id="3ff6f-231">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-232">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-232">Definition</span></span>

<span data-ttu-id="3ff6f-233">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-234">Регулярное выражение `Regex_cyprus_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-235">Найдено ключевое `Keywords_cyprus_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-236">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-236">Keywords</span></span>

<span data-ttu-id="3ff6f-237">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-237">| |</span></span>
|<span data-ttu-id="3ff6f-238">**Keywords_cyprus_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-239">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-239">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-240">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-240">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-241">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-241">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-242">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-242">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-243">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-243">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-244">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-245">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-246">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-246">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-247">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-247">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-248">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-248">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-249">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-249">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="3ff6f-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="3ff6f-251">Чехия</span><span class="sxs-lookup"><span data-stu-id="3ff6f-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-252">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-252">Format</span></span>

<span data-ttu-id="3ff6f-253">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-254">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-254">Pattern</span></span>

<span data-ttu-id="3ff6f-255">Восемь букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="3ff6f-256">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="3ff6f-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="3ff6f-257">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="3ff6f-257">A space (optional)</span></span>
    
- <span data-ttu-id="3ff6f-258">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-259">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-259">Checksum</span></span>

<span data-ttu-id="3ff6f-260">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-261">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-261">Definition</span></span>

<span data-ttu-id="3ff6f-262">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-263">Регулярное выражение `Regex_czech_republic_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-264">Найдено ключевое `Keywords_czech_republic_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="3ff6f-265">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-265">Keywords</span></span>

<span data-ttu-id="3ff6f-266">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-266">| |</span></span>
|<span data-ttu-id="3ff6f-267">**Keywords_czech_republic_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-268">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-268">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-269">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-269">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-270">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-270">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-271">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-271">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-272">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-272">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-273">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-274">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-275">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-276">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-276">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-277">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-277">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-278">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-278">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-279">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-279">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-280">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-280">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-281">řидиčскý прúказ</span><span class="sxs-lookup"><span data-stu-id="3ff6f-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="3ff6f-282">Дания</span><span class="sxs-lookup"><span data-stu-id="3ff6f-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-283">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-283">Format</span></span>

<span data-ttu-id="3ff6f-284">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="3ff6f-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-285">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-285">Pattern</span></span>

<span data-ttu-id="3ff6f-286">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3ff6f-287">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-287">Checksum</span></span>

<span data-ttu-id="3ff6f-288">Да</span><span class="sxs-lookup"><span data-stu-id="3ff6f-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-289">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-289">Definition</span></span>

<span data-ttu-id="3ff6f-290">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-291">Регулярное выражение `Regex_denmark_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-292">Найдено ключевое `Keywords_denmark_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="3ff6f-293">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-293">Keywords</span></span>

<span data-ttu-id="3ff6f-294">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-294">| |</span></span>
|<span data-ttu-id="3ff6f-295">**Keywords_denmark_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-296">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-296">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-297">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-297">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-298">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-298">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-299">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-299">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-300">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-300">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-301">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-302">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-303">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-304">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-304">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-305">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-305">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-306">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-306">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-307">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-307">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-308">кøрекорт</span><span class="sxs-lookup"><span data-stu-id="3ff6f-308">kørekort</span></span>  <br/> <span data-ttu-id="3ff6f-309">кøрекортнуммер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="3ff6f-310">Эстония</span><span class="sxs-lookup"><span data-stu-id="3ff6f-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-311">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-311">Format</span></span>

<span data-ttu-id="3ff6f-312">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-313">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-313">Pattern</span></span>

<span data-ttu-id="3ff6f-314">Две буквы и шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="3ff6f-315">Буквы "ET" (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="3ff6f-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="3ff6f-316">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-317">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-317">Checksum</span></span>

<span data-ttu-id="3ff6f-318">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-319">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-319">Definition</span></span>

<span data-ttu-id="3ff6f-320">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-321">Регулярное выражение `Regex_estonia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-322">Найдено ключевое `Keywords_estonia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-323">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-323">Keywords</span></span>

<span data-ttu-id="3ff6f-324">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-324">| |</span></span>
|<span data-ttu-id="3ff6f-325">**Keywords_estonia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-326">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-326">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-327">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-327">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-328">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-328">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-329">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-329">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-330">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-330">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-331">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-331">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-332">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-333">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-334">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-335">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-335">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-336">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-336">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-337">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-337">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="3ff6f-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="3ff6f-339">Финляндия</span><span class="sxs-lookup"><span data-stu-id="3ff6f-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-340">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-340">Format</span></span>

<span data-ttu-id="3ff6f-341">10 цифр, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-342">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-342">Pattern</span></span>

<span data-ttu-id="3ff6f-343">10 цифр, содержащих дефис:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="3ff6f-344">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="3ff6f-344">Six digits</span></span> 
    
- <span data-ttu-id="3ff6f-345">дефис;</span><span class="sxs-lookup"><span data-stu-id="3ff6f-345">A hyphen</span></span>
    
-  <span data-ttu-id="3ff6f-346">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="3ff6f-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-347">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-347">Checksum</span></span>

<span data-ttu-id="3ff6f-348">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-349">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-349">Definition</span></span>

<span data-ttu-id="3ff6f-350">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-351">Регулярное выражение `Regex_finland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-352">Найдено ключевое `Keywords_finland_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-353">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-353">Keywords</span></span>

<span data-ttu-id="3ff6f-354">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-354">| |</span></span>
|<span data-ttu-id="3ff6f-355">**Keywords_finland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-356">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-356">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-357">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-357">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-358">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-358">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-359">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-359">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-360">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-360">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-361">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-362">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-363">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-364">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-364">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-365">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-365">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-366">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-366">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-367">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-367">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-368">ажокортти</span><span class="sxs-lookup"><span data-stu-id="3ff6f-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="3ff6f-369">Франция</span><span class="sxs-lookup"><span data-stu-id="3ff6f-369">France</span></span>

<span data-ttu-id="3ff6f-370">Дополнительные сведения см. в разделе "номер водительского удостоверения для Франции" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3ff6f-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="3ff6f-371">Германия</span><span class="sxs-lookup"><span data-stu-id="3ff6f-371">Germany</span></span>

<span data-ttu-id="3ff6f-372">Дополнительные сведения можно найти в разделе "номер водительского удостоверения для немецкого драйвера" [, который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3ff6f-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="3ff6f-373">Греция</span><span class="sxs-lookup"><span data-stu-id="3ff6f-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-374">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-374">Format</span></span>

<span data-ttu-id="3ff6f-375">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="3ff6f-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-376">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-376">Pattern</span></span>

 <span data-ttu-id="3ff6f-377">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3ff6f-378">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-378">Checksum</span></span>

<span data-ttu-id="3ff6f-379">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-380">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-380">Definition</span></span>

<span data-ttu-id="3ff6f-381">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-382">Регулярное выражение `Regex_greece_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-383">Найдено ключевое `Keywords_greece_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-384">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-384">Keywords</span></span>

<span data-ttu-id="3ff6f-385">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-385">| |</span></span>
|<span data-ttu-id="3ff6f-386">**Keywords_greece_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-387">Файл #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-387">dlL#</span></span>  <br/> <span data-ttu-id="3ff6f-388">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-388">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-389">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-389">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-390">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-390">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-391">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-391">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-392">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-393">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-394">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-395">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-395">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-396">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-396">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-397">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-397">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-398">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-398">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="3ff6f-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="3ff6f-400">Адеиа одигисис</span><span class="sxs-lookup"><span data-stu-id="3ff6f-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="3ff6f-401">Венгрия</span><span class="sxs-lookup"><span data-stu-id="3ff6f-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-402">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-402">Format</span></span>

<span data-ttu-id="3ff6f-403">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-404">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-404">Pattern</span></span>

<span data-ttu-id="3ff6f-405">Две буквы и шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="3ff6f-406">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="3ff6f-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="3ff6f-407">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-408">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-408">Checksum</span></span>

<span data-ttu-id="3ff6f-409">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-410">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-410">Definition</span></span>

<span data-ttu-id="3ff6f-411">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-412">Регулярное выражение `Regex_hungary_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-413">Найдено ключевое `Keywords_hungary_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-414">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-414">Keywords</span></span>

<span data-ttu-id="3ff6f-415">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-415">| |</span></span>
|<span data-ttu-id="3ff6f-416">**Keywords_hungary_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-417">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-417">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-418">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-418">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-419">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-419">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-420">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-420">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-421">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-421">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-422">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-423">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-424">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-425">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-425">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-426">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-426">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-427">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-427">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-428">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-428">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-429">везетои енжедели</span><span class="sxs-lookup"><span data-stu-id="3ff6f-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="3ff6f-430">Ирландия</span><span class="sxs-lookup"><span data-stu-id="3ff6f-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-431">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-431">Format</span></span>

<span data-ttu-id="3ff6f-432">Шесть цифр, за которыми следуют четыре буквы</span><span class="sxs-lookup"><span data-stu-id="3ff6f-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-433">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-433">Pattern</span></span>

<span data-ttu-id="3ff6f-434">Шесть цифр и четыре буквы:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="3ff6f-435">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="3ff6f-435">Six digits</span></span>
    
- <span data-ttu-id="3ff6f-436">Четыре буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="3ff6f-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-437">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-437">Checksum</span></span>

<span data-ttu-id="3ff6f-438">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-439">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-439">Definition</span></span>

<span data-ttu-id="3ff6f-440">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-441">Регулярное выражение `Regex_ireland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-442">Найдено ключевое `Keywords_ireland_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-443">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-443">Keywords</span></span>

<span data-ttu-id="3ff6f-444">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-444">| |</span></span>
|<span data-ttu-id="3ff6f-445">**Keywords_ireland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-446">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-446">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-447">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-447">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-448">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-448">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-449">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-449">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-450">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-450">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-451">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-452">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-453">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-454">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-454">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-455">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-455">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-456">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-456">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-457">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-457">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-458">цеадúнас тиомáна</span><span class="sxs-lookup"><span data-stu-id="3ff6f-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="3ff6f-459">Италия</span><span class="sxs-lookup"><span data-stu-id="3ff6f-459">Italy</span></span>

<span data-ttu-id="3ff6f-460">Дополнительные сведения см. в разделе "номер водительского удостоверения для Италии" [, который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3ff6f-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="3ff6f-461">Латвия</span><span class="sxs-lookup"><span data-stu-id="3ff6f-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-462">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-462">Format</span></span>

<span data-ttu-id="3ff6f-463">Три буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-464">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-464">Pattern</span></span>

<span data-ttu-id="3ff6f-465">Три буквы и шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="3ff6f-466">Три буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="3ff6f-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="3ff6f-467">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-468">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-468">Checksum</span></span>

<span data-ttu-id="3ff6f-469">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-470">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-470">Definition</span></span>

<span data-ttu-id="3ff6f-471">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-472">Регулярное выражение `Regex_latvia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-473">Найдено ключевое `Keywords_latvia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-474">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-474">Keywords</span></span>

<span data-ttu-id="3ff6f-475">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-475">| |</span></span>
|<span data-ttu-id="3ff6f-476">**Keywords_latvia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-477">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-477">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-478">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-478">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-479">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-479">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-480">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-480">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-481">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-481">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-482">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-483">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-484">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-485">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-485">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-486">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-486">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-487">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-487">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-488">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-488">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-489">аутовадīтāжа аплиекīба</span><span class="sxs-lookup"><span data-stu-id="3ff6f-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="3ff6f-490">Литва</span><span class="sxs-lookup"><span data-stu-id="3ff6f-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-491">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-491">Format</span></span>

<span data-ttu-id="3ff6f-492">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="3ff6f-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-493">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-493">Pattern</span></span>

 <span data-ttu-id="3ff6f-494">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3ff6f-495">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-495">Checksum</span></span>

<span data-ttu-id="3ff6f-496">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-497">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-497">Definition</span></span>

<span data-ttu-id="3ff6f-498">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-499">Регулярное выражение `Regex_lithuania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-500">Найдено ключевое `Keywords_lithuania_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-501">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-501">Keywords</span></span>

<span data-ttu-id="3ff6f-502">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-502">| |</span></span>
|<span data-ttu-id="3ff6f-503">**Keywords_lithuania_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-504">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-504">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-505">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-505">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-506">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-506">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-507">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-507">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-508">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-508">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-509">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-510">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-511">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-512">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-512">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-513">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-513">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-514">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-514">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-515">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-515">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-516">ваируотожо паžимėжимас</span><span class="sxs-lookup"><span data-stu-id="3ff6f-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="3ff6f-517">луксембург</span><span class="sxs-lookup"><span data-stu-id="3ff6f-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-518">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-518">Format</span></span>

<span data-ttu-id="3ff6f-519">Шесть цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="3ff6f-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-520">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-520">Pattern</span></span>

 <span data-ttu-id="3ff6f-521">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="3ff6f-522">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-522">Checksum</span></span>

<span data-ttu-id="3ff6f-523">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-524">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-524">Definition</span></span>

<span data-ttu-id="3ff6f-525">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-526">Регулярное выражение `Regex_luxemburg_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-527">Найдено ключевое `Keywords_luxemburg_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-528">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-528">Keywords</span></span>

<span data-ttu-id="3ff6f-529">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-529">| |</span></span>
|<span data-ttu-id="3ff6f-530">**Keywords_luxemburg_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-531">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-531">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-532">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-532">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-533">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-533">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-534">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-534">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-535">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-535">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-536">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-537">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-538">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-539">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-539">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-540">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-540">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-541">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-541">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-542">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-542">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-543">фахрерлаубнис</span><span class="sxs-lookup"><span data-stu-id="3ff6f-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="3ff6f-544">Мальта</span><span class="sxs-lookup"><span data-stu-id="3ff6f-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-545">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-545">Format</span></span>

<span data-ttu-id="3ff6f-546">Сочетание двух символов и шести цифр в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="3ff6f-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-547">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-547">Pattern</span></span>

<span data-ttu-id="3ff6f-548">Сочетание двух символов и шести цифр:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="3ff6f-549">Два символа (цифры или буквы без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="3ff6f-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="3ff6f-550">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="3ff6f-550">A space (optional)</span></span>
    
- <span data-ttu-id="3ff6f-551">три цифры; </span><span class="sxs-lookup"><span data-stu-id="3ff6f-551">Three digits</span></span>
    
- <span data-ttu-id="3ff6f-552">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="3ff6f-552">A space (optional)</span></span>
    
- <span data-ttu-id="3ff6f-553">Три цифры</span><span class="sxs-lookup"><span data-stu-id="3ff6f-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-554">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-554">Checksum</span></span>

<span data-ttu-id="3ff6f-555">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-556">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-556">Definition</span></span>

<span data-ttu-id="3ff6f-557">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-558">Регулярное выражение `Regex_malta_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-559">Найдено ключевое `Keywords_malta_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-560">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-560">Keywords</span></span>

<span data-ttu-id="3ff6f-561">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-561">| |</span></span>
|<span data-ttu-id="3ff6f-562">**Keywords_malta_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-563">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-563">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-564">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-564">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-565">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-565">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-566">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-566">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-567">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-567">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-568">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-569">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-570">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-571">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-571">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-572">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-572">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-573">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-573">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-574">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-574">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-575">лиċензжаные зада Севкан</span><span class="sxs-lookup"><span data-stu-id="3ff6f-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="3ff6f-576">Нидерланды</span><span class="sxs-lookup"><span data-stu-id="3ff6f-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-577">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-577">Format</span></span>

<span data-ttu-id="3ff6f-578">10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="3ff6f-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-579">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-579">Pattern</span></span>

<span data-ttu-id="3ff6f-580">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3ff6f-581">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-581">Checksum</span></span>

<span data-ttu-id="3ff6f-582">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-583">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-583">Definition</span></span>

<span data-ttu-id="3ff6f-584">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-585">Регулярное выражение `Regex_netherlands_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-586">Найдено ключевое `Keywords_netherlands_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-587">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-587">Keywords</span></span>

<span data-ttu-id="3ff6f-588">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-588">| |</span></span>
|<span data-ttu-id="3ff6f-589">**Keywords_netherlands_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-590">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-590">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-591">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-591">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-592">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-592">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-593">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-593">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-594">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-594">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-595">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-596">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-597">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-598">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-598">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-599">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-599">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-600">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-600">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-601">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-601">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="3ff6f-602">permis de conduire</span></span>  <br/> <span data-ttu-id="3ff6f-603">рижбевижс</span><span class="sxs-lookup"><span data-stu-id="3ff6f-603">rijbewijs</span></span>  <br/> <span data-ttu-id="3ff6f-604">рижбевижснуммер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="3ff6f-605">Польша</span><span class="sxs-lookup"><span data-stu-id="3ff6f-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-606">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-606">Format</span></span>

<span data-ttu-id="3ff6f-607">14 цифр, содержащих 2 косых черты.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-608">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-608">Pattern</span></span>

<span data-ttu-id="3ff6f-609">14 цифр и 2 косых черт:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="3ff6f-610">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="3ff6f-610">Five digits</span></span> 
    
- <span data-ttu-id="3ff6f-611">косая черта;</span><span class="sxs-lookup"><span data-stu-id="3ff6f-611">A forward slash</span></span>
    
- <span data-ttu-id="3ff6f-612">Две цифры</span><span class="sxs-lookup"><span data-stu-id="3ff6f-612">Two digits</span></span>
    
- <span data-ttu-id="3ff6f-613">косая черта;</span><span class="sxs-lookup"><span data-stu-id="3ff6f-613">A forward slash</span></span>
    
- <span data-ttu-id="3ff6f-614">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-615">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-615">Checksum</span></span>

<span data-ttu-id="3ff6f-616">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-617">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-617">Definition</span></span>

<span data-ttu-id="3ff6f-618">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-619">Регулярное выражение `Regex_poland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-620">Найдено ключевое `Keywords_poland_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-621">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-621">Keywords</span></span>

<span data-ttu-id="3ff6f-622">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-622">| |</span></span>
|<span data-ttu-id="3ff6f-623">**Keywords_poland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-624">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-624">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-625">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-625">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-626">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-626">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-627">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-627">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-628">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-628">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-629">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-630">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-631">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-632">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-632">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-633">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-633">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-634">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-634">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-635">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-635">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-636">право жазди</span><span class="sxs-lookup"><span data-stu-id="3ff6f-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="3ff6f-637">Португалия</span><span class="sxs-lookup"><span data-stu-id="3ff6f-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-638">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-638">Format</span></span>

<span data-ttu-id="3ff6f-639">Две буквы, за которыми следуют семь чисел в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="3ff6f-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-640">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-640">Pattern</span></span>

<span data-ttu-id="3ff6f-641">Две буквы, за которыми следуют семь цифр со специальными символами:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="3ff6f-642">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="3ff6f-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="3ff6f-643">дефис;</span><span class="sxs-lookup"><span data-stu-id="3ff6f-643">A hyphen</span></span>
    
- <span data-ttu-id="3ff6f-644">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="3ff6f-644">Six digits</span></span>
    
- <span data-ttu-id="3ff6f-645">Пробел</span><span class="sxs-lookup"><span data-stu-id="3ff6f-645">A space</span></span>
    
- <span data-ttu-id="3ff6f-646">одна цифра.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-647">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-647">Checksum</span></span>

<span data-ttu-id="3ff6f-648">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-649">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-649">Definition</span></span>

<span data-ttu-id="3ff6f-650">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-651">Регулярное выражение `Regex_portugal_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-652">Найдено ключевое `Keywords_portugal_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-653">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-653">Keywords</span></span>

<span data-ttu-id="3ff6f-654">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-654">| |</span></span>
|<span data-ttu-id="3ff6f-655">**Keywords_portugal_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-656">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-656">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-657">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-657">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-658">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-658">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-659">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-659">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-660">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-660">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-661">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-662">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-663">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-664">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-664">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-665">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-665">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-666">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-666">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-667">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-667">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-668">картеира de моториста</span><span class="sxs-lookup"><span data-stu-id="3ff6f-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="3ff6f-669">Румыния</span><span class="sxs-lookup"><span data-stu-id="3ff6f-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-670">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-670">Format</span></span>

<span data-ttu-id="3ff6f-671">Один символ, за которым следуют восемь цифр</span><span class="sxs-lookup"><span data-stu-id="3ff6f-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-672">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-672">Pattern</span></span>

<span data-ttu-id="3ff6f-673">Один символ, за которым следуют восемь цифр:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="3ff6f-674">Одна буква (без учета регистра) или цифра</span><span class="sxs-lookup"><span data-stu-id="3ff6f-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="3ff6f-675">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-676">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-676">Checksum</span></span>

<span data-ttu-id="3ff6f-677">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-678">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-678">Definition</span></span>

<span data-ttu-id="3ff6f-679">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-680">Регулярное выражение `Regex_romania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-681">Найдено ключевое `Keywords_romania_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-682">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-682">Keywords</span></span>

<span data-ttu-id="3ff6f-683">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-683">| |</span></span>
|<span data-ttu-id="3ff6f-684">**Keywords_romania_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-685">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-685">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-686">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-686">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-687">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-687">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-688">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-688">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-689">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-689">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-690">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-691">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-692">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-693">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-693">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-694">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-694">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-695">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-695">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-696">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-696">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-697">разрешение de кондуцере</span><span class="sxs-lookup"><span data-stu-id="3ff6f-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="3ff6f-698">Словакия</span><span class="sxs-lookup"><span data-stu-id="3ff6f-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-699">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-699">Format</span></span>

<span data-ttu-id="3ff6f-700">Один символ, за которым следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-701">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-701">Pattern</span></span>

<span data-ttu-id="3ff6f-702">Один символ, за которым следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="3ff6f-703">Одна буква (без учета регистра) или цифра</span><span class="sxs-lookup"><span data-stu-id="3ff6f-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="3ff6f-704">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-705">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-705">Checksum</span></span>

<span data-ttu-id="3ff6f-706">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-707">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-707">Definition</span></span>

<span data-ttu-id="3ff6f-708">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-709">Регулярное выражение `Regex_slovakia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-710">Найдено ключевое `Keywords_slovakia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-711">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-711">Keywords</span></span>

<span data-ttu-id="3ff6f-712">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-712">| |</span></span>
|<span data-ttu-id="3ff6f-713">**Keywords_slovakia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-714">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-714">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-715">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-715">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-716">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-716">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-717">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-717">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-718">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-718">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-719">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-720">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-721">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-722">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-722">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-723">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-723">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-724">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-724">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-725">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-725">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-726">водиčскý преуказ</span><span class="sxs-lookup"><span data-stu-id="3ff6f-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="3ff6f-727">Словения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-728">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-728">Format</span></span>

<span data-ttu-id="3ff6f-729">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="3ff6f-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-730">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-730">Pattern</span></span>

<span data-ttu-id="3ff6f-731">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="3ff6f-732">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-732">Checksum</span></span>

<span data-ttu-id="3ff6f-733">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-734">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-734">Definition</span></span>

<span data-ttu-id="3ff6f-735">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-736">Регулярное выражение `Regex_slovenia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-737">Найдено ключевое `Keywords_slovenia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-738">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-738">Keywords</span></span>

<span data-ttu-id="3ff6f-739">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-739">| |</span></span>
|<span data-ttu-id="3ff6f-740">**Keywords_slovenia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-741">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-741">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-742">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-742">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-743">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-743">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-744">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-744">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-745">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-745">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-746">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-747">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-748">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-749">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-749">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-750">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-750">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-751">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-751">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-752">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-752">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-753">возниšко доволженже</span><span class="sxs-lookup"><span data-stu-id="3ff6f-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="3ff6f-754">Испания</span><span class="sxs-lookup"><span data-stu-id="3ff6f-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-755">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-755">Format</span></span>

<span data-ttu-id="3ff6f-756">Восемь цифр, за которыми следует один символ</span><span class="sxs-lookup"><span data-stu-id="3ff6f-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-757">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-757">Pattern</span></span>

<span data-ttu-id="3ff6f-758">Восемь цифр, за которыми следует один символ:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="3ff6f-759">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-759">Eight digits</span></span> 
    
- <span data-ttu-id="3ff6f-760">Одна цифра или буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="3ff6f-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-761">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-761">Checksum</span></span>

<span data-ttu-id="3ff6f-762">Да</span><span class="sxs-lookup"><span data-stu-id="3ff6f-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-763">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-763">Definition</span></span>

<span data-ttu-id="3ff6f-764">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-765">Функция `Func_spain_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-766">Найдено ключевое `Keywords_spain_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-767">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-767">Keywords</span></span>

<span data-ttu-id="3ff6f-768">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-768">| |</span></span>
|<span data-ttu-id="3ff6f-769">**Keywords_spain_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-770">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-770">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-771">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-771">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-772">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-772">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-773">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-773">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-774">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-774">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-775">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-776">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-777">driver's licence</span></span>  <br/> <span data-ttu-id="3ff6f-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-778">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-779">driving licence</span></span>  <br/> <span data-ttu-id="3ff6f-780">driving license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-780">driving license</span></span>  <br/> <span data-ttu-id="3ff6f-781">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-781">driver licence number</span></span>  <br/> <span data-ttu-id="3ff6f-782">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-782">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-783">драйвер номер лицензии</span><span class="sxs-lookup"><span data-stu-id="3ff6f-783">drivers licence number</span></span>  <br/> <span data-ttu-id="3ff6f-784">номер лицензии на драйверы</span><span class="sxs-lookup"><span data-stu-id="3ff6f-784">drivers license number</span></span>  <br/> <span data-ttu-id="3ff6f-785">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-785">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-786">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-786">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-787">номер водительской лицензии</span><span class="sxs-lookup"><span data-stu-id="3ff6f-787">driving licence number</span></span>  <br/> <span data-ttu-id="3ff6f-788">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-788">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-789">движущие разрешение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-789">driving permit</span></span>  <br/> <span data-ttu-id="3ff6f-790">движущие число разрешений</span><span class="sxs-lookup"><span data-stu-id="3ff6f-790">driving permit number</span></span>  <br/> <span data-ttu-id="3ff6f-791">пермисо de кондукЦиóн</span><span class="sxs-lookup"><span data-stu-id="3ff6f-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="3ff6f-792">пермисо кондукЦиóн</span><span class="sxs-lookup"><span data-stu-id="3ff6f-792">permiso conducción</span></span>  <br/> <span data-ttu-id="3ff6f-793">нúмеро лиценЦиа кондуЦир</span><span class="sxs-lookup"><span data-stu-id="3ff6f-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="3ff6f-794">нúмеро de карнет де кондуЦир</span><span class="sxs-lookup"><span data-stu-id="3ff6f-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="3ff6f-795">нúмеро карнет кондуЦир</span><span class="sxs-lookup"><span data-stu-id="3ff6f-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="3ff6f-796">лиценЦиа кондуЦир</span><span class="sxs-lookup"><span data-stu-id="3ff6f-796">licencia conducir</span></span>  <br/> <span data-ttu-id="3ff6f-797">нúмеро de пермисо де кондуЦир</span><span class="sxs-lookup"><span data-stu-id="3ff6f-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="3ff6f-798">нúмеро де пермисо кондуЦир</span><span class="sxs-lookup"><span data-stu-id="3ff6f-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="3ff6f-799">нúмеро пермисо кондуЦир</span><span class="sxs-lookup"><span data-stu-id="3ff6f-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="3ff6f-800">пермисо кондуЦир</span><span class="sxs-lookup"><span data-stu-id="3ff6f-800">permiso conducir</span></span>  <br/> <span data-ttu-id="3ff6f-801">лиценЦиа de манежо</span><span class="sxs-lookup"><span data-stu-id="3ff6f-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="3ff6f-802">El карнет de кондуЦир</span><span class="sxs-lookup"><span data-stu-id="3ff6f-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="3ff6f-803">Карнет кондуЦир</span><span class="sxs-lookup"><span data-stu-id="3ff6f-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="3ff6f-804">Швеция</span><span class="sxs-lookup"><span data-stu-id="3ff6f-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="3ff6f-805">Format</span><span class="sxs-lookup"><span data-stu-id="3ff6f-805">Format</span></span>

<span data-ttu-id="3ff6f-806">Десять цифр, содержащие дефис</span><span class="sxs-lookup"><span data-stu-id="3ff6f-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="3ff6f-807">Шаблон</span><span class="sxs-lookup"><span data-stu-id="3ff6f-807">Pattern</span></span>

<span data-ttu-id="3ff6f-808">Десять цифр, содержащих дефис:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="3ff6f-809">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="3ff6f-809">Six digits</span></span> 
    
- <span data-ttu-id="3ff6f-810">дефис;</span><span class="sxs-lookup"><span data-stu-id="3ff6f-810">A hyphen</span></span>
    
- <span data-ttu-id="3ff6f-811">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="3ff6f-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="3ff6f-812">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="3ff6f-812">Checksum</span></span>

<span data-ttu-id="3ff6f-813">Нет</span><span class="sxs-lookup"><span data-stu-id="3ff6f-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="3ff6f-814">Определение</span><span class="sxs-lookup"><span data-stu-id="3ff6f-814">Definition</span></span>

<span data-ttu-id="3ff6f-815">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="3ff6f-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="3ff6f-816">Регулярное выражение `Regex_sweden_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="3ff6f-817">Найдено ключевое `Keywords_sweden_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="3ff6f-818">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="3ff6f-818">Keywords</span></span>

<span data-ttu-id="3ff6f-819">| |</span><span class="sxs-lookup"><span data-stu-id="3ff6f-819">| |</span></span>
|<span data-ttu-id="3ff6f-820">**Keywords_sweden_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="3ff6f-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="3ff6f-821">DL #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-821">dl#</span></span>  <br/> <span data-ttu-id="3ff6f-822">driver license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-822">driver license</span></span>  <br/> <span data-ttu-id="3ff6f-823">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-823">driver license number</span></span>  <br/> <span data-ttu-id="3ff6f-824">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-824">driver licence</span></span>  <br/> <span data-ttu-id="3ff6f-825">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="3ff6f-825">drivers lic.</span></span>  <br/> <span data-ttu-id="3ff6f-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-826">drivers license</span></span>  <br/> <span data-ttu-id="3ff6f-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="3ff6f-827">drivers licence</span></span>  <br/> <span data-ttu-id="3ff6f-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="3ff6f-828">driver's license</span></span>  <br/> <span data-ttu-id="3ff6f-829">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-829">driver's license number</span></span>  <br/> <span data-ttu-id="3ff6f-830">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="3ff6f-830">driver's licence number</span></span>  <br/> <span data-ttu-id="3ff6f-831">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="3ff6f-831">driving license number</span></span>  <br/> <span data-ttu-id="3ff6f-832">длно #</span><span class="sxs-lookup"><span data-stu-id="3ff6f-832">dlno#</span></span>  <br/> <span data-ttu-id="3ff6f-833">кöркорт</span><span class="sxs-lookup"><span data-stu-id="3ff6f-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="3ff6f-834">ВОЗМЕЩЕН</span><span class="sxs-lookup"><span data-stu-id="3ff6f-834">UK</span></span>

<span data-ttu-id="3ff6f-835">Дополнительные сведения см. в разделе "Великобритания</span><span class="sxs-lookup"><span data-stu-id="3ff6f-835">For details, see the section "U.K.</span></span> <span data-ttu-id="3ff6f-836">Номер водительского удостоверения, в [котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="3ff6f-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3ff6f-837">См. также</span><span class="sxs-lookup"><span data-stu-id="3ff6f-837">See also</span></span>

[<span data-ttu-id="3ff6f-838">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="3ff6f-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

