---
title: Номер водительского удостоверения для драйвера ЕС
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
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации номера лицензии для драйвера ЕС. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: c54fcefcda08d0bc2ec500d25c74bb5789e27398
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592660"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="1b430-104">Номер водительского удостоверения для драйвера ЕС</span><span class="sxs-lookup"><span data-stu-id="1b430-104">EU Driver's License Number</span></span>

<span data-ttu-id="1b430-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации номера лицензии для драйвера ЕС.</span><span class="sxs-lookup"><span data-stu-id="1b430-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="1b430-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="1b430-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="1b430-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="1b430-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="1b430-108">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-108">Format</span></span>

<span data-ttu-id="1b430-109">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="1b430-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-110">Pattern</span></span>

<span data-ttu-id="1b430-111">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1b430-112">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-112">Checksum</span></span>

<span data-ttu-id="1b430-113">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-114">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-114">Definition</span></span>

<span data-ttu-id="1b430-115">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-116">Регулярное выражение `Regex_austria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-117">Найдено ключевое `Keywords_austria_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="1b430-118">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-118">Keywords</span></span>

<span data-ttu-id="1b430-119">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-119">| |</span></span>
|<span data-ttu-id="1b430-120">**Keywords_austria_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-121">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-121">dl#</span></span>  <br/> <span data-ttu-id="1b430-122">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-122">driver license</span></span>  <br/> <span data-ttu-id="1b430-123">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-123">driver license number</span></span>  <br/> <span data-ttu-id="1b430-124">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-124">driver licence</span></span>  <br/> <span data-ttu-id="1b430-125">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-125">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-126">drivers license</span></span>  <br/> <span data-ttu-id="1b430-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="1b430-127">driver's licence</span></span>  <br/> <span data-ttu-id="1b430-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-128">driver's license</span></span>  <br/> <span data-ttu-id="1b430-129">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-129">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-130">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="1b430-131">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-131">driving license number</span></span>  <br/> <span data-ttu-id="1b430-132">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-132">dlno#</span></span>  <br/> <span data-ttu-id="1b430-133">фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="1b430-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="1b430-134">фухрерсчеин Републик остерреич</span><span class="sxs-lookup"><span data-stu-id="1b430-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="1b430-135">Бельгия</span><span class="sxs-lookup"><span data-stu-id="1b430-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="1b430-136">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-136">Format</span></span>

<span data-ttu-id="1b430-137">10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="1b430-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-138">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-138">Pattern</span></span>

<span data-ttu-id="1b430-139">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1b430-140">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-140">Checksum</span></span>

<span data-ttu-id="1b430-141">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-142">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-142">Definition</span></span>

<span data-ttu-id="1b430-143">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-144">Регулярное выражение `Regex_belgium_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-145">Найдено ключевое `Keywords_belgium_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="1b430-146">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-146">Keywords</span></span>

<span data-ttu-id="1b430-147">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-147">| |</span></span>
|<span data-ttu-id="1b430-148">**Keywords__belgium_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-149">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-149">dl#</span></span>  <br/> <span data-ttu-id="1b430-150">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-150">driver license</span></span>  <br/> <span data-ttu-id="1b430-151">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-151">driver license number</span></span>  <br/> <span data-ttu-id="1b430-152">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-152">driver licence</span></span>  <br/> <span data-ttu-id="1b430-153">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-153">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-154">drivers license</span></span>  <br/> <span data-ttu-id="1b430-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-155">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-156">driver's license</span></span>  <br/> <span data-ttu-id="1b430-157">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-157">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-158">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-158">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-159">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-159">dlno#</span></span>  <br/> <span data-ttu-id="1b430-160">рижбевижс</span><span class="sxs-lookup"><span data-stu-id="1b430-160">rijbewijs</span></span>  <br/> <span data-ttu-id="1b430-161">рижбевижснуммер</span><span class="sxs-lookup"><span data-stu-id="1b430-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="1b430-162">фüхрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="1b430-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="1b430-163">фухрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="1b430-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="1b430-164">фуехрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="1b430-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="1b430-165">фüхрерсчеин — НР</span><span class="sxs-lookup"><span data-stu-id="1b430-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="1b430-166">фуехрерсчеин — НР</span><span class="sxs-lookup"><span data-stu-id="1b430-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="1b430-167">фуехрерсчеин — НР</span><span class="sxs-lookup"><span data-stu-id="1b430-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="1b430-168">Болгария</span><span class="sxs-lookup"><span data-stu-id="1b430-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="1b430-169">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-169">Format</span></span>

<span data-ttu-id="1b430-170">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="1b430-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-171">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-171">Pattern</span></span>

<span data-ttu-id="1b430-172">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1b430-173">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-173">Checksum</span></span>

<span data-ttu-id="1b430-174">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-175">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-175">Definition</span></span>

<span data-ttu-id="1b430-176">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-177">Регулярное выражение `Regex_bulgaria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-178">Найдено ключевое `Keywords_bulgaria_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="1b430-179">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-179">Keywords</span></span>

<span data-ttu-id="1b430-180">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-180">| |</span></span>
|<span data-ttu-id="1b430-181">**Keywords_bulgaria_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-182">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-182">dl#</span></span>  <br/> <span data-ttu-id="1b430-183">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-183">driver license</span></span>  <br/> <span data-ttu-id="1b430-184">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-184">driver license number</span></span>  <br/> <span data-ttu-id="1b430-185">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-185">driver licence</span></span>  <br/> <span data-ttu-id="1b430-186">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-186">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-187">drivers license</span></span>  <br/> <span data-ttu-id="1b430-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-188">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-189">driver's license</span></span>  <br/> <span data-ttu-id="1b430-190">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-190">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-191">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-191">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-192">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-192">driving license number</span></span>  <br/> <span data-ttu-id="1b430-193">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-193">dlno#</span></span>  <br/> <span data-ttu-id="1b430-194">свидетелство за управление на МПС</span><span class="sxs-lookup"><span data-stu-id="1b430-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="1b430-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="1b430-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="1b430-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="1b430-196">сумпс</span></span>  <br/> <span data-ttu-id="1b430-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="1b430-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="1b430-198">Хорватия</span><span class="sxs-lookup"><span data-stu-id="1b430-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="1b430-199">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-199">Format</span></span>

<span data-ttu-id="1b430-200">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="1b430-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-201">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-201">Pattern</span></span>

<span data-ttu-id="1b430-202">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1b430-203">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-203">Checksum</span></span>

<span data-ttu-id="1b430-204">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-205">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-205">Definition</span></span>

<span data-ttu-id="1b430-206">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-207">Регулярное выражение `Regex_croatia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-208">Найдено ключевое `Keywords_croatia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="1b430-209">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-209">Keywords</span></span>

<span data-ttu-id="1b430-210">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-210">| |</span></span>
|<span data-ttu-id="1b430-211">**Keywords_croatia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-212">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-212">dl#</span></span>  <br/> <span data-ttu-id="1b430-213">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-213">driver license</span></span>  <br/> <span data-ttu-id="1b430-214">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-214">driver license number</span></span>  <br/> <span data-ttu-id="1b430-215">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-215">driver licence</span></span>  <br/> <span data-ttu-id="1b430-216">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-216">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-217">drivers license</span></span>  <br/> <span data-ttu-id="1b430-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-218">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-219">driver's license</span></span>  <br/> <span data-ttu-id="1b430-220">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-220">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-221">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-221">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-222">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-222">driving license number</span></span>  <br/> <span data-ttu-id="1b430-223">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-223">dlno#</span></span>  <br/> <span data-ttu-id="1b430-224">возаčка дозвола</span><span class="sxs-lookup"><span data-stu-id="1b430-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="1b430-225">Кипр</span><span class="sxs-lookup"><span data-stu-id="1b430-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="1b430-226">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-226">Format</span></span>

<span data-ttu-id="1b430-227">12 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="1b430-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-228">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-228">Pattern</span></span>

<span data-ttu-id="1b430-229">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1b430-230">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-230">Checksum</span></span>

<span data-ttu-id="1b430-231">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-232">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-232">Definition</span></span>

<span data-ttu-id="1b430-233">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-234">Регулярное выражение `Regex_cyprus_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-235">Найдено ключевое `Keywords_cyprus_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-236">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-236">Keywords</span></span>

<span data-ttu-id="1b430-237">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-237">| |</span></span>
|<span data-ttu-id="1b430-238">**Keywords_cyprus_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-239">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-239">dl#</span></span>  <br/> <span data-ttu-id="1b430-240">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-240">driver license</span></span>  <br/> <span data-ttu-id="1b430-241">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-241">driver license number</span></span>  <br/> <span data-ttu-id="1b430-242">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-242">driver licence</span></span>  <br/> <span data-ttu-id="1b430-243">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-243">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-244">drivers license</span></span>  <br/> <span data-ttu-id="1b430-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-245">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-246">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-246">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-247">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-247">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-248">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-248">driving license number</span></span>  <br/> <span data-ttu-id="1b430-249">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-249">dlno#</span></span>  <br/> <span data-ttu-id="1b430-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="1b430-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="1b430-251">Чешская Республика</span><span class="sxs-lookup"><span data-stu-id="1b430-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="1b430-252">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-252">Format</span></span>

<span data-ttu-id="1b430-253">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-254">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-254">Pattern</span></span>

<span data-ttu-id="1b430-255">Восемь букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="1b430-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="1b430-256">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="1b430-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="1b430-257">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="1b430-257">A space (optional)</span></span>
    
- <span data-ttu-id="1b430-258">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1b430-259">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-259">Checksum</span></span>

<span data-ttu-id="1b430-260">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-261">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-261">Definition</span></span>

<span data-ttu-id="1b430-262">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-263">Регулярное выражение `Regex_czech_republic_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-264">Найдено ключевое `Keywords_czech_republic_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="1b430-265">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-265">Keywords</span></span>

<span data-ttu-id="1b430-266">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-266">| |</span></span>
|<span data-ttu-id="1b430-267">**Keywords_czech_republic_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-268">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-268">dl#</span></span>  <br/> <span data-ttu-id="1b430-269">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-269">driver license</span></span>  <br/> <span data-ttu-id="1b430-270">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-270">driver license number</span></span>  <br/> <span data-ttu-id="1b430-271">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-271">driver licence</span></span>  <br/> <span data-ttu-id="1b430-272">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-272">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-273">drivers license</span></span>  <br/> <span data-ttu-id="1b430-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-274">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-275">driver's license</span></span>  <br/> <span data-ttu-id="1b430-276">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-276">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-277">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-277">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-278">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-278">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-279">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-279">driving license number</span></span>  <br/> <span data-ttu-id="1b430-280">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-280">dlno#</span></span>  <br/> <span data-ttu-id="1b430-281">řидиčскý прúказ</span><span class="sxs-lookup"><span data-stu-id="1b430-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="1b430-282">Дания</span><span class="sxs-lookup"><span data-stu-id="1b430-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="1b430-283">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-283">Format</span></span>

<span data-ttu-id="1b430-284">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="1b430-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-285">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-285">Pattern</span></span>

<span data-ttu-id="1b430-286">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1b430-287">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-287">Checksum</span></span>

<span data-ttu-id="1b430-288">Да</span><span class="sxs-lookup"><span data-stu-id="1b430-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-289">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-289">Definition</span></span>

<span data-ttu-id="1b430-290">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-291">Регулярное выражение `Regex_denmark_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-292">Найдено ключевое `Keywords_denmark_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="1b430-293">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-293">Keywords</span></span>

<span data-ttu-id="1b430-294">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-294">| |</span></span>
|<span data-ttu-id="1b430-295">**Keywords_denmark_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-296">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-296">dl#</span></span>  <br/> <span data-ttu-id="1b430-297">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-297">driver license</span></span>  <br/> <span data-ttu-id="1b430-298">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-298">driver license number</span></span>  <br/> <span data-ttu-id="1b430-299">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-299">driver licence</span></span>  <br/> <span data-ttu-id="1b430-300">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-300">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-301">drivers license</span></span>  <br/> <span data-ttu-id="1b430-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-302">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-303">driver's license</span></span>  <br/> <span data-ttu-id="1b430-304">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-304">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-305">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-305">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-306">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-306">driving license number</span></span>  <br/> <span data-ttu-id="1b430-307">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-307">dlno#</span></span>  <br/> <span data-ttu-id="1b430-308">кøрекорт</span><span class="sxs-lookup"><span data-stu-id="1b430-308">kørekort</span></span>  <br/> <span data-ttu-id="1b430-309">кøрекортнуммер</span><span class="sxs-lookup"><span data-stu-id="1b430-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="1b430-310">Эстония</span><span class="sxs-lookup"><span data-stu-id="1b430-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="1b430-311">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-311">Format</span></span>

<span data-ttu-id="1b430-312">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-313">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-313">Pattern</span></span>

<span data-ttu-id="1b430-314">Две буквы и шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="1b430-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="1b430-315">Буквы "ET" (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="1b430-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="1b430-316">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1b430-317">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-317">Checksum</span></span>

<span data-ttu-id="1b430-318">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-319">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-319">Definition</span></span>

<span data-ttu-id="1b430-320">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-321">Регулярное выражение `Regex_estonia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-322">Найдено ключевое `Keywords_estonia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-323">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-323">Keywords</span></span>

<span data-ttu-id="1b430-324">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-324">| |</span></span>
|<span data-ttu-id="1b430-325">**Keywords_estonia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-326">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-326">dl#</span></span>  <br/> <span data-ttu-id="1b430-327">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-327">driver license</span></span>  <br/> <span data-ttu-id="1b430-328">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-328">driver license number</span></span>  <br/> <span data-ttu-id="1b430-329">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-329">driver license number</span></span>  <br/> <span data-ttu-id="1b430-330">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-330">driver licence</span></span>  <br/> <span data-ttu-id="1b430-331">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-331">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-332">drivers license</span></span>  <br/> <span data-ttu-id="1b430-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-333">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-334">driver's license</span></span>  <br/> <span data-ttu-id="1b430-335">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-335">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-336">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-336">driving license number</span></span>  <br/> <span data-ttu-id="1b430-337">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-337">dlno#</span></span>  <br/> <span data-ttu-id="1b430-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="1b430-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="1b430-339">Финляндия</span><span class="sxs-lookup"><span data-stu-id="1b430-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="1b430-340">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-340">Format</span></span>

<span data-ttu-id="1b430-341">10 цифр, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="1b430-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-342">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-342">Pattern</span></span>

<span data-ttu-id="1b430-343">10 цифр, содержащих дефис:</span><span class="sxs-lookup"><span data-stu-id="1b430-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="1b430-344">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="1b430-344">Six digits</span></span> 
    
- <span data-ttu-id="1b430-345">дефис;</span><span class="sxs-lookup"><span data-stu-id="1b430-345">A hyphen</span></span>
    
-  <span data-ttu-id="1b430-346">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="1b430-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1b430-347">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-347">Checksum</span></span>

<span data-ttu-id="1b430-348">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-349">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-349">Definition</span></span>

<span data-ttu-id="1b430-350">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-351">Регулярное выражение `Regex_finland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-352">Найдено ключевое `Keywords_finland_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-353">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-353">Keywords</span></span>

<span data-ttu-id="1b430-354">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-354">| |</span></span>
|<span data-ttu-id="1b430-355">**Keywords_finland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-356">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-356">dl#</span></span>  <br/> <span data-ttu-id="1b430-357">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-357">driver license</span></span>  <br/> <span data-ttu-id="1b430-358">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-358">driver license number</span></span>  <br/> <span data-ttu-id="1b430-359">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-359">driver licence</span></span>  <br/> <span data-ttu-id="1b430-360">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-360">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-361">drivers license</span></span>  <br/> <span data-ttu-id="1b430-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-362">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-363">driver's license</span></span>  <br/> <span data-ttu-id="1b430-364">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-364">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-365">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-365">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-366">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-366">driving license number</span></span>  <br/> <span data-ttu-id="1b430-367">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-367">dlno#</span></span>  <br/> <span data-ttu-id="1b430-368">ажокортти</span><span class="sxs-lookup"><span data-stu-id="1b430-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="1b430-369">Франция</span><span class="sxs-lookup"><span data-stu-id="1b430-369">France</span></span>

<span data-ttu-id="1b430-370">Дополнительные сведения см. в разделе "номер водительского удостоверения для Франции" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1b430-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="1b430-371">Германия</span><span class="sxs-lookup"><span data-stu-id="1b430-371">Germany</span></span>

<span data-ttu-id="1b430-372">Дополнительные сведения можно найти в разделе "номер водительского удостоверения для немецкого драйвера" [, который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1b430-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="1b430-373">Греция</span><span class="sxs-lookup"><span data-stu-id="1b430-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="1b430-374">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-374">Format</span></span>

<span data-ttu-id="1b430-375">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="1b430-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-376">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-376">Pattern</span></span>

 <span data-ttu-id="1b430-377">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1b430-378">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-378">Checksum</span></span>

<span data-ttu-id="1b430-379">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-380">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-380">Definition</span></span>

<span data-ttu-id="1b430-381">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-382">Регулярное выражение `Regex_greece_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-383">Найдено ключевое `Keywords_greece_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-384">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-384">Keywords</span></span>

<span data-ttu-id="1b430-385">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-385">| |</span></span>
|<span data-ttu-id="1b430-386">**Keywords_greece_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-387">Файл #</span><span class="sxs-lookup"><span data-stu-id="1b430-387">dlL#</span></span>  <br/> <span data-ttu-id="1b430-388">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-388">driver license</span></span>  <br/> <span data-ttu-id="1b430-389">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-389">driver license number</span></span>  <br/> <span data-ttu-id="1b430-390">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-390">driver licence</span></span>  <br/> <span data-ttu-id="1b430-391">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-391">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-392">drivers license</span></span>  <br/> <span data-ttu-id="1b430-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-393">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-394">driver's license</span></span>  <br/> <span data-ttu-id="1b430-395">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-395">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-396">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-396">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-397">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-397">driving license number</span></span>  <br/> <span data-ttu-id="1b430-398">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-398">dlno#</span></span>  <br/> <span data-ttu-id="1b430-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="1b430-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="1b430-400">Адеиа одигисис</span><span class="sxs-lookup"><span data-stu-id="1b430-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="1b430-401">Венгрия</span><span class="sxs-lookup"><span data-stu-id="1b430-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="1b430-402">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-402">Format</span></span>

<span data-ttu-id="1b430-403">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-404">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-404">Pattern</span></span>

<span data-ttu-id="1b430-405">Две буквы и шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="1b430-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="1b430-406">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="1b430-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="1b430-407">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1b430-408">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-408">Checksum</span></span>

<span data-ttu-id="1b430-409">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-410">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-410">Definition</span></span>

<span data-ttu-id="1b430-411">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-412">Регулярное выражение `Regex_hungary_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-413">Найдено ключевое `Keywords_hungary_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-414">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-414">Keywords</span></span>

<span data-ttu-id="1b430-415">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-415">| |</span></span>
|<span data-ttu-id="1b430-416">**Keywords_hungary_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-417">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-417">dl#</span></span>  <br/> <span data-ttu-id="1b430-418">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-418">driver license</span></span>  <br/> <span data-ttu-id="1b430-419">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-419">driver license number</span></span>  <br/> <span data-ttu-id="1b430-420">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-420">driver licence</span></span>  <br/> <span data-ttu-id="1b430-421">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-421">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-422">drivers license</span></span>  <br/> <span data-ttu-id="1b430-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-423">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-424">driver's license</span></span>  <br/> <span data-ttu-id="1b430-425">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-425">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-426">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-426">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-427">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-427">driving license number</span></span>  <br/> <span data-ttu-id="1b430-428">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-428">dlno#</span></span>  <br/> <span data-ttu-id="1b430-429">везетои енжедели</span><span class="sxs-lookup"><span data-stu-id="1b430-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="1b430-430">Ireland (Ирландия)</span><span class="sxs-lookup"><span data-stu-id="1b430-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="1b430-431">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-431">Format</span></span>

<span data-ttu-id="1b430-432">Шесть цифр, за которыми следуют четыре буквы</span><span class="sxs-lookup"><span data-stu-id="1b430-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-433">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-433">Pattern</span></span>

<span data-ttu-id="1b430-434">Шесть цифр и четыре буквы:</span><span class="sxs-lookup"><span data-stu-id="1b430-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="1b430-435">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="1b430-435">Six digits</span></span>
    
- <span data-ttu-id="1b430-436">Четыре буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="1b430-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1b430-437">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-437">Checksum</span></span>

<span data-ttu-id="1b430-438">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-439">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-439">Definition</span></span>

<span data-ttu-id="1b430-440">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-441">Регулярное выражение `Regex_ireland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-442">Найдено ключевое `Keywords_ireland_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-443">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-443">Keywords</span></span>

<span data-ttu-id="1b430-444">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-444">| |</span></span>
|<span data-ttu-id="1b430-445">**Keywords_ireland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-446">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-446">dl#</span></span>  <br/> <span data-ttu-id="1b430-447">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-447">driver license</span></span>  <br/> <span data-ttu-id="1b430-448">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-448">driver license number</span></span>  <br/> <span data-ttu-id="1b430-449">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-449">driver licence</span></span>  <br/> <span data-ttu-id="1b430-450">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-450">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-451">drivers license</span></span>  <br/> <span data-ttu-id="1b430-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-452">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-453">driver's license</span></span>  <br/> <span data-ttu-id="1b430-454">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-454">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-455">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-455">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-456">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-456">driving license number</span></span>  <br/> <span data-ttu-id="1b430-457">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-457">dlno#</span></span>  <br/> <span data-ttu-id="1b430-458">цеадúнас тиомáна</span><span class="sxs-lookup"><span data-stu-id="1b430-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="1b430-459">Италия</span><span class="sxs-lookup"><span data-stu-id="1b430-459">Italy</span></span>

<span data-ttu-id="1b430-460">Дополнительные сведения см. в разделе "номер водительского удостоверения для Италии" [, который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1b430-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="1b430-461">Латвия</span><span class="sxs-lookup"><span data-stu-id="1b430-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="1b430-462">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-462">Format</span></span>

<span data-ttu-id="1b430-463">Три буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-464">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-464">Pattern</span></span>

<span data-ttu-id="1b430-465">Три буквы и шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="1b430-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="1b430-466">Три буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="1b430-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="1b430-467">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1b430-468">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-468">Checksum</span></span>

<span data-ttu-id="1b430-469">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-470">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-470">Definition</span></span>

<span data-ttu-id="1b430-471">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-472">Регулярное выражение `Regex_latvia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-473">Найдено ключевое `Keywords_latvia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-474">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-474">Keywords</span></span>

<span data-ttu-id="1b430-475">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-475">| |</span></span>
|<span data-ttu-id="1b430-476">**Keywords_latvia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-477">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-477">dl#</span></span>  <br/> <span data-ttu-id="1b430-478">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-478">driver license</span></span>  <br/> <span data-ttu-id="1b430-479">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-479">driver license number</span></span>  <br/> <span data-ttu-id="1b430-480">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-480">driver licence</span></span>  <br/> <span data-ttu-id="1b430-481">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-481">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-482">drivers license</span></span>  <br/> <span data-ttu-id="1b430-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-483">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-484">driver's license</span></span>  <br/> <span data-ttu-id="1b430-485">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-485">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-486">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-486">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-487">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-487">driving license number</span></span>  <br/> <span data-ttu-id="1b430-488">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-488">dlno#</span></span>  <br/> <span data-ttu-id="1b430-489">аутовадīтāжа аплиекīба</span><span class="sxs-lookup"><span data-stu-id="1b430-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="1b430-490">Литва</span><span class="sxs-lookup"><span data-stu-id="1b430-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="1b430-491">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-491">Format</span></span>

<span data-ttu-id="1b430-492">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="1b430-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-493">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-493">Pattern</span></span>

 <span data-ttu-id="1b430-494">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1b430-495">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-495">Checksum</span></span>

<span data-ttu-id="1b430-496">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-497">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-497">Definition</span></span>

<span data-ttu-id="1b430-498">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-499">Регулярное выражение `Regex_lithuania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-500">Найдено ключевое `Keywords_lithuania_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-501">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-501">Keywords</span></span>

<span data-ttu-id="1b430-502">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-502">| |</span></span>
|<span data-ttu-id="1b430-503">**Keywords_lithuania_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-504">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-504">dl#</span></span>  <br/> <span data-ttu-id="1b430-505">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-505">driver license</span></span>  <br/> <span data-ttu-id="1b430-506">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-506">driver license number</span></span>  <br/> <span data-ttu-id="1b430-507">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-507">driver licence</span></span>  <br/> <span data-ttu-id="1b430-508">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-508">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-509">drivers license</span></span>  <br/> <span data-ttu-id="1b430-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-510">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-511">driver's license</span></span>  <br/> <span data-ttu-id="1b430-512">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-512">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-513">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-513">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-514">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-514">driving license number</span></span>  <br/> <span data-ttu-id="1b430-515">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-515">dlno#</span></span>  <br/> <span data-ttu-id="1b430-516">ваируотожо паžимėжимас</span><span class="sxs-lookup"><span data-stu-id="1b430-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="1b430-517">луксембург</span><span class="sxs-lookup"><span data-stu-id="1b430-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="1b430-518">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-518">Format</span></span>

<span data-ttu-id="1b430-519">Шесть цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="1b430-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-520">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-520">Pattern</span></span>

 <span data-ttu-id="1b430-521">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1b430-522">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-522">Checksum</span></span>

<span data-ttu-id="1b430-523">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-524">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-524">Definition</span></span>

<span data-ttu-id="1b430-525">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-526">Регулярное выражение `Regex_luxemburg_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-527">Найдено ключевое `Keywords_luxemburg_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-528">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-528">Keywords</span></span>

<span data-ttu-id="1b430-529">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-529">| |</span></span>
|<span data-ttu-id="1b430-530">**Keywords_luxemburg_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-531">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-531">dl#</span></span>  <br/> <span data-ttu-id="1b430-532">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-532">driver license</span></span>  <br/> <span data-ttu-id="1b430-533">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-533">driver license number</span></span>  <br/> <span data-ttu-id="1b430-534">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-534">driver licence</span></span>  <br/> <span data-ttu-id="1b430-535">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-535">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-536">drivers license</span></span>  <br/> <span data-ttu-id="1b430-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-537">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-538">driver's license</span></span>  <br/> <span data-ttu-id="1b430-539">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-539">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-540">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-540">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-541">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-541">driving license number</span></span>  <br/> <span data-ttu-id="1b430-542">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-542">dlno#</span></span>  <br/> <span data-ttu-id="1b430-543">фахрерлаубнис</span><span class="sxs-lookup"><span data-stu-id="1b430-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="1b430-544">Мальта</span><span class="sxs-lookup"><span data-stu-id="1b430-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="1b430-545">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-545">Format</span></span>

<span data-ttu-id="1b430-546">Сочетание двух символов и шести цифр в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="1b430-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-547">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-547">Pattern</span></span>

<span data-ttu-id="1b430-548">Сочетание двух символов и шести цифр:</span><span class="sxs-lookup"><span data-stu-id="1b430-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="1b430-549">Два символа (цифры или буквы без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="1b430-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="1b430-550">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="1b430-550">A space (optional)</span></span>
    
- <span data-ttu-id="1b430-551">три цифры; </span><span class="sxs-lookup"><span data-stu-id="1b430-551">Three digits</span></span>
    
- <span data-ttu-id="1b430-552">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="1b430-552">A space (optional)</span></span>
    
- <span data-ttu-id="1b430-553">Три цифры</span><span class="sxs-lookup"><span data-stu-id="1b430-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1b430-554">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-554">Checksum</span></span>

<span data-ttu-id="1b430-555">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-556">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-556">Definition</span></span>

<span data-ttu-id="1b430-557">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-558">Регулярное выражение `Regex_malta_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-559">Найдено ключевое `Keywords_malta_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-560">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-560">Keywords</span></span>

<span data-ttu-id="1b430-561">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-561">| |</span></span>
|<span data-ttu-id="1b430-562">**Keywords_malta_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-563">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-563">dl#</span></span>  <br/> <span data-ttu-id="1b430-564">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-564">driver license</span></span>  <br/> <span data-ttu-id="1b430-565">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-565">driver license number</span></span>  <br/> <span data-ttu-id="1b430-566">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-566">driver licence</span></span>  <br/> <span data-ttu-id="1b430-567">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-567">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-568">drivers license</span></span>  <br/> <span data-ttu-id="1b430-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-569">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-570">driver's license</span></span>  <br/> <span data-ttu-id="1b430-571">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-571">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-572">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-572">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-573">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-573">driving license number</span></span>  <br/> <span data-ttu-id="1b430-574">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-574">dlno#</span></span>  <br/> <span data-ttu-id="1b430-575">лиċензжаные зада Севкан</span><span class="sxs-lookup"><span data-stu-id="1b430-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="1b430-576">Нидерланды</span><span class="sxs-lookup"><span data-stu-id="1b430-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="1b430-577">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-577">Format</span></span>

<span data-ttu-id="1b430-578">10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="1b430-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-579">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-579">Pattern</span></span>

<span data-ttu-id="1b430-580">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1b430-581">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-581">Checksum</span></span>

<span data-ttu-id="1b430-582">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-583">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-583">Definition</span></span>

<span data-ttu-id="1b430-584">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-585">Регулярное выражение `Regex_netherlands_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-586">Найдено ключевое `Keywords_netherlands_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-587">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-587">Keywords</span></span>

<span data-ttu-id="1b430-588">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-588">| |</span></span>
|<span data-ttu-id="1b430-589">**Keywords_netherlands_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-590">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-590">dl#</span></span>  <br/> <span data-ttu-id="1b430-591">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-591">driver license</span></span>  <br/> <span data-ttu-id="1b430-592">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-592">driver license number</span></span>  <br/> <span data-ttu-id="1b430-593">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-593">driver licence</span></span>  <br/> <span data-ttu-id="1b430-594">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-594">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-595">drivers license</span></span>  <br/> <span data-ttu-id="1b430-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-596">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-597">driver's license</span></span>  <br/> <span data-ttu-id="1b430-598">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-598">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-599">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-599">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-600">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-600">driving license number</span></span>  <br/> <span data-ttu-id="1b430-601">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-601">dlno#</span></span>  <br/> <span data-ttu-id="1b430-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="1b430-602">permis de conduire</span></span>  <br/> <span data-ttu-id="1b430-603">рижбевижс</span><span class="sxs-lookup"><span data-stu-id="1b430-603">rijbewijs</span></span>  <br/> <span data-ttu-id="1b430-604">рижбевижснуммер</span><span class="sxs-lookup"><span data-stu-id="1b430-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="1b430-605">Польша</span><span class="sxs-lookup"><span data-stu-id="1b430-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="1b430-606">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-606">Format</span></span>

<span data-ttu-id="1b430-607">14 цифр, содержащих 2 косых черты.</span><span class="sxs-lookup"><span data-stu-id="1b430-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-608">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-608">Pattern</span></span>

<span data-ttu-id="1b430-609">14 цифр и 2 косых черт:</span><span class="sxs-lookup"><span data-stu-id="1b430-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="1b430-610">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="1b430-610">Five digits</span></span> 
    
- <span data-ttu-id="1b430-611">косая черта;</span><span class="sxs-lookup"><span data-stu-id="1b430-611">A forward slash</span></span>
    
- <span data-ttu-id="1b430-612">Две цифры</span><span class="sxs-lookup"><span data-stu-id="1b430-612">Two digits</span></span>
    
- <span data-ttu-id="1b430-613">косая черта;</span><span class="sxs-lookup"><span data-stu-id="1b430-613">A forward slash</span></span>
    
- <span data-ttu-id="1b430-614">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1b430-615">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-615">Checksum</span></span>

<span data-ttu-id="1b430-616">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-617">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-617">Definition</span></span>

<span data-ttu-id="1b430-618">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-619">Регулярное выражение `Regex_poland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-620">Найдено ключевое `Keywords_poland_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-621">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-621">Keywords</span></span>

<span data-ttu-id="1b430-622">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-622">| |</span></span>
|<span data-ttu-id="1b430-623">**Keywords_poland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-624">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-624">dl#</span></span>  <br/> <span data-ttu-id="1b430-625">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-625">driver license</span></span>  <br/> <span data-ttu-id="1b430-626">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-626">driver license number</span></span>  <br/> <span data-ttu-id="1b430-627">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-627">driver licence</span></span>  <br/> <span data-ttu-id="1b430-628">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-628">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-629">drivers license</span></span>  <br/> <span data-ttu-id="1b430-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-630">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-631">driver's license</span></span>  <br/> <span data-ttu-id="1b430-632">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-632">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-633">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-633">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-634">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-634">driving license number</span></span>  <br/> <span data-ttu-id="1b430-635">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-635">dlno#</span></span>  <br/> <span data-ttu-id="1b430-636">право жазди</span><span class="sxs-lookup"><span data-stu-id="1b430-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="1b430-637">Португалия</span><span class="sxs-lookup"><span data-stu-id="1b430-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="1b430-638">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-638">Format</span></span>

<span data-ttu-id="1b430-639">Две буквы, за которыми следуют семь чисел в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="1b430-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-640">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-640">Pattern</span></span>

<span data-ttu-id="1b430-641">Две буквы, за которыми следуют семь цифр со специальными символами:</span><span class="sxs-lookup"><span data-stu-id="1b430-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="1b430-642">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="1b430-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="1b430-643">дефис;</span><span class="sxs-lookup"><span data-stu-id="1b430-643">A hyphen</span></span>
    
- <span data-ttu-id="1b430-644">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="1b430-644">Six digits</span></span>
    
- <span data-ttu-id="1b430-645">Пробел</span><span class="sxs-lookup"><span data-stu-id="1b430-645">A space</span></span>
    
- <span data-ttu-id="1b430-646">одна цифра.</span><span class="sxs-lookup"><span data-stu-id="1b430-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1b430-647">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-647">Checksum</span></span>

<span data-ttu-id="1b430-648">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-649">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-649">Definition</span></span>

<span data-ttu-id="1b430-650">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-651">Регулярное выражение `Regex_portugal_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-652">Найдено ключевое `Keywords_portugal_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-653">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-653">Keywords</span></span>

<span data-ttu-id="1b430-654">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-654">| |</span></span>
|<span data-ttu-id="1b430-655">**Keywords_portugal_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-656">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-656">dl#</span></span>  <br/> <span data-ttu-id="1b430-657">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-657">driver license</span></span>  <br/> <span data-ttu-id="1b430-658">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-658">driver license number</span></span>  <br/> <span data-ttu-id="1b430-659">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-659">driver licence</span></span>  <br/> <span data-ttu-id="1b430-660">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-660">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-661">drivers license</span></span>  <br/> <span data-ttu-id="1b430-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-662">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-663">driver's license</span></span>  <br/> <span data-ttu-id="1b430-664">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-664">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-665">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-665">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-666">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-666">driving license number</span></span>  <br/> <span data-ttu-id="1b430-667">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-667">dlno#</span></span>  <br/> <span data-ttu-id="1b430-668">картеира de моториста</span><span class="sxs-lookup"><span data-stu-id="1b430-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="1b430-669">Румыния</span><span class="sxs-lookup"><span data-stu-id="1b430-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="1b430-670">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-670">Format</span></span>

<span data-ttu-id="1b430-671">Один символ, за которым следуют восемь цифр</span><span class="sxs-lookup"><span data-stu-id="1b430-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-672">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-672">Pattern</span></span>

<span data-ttu-id="1b430-673">Один символ, за которым следуют восемь цифр:</span><span class="sxs-lookup"><span data-stu-id="1b430-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="1b430-674">Одна буква (без учета регистра) или цифра</span><span class="sxs-lookup"><span data-stu-id="1b430-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="1b430-675">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1b430-676">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-676">Checksum</span></span>

<span data-ttu-id="1b430-677">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-678">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-678">Definition</span></span>

<span data-ttu-id="1b430-679">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-680">Регулярное выражение `Regex_romania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-681">Найдено ключевое `Keywords_romania_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-682">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-682">Keywords</span></span>

<span data-ttu-id="1b430-683">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-683">| |</span></span>
|<span data-ttu-id="1b430-684">**Keywords_romania_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-685">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-685">dl#</span></span>  <br/> <span data-ttu-id="1b430-686">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-686">driver license</span></span>  <br/> <span data-ttu-id="1b430-687">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-687">driver license number</span></span>  <br/> <span data-ttu-id="1b430-688">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-688">driver licence</span></span>  <br/> <span data-ttu-id="1b430-689">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-689">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-690">drivers license</span></span>  <br/> <span data-ttu-id="1b430-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-691">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-692">driver's license</span></span>  <br/> <span data-ttu-id="1b430-693">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-693">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-694">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-694">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-695">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-695">driving license number</span></span>  <br/> <span data-ttu-id="1b430-696">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-696">dlno#</span></span>  <br/> <span data-ttu-id="1b430-697">разрешение de кондуцере</span><span class="sxs-lookup"><span data-stu-id="1b430-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="1b430-698">Словакия</span><span class="sxs-lookup"><span data-stu-id="1b430-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="1b430-699">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-699">Format</span></span>

<span data-ttu-id="1b430-700">Один символ, за которым следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-701">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-701">Pattern</span></span>

<span data-ttu-id="1b430-702">Один символ, за которым следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="1b430-703">Одна буква (без учета регистра) или цифра</span><span class="sxs-lookup"><span data-stu-id="1b430-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="1b430-704">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="1b430-705">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-705">Checksum</span></span>

<span data-ttu-id="1b430-706">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-707">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-707">Definition</span></span>

<span data-ttu-id="1b430-708">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-709">Регулярное выражение `Regex_slovakia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-710">Найдено ключевое `Keywords_slovakia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-711">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-711">Keywords</span></span>

<span data-ttu-id="1b430-712">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-712">| |</span></span>
|<span data-ttu-id="1b430-713">**Keywords_slovakia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-714">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-714">dl#</span></span>  <br/> <span data-ttu-id="1b430-715">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-715">driver license</span></span>  <br/> <span data-ttu-id="1b430-716">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-716">driver license number</span></span>  <br/> <span data-ttu-id="1b430-717">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-717">driver licence</span></span>  <br/> <span data-ttu-id="1b430-718">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-718">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-719">drivers license</span></span>  <br/> <span data-ttu-id="1b430-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-720">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-721">driver's license</span></span>  <br/> <span data-ttu-id="1b430-722">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-722">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-723">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-723">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-724">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-724">driving license number</span></span>  <br/> <span data-ttu-id="1b430-725">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-725">dlno#</span></span>  <br/> <span data-ttu-id="1b430-726">водиčскý преуказ</span><span class="sxs-lookup"><span data-stu-id="1b430-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="1b430-727">Словения</span><span class="sxs-lookup"><span data-stu-id="1b430-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="1b430-728">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-728">Format</span></span>

<span data-ttu-id="1b430-729">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="1b430-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-730">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-730">Pattern</span></span>

<span data-ttu-id="1b430-731">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1b430-732">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-732">Checksum</span></span>

<span data-ttu-id="1b430-733">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-734">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-734">Definition</span></span>

<span data-ttu-id="1b430-735">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-736">Регулярное выражение `Regex_slovenia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-737">Найдено ключевое `Keywords_slovenia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-738">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-738">Keywords</span></span>

<span data-ttu-id="1b430-739">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-739">| |</span></span>
|<span data-ttu-id="1b430-740">**Keywords_slovenia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-741">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-741">dl#</span></span>  <br/> <span data-ttu-id="1b430-742">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-742">driver license</span></span>  <br/> <span data-ttu-id="1b430-743">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-743">driver license number</span></span>  <br/> <span data-ttu-id="1b430-744">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-744">driver licence</span></span>  <br/> <span data-ttu-id="1b430-745">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-745">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-746">drivers license</span></span>  <br/> <span data-ttu-id="1b430-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-747">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-748">driver's license</span></span>  <br/> <span data-ttu-id="1b430-749">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-749">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-750">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-750">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-751">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-751">driving license number</span></span>  <br/> <span data-ttu-id="1b430-752">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-752">dlno#</span></span>  <br/> <span data-ttu-id="1b430-753">возниšко доволженже</span><span class="sxs-lookup"><span data-stu-id="1b430-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="1b430-754">Испания</span><span class="sxs-lookup"><span data-stu-id="1b430-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="1b430-755">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-755">Format</span></span>

<span data-ttu-id="1b430-756">Восемь цифр, за которыми следует один символ</span><span class="sxs-lookup"><span data-stu-id="1b430-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-757">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-757">Pattern</span></span>

<span data-ttu-id="1b430-758">Восемь цифр, за которыми следует один символ:</span><span class="sxs-lookup"><span data-stu-id="1b430-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="1b430-759">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="1b430-759">Eight digits</span></span> 
    
- <span data-ttu-id="1b430-760">Одна цифра или буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="1b430-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1b430-761">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-761">Checksum</span></span>

<span data-ttu-id="1b430-762">Да</span><span class="sxs-lookup"><span data-stu-id="1b430-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-763">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-763">Definition</span></span>

<span data-ttu-id="1b430-764">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-765">Функция `Func_spain_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-766">Найдено ключевое `Keywords_spain_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1b430-767">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-767">Keywords</span></span>

<span data-ttu-id="1b430-768">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-768">| |</span></span>
|<span data-ttu-id="1b430-769">**Keywords_spain_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-770">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-770">dlno#</span></span>  <br/> <span data-ttu-id="1b430-771">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-771">dl#</span></span>  <br/> <span data-ttu-id="1b430-772">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-772">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-773">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-773">driver licence</span></span>  <br/> <span data-ttu-id="1b430-774">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-774">driver license</span></span>  <br/> <span data-ttu-id="1b430-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-775">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-776">drivers license</span></span>  <br/> <span data-ttu-id="1b430-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="1b430-777">driver's licence</span></span>  <br/> <span data-ttu-id="1b430-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-778">driver's license</span></span>  <br/> <span data-ttu-id="1b430-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="1b430-779">driving licence</span></span>  <br/> <span data-ttu-id="1b430-780">driving license</span><span class="sxs-lookup"><span data-stu-id="1b430-780">driving license</span></span>  <br/> <span data-ttu-id="1b430-781">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-781">driver licence number</span></span>  <br/> <span data-ttu-id="1b430-782">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-782">driver license number</span></span>  <br/> <span data-ttu-id="1b430-783">драйвер номер лицензии</span><span class="sxs-lookup"><span data-stu-id="1b430-783">drivers licence number</span></span>  <br/> <span data-ttu-id="1b430-784">номер лицензии на драйверы</span><span class="sxs-lookup"><span data-stu-id="1b430-784">drivers license number</span></span>  <br/> <span data-ttu-id="1b430-785">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-785">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-786">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-786">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-787">номер водительской лицензии</span><span class="sxs-lookup"><span data-stu-id="1b430-787">driving licence number</span></span>  <br/> <span data-ttu-id="1b430-788">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-788">driving license number</span></span>  <br/> <span data-ttu-id="1b430-789">движущие разрешение</span><span class="sxs-lookup"><span data-stu-id="1b430-789">driving permit</span></span>  <br/> <span data-ttu-id="1b430-790">движущие число разрешений</span><span class="sxs-lookup"><span data-stu-id="1b430-790">driving permit number</span></span>  <br/> <span data-ttu-id="1b430-791">пермисо de кондукЦиóн</span><span class="sxs-lookup"><span data-stu-id="1b430-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="1b430-792">пермисо кондукЦиóн</span><span class="sxs-lookup"><span data-stu-id="1b430-792">permiso conducción</span></span>  <br/> <span data-ttu-id="1b430-793">нúмеро лиценЦиа кондуЦир</span><span class="sxs-lookup"><span data-stu-id="1b430-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="1b430-794">нúмеро de карнет де кондуЦир</span><span class="sxs-lookup"><span data-stu-id="1b430-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="1b430-795">нúмеро карнет кондуЦир</span><span class="sxs-lookup"><span data-stu-id="1b430-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="1b430-796">лиценЦиа кондуЦир</span><span class="sxs-lookup"><span data-stu-id="1b430-796">licencia conducir</span></span>  <br/> <span data-ttu-id="1b430-797">нúмеро de пермисо де кондуЦир</span><span class="sxs-lookup"><span data-stu-id="1b430-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="1b430-798">нúмеро де пермисо кондуЦир</span><span class="sxs-lookup"><span data-stu-id="1b430-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="1b430-799">нúмеро пермисо кондуЦир</span><span class="sxs-lookup"><span data-stu-id="1b430-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="1b430-800">пермисо кондуЦир</span><span class="sxs-lookup"><span data-stu-id="1b430-800">permiso conducir</span></span>  <br/> <span data-ttu-id="1b430-801">лиценЦиа de манежо</span><span class="sxs-lookup"><span data-stu-id="1b430-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="1b430-802">El карнет de кондуЦир</span><span class="sxs-lookup"><span data-stu-id="1b430-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="1b430-803">Карнет кондуЦир</span><span class="sxs-lookup"><span data-stu-id="1b430-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="1b430-804">Швеция</span><span class="sxs-lookup"><span data-stu-id="1b430-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="1b430-805">Format</span><span class="sxs-lookup"><span data-stu-id="1b430-805">Format</span></span>

<span data-ttu-id="1b430-806">Десять цифр, содержащие дефис</span><span class="sxs-lookup"><span data-stu-id="1b430-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1b430-807">Шаблон</span><span class="sxs-lookup"><span data-stu-id="1b430-807">Pattern</span></span>

<span data-ttu-id="1b430-808">Десять цифр, содержащих дефис:</span><span class="sxs-lookup"><span data-stu-id="1b430-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="1b430-809">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="1b430-809">Six digits</span></span> 
    
- <span data-ttu-id="1b430-810">дефис;</span><span class="sxs-lookup"><span data-stu-id="1b430-810">A hyphen</span></span>
    
- <span data-ttu-id="1b430-811">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="1b430-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1b430-812">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="1b430-812">Checksum</span></span>

<span data-ttu-id="1b430-813">Нет</span><span class="sxs-lookup"><span data-stu-id="1b430-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1b430-814">Определение</span><span class="sxs-lookup"><span data-stu-id="1b430-814">Definition</span></span>

<span data-ttu-id="1b430-815">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="1b430-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1b430-816">Регулярное выражение `Regex_sweden_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="1b430-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1b430-817">Найдено ключевое `Keywords_sweden_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="1b430-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="1b430-818">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1b430-818">Keywords</span></span>

<span data-ttu-id="1b430-819">| |</span><span class="sxs-lookup"><span data-stu-id="1b430-819">| |</span></span>
|<span data-ttu-id="1b430-820">**Keywords_sweden_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="1b430-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="1b430-821">DL #</span><span class="sxs-lookup"><span data-stu-id="1b430-821">dl#</span></span>  <br/> <span data-ttu-id="1b430-822">driver license</span><span class="sxs-lookup"><span data-stu-id="1b430-822">driver license</span></span>  <br/> <span data-ttu-id="1b430-823">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-823">driver license number</span></span>  <br/> <span data-ttu-id="1b430-824">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-824">driver licence</span></span>  <br/> <span data-ttu-id="1b430-825">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="1b430-825">drivers lic.</span></span>  <br/> <span data-ttu-id="1b430-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="1b430-826">drivers license</span></span>  <br/> <span data-ttu-id="1b430-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="1b430-827">drivers licence</span></span>  <br/> <span data-ttu-id="1b430-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="1b430-828">driver's license</span></span>  <br/> <span data-ttu-id="1b430-829">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-829">driver's license number</span></span>  <br/> <span data-ttu-id="1b430-830">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="1b430-830">driver's licence number</span></span>  <br/> <span data-ttu-id="1b430-831">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="1b430-831">driving license number</span></span>  <br/> <span data-ttu-id="1b430-832">длно #</span><span class="sxs-lookup"><span data-stu-id="1b430-832">dlno#</span></span>  <br/> <span data-ttu-id="1b430-833">кöркорт</span><span class="sxs-lookup"><span data-stu-id="1b430-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="1b430-834">ВОЗМЕЩЕН</span><span class="sxs-lookup"><span data-stu-id="1b430-834">UK</span></span>

<span data-ttu-id="1b430-835">Дополнительные сведения см. в разделе "Великобритания</span><span class="sxs-lookup"><span data-stu-id="1b430-835">For details, see the section "U.K.</span></span> <span data-ttu-id="1b430-836">Номер водительского удостоверения, в [котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1b430-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1b430-837">См. также</span><span class="sxs-lookup"><span data-stu-id="1b430-837">See also</span></span>

[<span data-ttu-id="1b430-838">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="1b430-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

