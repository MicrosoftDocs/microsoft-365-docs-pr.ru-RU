---
title: Национальный идентификационный номер ЕС
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС по национальному идентификационному номеру. Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.
ms.openlocfilehash: f001d23ec3d6d8a2b3aa9575d4a9d602c4315e13
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592240"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="2a9aa-104">Национальный идентификационный номер ЕС</span><span class="sxs-lookup"><span data-stu-id="2a9aa-104">EU National Identification Number</span></span>

<span data-ttu-id="2a9aa-105">В этом разделе показано, как будет выглядеть политика защиты от потери данных (DLP), когда она обнаруживает тип конфиденциальной информации ЕС по национальному идентификационному номеру.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="2a9aa-106">Этот тип конфиденциальной информации определяет различные шаблоны, ключевые слова и другие доказательства для каждой страны.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="2a9aa-107">Австрия</span><span class="sxs-lookup"><span data-stu-id="2a9aa-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-108">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-108">Format</span></span>

<span data-ttu-id="2a9aa-109">24 – символическое сочетание букв, цифр и специальных символов;</span><span class="sxs-lookup"><span data-stu-id="2a9aa-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-110">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-110">Pattern</span></span>

<span data-ttu-id="2a9aa-111">24 символа:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-111">24 characters:</span></span>
  
-  <span data-ttu-id="2a9aa-112">22 буквы (без учета регистра), цифры, обратные косые черты, косые черты и знаки плюса</span><span class="sxs-lookup"><span data-stu-id="2a9aa-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="2a9aa-113">Две буквы (без учета регистра), цифры, обратные косые черты, знаки косой черты, знаки плюса и знаки равенства.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2a9aa-114">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-114">Checksum</span></span>

<span data-ttu-id="2a9aa-115">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="2a9aa-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-116">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-116">Definition</span></span>

<span data-ttu-id="2a9aa-117">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-118">Регулярное выражение `Regex_austria_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-119">Найдено ключевое `Keywords_austria_eu_national_id_card` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-120">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-120">Keywords</span></span>

#### <a name="keywords_austria_eu_national_id_card"></a><span data-ttu-id="2a9aa-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-122">Австрийский номер удостоверения</span><span class="sxs-lookup"><span data-stu-id="2a9aa-122">austrian identity number</span></span>
  
<span data-ttu-id="2a9aa-123">Национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-123">national identity number</span></span>
  
<span data-ttu-id="2a9aa-124">идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-124">identity number</span></span>
  
<span data-ttu-id="2a9aa-125">national id</span><span class="sxs-lookup"><span data-stu-id="2a9aa-125">national id</span></span>
  
<span data-ttu-id="2a9aa-126">персоналаусвеис Републик öстерреич</span><span class="sxs-lookup"><span data-stu-id="2a9aa-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="2a9aa-127">Бельгия</span><span class="sxs-lookup"><span data-stu-id="2a9aa-127">Belgium</span></span>

<span data-ttu-id="2a9aa-128">Дополнительные сведения можно найти в разделе "Бельгии National Number", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2a9aa-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="2a9aa-129">Болгария</span><span class="sxs-lookup"><span data-stu-id="2a9aa-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-130">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-130">Format</span></span>

<span data-ttu-id="2a9aa-131">Десять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="2a9aa-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-132">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-132">Pattern</span></span>

<span data-ttu-id="2a9aa-133">Десять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="2a9aa-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="2a9aa-134">Шесть цифр, соответствующих дате рождения (ГГММДД)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="2a9aa-135">Две цифры, соответствующие порядку рождения</span><span class="sxs-lookup"><span data-stu-id="2a9aa-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="2a9aa-136">Одна цифра, соответствующая Пол: четное число для пола и нечетная цифра для розетки</span><span class="sxs-lookup"><span data-stu-id="2a9aa-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="2a9aa-137">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="2a9aa-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2a9aa-138">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-138">Checksum</span></span>

<span data-ttu-id="2a9aa-139">Да</span><span class="sxs-lookup"><span data-stu-id="2a9aa-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-140">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-140">Definition</span></span>

<span data-ttu-id="2a9aa-141">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-142">Функция `Func_bulgaria_national_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-143">Найдено ключевое `Keywords_bulgaria_national_number` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="2a9aa-144">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-145">Функция `Func_bulgaria_national_number` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-146">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-146">Keywords</span></span>

#### <a name="keywords_bulgaria_national_number"></a><span data-ttu-id="2a9aa-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="2a9aa-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="2a9aa-148">егн</span><span class="sxs-lookup"><span data-stu-id="2a9aa-148">egn</span></span>
  
<span data-ttu-id="2a9aa-149">егн #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-149">egn#</span></span>
  
<span data-ttu-id="2a9aa-150">Национальный номер для болгарского языка</span><span class="sxs-lookup"><span data-stu-id="2a9aa-150">bulgarian national number</span></span>
  
<span data-ttu-id="2a9aa-151">номер страны</span><span class="sxs-lookup"><span data-stu-id="2a9aa-151">national number</span></span>
  
<span data-ttu-id="2a9aa-152">social security number</span><span class="sxs-lookup"><span data-stu-id="2a9aa-152">social security number</span></span>
  
<span data-ttu-id="2a9aa-153">натионалнумбер #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-153">nationalnumber#</span></span>
  
<span data-ttu-id="2a9aa-154">SSN #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-154">ssn#</span></span>
  
<span data-ttu-id="2a9aa-155">SSN</span><span class="sxs-lookup"><span data-stu-id="2a9aa-155">ssn</span></span>
  
<span data-ttu-id="2a9aa-156">натионалнумбер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-156">nationalnumber</span></span>
  
<span data-ttu-id="2a9aa-157">бнн #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-157">bnn#</span></span>
  
<span data-ttu-id="2a9aa-158">бнн</span><span class="sxs-lookup"><span data-stu-id="2a9aa-158">bnn</span></span>
  
<span data-ttu-id="2a9aa-159">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-159">personal id number</span></span>
  
<span data-ttu-id="2a9aa-160">персоналиднумбер #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-160">personalidnumber#</span></span>
  
<span data-ttu-id="2a9aa-161">единен граждански номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-161">единен граждански номер</span></span>
  
<span data-ttu-id="2a9aa-162">единен граздански номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="2a9aa-163">егн</span><span class="sxs-lookup"><span data-stu-id="2a9aa-163">егн</span></span>
  
<span data-ttu-id="2a9aa-164">егн #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="2a9aa-165">Хорватия</span><span class="sxs-lookup"><span data-stu-id="2a9aa-165">Croatia</span></span>

<span data-ttu-id="2a9aa-166">Дополнительные сведения см. в разделе "номер идентификатора Хорватия" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2a9aa-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="2a9aa-167">Кипр</span><span class="sxs-lookup"><span data-stu-id="2a9aa-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-168">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-168">Format</span></span>

<span data-ttu-id="2a9aa-169">Десять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="2a9aa-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-170">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-170">Pattern</span></span>

 <span data-ttu-id="2a9aa-171">Десять цифр</span><span class="sxs-lookup"><span data-stu-id="2a9aa-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2a9aa-172">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-172">Checksum</span></span>

<span data-ttu-id="2a9aa-173">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="2a9aa-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-174">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-174">Definition</span></span>

<span data-ttu-id="2a9aa-175">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-176">Регулярное выражение `Regex_cyprus_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-177">Найдено ключевое `Keywords_cyprus_eu_national_id_card` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-178">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-178">Keywords</span></span>

#### <a name="keywords_cyprus_eu_national_id_card"></a><span data-ttu-id="2a9aa-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-180">идентификационный номер карточки</span><span class="sxs-lookup"><span data-stu-id="2a9aa-180">id card number</span></span>
  
<span data-ttu-id="2a9aa-181">national identification number</span><span class="sxs-lookup"><span data-stu-id="2a9aa-181">national identification number</span></span>
  
<span data-ttu-id="2a9aa-182">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-182">personal id number</span></span>
  
<span data-ttu-id="2a9aa-183">Номер идентификационной карточки</span><span class="sxs-lookup"><span data-stu-id="2a9aa-183">identity card number</span></span>
  
<span data-ttu-id="2a9aa-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="2a9aa-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="2a9aa-185">Чешская Республика</span><span class="sxs-lookup"><span data-stu-id="2a9aa-185">Czech Republic</span></span>

<span data-ttu-id="2a9aa-186">Для получения дополнительных сведений обратитесь к разделу "Чешский Национальный идентификационный номер", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2a9aa-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="2a9aa-187">Дания</span><span class="sxs-lookup"><span data-stu-id="2a9aa-187">Denmark</span></span>

<span data-ttu-id="2a9aa-188">Дополнительные сведения можно найти в разделе "Дания персонального идентификационного номера", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2a9aa-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="2a9aa-189">Эстония</span><span class="sxs-lookup"><span data-stu-id="2a9aa-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-190">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-190">Format</span></span>

<span data-ttu-id="2a9aa-191">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="2a9aa-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-192">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-192">Pattern</span></span>

<span data-ttu-id="2a9aa-193">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-193">11 digits:</span></span>
  
- <span data-ttu-id="2a9aa-194">Одна цифра, соответствующая упоминанию секса и столетию рождения (нечетный номер, четная розетка), 1-2:19 века; 3-4:20 века; 5-6:21 столетие)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="2a9aa-195">Шесть цифр, соответствующих дате рождения (ГГММДД)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="2a9aa-196">Три цифры, которые соответствуют порядковому номеру, разделенному на одну и ту же дату.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="2a9aa-197">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="2a9aa-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2a9aa-198">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-198">Checksum</span></span>

<span data-ttu-id="2a9aa-199">Да</span><span class="sxs-lookup"><span data-stu-id="2a9aa-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-200">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-200">Definition</span></span>

<span data-ttu-id="2a9aa-201">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-202">Функция `Func_estonia_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-203">Найдено ключевое `Keywords_estonia_eu_national_id_card` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2a9aa-204">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-205">Функция `Func_estonia_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-206">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-206">Keywords</span></span>

#### <a name="keywords_estonia_eu_national_id_card"></a><span data-ttu-id="2a9aa-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-208">персональный идентификационный код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-208">personal identification code</span></span>
  
<span data-ttu-id="2a9aa-209">персональный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-209">personal identification number</span></span>
  
<span data-ttu-id="2a9aa-210">national identification number</span><span class="sxs-lookup"><span data-stu-id="2a9aa-210">national identification number</span></span>
  
<span data-ttu-id="2a9aa-211">номер страны</span><span class="sxs-lookup"><span data-stu-id="2a9aa-211">national number</span></span>
  
<span data-ttu-id="2a9aa-212">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-212">personal id number</span></span>
  
<span data-ttu-id="2a9aa-213">персоналиднумбер #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-213">personalidnumber#</span></span>
  
<span data-ttu-id="2a9aa-214">фигуры</span><span class="sxs-lookup"><span data-stu-id="2a9aa-214">ik</span></span>
  
<span data-ttu-id="2a9aa-215">исикукуд</span><span class="sxs-lookup"><span data-stu-id="2a9aa-215">isikukood</span></span>
  
<span data-ttu-id="2a9aa-216">ID — каарт</span><span class="sxs-lookup"><span data-stu-id="2a9aa-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="2a9aa-217">Финляндия</span><span class="sxs-lookup"><span data-stu-id="2a9aa-217">Finland</span></span>

<span data-ttu-id="2a9aa-218">Дополнительные сведения можно найти в разделе "Финляндия национального ID", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2a9aa-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="2a9aa-219">Франция</span><span class="sxs-lookup"><span data-stu-id="2a9aa-219">France</span></span>

<span data-ttu-id="2a9aa-220">Дополнительные сведения можно найти в разделе "Французская Национальная ИДЕНТИФИКАЦИОНная карточка (CNI)" [, в которой отображаются типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2a9aa-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="2a9aa-221">Германия</span><span class="sxs-lookup"><span data-stu-id="2a9aa-221">Germany</span></span>

<span data-ttu-id="2a9aa-222">Дополнительные сведения можно найти в разделе "номер идентификационной карточки для Германии" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2a9aa-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="2a9aa-223">Греция</span><span class="sxs-lookup"><span data-stu-id="2a9aa-223">Greece</span></span>

<span data-ttu-id="2a9aa-224">Дополнительные сведения можно найти в разделе "Греция National ID Card", [который будет искать тип конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2a9aa-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="2a9aa-225">Венгрия</span><span class="sxs-lookup"><span data-stu-id="2a9aa-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-226">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-226">Format</span></span>

<span data-ttu-id="2a9aa-227">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-228">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-228">Pattern</span></span>

<span data-ttu-id="2a9aa-229">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-229">11 digits:</span></span>
  
-  <span data-ttu-id="2a9aa-230">Одна цифра, соответствующая пол (1-м-штекер, 2-гнездо, другие номера также могут иметь гражданские телефоны перед 1900 или гражданами с удвоенной гражданией)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="2a9aa-231">Шесть цифр, соответствующих дате рождения (ГГММДД)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="2a9aa-232">Три цифры, соответствующие серийному номеру.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="2a9aa-233">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="2a9aa-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2a9aa-234">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-234">Checksum</span></span>

<span data-ttu-id="2a9aa-235">Да</span><span class="sxs-lookup"><span data-stu-id="2a9aa-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-236">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-236">Definition</span></span>

<span data-ttu-id="2a9aa-237">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-238">Функция `Func_hungary_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-239">Найдено ключевое `Keywords_hungary_eu_national_id_card` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2a9aa-240">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-241">Функция `Func_hungary_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-242">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-242">Keywords</span></span>

#### <a name="keywords_hungary_eu_national_id_card"></a><span data-ttu-id="2a9aa-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-244">персональный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-244">personal identification number</span></span>
  
<span data-ttu-id="2a9aa-245">identification number</span><span class="sxs-lookup"><span data-stu-id="2a9aa-245">identification number</span></span>
  
<span data-ttu-id="2a9aa-246">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-246">personal id number</span></span>
  
<span data-ttu-id="2a9aa-247">сземéлязоносíтó игазолвáни</span><span class="sxs-lookup"><span data-stu-id="2a9aa-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="2a9aa-248">Ireland (Ирландия)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-249">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-249">Format</span></span>

<span data-ttu-id="2a9aa-250">Сочетание букв, цифр и пробела в указанном шаблоне.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-251">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-251">Pattern</span></span>

<span data-ttu-id="2a9aa-252">Сочетание букв, цифр и пробела в указанном шаблоне.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="2a9aa-253">От 01 января 2013 до Now:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="2a9aa-254">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="2a9aa-254">Seven digits</span></span> 
    
- <span data-ttu-id="2a9aa-255">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="2a9aa-255">One check digit</span></span>
    
- <span data-ttu-id="2a9aa-256">Один пробел или буква в верхнем регистре "W" (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="2a9aa-257">До 01 января 2013:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="2a9aa-258">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="2a9aa-258">Seven digits</span></span> 
    
- <span data-ttu-id="2a9aa-259">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="2a9aa-259">One check digit</span></span>
    
- <span data-ttu-id="2a9aa-260">Один пробел или буква в верхнем регистре (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2a9aa-261">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-261">Checksum</span></span>

<span data-ttu-id="2a9aa-262">Да</span><span class="sxs-lookup"><span data-stu-id="2a9aa-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-263">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-263">Definition</span></span>

<span data-ttu-id="2a9aa-264">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-265">Функция находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="2a9aa-266">Найдено ключевое слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-266">A keyword from is found.</span></span>
    
<span data-ttu-id="2a9aa-267">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-268">Функция находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-268">The function finds content that matches the pattern.</span></span>
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-269">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-269">Keywords</span></span>

#### <a name="keywords_ireland_eu_national_id_card"></a><span data-ttu-id="2a9aa-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-271">номер личной общедоступной службы</span><span class="sxs-lookup"><span data-stu-id="2a9aa-271">personal public service number</span></span>
  
<span data-ttu-id="2a9aa-272">PPS нет</span><span class="sxs-lookup"><span data-stu-id="2a9aa-272">pps no</span></span>
  
<span data-ttu-id="2a9aa-273">номер дохода и социального страхования</span><span class="sxs-lookup"><span data-stu-id="2a9aa-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="2a9aa-274">RSI нет</span><span class="sxs-lookup"><span data-stu-id="2a9aa-274">rsi no</span></span>
  
<span data-ttu-id="2a9aa-275">персональный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-275">personal identification number</span></span>
  
<span data-ttu-id="2a9aa-276">identification number</span><span class="sxs-lookup"><span data-stu-id="2a9aa-276">identification number</span></span>
  
<span data-ttu-id="2a9aa-277">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-277">personal id number</span></span>
  
<span data-ttu-id="2a9aa-278">уимхир феарсанта сеирбхíсе поиблí</span><span class="sxs-lookup"><span data-stu-id="2a9aa-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="2a9aa-279">уимх.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-279">uimh.</span></span> <span data-ttu-id="2a9aa-280">настроен</span><span class="sxs-lookup"><span data-stu-id="2a9aa-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="2a9aa-281">Италия</span><span class="sxs-lookup"><span data-stu-id="2a9aa-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-282">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-282">Format</span></span>

<span data-ttu-id="2a9aa-283">16 – символическое сочетание букв и цифр в указанном шаблоне.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-284">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-284">Pattern</span></span>

<span data-ttu-id="2a9aa-285">16 – буквенное сочетание букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="2a9aa-286">Три буквы, соответствующие первым трем согласным в имени семейства</span><span class="sxs-lookup"><span data-stu-id="2a9aa-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="2a9aa-287">Три буквы, соответствующие первым, третьим и четвертым согласным в имени.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="2a9aa-288">Две цифры, соответствующие последним цифрам года рождения</span><span class="sxs-lookup"><span data-stu-id="2a9aa-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="2a9aa-289">Одна буква, соответствующая букве дня рождения, буквы используются в алфавитном порядке, но используются только буквы от A до E, H, L, M, P, R — T (то есть Январь — это R, а Октябрь — R)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="2a9aa-290">Две цифры, которые соответствуют дню месяца рождения, для различения пола, 40 добавляется в день рождения для женщин</span><span class="sxs-lookup"><span data-stu-id="2a9aa-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="2a9aa-291">Четыре цифры, соответствующие коду города, который относится к органу государственной власти, в котором был создан пользователь, (для иностранных стран используются коды уровня страны).</span><span class="sxs-lookup"><span data-stu-id="2a9aa-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="2a9aa-292">Одна цифра четности</span><span class="sxs-lookup"><span data-stu-id="2a9aa-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2a9aa-293">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-293">Checksum</span></span>

<span data-ttu-id="2a9aa-294">Да</span><span class="sxs-lookup"><span data-stu-id="2a9aa-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-295">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-295">Definition</span></span>

<span data-ttu-id="2a9aa-296">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-297">Функция `Func_italy_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-298">Найдено ключевое `Keywords_italy_eu_national_id_card` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2a9aa-299">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-300">Функция `Func_italy_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-301">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-301">Keywords</span></span>

#### <a name="keywords_italy_eu_national_id_card"></a><span data-ttu-id="2a9aa-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-303">персональный код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-303">personal code</span></span>
  
<span data-ttu-id="2a9aa-304">номер личного кода</span><span class="sxs-lookup"><span data-stu-id="2a9aa-304">personal code number</span></span>
  
<span data-ttu-id="2a9aa-305">личный номер сертификата</span><span class="sxs-lookup"><span data-stu-id="2a9aa-305">personal certificate number</span></span>
  
<span data-ttu-id="2a9aa-306">Финансовый код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-306">fiscal code</span></span>
  
<span data-ttu-id="2a9aa-307">персоналкодено #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-307">personalcodeno#</span></span>
  
<span data-ttu-id="2a9aa-308">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-308">personal id number</span></span>
  
<span data-ttu-id="2a9aa-309">личный код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-309">personal id code</span></span>
  
<span data-ttu-id="2a9aa-310">Персональные подкодеки</span><span class="sxs-lookup"><span data-stu-id="2a9aa-310">codice personale</span></span>
  
<span data-ttu-id="2a9aa-311">Нумеро цертификато персональный</span><span class="sxs-lookup"><span data-stu-id="2a9aa-311">numero certificato personale</span></span>
  
<span data-ttu-id="2a9aa-312">персональные настройки нумеро</span><span class="sxs-lookup"><span data-stu-id="2a9aa-312">numero personale</span></span>
  
<span data-ttu-id="2a9aa-313">личный идентификатор нумеро</span><span class="sxs-lookup"><span data-stu-id="2a9aa-313">numero id personale</span></span>
  
<span data-ttu-id="2a9aa-314">личные коды для сокодовых костей</span><span class="sxs-lookup"><span data-stu-id="2a9aa-314">codice id personale</span></span>
  
<span data-ttu-id="2a9aa-315">финансовый отчет по сокостям</span><span class="sxs-lookup"><span data-stu-id="2a9aa-315">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="2a9aa-316">Латвия</span><span class="sxs-lookup"><span data-stu-id="2a9aa-316">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-317">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-317">Format</span></span>

<span data-ttu-id="2a9aa-318">11 цифр и дефис в указанном формате.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-319">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-319">Pattern</span></span>

<span data-ttu-id="2a9aa-320">11 цифр и дефис:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="2a9aa-321">Шесть цифр, соответствующих дате рождения (ДДММГГ —)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="2a9aa-322">дефис;</span><span class="sxs-lookup"><span data-stu-id="2a9aa-322">A hyphen</span></span>
    
- <span data-ttu-id="2a9aa-323">Одна цифра, соответствующая столетию рождения ("0" для 19 века, "1" для 20-й век) и "2" для 21 века)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="2a9aa-324">Четыре цифры, созданные случайным образом</span><span class="sxs-lookup"><span data-stu-id="2a9aa-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2a9aa-325">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-325">Checksum</span></span>

<span data-ttu-id="2a9aa-326">Да</span><span class="sxs-lookup"><span data-stu-id="2a9aa-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-327">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-327">Definition</span></span>

<span data-ttu-id="2a9aa-328">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-329">Функция `Func_latvia_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-330">Найдено ключевое `Keywords_latvia_eu_national_id_card` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2a9aa-331">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-332">Функция `Func_latvia_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-333">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-333">Keywords</span></span>

#### <a name="keywords_latvia_eu_national_id_card"></a><span data-ttu-id="2a9aa-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-335">персональный код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-335">personal code</span></span>
  
<span data-ttu-id="2a9aa-336">номер личного кода</span><span class="sxs-lookup"><span data-stu-id="2a9aa-336">personal code number</span></span>
  
<span data-ttu-id="2a9aa-337">личный номер сертификата</span><span class="sxs-lookup"><span data-stu-id="2a9aa-337">personal certificate number</span></span>
  
<span data-ttu-id="2a9aa-338">персоналкодено #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-338">personalcodeno#</span></span>
  
<span data-ttu-id="2a9aa-339">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-339">personal id number</span></span>
  
<span data-ttu-id="2a9aa-340">личный код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-340">personal id code</span></span>
  
<span data-ttu-id="2a9aa-341">Пользователи Кодс</span><span class="sxs-lookup"><span data-stu-id="2a9aa-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="2a9aa-342">Литва</span><span class="sxs-lookup"><span data-stu-id="2a9aa-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-343">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-343">Format</span></span>

<span data-ttu-id="2a9aa-344">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="2a9aa-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-345">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-345">Pattern</span></span>

<span data-ttu-id="2a9aa-346">11 цифр без пробелов и разделителей:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="2a9aa-347">Одна цифра, соответствующая пол и век рождения человека</span><span class="sxs-lookup"><span data-stu-id="2a9aa-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="2a9aa-348">Шесть цифр, соответствующих дате рождения (ГГММДД)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="2a9aa-349">Три цифры, которые соответствуют серийному числу даты рождения.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="2a9aa-350">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="2a9aa-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2a9aa-351">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-351">Checksum</span></span>

<span data-ttu-id="2a9aa-352">Да</span><span class="sxs-lookup"><span data-stu-id="2a9aa-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-353">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-353">Definition</span></span>

<span data-ttu-id="2a9aa-354">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-355">Функция `Func_lithuania_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-356">Найдено ключевое `Keywords_lithuania_eu_national_id_card` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2a9aa-357">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-358">Функция `Func_lithuania_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-359">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-359">Keywords</span></span>

#### <a name="keywords_lithuania_eu_national_id_card"></a><span data-ttu-id="2a9aa-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-361">персональный числовой код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-361">personal numeric code</span></span>
  
<span data-ttu-id="2a9aa-362">уникальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-362">unique identification number</span></span>
  
<span data-ttu-id="2a9aa-363">номер службы для себя</span><span class="sxs-lookup"><span data-stu-id="2a9aa-363">citizen service number</span></span>
  
<span data-ttu-id="2a9aa-364">уникальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-364">unique identity number</span></span>
  
<span data-ttu-id="2a9aa-365">уникуеидентитино #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="2a9aa-366">персональный код.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-366">personal code.</span></span>
  
<span data-ttu-id="2a9aa-367">асменинис скаитменинис кодас</span><span class="sxs-lookup"><span data-stu-id="2a9aa-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="2a9aa-368">уникалус идентификавимо нумерис</span><span class="sxs-lookup"><span data-stu-id="2a9aa-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="2a9aa-369">пилиеčио паслаугос нумерис</span><span class="sxs-lookup"><span data-stu-id="2a9aa-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="2a9aa-370">уникалус идентификавимо кодас</span><span class="sxs-lookup"><span data-stu-id="2a9aa-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="2a9aa-371">асменс кодас.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="2a9aa-372">луксембург</span><span class="sxs-lookup"><span data-stu-id="2a9aa-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-373">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-373">Format</span></span>

<span data-ttu-id="2a9aa-374">11 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="2a9aa-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-375">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-375">Pattern</span></span>

<span data-ttu-id="2a9aa-376">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-376">11 digits</span></span>
  
- <span data-ttu-id="2a9aa-377">Одна цифра, соответствующая пол и век рождения человека</span><span class="sxs-lookup"><span data-stu-id="2a9aa-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="2a9aa-378">Шесть цифр, соответствующих дате рождения (ГГММДД)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="2a9aa-379">Три цифры, которые соответствуют серийному числу даты рождения.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="2a9aa-380">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="2a9aa-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2a9aa-381">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-381">Checksum</span></span>

<span data-ttu-id="2a9aa-382">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="2a9aa-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-383">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-383">Definition</span></span>

<span data-ttu-id="2a9aa-384">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-385">Регулярное выражение `Regex_luxemburg_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-386">Найдено ключевое `Keywords_luxemburg_eu_national_id_card` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-387">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-387">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_national_id_card"></a><span data-ttu-id="2a9aa-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-389">личный идентификатор</span><span class="sxs-lookup"><span data-stu-id="2a9aa-389">personal id</span></span>
  
<span data-ttu-id="2a9aa-390">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-390">personal id number</span></span>
  
<span data-ttu-id="2a9aa-391">персоналидно #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-391">personalidno#</span></span>
  
<span data-ttu-id="2a9aa-392">уникальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-392">unique id number</span></span>
  
<span data-ttu-id="2a9aa-393">персоналиднумбер #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-393">personalidnumber#</span></span>
  
<span data-ttu-id="2a9aa-394">уникальный ключ идентификатора</span><span class="sxs-lookup"><span data-stu-id="2a9aa-394">unique id key</span></span>
  
<span data-ttu-id="2a9aa-395">личный код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-395">personal id code</span></span>
  
<span data-ttu-id="2a9aa-396">уникуеидкэй #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-396">uniqueidkey#</span></span>
  
<span data-ttu-id="2a9aa-397">отдельный код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-397">individual code</span></span>
  
<span data-ttu-id="2a9aa-398">индивидуальный идентификатор</span><span class="sxs-lookup"><span data-stu-id="2a9aa-398">individual id</span></span>
  
<span data-ttu-id="2a9aa-399">Идентификатор еиндеутиже — нуммер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="2a9aa-400">Идентификатор еиндеутиже</span><span class="sxs-lookup"><span data-stu-id="2a9aa-400">eindeutige id</span></span>
  
<span data-ttu-id="2a9aa-401">ID персоннелле</span><span class="sxs-lookup"><span data-stu-id="2a9aa-401">id personnelle</span></span>
  
<span data-ttu-id="2a9aa-402">нумéро д'идентификатион сотрудники</span><span class="sxs-lookup"><span data-stu-id="2a9aa-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="2a9aa-403">идперсоннелле #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-403">idpersonnelle#</span></span>
  
<span data-ttu-id="2a9aa-404">персöнличе идентификатионснуммер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="2a9aa-405">еиндеутижеид #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="2a9aa-406">Мальта</span><span class="sxs-lookup"><span data-stu-id="2a9aa-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-407">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-407">Format</span></span>

<span data-ttu-id="2a9aa-408">Семь цифр, за которыми следует одна буква</span><span class="sxs-lookup"><span data-stu-id="2a9aa-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-409">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-409">Pattern</span></span>

<span data-ttu-id="2a9aa-410">Семь цифр, за которыми следует одна буква:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="2a9aa-411">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="2a9aa-411">Seven digits</span></span> 
    
- <span data-ttu-id="2a9aa-412">Одна прописная буква (с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2a9aa-413">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-413">Checksum</span></span>

<span data-ttu-id="2a9aa-414">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="2a9aa-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-415">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-415">Definition</span></span>

<span data-ttu-id="2a9aa-416">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-417">Регулярное выражение `Regex_malta_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-418">Найдено ключевое `Keywords_malta_eu_national_id_card` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2a9aa-419">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-420">Регулярное выражение `Regex_malta_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-421">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-421">Keywords</span></span>

#### <a name="keywords_malta_eu_national_id_card"></a><span data-ttu-id="2a9aa-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-423">персональный числовой код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-423">personal numeric code</span></span>
  
<span data-ttu-id="2a9aa-424">уникальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-424">unique identification number</span></span>
  
<span data-ttu-id="2a9aa-425">номер службы для себя</span><span class="sxs-lookup"><span data-stu-id="2a9aa-425">citizen service number</span></span>
  
<span data-ttu-id="2a9aa-426">уникальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-426">unique identity number</span></span>
  
<span data-ttu-id="2a9aa-427">уникуеидентитино #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="2a9aa-428">кодиċи нумерали персонали</span><span class="sxs-lookup"><span data-stu-id="2a9aa-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="2a9aa-429">нумру Ta ' идентификаззжони унику</span><span class="sxs-lookup"><span data-stu-id="2a9aa-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="2a9aa-430">нумруные зада сервизз таċ ċиттадин</span><span class="sxs-lookup"><span data-stu-id="2a9aa-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="2a9aa-431">нумру Ta ' идентитà унику</span><span class="sxs-lookup"><span data-stu-id="2a9aa-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="2a9aa-432">Нидерланды</span><span class="sxs-lookup"><span data-stu-id="2a9aa-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-433">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-433">Format</span></span>

<span data-ttu-id="2a9aa-434">Девять цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="2a9aa-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-435">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-435">Pattern</span></span>

<span data-ttu-id="2a9aa-436">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2a9aa-437">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-437">Checksum</span></span>

<span data-ttu-id="2a9aa-438">Да</span><span class="sxs-lookup"><span data-stu-id="2a9aa-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-439">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-439">Definition</span></span>

<span data-ttu-id="2a9aa-440">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-441">Функция `Func_netherlands_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-442">Найдено ключевое слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-442">A keyword from is found.</span></span>
    
<span data-ttu-id="2a9aa-443">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-444">Функция `Func_netherlands_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-445">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-445">Keywords</span></span>

#### <a name="keywords_netherlands_eu_national_id_card"></a><span data-ttu-id="2a9aa-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-447">персональный числовой код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-447">personal numeric code</span></span>
  
<span data-ttu-id="2a9aa-448">уникальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-448">unique identification number</span></span>
  
<span data-ttu-id="2a9aa-449">номер службы для себя</span><span class="sxs-lookup"><span data-stu-id="2a9aa-449">citizen service number</span></span>
  
<span data-ttu-id="2a9aa-450">уникальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-450">unique identity number</span></span>
  
<span data-ttu-id="2a9aa-451">уникуеидентитино #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="2a9aa-452">BSN</span><span class="sxs-lookup"><span data-stu-id="2a9aa-452">bsn</span></span>
  
<span data-ttu-id="2a9aa-453">BSN #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-453">bsn#</span></span>
  
<span data-ttu-id="2a9aa-454">персунлижке нумериеке код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="2a9aa-455">униек идентификатиенуммер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="2a9aa-456">буржерсервиценуммер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-456">burgerservicenummer</span></span>
  
<span data-ttu-id="2a9aa-457">униек идентитеитснуммер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="2a9aa-458">Польша</span><span class="sxs-lookup"><span data-stu-id="2a9aa-458">Poland</span></span>

<span data-ttu-id="2a9aa-459">Дополнительные сведения см. в разделе "Польша National ID (PESEL)" [, в котором ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2a9aa-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="2a9aa-460">Португалия</span><span class="sxs-lookup"><span data-stu-id="2a9aa-460">Portugal</span></span>

<span data-ttu-id="2a9aa-461">Дополнительные сведения можно найти в разделе "номер карты для Португалия" в разделе [сведения о типах конфиденциальной информации для поиска](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2a9aa-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="2a9aa-462">Румыния</span><span class="sxs-lookup"><span data-stu-id="2a9aa-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-463">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-463">Format</span></span>

<span data-ttu-id="2a9aa-464">13 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="2a9aa-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-465">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-465">Pattern</span></span>

<span data-ttu-id="2a9aa-466">13 цифр.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2a9aa-467">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-467">Checksum</span></span>

<span data-ttu-id="2a9aa-468">Да</span><span class="sxs-lookup"><span data-stu-id="2a9aa-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-469">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-469">Definition</span></span>

<span data-ttu-id="2a9aa-470">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-471">Функция `Func_romania_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-472">Найдено ключевое `Keywords_romania_eu_national_id_card` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2a9aa-473">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-474">Функция `Func_romania_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-475">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-475">Keywords</span></span>

#### <a name="keywords_romania_eu_national_id_card"></a><span data-ttu-id="2a9aa-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-477">персональный числовой код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-477">personal numeric code</span></span>
  
<span data-ttu-id="2a9aa-478">уникальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-478">unique identification number</span></span>
  
<span data-ttu-id="2a9aa-479">кнп</span><span class="sxs-lookup"><span data-stu-id="2a9aa-479">cnp</span></span>
  
<span data-ttu-id="2a9aa-480">кнп #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-480">cnp#</span></span>
  
<span data-ttu-id="2a9aa-481">крепления</span><span class="sxs-lookup"><span data-stu-id="2a9aa-481">pin</span></span>
  
<span data-ttu-id="2a9aa-482">крепления #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-482">pin#</span></span>
  
<span data-ttu-id="2a9aa-483">страховой номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-483">insurance number</span></span>
  
<span data-ttu-id="2a9aa-484">инсуранценумбер #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-484">insurancenumber#</span></span>
  
<span data-ttu-id="2a9aa-485">уникальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-485">unique identity number</span></span>
  
<span data-ttu-id="2a9aa-486">уникуеидентитино #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="2a9aa-487">цифровой платеж, персональный</span><span class="sxs-lookup"><span data-stu-id="2a9aa-487">cod numeric personal</span></span>
  
<span data-ttu-id="2a9aa-488">Личный идентификаре наложенного платежа</span><span class="sxs-lookup"><span data-stu-id="2a9aa-488">cod identificare personal</span></span>
  
<span data-ttu-id="2a9aa-489">наложенный Уник идентификаре</span><span class="sxs-lookup"><span data-stu-id="2a9aa-489">cod unic identificare</span></span>
  
<span data-ttu-id="2a9aa-490">нумăр Personal Уник</span><span class="sxs-lookup"><span data-stu-id="2a9aa-490">număr personal unic</span></span>
  
<span data-ttu-id="2a9aa-491">нумăр идентитате</span><span class="sxs-lookup"><span data-stu-id="2a9aa-491">număr identitate</span></span>
  
<span data-ttu-id="2a9aa-492">нумăр идентификаре персональный</span><span class="sxs-lookup"><span data-stu-id="2a9aa-492">număr identificare personal</span></span>
  
<span data-ttu-id="2a9aa-493">нумăридентитате #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-493">număridentitate#</span></span>
  
<span data-ttu-id="2a9aa-494">коднумерикперсонал #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="2a9aa-495">нумăрперсоналуник #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="2a9aa-496">Словакия</span><span class="sxs-lookup"><span data-stu-id="2a9aa-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-497">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-497">Format</span></span>

<span data-ttu-id="2a9aa-498">Десять цифр, содержащих одну обратную косую черту;</span><span class="sxs-lookup"><span data-stu-id="2a9aa-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-499">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-499">Pattern</span></span>

<span data-ttu-id="2a9aa-500">Десять цифр, содержащих одну обратную косую черту:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2a9aa-501">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-501">Checksum</span></span>

<span data-ttu-id="2a9aa-502">Да</span><span class="sxs-lookup"><span data-stu-id="2a9aa-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-503">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-503">Definition</span></span>

<span data-ttu-id="2a9aa-504">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-505">Функция `Func_slovakia_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-506">Найдено ключевое `Keywords_slovakia_eu_national_id_card` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2a9aa-507">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-508">Функция `Func_slovakia_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-509">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-509">Keywords</span></span>

#### <a name="keywords_slovakia_eu_national_id_card"></a><span data-ttu-id="2a9aa-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-511">номер рождения</span><span class="sxs-lookup"><span data-stu-id="2a9aa-511">birth number</span></span>
  
<span data-ttu-id="2a9aa-512">national identification number</span><span class="sxs-lookup"><span data-stu-id="2a9aa-512">national identification number</span></span>
  
<span data-ttu-id="2a9aa-513">персональный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-513">personal identification number</span></span>
  
<span data-ttu-id="2a9aa-514">social security number</span><span class="sxs-lookup"><span data-stu-id="2a9aa-514">social security number</span></span>
  
<span data-ttu-id="2a9aa-515">натионалнумбер #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-515">nationalnumber#</span></span>
  
<span data-ttu-id="2a9aa-516">SSN #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-516">ssn#</span></span>
  
<span data-ttu-id="2a9aa-517">SSN</span><span class="sxs-lookup"><span data-stu-id="2a9aa-517">ssn</span></span>
  
<span data-ttu-id="2a9aa-518">номер страны</span><span class="sxs-lookup"><span data-stu-id="2a9aa-518">national number</span></span>
  
<span data-ttu-id="2a9aa-519">личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-519">personal id number</span></span>
  
<span data-ttu-id="2a9aa-520">персоналиднумбер #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-520">personalidnumber#</span></span>
  
<span data-ttu-id="2a9aa-521">рč</span><span class="sxs-lookup"><span data-stu-id="2a9aa-521">rč</span></span>
  
<span data-ttu-id="2a9aa-522">роднé číсло</span><span class="sxs-lookup"><span data-stu-id="2a9aa-522">rodné číslo</span></span>
  
<span data-ttu-id="2a9aa-523">родне Цисло</span><span class="sxs-lookup"><span data-stu-id="2a9aa-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="2a9aa-524">Словения</span><span class="sxs-lookup"><span data-stu-id="2a9aa-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-525">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-525">Format</span></span>

<span data-ttu-id="2a9aa-526">13 цифр без пробелов и разделителей</span><span class="sxs-lookup"><span data-stu-id="2a9aa-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-527">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-527">Pattern</span></span>

<span data-ttu-id="2a9aa-528">13 цифр в указанном шаблоне:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="2a9aa-529">Семь цифр, которые соответствуют дате рождения (ДДММЛЛЛ), где "ЛЛЛ" соответствует последним трем цифрам года рождения</span><span class="sxs-lookup"><span data-stu-id="2a9aa-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="2a9aa-530">Две цифры, соответствующие области рождения</span><span class="sxs-lookup"><span data-stu-id="2a9aa-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="2a9aa-531">Три цифры, которые соответствуют сочетанию пола и серийного номера для людей, которые приставили один и тот же день (000-499 для пола и 500-999 для розетки)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="2a9aa-532">Одна контрольная цифра</span><span class="sxs-lookup"><span data-stu-id="2a9aa-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2a9aa-533">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-533">Checksum</span></span>

<span data-ttu-id="2a9aa-534">Да</span><span class="sxs-lookup"><span data-stu-id="2a9aa-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-535">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-535">Definition</span></span>

<span data-ttu-id="2a9aa-536">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-537">Функция `Func_slovenia_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-538">Найдено ключевое `Keywords_slovenia_eu_national_id_card` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="2a9aa-539">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-540">Функция `Func_slovenia_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-541">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-541">Keywords</span></span>

#### <a name="keywords_slovenia_eu_national_id_card"></a><span data-ttu-id="2a9aa-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-543">персональный числовой код</span><span class="sxs-lookup"><span data-stu-id="2a9aa-543">personal numeric code</span></span>
  
<span data-ttu-id="2a9aa-544">уникальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-544">unique identification number</span></span>
  
<span data-ttu-id="2a9aa-545">уникальный регистрационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-545">unique registration number</span></span>
  
<span data-ttu-id="2a9aa-546">уникальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-546">unique identity number</span></span>
  
<span data-ttu-id="2a9aa-547">уникуеидентитино #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="2a9aa-548">уникальный основной номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-548">unique master citizen number</span></span>
  
<span data-ttu-id="2a9aa-549">единствена идентификаЦижска šтевилка</span><span class="sxs-lookup"><span data-stu-id="2a9aa-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="2a9aa-550">уникуеидентитино #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="2a9aa-551">единствена šтевилка главнега дрžавлжана</span><span class="sxs-lookup"><span data-stu-id="2a9aa-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="2a9aa-552">емšо</span><span class="sxs-lookup"><span data-stu-id="2a9aa-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="2a9aa-553">Испания</span><span class="sxs-lookup"><span data-stu-id="2a9aa-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="2a9aa-554">Format</span><span class="sxs-lookup"><span data-stu-id="2a9aa-554">Format</span></span>

<span data-ttu-id="2a9aa-555">Семь цифр, за которыми следует один символ</span><span class="sxs-lookup"><span data-stu-id="2a9aa-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2a9aa-556">Шаблон</span><span class="sxs-lookup"><span data-stu-id="2a9aa-556">Pattern</span></span>

<span data-ttu-id="2a9aa-557">Семь цифр, за которыми следует один символ</span><span class="sxs-lookup"><span data-stu-id="2a9aa-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="2a9aa-558">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="2a9aa-558">Seven digits</span></span>
    
- <span data-ttu-id="2a9aa-559">Одна цифра или буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="2a9aa-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2a9aa-560">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="2a9aa-560">Checksum</span></span>

<span data-ttu-id="2a9aa-561">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="2a9aa-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2a9aa-562">Определение</span><span class="sxs-lookup"><span data-stu-id="2a9aa-562">Definition</span></span>

<span data-ttu-id="2a9aa-563">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="2a9aa-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2a9aa-564">Регулярное выражение `Regex_spain_eu_national_id_card` находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2a9aa-565">Найдено ключевое `Keywords_spain_eu_national_id_card"` слово FROM.</span><span class="sxs-lookup"><span data-stu-id="2a9aa-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2a9aa-566">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="2a9aa-566">Keywords</span></span>

#### <a name="keywords_spain_eu_national_id_card"></a><span data-ttu-id="2a9aa-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="2a9aa-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="2a9aa-568">DNI</span><span class="sxs-lookup"><span data-stu-id="2a9aa-568">dni</span></span>
  
<span data-ttu-id="2a9aa-569">national identification number</span><span class="sxs-lookup"><span data-stu-id="2a9aa-569">national identification number</span></span>
  
<span data-ttu-id="2a9aa-570">Национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-570">national identity number</span></span>
  
<span data-ttu-id="2a9aa-571">страховой номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-571">insurance number</span></span>
  
<span data-ttu-id="2a9aa-572">персональный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-572">personal identification number</span></span>
  
<span data-ttu-id="2a9aa-573">Национальная идентификация</span><span class="sxs-lookup"><span data-stu-id="2a9aa-573">national identity</span></span>
  
<span data-ttu-id="2a9aa-574">личный идентификатор</span><span class="sxs-lookup"><span data-stu-id="2a9aa-574">personal identity no</span></span>
  
<span data-ttu-id="2a9aa-575">уникальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="2a9aa-575">unique identity number</span></span>
  
<span data-ttu-id="2a9aa-576">натионалидно #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-576">nationalidno#</span></span>
  
<span data-ttu-id="2a9aa-577">уникальным #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-577">uniqueid#</span></span>
  
<span data-ttu-id="2a9aa-578">DNI #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-578">dni#</span></span>
  
<span data-ttu-id="2a9aa-579">натионалид #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-579">nationalid#</span></span>
  
<span data-ttu-id="2a9aa-580">ние #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-580">nie#</span></span>
  
<span data-ttu-id="2a9aa-581">ние</span><span class="sxs-lookup"><span data-stu-id="2a9aa-581">nie</span></span>
  
<span data-ttu-id="2a9aa-582">ниенúмеро #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-582">nienúmero#</span></span>
  
<span data-ttu-id="2a9aa-583">ние нúмеро</span><span class="sxs-lookup"><span data-stu-id="2a9aa-583">nie número</span></span>
  
<span data-ttu-id="2a9aa-584">документо наЦионал де ИДЕНТИДАД</span><span class="sxs-lookup"><span data-stu-id="2a9aa-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="2a9aa-585">ИДЕНТИДАД úнико</span><span class="sxs-lookup"><span data-stu-id="2a9aa-585">identidad único</span></span>
  
<span data-ttu-id="2a9aa-586">нúмеро наЦионал ИДЕНТИДАД</span><span class="sxs-lookup"><span data-stu-id="2a9aa-586">número nacional identidad</span></span>
  
<span data-ttu-id="2a9aa-587">DNI нúмеро</span><span class="sxs-lookup"><span data-stu-id="2a9aa-587">dni número</span></span>
  
<span data-ttu-id="2a9aa-588">днинúмеро #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-588">dninúmero#</span></span>
  
<span data-ttu-id="2a9aa-589">идентидадúнико #</span><span class="sxs-lookup"><span data-stu-id="2a9aa-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="2a9aa-590">Швеция</span><span class="sxs-lookup"><span data-stu-id="2a9aa-590">Sweden</span></span>

<span data-ttu-id="2a9aa-591">Для получения дополнительных сведений обратитесь к разделу "Швеции National ID", в котором [ищутся типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="2a9aa-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2a9aa-592">См. также</span><span class="sxs-lookup"><span data-stu-id="2a9aa-592">See also</span></span>

[<span data-ttu-id="2a9aa-593">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="2a9aa-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

