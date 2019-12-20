---
title: Номер водительского удостоверения для драйвера ЕС
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
ms.openlocfilehash: 6df025caf8d06c617e09a3b53dc6c82d69aaf5a8
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805962"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="8f174-104">Номер водительского удостоверения для драйвера ЕС</span><span class="sxs-lookup"><span data-stu-id="8f174-104">EU Driver's License Number</span></span>

<span data-ttu-id="8f174-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации номера лицензии для драйвера ЕС.</span><span class="sxs-lookup"><span data-stu-id="8f174-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="8f174-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="8f174-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="8f174-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="8f174-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="8f174-108">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-108">Format</span></span>

<span data-ttu-id="8f174-109">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="8f174-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-110">Pattern</span></span>

<span data-ttu-id="8f174-111">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f174-112">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-112">Checksum</span></span>

<span data-ttu-id="8f174-113">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-114">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-114">Definition</span></span>

<span data-ttu-id="8f174-115">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-116">Регулярное выражение `Regex_austria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-117">Найдено ключевое `Keywords_austria_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="8f174-118">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-118">Keywords</span></span>

<span data-ttu-id="8f174-119">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-119"></span></span>
|<span data-ttu-id="8f174-120">**Keywords_austria_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-121">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-121">dl#</span></span>  <br/> <span data-ttu-id="8f174-122">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-122">driver license</span></span>  <br/> <span data-ttu-id="8f174-123">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-123">driver license number</span></span>  <br/> <span data-ttu-id="8f174-124">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-124">driver licence</span></span>  <br/> <span data-ttu-id="8f174-125">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-125">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-126">drivers license</span></span>  <br/> <span data-ttu-id="8f174-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="8f174-127">driver's licence</span></span>  <br/> <span data-ttu-id="8f174-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-128">driver's license</span></span>  <br/> <span data-ttu-id="8f174-129">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-129">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-130">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="8f174-131">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-131">driving license number</span></span>  <br/> <span data-ttu-id="8f174-132">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-132">dlno#</span></span>  <br/> <span data-ttu-id="8f174-133">фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="8f174-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="8f174-134">фухрерсчеин Републик остерреич</span><span class="sxs-lookup"><span data-stu-id="8f174-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="8f174-135">Бельгия</span><span class="sxs-lookup"><span data-stu-id="8f174-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="8f174-136">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-136">Format</span></span>

<span data-ttu-id="8f174-137">10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="8f174-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-138">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-138">Pattern</span></span>

<span data-ttu-id="8f174-139">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f174-140">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-140">Checksum</span></span>

<span data-ttu-id="8f174-141">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-142">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-142">Definition</span></span>

<span data-ttu-id="8f174-143">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-144">Регулярное выражение `Regex_belgium_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-145">Найдено ключевое `Keywords_belgium_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="8f174-146">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-146">Keywords</span></span>

<span data-ttu-id="8f174-147">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-147"></span></span>
|<span data-ttu-id="8f174-148">**Keywords__belgium_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-149">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-149">dl#</span></span>  <br/> <span data-ttu-id="8f174-150">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-150">driver license</span></span>  <br/> <span data-ttu-id="8f174-151">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-151">driver license number</span></span>  <br/> <span data-ttu-id="8f174-152">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-152">driver licence</span></span>  <br/> <span data-ttu-id="8f174-153">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-153">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-154">drivers license</span></span>  <br/> <span data-ttu-id="8f174-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-155">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-156">driver's license</span></span>  <br/> <span data-ttu-id="8f174-157">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-157">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-158">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-158">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-159">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-159">dlno#</span></span>  <br/> <span data-ttu-id="8f174-160">рижбевижс</span><span class="sxs-lookup"><span data-stu-id="8f174-160">rijbewijs</span></span>  <br/> <span data-ttu-id="8f174-161">рижбевижснуммер</span><span class="sxs-lookup"><span data-stu-id="8f174-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="8f174-162">фüхрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="8f174-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="8f174-163">фухрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="8f174-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="8f174-164">фуехрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="8f174-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="8f174-165">фüхрерсчеин — НР</span><span class="sxs-lookup"><span data-stu-id="8f174-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="8f174-166">фуехрерсчеин — НР</span><span class="sxs-lookup"><span data-stu-id="8f174-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="8f174-167">фуехрерсчеин — НР</span><span class="sxs-lookup"><span data-stu-id="8f174-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="8f174-168">Болгария</span><span class="sxs-lookup"><span data-stu-id="8f174-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="8f174-169">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-169">Format</span></span>

<span data-ttu-id="8f174-170">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="8f174-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-171">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-171">Pattern</span></span>

<span data-ttu-id="8f174-172">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f174-173">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-173">Checksum</span></span>

<span data-ttu-id="8f174-174">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-175">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-175">Definition</span></span>

<span data-ttu-id="8f174-176">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-177">Регулярное выражение `Regex_bulgaria_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-178">Найдено ключевое `Keywords_bulgaria_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="8f174-179">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-179">Keywords</span></span>

<span data-ttu-id="8f174-180">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-180"></span></span>
|<span data-ttu-id="8f174-181">**Keywords_bulgaria_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-182">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-182">dl#</span></span>  <br/> <span data-ttu-id="8f174-183">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-183">driver license</span></span>  <br/> <span data-ttu-id="8f174-184">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-184">driver license number</span></span>  <br/> <span data-ttu-id="8f174-185">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-185">driver licence</span></span>  <br/> <span data-ttu-id="8f174-186">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-186">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-187">drivers license</span></span>  <br/> <span data-ttu-id="8f174-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-188">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-189">driver's license</span></span>  <br/> <span data-ttu-id="8f174-190">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-190">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-191">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-191">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-192">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-192">driving license number</span></span>  <br/> <span data-ttu-id="8f174-193">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-193">dlno#</span></span>  <br/> <span data-ttu-id="8f174-194">свидетелство за управление на МПС</span><span class="sxs-lookup"><span data-stu-id="8f174-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="8f174-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="8f174-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="8f174-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="8f174-196">сумпс</span></span>  <br/> <span data-ttu-id="8f174-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="8f174-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="8f174-198">Хорватия</span><span class="sxs-lookup"><span data-stu-id="8f174-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="8f174-199">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-199">Format</span></span>

<span data-ttu-id="8f174-200">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="8f174-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-201">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-201">Pattern</span></span>

<span data-ttu-id="8f174-202">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f174-203">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-203">Checksum</span></span>

<span data-ttu-id="8f174-204">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-205">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-205">Definition</span></span>

<span data-ttu-id="8f174-206">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-207">Регулярное выражение `Regex_croatia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-208">Найдено ключевое `Keywords_croatia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="8f174-209">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-209">Keywords</span></span>

<span data-ttu-id="8f174-210">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-210"></span></span>
|<span data-ttu-id="8f174-211">**Keywords_croatia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-212">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-212">dl#</span></span>  <br/> <span data-ttu-id="8f174-213">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-213">driver license</span></span>  <br/> <span data-ttu-id="8f174-214">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-214">driver license number</span></span>  <br/> <span data-ttu-id="8f174-215">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-215">driver licence</span></span>  <br/> <span data-ttu-id="8f174-216">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-216">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-217">drivers license</span></span>  <br/> <span data-ttu-id="8f174-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-218">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-219">driver's license</span></span>  <br/> <span data-ttu-id="8f174-220">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-220">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-221">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-221">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-222">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-222">driving license number</span></span>  <br/> <span data-ttu-id="8f174-223">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-223">dlno#</span></span>  <br/> <span data-ttu-id="8f174-224">возаčка дозвола</span><span class="sxs-lookup"><span data-stu-id="8f174-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="8f174-225">Кипр</span><span class="sxs-lookup"><span data-stu-id="8f174-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="8f174-226">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-226">Format</span></span>

<span data-ttu-id="8f174-227">12 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="8f174-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-228">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-228">Pattern</span></span>

<span data-ttu-id="8f174-229">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f174-230">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-230">Checksum</span></span>

<span data-ttu-id="8f174-231">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-232">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-232">Definition</span></span>

<span data-ttu-id="8f174-233">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-234">Регулярное выражение `Regex_cyprus_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-235">Найдено ключевое `Keywords_cyprus_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-236">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-236">Keywords</span></span>

<span data-ttu-id="8f174-237">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-237"></span></span>
|<span data-ttu-id="8f174-238">**Keywords_cyprus_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-239">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-239">dl#</span></span>  <br/> <span data-ttu-id="8f174-240">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-240">driver license</span></span>  <br/> <span data-ttu-id="8f174-241">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-241">driver license number</span></span>  <br/> <span data-ttu-id="8f174-242">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-242">driver licence</span></span>  <br/> <span data-ttu-id="8f174-243">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-243">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-244">drivers license</span></span>  <br/> <span data-ttu-id="8f174-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-245">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-246">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-246">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-247">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-247">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-248">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-248">driving license number</span></span>  <br/> <span data-ttu-id="8f174-249">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-249">dlno#</span></span>  <br/> <span data-ttu-id="8f174-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="8f174-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="8f174-251">Чешская Республика</span><span class="sxs-lookup"><span data-stu-id="8f174-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="8f174-252">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-252">Format</span></span>

<span data-ttu-id="8f174-253">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-254">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-254">Pattern</span></span>

<span data-ttu-id="8f174-255">Восемь букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="8f174-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="8f174-256">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="8f174-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="8f174-257">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="8f174-257">A space (optional)</span></span>
    
- <span data-ttu-id="8f174-258">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f174-259">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-259">Checksum</span></span>

<span data-ttu-id="8f174-260">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-261">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-261">Definition</span></span>

<span data-ttu-id="8f174-262">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-263">Регулярное выражение `Regex_czech_republic_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-264">Найдено ключевое `Keywords_czech_republic_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="8f174-265">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-265">Keywords</span></span>

<span data-ttu-id="8f174-266">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-266"></span></span>
|<span data-ttu-id="8f174-267">**Keywords_czech_republic_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-268">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-268">dl#</span></span>  <br/> <span data-ttu-id="8f174-269">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-269">driver license</span></span>  <br/> <span data-ttu-id="8f174-270">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-270">driver license number</span></span>  <br/> <span data-ttu-id="8f174-271">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-271">driver licence</span></span>  <br/> <span data-ttu-id="8f174-272">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-272">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-273">drivers license</span></span>  <br/> <span data-ttu-id="8f174-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-274">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-275">driver's license</span></span>  <br/> <span data-ttu-id="8f174-276">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-276">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-277">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-277">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-278">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-278">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-279">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-279">driving license number</span></span>  <br/> <span data-ttu-id="8f174-280">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-280">dlno#</span></span>  <br/> <span data-ttu-id="8f174-281">řидиčскý прúказ</span><span class="sxs-lookup"><span data-stu-id="8f174-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="8f174-282">Дания</span><span class="sxs-lookup"><span data-stu-id="8f174-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="8f174-283">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-283">Format</span></span>

<span data-ttu-id="8f174-284">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="8f174-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-285">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-285">Pattern</span></span>

<span data-ttu-id="8f174-286">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f174-287">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-287">Checksum</span></span>

<span data-ttu-id="8f174-288">Да</span><span class="sxs-lookup"><span data-stu-id="8f174-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-289">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-289">Definition</span></span>

<span data-ttu-id="8f174-290">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-291">Регулярное выражение `Regex_denmark_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-292">Найдено ключевое `Keywords_denmark_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="8f174-293">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-293">Keywords</span></span>

<span data-ttu-id="8f174-294">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-294"></span></span>
|<span data-ttu-id="8f174-295">**Keywords_denmark_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-296">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-296">dl#</span></span>  <br/> <span data-ttu-id="8f174-297">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-297">driver license</span></span>  <br/> <span data-ttu-id="8f174-298">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-298">driver license number</span></span>  <br/> <span data-ttu-id="8f174-299">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-299">driver licence</span></span>  <br/> <span data-ttu-id="8f174-300">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-300">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-301">drivers license</span></span>  <br/> <span data-ttu-id="8f174-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-302">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-303">driver's license</span></span>  <br/> <span data-ttu-id="8f174-304">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-304">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-305">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-305">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-306">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-306">driving license number</span></span>  <br/> <span data-ttu-id="8f174-307">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-307">dlno#</span></span>  <br/> <span data-ttu-id="8f174-308">кøрекорт</span><span class="sxs-lookup"><span data-stu-id="8f174-308">kørekort</span></span>  <br/> <span data-ttu-id="8f174-309">кøрекортнуммер</span><span class="sxs-lookup"><span data-stu-id="8f174-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="8f174-310">Эстония</span><span class="sxs-lookup"><span data-stu-id="8f174-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="8f174-311">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-311">Format</span></span>

<span data-ttu-id="8f174-312">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-313">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-313">Pattern</span></span>

<span data-ttu-id="8f174-314">Две буквы и шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="8f174-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="8f174-315">Буквы "ET" (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="8f174-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="8f174-316">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f174-317">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-317">Checksum</span></span>

<span data-ttu-id="8f174-318">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-319">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-319">Definition</span></span>

<span data-ttu-id="8f174-320">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-321">Регулярное выражение `Regex_estonia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-322">Найдено ключевое `Keywords_estonia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-323">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-323">Keywords</span></span>

<span data-ttu-id="8f174-324">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-324"></span></span>
|<span data-ttu-id="8f174-325">**Keywords_estonia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-326">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-326">dl#</span></span>  <br/> <span data-ttu-id="8f174-327">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-327">driver license</span></span>  <br/> <span data-ttu-id="8f174-328">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-328">driver license number</span></span>  <br/> <span data-ttu-id="8f174-329">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-329">driver license number</span></span>  <br/> <span data-ttu-id="8f174-330">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-330">driver licence</span></span>  <br/> <span data-ttu-id="8f174-331">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-331">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-332">drivers license</span></span>  <br/> <span data-ttu-id="8f174-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-333">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-334">driver's license</span></span>  <br/> <span data-ttu-id="8f174-335">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-335">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-336">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-336">driving license number</span></span>  <br/> <span data-ttu-id="8f174-337">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-337">dlno#</span></span>  <br/> <span data-ttu-id="8f174-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="8f174-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="8f174-339">Финляндия</span><span class="sxs-lookup"><span data-stu-id="8f174-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="8f174-340">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-340">Format</span></span>

<span data-ttu-id="8f174-341">10 цифр, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="8f174-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-342">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-342">Pattern</span></span>

<span data-ttu-id="8f174-343">10 цифр, содержащих дефис:</span><span class="sxs-lookup"><span data-stu-id="8f174-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="8f174-344">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="8f174-344">Six digits</span></span> 
    
- <span data-ttu-id="8f174-345">дефис;</span><span class="sxs-lookup"><span data-stu-id="8f174-345">A hyphen</span></span>
    
-  <span data-ttu-id="8f174-346">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="8f174-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8f174-347">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-347">Checksum</span></span>

<span data-ttu-id="8f174-348">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-349">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-349">Definition</span></span>

<span data-ttu-id="8f174-350">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-351">Регулярное выражение `Regex_finland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-352">Найдено ключевое `Keywords_finland_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-353">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-353">Keywords</span></span>

<span data-ttu-id="8f174-354">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-354"></span></span>
|<span data-ttu-id="8f174-355">**Keywords_finland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-356">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-356">dl#</span></span>  <br/> <span data-ttu-id="8f174-357">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-357">driver license</span></span>  <br/> <span data-ttu-id="8f174-358">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-358">driver license number</span></span>  <br/> <span data-ttu-id="8f174-359">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-359">driver licence</span></span>  <br/> <span data-ttu-id="8f174-360">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-360">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-361">drivers license</span></span>  <br/> <span data-ttu-id="8f174-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-362">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-363">driver's license</span></span>  <br/> <span data-ttu-id="8f174-364">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-364">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-365">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-365">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-366">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-366">driving license number</span></span>  <br/> <span data-ttu-id="8f174-367">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-367">dlno#</span></span>  <br/> <span data-ttu-id="8f174-368">ажокортти</span><span class="sxs-lookup"><span data-stu-id="8f174-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="8f174-369">Франция</span><span class="sxs-lookup"><span data-stu-id="8f174-369">France</span></span>

<span data-ttu-id="8f174-370">Дополнительные сведения см. в разделе "номер водительского удостоверения для Франции" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8f174-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="8f174-371">Германия</span><span class="sxs-lookup"><span data-stu-id="8f174-371">Germany</span></span>

<span data-ttu-id="8f174-372">Дополнительные сведения можно найти в разделе "номер водительского удостоверения для немецкого драйвера" [, который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8f174-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="8f174-373">Греция</span><span class="sxs-lookup"><span data-stu-id="8f174-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="8f174-374">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-374">Format</span></span>

<span data-ttu-id="8f174-375">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="8f174-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-376">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-376">Pattern</span></span>

 <span data-ttu-id="8f174-377">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8f174-378">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-378">Checksum</span></span>

<span data-ttu-id="8f174-379">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-380">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-380">Definition</span></span>

<span data-ttu-id="8f174-381">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-382">Регулярное выражение `Regex_greece_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-383">Найдено ключевое `Keywords_greece_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-384">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-384">Keywords</span></span>

<span data-ttu-id="8f174-385">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-385"></span></span>
|<span data-ttu-id="8f174-386">**Keywords_greece_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-387">Файл #</span><span class="sxs-lookup"><span data-stu-id="8f174-387">dlL#</span></span>  <br/> <span data-ttu-id="8f174-388">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-388">driver license</span></span>  <br/> <span data-ttu-id="8f174-389">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-389">driver license number</span></span>  <br/> <span data-ttu-id="8f174-390">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-390">driver licence</span></span>  <br/> <span data-ttu-id="8f174-391">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-391">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-392">drivers license</span></span>  <br/> <span data-ttu-id="8f174-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-393">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-394">driver's license</span></span>  <br/> <span data-ttu-id="8f174-395">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-395">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-396">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-396">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-397">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-397">driving license number</span></span>  <br/> <span data-ttu-id="8f174-398">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-398">dlno#</span></span>  <br/> <span data-ttu-id="8f174-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="8f174-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="8f174-400">Адеиа одигисис</span><span class="sxs-lookup"><span data-stu-id="8f174-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="8f174-401">Венгрия</span><span class="sxs-lookup"><span data-stu-id="8f174-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="8f174-402">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-402">Format</span></span>

<span data-ttu-id="8f174-403">Две буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-404">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-404">Pattern</span></span>

<span data-ttu-id="8f174-405">Две буквы и шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="8f174-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="8f174-406">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="8f174-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="8f174-407">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f174-408">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-408">Checksum</span></span>

<span data-ttu-id="8f174-409">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-410">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-410">Definition</span></span>

<span data-ttu-id="8f174-411">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-412">Регулярное выражение `Regex_hungary_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-413">Найдено ключевое `Keywords_hungary_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-414">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-414">Keywords</span></span>

<span data-ttu-id="8f174-415">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-415"></span></span>
|<span data-ttu-id="8f174-416">**Keywords_hungary_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-417">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-417">dl#</span></span>  <br/> <span data-ttu-id="8f174-418">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-418">driver license</span></span>  <br/> <span data-ttu-id="8f174-419">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-419">driver license number</span></span>  <br/> <span data-ttu-id="8f174-420">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-420">driver licence</span></span>  <br/> <span data-ttu-id="8f174-421">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-421">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-422">drivers license</span></span>  <br/> <span data-ttu-id="8f174-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-423">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-424">driver's license</span></span>  <br/> <span data-ttu-id="8f174-425">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-425">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-426">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-426">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-427">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-427">driving license number</span></span>  <br/> <span data-ttu-id="8f174-428">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-428">dlno#</span></span>  <br/> <span data-ttu-id="8f174-429">везетои енжедели</span><span class="sxs-lookup"><span data-stu-id="8f174-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="8f174-430">Ireland (Ирландия)</span><span class="sxs-lookup"><span data-stu-id="8f174-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="8f174-431">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-431">Format</span></span>

<span data-ttu-id="8f174-432">Шесть цифр, за которыми следуют четыре буквы</span><span class="sxs-lookup"><span data-stu-id="8f174-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-433">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-433">Pattern</span></span>

<span data-ttu-id="8f174-434">Шесть цифр и четыре буквы:</span><span class="sxs-lookup"><span data-stu-id="8f174-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="8f174-435">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="8f174-435">Six digits</span></span>
    
- <span data-ttu-id="8f174-436">Четыре буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="8f174-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f174-437">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-437">Checksum</span></span>

<span data-ttu-id="8f174-438">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-439">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-439">Definition</span></span>

<span data-ttu-id="8f174-440">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-441">Регулярное выражение `Regex_ireland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-442">Найдено ключевое `Keywords_ireland_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-443">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-443">Keywords</span></span>

<span data-ttu-id="8f174-444">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-444"></span></span>
|<span data-ttu-id="8f174-445">**Keywords_ireland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-446">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-446">dl#</span></span>  <br/> <span data-ttu-id="8f174-447">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-447">driver license</span></span>  <br/> <span data-ttu-id="8f174-448">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-448">driver license number</span></span>  <br/> <span data-ttu-id="8f174-449">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-449">driver licence</span></span>  <br/> <span data-ttu-id="8f174-450">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-450">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-451">drivers license</span></span>  <br/> <span data-ttu-id="8f174-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-452">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-453">driver's license</span></span>  <br/> <span data-ttu-id="8f174-454">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-454">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-455">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-455">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-456">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-456">driving license number</span></span>  <br/> <span data-ttu-id="8f174-457">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-457">dlno#</span></span>  <br/> <span data-ttu-id="8f174-458">цеадúнас тиомáна</span><span class="sxs-lookup"><span data-stu-id="8f174-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="8f174-459">Италия</span><span class="sxs-lookup"><span data-stu-id="8f174-459">Italy</span></span>

<span data-ttu-id="8f174-460">Дополнительные сведения см. в разделе "номер водительского удостоверения для Италии" [, который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8f174-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="8f174-461">Латвия</span><span class="sxs-lookup"><span data-stu-id="8f174-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="8f174-462">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-462">Format</span></span>

<span data-ttu-id="8f174-463">Три буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-464">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-464">Pattern</span></span>

<span data-ttu-id="8f174-465">Три буквы и шесть цифр:</span><span class="sxs-lookup"><span data-stu-id="8f174-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="8f174-466">Три буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="8f174-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="8f174-467">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f174-468">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-468">Checksum</span></span>

<span data-ttu-id="8f174-469">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-470">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-470">Definition</span></span>

<span data-ttu-id="8f174-471">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-472">Регулярное выражение `Regex_latvia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-473">Найдено ключевое `Keywords_latvia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-474">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-474">Keywords</span></span>

<span data-ttu-id="8f174-475">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-475"></span></span>
|<span data-ttu-id="8f174-476">**Keywords_latvia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-477">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-477">dl#</span></span>  <br/> <span data-ttu-id="8f174-478">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-478">driver license</span></span>  <br/> <span data-ttu-id="8f174-479">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-479">driver license number</span></span>  <br/> <span data-ttu-id="8f174-480">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-480">driver licence</span></span>  <br/> <span data-ttu-id="8f174-481">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-481">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-482">drivers license</span></span>  <br/> <span data-ttu-id="8f174-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-483">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-484">driver's license</span></span>  <br/> <span data-ttu-id="8f174-485">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-485">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-486">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-486">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-487">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-487">driving license number</span></span>  <br/> <span data-ttu-id="8f174-488">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-488">dlno#</span></span>  <br/> <span data-ttu-id="8f174-489">аутовадīтāжа аплиекīба</span><span class="sxs-lookup"><span data-stu-id="8f174-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="8f174-490">Литва</span><span class="sxs-lookup"><span data-stu-id="8f174-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="8f174-491">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-491">Format</span></span>

<span data-ttu-id="8f174-492">Восемь цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="8f174-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-493">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-493">Pattern</span></span>

 <span data-ttu-id="8f174-494">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8f174-495">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-495">Checksum</span></span>

<span data-ttu-id="8f174-496">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-497">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-497">Definition</span></span>

<span data-ttu-id="8f174-498">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-499">Регулярное выражение `Regex_lithuania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-500">Найдено ключевое `Keywords_lithuania_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-501">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-501">Keywords</span></span>

<span data-ttu-id="8f174-502">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-502"></span></span>
|<span data-ttu-id="8f174-503">**Keywords_lithuania_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-504">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-504">dl#</span></span>  <br/> <span data-ttu-id="8f174-505">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-505">driver license</span></span>  <br/> <span data-ttu-id="8f174-506">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-506">driver license number</span></span>  <br/> <span data-ttu-id="8f174-507">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-507">driver licence</span></span>  <br/> <span data-ttu-id="8f174-508">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-508">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-509">drivers license</span></span>  <br/> <span data-ttu-id="8f174-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-510">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-511">driver's license</span></span>  <br/> <span data-ttu-id="8f174-512">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-512">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-513">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-513">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-514">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-514">driving license number</span></span>  <br/> <span data-ttu-id="8f174-515">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-515">dlno#</span></span>  <br/> <span data-ttu-id="8f174-516">ваируотожо паžимėжимас</span><span class="sxs-lookup"><span data-stu-id="8f174-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="8f174-517">луксембург</span><span class="sxs-lookup"><span data-stu-id="8f174-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="8f174-518">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-518">Format</span></span>

<span data-ttu-id="8f174-519">Шесть цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="8f174-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-520">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-520">Pattern</span></span>

 <span data-ttu-id="8f174-521">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8f174-522">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-522">Checksum</span></span>

<span data-ttu-id="8f174-523">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-524">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-524">Definition</span></span>

<span data-ttu-id="8f174-525">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-526">Регулярное выражение `Regex_luxemburg_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-527">Найдено ключевое `Keywords_luxemburg_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-528">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-528">Keywords</span></span>

<span data-ttu-id="8f174-529">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-529"></span></span>
|<span data-ttu-id="8f174-530">**Keywords_luxemburg_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-531">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-531">dl#</span></span>  <br/> <span data-ttu-id="8f174-532">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-532">driver license</span></span>  <br/> <span data-ttu-id="8f174-533">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-533">driver license number</span></span>  <br/> <span data-ttu-id="8f174-534">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-534">driver licence</span></span>  <br/> <span data-ttu-id="8f174-535">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-535">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-536">drivers license</span></span>  <br/> <span data-ttu-id="8f174-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-537">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-538">driver's license</span></span>  <br/> <span data-ttu-id="8f174-539">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-539">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-540">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-540">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-541">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-541">driving license number</span></span>  <br/> <span data-ttu-id="8f174-542">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-542">dlno#</span></span>  <br/> <span data-ttu-id="8f174-543">фахрерлаубнис</span><span class="sxs-lookup"><span data-stu-id="8f174-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="8f174-544">Мальта</span><span class="sxs-lookup"><span data-stu-id="8f174-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="8f174-545">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-545">Format</span></span>

<span data-ttu-id="8f174-546">Сочетание двух символов и шести цифр в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="8f174-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-547">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-547">Pattern</span></span>

<span data-ttu-id="8f174-548">Сочетание двух символов и шести цифр:</span><span class="sxs-lookup"><span data-stu-id="8f174-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="8f174-549">Два символа (цифры или буквы без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="8f174-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="8f174-550">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="8f174-550">A space (optional)</span></span>
    
- <span data-ttu-id="8f174-551">три цифры; </span><span class="sxs-lookup"><span data-stu-id="8f174-551">Three digits</span></span>
    
- <span data-ttu-id="8f174-552">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="8f174-552">A space (optional)</span></span>
    
- <span data-ttu-id="8f174-553">Три цифры</span><span class="sxs-lookup"><span data-stu-id="8f174-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f174-554">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-554">Checksum</span></span>

<span data-ttu-id="8f174-555">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-556">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-556">Definition</span></span>

<span data-ttu-id="8f174-557">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-558">Регулярное выражение `Regex_malta_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-559">Найдено ключевое `Keywords_malta_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-560">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-560">Keywords</span></span>

<span data-ttu-id="8f174-561">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-561"></span></span>
|<span data-ttu-id="8f174-562">**Keywords_malta_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-563">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-563">dl#</span></span>  <br/> <span data-ttu-id="8f174-564">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-564">driver license</span></span>  <br/> <span data-ttu-id="8f174-565">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-565">driver license number</span></span>  <br/> <span data-ttu-id="8f174-566">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-566">driver licence</span></span>  <br/> <span data-ttu-id="8f174-567">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-567">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-568">drivers license</span></span>  <br/> <span data-ttu-id="8f174-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-569">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-570">driver's license</span></span>  <br/> <span data-ttu-id="8f174-571">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-571">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-572">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-572">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-573">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-573">driving license number</span></span>  <br/> <span data-ttu-id="8f174-574">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-574">dlno#</span></span>  <br/> <span data-ttu-id="8f174-575">лиċензжаные зада Севкан</span><span class="sxs-lookup"><span data-stu-id="8f174-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="8f174-576">Нидерланды</span><span class="sxs-lookup"><span data-stu-id="8f174-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="8f174-577">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-577">Format</span></span>

<span data-ttu-id="8f174-578">10 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="8f174-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-579">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-579">Pattern</span></span>

<span data-ttu-id="8f174-580">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f174-581">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-581">Checksum</span></span>

<span data-ttu-id="8f174-582">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-583">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-583">Definition</span></span>

<span data-ttu-id="8f174-584">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-585">Регулярное выражение `Regex_netherlands_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-586">Найдено ключевое `Keywords_netherlands_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-587">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-587">Keywords</span></span>

<span data-ttu-id="8f174-588">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-588"></span></span>
|<span data-ttu-id="8f174-589">**Keywords_netherlands_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-590">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-590">dl#</span></span>  <br/> <span data-ttu-id="8f174-591">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-591">driver license</span></span>  <br/> <span data-ttu-id="8f174-592">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-592">driver license number</span></span>  <br/> <span data-ttu-id="8f174-593">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-593">driver licence</span></span>  <br/> <span data-ttu-id="8f174-594">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-594">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-595">drivers license</span></span>  <br/> <span data-ttu-id="8f174-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-596">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-597">driver's license</span></span>  <br/> <span data-ttu-id="8f174-598">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-598">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-599">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-599">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-600">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-600">driving license number</span></span>  <br/> <span data-ttu-id="8f174-601">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-601">dlno#</span></span>  <br/> <span data-ttu-id="8f174-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="8f174-602">permis de conduire</span></span>  <br/> <span data-ttu-id="8f174-603">рижбевижс</span><span class="sxs-lookup"><span data-stu-id="8f174-603">rijbewijs</span></span>  <br/> <span data-ttu-id="8f174-604">рижбевижснуммер</span><span class="sxs-lookup"><span data-stu-id="8f174-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="8f174-605">Польша</span><span class="sxs-lookup"><span data-stu-id="8f174-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="8f174-606">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-606">Format</span></span>

<span data-ttu-id="8f174-607">14 цифр, содержащих 2 косых черты.</span><span class="sxs-lookup"><span data-stu-id="8f174-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-608">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-608">Pattern</span></span>

<span data-ttu-id="8f174-609">14 цифр и 2 косых черт:</span><span class="sxs-lookup"><span data-stu-id="8f174-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="8f174-610">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="8f174-610">Five digits</span></span> 
    
- <span data-ttu-id="8f174-611">косая черта;</span><span class="sxs-lookup"><span data-stu-id="8f174-611">A forward slash</span></span>
    
- <span data-ttu-id="8f174-612">Две цифры</span><span class="sxs-lookup"><span data-stu-id="8f174-612">Two digits</span></span>
    
- <span data-ttu-id="8f174-613">косая черта;</span><span class="sxs-lookup"><span data-stu-id="8f174-613">A forward slash</span></span>
    
- <span data-ttu-id="8f174-614">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f174-615">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-615">Checksum</span></span>

<span data-ttu-id="8f174-616">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-617">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-617">Definition</span></span>

<span data-ttu-id="8f174-618">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-619">Регулярное выражение `Regex_poland_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-620">Найдено ключевое `Keywords_poland_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-621">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-621">Keywords</span></span>

<span data-ttu-id="8f174-622">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-622"></span></span>
|<span data-ttu-id="8f174-623">**Keywords_poland_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-624">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-624">dl#</span></span>  <br/> <span data-ttu-id="8f174-625">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-625">driver license</span></span>  <br/> <span data-ttu-id="8f174-626">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-626">driver license number</span></span>  <br/> <span data-ttu-id="8f174-627">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-627">driver licence</span></span>  <br/> <span data-ttu-id="8f174-628">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-628">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-629">drivers license</span></span>  <br/> <span data-ttu-id="8f174-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-630">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-631">driver's license</span></span>  <br/> <span data-ttu-id="8f174-632">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-632">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-633">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-633">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-634">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-634">driving license number</span></span>  <br/> <span data-ttu-id="8f174-635">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-635">dlno#</span></span>  <br/> <span data-ttu-id="8f174-636">право жазди</span><span class="sxs-lookup"><span data-stu-id="8f174-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="8f174-637">Португалия</span><span class="sxs-lookup"><span data-stu-id="8f174-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="8f174-638">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-638">Format</span></span>

<span data-ttu-id="8f174-639">Две буквы, за которыми следуют семь чисел в указанном шаблоне</span><span class="sxs-lookup"><span data-stu-id="8f174-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-640">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-640">Pattern</span></span>

<span data-ttu-id="8f174-641">Две буквы, за которыми следуют семь цифр со специальными символами:</span><span class="sxs-lookup"><span data-stu-id="8f174-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="8f174-642">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="8f174-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="8f174-643">дефис;</span><span class="sxs-lookup"><span data-stu-id="8f174-643">A hyphen</span></span>
    
- <span data-ttu-id="8f174-644">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="8f174-644">Six digits</span></span>
    
- <span data-ttu-id="8f174-645">Пробел</span><span class="sxs-lookup"><span data-stu-id="8f174-645">A space</span></span>
    
- <span data-ttu-id="8f174-646">одна цифра.</span><span class="sxs-lookup"><span data-stu-id="8f174-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f174-647">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-647">Checksum</span></span>

<span data-ttu-id="8f174-648">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-649">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-649">Definition</span></span>

<span data-ttu-id="8f174-650">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-651">Регулярное выражение `Regex_portugal_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-652">Найдено ключевое `Keywords_portugal_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-653">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-653">Keywords</span></span>

<span data-ttu-id="8f174-654">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-654"></span></span>
|<span data-ttu-id="8f174-655">**Keywords_portugal_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-656">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-656">dl#</span></span>  <br/> <span data-ttu-id="8f174-657">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-657">driver license</span></span>  <br/> <span data-ttu-id="8f174-658">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-658">driver license number</span></span>  <br/> <span data-ttu-id="8f174-659">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-659">driver licence</span></span>  <br/> <span data-ttu-id="8f174-660">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-660">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-661">drivers license</span></span>  <br/> <span data-ttu-id="8f174-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-662">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-663">driver's license</span></span>  <br/> <span data-ttu-id="8f174-664">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-664">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-665">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-665">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-666">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-666">driving license number</span></span>  <br/> <span data-ttu-id="8f174-667">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-667">dlno#</span></span>  <br/> <span data-ttu-id="8f174-668">картеира de моториста</span><span class="sxs-lookup"><span data-stu-id="8f174-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="8f174-669">Румыния</span><span class="sxs-lookup"><span data-stu-id="8f174-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="8f174-670">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-670">Format</span></span>

<span data-ttu-id="8f174-671">Один символ, за которым следуют восемь цифр</span><span class="sxs-lookup"><span data-stu-id="8f174-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-672">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-672">Pattern</span></span>

<span data-ttu-id="8f174-673">Один символ, за которым следуют восемь цифр:</span><span class="sxs-lookup"><span data-stu-id="8f174-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="8f174-674">Одна буква (без учета регистра) или цифра</span><span class="sxs-lookup"><span data-stu-id="8f174-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="8f174-675">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f174-676">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-676">Checksum</span></span>

<span data-ttu-id="8f174-677">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-678">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-678">Definition</span></span>

<span data-ttu-id="8f174-679">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-680">Регулярное выражение `Regex_romania_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-681">Найдено ключевое `Keywords_romania_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-682">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-682">Keywords</span></span>

<span data-ttu-id="8f174-683">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-683"></span></span>
|<span data-ttu-id="8f174-684">**Keywords_romania_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-685">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-685">dl#</span></span>  <br/> <span data-ttu-id="8f174-686">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-686">driver license</span></span>  <br/> <span data-ttu-id="8f174-687">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-687">driver license number</span></span>  <br/> <span data-ttu-id="8f174-688">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-688">driver licence</span></span>  <br/> <span data-ttu-id="8f174-689">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-689">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-690">drivers license</span></span>  <br/> <span data-ttu-id="8f174-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-691">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-692">driver's license</span></span>  <br/> <span data-ttu-id="8f174-693">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-693">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-694">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-694">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-695">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-695">driving license number</span></span>  <br/> <span data-ttu-id="8f174-696">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-696">dlno#</span></span>  <br/> <span data-ttu-id="8f174-697">разрешение de кондуцере</span><span class="sxs-lookup"><span data-stu-id="8f174-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="8f174-698">Словакия</span><span class="sxs-lookup"><span data-stu-id="8f174-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="8f174-699">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-699">Format</span></span>

<span data-ttu-id="8f174-700">Один символ, за которым следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-701">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-701">Pattern</span></span>

<span data-ttu-id="8f174-702">Один символ, за которым следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="8f174-703">Одна буква (без учета регистра) или цифра</span><span class="sxs-lookup"><span data-stu-id="8f174-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="8f174-704">семь цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8f174-705">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-705">Checksum</span></span>

<span data-ttu-id="8f174-706">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-707">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-707">Definition</span></span>

<span data-ttu-id="8f174-708">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-709">Регулярное выражение `Regex_slovakia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-710">Найдено ключевое `Keywords_slovakia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-711">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-711">Keywords</span></span>

<span data-ttu-id="8f174-712">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-712"></span></span>
|<span data-ttu-id="8f174-713">**Keywords_slovakia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-714">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-714">dl#</span></span>  <br/> <span data-ttu-id="8f174-715">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-715">driver license</span></span>  <br/> <span data-ttu-id="8f174-716">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-716">driver license number</span></span>  <br/> <span data-ttu-id="8f174-717">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-717">driver licence</span></span>  <br/> <span data-ttu-id="8f174-718">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-718">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-719">drivers license</span></span>  <br/> <span data-ttu-id="8f174-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-720">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-721">driver's license</span></span>  <br/> <span data-ttu-id="8f174-722">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-722">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-723">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-723">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-724">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-724">driving license number</span></span>  <br/> <span data-ttu-id="8f174-725">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-725">dlno#</span></span>  <br/> <span data-ttu-id="8f174-726">водиčскý преуказ</span><span class="sxs-lookup"><span data-stu-id="8f174-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="8f174-727">Словения</span><span class="sxs-lookup"><span data-stu-id="8f174-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="8f174-728">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-728">Format</span></span>

<span data-ttu-id="8f174-729">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="8f174-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-730">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-730">Pattern</span></span>

<span data-ttu-id="8f174-731">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8f174-732">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-732">Checksum</span></span>

<span data-ttu-id="8f174-733">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-734">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-734">Definition</span></span>

<span data-ttu-id="8f174-735">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-736">Регулярное выражение `Regex_slovenia_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-737">Найдено ключевое `Keywords_slovenia_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-738">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-738">Keywords</span></span>

<span data-ttu-id="8f174-739">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-739"></span></span>
|<span data-ttu-id="8f174-740">**Keywords_slovenia_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-741">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-741">dl#</span></span>  <br/> <span data-ttu-id="8f174-742">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-742">driver license</span></span>  <br/> <span data-ttu-id="8f174-743">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-743">driver license number</span></span>  <br/> <span data-ttu-id="8f174-744">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-744">driver licence</span></span>  <br/> <span data-ttu-id="8f174-745">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-745">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-746">drivers license</span></span>  <br/> <span data-ttu-id="8f174-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-747">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-748">driver's license</span></span>  <br/> <span data-ttu-id="8f174-749">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-749">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-750">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-750">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-751">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-751">driving license number</span></span>  <br/> <span data-ttu-id="8f174-752">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-752">dlno#</span></span>  <br/> <span data-ttu-id="8f174-753">возниšко доволженже</span><span class="sxs-lookup"><span data-stu-id="8f174-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="8f174-754">Испания</span><span class="sxs-lookup"><span data-stu-id="8f174-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="8f174-755">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-755">Format</span></span>

<span data-ttu-id="8f174-756">Восемь цифр, за которыми следует один символ</span><span class="sxs-lookup"><span data-stu-id="8f174-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-757">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-757">Pattern</span></span>

<span data-ttu-id="8f174-758">Восемь цифр, за которыми следует один символ:</span><span class="sxs-lookup"><span data-stu-id="8f174-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="8f174-759">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="8f174-759">Eight digits</span></span> 
    
- <span data-ttu-id="8f174-760">Одна цифра или буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="8f174-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f174-761">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-761">Checksum</span></span>

<span data-ttu-id="8f174-762">Да</span><span class="sxs-lookup"><span data-stu-id="8f174-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-763">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-763">Definition</span></span>

<span data-ttu-id="8f174-764">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-765">Функция `Func_spain_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-766">Найдено ключевое `Keywords_spain_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8f174-767">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-767">Keywords</span></span>

<span data-ttu-id="8f174-768">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-768"></span></span>
|<span data-ttu-id="8f174-769">**Keywords_spain_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-770">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-770">dlno#</span></span>  <br/> <span data-ttu-id="8f174-771">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-771">dl#</span></span>  <br/> <span data-ttu-id="8f174-772">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-772">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-773">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-773">driver licence</span></span>  <br/> <span data-ttu-id="8f174-774">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-774">driver license</span></span>  <br/> <span data-ttu-id="8f174-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-775">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-776">drivers license</span></span>  <br/> <span data-ttu-id="8f174-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="8f174-777">driver's licence</span></span>  <br/> <span data-ttu-id="8f174-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-778">driver's license</span></span>  <br/> <span data-ttu-id="8f174-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="8f174-779">driving licence</span></span>  <br/> <span data-ttu-id="8f174-780">driving license</span><span class="sxs-lookup"><span data-stu-id="8f174-780">driving license</span></span>  <br/> <span data-ttu-id="8f174-781">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-781">driver licence number</span></span>  <br/> <span data-ttu-id="8f174-782">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-782">driver license number</span></span>  <br/> <span data-ttu-id="8f174-783">драйвер номер лицензии</span><span class="sxs-lookup"><span data-stu-id="8f174-783">drivers licence number</span></span>  <br/> <span data-ttu-id="8f174-784">номер лицензии на драйверы</span><span class="sxs-lookup"><span data-stu-id="8f174-784">drivers license number</span></span>  <br/> <span data-ttu-id="8f174-785">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-785">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-786">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-786">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-787">номер водительской лицензии</span><span class="sxs-lookup"><span data-stu-id="8f174-787">driving licence number</span></span>  <br/> <span data-ttu-id="8f174-788">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-788">driving license number</span></span>  <br/> <span data-ttu-id="8f174-789">движущие разрешение</span><span class="sxs-lookup"><span data-stu-id="8f174-789">driving permit</span></span>  <br/> <span data-ttu-id="8f174-790">движущие число разрешений</span><span class="sxs-lookup"><span data-stu-id="8f174-790">driving permit number</span></span>  <br/> <span data-ttu-id="8f174-791">пермисо de кондукЦиóн</span><span class="sxs-lookup"><span data-stu-id="8f174-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="8f174-792">пермисо кондукЦиóн</span><span class="sxs-lookup"><span data-stu-id="8f174-792">permiso conducción</span></span>  <br/> <span data-ttu-id="8f174-793">нúмеро лиценЦиа кондуЦир</span><span class="sxs-lookup"><span data-stu-id="8f174-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="8f174-794">нúмеро de карнет де кондуЦир</span><span class="sxs-lookup"><span data-stu-id="8f174-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="8f174-795">нúмеро карнет кондуЦир</span><span class="sxs-lookup"><span data-stu-id="8f174-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="8f174-796">лиценЦиа кондуЦир</span><span class="sxs-lookup"><span data-stu-id="8f174-796">licencia conducir</span></span>  <br/> <span data-ttu-id="8f174-797">нúмеро de пермисо де кондуЦир</span><span class="sxs-lookup"><span data-stu-id="8f174-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="8f174-798">нúмеро де пермисо кондуЦир</span><span class="sxs-lookup"><span data-stu-id="8f174-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="8f174-799">нúмеро пермисо кондуЦир</span><span class="sxs-lookup"><span data-stu-id="8f174-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="8f174-800">пермисо кондуЦир</span><span class="sxs-lookup"><span data-stu-id="8f174-800">permiso conducir</span></span>  <br/> <span data-ttu-id="8f174-801">лиценЦиа de манежо</span><span class="sxs-lookup"><span data-stu-id="8f174-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="8f174-802">El карнет de кондуЦир</span><span class="sxs-lookup"><span data-stu-id="8f174-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="8f174-803">Карнет кондуЦир</span><span class="sxs-lookup"><span data-stu-id="8f174-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="8f174-804">Швеция</span><span class="sxs-lookup"><span data-stu-id="8f174-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="8f174-805">Format</span><span class="sxs-lookup"><span data-stu-id="8f174-805">Format</span></span>

<span data-ttu-id="8f174-806">Десять цифр, содержащие дефис</span><span class="sxs-lookup"><span data-stu-id="8f174-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8f174-807">Шаблон</span><span class="sxs-lookup"><span data-stu-id="8f174-807">Pattern</span></span>

<span data-ttu-id="8f174-808">Десять цифр, содержащих дефис:</span><span class="sxs-lookup"><span data-stu-id="8f174-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="8f174-809">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="8f174-809">Six digits</span></span> 
    
- <span data-ttu-id="8f174-810">дефис;</span><span class="sxs-lookup"><span data-stu-id="8f174-810">A hyphen</span></span>
    
- <span data-ttu-id="8f174-811">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="8f174-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8f174-812">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="8f174-812">Checksum</span></span>

<span data-ttu-id="8f174-813">Нет</span><span class="sxs-lookup"><span data-stu-id="8f174-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8f174-814">Определение</span><span class="sxs-lookup"><span data-stu-id="8f174-814">Definition</span></span>

<span data-ttu-id="8f174-815">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="8f174-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8f174-816">Регулярное выражение `Regex_sweden_eu_driver's_license_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="8f174-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8f174-817">Найдено ключевое `Keywords_sweden_eu_driver's_license_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="8f174-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="8f174-818">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8f174-818">Keywords</span></span>

<span data-ttu-id="8f174-819">| |</span><span class="sxs-lookup"><span data-stu-id="8f174-819"></span></span>
|<span data-ttu-id="8f174-820">**Keywords_sweden_eu_driver "s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8f174-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8f174-821">DL #</span><span class="sxs-lookup"><span data-stu-id="8f174-821">dl#</span></span>  <br/> <span data-ttu-id="8f174-822">driver license</span><span class="sxs-lookup"><span data-stu-id="8f174-822">driver license</span></span>  <br/> <span data-ttu-id="8f174-823">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-823">driver license number</span></span>  <br/> <span data-ttu-id="8f174-824">Лицензия на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-824">driver licence</span></span>  <br/> <span data-ttu-id="8f174-825">Drivers лик.</span><span class="sxs-lookup"><span data-stu-id="8f174-825">drivers lic.</span></span>  <br/> <span data-ttu-id="8f174-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="8f174-826">drivers license</span></span>  <br/> <span data-ttu-id="8f174-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8f174-827">drivers licence</span></span>  <br/> <span data-ttu-id="8f174-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="8f174-828">driver's license</span></span>  <br/> <span data-ttu-id="8f174-829">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-829">driver's license number</span></span>  <br/> <span data-ttu-id="8f174-830">номер лицензии на драйвер</span><span class="sxs-lookup"><span data-stu-id="8f174-830">driver's licence number</span></span>  <br/> <span data-ttu-id="8f174-831">номер водительского удостоверения</span><span class="sxs-lookup"><span data-stu-id="8f174-831">driving license number</span></span>  <br/> <span data-ttu-id="8f174-832">длно #</span><span class="sxs-lookup"><span data-stu-id="8f174-832">dlno#</span></span>  <br/> <span data-ttu-id="8f174-833">кöркорт</span><span class="sxs-lookup"><span data-stu-id="8f174-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="8f174-834">ВОЗМЕЩЕН</span><span class="sxs-lookup"><span data-stu-id="8f174-834">UK</span></span>

<span data-ttu-id="8f174-835">Дополнительные сведения см. в разделе "Великобритания</span><span class="sxs-lookup"><span data-stu-id="8f174-835">For details, see the section "U.K.</span></span> <span data-ttu-id="8f174-836">Номер водительского удостоверения, в [котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8f174-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8f174-837">См. также</span><span class="sxs-lookup"><span data-stu-id="8f174-837">See also</span></span>

[<span data-ttu-id="8f174-838">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="8f174-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

