---
title: Что позволяют искать типы конфиденциальной информации
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Защита от потери данных (DLP) в центре безопасности &amp; Office 365 включает в себя 80 типов конфиденциальной информации, готовых к использованию в политиках защиты от потери данных. В этой статье перечислены все эти типы конфиденциальной информации и показано, каким именно образом политика защиты от потери данных выявляет каждый тип.
ms.openlocfilehash: 820bab0a128f952cf5d96208f5d561f4994bd859
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090842"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="36494-104">Что позволяют искать типы конфиденциальной информации</span><span class="sxs-lookup"><span data-stu-id="36494-104">What the sensitive information types look for</span></span>

<span data-ttu-id="36494-105">Защита от потери данных (DLP) в центре безопасности &amp; Office 365 содержит множество типов конфиденциальной информации, готовых к использованию в политиках защиты от потери данных.</span><span class="sxs-lookup"><span data-stu-id="36494-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="36494-106">В этой статье перечислены все эти типы конфиденциальной информации и показано, каким именно образом политика защиты от потери данных выявляет каждый тип.</span><span class="sxs-lookup"><span data-stu-id="36494-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="36494-107">Тип конфиденциальной информации определяется шаблоном, который можно идентифицировать регулярным выражением или функцией.</span><span class="sxs-lookup"><span data-stu-id="36494-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="36494-108">Кроме того, для идентификации типа конфиденциальной информации могут использоваться подкрепляющие доказательства, такие как ключевые слова и контрольные суммы.</span><span class="sxs-lookup"><span data-stu-id="36494-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="36494-109">Уровень вероятности и расположение слов и знаков также используются в процессе оценки.</span><span class="sxs-lookup"><span data-stu-id="36494-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="36494-110">Код банка ABA</span><span class="sxs-lookup"><span data-stu-id="36494-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-111">Format</span><span class="sxs-lookup"><span data-stu-id="36494-111">Format</span></span>

<span data-ttu-id="36494-112">9 цифр в виде форматированного или неформатированного шаблона.</span><span class="sxs-lookup"><span data-stu-id="36494-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-113">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-113">Pattern</span></span>

<span data-ttu-id="36494-114">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="36494-114">Formatted:</span></span>
- <span data-ttu-id="36494-115">четыре цифры, начиная с 0, 1, 2, 3, 6, 7 или 8;</span><span class="sxs-lookup"><span data-stu-id="36494-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="36494-116">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-116">A hyphen</span></span>
- <span data-ttu-id="36494-117">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-117">Four digits</span></span>
- <span data-ttu-id="36494-118">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-118">A hyphen</span></span>
- <span data-ttu-id="36494-119">цифра.</span><span class="sxs-lookup"><span data-stu-id="36494-119">A digit</span></span>

<span data-ttu-id="36494-120">Неформатированные: 9 последовательных цифр, начиная с 0, 1, 2, 3, 6, 7 или 8.</span><span class="sxs-lookup"><span data-stu-id="36494-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="36494-121">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-121">Checksum</span></span>

<span data-ttu-id="36494-122">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-123">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-123">Definition</span></span>

<span data-ttu-id="36494-124">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-125">функция Func_aba_routing находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-126">находится ключевое слово из Keyword_ABA_Routing.</span><span class="sxs-lookup"><span data-stu-id="36494-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="36494-127">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="36494-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="36494-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="36494-129">код банка ABA</span><span class="sxs-lookup"><span data-stu-id="36494-129">aba</span></span>
- <span data-ttu-id="36494-130">aba#</span><span class="sxs-lookup"><span data-stu-id="36494-130">aba #</span></span>
- <span data-ttu-id="36494-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="36494-131">aba routing #</span></span>
- <span data-ttu-id="36494-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="36494-132">aba routing number</span></span>
- <span data-ttu-id="36494-133">код банка ABA #</span><span class="sxs-lookup"><span data-stu-id="36494-133">aba#</span></span>
- <span data-ttu-id="36494-134">абараутинг #</span><span class="sxs-lookup"><span data-stu-id="36494-134">abarouting#</span></span>
- <span data-ttu-id="36494-135">aba number</span><span class="sxs-lookup"><span data-stu-id="36494-135">aba number</span></span>
- <span data-ttu-id="36494-136">абараутингнумбер</span><span class="sxs-lookup"><span data-stu-id="36494-136">abaroutingnumber</span></span>
- <span data-ttu-id="36494-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="36494-137">american bank association routing #</span></span>
- <span data-ttu-id="36494-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="36494-138">american bank association routing number</span></span>
- <span data-ttu-id="36494-139">американбанкассоЦиатионраутинг #</span><span class="sxs-lookup"><span data-stu-id="36494-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="36494-140">американбанкассоЦиатионраутингнумбер</span><span class="sxs-lookup"><span data-stu-id="36494-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="36494-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="36494-141">bank routing number</span></span>
- <span data-ttu-id="36494-142">банкраутинг #</span><span class="sxs-lookup"><span data-stu-id="36494-142">bankrouting#</span></span>
- <span data-ttu-id="36494-143">банкраутингнумбер</span><span class="sxs-lookup"><span data-stu-id="36494-143">bankroutingnumber</span></span>
- <span data-ttu-id="36494-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="36494-144">routing transit number</span></span>
- <span data-ttu-id="36494-145">ртн</span><span class="sxs-lookup"><span data-stu-id="36494-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="36494-146">Номер внутреннего удостоверения личности для Аргентины (DNI)</span><span class="sxs-lookup"><span data-stu-id="36494-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-147">Format</span><span class="sxs-lookup"><span data-stu-id="36494-147">Format</span></span>

<span data-ttu-id="36494-148">Восемь цифр, разделенных точками.</span><span class="sxs-lookup"><span data-stu-id="36494-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-149">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-149">Pattern</span></span>

<span data-ttu-id="36494-150">Восемь цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-150">Eight digits:</span></span>
- <span data-ttu-id="36494-151">две цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-151">Two digits</span></span>
- <span data-ttu-id="36494-152">точка;</span><span class="sxs-lookup"><span data-stu-id="36494-152">A period</span></span>
- <span data-ttu-id="36494-153">три цифры; </span><span class="sxs-lookup"><span data-stu-id="36494-153">Three digits</span></span>
- <span data-ttu-id="36494-154">точка;</span><span class="sxs-lookup"><span data-stu-id="36494-154">A period</span></span>
- <span data-ttu-id="36494-155">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-156">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-156">Checksum</span></span>

<span data-ttu-id="36494-157">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-158">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-158">Definition</span></span>

<span data-ttu-id="36494-159">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-160">регулярное выражение Regex_argentina_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-161">находится ключевое слово из Keyword_argentina_national_id.</span><span class="sxs-lookup"><span data-stu-id="36494-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-162">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="36494-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="36494-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="36494-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="36494-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="36494-165">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="36494-165">Identity</span></span> 
- <span data-ttu-id="36494-166">Идентификация национальной идентификационной карточки</span><span class="sxs-lookup"><span data-stu-id="36494-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="36494-167">DNI</span><span class="sxs-lookup"><span data-stu-id="36494-167">DNI</span></span> 
- <span data-ttu-id="36494-168">Национальная реестр пользователей NIC</span><span class="sxs-lookup"><span data-stu-id="36494-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="36494-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="36494-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="36494-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="36494-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="36494-171">идентидад</span><span class="sxs-lookup"><span data-stu-id="36494-171">Identidad</span></span> 
- <span data-ttu-id="36494-172">идентификаЦиóн</span><span class="sxs-lookup"><span data-stu-id="36494-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="36494-173">Номер банковского счета для Австралии</span><span class="sxs-lookup"><span data-stu-id="36494-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-174">Format</span><span class="sxs-lookup"><span data-stu-id="36494-174">Format</span></span>

<span data-ttu-id="36494-175">6–10 цифр с номером филиала банка в штате или без него.</span><span class="sxs-lookup"><span data-stu-id="36494-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-176">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-176">Pattern</span></span>

<span data-ttu-id="36494-177">Номер счета состоит из 6–10 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="36494-178">Номер филиала государственного банка Австралии</span><span class="sxs-lookup"><span data-stu-id="36494-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="36494-179">три цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-179">Three digits</span></span> 
- <span data-ttu-id="36494-180">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-180">A hyphen</span></span> 
- <span data-ttu-id="36494-181">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-182">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-182">Checksum</span></span>

<span data-ttu-id="36494-183">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-184">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-184">Definition</span></span>

<span data-ttu-id="36494-185">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-186">регулярное выражение Regex_australia_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="36494-187">находится ключевое слово из Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="36494-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="36494-188">регулярное выражение Regex_australia_bank_account_number_bsb находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="36494-189">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-190">регулярное выражение Regex_australia_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="36494-191">находится ключевое слово из Keyword_australia_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="36494-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-192">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="36494-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="36494-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="36494-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="36494-194">swift bank code</span></span>
- <span data-ttu-id="36494-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="36494-195">correspondent bank</span></span>
- <span data-ttu-id="36494-196">base currency</span><span class="sxs-lookup"><span data-stu-id="36494-196">base currency</span></span>
- <span data-ttu-id="36494-197">usa account</span><span class="sxs-lookup"><span data-stu-id="36494-197">usa account</span></span>
- <span data-ttu-id="36494-198">holder address</span><span class="sxs-lookup"><span data-stu-id="36494-198">holder address</span></span>
- <span data-ttu-id="36494-199">bank address</span><span class="sxs-lookup"><span data-stu-id="36494-199">bank address</span></span>
- <span data-ttu-id="36494-200">information account</span><span class="sxs-lookup"><span data-stu-id="36494-200">information account</span></span>
- <span data-ttu-id="36494-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="36494-201">fund transfers</span></span>
- <span data-ttu-id="36494-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="36494-202">bank charges</span></span>
- <span data-ttu-id="36494-203">bank details</span><span class="sxs-lookup"><span data-stu-id="36494-203">bank details</span></span>
- <span data-ttu-id="36494-204">banking information</span><span class="sxs-lookup"><span data-stu-id="36494-204">banking information</span></span>
- <span data-ttu-id="36494-205">full names</span><span class="sxs-lookup"><span data-stu-id="36494-205">full names</span></span>
- <span data-ttu-id="36494-206">иаеа</span><span class="sxs-lookup"><span data-stu-id="36494-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="36494-207">Номер водительского удостоверения для Австралии</span><span class="sxs-lookup"><span data-stu-id="36494-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-208">Format</span><span class="sxs-lookup"><span data-stu-id="36494-208">Format</span></span>

<span data-ttu-id="36494-209">Девять букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-210">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-210">Pattern</span></span>

<span data-ttu-id="36494-211">Девять букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="36494-212">две цифры или буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="36494-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="36494-213">две цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-213">Two digits</span></span> 
- <span data-ttu-id="36494-214">пять цифр или букв (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="36494-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="36494-215">OR</span><span class="sxs-lookup"><span data-stu-id="36494-215">OR</span></span>

- <span data-ttu-id="36494-216">1–2 дополнительные буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="36494-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="36494-217">4–9 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-217">4-9 digits</span></span>

<span data-ttu-id="36494-218">OR</span><span class="sxs-lookup"><span data-stu-id="36494-218">OR</span></span>

- <span data-ttu-id="36494-219">девять цифр или букв (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="36494-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-220">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-220">Checksum</span></span>

<span data-ttu-id="36494-221">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-222">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-222">Definition</span></span>

<span data-ttu-id="36494-223">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-224">регулярное выражение Regex_australia_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-225">находится ключевое слово из Keyword_australia_drivers_license_number;</span><span class="sxs-lookup"><span data-stu-id="36494-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="36494-226">ни одно ключевое слово из Keyword_australia_drivers_license_number_exclusions не находится.</span><span class="sxs-lookup"><span data-stu-id="36494-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-227">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="36494-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="36494-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="36494-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="36494-229">international driving permits</span></span>
- <span data-ttu-id="36494-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="36494-230">australian automobile association</span></span>
- <span data-ttu-id="36494-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="36494-231">international driving permit</span></span>
- <span data-ttu-id="36494-232">дриверлиценце</span><span class="sxs-lookup"><span data-stu-id="36494-232">DriverLicence</span></span>
- <span data-ttu-id="36494-233">дриверлиценцес</span><span class="sxs-lookup"><span data-stu-id="36494-233">DriverLicences</span></span>
- <span data-ttu-id="36494-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="36494-234">Driver Lic</span></span>
- <span data-ttu-id="36494-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="36494-235">Driver Licence</span></span>
- <span data-ttu-id="36494-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="36494-236">Driver Licences</span></span>
- <span data-ttu-id="36494-237">дриверслик</span><span class="sxs-lookup"><span data-stu-id="36494-237">DriversLic</span></span>
- <span data-ttu-id="36494-238">дриверслиценце</span><span class="sxs-lookup"><span data-stu-id="36494-238">DriversLicence</span></span>
- <span data-ttu-id="36494-239">дриверслиценцес</span><span class="sxs-lookup"><span data-stu-id="36494-239">DriversLicences</span></span>
- <span data-ttu-id="36494-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="36494-240">Drivers Lic</span></span>
- <span data-ttu-id="36494-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="36494-241">Drivers Lics</span></span>
- <span data-ttu-id="36494-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="36494-242">Drivers Licence</span></span>
- <span data-ttu-id="36494-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="36494-243">Drivers Licences</span></span>
- <span data-ttu-id="36494-244">Driver ' LIC</span><span class="sxs-lookup"><span data-stu-id="36494-244">Driver'Lic</span></span>
- <span data-ttu-id="36494-245">Driver ' LICS</span><span class="sxs-lookup"><span data-stu-id="36494-245">Driver'Lics</span></span>
- <span data-ttu-id="36494-246">Driver ' Licence</span><span class="sxs-lookup"><span data-stu-id="36494-246">Driver'Licence</span></span>
- <span data-ttu-id="36494-247">Driver ' Licences</span><span class="sxs-lookup"><span data-stu-id="36494-247">Driver'Licences</span></span>
- <span data-ttu-id="36494-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="36494-248">Driver' Lic</span></span>
- <span data-ttu-id="36494-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="36494-249">Driver' Lics</span></span>
- <span data-ttu-id="36494-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="36494-250">Driver' Licence</span></span>
- <span data-ttu-id="36494-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="36494-251">Driver' Licences</span></span>
- <span data-ttu-id="36494-252">дривер'слик</span><span class="sxs-lookup"><span data-stu-id="36494-252">Driver'sLic</span></span>
- <span data-ttu-id="36494-253">дривер'сликс</span><span class="sxs-lookup"><span data-stu-id="36494-253">Driver'sLics</span></span>
- <span data-ttu-id="36494-254">дривер'слиценце</span><span class="sxs-lookup"><span data-stu-id="36494-254">Driver'sLicence</span></span>
- <span data-ttu-id="36494-255">дривер'слиценцес</span><span class="sxs-lookup"><span data-stu-id="36494-255">Driver'sLicences</span></span>
- <span data-ttu-id="36494-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="36494-256">Driver's Lic</span></span>
- <span data-ttu-id="36494-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="36494-257">Driver's Lics</span></span>
- <span data-ttu-id="36494-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="36494-258">Driver's Licence</span></span>
- <span data-ttu-id="36494-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="36494-259">Driver's Licences</span></span>
- <span data-ttu-id="36494-260">дриверлик #</span><span class="sxs-lookup"><span data-stu-id="36494-260">DriverLic#</span></span>
- <span data-ttu-id="36494-261">дриверликс #</span><span class="sxs-lookup"><span data-stu-id="36494-261">DriverLics#</span></span>
- <span data-ttu-id="36494-262">дриверлиценце #</span><span class="sxs-lookup"><span data-stu-id="36494-262">DriverLicence#</span></span>
- <span data-ttu-id="36494-263">дриверлиценцес #</span><span class="sxs-lookup"><span data-stu-id="36494-263">DriverLicences#</span></span>
- <span data-ttu-id="36494-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="36494-264">Driver Lic#</span></span>
- <span data-ttu-id="36494-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="36494-265">Driver Lics#</span></span>
- <span data-ttu-id="36494-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="36494-266">Driver Licence#</span></span>
- <span data-ttu-id="36494-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="36494-267">Driver Licences#</span></span>
- <span data-ttu-id="36494-268">дриверслик #</span><span class="sxs-lookup"><span data-stu-id="36494-268">DriversLic#</span></span>
- <span data-ttu-id="36494-269">дриверсликс #</span><span class="sxs-lookup"><span data-stu-id="36494-269">DriversLics#</span></span>
- <span data-ttu-id="36494-270">дриверслиценце #</span><span class="sxs-lookup"><span data-stu-id="36494-270">DriversLicence#</span></span>
- <span data-ttu-id="36494-271">дриверслиценцес #</span><span class="sxs-lookup"><span data-stu-id="36494-271">DriversLicences#</span></span>
- <span data-ttu-id="36494-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="36494-272">Drivers Lic#</span></span>
- <span data-ttu-id="36494-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="36494-273">Drivers Lics#</span></span>
- <span data-ttu-id="36494-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="36494-274">Drivers Licence#</span></span>
- <span data-ttu-id="36494-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="36494-275">Drivers Licences#</span></span>
- <span data-ttu-id="36494-276">Driver ' LIC #</span><span class="sxs-lookup"><span data-stu-id="36494-276">Driver'Lic#</span></span>
- <span data-ttu-id="36494-277">Driver ' LICS #</span><span class="sxs-lookup"><span data-stu-id="36494-277">Driver'Lics#</span></span>
- <span data-ttu-id="36494-278">Driver ' Licence #</span><span class="sxs-lookup"><span data-stu-id="36494-278">Driver'Licence#</span></span>
- <span data-ttu-id="36494-279">Driver ' Licences #</span><span class="sxs-lookup"><span data-stu-id="36494-279">Driver'Licences#</span></span>
- <span data-ttu-id="36494-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="36494-280">Driver' Lic#</span></span>
- <span data-ttu-id="36494-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="36494-281">Driver' Lics#</span></span>
- <span data-ttu-id="36494-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="36494-282">Driver' Licence#</span></span>
- <span data-ttu-id="36494-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="36494-283">Driver' Licences#</span></span>
- <span data-ttu-id="36494-284">дривер'слик #</span><span class="sxs-lookup"><span data-stu-id="36494-284">Driver'sLic#</span></span>
- <span data-ttu-id="36494-285">дривер'сликс #</span><span class="sxs-lookup"><span data-stu-id="36494-285">Driver'sLics#</span></span>
- <span data-ttu-id="36494-286">дривер'слиценце #</span><span class="sxs-lookup"><span data-stu-id="36494-286">Driver'sLicence#</span></span>
- <span data-ttu-id="36494-287">дривер'слиценцес #</span><span class="sxs-lookup"><span data-stu-id="36494-287">Driver'sLicences#</span></span>
- <span data-ttu-id="36494-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="36494-288">Driver's Lic#</span></span>
- <span data-ttu-id="36494-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="36494-289">Driver's Lics#</span></span>
- <span data-ttu-id="36494-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="36494-290">Driver's Licence#</span></span>
- <span data-ttu-id="36494-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="36494-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="36494-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="36494-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="36494-293">AAA</span><span class="sxs-lookup"><span data-stu-id="36494-293">aaa</span></span>
- <span data-ttu-id="36494-294">дриверлиценсе</span><span class="sxs-lookup"><span data-stu-id="36494-294">DriverLicense</span></span>
- <span data-ttu-id="36494-295">дриверлиценсес</span><span class="sxs-lookup"><span data-stu-id="36494-295">DriverLicenses</span></span>
- <span data-ttu-id="36494-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="36494-296">Driver License</span></span>
- <span data-ttu-id="36494-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-297">Driver Licenses</span></span>
- <span data-ttu-id="36494-298">дриверслиценсе</span><span class="sxs-lookup"><span data-stu-id="36494-298">DriversLicense</span></span>
- <span data-ttu-id="36494-299">дриверслиценсес</span><span class="sxs-lookup"><span data-stu-id="36494-299">DriversLicenses</span></span>
- <span data-ttu-id="36494-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="36494-300">Drivers License</span></span>
- <span data-ttu-id="36494-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-301">Drivers Licenses</span></span>
- <span data-ttu-id="36494-302">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="36494-302">Driver'License</span></span>
- <span data-ttu-id="36494-303">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-303">Driver'Licenses</span></span>
- <span data-ttu-id="36494-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="36494-304">Driver' License</span></span>
- <span data-ttu-id="36494-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-305">Driver' Licenses</span></span>
- <span data-ttu-id="36494-306">дривер'слиценсе</span><span class="sxs-lookup"><span data-stu-id="36494-306">Driver'sLicense</span></span>
- <span data-ttu-id="36494-307">дривер'слиценсес</span><span class="sxs-lookup"><span data-stu-id="36494-307">Driver'sLicenses</span></span>
- <span data-ttu-id="36494-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="36494-308">Driver's License</span></span>
- <span data-ttu-id="36494-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-309">Driver's Licenses</span></span>
- <span data-ttu-id="36494-310">дриверлиценсе #</span><span class="sxs-lookup"><span data-stu-id="36494-310">DriverLicense#</span></span>
- <span data-ttu-id="36494-311">дриверлиценсес #</span><span class="sxs-lookup"><span data-stu-id="36494-311">DriverLicenses#</span></span>
- <span data-ttu-id="36494-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="36494-312">Driver License#</span></span>
- <span data-ttu-id="36494-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="36494-313">Driver Licenses#</span></span>
- <span data-ttu-id="36494-314">дриверслиценсе #</span><span class="sxs-lookup"><span data-stu-id="36494-314">DriversLicense#</span></span>
- <span data-ttu-id="36494-315">дриверслиценсес #</span><span class="sxs-lookup"><span data-stu-id="36494-315">DriversLicenses#</span></span>
- <span data-ttu-id="36494-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="36494-316">Drivers License#</span></span>
- <span data-ttu-id="36494-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="36494-317">Drivers Licenses#</span></span>
- <span data-ttu-id="36494-318">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="36494-318">Driver'License#</span></span>
- <span data-ttu-id="36494-319">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="36494-319">Driver'Licenses#</span></span>
- <span data-ttu-id="36494-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="36494-320">Driver' License#</span></span>
- <span data-ttu-id="36494-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="36494-321">Driver' Licenses#</span></span>
- <span data-ttu-id="36494-322">дривер'слиценсе #</span><span class="sxs-lookup"><span data-stu-id="36494-322">Driver'sLicense#</span></span>
- <span data-ttu-id="36494-323">дривер'слиценсес #</span><span class="sxs-lookup"><span data-stu-id="36494-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="36494-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="36494-324">Driver's License#</span></span>
- <span data-ttu-id="36494-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="36494-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="36494-326">Номер карты медицинского страхования для Австралии</span><span class="sxs-lookup"><span data-stu-id="36494-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-327">Format</span><span class="sxs-lookup"><span data-stu-id="36494-327">Format</span></span>

<span data-ttu-id="36494-328">10–11 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-329">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-329">Pattern</span></span>

<span data-ttu-id="36494-330">10–11 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-330">10-11 digits:</span></span>
- <span data-ttu-id="36494-331">Первая цифра находится в диапазоне 2–6.</span><span class="sxs-lookup"><span data-stu-id="36494-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="36494-332">Девятая цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="36494-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="36494-333">Десятая цифра — цифра серии.</span><span class="sxs-lookup"><span data-stu-id="36494-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="36494-334">Одиннадцатая цифра (необязательно) — индивидуальный номер.</span><span class="sxs-lookup"><span data-stu-id="36494-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-335">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-335">Checksum</span></span>

<span data-ttu-id="36494-336">Да</span><span class="sxs-lookup"><span data-stu-id="36494-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-337">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-337">Definition</span></span>

<span data-ttu-id="36494-338">Политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-339">функция Func_australian_medical_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-340">находится ключевое слово из Keyword_Australia_Medical_Account_Number;</span><span class="sxs-lookup"><span data-stu-id="36494-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="36494-341">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-341">The checksum passes.</span></span>

<span data-ttu-id="36494-342">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-343">функция Func_australian_medical_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-344">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-344">The checksum passes.</span></span>

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-345">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="36494-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="36494-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="36494-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="36494-347">bank account details</span></span>
- <span data-ttu-id="36494-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="36494-348">medicare payments</span></span>
- <span data-ttu-id="36494-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="36494-349">mortgage account</span></span>
- <span data-ttu-id="36494-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="36494-350">bank payments</span></span>
- <span data-ttu-id="36494-351">information branch</span><span class="sxs-lookup"><span data-stu-id="36494-351">information branch</span></span>
- <span data-ttu-id="36494-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="36494-352">credit card loan</span></span>
- <span data-ttu-id="36494-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="36494-353">department of human services</span></span>
- <span data-ttu-id="36494-354">local service</span><span class="sxs-lookup"><span data-stu-id="36494-354">local service</span></span>
- <span data-ttu-id="36494-355">медикаре</span><span class="sxs-lookup"><span data-stu-id="36494-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="36494-356">Номер паспорта гражданина Австралии</span><span class="sxs-lookup"><span data-stu-id="36494-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-357">Format</span><span class="sxs-lookup"><span data-stu-id="36494-357">Format</span></span>

<span data-ttu-id="36494-358">Буква, за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-359">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-359">Pattern</span></span>

<span data-ttu-id="36494-360">Буква (без учета регистра), за которой следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-361">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-361">Checksum</span></span>

<span data-ttu-id="36494-362">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-363">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-363">Definition</span></span>

<span data-ttu-id="36494-364">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-365">регулярное выражение Regex_australia_passport_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-366">Найдено ключевое слово из Keyword_passport или Keyword_australia_passport_number.</span><span class="sxs-lookup"><span data-stu-id="36494-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a><span data-ttu-id="36494-367">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="36494-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="36494-368">Keyword_passport</span></span>

- <span data-ttu-id="36494-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="36494-369">Passport Number</span></span>
- <span data-ttu-id="36494-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="36494-370">Passport No</span></span>
- <span data-ttu-id="36494-371">Passport#</span><span class="sxs-lookup"><span data-stu-id="36494-371">Passport #</span></span>
- <span data-ttu-id="36494-372">Службу #</span><span class="sxs-lookup"><span data-stu-id="36494-372">Passport#</span></span>
- <span data-ttu-id="36494-373">пасспортид</span><span class="sxs-lookup"><span data-stu-id="36494-373">PassportID</span></span>
- <span data-ttu-id="36494-374">пасспортно</span><span class="sxs-lookup"><span data-stu-id="36494-374">Passportno</span></span>
- <span data-ttu-id="36494-375">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="36494-375">passportnumber</span></span>
- <span data-ttu-id="36494-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="36494-376">パスポート</span></span>
- <span data-ttu-id="36494-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="36494-377">パスポート番号</span></span>
- <span data-ttu-id="36494-378">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="36494-378">パスポートのNum</span></span>
- <span data-ttu-id="36494-379">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="36494-379">パスポート ＃</span></span> 
- <span data-ttu-id="36494-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="36494-380">Numéro de passeport</span></span>
- <span data-ttu-id="36494-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="36494-381">Passeport n °</span></span>
- <span data-ttu-id="36494-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="36494-382">Passeport Non</span></span>
- <span data-ttu-id="36494-383">Passeport#</span><span class="sxs-lookup"><span data-stu-id="36494-383">Passeport #</span></span>
- <span data-ttu-id="36494-384">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="36494-384">Passeport#</span></span>
- <span data-ttu-id="36494-385">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="36494-385">PasseportNon</span></span>
- <span data-ttu-id="36494-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="36494-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="36494-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="36494-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="36494-388">службу</span><span class="sxs-lookup"><span data-stu-id="36494-388">passport</span></span>
- <span data-ttu-id="36494-389">passport details</span><span class="sxs-lookup"><span data-stu-id="36494-389">passport details</span></span>
- <span data-ttu-id="36494-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="36494-390">immigration and citizenship</span></span>
- <span data-ttu-id="36494-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="36494-391">commonwealth of australia</span></span>
- <span data-ttu-id="36494-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="36494-392">department of immigration</span></span>
- <span data-ttu-id="36494-393">residential address</span><span class="sxs-lookup"><span data-stu-id="36494-393">residential address</span></span>
- <span data-ttu-id="36494-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="36494-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="36494-395">Visa</span><span class="sxs-lookup"><span data-stu-id="36494-395">visa</span></span>
- <span data-ttu-id="36494-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="36494-396">national identity card</span></span>
- <span data-ttu-id="36494-397">passport number</span><span class="sxs-lookup"><span data-stu-id="36494-397">passport number</span></span>
- <span data-ttu-id="36494-398">travel document</span><span class="sxs-lookup"><span data-stu-id="36494-398">travel document</span></span>
- <span data-ttu-id="36494-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="36494-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="36494-400">Номер налогоплательщика для Австралии</span><span class="sxs-lookup"><span data-stu-id="36494-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-401">Format</span><span class="sxs-lookup"><span data-stu-id="36494-401">Format</span></span>

<span data-ttu-id="36494-402">8–9 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-403">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-403">Pattern</span></span>

<span data-ttu-id="36494-404">8–9 цифр, которые обычно разделены пробелами указанным ниже образом.</span><span class="sxs-lookup"><span data-stu-id="36494-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="36494-405">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-405">Three digits</span></span> 
- <span data-ttu-id="36494-406">Необязательный пробел</span><span class="sxs-lookup"><span data-stu-id="36494-406">An optional space</span></span> 
- <span data-ttu-id="36494-407">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-407">Three digits</span></span> 
- <span data-ttu-id="36494-408">Необязательный пробел</span><span class="sxs-lookup"><span data-stu-id="36494-408">An optional space</span></span> 
- <span data-ttu-id="36494-409">2–3 цифры, причем последняя цифра — контрольная</span><span class="sxs-lookup"><span data-stu-id="36494-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-410">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-410">Checksum</span></span>

<span data-ttu-id="36494-411">Да</span><span class="sxs-lookup"><span data-stu-id="36494-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-412">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-412">Definition</span></span>

<span data-ttu-id="36494-413">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-414">функция Func_australian_tax_file_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-415">ни одно ключевое слово из Keyword_Australia_Tax_File_Number или Keyword_number_exclusions не найдено;</span><span class="sxs-lookup"><span data-stu-id="36494-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="36494-416">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-416">The checksum passes.</span></span>

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-417">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="36494-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="36494-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="36494-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="36494-419">australian business number</span></span>
- <span data-ttu-id="36494-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="36494-420">marginal tax rate</span></span>
- <span data-ttu-id="36494-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="36494-421">medicare levy</span></span>
- <span data-ttu-id="36494-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="36494-422">portfolio number</span></span>
- <span data-ttu-id="36494-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="36494-423">service veterans</span></span>
- <span data-ttu-id="36494-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="36494-424">withholding tax</span></span>
- <span data-ttu-id="36494-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="36494-425">individual tax return</span></span>
- <span data-ttu-id="36494-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="36494-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="36494-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="36494-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="36494-428">00000001</span><span class="sxs-lookup"><span data-stu-id="36494-428">00000000</span></span>
- <span data-ttu-id="36494-429">11111111</span><span class="sxs-lookup"><span data-stu-id="36494-429">11111111</span></span>
- <span data-ttu-id="36494-430">22222222</span><span class="sxs-lookup"><span data-stu-id="36494-430">22222222</span></span>
- <span data-ttu-id="36494-431">33333333</span><span class="sxs-lookup"><span data-stu-id="36494-431">33333333</span></span>
- <span data-ttu-id="36494-432">44444444</span><span class="sxs-lookup"><span data-stu-id="36494-432">44444444</span></span>
- <span data-ttu-id="36494-433">55555555</span><span class="sxs-lookup"><span data-stu-id="36494-433">55555555</span></span>
- <span data-ttu-id="36494-434">66666666</span><span class="sxs-lookup"><span data-stu-id="36494-434">66666666</span></span>
- <span data-ttu-id="36494-435">77777777</span><span class="sxs-lookup"><span data-stu-id="36494-435">77777777</span></span>
- <span data-ttu-id="36494-436">88888888</span><span class="sxs-lookup"><span data-stu-id="36494-436">88888888</span></span>
- <span data-ttu-id="36494-437">99999999</span><span class="sxs-lookup"><span data-stu-id="36494-437">99999999</span></span>
- <span data-ttu-id="36494-438">000000000</span><span class="sxs-lookup"><span data-stu-id="36494-438">000000000</span></span>
- <span data-ttu-id="36494-439">111111111</span><span class="sxs-lookup"><span data-stu-id="36494-439">111111111</span></span>
- <span data-ttu-id="36494-440">222222222</span><span class="sxs-lookup"><span data-stu-id="36494-440">222222222</span></span>
- <span data-ttu-id="36494-441">333333333</span><span class="sxs-lookup"><span data-stu-id="36494-441">333333333</span></span>
- <span data-ttu-id="36494-442">444444444</span><span class="sxs-lookup"><span data-stu-id="36494-442">444444444</span></span>
- <span data-ttu-id="36494-443">555555555</span><span class="sxs-lookup"><span data-stu-id="36494-443">555555555</span></span>
- <span data-ttu-id="36494-444">666666666</span><span class="sxs-lookup"><span data-stu-id="36494-444">666666666</span></span>
- <span data-ttu-id="36494-445">777777777</span><span class="sxs-lookup"><span data-stu-id="36494-445">777777777</span></span>
- <span data-ttu-id="36494-446">888888888</span><span class="sxs-lookup"><span data-stu-id="36494-446">888888888</span></span>
- <span data-ttu-id="36494-447">999999999</span><span class="sxs-lookup"><span data-stu-id="36494-447">999999999</span></span>
- <span data-ttu-id="36494-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="36494-448">0000000000</span></span>
- <span data-ttu-id="36494-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="36494-449">1111111111</span></span>
- <span data-ttu-id="36494-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="36494-450">2222222222</span></span>
- <span data-ttu-id="36494-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="36494-451">3333333333</span></span>
- <span data-ttu-id="36494-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="36494-452">4444444444</span></span>
- <span data-ttu-id="36494-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="36494-453">5555555555</span></span>
- <span data-ttu-id="36494-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="36494-454">6666666666</span></span>
- <span data-ttu-id="36494-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="36494-455">7777777777</span></span>
- <span data-ttu-id="36494-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="36494-456">8888888888</span></span>
- <span data-ttu-id="36494-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="36494-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="36494-458">Ключ проверки подлинности Azure DocumentDB</span><span class="sxs-lookup"><span data-stu-id="36494-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="36494-459">Format</span><span class="sxs-lookup"><span data-stu-id="36494-459">Format</span></span>

<span data-ttu-id="36494-460">Строка "DocumentDb", за которой следуют символы и строки, описанные в приведенном ниже шаблоне.</span><span class="sxs-lookup"><span data-stu-id="36494-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-461">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-461">Pattern</span></span>

- <span data-ttu-id="36494-462">Строка "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="36494-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="36494-463">Любая комбинация из 3-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="36494-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="36494-464">Символ "больше" (>), знак равенства (=), кавычки (") или апостроф (')</span><span class="sxs-lookup"><span data-stu-id="36494-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="36494-465">Любая комбинация 86 строчных или прописных букв, цифр, символов косой черты (/) или знака плюса (+).</span><span class="sxs-lookup"><span data-stu-id="36494-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="36494-466">Два знака равенства (=)</span><span class="sxs-lookup"><span data-stu-id="36494-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-467">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-467">Checksum</span></span>

<span data-ttu-id="36494-468">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-469">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-469">Definition</span></span>

<span data-ttu-id="36494-470">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-471">Регулярное выражение CEP_Regex_AzureDocumentDBAuthKey находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-472">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-473">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="36494-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="36494-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="36494-475">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="36494-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="36494-476">компанией</span><span class="sxs-lookup"><span data-stu-id="36494-476">contoso</span></span>
- <span data-ttu-id="36494-477">компании</span><span class="sxs-lookup"><span data-stu-id="36494-477">fabrikam</span></span>
- <span data-ttu-id="36494-478">базу</span><span class="sxs-lookup"><span data-stu-id="36494-478">northwind</span></span>
- <span data-ttu-id="36494-479">песочниц</span><span class="sxs-lookup"><span data-stu-id="36494-479">sandbox</span></span>
- <span data-ttu-id="36494-480">онебокс</span><span class="sxs-lookup"><span data-stu-id="36494-480">onebox</span></span>
- <span data-ttu-id="36494-481">localhost</span><span class="sxs-lookup"><span data-stu-id="36494-481">localhost</span></span>
- <span data-ttu-id="36494-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="36494-482">127.0.0.1</span></span>
- <span data-ttu-id="36494-483">тестакс.</span><span class="sxs-lookup"><span data-stu-id="36494-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="36494-484">порта</span><span class="sxs-lookup"><span data-stu-id="36494-484">com</span></span>
- <span data-ttu-id="36494-485">s — int.</span><span class="sxs-lookup"><span data-stu-id="36494-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="36494-486">команде</span><span class="sxs-lookup"><span data-stu-id="36494-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="36494-487">Строка подключения к базе данных Azure IAAS и строка подключения к SQL Azure</span><span class="sxs-lookup"><span data-stu-id="36494-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="36494-488">Format</span><span class="sxs-lookup"><span data-stu-id="36494-488">Format</span></span>

<span data-ttu-id="36494-489">Строка "Server", "Server" или "Data Source", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строку "клаудапп. Azure".</span><span class="sxs-lookup"><span data-stu-id="36494-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="36494-490">com "или" клаудапп. Azure.</span><span class="sxs-lookup"><span data-stu-id="36494-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="36494-491">NET "или" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="36494-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="36494-492">NET ", а также строку" Password "или" Password "или" pwd ".</span><span class="sxs-lookup"><span data-stu-id="36494-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-493">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-493">Pattern</span></span>

- <span data-ttu-id="36494-494">Строка "Server", "Server" или "Data Source"</span><span class="sxs-lookup"><span data-stu-id="36494-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="36494-495">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-496">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-496">An equal sign (=)</span></span>
- <span data-ttu-id="36494-497">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-498">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="36494-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="36494-499">Строка "клаудапп. Azure.</span><span class="sxs-lookup"><span data-stu-id="36494-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="36494-500">com "," клаудапп. Azure.</span><span class="sxs-lookup"><span data-stu-id="36494-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="36494-501">NET "или" Database. Windows.</span><span class="sxs-lookup"><span data-stu-id="36494-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="36494-502">команде</span><span class="sxs-lookup"><span data-stu-id="36494-502">net"</span></span>
- <span data-ttu-id="36494-503">Любая комбинация из 1-300 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="36494-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="36494-504">Строка "Password", "Password" или "pwd"</span><span class="sxs-lookup"><span data-stu-id="36494-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="36494-505">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-506">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-506">An equal sign (=)</span></span>
- <span data-ttu-id="36494-507">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-508">Один или несколько символов, не отделяющая точку с запятой (;), кавычки (") или апостроф (')</span><span class="sxs-lookup"><span data-stu-id="36494-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="36494-509">Точка с запятой (;), кавычки (") или апостроф (')</span><span class="sxs-lookup"><span data-stu-id="36494-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-510">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-510">Checksum</span></span>

<span data-ttu-id="36494-511">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-512">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-512">Definition</span></span>

<span data-ttu-id="36494-513">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-514">Регулярное выражение CEP_Regex_AzureConnectionString находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-515">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-516">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="36494-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="36494-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="36494-518">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="36494-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="36494-519">компанией</span><span class="sxs-lookup"><span data-stu-id="36494-519">contoso</span></span>
- <span data-ttu-id="36494-520">компании</span><span class="sxs-lookup"><span data-stu-id="36494-520">fabrikam</span></span>
- <span data-ttu-id="36494-521">базу</span><span class="sxs-lookup"><span data-stu-id="36494-521">northwind</span></span>
- <span data-ttu-id="36494-522">песочниц</span><span class="sxs-lookup"><span data-stu-id="36494-522">sandbox</span></span>
- <span data-ttu-id="36494-523">онебокс</span><span class="sxs-lookup"><span data-stu-id="36494-523">onebox</span></span>
- <span data-ttu-id="36494-524">localhost</span><span class="sxs-lookup"><span data-stu-id="36494-524">localhost</span></span>
- <span data-ttu-id="36494-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="36494-525">127.0.0.1</span></span>
- <span data-ttu-id="36494-526">тестакс.</span><span class="sxs-lookup"><span data-stu-id="36494-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="36494-527">порта</span><span class="sxs-lookup"><span data-stu-id="36494-527">com</span></span>
- <span data-ttu-id="36494-528">s — int.</span><span class="sxs-lookup"><span data-stu-id="36494-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="36494-529">команде</span><span class="sxs-lookup"><span data-stu-id="36494-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="36494-530">Строка подключения Azure IoT</span><span class="sxs-lookup"><span data-stu-id="36494-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="36494-531">Format</span><span class="sxs-lookup"><span data-stu-id="36494-531">Format</span></span>

<span data-ttu-id="36494-532">Строка "HostName", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, включая строки "Azure — Devices.</span><span class="sxs-lookup"><span data-stu-id="36494-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="36494-533">NET "и" Шаредакцесскэй ".</span><span class="sxs-lookup"><span data-stu-id="36494-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-534">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-534">Pattern</span></span>

- <span data-ttu-id="36494-535">Строка "HostName"</span><span class="sxs-lookup"><span data-stu-id="36494-535">The string "HostName"</span></span>
- <span data-ttu-id="36494-536">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-537">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-537">An equal sign (=)</span></span>
- <span data-ttu-id="36494-538">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-539">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="36494-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="36494-540">Строка "Azure — Devices.</span><span class="sxs-lookup"><span data-stu-id="36494-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="36494-541">команде</span><span class="sxs-lookup"><span data-stu-id="36494-541">net"</span></span>
- <span data-ttu-id="36494-542">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="36494-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="36494-543">Строка "Шаредакцесскэй"</span><span class="sxs-lookup"><span data-stu-id="36494-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="36494-544">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-545">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-545">An equal sign (=)</span></span>
- <span data-ttu-id="36494-546">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-547">Любая комбинация 43 строчных или прописных букв, цифр, символов косой черты (/) или знака плюса (+).</span><span class="sxs-lookup"><span data-stu-id="36494-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="36494-548">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-549">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-549">Checksum</span></span>

<span data-ttu-id="36494-550">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-551">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-551">Definition</span></span>

<span data-ttu-id="36494-552">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-553">Регулярное выражение CEP_Regex_AzureIoTConnectionString находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-554">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-555">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="36494-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="36494-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="36494-557">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="36494-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="36494-558">компанией</span><span class="sxs-lookup"><span data-stu-id="36494-558">contoso</span></span>
- <span data-ttu-id="36494-559">компании</span><span class="sxs-lookup"><span data-stu-id="36494-559">fabrikam</span></span>
- <span data-ttu-id="36494-560">базу</span><span class="sxs-lookup"><span data-stu-id="36494-560">northwind</span></span>
- <span data-ttu-id="36494-561">песочниц</span><span class="sxs-lookup"><span data-stu-id="36494-561">sandbox</span></span>
- <span data-ttu-id="36494-562">онебокс</span><span class="sxs-lookup"><span data-stu-id="36494-562">onebox</span></span>
- <span data-ttu-id="36494-563">localhost</span><span class="sxs-lookup"><span data-stu-id="36494-563">localhost</span></span>
- <span data-ttu-id="36494-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="36494-564">127.0.0.1</span></span>
- <span data-ttu-id="36494-565">тестакс.</span><span class="sxs-lookup"><span data-stu-id="36494-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="36494-566">порта</span><span class="sxs-lookup"><span data-stu-id="36494-566">com</span></span>
- <span data-ttu-id="36494-567">s — int.</span><span class="sxs-lookup"><span data-stu-id="36494-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="36494-568">команде</span><span class="sxs-lookup"><span data-stu-id="36494-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="36494-569">Пароль для параметра публикации Azure</span><span class="sxs-lookup"><span data-stu-id="36494-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="36494-570">Format</span><span class="sxs-lookup"><span data-stu-id="36494-570">Format</span></span>

<span data-ttu-id="36494-571">Строка "усерпвд =", за которой следует буквенно-цифровая строка.</span><span class="sxs-lookup"><span data-stu-id="36494-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-572">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-572">Pattern</span></span>

- <span data-ttu-id="36494-573">Строка "усерпвд ="</span><span class="sxs-lookup"><span data-stu-id="36494-573">The string "userpwd="</span></span>
- <span data-ttu-id="36494-574">Любая комбинация букв или цифр в нижнем регистре 60</span><span class="sxs-lookup"><span data-stu-id="36494-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="36494-575">Знак кавычек (")</span><span class="sxs-lookup"><span data-stu-id="36494-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-576">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-576">Checksum</span></span>

<span data-ttu-id="36494-577">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-578">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-578">Definition</span></span>

<span data-ttu-id="36494-579">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-580">Регулярное выражение CEP_Regex_AzurePublishSettingPasswords находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-581">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-582">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="36494-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="36494-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="36494-584">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="36494-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="36494-585">компанией</span><span class="sxs-lookup"><span data-stu-id="36494-585">contoso</span></span>
- <span data-ttu-id="36494-586">компании</span><span class="sxs-lookup"><span data-stu-id="36494-586">fabrikam</span></span>
- <span data-ttu-id="36494-587">базу</span><span class="sxs-lookup"><span data-stu-id="36494-587">northwind</span></span>
- <span data-ttu-id="36494-588">песочниц</span><span class="sxs-lookup"><span data-stu-id="36494-588">sandbox</span></span>
- <span data-ttu-id="36494-589">онебокс</span><span class="sxs-lookup"><span data-stu-id="36494-589">onebox</span></span>
- <span data-ttu-id="36494-590">localhost</span><span class="sxs-lookup"><span data-stu-id="36494-590">localhost</span></span>
- <span data-ttu-id="36494-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="36494-591">127.0.0.1</span></span>
- <span data-ttu-id="36494-592">тестакс.</span><span class="sxs-lookup"><span data-stu-id="36494-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="36494-593">порта</span><span class="sxs-lookup"><span data-stu-id="36494-593">com</span></span>
- <span data-ttu-id="36494-594">s — int.</span><span class="sxs-lookup"><span data-stu-id="36494-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="36494-595">команде</span><span class="sxs-lookup"><span data-stu-id="36494-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="36494-596">Строка подключения к кэшу Azure Redis</span><span class="sxs-lookup"><span data-stu-id="36494-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="36494-597">Format</span><span class="sxs-lookup"><span data-stu-id="36494-597">Format</span></span>

<span data-ttu-id="36494-598">Строка "Redis. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="36494-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="36494-599">NET, за которыми следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строку "Password" или "pwd".</span><span class="sxs-lookup"><span data-stu-id="36494-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-600">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-600">Pattern</span></span>

- <span data-ttu-id="36494-601">Строка "Redis. Cache. Windows.</span><span class="sxs-lookup"><span data-stu-id="36494-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="36494-602">команде</span><span class="sxs-lookup"><span data-stu-id="36494-602">net"</span></span>
- <span data-ttu-id="36494-603">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="36494-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="36494-604">Строка "Password" или "pwd"</span><span class="sxs-lookup"><span data-stu-id="36494-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="36494-605">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-606">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-606">An equal sign (=)</span></span>
- <span data-ttu-id="36494-607">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-608">Любое сочетание 43 символов, которые представляют собой буквы нижнего или верхнего регистра, цифры, косую черту (/) или знак плюса (+).</span><span class="sxs-lookup"><span data-stu-id="36494-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="36494-609">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-610">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-610">Checksum</span></span>

<span data-ttu-id="36494-611">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-612">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-612">Definition</span></span>

<span data-ttu-id="36494-613">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-614">Регулярное выражение CEP_Regex_AzureRedisCacheConnectionString находит содержимое, которое соответствует шаблону..</span><span class="sxs-lookup"><span data-stu-id="36494-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="36494-615">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-616">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="36494-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="36494-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="36494-618">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="36494-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="36494-619">компанией</span><span class="sxs-lookup"><span data-stu-id="36494-619">contoso</span></span>
- <span data-ttu-id="36494-620">компании</span><span class="sxs-lookup"><span data-stu-id="36494-620">fabrikam</span></span>
- <span data-ttu-id="36494-621">базу</span><span class="sxs-lookup"><span data-stu-id="36494-621">northwind</span></span>
- <span data-ttu-id="36494-622">песочниц</span><span class="sxs-lookup"><span data-stu-id="36494-622">sandbox</span></span>
- <span data-ttu-id="36494-623">онебокс</span><span class="sxs-lookup"><span data-stu-id="36494-623">onebox</span></span>
- <span data-ttu-id="36494-624">localhost</span><span class="sxs-lookup"><span data-stu-id="36494-624">localhost</span></span>
- <span data-ttu-id="36494-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="36494-625">127.0.0.1</span></span>
- <span data-ttu-id="36494-626">тестакс.</span><span class="sxs-lookup"><span data-stu-id="36494-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="36494-627">порта</span><span class="sxs-lookup"><span data-stu-id="36494-627">com</span></span>
- <span data-ttu-id="36494-628">s — int.</span><span class="sxs-lookup"><span data-stu-id="36494-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="36494-629">команде</span><span class="sxs-lookup"><span data-stu-id="36494-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="36494-630">SAS Azure</span><span class="sxs-lookup"><span data-stu-id="36494-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="36494-631">Format</span><span class="sxs-lookup"><span data-stu-id="36494-631">Format</span></span>

<span data-ttu-id="36494-632">Строка "SIG", за которой следуют символы и строки, описанные в приведенном ниже шаблоне.</span><span class="sxs-lookup"><span data-stu-id="36494-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-633">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-633">Pattern</span></span>

- <span data-ttu-id="36494-634">Строка "SIG"</span><span class="sxs-lookup"><span data-stu-id="36494-634">The string "sig"</span></span>
- <span data-ttu-id="36494-635">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-636">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-636">An equal sign (=)</span></span>
- <span data-ttu-id="36494-637">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-638">Любое сочетание 43-53 символов, которые являются буквами нижнего или верхнего регистра, цифрами или знаком процента (%)</span><span class="sxs-lookup"><span data-stu-id="36494-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="36494-639">Строка "% 3D"</span><span class="sxs-lookup"><span data-stu-id="36494-639">The string "%3d"</span></span>
- <span data-ttu-id="36494-640">Любой символ, который не является буквой нижнего или верхнего регистра, цифрой или знаком процента (%)</span><span class="sxs-lookup"><span data-stu-id="36494-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-641">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-641">Checksum</span></span>

<span data-ttu-id="36494-642">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-643">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-643">Definition</span></span>

<span data-ttu-id="36494-644">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-645">Регулярное выражение CEP_Regex_AzureSAS находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="36494-646">Строка подключения к служебной шине Azure</span><span class="sxs-lookup"><span data-stu-id="36494-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="36494-647">Format</span><span class="sxs-lookup"><span data-stu-id="36494-647">Format</span></span>

<span data-ttu-id="36494-648">Строка "EndPoint", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строки "сервицебус. Windows.</span><span class="sxs-lookup"><span data-stu-id="36494-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="36494-649">NET "и" Шаредакцескэй ".</span><span class="sxs-lookup"><span data-stu-id="36494-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-650">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-650">Pattern</span></span>

- <span data-ttu-id="36494-651">Строка "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="36494-651">The string "EndPoint"</span></span>
- <span data-ttu-id="36494-652">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-653">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-653">An equal sign (=)</span></span>
- <span data-ttu-id="36494-654">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-655">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="36494-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="36494-656">Строка "сервицебус. Windows.</span><span class="sxs-lookup"><span data-stu-id="36494-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="36494-657">команде</span><span class="sxs-lookup"><span data-stu-id="36494-657">net"</span></span>
- <span data-ttu-id="36494-658">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="36494-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="36494-659">Строка "Шаредакцесскэй"</span><span class="sxs-lookup"><span data-stu-id="36494-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="36494-660">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-661">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-661">An equal sign (=)</span></span>
- <span data-ttu-id="36494-662">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-663">Любое сочетание 43 символов, которые представляют собой буквы нижнего или верхнего регистра, цифры, косую черту (/) или знак плюса (+).</span><span class="sxs-lookup"><span data-stu-id="36494-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="36494-664">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-665">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-665">Checksum</span></span>

<span data-ttu-id="36494-666">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-667">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-667">Definition</span></span>

<span data-ttu-id="36494-668">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-669">Регулярное выражение CEP_Regex_AzureServiceBusConnectionString находит содержимое, которое соответствует шаблону..</span><span class="sxs-lookup"><span data-stu-id="36494-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="36494-670">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-671">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="36494-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="36494-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="36494-673">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="36494-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="36494-674">компанией</span><span class="sxs-lookup"><span data-stu-id="36494-674">contoso</span></span>
- <span data-ttu-id="36494-675">компании</span><span class="sxs-lookup"><span data-stu-id="36494-675">fabrikam</span></span>
- <span data-ttu-id="36494-676">базу</span><span class="sxs-lookup"><span data-stu-id="36494-676">northwind</span></span>
- <span data-ttu-id="36494-677">песочниц</span><span class="sxs-lookup"><span data-stu-id="36494-677">sandbox</span></span>
- <span data-ttu-id="36494-678">онебокс</span><span class="sxs-lookup"><span data-stu-id="36494-678">onebox</span></span>
- <span data-ttu-id="36494-679">localhost</span><span class="sxs-lookup"><span data-stu-id="36494-679">localhost</span></span>
- <span data-ttu-id="36494-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="36494-680">127.0.0.1</span></span>
- <span data-ttu-id="36494-681">тестакс.</span><span class="sxs-lookup"><span data-stu-id="36494-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="36494-682">порта</span><span class="sxs-lookup"><span data-stu-id="36494-682">com</span></span>
- <span data-ttu-id="36494-683">s — int.</span><span class="sxs-lookup"><span data-stu-id="36494-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="36494-684">команде</span><span class="sxs-lookup"><span data-stu-id="36494-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="36494-685">Ключ учетной записи хранилища Azure</span><span class="sxs-lookup"><span data-stu-id="36494-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="36494-686">Format</span><span class="sxs-lookup"><span data-stu-id="36494-686">Format</span></span>

<span data-ttu-id="36494-687">Строка "Дефаултендпоинтспротокол", за которой следуют символы и строки, описанные в приведенном ниже шаблоне, в том числе строку "AccountKey".</span><span class="sxs-lookup"><span data-stu-id="36494-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-688">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-688">Pattern</span></span>

- <span data-ttu-id="36494-689">Строка "Дефаултендпоинтспротокол"</span><span class="sxs-lookup"><span data-stu-id="36494-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="36494-690">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-691">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-691">An equal sign (=)</span></span>
- <span data-ttu-id="36494-692">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-693">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="36494-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="36494-694">Строка "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="36494-694">The string "AccountKey"</span></span>
- <span data-ttu-id="36494-695">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-696">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-696">An equal sign (=)</span></span>
- <span data-ttu-id="36494-697">0-2 символов пробела</span><span class="sxs-lookup"><span data-stu-id="36494-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="36494-698">Любое сочетание 86 символов, которые представляют собой буквы нижнего или верхнего регистра, цифры, косую черту (/) или знак плюса (+).</span><span class="sxs-lookup"><span data-stu-id="36494-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="36494-699">Два знака равенства (=)</span><span class="sxs-lookup"><span data-stu-id="36494-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-700">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-700">Checksum</span></span>

<span data-ttu-id="36494-701">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-702">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-702">Definition</span></span>

<span data-ttu-id="36494-703">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-704">Регулярное выражение CEP_Regex_AzureStorageAccountKey находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-705">Регулярное выражение CEP_AzureEmulatorStorageAccountFilter не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="36494-706">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-707">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="36494-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="36494-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="36494-709">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="36494-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="36494-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/Кбхбексогмгв = =</span><span class="sxs-lookup"><span data-stu-id="36494-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="36494-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="36494-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="36494-712">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="36494-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="36494-713">компанией</span><span class="sxs-lookup"><span data-stu-id="36494-713">contoso</span></span>
- <span data-ttu-id="36494-714">компании</span><span class="sxs-lookup"><span data-stu-id="36494-714">fabrikam</span></span>
- <span data-ttu-id="36494-715">базу</span><span class="sxs-lookup"><span data-stu-id="36494-715">northwind</span></span>
- <span data-ttu-id="36494-716">песочниц</span><span class="sxs-lookup"><span data-stu-id="36494-716">sandbox</span></span>
- <span data-ttu-id="36494-717">онебокс</span><span class="sxs-lookup"><span data-stu-id="36494-717">onebox</span></span>
- <span data-ttu-id="36494-718">localhost</span><span class="sxs-lookup"><span data-stu-id="36494-718">localhost</span></span>
- <span data-ttu-id="36494-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="36494-719">127.0.0.1</span></span>
- <span data-ttu-id="36494-720">тестакс.</span><span class="sxs-lookup"><span data-stu-id="36494-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="36494-721">порта</span><span class="sxs-lookup"><span data-stu-id="36494-721">com</span></span>
- <span data-ttu-id="36494-722">s — int.</span><span class="sxs-lookup"><span data-stu-id="36494-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="36494-723">команде</span><span class="sxs-lookup"><span data-stu-id="36494-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="36494-724">Ключ учетной записи хранилища Azure (общий)</span><span class="sxs-lookup"><span data-stu-id="36494-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="36494-725">Format</span><span class="sxs-lookup"><span data-stu-id="36494-725">Format</span></span>

<span data-ttu-id="36494-726">Любая комбинация 86 строчных или прописных букв, цифр, знаков косой черты (/) или знака плюса (+) перед или за ними следуют символы, указанные в приведенном ниже шаблоне.</span><span class="sxs-lookup"><span data-stu-id="36494-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-727">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-727">Pattern</span></span>

- <span data-ttu-id="36494-728">0-1 из символа "больше" (>), апостроф ('), знак равенства (=), знак кавычек (") или решетка (#)</span><span class="sxs-lookup"><span data-stu-id="36494-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="36494-729">Любое сочетание 86 символов, которые представляют собой буквы в нижнем или верхнем регистре, цифры, косую черту (/) или знак плюса (+).</span><span class="sxs-lookup"><span data-stu-id="36494-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="36494-730">Два знака равенства (=)</span><span class="sxs-lookup"><span data-stu-id="36494-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="36494-731">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-731">Checksum</span></span>

<span data-ttu-id="36494-732">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-733">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-733">Definition</span></span>

<span data-ttu-id="36494-734">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-735">Регулярное выражение CEP_Regex_AzureStorageAccountKeyGeneric находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="36494-736">Номер национального документа для Бельгии</span><span class="sxs-lookup"><span data-stu-id="36494-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-737">Format</span><span class="sxs-lookup"><span data-stu-id="36494-737">Format</span></span>

<span data-ttu-id="36494-738">11 цифр, а также разделители.</span><span class="sxs-lookup"><span data-stu-id="36494-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-739">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-739">Pattern</span></span>

<span data-ttu-id="36494-740">11 цифр, а также разделители:</span><span class="sxs-lookup"><span data-stu-id="36494-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="36494-741">шесть цифр и две точки в формате ГГ.ММ.ДД для даты рождения;</span><span class="sxs-lookup"><span data-stu-id="36494-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="36494-742">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-742">A hyphen</span></span> 
- <span data-ttu-id="36494-743">три последовательные цифры (нечетные для мужчин, четные для женщин);</span><span class="sxs-lookup"><span data-stu-id="36494-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="36494-744">точка;</span><span class="sxs-lookup"><span data-stu-id="36494-744">A period</span></span> 
- <span data-ttu-id="36494-745">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-746">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-746">Checksum</span></span>

<span data-ttu-id="36494-747">Да</span><span class="sxs-lookup"><span data-stu-id="36494-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-748">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-748">Definition</span></span>

<span data-ttu-id="36494-749">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-750">функция Func_belgium_national_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-751">находится ключевое слово из Keyword_belgium_national_number;</span><span class="sxs-lookup"><span data-stu-id="36494-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="36494-752">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-753">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="36494-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="36494-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="36494-755">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="36494-755">Identity</span></span>
- <span data-ttu-id="36494-756">Зарегистрировал</span><span class="sxs-lookup"><span data-stu-id="36494-756">Registration</span></span>
- <span data-ttu-id="36494-757">Процедура</span><span class="sxs-lookup"><span data-stu-id="36494-757">Identification</span></span> 
- <span data-ttu-id="36494-758">ID</span><span class="sxs-lookup"><span data-stu-id="36494-758">ID</span></span> 
- <span data-ttu-id="36494-759">идентитеитскаарт</span><span class="sxs-lookup"><span data-stu-id="36494-759">Identiteitskaart</span></span>
- <span data-ttu-id="36494-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="36494-760">Registratie nummer</span></span> 
- <span data-ttu-id="36494-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="36494-761">Identificatie nummer</span></span> 
- <span data-ttu-id="36494-762">идентитеит</span><span class="sxs-lookup"><span data-stu-id="36494-762">Identiteit</span></span>
- <span data-ttu-id="36494-763">регистратие</span><span class="sxs-lookup"><span data-stu-id="36494-763">Registratie</span></span>
- <span data-ttu-id="36494-764">идентификатие</span><span class="sxs-lookup"><span data-stu-id="36494-764">Identificatie</span></span> 
- <span data-ttu-id="36494-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="36494-765">Carte d’identité</span></span> 
- <span data-ttu-id="36494-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="36494-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="36494-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="36494-767">numéro d'identification</span></span>
- <span data-ttu-id="36494-768">идентитé</span><span class="sxs-lookup"><span data-stu-id="36494-768">identité</span></span> 
- <span data-ttu-id="36494-769">инскриптион</span><span class="sxs-lookup"><span data-stu-id="36494-769">inscription</span></span> 
- <span data-ttu-id="36494-770">идентификатион</span><span class="sxs-lookup"><span data-stu-id="36494-770">Identifikation</span></span>
- <span data-ttu-id="36494-771">идентифизиерунг</span><span class="sxs-lookup"><span data-stu-id="36494-771">Identifizierung</span></span>
- <span data-ttu-id="36494-772">идентификатионснуммер</span><span class="sxs-lookup"><span data-stu-id="36494-772">Identifikationsnummer</span></span>
- <span data-ttu-id="36494-773">персоналаусвеис</span><span class="sxs-lookup"><span data-stu-id="36494-773">Personalausweis</span></span>
- <span data-ttu-id="36494-774">регистриерунг</span><span class="sxs-lookup"><span data-stu-id="36494-774">Registrierung</span></span>
- <span data-ttu-id="36494-775">регистратионснуммер</span><span class="sxs-lookup"><span data-stu-id="36494-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="36494-776">Номер CPF для Бразилии</span><span class="sxs-lookup"><span data-stu-id="36494-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-777">Format</span><span class="sxs-lookup"><span data-stu-id="36494-777">Format</span></span>

<span data-ttu-id="36494-778">11 цифр, которые включают проверочную цифру и могут быть форматированными или неформатированными.</span><span class="sxs-lookup"><span data-stu-id="36494-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-779">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-779">Pattern</span></span>

<span data-ttu-id="36494-780">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="36494-780">Formatted:</span></span>
- <span data-ttu-id="36494-781">три цифры; </span><span class="sxs-lookup"><span data-stu-id="36494-781">Three digits</span></span> 
- <span data-ttu-id="36494-782">точка;</span><span class="sxs-lookup"><span data-stu-id="36494-782">A period</span></span> 
- <span data-ttu-id="36494-783">три цифры; </span><span class="sxs-lookup"><span data-stu-id="36494-783">Three digits</span></span> 
- <span data-ttu-id="36494-784">точка;</span><span class="sxs-lookup"><span data-stu-id="36494-784">A period</span></span> 
- <span data-ttu-id="36494-785">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-785">Three digits</span></span> 
- <span data-ttu-id="36494-786">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-786">A hyphen</span></span> 
- <span data-ttu-id="36494-787">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-787">Two digits which are check digits</span></span>

<span data-ttu-id="36494-788">Неформатированные</span><span class="sxs-lookup"><span data-stu-id="36494-788">Unformatted:</span></span>
- <span data-ttu-id="36494-789">11 цифр, где две последние цифры — проверочные.</span><span class="sxs-lookup"><span data-stu-id="36494-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-790">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-790">Checksum</span></span>

<span data-ttu-id="36494-791">Да</span><span class="sxs-lookup"><span data-stu-id="36494-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-792">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-792">Definition</span></span>

<span data-ttu-id="36494-793">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-794">функция Func_brazil_cpf находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-795">находится ключевое слово из Keyword_brazil_cpf;</span><span class="sxs-lookup"><span data-stu-id="36494-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="36494-796">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-796">The checksum passes.</span></span>

<span data-ttu-id="36494-797">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-798">функция Func_brazil_cpf находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-799">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-799">The checksum passes.</span></span>

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-800">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="36494-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="36494-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="36494-802">CPF</span><span class="sxs-lookup"><span data-stu-id="36494-802">CPF</span></span>
- <span data-ttu-id="36494-803">Процедура</span><span class="sxs-lookup"><span data-stu-id="36494-803">Identification</span></span>
- <span data-ttu-id="36494-804">Зарегистрировал</span><span class="sxs-lookup"><span data-stu-id="36494-804">Registration</span></span>
- <span data-ttu-id="36494-805">Реализации</span><span class="sxs-lookup"><span data-stu-id="36494-805">Revenue</span></span>
- <span data-ttu-id="36494-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="36494-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="36494-807">импосто</span><span class="sxs-lookup"><span data-stu-id="36494-807">Imposto</span></span> 
- <span data-ttu-id="36494-808">идентификаçãо</span><span class="sxs-lookup"><span data-stu-id="36494-808">Identificação</span></span> 
- <span data-ttu-id="36494-809">инскриçãо</span><span class="sxs-lookup"><span data-stu-id="36494-809">Inscrição</span></span> 
- <span data-ttu-id="36494-810">рецеита</span><span class="sxs-lookup"><span data-stu-id="36494-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="36494-811">Номер юридического лица для Бразилии (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="36494-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="36494-812">Format</span><span class="sxs-lookup"><span data-stu-id="36494-812">Format</span></span>

<span data-ttu-id="36494-813">14 цифр, которые включают регистрационный номер, номер филиала и проверочные цифры, а также разделители.</span><span class="sxs-lookup"><span data-stu-id="36494-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-814">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-814">Pattern</span></span>
<span data-ttu-id="36494-815">14 цифр, а также разделители:</span><span class="sxs-lookup"><span data-stu-id="36494-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="36494-816">две цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-816">Two digits</span></span> 
- <span data-ttu-id="36494-817">точка;</span><span class="sxs-lookup"><span data-stu-id="36494-817">A period</span></span> 
- <span data-ttu-id="36494-818">три цифры; </span><span class="sxs-lookup"><span data-stu-id="36494-818">Three digits</span></span> 
- <span data-ttu-id="36494-819">точка;</span><span class="sxs-lookup"><span data-stu-id="36494-819">A period</span></span> 
- <span data-ttu-id="36494-820">три цифры (эти первые восемь цифр — регистрационный номер);</span><span class="sxs-lookup"><span data-stu-id="36494-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="36494-821">косая черта;</span><span class="sxs-lookup"><span data-stu-id="36494-821">A forward slash</span></span> 
- <span data-ttu-id="36494-822">номер отделения из четырех цифр;</span><span class="sxs-lookup"><span data-stu-id="36494-822">Four-digit branch number</span></span> 
- <span data-ttu-id="36494-823">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-823">A hyphen</span></span> 
- <span data-ttu-id="36494-824">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-825">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-825">Checksum</span></span>

<span data-ttu-id="36494-826">Да</span><span class="sxs-lookup"><span data-stu-id="36494-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-827">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-827">Definition</span></span>

<span data-ttu-id="36494-828">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-829">функция Func_brazil_cnpj находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-830">находится ключевое слово из Keyword_brazil_cnpj;</span><span class="sxs-lookup"><span data-stu-id="36494-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="36494-831">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-831">The checksum passes.</span></span>

<span data-ttu-id="36494-832">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-833">функция Func_brazil_cnpj находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-834">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-834">The checksum passes.</span></span>

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-835">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="36494-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="36494-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="36494-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="36494-837">CNPJ</span></span> 
- <span data-ttu-id="36494-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="36494-838">CNPJ/MF</span></span> 
- <span data-ttu-id="36494-839">CNPJ – MF</span><span class="sxs-lookup"><span data-stu-id="36494-839">CNPJ-MF</span></span> 
- <span data-ttu-id="36494-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="36494-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="36494-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="36494-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="36494-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="36494-842">Legal entity</span></span> 
- <span data-ttu-id="36494-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="36494-843">Legal entities</span></span> 
- <span data-ttu-id="36494-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="36494-844">Registration Status</span></span> 
- <span data-ttu-id="36494-845">Бизнес</span><span class="sxs-lookup"><span data-stu-id="36494-845">Business</span></span> 
- <span data-ttu-id="36494-846">Company</span><span class="sxs-lookup"><span data-stu-id="36494-846">Company</span></span>
- <span data-ttu-id="36494-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="36494-847">CNPJ</span></span> 
- <span data-ttu-id="36494-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="36494-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="36494-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="36494-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="36494-850">кгк</span><span class="sxs-lookup"><span data-stu-id="36494-850">CGC</span></span> 
- <span data-ttu-id="36494-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="36494-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="36494-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="36494-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="36494-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="36494-853">Situação cadastral</span></span> 
- <span data-ttu-id="36494-854">инскриçãо</span><span class="sxs-lookup"><span data-stu-id="36494-854">Inscrição</span></span> 
- <span data-ttu-id="36494-855">емпреса</span><span class="sxs-lookup"><span data-stu-id="36494-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="36494-856">	Номер внутреннего удостоверения личности для Бразилии (RG)</span><span class="sxs-lookup"><span data-stu-id="36494-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="36494-857">Format</span><span class="sxs-lookup"><span data-stu-id="36494-857">Format</span></span>

<span data-ttu-id="36494-858">Registro Geral (старый формат): девять цифр</span><span class="sxs-lookup"><span data-stu-id="36494-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="36494-859">Registro de identidade (RIC) (новый формат): 11 цифр</span><span class="sxs-lookup"><span data-stu-id="36494-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-860">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-860">Pattern</span></span>

<span data-ttu-id="36494-861">Registro Geral (старый формат):</span><span class="sxs-lookup"><span data-stu-id="36494-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="36494-862">две цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-862">Two digits</span></span> 
- <span data-ttu-id="36494-863">точка;</span><span class="sxs-lookup"><span data-stu-id="36494-863">A period</span></span> 
- <span data-ttu-id="36494-864">три цифры; </span><span class="sxs-lookup"><span data-stu-id="36494-864">Three digits</span></span> 
- <span data-ttu-id="36494-865">точка;</span><span class="sxs-lookup"><span data-stu-id="36494-865">A period</span></span> 
- <span data-ttu-id="36494-866">три цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-866">Three digits</span></span> 
- <span data-ttu-id="36494-867">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-867">A hyphen</span></span> 
- <span data-ttu-id="36494-868">одна цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="36494-868">One digit which is a check digit</span></span>

<span data-ttu-id="36494-869">Registro de identidade (RIC) (новый формат):</span><span class="sxs-lookup"><span data-stu-id="36494-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="36494-870">10 цифр;</span><span class="sxs-lookup"><span data-stu-id="36494-870">10 digits</span></span> 
- <span data-ttu-id="36494-871">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-871">A hyphen</span></span> 
- <span data-ttu-id="36494-872">одна цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="36494-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-873">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-873">Checksum</span></span>

<span data-ttu-id="36494-874">Да</span><span class="sxs-lookup"><span data-stu-id="36494-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-875">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-875">Definition</span></span>

<span data-ttu-id="36494-876">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-877">функция Func_brazil_rg находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-878">находится ключевое слово из Keyword_brazil_rg;</span><span class="sxs-lookup"><span data-stu-id="36494-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="36494-879">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-879">The checksum passes.</span></span>

<span data-ttu-id="36494-880">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-881">функция Func_brazil_rg находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-882">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-882">The checksum passes.</span></span>

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-883">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="36494-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="36494-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="36494-885">Кéдула de identidade Identity Card National ID нúмеро de ррегистро Registro de Иидентидаде Registro Geral RG (это ключевое слово учитывает регистр) RIC (это ключевое слово учитывает регистр).</span><span class="sxs-lookup"><span data-stu-id="36494-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="36494-886">Номер банковского счета для Канады</span><span class="sxs-lookup"><span data-stu-id="36494-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-887">Format</span><span class="sxs-lookup"><span data-stu-id="36494-887">Format</span></span>

<span data-ttu-id="36494-888">Семь или двенадцать цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-889">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-889">Pattern</span></span>

<span data-ttu-id="36494-890">Номер банковского счета для Канады — семь или двенадцать цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="36494-891">Транзитный номер банковского счета в Канаде имеет указанный ниже формат.</span><span class="sxs-lookup"><span data-stu-id="36494-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="36494-892">пять цифр;</span><span class="sxs-lookup"><span data-stu-id="36494-892">Five digits</span></span> 
- <span data-ttu-id="36494-893">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-893">A hyphen</span></span> 
- <span data-ttu-id="36494-894">Три цифры или</span><span class="sxs-lookup"><span data-stu-id="36494-894">Three digits OR</span></span>
- <span data-ttu-id="36494-895">ноль "0";</span><span class="sxs-lookup"><span data-stu-id="36494-895">A zero "0"</span></span> 
- <span data-ttu-id="36494-896">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-897">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-897">Checksum</span></span>

<span data-ttu-id="36494-898">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-899">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-899">Definition</span></span>

<span data-ttu-id="36494-900">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-901">регулярное выражение Regex_canada_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-902">находится ключевое слово из Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="36494-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="36494-903">регулярное выражение Regex_canada_bank_account_transit_number находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="36494-904">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-905">регулярное выражение Regex_canada_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-906">находится ключевое слово из Keyword_canada_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="36494-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-907">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="36494-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="36494-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="36494-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="36494-909">canada savings bonds</span></span>
- <span data-ttu-id="36494-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="36494-910">canada revenue agency</span></span>
- <span data-ttu-id="36494-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="36494-911">canadian financial institution</span></span>
- <span data-ttu-id="36494-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="36494-912">direct deposit form</span></span>
- <span data-ttu-id="36494-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="36494-913">canadian citizen</span></span>
- <span data-ttu-id="36494-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="36494-914">legal representative</span></span>
- <span data-ttu-id="36494-915">notary public</span><span class="sxs-lookup"><span data-stu-id="36494-915">notary public</span></span>
- <span data-ttu-id="36494-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="36494-916">commissioner for oaths</span></span>
- <span data-ttu-id="36494-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="36494-917">child care benefit</span></span>
- <span data-ttu-id="36494-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="36494-918">universal child care</span></span>
- <span data-ttu-id="36494-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="36494-919">canada child tax benefit</span></span>
- <span data-ttu-id="36494-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="36494-920">income tax benefit</span></span>
- <span data-ttu-id="36494-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="36494-921">harmonized sales tax</span></span>
- <span data-ttu-id="36494-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="36494-922">social insurance number</span></span>
- <span data-ttu-id="36494-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="36494-923">income tax refund</span></span>
- <span data-ttu-id="36494-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="36494-924">child tax benefit</span></span>
- <span data-ttu-id="36494-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="36494-925">territorial payments</span></span>
- <span data-ttu-id="36494-926">institution number</span><span class="sxs-lookup"><span data-stu-id="36494-926">institution number</span></span>
- <span data-ttu-id="36494-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="36494-927">deposit request</span></span>
- <span data-ttu-id="36494-928">banking information</span><span class="sxs-lookup"><span data-stu-id="36494-928">banking information</span></span>
- <span data-ttu-id="36494-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="36494-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="36494-930">Номер водительского удостоверения для Канады</span><span class="sxs-lookup"><span data-stu-id="36494-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-931">Format</span><span class="sxs-lookup"><span data-stu-id="36494-931">Format</span></span>

<span data-ttu-id="36494-932">Зависит от провинции.</span><span class="sxs-lookup"><span data-stu-id="36494-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-933">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-933">Pattern</span></span>

<span data-ttu-id="36494-934">Различные шаблоны, соответствующие провинциям Альберта, Британская Колумбия, Манитоба, Нью-Брансуик, Ньюфаундленд и Лабрадор, Новая Шотландия, Онтарио, Остров Принца Эдуарда, Квебек и Саскачеван.</span><span class="sxs-lookup"><span data-stu-id="36494-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-935">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-935">Checksum</span></span>

<span data-ttu-id="36494-936">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-937">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-937">Definition</span></span>

<span data-ttu-id="36494-938">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-939">функция Func_[province_name]_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-940">находится ключевое слово из Keyword_[province_name]_drivers_license_name;</span><span class="sxs-lookup"><span data-stu-id="36494-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="36494-941">находится ключевое слово из Keyword_canada_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="36494-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-942">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="36494-943">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="36494-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="36494-944">Аббревиатура провинции, например AB.</span><span class="sxs-lookup"><span data-stu-id="36494-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="36494-945">Название провинции, например Альберта.</span><span class="sxs-lookup"><span data-stu-id="36494-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="36494-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="36494-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="36494-947">DL</span><span class="sxs-lookup"><span data-stu-id="36494-947">DL</span></span>
- <span data-ttu-id="36494-948">БИБЛИОТЕК</span><span class="sxs-lookup"><span data-stu-id="36494-948">DLS</span></span>
- <span data-ttu-id="36494-949">кдл</span><span class="sxs-lookup"><span data-stu-id="36494-949">CDL</span></span>
- <span data-ttu-id="36494-950">кдлс</span><span class="sxs-lookup"><span data-stu-id="36494-950">CDLS</span></span>
- <span data-ttu-id="36494-951">дриверлик</span><span class="sxs-lookup"><span data-stu-id="36494-951">DriverLic</span></span>
- <span data-ttu-id="36494-952">дриверликс</span><span class="sxs-lookup"><span data-stu-id="36494-952">DriverLics</span></span>
- <span data-ttu-id="36494-953">дриверлиценсе</span><span class="sxs-lookup"><span data-stu-id="36494-953">DriverLicense</span></span>
- <span data-ttu-id="36494-954">дриверлиценсес</span><span class="sxs-lookup"><span data-stu-id="36494-954">DriverLicenses</span></span>
- <span data-ttu-id="36494-955">дриверлиценце</span><span class="sxs-lookup"><span data-stu-id="36494-955">DriverLicence</span></span>
- <span data-ttu-id="36494-956">дриверлиценцес</span><span class="sxs-lookup"><span data-stu-id="36494-956">DriverLicences</span></span>
- <span data-ttu-id="36494-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="36494-957">Driver Lic</span></span>
- <span data-ttu-id="36494-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="36494-958">Driver Lics</span></span>
- <span data-ttu-id="36494-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="36494-959">Driver License</span></span>
- <span data-ttu-id="36494-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-960">Driver Licenses</span></span>
- <span data-ttu-id="36494-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="36494-961">Driver Licence</span></span>
- <span data-ttu-id="36494-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="36494-962">Driver Licences</span></span>
- <span data-ttu-id="36494-963">дриверслик</span><span class="sxs-lookup"><span data-stu-id="36494-963">DriversLic</span></span>
- <span data-ttu-id="36494-964">дриверсликс</span><span class="sxs-lookup"><span data-stu-id="36494-964">DriversLics</span></span>
- <span data-ttu-id="36494-965">дриверслиценце</span><span class="sxs-lookup"><span data-stu-id="36494-965">DriversLicence</span></span>
- <span data-ttu-id="36494-966">дриверслиценцес</span><span class="sxs-lookup"><span data-stu-id="36494-966">DriversLicences</span></span>
- <span data-ttu-id="36494-967">дриверслиценсе</span><span class="sxs-lookup"><span data-stu-id="36494-967">DriversLicense</span></span>
- <span data-ttu-id="36494-968">дриверслиценсес</span><span class="sxs-lookup"><span data-stu-id="36494-968">DriversLicenses</span></span>
- <span data-ttu-id="36494-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="36494-969">Drivers Lic</span></span>
- <span data-ttu-id="36494-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="36494-970">Drivers Lics</span></span>
- <span data-ttu-id="36494-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="36494-971">Drivers License</span></span>
- <span data-ttu-id="36494-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-972">Drivers Licenses</span></span>
- <span data-ttu-id="36494-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="36494-973">Drivers Licence</span></span>
- <span data-ttu-id="36494-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="36494-974">Drivers Licences</span></span>
- <span data-ttu-id="36494-975">Driver ' LIC</span><span class="sxs-lookup"><span data-stu-id="36494-975">Driver'Lic</span></span>
- <span data-ttu-id="36494-976">Driver ' LICS</span><span class="sxs-lookup"><span data-stu-id="36494-976">Driver'Lics</span></span>
- <span data-ttu-id="36494-977">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="36494-977">Driver'License</span></span>
- <span data-ttu-id="36494-978">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-978">Driver'Licenses</span></span>
- <span data-ttu-id="36494-979">Driver ' Licence</span><span class="sxs-lookup"><span data-stu-id="36494-979">Driver'Licence</span></span>
- <span data-ttu-id="36494-980">Driver ' Licences</span><span class="sxs-lookup"><span data-stu-id="36494-980">Driver'Licences</span></span>
- <span data-ttu-id="36494-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="36494-981">Driver' Lic</span></span>
- <span data-ttu-id="36494-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="36494-982">Driver' Lics</span></span>
- <span data-ttu-id="36494-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="36494-983">Driver' License</span></span>
- <span data-ttu-id="36494-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-984">Driver' Licenses</span></span>
- <span data-ttu-id="36494-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="36494-985">Driver' Licence</span></span>
- <span data-ttu-id="36494-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="36494-986">Driver' Licences</span></span>
- <span data-ttu-id="36494-987">дривер'слик</span><span class="sxs-lookup"><span data-stu-id="36494-987">Driver'sLic</span></span>
- <span data-ttu-id="36494-988">дривер'сликс</span><span class="sxs-lookup"><span data-stu-id="36494-988">Driver'sLics</span></span>
- <span data-ttu-id="36494-989">дривер'слиценсе</span><span class="sxs-lookup"><span data-stu-id="36494-989">Driver'sLicense</span></span>
- <span data-ttu-id="36494-990">дривер'слиценсес</span><span class="sxs-lookup"><span data-stu-id="36494-990">Driver'sLicenses</span></span>
- <span data-ttu-id="36494-991">дривер'слиценце</span><span class="sxs-lookup"><span data-stu-id="36494-991">Driver'sLicence</span></span>
- <span data-ttu-id="36494-992">дривер'слиценцес</span><span class="sxs-lookup"><span data-stu-id="36494-992">Driver'sLicences</span></span>
- <span data-ttu-id="36494-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="36494-993">Driver's Lic</span></span>
- <span data-ttu-id="36494-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="36494-994">Driver's Lics</span></span>
- <span data-ttu-id="36494-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="36494-995">Driver's License</span></span>
- <span data-ttu-id="36494-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-996">Driver's Licenses</span></span>
- <span data-ttu-id="36494-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="36494-997">Driver's Licence</span></span>
- <span data-ttu-id="36494-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="36494-998">Driver's Licences</span></span>
- <span data-ttu-id="36494-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="36494-999">Permis de Conduire</span></span>
- <span data-ttu-id="36494-1000">id</span><span class="sxs-lookup"><span data-stu-id="36494-1000">id</span></span>
- <span data-ttu-id="36494-1001">ids</span><span class="sxs-lookup"><span data-stu-id="36494-1001">ids</span></span>
- <span data-ttu-id="36494-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="36494-1002">idcard number</span></span>
- <span data-ttu-id="36494-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="36494-1003">idcard numbers</span></span>
- <span data-ttu-id="36494-1004">idcard#</span><span class="sxs-lookup"><span data-stu-id="36494-1004">idcard #</span></span>
- <span data-ttu-id="36494-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="36494-1005">idcard #s</span></span>
- <span data-ttu-id="36494-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="36494-1006">idcard card</span></span>
- <span data-ttu-id="36494-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="36494-1007">idcard cards</span></span>
- <span data-ttu-id="36494-1008">идкард</span><span class="sxs-lookup"><span data-stu-id="36494-1008">idcard</span></span>
- <span data-ttu-id="36494-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="36494-1009">identification number</span></span>
- <span data-ttu-id="36494-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="36494-1010">identification numbers</span></span>
- <span data-ttu-id="36494-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="36494-1011">identification #</span></span>
- <span data-ttu-id="36494-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="36494-1012">identification #s</span></span>
- <span data-ttu-id="36494-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="36494-1013">identification card</span></span>
- <span data-ttu-id="36494-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="36494-1014">identification cards</span></span>
- <span data-ttu-id="36494-1015">процедура</span><span class="sxs-lookup"><span data-stu-id="36494-1015">identification</span></span> 
- <span data-ttu-id="36494-1016">DL #</span><span class="sxs-lookup"><span data-stu-id="36494-1016">DL#</span></span>
- <span data-ttu-id="36494-1017">БИБЛИОТЕК #</span><span class="sxs-lookup"><span data-stu-id="36494-1017">DLS#</span></span> 
- <span data-ttu-id="36494-1018">кдл #</span><span class="sxs-lookup"><span data-stu-id="36494-1018">CDL#</span></span> 
- <span data-ttu-id="36494-1019">кдлс #</span><span class="sxs-lookup"><span data-stu-id="36494-1019">CDLS#</span></span> 
- <span data-ttu-id="36494-1020">дриверлик #</span><span class="sxs-lookup"><span data-stu-id="36494-1020">DriverLic#</span></span> 
- <span data-ttu-id="36494-1021">дриверликс #</span><span class="sxs-lookup"><span data-stu-id="36494-1021">DriverLics#</span></span> 
- <span data-ttu-id="36494-1022">дриверлиценсе #</span><span class="sxs-lookup"><span data-stu-id="36494-1022">DriverLicense#</span></span> 
- <span data-ttu-id="36494-1023">дриверлиценсес #</span><span class="sxs-lookup"><span data-stu-id="36494-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="36494-1024">дриверлиценце #</span><span class="sxs-lookup"><span data-stu-id="36494-1024">DriverLicence#</span></span> 
- <span data-ttu-id="36494-1025">дриверлиценцес #</span><span class="sxs-lookup"><span data-stu-id="36494-1025">DriverLicences#</span></span> 
- <span data-ttu-id="36494-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="36494-1026">Driver Lic#</span></span>
- <span data-ttu-id="36494-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="36494-1027">Driver Lics#</span></span> 
- <span data-ttu-id="36494-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="36494-1028">Driver License#</span></span> 
- <span data-ttu-id="36494-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="36494-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="36494-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="36494-1030">Driver License#</span></span> 
- <span data-ttu-id="36494-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="36494-1031">Driver Licences#</span></span> 
- <span data-ttu-id="36494-1032">дриверслик #</span><span class="sxs-lookup"><span data-stu-id="36494-1032">DriversLic#</span></span> 
- <span data-ttu-id="36494-1033">дриверсликс #</span><span class="sxs-lookup"><span data-stu-id="36494-1033">DriversLics#</span></span> 
- <span data-ttu-id="36494-1034">дриверслиценсе #</span><span class="sxs-lookup"><span data-stu-id="36494-1034">DriversLicense#</span></span> 
- <span data-ttu-id="36494-1035">дриверслиценсес #</span><span class="sxs-lookup"><span data-stu-id="36494-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="36494-1036">дриверслиценце #</span><span class="sxs-lookup"><span data-stu-id="36494-1036">DriversLicence#</span></span> 
- <span data-ttu-id="36494-1037">дриверслиценцес #</span><span class="sxs-lookup"><span data-stu-id="36494-1037">DriversLicences#</span></span> 
- <span data-ttu-id="36494-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="36494-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="36494-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="36494-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="36494-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="36494-1040">Drivers License#</span></span> 
- <span data-ttu-id="36494-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="36494-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="36494-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="36494-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="36494-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="36494-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="36494-1044">Driver ' LIC #</span><span class="sxs-lookup"><span data-stu-id="36494-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="36494-1045">Driver ' LICS #</span><span class="sxs-lookup"><span data-stu-id="36494-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="36494-1046">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="36494-1046">Driver'License#</span></span> 
- <span data-ttu-id="36494-1047">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="36494-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="36494-1048">Driver ' Licence #</span><span class="sxs-lookup"><span data-stu-id="36494-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="36494-1049">Driver ' Licences #</span><span class="sxs-lookup"><span data-stu-id="36494-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="36494-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="36494-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="36494-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="36494-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="36494-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="36494-1052">Driver' License#</span></span> 
- <span data-ttu-id="36494-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="36494-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="36494-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="36494-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="36494-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="36494-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="36494-1056">дривер'слик #</span><span class="sxs-lookup"><span data-stu-id="36494-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="36494-1057">дривер'сликс #</span><span class="sxs-lookup"><span data-stu-id="36494-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="36494-1058">дривер'слиценсе #</span><span class="sxs-lookup"><span data-stu-id="36494-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="36494-1059">дривер'слиценсес #</span><span class="sxs-lookup"><span data-stu-id="36494-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="36494-1060">дривер'слиценце #</span><span class="sxs-lookup"><span data-stu-id="36494-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="36494-1061">дривер'слиценцес #</span><span class="sxs-lookup"><span data-stu-id="36494-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="36494-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="36494-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="36494-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="36494-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="36494-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="36494-1064">Driver's License#</span></span> 
- <span data-ttu-id="36494-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="36494-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="36494-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="36494-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="36494-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="36494-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="36494-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="36494-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="36494-1069">кодов #</span><span class="sxs-lookup"><span data-stu-id="36494-1069">id#</span></span> 
- <span data-ttu-id="36494-1070">идентификаторы #</span><span class="sxs-lookup"><span data-stu-id="36494-1070">ids#</span></span> 
- <span data-ttu-id="36494-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="36494-1071">idcard card#</span></span> 
- <span data-ttu-id="36494-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="36494-1072">idcard cards#</span></span> 
- <span data-ttu-id="36494-1073">идкард #</span><span class="sxs-lookup"><span data-stu-id="36494-1073">idcard#</span></span> 
- <span data-ttu-id="36494-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="36494-1074">identification card#</span></span> 
- <span data-ttu-id="36494-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="36494-1075">identification cards#</span></span> 
- <span data-ttu-id="36494-1076">процедура #</span><span class="sxs-lookup"><span data-stu-id="36494-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="36494-1077">Номер службы здравоохранения для Канады</span><span class="sxs-lookup"><span data-stu-id="36494-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1078">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1078">Format</span></span>

<span data-ttu-id="36494-1079">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1080">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1080">Pattern</span></span>

<span data-ttu-id="36494-1081">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1082">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1082">Checksum</span></span>

<span data-ttu-id="36494-1083">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1084">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1084">Definition</span></span>

<span data-ttu-id="36494-1085">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1086">регулярное выражение Regex_canada_health_service_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1087">находится ключевое слово из Keyword_canada_health_service_number.</span><span class="sxs-lookup"><span data-stu-id="36494-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1088">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="36494-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="36494-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="36494-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="36494-1090">personal health number</span></span>
- <span data-ttu-id="36494-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="36494-1091">patient information</span></span>
- <span data-ttu-id="36494-1092">health services</span><span class="sxs-lookup"><span data-stu-id="36494-1092">health services</span></span>
- <span data-ttu-id="36494-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="36494-1093">speciality services</span></span>
- <span data-ttu-id="36494-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="36494-1094">automobile accident</span></span>
- <span data-ttu-id="36494-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="36494-1095">patient hospital</span></span>
- <span data-ttu-id="36494-1096">псичиатрист</span><span class="sxs-lookup"><span data-stu-id="36494-1096">psychiatrist</span></span>
- <span data-ttu-id="36494-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="36494-1097">workers compensation</span></span>
- <span data-ttu-id="36494-1098">ограничен</span><span class="sxs-lookup"><span data-stu-id="36494-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="36494-1099">Номер паспорта гражданина Канады</span><span class="sxs-lookup"><span data-stu-id="36494-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1100">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1100">Format</span></span>

<span data-ttu-id="36494-1101">Две прописные буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1102">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1102">Pattern</span></span>

<span data-ttu-id="36494-1103">Две прописные буквы, за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1104">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1104">Checksum</span></span>

<span data-ttu-id="36494-1105">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1106">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1106">Definition</span></span>

<span data-ttu-id="36494-1107">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1108">регулярное выражение Regex_canada_passport_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1109">Найдено ключевое слово из Keyword_canada_passport_number или Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="36494-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1110">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="36494-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="36494-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="36494-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="36494-1112">canadian citizenship</span></span>
- <span data-ttu-id="36494-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="36494-1113">canadian passport</span></span>
- <span data-ttu-id="36494-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="36494-1114">passport application</span></span>
- <span data-ttu-id="36494-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="36494-1115">passport photos</span></span>
- <span data-ttu-id="36494-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="36494-1116">certified translator</span></span>
- <span data-ttu-id="36494-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="36494-1117">canadian citizens</span></span>
- <span data-ttu-id="36494-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="36494-1118">processing times</span></span>
- <span data-ttu-id="36494-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="36494-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="36494-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="36494-1120">Keyword_passport</span></span>

- <span data-ttu-id="36494-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="36494-1121">Passport Number</span></span>
- <span data-ttu-id="36494-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="36494-1122">Passport No</span></span>
- <span data-ttu-id="36494-1123">Passport#</span><span class="sxs-lookup"><span data-stu-id="36494-1123">Passport #</span></span>
- <span data-ttu-id="36494-1124">Службу #</span><span class="sxs-lookup"><span data-stu-id="36494-1124">Passport#</span></span>
- <span data-ttu-id="36494-1125">пасспортид</span><span class="sxs-lookup"><span data-stu-id="36494-1125">PassportID</span></span>
- <span data-ttu-id="36494-1126">пасспортно</span><span class="sxs-lookup"><span data-stu-id="36494-1126">Passportno</span></span>
- <span data-ttu-id="36494-1127">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="36494-1127">passportnumber</span></span>
- <span data-ttu-id="36494-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="36494-1128">パスポート</span></span>
- <span data-ttu-id="36494-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="36494-1129">パスポート番号</span></span>
- <span data-ttu-id="36494-1130">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="36494-1130">パスポートのNum</span></span>
- <span data-ttu-id="36494-1131">パスポート #</span><span class="sxs-lookup"><span data-stu-id="36494-1131">パスポート＃</span></span>
- <span data-ttu-id="36494-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="36494-1132">Numéro de passeport</span></span>
- <span data-ttu-id="36494-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="36494-1133">Passeport n °</span></span>
- <span data-ttu-id="36494-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="36494-1134">Passeport Non</span></span>
- <span data-ttu-id="36494-1135">Passeport#</span><span class="sxs-lookup"><span data-stu-id="36494-1135">Passeport #</span></span>
- <span data-ttu-id="36494-1136">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="36494-1136">Passeport#</span></span>
- <span data-ttu-id="36494-1137">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="36494-1137">PasseportNon</span></span>
- <span data-ttu-id="36494-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="36494-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="36494-1139">Персональный идентификационный номер службы здравоохранения для Канады (PHIN)</span><span class="sxs-lookup"><span data-stu-id="36494-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="36494-1140">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1140">Format</span></span>

<span data-ttu-id="36494-1141">девять цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1142">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1142">Pattern</span></span>

<span data-ttu-id="36494-1143">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1144">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1144">Checksum</span></span>

<span data-ttu-id="36494-1145">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1146">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1146">Definition</span></span>

<span data-ttu-id="36494-1147">Политика защиты от потери данных — 75% уверенности в том, что этот тип конфиденциальной информации обнаружен, если в пределах близости от 300 символов: регулярное выражение Regex_canada_phin находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="36494-1148">Найдены по крайней мере два ключевых слова от Keyword_canada_phin или Keyword_canada_provinces.</span><span class="sxs-lookup"><span data-stu-id="36494-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1149">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="36494-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="36494-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="36494-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="36494-1151">social insurance number</span></span>
- <span data-ttu-id="36494-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="36494-1152">health information act</span></span>
- <span data-ttu-id="36494-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="36494-1153">income tax information</span></span>
- <span data-ttu-id="36494-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="36494-1154">manitoba health</span></span>
- <span data-ttu-id="36494-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="36494-1155">health registration</span></span>
- <span data-ttu-id="36494-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="36494-1156">prescription purchases</span></span>
- <span data-ttu-id="36494-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="36494-1157">benefit eligibility</span></span>
- <span data-ttu-id="36494-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="36494-1158">personal health</span></span>
- <span data-ttu-id="36494-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="36494-1159">power of attorney</span></span>
- <span data-ttu-id="36494-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="36494-1160">registration number</span></span>
- <span data-ttu-id="36494-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="36494-1161">personal health number</span></span>
- <span data-ttu-id="36494-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="36494-1162">practitioner referral</span></span>
- <span data-ttu-id="36494-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="36494-1163">wellness professional</span></span>
- <span data-ttu-id="36494-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="36494-1164">patient referral</span></span>
- <span data-ttu-id="36494-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="36494-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="36494-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="36494-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="36494-1167">нунавут</span><span class="sxs-lookup"><span data-stu-id="36494-1167">Nunavut</span></span>
- <span data-ttu-id="36494-1168">Квебека</span><span class="sxs-lookup"><span data-stu-id="36494-1168">Quebec</span></span>
- <span data-ttu-id="36494-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="36494-1169">Northwest Territories</span></span>
- <span data-ttu-id="36494-1170">Онтарио</span><span class="sxs-lookup"><span data-stu-id="36494-1170">Ontario</span></span>
- <span data-ttu-id="36494-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="36494-1171">British Columbia</span></span>
- <span data-ttu-id="36494-1172">Альберта</span><span class="sxs-lookup"><span data-stu-id="36494-1172">Alberta</span></span>
- <span data-ttu-id="36494-1173">Саскачеван</span><span class="sxs-lookup"><span data-stu-id="36494-1173">Saskatchewan</span></span>
- <span data-ttu-id="36494-1174">Манитоба</span><span class="sxs-lookup"><span data-stu-id="36494-1174">Manitoba</span></span>
- <span data-ttu-id="36494-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="36494-1175">Yukon</span></span>
- <span data-ttu-id="36494-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="36494-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="36494-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="36494-1177">New Brunswick</span></span>
- <span data-ttu-id="36494-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="36494-1178">Nova Scotia</span></span>
- <span data-ttu-id="36494-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="36494-1179">Prince Edward Island</span></span>
- <span data-ttu-id="36494-1180">Канада</span><span class="sxs-lookup"><span data-stu-id="36494-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="36494-1181">Номер карты социального страхования для Канады</span><span class="sxs-lookup"><span data-stu-id="36494-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1182">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1182">Format</span></span>

<span data-ttu-id="36494-1183">Девять цифр с необязательными дефисами или пробелами.</span><span class="sxs-lookup"><span data-stu-id="36494-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1184">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1184">Pattern</span></span>

<span data-ttu-id="36494-1185">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="36494-1185">Formatted:</span></span>
- <span data-ttu-id="36494-1186">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-1186">Three digits</span></span> 
- <span data-ttu-id="36494-1187">Дефис или пробел</span><span class="sxs-lookup"><span data-stu-id="36494-1187">A hyphen or space</span></span> 
- <span data-ttu-id="36494-1188">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-1188">Three digits</span></span> 
- <span data-ttu-id="36494-1189">Дефис или пробел</span><span class="sxs-lookup"><span data-stu-id="36494-1189">A hyphen or space</span></span> 
- <span data-ttu-id="36494-1190">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-1190">Three digits</span></span>

<span data-ttu-id="36494-1191">Неформатированные: девять цифр</span><span class="sxs-lookup"><span data-stu-id="36494-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1192">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1192">Checksum</span></span>

<span data-ttu-id="36494-1193">Да</span><span class="sxs-lookup"><span data-stu-id="36494-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1194">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1194">Definition</span></span>

<span data-ttu-id="36494-1195">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1196">Функция Func_canadian_sin находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1197">Выполняются по меньшей мере два из таких условий:</span><span class="sxs-lookup"><span data-stu-id="36494-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="36494-1198">найдено ключевое слово из Keyword_sin;</span><span class="sxs-lookup"><span data-stu-id="36494-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="36494-1199">найдено ключевое слово из Keyword_sin_collaborative;</span><span class="sxs-lookup"><span data-stu-id="36494-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="36494-1200">функция Func_eu_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="36494-1201">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1201">The checksum passes.</span></span>

<span data-ttu-id="36494-1202">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1203">функция Func_unformatted_canadian_sin находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1204">найдено ключевое слово из Keyword_sin;</span><span class="sxs-lookup"><span data-stu-id="36494-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="36494-1205">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1205">The checksum passes.</span></span>

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1206">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="36494-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="36494-1207">Keyword_sin</span></span>

- <span data-ttu-id="36494-1208">sin</span><span class="sxs-lookup"><span data-stu-id="36494-1208">sin</span></span> 
- <span data-ttu-id="36494-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="36494-1209">social insurance</span></span> 
- <span data-ttu-id="36494-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="36494-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="36494-1211">грехов</span><span class="sxs-lookup"><span data-stu-id="36494-1211">sins</span></span> 
- <span data-ttu-id="36494-1212">SSN</span><span class="sxs-lookup"><span data-stu-id="36494-1212">ssn</span></span> 
- <span data-ttu-id="36494-1213">ssNS</span><span class="sxs-lookup"><span data-stu-id="36494-1213">ssns</span></span> 
- <span data-ttu-id="36494-1214">social security</span><span class="sxs-lookup"><span data-stu-id="36494-1214">social security</span></span> 
- <span data-ttu-id="36494-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="36494-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="36494-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="36494-1216">national identification number</span></span> 
- <span data-ttu-id="36494-1217">national id</span><span class="sxs-lookup"><span data-stu-id="36494-1217">national id</span></span> 
- <span data-ttu-id="36494-1218">Синус #</span><span class="sxs-lookup"><span data-stu-id="36494-1218">sin#</span></span> 
- <span data-ttu-id="36494-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="36494-1219">soc ins</span></span> 
- <span data-ttu-id="36494-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="36494-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="36494-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="36494-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="36494-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="36494-1222">driver's license</span></span> 
- <span data-ttu-id="36494-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="36494-1223">drivers license</span></span> 
- <span data-ttu-id="36494-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="36494-1224">driver's licence</span></span> 
- <span data-ttu-id="36494-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="36494-1225">drivers licence</span></span> 
- <span data-ttu-id="36494-1226">доб</span><span class="sxs-lookup"><span data-stu-id="36494-1226">DOB</span></span> 
- <span data-ttu-id="36494-1227">Birthdate</span><span class="sxs-lookup"><span data-stu-id="36494-1227">Birthdate</span></span> 
- <span data-ttu-id="36494-1228">День рождения </span><span class="sxs-lookup"><span data-stu-id="36494-1228">Birthday</span></span> 
- <span data-ttu-id="36494-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="36494-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="36494-1230">	Номер удостоверения личности для Чили</span><span class="sxs-lookup"><span data-stu-id="36494-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1231">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1231">Format</span></span>

<span data-ttu-id="36494-1232">7-8 цифр и разделители — контрольная цифра или буква</span><span class="sxs-lookup"><span data-stu-id="36494-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1233">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1233">Pattern</span></span>

<span data-ttu-id="36494-1234">7–8 цифр, а также разделители:</span><span class="sxs-lookup"><span data-stu-id="36494-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="36494-1235">1 или 2 цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-1235">1-2 digits</span></span> 
- <span data-ttu-id="36494-1236">точка;</span><span class="sxs-lookup"><span data-stu-id="36494-1236">A period</span></span> 
- <span data-ttu-id="36494-1237">три цифры; </span><span class="sxs-lookup"><span data-stu-id="36494-1237">Three digits</span></span> 
- <span data-ttu-id="36494-1238">точка;</span><span class="sxs-lookup"><span data-stu-id="36494-1238">A period</span></span> 
- <span data-ttu-id="36494-1239">три цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-1239">Three digits</span></span> 
- <span data-ttu-id="36494-1240">тире;</span><span class="sxs-lookup"><span data-stu-id="36494-1240">A dash</span></span> 
- <span data-ttu-id="36494-1241">одна цифра или буква (без учета регистра) — проверочная.</span><span class="sxs-lookup"><span data-stu-id="36494-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1242">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1242">Checksum</span></span>

<span data-ttu-id="36494-1243">Да</span><span class="sxs-lookup"><span data-stu-id="36494-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1244">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1244">Definition</span></span>

<span data-ttu-id="36494-1245">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1246">функция Func_chile_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1247">находится ключевое слово из Keyword_chile_id_card;</span><span class="sxs-lookup"><span data-stu-id="36494-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="36494-1248">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1248">The checksum passes.</span></span>

<span data-ttu-id="36494-1249">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1250">функция Func_chile_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1251">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1251">The checksum passes.</span></span>

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1252">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="36494-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="36494-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="36494-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="36494-1254">National Identification Number</span></span> 
- <span data-ttu-id="36494-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="36494-1255">Identity card</span></span> 
- <span data-ttu-id="36494-1256">ID</span><span class="sxs-lookup"><span data-stu-id="36494-1256">ID</span></span> 
- <span data-ttu-id="36494-1257">Процедура</span><span class="sxs-lookup"><span data-stu-id="36494-1257">Identification</span></span> 
- <span data-ttu-id="36494-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="36494-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="36494-1259">ВЫПОЛНЯЕМ</span><span class="sxs-lookup"><span data-stu-id="36494-1259">RUN</span></span> 
- <span data-ttu-id="36494-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="36494-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="36494-1261">СНИЖАТЬСЯ</span><span class="sxs-lookup"><span data-stu-id="36494-1261">RUT</span></span> 
- <span data-ttu-id="36494-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="36494-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="36494-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="36494-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="36494-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="36494-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="36494-1265">идентификаЦиóн</span><span class="sxs-lookup"><span data-stu-id="36494-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="36494-1266">	Номер удостоверения личности жителя Китая (КНР)</span><span class="sxs-lookup"><span data-stu-id="36494-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1267">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1267">Format</span></span>

<span data-ttu-id="36494-1268">18 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1269">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1269">Pattern</span></span>

<span data-ttu-id="36494-1270">18 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-1270">18 digits:</span></span>
- <span data-ttu-id="36494-1271">шесть цифр — код адреса;</span><span class="sxs-lookup"><span data-stu-id="36494-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="36494-1272">восемь цифр в виде ГГГГММДД — дата рождения;</span><span class="sxs-lookup"><span data-stu-id="36494-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="36494-1273">три цифры — серия карты;</span><span class="sxs-lookup"><span data-stu-id="36494-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="36494-1274">одна цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="36494-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1275">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1275">Checksum</span></span>

<span data-ttu-id="36494-1276">Да</span><span class="sxs-lookup"><span data-stu-id="36494-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1277">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1277">Definition</span></span>

<span data-ttu-id="36494-1278">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1279">функция Func_china_resident_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1280">находится ключевое слово из Keyword_china_resident_id;</span><span class="sxs-lookup"><span data-stu-id="36494-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="36494-1281">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1281">The checksum passes.</span></span>

<span data-ttu-id="36494-1282">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1283">функция Func_china_resident_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1284">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1284">The checksum passes.</span></span>

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1285">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="36494-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="36494-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="36494-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="36494-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="36494-1288">NO7</span><span class="sxs-lookup"><span data-stu-id="36494-1288">PRC</span></span> 
- <span data-ttu-id="36494-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="36494-1289">National Identification Card</span></span> 
- <span data-ttu-id="36494-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="36494-1290">身份证</span></span> 
- <span data-ttu-id="36494-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="36494-1291">居民 身份证</span></span> 
- <span data-ttu-id="36494-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="36494-1292">居民身份证</span></span> 
- <span data-ttu-id="36494-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="36494-1293">鉴定</span></span> 
- <span data-ttu-id="36494-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="36494-1294">身分證</span></span> 
- <span data-ttu-id="36494-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="36494-1295">居民 身份證</span></span>
- <span data-ttu-id="36494-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="36494-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="36494-1297">Номер кредитной карты</span><span class="sxs-lookup"><span data-stu-id="36494-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1298">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1298">Format</span></span>

<span data-ttu-id="36494-1299">16 цифр, которые могут быть форматированными или неформатированными (цццццццццццццццц) и должны пройти проверку Луна.</span><span class="sxs-lookup"><span data-stu-id="36494-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1300">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1300">Pattern</span></span>

<span data-ttu-id="36494-1301">Очень сложный и надежный шаблон, который определяет карты всех основных мировых стандартов, включая Visa, MasterCard, Discover Card, JCB, American Express, подарочные карты и карты Diners Club.</span><span class="sxs-lookup"><span data-stu-id="36494-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1302">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1302">Checksum</span></span>

<span data-ttu-id="36494-1303">Да (рассчитывается по алгоритму Луна).</span><span class="sxs-lookup"><span data-stu-id="36494-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1304">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1304">Definition</span></span>

<span data-ttu-id="36494-1305">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1306">Функция Func_credit_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1307">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="36494-1307">One of the following is true:</span></span>
    - <span data-ttu-id="36494-1308">найдено ключевое слово из Keyword_cc_verification;</span><span class="sxs-lookup"><span data-stu-id="36494-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="36494-1309">найдено ключевое слово из Keyword_cc_name;</span><span class="sxs-lookup"><span data-stu-id="36494-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="36494-1310">функция Func_expiration_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="36494-1311">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1311">The checksum passes.</span></span>

<span data-ttu-id="36494-1312">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1313">функция Func_credit_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1314">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1314">The checksum passes.</span></span>

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1315">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="36494-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="36494-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="36494-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="36494-1317">card verification</span></span>
- <span data-ttu-id="36494-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="36494-1318">card identification number</span></span>
- <span data-ttu-id="36494-1319">квн</span><span class="sxs-lookup"><span data-stu-id="36494-1319">cvn</span></span>
- <span data-ttu-id="36494-1320">cid</span><span class="sxs-lookup"><span data-stu-id="36494-1320">cid</span></span>
- <span data-ttu-id="36494-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="36494-1321">cvc2</span></span>
- <span data-ttu-id="36494-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="36494-1322">cvv2</span></span>
- <span data-ttu-id="36494-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="36494-1323">pin block</span></span>
- <span data-ttu-id="36494-1324">security code</span><span class="sxs-lookup"><span data-stu-id="36494-1324">security code</span></span>
- <span data-ttu-id="36494-1325">security number</span><span class="sxs-lookup"><span data-stu-id="36494-1325">security number</span></span>
- <span data-ttu-id="36494-1326">security no</span><span class="sxs-lookup"><span data-stu-id="36494-1326">security no</span></span>
- <span data-ttu-id="36494-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="36494-1327">issue number</span></span>
- <span data-ttu-id="36494-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="36494-1328">issue no</span></span>
- <span data-ttu-id="36494-1329">криптограмме</span><span class="sxs-lookup"><span data-stu-id="36494-1329">cryptogramme</span></span>
- <span data-ttu-id="36494-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="36494-1330">numéro de sécurité</span></span>
- <span data-ttu-id="36494-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="36494-1331">numero de securite</span></span>
- <span data-ttu-id="36494-1332">кредиткартенпрüфнуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="36494-1333">кредиткартенпруфнуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="36494-1334">прüфзиффер</span><span class="sxs-lookup"><span data-stu-id="36494-1334">prüfziffer</span></span>
- <span data-ttu-id="36494-1335">пруфзиффер</span><span class="sxs-lookup"><span data-stu-id="36494-1335">prufziffer</span></span>
- <span data-ttu-id="36494-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="36494-1336">sicherheits Kode</span></span>
- <span data-ttu-id="36494-1337">сичерхеитскоде</span><span class="sxs-lookup"><span data-stu-id="36494-1337">sicherheitscode</span></span>
- <span data-ttu-id="36494-1338">сичерхеитснуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="36494-1339">верфаллдатум</span><span class="sxs-lookup"><span data-stu-id="36494-1339">verfalldatum</span></span>
- <span data-ttu-id="36494-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="36494-1340">codice di verifica</span></span>
- <span data-ttu-id="36494-1341">наложен.</span><span class="sxs-lookup"><span data-stu-id="36494-1341">cod.</span></span> <span data-ttu-id="36494-1342">сикурезза</span><span class="sxs-lookup"><span data-stu-id="36494-1342">sicurezza</span></span>
- <span data-ttu-id="36494-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="36494-1343">cod sicurezza</span></span>
- <span data-ttu-id="36494-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="36494-1344">n autorizzazione</span></span>
- <span data-ttu-id="36494-1345">кóдиго</span><span class="sxs-lookup"><span data-stu-id="36494-1345">código</span></span>
- <span data-ttu-id="36494-1346">кодиго</span><span class="sxs-lookup"><span data-stu-id="36494-1346">codigo</span></span>
- <span data-ttu-id="36494-1347">наложен.</span><span class="sxs-lookup"><span data-stu-id="36494-1347">cod.</span></span> <span data-ttu-id="36494-1348">сег</span><span class="sxs-lookup"><span data-stu-id="36494-1348">seg</span></span>
- <span data-ttu-id="36494-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="36494-1349">cod seg</span></span>
- <span data-ttu-id="36494-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="36494-1350">código de segurança</span></span>
- <span data-ttu-id="36494-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="36494-1351">codigo de seguranca</span></span>
- <span data-ttu-id="36494-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="36494-1352">codigo de segurança</span></span>
- <span data-ttu-id="36494-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="36494-1353">código de seguranca</span></span>
- <span data-ttu-id="36494-1354">кóд.</span><span class="sxs-lookup"><span data-stu-id="36494-1354">cód.</span></span> <span data-ttu-id="36494-1355">сегуранçа</span><span class="sxs-lookup"><span data-stu-id="36494-1355">segurança</span></span>
- <span data-ttu-id="36494-1356">наложен.</span><span class="sxs-lookup"><span data-stu-id="36494-1356">cod.</span></span> <span data-ttu-id="36494-1357">сегуранка наложенный платеж.</span><span class="sxs-lookup"><span data-stu-id="36494-1357">seguranca cod.</span></span> <span data-ttu-id="36494-1358">сегуранçа</span><span class="sxs-lookup"><span data-stu-id="36494-1358">segurança</span></span>
- <span data-ttu-id="36494-1359">кóд.</span><span class="sxs-lookup"><span data-stu-id="36494-1359">cód.</span></span> <span data-ttu-id="36494-1360">сегуранка</span><span class="sxs-lookup"><span data-stu-id="36494-1360">seguranca</span></span>
- <span data-ttu-id="36494-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="36494-1361">cód segurança</span></span>
- <span data-ttu-id="36494-1362">наложенный на наложенный сегуранка сегуранçа</span><span class="sxs-lookup"><span data-stu-id="36494-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="36494-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="36494-1363">cód seguranca</span></span>
- <span data-ttu-id="36494-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="36494-1364">número de verificação</span></span>
- <span data-ttu-id="36494-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="36494-1365">numero de verificacao</span></span>
- <span data-ttu-id="36494-1366">аблауф</span><span class="sxs-lookup"><span data-stu-id="36494-1366">ablauf</span></span>
- <span data-ttu-id="36494-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="36494-1367">gültig bis</span></span>
- <span data-ttu-id="36494-1368">гüлтигкеитсдатум</span><span class="sxs-lookup"><span data-stu-id="36494-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="36494-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="36494-1369">gultig bis</span></span>
- <span data-ttu-id="36494-1370">гултигкеитсдатум</span><span class="sxs-lookup"><span data-stu-id="36494-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="36494-1371">скаденза</span><span class="sxs-lookup"><span data-stu-id="36494-1371">scadenza</span></span>
- <span data-ttu-id="36494-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="36494-1372">data scad</span></span>
- <span data-ttu-id="36494-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="36494-1373">fecha de expiracion</span></span>
- <span data-ttu-id="36494-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="36494-1374">fecha de venc</span></span>
- <span data-ttu-id="36494-1375">венЦимиенто</span><span class="sxs-lookup"><span data-stu-id="36494-1375">vencimiento</span></span>
- <span data-ttu-id="36494-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="36494-1376">válido hasta</span></span>
- <span data-ttu-id="36494-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="36494-1377">valido hasta</span></span>
- <span data-ttu-id="36494-1378">вто</span><span class="sxs-lookup"><span data-stu-id="36494-1378">vto</span></span>
- <span data-ttu-id="36494-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="36494-1379">data de expiração</span></span>
- <span data-ttu-id="36494-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="36494-1380">data de expiracao</span></span>
- <span data-ttu-id="36494-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="36494-1381">data em que expira</span></span>
- <span data-ttu-id="36494-1382">валидаде</span><span class="sxs-lookup"><span data-stu-id="36494-1382">validade</span></span>
- <span data-ttu-id="36494-1383">валор</span><span class="sxs-lookup"><span data-stu-id="36494-1383">valor</span></span>
- <span data-ttu-id="36494-1384">венЦименто</span><span class="sxs-lookup"><span data-stu-id="36494-1384">vencimento</span></span>
- <span data-ttu-id="36494-1385">венк</span><span class="sxs-lookup"><span data-stu-id="36494-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="36494-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="36494-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="36494-1387">амекс</span><span class="sxs-lookup"><span data-stu-id="36494-1387">amex</span></span>
- <span data-ttu-id="36494-1388">american express</span><span class="sxs-lookup"><span data-stu-id="36494-1388">american express</span></span>
- <span data-ttu-id="36494-1389">американекспресс</span><span class="sxs-lookup"><span data-stu-id="36494-1389">americanexpress</span></span>
- <span data-ttu-id="36494-1390">Visa</span><span class="sxs-lookup"><span data-stu-id="36494-1390">Visa</span></span>
- <span data-ttu-id="36494-1391">MasterCard</span><span class="sxs-lookup"><span data-stu-id="36494-1391">mastercard</span></span>
- <span data-ttu-id="36494-1392">master card</span><span class="sxs-lookup"><span data-stu-id="36494-1392">master card</span></span>
- <span data-ttu-id="36494-1393">MC</span><span class="sxs-lookup"><span data-stu-id="36494-1393">mc</span></span> 
- <span data-ttu-id="36494-1394">мастеркардс</span><span class="sxs-lookup"><span data-stu-id="36494-1394">mastercards</span></span>
- <span data-ttu-id="36494-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="36494-1395">master cards</span></span>
- <span data-ttu-id="36494-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="36494-1396">diner's Club</span></span>
- <span data-ttu-id="36494-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="36494-1397">diners club</span></span>
- <span data-ttu-id="36494-1398">динерсклуб</span><span class="sxs-lookup"><span data-stu-id="36494-1398">dinersclub</span></span>
- <span data-ttu-id="36494-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="36494-1399">discover card</span></span>
- <span data-ttu-id="36494-1400">дисковеркард</span><span class="sxs-lookup"><span data-stu-id="36494-1400">discovercard</span></span>
- <span data-ttu-id="36494-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="36494-1401">discover cards</span></span>
- <span data-ttu-id="36494-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="36494-1402">JCB</span></span>
- <span data-ttu-id="36494-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="36494-1403">japanese card bureau</span></span>
- <span data-ttu-id="36494-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="36494-1404">carte blanche</span></span>
- <span data-ttu-id="36494-1405">картебланче</span><span class="sxs-lookup"><span data-stu-id="36494-1405">carteblanche</span></span>
- <span data-ttu-id="36494-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="36494-1406">credit card</span></span>
- <span data-ttu-id="36494-1407">Центральной #</span><span class="sxs-lookup"><span data-stu-id="36494-1407">cc#</span></span>
- <span data-ttu-id="36494-1408">CC #:</span><span class="sxs-lookup"><span data-stu-id="36494-1408">cc#:</span></span>
- <span data-ttu-id="36494-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="36494-1409">expiration date</span></span>
- <span data-ttu-id="36494-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="36494-1410">exp date</span></span>
- <span data-ttu-id="36494-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="36494-1411">expiry date</span></span>
- <span data-ttu-id="36494-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="36494-1412">date d’expiration</span></span>
- <span data-ttu-id="36494-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="36494-1413">date d'exp</span></span>
- <span data-ttu-id="36494-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="36494-1414">date expiration</span></span>
- <span data-ttu-id="36494-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="36494-1415">bank card</span></span>
- <span data-ttu-id="36494-1416">банккард</span><span class="sxs-lookup"><span data-stu-id="36494-1416">bankcard</span></span>
- <span data-ttu-id="36494-1417">card number</span><span class="sxs-lookup"><span data-stu-id="36494-1417">card number</span></span>
- <span data-ttu-id="36494-1418">card num</span><span class="sxs-lookup"><span data-stu-id="36494-1418">card num</span></span>
- <span data-ttu-id="36494-1419">карднумбер</span><span class="sxs-lookup"><span data-stu-id="36494-1419">cardnumber</span></span>
- <span data-ttu-id="36494-1420">карднумберс</span><span class="sxs-lookup"><span data-stu-id="36494-1420">cardnumbers</span></span>
- <span data-ttu-id="36494-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="36494-1421">card numbers</span></span>
- <span data-ttu-id="36494-1422">кредиткард</span><span class="sxs-lookup"><span data-stu-id="36494-1422">creditcard</span></span>
- <span data-ttu-id="36494-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="36494-1423">credit cards</span></span>
- <span data-ttu-id="36494-1424">кредиткардс</span><span class="sxs-lookup"><span data-stu-id="36494-1424">creditcards</span></span>
- <span data-ttu-id="36494-1425">CCN</span><span class="sxs-lookup"><span data-stu-id="36494-1425">ccn</span></span>
- <span data-ttu-id="36494-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="36494-1426">card holder</span></span>
- <span data-ttu-id="36494-1427">банков</span><span class="sxs-lookup"><span data-stu-id="36494-1427">cardholder</span></span>
- <span data-ttu-id="36494-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="36494-1428">card holders</span></span>
- <span data-ttu-id="36494-1429">карты</span><span class="sxs-lookup"><span data-stu-id="36494-1429">cardholders</span></span>
- <span data-ttu-id="36494-1430">check card</span><span class="sxs-lookup"><span data-stu-id="36494-1430">check card</span></span>
- <span data-ttu-id="36494-1431">чекккард</span><span class="sxs-lookup"><span data-stu-id="36494-1431">checkcard</span></span>
- <span data-ttu-id="36494-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="36494-1432">check cards</span></span>
- <span data-ttu-id="36494-1433">чекккардс</span><span class="sxs-lookup"><span data-stu-id="36494-1433">checkcards</span></span>
- <span data-ttu-id="36494-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="36494-1434">debit card</span></span>
- <span data-ttu-id="36494-1435">дебиткард</span><span class="sxs-lookup"><span data-stu-id="36494-1435">debitcard</span></span>
- <span data-ttu-id="36494-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="36494-1436">debit cards</span></span>
- <span data-ttu-id="36494-1437">дебиткардс</span><span class="sxs-lookup"><span data-stu-id="36494-1437">debitcards</span></span>
- <span data-ttu-id="36494-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="36494-1438">atm card</span></span>
- <span data-ttu-id="36494-1439">атмкард</span><span class="sxs-lookup"><span data-stu-id="36494-1439">atmcard</span></span>
- <span data-ttu-id="36494-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="36494-1440">atm cards</span></span>
- <span data-ttu-id="36494-1441">атмкардс</span><span class="sxs-lookup"><span data-stu-id="36494-1441">atmcards</span></span>
- <span data-ttu-id="36494-1442">енрауте</span><span class="sxs-lookup"><span data-stu-id="36494-1442">enroute</span></span>
- <span data-ttu-id="36494-1443">en route</span><span class="sxs-lookup"><span data-stu-id="36494-1443">en route</span></span>
- <span data-ttu-id="36494-1444">card type</span><span class="sxs-lookup"><span data-stu-id="36494-1444">card type</span></span>
- <span data-ttu-id="36494-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="36494-1445">carte bancaire</span></span>
- <span data-ttu-id="36494-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="36494-1446">carte de crédit</span></span>
- <span data-ttu-id="36494-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="36494-1447">carte de credit</span></span>
- <span data-ttu-id="36494-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="36494-1448">numéro de carte</span></span>
- <span data-ttu-id="36494-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="36494-1449">numero de carte</span></span>
- <span data-ttu-id="36494-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="36494-1450">nº de la carte</span></span>
- <span data-ttu-id="36494-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="36494-1451">nº de carte</span></span>
- <span data-ttu-id="36494-1452">кредиткарте</span><span class="sxs-lookup"><span data-stu-id="36494-1452">kreditkarte</span></span>
- <span data-ttu-id="36494-1453">карте</span><span class="sxs-lookup"><span data-stu-id="36494-1453">karte</span></span>
- <span data-ttu-id="36494-1454">картенинхабер</span><span class="sxs-lookup"><span data-stu-id="36494-1454">karteninhaber</span></span>
- <span data-ttu-id="36494-1455">картенинхаберс</span><span class="sxs-lookup"><span data-stu-id="36494-1455">karteninhabers</span></span>
- <span data-ttu-id="36494-1456">кредиткартенинхабер</span><span class="sxs-lookup"><span data-stu-id="36494-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="36494-1457">кредиткартенинститут</span><span class="sxs-lookup"><span data-stu-id="36494-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="36494-1458">кредиткартентип</span><span class="sxs-lookup"><span data-stu-id="36494-1458">kreditkartentyp</span></span>
- <span data-ttu-id="36494-1459">еижентüмернаме</span><span class="sxs-lookup"><span data-stu-id="36494-1459">eigentümername</span></span>
- <span data-ttu-id="36494-1460">картеннр</span><span class="sxs-lookup"><span data-stu-id="36494-1460">kartennr</span></span> 
- <span data-ttu-id="36494-1461">картеннуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1461">kartennummer</span></span>
- <span data-ttu-id="36494-1462">кредиткартеннуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1462">kreditkartennummer</span></span>
- <span data-ttu-id="36494-1463">кредиткартен — нуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="36494-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="36494-1464">carta di credito</span></span>
- <span data-ttu-id="36494-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="36494-1465">carta credito</span></span>
- <span data-ttu-id="36494-1466">Корзина "</span><span class="sxs-lookup"><span data-stu-id="36494-1466">carta</span></span>
- <span data-ttu-id="36494-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="36494-1467">n carta</span></span>
- <span data-ttu-id="36494-1468">НР.</span><span class="sxs-lookup"><span data-stu-id="36494-1468">nr.</span></span> <span data-ttu-id="36494-1469">Корзина "</span><span class="sxs-lookup"><span data-stu-id="36494-1469">carta</span></span>
- <span data-ttu-id="36494-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="36494-1470">nr carta</span></span>
- <span data-ttu-id="36494-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="36494-1471">numero carta</span></span>
- <span data-ttu-id="36494-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="36494-1472">numero della carta</span></span>
- <span data-ttu-id="36494-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="36494-1473">numero di carta</span></span>
- <span data-ttu-id="36494-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="36494-1474">tarjeta credito</span></span>
- <span data-ttu-id="36494-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="36494-1475">tarjeta de credito</span></span>
- <span data-ttu-id="36494-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="36494-1476">tarjeta crédito</span></span>
- <span data-ttu-id="36494-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="36494-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="36494-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="36494-1478">tarjeta de atm</span></span>
- <span data-ttu-id="36494-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="36494-1479">tarjeta atm</span></span>
- <span data-ttu-id="36494-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="36494-1480">tarjeta debito</span></span>
- <span data-ttu-id="36494-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="36494-1481">tarjeta de debito</span></span>
- <span data-ttu-id="36494-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="36494-1482">tarjeta débito</span></span>
- <span data-ttu-id="36494-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="36494-1483">tarjeta de débito</span></span>
- <span data-ttu-id="36494-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="36494-1484">nº de tarjeta</span></span>
- <span data-ttu-id="36494-1485">Нет.</span><span class="sxs-lookup"><span data-stu-id="36494-1485">no.</span></span> <span data-ttu-id="36494-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="36494-1486">de tarjeta</span></span>
- <span data-ttu-id="36494-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="36494-1487">no de tarjeta</span></span>
- <span data-ttu-id="36494-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="36494-1488">numero de tarjeta</span></span>
- <span data-ttu-id="36494-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="36494-1489">número de tarjeta</span></span>
- <span data-ttu-id="36494-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="36494-1490">tarjeta no</span></span>
- <span data-ttu-id="36494-1491">таржетахабиенте</span><span class="sxs-lookup"><span data-stu-id="36494-1491">tarjetahabiente</span></span>
- <span data-ttu-id="36494-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="36494-1492">cartão de crédito</span></span>
- <span data-ttu-id="36494-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="36494-1493">cartão de credito</span></span>
- <span data-ttu-id="36494-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="36494-1494">cartao de crédito</span></span>
- <span data-ttu-id="36494-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="36494-1495">cartao de credito</span></span>
- <span data-ttu-id="36494-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="36494-1496">cartão de débito</span></span>
- <span data-ttu-id="36494-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="36494-1497">cartao de débito</span></span>
- <span data-ttu-id="36494-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="36494-1498">cartão de debito</span></span>
- <span data-ttu-id="36494-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="36494-1499">cartao de debito</span></span>
- <span data-ttu-id="36494-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="36494-1500">débito automático</span></span>
- <span data-ttu-id="36494-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="36494-1501">debito automatico</span></span>
- <span data-ttu-id="36494-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1502">número do cartão</span></span>
- <span data-ttu-id="36494-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1503">numero do cartão</span></span> 
- <span data-ttu-id="36494-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1504">número do cartao</span></span>
- <span data-ttu-id="36494-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1505">numero do cartao</span></span>
- <span data-ttu-id="36494-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1506">número de cartão</span></span>
- <span data-ttu-id="36494-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1507">numero de cartão</span></span>
- <span data-ttu-id="36494-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1508">número de cartao</span></span>
- <span data-ttu-id="36494-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1509">numero de cartao</span></span>
- <span data-ttu-id="36494-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1510">nº do cartão</span></span>
- <span data-ttu-id="36494-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1511">nº do cartao</span></span>
- <span data-ttu-id="36494-1512">n º.</span><span class="sxs-lookup"><span data-stu-id="36494-1512">nº.</span></span> <span data-ttu-id="36494-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1513">do cartão</span></span>
- <span data-ttu-id="36494-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1514">no do cartão</span></span>
- <span data-ttu-id="36494-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1515">no do cartao</span></span>
- <span data-ttu-id="36494-1516">Нет.</span><span class="sxs-lookup"><span data-stu-id="36494-1516">no.</span></span> <span data-ttu-id="36494-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1517">do cartão</span></span>
- <span data-ttu-id="36494-1518">Нет.</span><span class="sxs-lookup"><span data-stu-id="36494-1518">no.</span></span> <span data-ttu-id="36494-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="36494-1520">	Номер удостоверения личности для Хорватии</span><span class="sxs-lookup"><span data-stu-id="36494-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1521">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1521">Format</span></span>

<span data-ttu-id="36494-1522">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1523">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1523">Pattern</span></span>

<span data-ttu-id="36494-1524">Девять последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1525">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1525">Checksum</span></span>

<span data-ttu-id="36494-1526">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1527">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1527">Definition</span></span>

<span data-ttu-id="36494-1528">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1529">функция Func_croatia_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1530">находится ключевое слово из Keyword_croatia_id_card.</span><span class="sxs-lookup"><span data-stu-id="36494-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1531">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="36494-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="36494-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="36494-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="36494-1533">Croatian identity card</span></span>
- <span data-ttu-id="36494-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="36494-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="36494-1535">	Индивидуальный идентификационный номер (OIB) для Хорватии</span><span class="sxs-lookup"><span data-stu-id="36494-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1536">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1536">Format</span></span>

<span data-ttu-id="36494-1537">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1538">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1538">Pattern</span></span>

<span data-ttu-id="36494-1539">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-1539">11 digits:</span></span>
- <span data-ttu-id="36494-1540">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1540">10 digits</span></span> 
- <span data-ttu-id="36494-1541">Последняя цифра — контрольная цифра для международного обмена данными, буквы добавляются до одиннадцати цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1542">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1542">Checksum</span></span>

<span data-ttu-id="36494-1543">Да</span><span class="sxs-lookup"><span data-stu-id="36494-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1544">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1544">Definition</span></span>

<span data-ttu-id="36494-1545">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1546">функция Func_croatia_oib_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1547">находится ключевое слово из Keyword_croatia_oib_number;</span><span class="sxs-lookup"><span data-stu-id="36494-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="36494-1548">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1548">The checksum passes.</span></span>

<span data-ttu-id="36494-1549">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1550">функция Func_croatia_oib_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1551">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1551">The checksum passes.</span></span>

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1552">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="36494-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="36494-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="36494-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="36494-1554">Personal Identification Number</span></span>
- <span data-ttu-id="36494-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="36494-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="36494-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="36494-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="36494-1557">Номер личного удостоверения для чешского языка</span><span class="sxs-lookup"><span data-stu-id="36494-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1558">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1558">Format</span></span>

<span data-ttu-id="36494-1559">Девять цифр с необязательной косой чертой (старый формат) 10 цифрами с необязательной косой чертой (новый формат)</span><span class="sxs-lookup"><span data-stu-id="36494-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1560">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1560">Pattern</span></span>

<span data-ttu-id="36494-1561">Девять цифр (старый формат):</span><span class="sxs-lookup"><span data-stu-id="36494-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="36494-1562">девять цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1562">Nine digits</span></span>

<span data-ttu-id="36494-1563">OR</span><span class="sxs-lookup"><span data-stu-id="36494-1563">OR</span></span>

- <span data-ttu-id="36494-1564">Шесть цифр, представляющих дату рождения</span><span class="sxs-lookup"><span data-stu-id="36494-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="36494-1565">косая черта;</span><span class="sxs-lookup"><span data-stu-id="36494-1565">A forward slash</span></span>
- <span data-ttu-id="36494-1566">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-1566">Three digits</span></span>

<span data-ttu-id="36494-1567">10 цифр (новый формат):</span><span class="sxs-lookup"><span data-stu-id="36494-1567">10 digits (new format):</span></span>
- <span data-ttu-id="36494-1568">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1568">10 digits</span></span>

<span data-ttu-id="36494-1569">OR</span><span class="sxs-lookup"><span data-stu-id="36494-1569">OR</span></span>

- <span data-ttu-id="36494-1570">Шесть цифр, представляющих дату рождения</span><span class="sxs-lookup"><span data-stu-id="36494-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="36494-1571">косая черта;</span><span class="sxs-lookup"><span data-stu-id="36494-1571">A forward slash</span></span> 
- <span data-ttu-id="36494-1572">Четыре цифры, где последняя цифра является контрольной цифрой</span><span class="sxs-lookup"><span data-stu-id="36494-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1573">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1573">Checksum</span></span>

<span data-ttu-id="36494-1574">Да</span><span class="sxs-lookup"><span data-stu-id="36494-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1575">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1575">Definition</span></span>

<span data-ttu-id="36494-1576">Политика защиты от потери данных — 85% уверенности, что она обнаружила этот тип конфиденциальной информации, если в пределах близости от 300 символов: функция Func_czech_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="36494-1577">находится ключевое слово из Keyword_czech_id_card;</span><span class="sxs-lookup"><span data-stu-id="36494-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="36494-1578">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="36494-1579">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1579">Keywords</span></span>

- <span data-ttu-id="36494-1580">номер личного удостоверения для чешского языка</span><span class="sxs-lookup"><span data-stu-id="36494-1580">czech personal identity number</span></span>
- <span data-ttu-id="36494-1581">Роднé číсло</span><span class="sxs-lookup"><span data-stu-id="36494-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="36494-1582">	Индивидуальный идентификационный номер для Дании</span><span class="sxs-lookup"><span data-stu-id="36494-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1583">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1583">Format</span></span>

<span data-ttu-id="36494-1584">10 цифр, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="36494-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1585">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1585">Pattern</span></span>

<span data-ttu-id="36494-1586">10 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-1586">10 digits:</span></span>
- <span data-ttu-id="36494-1587">шесть цифр в формате ДДММГГ — дата рождения;</span><span class="sxs-lookup"><span data-stu-id="36494-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="36494-1588">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-1588">A hyphen</span></span> 
- <span data-ttu-id="36494-1589">четыре цифры, где последняя цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="36494-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1590">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1590">Checksum</span></span>

<span data-ttu-id="36494-1591">Да</span><span class="sxs-lookup"><span data-stu-id="36494-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1592">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1592">Definition</span></span>

<span data-ttu-id="36494-1593">Политика защиты от потери данных — 75% уверенности в том, что этот тип конфиденциальной информации обнаружен, если в пределах близости от 300 символов: регулярное выражение Regex_denmark_id находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="36494-1594">находится ключевое слово из Keyword_denmark_id;</span><span class="sxs-lookup"><span data-stu-id="36494-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="36494-1595">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1596">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="36494-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="36494-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="36494-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="36494-1598">Personal Identification Number</span></span>
- <span data-ttu-id="36494-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="36494-1599">CPR</span></span>
- <span data-ttu-id="36494-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="36494-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="36494-1601">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="36494-1602">Номер Управления по борьбе с наркотиками США (DEA)</span><span class="sxs-lookup"><span data-stu-id="36494-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1603">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1603">Format</span></span>

<span data-ttu-id="36494-1604">Две буквы, за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1605">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1605">Pattern</span></span>

<span data-ttu-id="36494-1606">Шаблон должен включать в себя все указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="36494-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="36494-1607">Одна буква (без учета регистра) из следующего набора: abcdefghjklmnprstux, представляющая собой код регистрирующегося лица</span><span class="sxs-lookup"><span data-stu-id="36494-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="36494-1608">Одна буква (без учета регистра), представляющая собой первую букву фамилии регистрирующегося лица</span><span class="sxs-lookup"><span data-stu-id="36494-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="36494-1609">Семь цифр, последняя из которых — контрольная</span><span class="sxs-lookup"><span data-stu-id="36494-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1610">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1610">Checksum</span></span>

<span data-ttu-id="36494-1611">Да</span><span class="sxs-lookup"><span data-stu-id="36494-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1612">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1612">Definition</span></span>

<span data-ttu-id="36494-1613">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1614">функция Func_dea_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1615">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1616">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1616">Keywords</span></span>

<span data-ttu-id="36494-1617">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="36494-1618">Номер банковской карты для ЕС</span><span class="sxs-lookup"><span data-stu-id="36494-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1619">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1619">Format</span></span>

<span data-ttu-id="36494-1620">16 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1621">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1621">Pattern</span></span>

<span data-ttu-id="36494-1622">Очень сложный и надежный шаблон.</span><span class="sxs-lookup"><span data-stu-id="36494-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1623">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1623">Checksum</span></span>

<span data-ttu-id="36494-1624">Да</span><span class="sxs-lookup"><span data-stu-id="36494-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1625">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1625">Definition</span></span>

<span data-ttu-id="36494-1626">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1627">Функция Func_eu_debit_card находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1628">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="36494-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="36494-1629">найдено ключевое слово из Keyword_eu_debit_card;</span><span class="sxs-lookup"><span data-stu-id="36494-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="36494-1630">найдено ключевое слово из Keyword_card_terms_dict;</span><span class="sxs-lookup"><span data-stu-id="36494-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="36494-1631">найдено ключевое слово из Keyword_card_security_terms_dict;</span><span class="sxs-lookup"><span data-stu-id="36494-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="36494-1632">найдено ключевое слово из Keyword_card_expiration_terms_dict;</span><span class="sxs-lookup"><span data-stu-id="36494-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="36494-1633">функция Func_expiration_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="36494-1634">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1634">The checksum passes.</span></span>

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1635">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="36494-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="36494-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="36494-1637">account number</span><span class="sxs-lookup"><span data-stu-id="36494-1637">account number</span></span> 
- <span data-ttu-id="36494-1638">card number</span><span class="sxs-lookup"><span data-stu-id="36494-1638">card number</span></span> 
- <span data-ttu-id="36494-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="36494-1639">card no.</span></span> 
- <span data-ttu-id="36494-1640">security number</span><span class="sxs-lookup"><span data-stu-id="36494-1640">security number</span></span> 
- <span data-ttu-id="36494-1641">Центральной #</span><span class="sxs-lookup"><span data-stu-id="36494-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="36494-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="36494-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="36494-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="36494-1643">acct nbr</span></span> 
- <span data-ttu-id="36494-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="36494-1644">acct num</span></span> 
- <span data-ttu-id="36494-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="36494-1645">acct no</span></span> 
- <span data-ttu-id="36494-1646">american express</span><span class="sxs-lookup"><span data-stu-id="36494-1646">american express</span></span> 
- <span data-ttu-id="36494-1647">американекспресс</span><span class="sxs-lookup"><span data-stu-id="36494-1647">americanexpress</span></span> 
- <span data-ttu-id="36494-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="36494-1648">americano espresso</span></span> 
- <span data-ttu-id="36494-1649">амекс</span><span class="sxs-lookup"><span data-stu-id="36494-1649">amex</span></span> 
- <span data-ttu-id="36494-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="36494-1650">atm card</span></span> 
- <span data-ttu-id="36494-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="36494-1651">atm cards</span></span> 
- <span data-ttu-id="36494-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="36494-1652">atm kaart</span></span> 
- <span data-ttu-id="36494-1653">атмкард</span><span class="sxs-lookup"><span data-stu-id="36494-1653">atmcard</span></span> 
- <span data-ttu-id="36494-1654">атмкардс</span><span class="sxs-lookup"><span data-stu-id="36494-1654">atmcards</span></span> 
- <span data-ttu-id="36494-1655">атмкаарт</span><span class="sxs-lookup"><span data-stu-id="36494-1655">atmkaart</span></span> 
- <span data-ttu-id="36494-1656">атмкаартен</span><span class="sxs-lookup"><span data-stu-id="36494-1656">atmkaarten</span></span> 
- <span data-ttu-id="36494-1657">банконтакт</span><span class="sxs-lookup"><span data-stu-id="36494-1657">bancontact</span></span> 
- <span data-ttu-id="36494-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="36494-1658">bank card</span></span> 
- <span data-ttu-id="36494-1659">банккаарт</span><span class="sxs-lookup"><span data-stu-id="36494-1659">bankkaart</span></span> 
- <span data-ttu-id="36494-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="36494-1660">card holder</span></span> 
- <span data-ttu-id="36494-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="36494-1661">card holders</span></span> 
- <span data-ttu-id="36494-1662">card num</span><span class="sxs-lookup"><span data-stu-id="36494-1662">card num</span></span> 
- <span data-ttu-id="36494-1663">card number</span><span class="sxs-lookup"><span data-stu-id="36494-1663">card number</span></span> 
- <span data-ttu-id="36494-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="36494-1664">card numbers</span></span> 
- <span data-ttu-id="36494-1665">card type</span><span class="sxs-lookup"><span data-stu-id="36494-1665">card type</span></span> 
- <span data-ttu-id="36494-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="36494-1666">cardano numerico</span></span> 
- <span data-ttu-id="36494-1667">банков</span><span class="sxs-lookup"><span data-stu-id="36494-1667">cardholder</span></span> 
- <span data-ttu-id="36494-1668">карты</span><span class="sxs-lookup"><span data-stu-id="36494-1668">cardholders</span></span> 
- <span data-ttu-id="36494-1669">карднумбер</span><span class="sxs-lookup"><span data-stu-id="36494-1669">cardnumber</span></span> 
- <span data-ttu-id="36494-1670">карднумберс</span><span class="sxs-lookup"><span data-stu-id="36494-1670">cardnumbers</span></span> 
- <span data-ttu-id="36494-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="36494-1671">carta bianca</span></span> 
- <span data-ttu-id="36494-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="36494-1672">carta credito</span></span> 
- <span data-ttu-id="36494-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="36494-1673">carta di credito</span></span> 
- <span data-ttu-id="36494-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="36494-1674">cartao de credito</span></span> 
- <span data-ttu-id="36494-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="36494-1675">cartao de crédito</span></span> 
- <span data-ttu-id="36494-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="36494-1676">cartao de debito</span></span> 
- <span data-ttu-id="36494-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="36494-1677">cartao de débito</span></span> 
- <span data-ttu-id="36494-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="36494-1678">carte bancaire</span></span> 
- <span data-ttu-id="36494-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="36494-1679">carte blanche</span></span> 
- <span data-ttu-id="36494-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="36494-1680">carte bleue</span></span> 
- <span data-ttu-id="36494-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="36494-1681">carte de credit</span></span> 
- <span data-ttu-id="36494-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="36494-1682">carte de crédit</span></span> 
- <span data-ttu-id="36494-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="36494-1683">carte di credito</span></span> 
- <span data-ttu-id="36494-1684">картебланче</span><span class="sxs-lookup"><span data-stu-id="36494-1684">carteblanche</span></span> 
- <span data-ttu-id="36494-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="36494-1685">cartão de credito</span></span> 
- <span data-ttu-id="36494-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="36494-1686">cartão de crédito</span></span> 
- <span data-ttu-id="36494-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="36494-1687">cartão de debito</span></span> 
- <span data-ttu-id="36494-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="36494-1688">cartão de débito</span></span> 
- <span data-ttu-id="36494-1689">cb</span><span class="sxs-lookup"><span data-stu-id="36494-1689">cb</span></span> 
- <span data-ttu-id="36494-1690">CCN</span><span class="sxs-lookup"><span data-stu-id="36494-1690">ccn</span></span> 
- <span data-ttu-id="36494-1691">check card</span><span class="sxs-lookup"><span data-stu-id="36494-1691">check card</span></span> 
- <span data-ttu-id="36494-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="36494-1692">check cards</span></span> 
- <span data-ttu-id="36494-1693">чекккард</span><span class="sxs-lookup"><span data-stu-id="36494-1693">checkcard</span></span>
- <span data-ttu-id="36494-1694">чекккардс</span><span class="sxs-lookup"><span data-stu-id="36494-1694">checkcards</span></span> 
- <span data-ttu-id="36494-1695">чекуекаарт</span><span class="sxs-lookup"><span data-stu-id="36494-1695">chequekaart</span></span> 
- <span data-ttu-id="36494-1696">Logic</span><span class="sxs-lookup"><span data-stu-id="36494-1696">cirrus</span></span> 
- <span data-ttu-id="36494-1697">Cirrus центр EDC — Маестро</span><span class="sxs-lookup"><span data-stu-id="36494-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="36494-1698">контролекаарт</span><span class="sxs-lookup"><span data-stu-id="36494-1698">controlekaart</span></span> 
- <span data-ttu-id="36494-1699">контролекаартен</span><span class="sxs-lookup"><span data-stu-id="36494-1699">controlekaarten</span></span> 
- <span data-ttu-id="36494-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="36494-1700">credit card</span></span> 
- <span data-ttu-id="36494-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="36494-1701">credit cards</span></span> 
- <span data-ttu-id="36494-1702">кредиткард</span><span class="sxs-lookup"><span data-stu-id="36494-1702">creditcard</span></span> 
- <span data-ttu-id="36494-1703">кредиткардс</span><span class="sxs-lookup"><span data-stu-id="36494-1703">creditcards</span></span> 
- <span data-ttu-id="36494-1704">дебеткаарт</span><span class="sxs-lookup"><span data-stu-id="36494-1704">debetkaart</span></span> 
- <span data-ttu-id="36494-1705">дебеткаартен</span><span class="sxs-lookup"><span data-stu-id="36494-1705">debetkaarten</span></span> 
- <span data-ttu-id="36494-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="36494-1706">debit card</span></span> 
- <span data-ttu-id="36494-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="36494-1707">debit cards</span></span> 
- <span data-ttu-id="36494-1708">дебиткард</span><span class="sxs-lookup"><span data-stu-id="36494-1708">debitcard</span></span> 
- <span data-ttu-id="36494-1709">дебиткардс</span><span class="sxs-lookup"><span data-stu-id="36494-1709">debitcards</span></span> 
- <span data-ttu-id="36494-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="36494-1710">debito automatico</span></span> 
- <span data-ttu-id="36494-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="36494-1711">diners club</span></span> 
- <span data-ttu-id="36494-1712">динерсклуб</span><span class="sxs-lookup"><span data-stu-id="36494-1712">dinersclub</span></span> 
- <span data-ttu-id="36494-1713">Повтор</span><span class="sxs-lookup"><span data-stu-id="36494-1713">discover</span></span> 
- <span data-ttu-id="36494-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="36494-1714">discover card</span></span> 
- <span data-ttu-id="36494-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="36494-1715">discover cards</span></span> 
- <span data-ttu-id="36494-1716">дисковеркард</span><span class="sxs-lookup"><span data-stu-id="36494-1716">discovercard</span></span> 
- <span data-ttu-id="36494-1717">дисковеркардс</span><span class="sxs-lookup"><span data-stu-id="36494-1717">discovercards</span></span> 
- <span data-ttu-id="36494-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="36494-1718">débito automático</span></span>
- <span data-ttu-id="36494-1719">центр EDC</span><span class="sxs-lookup"><span data-stu-id="36494-1719">edc</span></span> 
- <span data-ttu-id="36494-1720">еижентüмернаме</span><span class="sxs-lookup"><span data-stu-id="36494-1720">eigentümername</span></span> 
- <span data-ttu-id="36494-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="36494-1721">european debit card</span></span> 
- <span data-ttu-id="36494-1722">хуфдкаарт</span><span class="sxs-lookup"><span data-stu-id="36494-1722">hoofdkaart</span></span> 
- <span data-ttu-id="36494-1723">хуфдкаартен</span><span class="sxs-lookup"><span data-stu-id="36494-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="36494-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="36494-1724">in viaggio</span></span> 
- <span data-ttu-id="36494-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="36494-1725">japanese card bureau</span></span> 
- <span data-ttu-id="36494-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="36494-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="36494-1727">JCB</span><span class="sxs-lookup"><span data-stu-id="36494-1727">jcb</span></span> 
- <span data-ttu-id="36494-1728">каарт</span><span class="sxs-lookup"><span data-stu-id="36494-1728">kaart</span></span> 
- <span data-ttu-id="36494-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="36494-1729">kaart num</span></span> 
- <span data-ttu-id="36494-1730">каартаантал</span><span class="sxs-lookup"><span data-stu-id="36494-1730">kaartaantal</span></span> 
- <span data-ttu-id="36494-1731">каартаанталлен</span><span class="sxs-lookup"><span data-stu-id="36494-1731">kaartaantallen</span></span> 
- <span data-ttu-id="36494-1732">каарсаудер</span><span class="sxs-lookup"><span data-stu-id="36494-1732">kaarthouder</span></span> 
- <span data-ttu-id="36494-1733">каарсаудерс</span><span class="sxs-lookup"><span data-stu-id="36494-1733">kaarthouders</span></span> 
- <span data-ttu-id="36494-1734">карте</span><span class="sxs-lookup"><span data-stu-id="36494-1734">karte</span></span>  
- <span data-ttu-id="36494-1735">картенинхабер</span><span class="sxs-lookup"><span data-stu-id="36494-1735">karteninhaber</span></span> 
- <span data-ttu-id="36494-1736">картенинхаберс</span><span class="sxs-lookup"><span data-stu-id="36494-1736">karteninhabers</span></span>
- <span data-ttu-id="36494-1737">картеннр</span><span class="sxs-lookup"><span data-stu-id="36494-1737">kartennr</span></span> 
- <span data-ttu-id="36494-1738">картеннуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1738">kartennummer</span></span> 
- <span data-ttu-id="36494-1739">кредиткарте</span><span class="sxs-lookup"><span data-stu-id="36494-1739">kreditkarte</span></span> 
- <span data-ttu-id="36494-1740">кредиткартен — нуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="36494-1741">кредиткартенинхабер</span><span class="sxs-lookup"><span data-stu-id="36494-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="36494-1742">кредиткартенинститут</span><span class="sxs-lookup"><span data-stu-id="36494-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="36494-1743">кредиткартеннуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="36494-1744">кредиткартентип</span><span class="sxs-lookup"><span data-stu-id="36494-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="36494-1745">маестро</span><span class="sxs-lookup"><span data-stu-id="36494-1745">maestro</span></span> 
- <span data-ttu-id="36494-1746">master card</span><span class="sxs-lookup"><span data-stu-id="36494-1746">master card</span></span> 
- <span data-ttu-id="36494-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="36494-1747">master cards</span></span> 
- <span data-ttu-id="36494-1748">MasterCard</span><span class="sxs-lookup"><span data-stu-id="36494-1748">mastercard</span></span> 
- <span data-ttu-id="36494-1749">мастеркардс</span><span class="sxs-lookup"><span data-stu-id="36494-1749">mastercards</span></span> 
- <span data-ttu-id="36494-1750">MC</span><span class="sxs-lookup"><span data-stu-id="36494-1750">mc</span></span> 
- <span data-ttu-id="36494-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="36494-1751">mister cash</span></span> 
- <span data-ttu-id="36494-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="36494-1752">n carta</span></span> 
- <span data-ttu-id="36494-1753">Корзина "</span><span class="sxs-lookup"><span data-stu-id="36494-1753">carta</span></span> 
- <span data-ttu-id="36494-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="36494-1754">no de tarjeta</span></span> 
- <span data-ttu-id="36494-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1755">no do cartao</span></span> 
- <span data-ttu-id="36494-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1756">no do cartão</span></span> 
- <span data-ttu-id="36494-1757">Нет.</span><span class="sxs-lookup"><span data-stu-id="36494-1757">no.</span></span> <span data-ttu-id="36494-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="36494-1758">de tarjeta</span></span> 
- <span data-ttu-id="36494-1759">Нет.</span><span class="sxs-lookup"><span data-stu-id="36494-1759">no.</span></span> <span data-ttu-id="36494-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1760">do cartao</span></span> 
- <span data-ttu-id="36494-1761">Нет.</span><span class="sxs-lookup"><span data-stu-id="36494-1761">no.</span></span> <span data-ttu-id="36494-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1762">do cartão</span></span> 
- <span data-ttu-id="36494-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="36494-1763">nr carta</span></span> 
- <span data-ttu-id="36494-1764">НР.</span><span class="sxs-lookup"><span data-stu-id="36494-1764">nr.</span></span> <span data-ttu-id="36494-1765">Корзина "</span><span class="sxs-lookup"><span data-stu-id="36494-1765">carta</span></span> 
- <span data-ttu-id="36494-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="36494-1766">numeri di scheda</span></span> 
- <span data-ttu-id="36494-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="36494-1767">numero carta</span></span> 
- <span data-ttu-id="36494-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1768">numero de cartao</span></span> 
- <span data-ttu-id="36494-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="36494-1769">numero de carte</span></span> 
- <span data-ttu-id="36494-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1770">numero de cartão</span></span> 
- <span data-ttu-id="36494-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="36494-1771">numero de tarjeta</span></span>
- <span data-ttu-id="36494-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="36494-1772">numero della carta</span></span> 
- <span data-ttu-id="36494-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="36494-1773">numero di carta</span></span> 
- <span data-ttu-id="36494-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="36494-1774">numero di scheda</span></span> 
- <span data-ttu-id="36494-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1775">numero do cartao</span></span> 
- <span data-ttu-id="36494-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1776">numero do cartão</span></span> 
- <span data-ttu-id="36494-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="36494-1777">numéro de carte</span></span> 
- <span data-ttu-id="36494-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="36494-1778">nº carta</span></span> 
- <span data-ttu-id="36494-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="36494-1779">nº de carte</span></span> 
- <span data-ttu-id="36494-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="36494-1780">nº de la carte</span></span> 
- <span data-ttu-id="36494-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="36494-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="36494-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1782">nº do cartao</span></span> 
- <span data-ttu-id="36494-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1783">nº do cartão</span></span> 
- <span data-ttu-id="36494-1784">n º.</span><span class="sxs-lookup"><span data-stu-id="36494-1784">nº.</span></span> <span data-ttu-id="36494-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1785">do cartão</span></span> 
- <span data-ttu-id="36494-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1786">número de cartao</span></span> 
- <span data-ttu-id="36494-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="36494-1787">número de cartão</span></span> 
- <span data-ttu-id="36494-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="36494-1788">número de tarjeta</span></span> 
- <span data-ttu-id="36494-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="36494-1789">número do cartao</span></span> 
- <span data-ttu-id="36494-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="36494-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="36494-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="36494-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="36494-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="36494-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="36494-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="36494-1793">scheda della banca</span></span> 
- <span data-ttu-id="36494-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="36494-1794">scheda di controllo</span></span> 
- <span data-ttu-id="36494-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="36494-1795">scheda di debito</span></span> 
- <span data-ttu-id="36494-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="36494-1796">scheda matrice</span></span> 
- <span data-ttu-id="36494-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="36494-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="36494-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="36494-1798">schede di controllo</span></span> 
- <span data-ttu-id="36494-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="36494-1799">schede di debito</span></span> 
- <span data-ttu-id="36494-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="36494-1800">schede matrici</span></span> 
- <span data-ttu-id="36494-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="36494-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="36494-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="36494-1802">scoprono le schede</span></span> 
- <span data-ttu-id="36494-1803">ОС</span><span class="sxs-lookup"><span data-stu-id="36494-1803">solo</span></span> 
- <span data-ttu-id="36494-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="36494-1804">supporti di scheda</span></span> 
- <span data-ttu-id="36494-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="36494-1805">supporto di scheda</span></span> 
- <span data-ttu-id="36494-1806">отключен</span><span class="sxs-lookup"><span data-stu-id="36494-1806">switch</span></span> 
- <span data-ttu-id="36494-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="36494-1807">tarjeta atm</span></span> 
- <span data-ttu-id="36494-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="36494-1808">tarjeta credito</span></span> 
- <span data-ttu-id="36494-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="36494-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="36494-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="36494-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="36494-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="36494-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="36494-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="36494-1812">tarjeta debito</span></span> 
- <span data-ttu-id="36494-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="36494-1813">tarjeta no</span></span>
- <span data-ttu-id="36494-1814">таржетахабиенте</span><span class="sxs-lookup"><span data-stu-id="36494-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="36494-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="36494-1815">tipo della scheda</span></span> 
- <span data-ttu-id="36494-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="36494-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="36494-1817">счеда</span><span class="sxs-lookup"><span data-stu-id="36494-1817">scheda</span></span> 
- <span data-ttu-id="36494-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="36494-1818">v pay</span></span> 
- <span data-ttu-id="36494-1819">v — оплата</span><span class="sxs-lookup"><span data-stu-id="36494-1819">v-pay</span></span> 
- <span data-ttu-id="36494-1820">Visa</span><span class="sxs-lookup"><span data-stu-id="36494-1820">visa</span></span> 
- <span data-ttu-id="36494-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="36494-1821">visa plus</span></span> 
- <span data-ttu-id="36494-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="36494-1822">visa electron</span></span> 
- <span data-ttu-id="36494-1823">висто</span><span class="sxs-lookup"><span data-stu-id="36494-1823">visto</span></span> 
- <span data-ttu-id="36494-1824">висум</span><span class="sxs-lookup"><span data-stu-id="36494-1824">visum</span></span> 
- <span data-ttu-id="36494-1825">впай</span><span class="sxs-lookup"><span data-stu-id="36494-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="36494-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="36494-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="36494-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="36494-1827">card identification number</span></span>
- <span data-ttu-id="36494-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="36494-1828">card verification</span></span> 
- <span data-ttu-id="36494-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="36494-1829">cardi la verifica</span></span> 
- <span data-ttu-id="36494-1830">cid</span><span class="sxs-lookup"><span data-stu-id="36494-1830">cid</span></span> 
- <span data-ttu-id="36494-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="36494-1831">cod seg</span></span> 
- <span data-ttu-id="36494-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="36494-1832">cod seguranca</span></span> 
- <span data-ttu-id="36494-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="36494-1833">cod segurança</span></span> 
- <span data-ttu-id="36494-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="36494-1834">cod sicurezza</span></span> 
- <span data-ttu-id="36494-1835">наложен.</span><span class="sxs-lookup"><span data-stu-id="36494-1835">cod.</span></span> <span data-ttu-id="36494-1836">сег</span><span class="sxs-lookup"><span data-stu-id="36494-1836">seg</span></span> 
- <span data-ttu-id="36494-1837">наложен.</span><span class="sxs-lookup"><span data-stu-id="36494-1837">cod.</span></span> <span data-ttu-id="36494-1838">сегуранка</span><span class="sxs-lookup"><span data-stu-id="36494-1838">seguranca</span></span> 
- <span data-ttu-id="36494-1839">наложен.</span><span class="sxs-lookup"><span data-stu-id="36494-1839">cod.</span></span> <span data-ttu-id="36494-1840">сегуранçа</span><span class="sxs-lookup"><span data-stu-id="36494-1840">segurança</span></span> 
- <span data-ttu-id="36494-1841">наложен.</span><span class="sxs-lookup"><span data-stu-id="36494-1841">cod.</span></span> <span data-ttu-id="36494-1842">сикурезза</span><span class="sxs-lookup"><span data-stu-id="36494-1842">sicurezza</span></span> 
- <span data-ttu-id="36494-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="36494-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="36494-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="36494-1844">codice di verifica</span></span> 
- <span data-ttu-id="36494-1845">кодиго</span><span class="sxs-lookup"><span data-stu-id="36494-1845">codigo</span></span> 
- <span data-ttu-id="36494-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="36494-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="36494-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="36494-1847">codigo de segurança</span></span> 
- <span data-ttu-id="36494-1848">криттограмма</span><span class="sxs-lookup"><span data-stu-id="36494-1848">crittogramma</span></span> 
- <span data-ttu-id="36494-1849">криптограм</span><span class="sxs-lookup"><span data-stu-id="36494-1849">cryptogram</span></span> 
- <span data-ttu-id="36494-1850">криптограмме</span><span class="sxs-lookup"><span data-stu-id="36494-1850">cryptogramme</span></span> 
- <span data-ttu-id="36494-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="36494-1851">cv2</span></span> 
- <span data-ttu-id="36494-1852">квк</span><span class="sxs-lookup"><span data-stu-id="36494-1852">cvc</span></span> 
- <span data-ttu-id="36494-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="36494-1853">cvc2</span></span> 
- <span data-ttu-id="36494-1854">квн</span><span class="sxs-lookup"><span data-stu-id="36494-1854">cvn</span></span> 
- <span data-ttu-id="36494-1855">квв</span><span class="sxs-lookup"><span data-stu-id="36494-1855">cvv</span></span> 
- <span data-ttu-id="36494-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="36494-1856">cvv2</span></span> 
- <span data-ttu-id="36494-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="36494-1857">cód seguranca</span></span> 
- <span data-ttu-id="36494-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="36494-1858">cód segurança</span></span> 
- <span data-ttu-id="36494-1859">кóд.</span><span class="sxs-lookup"><span data-stu-id="36494-1859">cód.</span></span> <span data-ttu-id="36494-1860">сегуранка</span><span class="sxs-lookup"><span data-stu-id="36494-1860">seguranca</span></span> 
- <span data-ttu-id="36494-1861">кóд.</span><span class="sxs-lookup"><span data-stu-id="36494-1861">cód.</span></span> <span data-ttu-id="36494-1862">сегуранçа</span><span class="sxs-lookup"><span data-stu-id="36494-1862">segurança</span></span> 
- <span data-ttu-id="36494-1863">кóдиго</span><span class="sxs-lookup"><span data-stu-id="36494-1863">código</span></span> 
- <span data-ttu-id="36494-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="36494-1864">código de seguranca</span></span> 
- <span data-ttu-id="36494-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="36494-1865">código de segurança</span></span> 
- <span data-ttu-id="36494-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="36494-1866">de kaart controle</span></span> 
- <span data-ttu-id="36494-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="36494-1867">geeft nr uit</span></span> 
- <span data-ttu-id="36494-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="36494-1868">issue no</span></span> 
- <span data-ttu-id="36494-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="36494-1869">issue number</span></span> 
- <span data-ttu-id="36494-1870">каартидентификатиенуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="36494-1871">кредиткартенпруфнуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="36494-1872">кредиткартенпрüфнуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="36494-1873">квестиеаантал</span><span class="sxs-lookup"><span data-stu-id="36494-1873">kwestieaantal</span></span> 
- <span data-ttu-id="36494-1874">Нет.</span><span class="sxs-lookup"><span data-stu-id="36494-1874">no.</span></span> <span data-ttu-id="36494-1875">делл'едизионе</span><span class="sxs-lookup"><span data-stu-id="36494-1875">dell'edizione</span></span> 
- <span data-ttu-id="36494-1876">Нет.</span><span class="sxs-lookup"><span data-stu-id="36494-1876">no.</span></span> <span data-ttu-id="36494-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="36494-1877">di sicurezza</span></span> 
- <span data-ttu-id="36494-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="36494-1878">numero de securite</span></span> 
- <span data-ttu-id="36494-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="36494-1879">numero de verificacao</span></span> 
- <span data-ttu-id="36494-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="36494-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="36494-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="36494-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="36494-1882">счеда</span><span class="sxs-lookup"><span data-stu-id="36494-1882">scheda</span></span> 
- <span data-ttu-id="36494-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="36494-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="36494-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="36494-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="36494-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="36494-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="36494-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="36494-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="36494-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="36494-1887">número de verificação</span></span> 
- <span data-ttu-id="36494-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="36494-1888">perno il blocco</span></span> 
- <span data-ttu-id="36494-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="36494-1889">pin block</span></span> 
- <span data-ttu-id="36494-1890">пруфзиффер</span><span class="sxs-lookup"><span data-stu-id="36494-1890">prufziffer</span></span> 
- <span data-ttu-id="36494-1891">прüфзиффер</span><span class="sxs-lookup"><span data-stu-id="36494-1891">prüfziffer</span></span> 
- <span data-ttu-id="36494-1892">security code</span><span class="sxs-lookup"><span data-stu-id="36494-1892">security code</span></span> 
- <span data-ttu-id="36494-1893">security no</span><span class="sxs-lookup"><span data-stu-id="36494-1893">security no</span></span> 
- <span data-ttu-id="36494-1894">security number</span><span class="sxs-lookup"><span data-stu-id="36494-1894">security number</span></span> 
- <span data-ttu-id="36494-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="36494-1895">sicherheits kode</span></span> 
- <span data-ttu-id="36494-1896">сичерхеитскоде</span><span class="sxs-lookup"><span data-stu-id="36494-1896">sicherheitscode</span></span> 
- <span data-ttu-id="36494-1897">сичерхеитснуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="36494-1898">спелдблок</span><span class="sxs-lookup"><span data-stu-id="36494-1898">speldblok</span></span> 
- <span data-ttu-id="36494-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="36494-1899">veiligheid nr</span></span> 
- <span data-ttu-id="36494-1900">веилигхеидсаантал</span><span class="sxs-lookup"><span data-stu-id="36494-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="36494-1901">веилигхеидскоде</span><span class="sxs-lookup"><span data-stu-id="36494-1901">veiligheidscode</span></span> 
- <span data-ttu-id="36494-1902">веилигхеидснуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="36494-1903">верфаллдатум</span><span class="sxs-lookup"><span data-stu-id="36494-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="36494-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="36494-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="36494-1905">аблауф</span><span class="sxs-lookup"><span data-stu-id="36494-1905">ablauf</span></span> 
- <span data-ttu-id="36494-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="36494-1906">data de expiracao</span></span> 
- <span data-ttu-id="36494-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="36494-1907">data de expiração</span></span> 
- <span data-ttu-id="36494-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="36494-1908">data del exp</span></span> 
- <span data-ttu-id="36494-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="36494-1909">data di exp</span></span> 
- <span data-ttu-id="36494-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="36494-1910">data di scadenza</span></span> 
- <span data-ttu-id="36494-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="36494-1911">data em que expira</span></span> 
- <span data-ttu-id="36494-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="36494-1912">data scad</span></span> 
- <span data-ttu-id="36494-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="36494-1913">data scadenza</span></span> 
- <span data-ttu-id="36494-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="36494-1914">date de validité</span></span> 
- <span data-ttu-id="36494-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="36494-1915">datum afloop</span></span> 
- <span data-ttu-id="36494-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="36494-1916">datum van exp</span></span> 
- <span data-ttu-id="36494-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="36494-1917">de afloop</span></span> 
- <span data-ttu-id="36494-1918">еспира</span><span class="sxs-lookup"><span data-stu-id="36494-1918">espira</span></span> 
- <span data-ttu-id="36494-1919">еспира</span><span class="sxs-lookup"><span data-stu-id="36494-1919">espira</span></span> 
- <span data-ttu-id="36494-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="36494-1920">exp date</span></span> 
- <span data-ttu-id="36494-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="36494-1921">exp datum</span></span> 
- <span data-ttu-id="36494-1922">срока действия</span><span class="sxs-lookup"><span data-stu-id="36494-1922">expiration</span></span> 
- <span data-ttu-id="36494-1923">истекает</span><span class="sxs-lookup"><span data-stu-id="36494-1923">expire</span></span> 
- <span data-ttu-id="36494-1924">истекает</span><span class="sxs-lookup"><span data-stu-id="36494-1924">expires</span></span> 
- <span data-ttu-id="36494-1925">окончания срока действия</span><span class="sxs-lookup"><span data-stu-id="36494-1925">expiry</span></span> 
- <span data-ttu-id="36494-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="36494-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="36494-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="36494-1927">fecha de venc</span></span> 
- <span data-ttu-id="36494-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="36494-1928">gultig bis</span></span> 
- <span data-ttu-id="36494-1929">гултигкеитсдатум</span><span class="sxs-lookup"><span data-stu-id="36494-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="36494-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="36494-1930">gültig bis</span></span> 
- <span data-ttu-id="36494-1931">гüлтигкеитсдатум</span><span class="sxs-lookup"><span data-stu-id="36494-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="36494-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="36494-1932">la scadenza</span></span> 
- <span data-ttu-id="36494-1933">скаденза</span><span class="sxs-lookup"><span data-stu-id="36494-1933">scadenza</span></span> 
- <span data-ttu-id="36494-1934">валабле</span><span class="sxs-lookup"><span data-stu-id="36494-1934">valable</span></span> 
- <span data-ttu-id="36494-1935">валидаде</span><span class="sxs-lookup"><span data-stu-id="36494-1935">validade</span></span> 
- <span data-ttu-id="36494-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="36494-1936">valido hasta</span></span> 
- <span data-ttu-id="36494-1937">валор</span><span class="sxs-lookup"><span data-stu-id="36494-1937">valor</span></span> 
- <span data-ttu-id="36494-1938">венк</span><span class="sxs-lookup"><span data-stu-id="36494-1938">venc</span></span> 
- <span data-ttu-id="36494-1939">венЦименто</span><span class="sxs-lookup"><span data-stu-id="36494-1939">vencimento</span></span> 
- <span data-ttu-id="36494-1940">венЦимиенто</span><span class="sxs-lookup"><span data-stu-id="36494-1940">vencimiento</span></span> 
- <span data-ttu-id="36494-1941">верлупт</span><span class="sxs-lookup"><span data-stu-id="36494-1941">verloopt</span></span> 
- <span data-ttu-id="36494-1942">вервалдаг</span><span class="sxs-lookup"><span data-stu-id="36494-1942">vervaldag</span></span> 
- <span data-ttu-id="36494-1943">вервалдатум</span><span class="sxs-lookup"><span data-stu-id="36494-1943">vervaldatum</span></span> 
- <span data-ttu-id="36494-1944">вто</span><span class="sxs-lookup"><span data-stu-id="36494-1944">vto</span></span> 
- <span data-ttu-id="36494-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="36494-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="36494-1946">Номер водительского удостоверения для драйвера ЕС</span><span class="sxs-lookup"><span data-stu-id="36494-1946">EU Driver's License Number</span></span>

<span data-ttu-id="36494-1947">Чтобы узнать больше, ознакомьтесь со статьей [тип конфиденциальной информации номера лицензии для драйвера ЕС](eu-driver-s-license-number.md).</span><span class="sxs-lookup"><span data-stu-id="36494-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="36494-1948">Национальный идентификационный номер ЕС</span><span class="sxs-lookup"><span data-stu-id="36494-1948">EU National Identification Number</span></span>

<span data-ttu-id="36494-1949">Чтобы узнать больше, ознакомьтесь со статьей [тип конфиденциальной информации для национального идентификационного номера ЕС](eu-national-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="36494-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="36494-1950">Номер паспорта ЕС</span><span class="sxs-lookup"><span data-stu-id="36494-1950">EU Passport Number</span></span>

<span data-ttu-id="36494-1951">Чтобы узнать больше, ознакомьтесь со статьей [тип конфиденциальной информации о номере паспорта ЕС](eu-passport-number.md).</span><span class="sxs-lookup"><span data-stu-id="36494-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="36494-1952">Номер социального страхования ЕС или эквивалентный идентификатор</span><span class="sxs-lookup"><span data-stu-id="36494-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="36494-1953">Чтобы узнать больше, ознакомьтесь со статьей [номер социального страхования ЕС или эквивалентный тип конфиденциальной информации ID](eu-social-security-number-or-equivalent-id.md).</span><span class="sxs-lookup"><span data-stu-id="36494-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="36494-1954">Идентификационный номер налогоплательщика ЕС</span><span class="sxs-lookup"><span data-stu-id="36494-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="36494-1955">Чтобы узнать больше, ознакомьтесь со статьей [тип конфиденциальной информации для налогового кода ЕС](eu-tax-identification-number.md).</span><span class="sxs-lookup"><span data-stu-id="36494-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="36494-1956">Национальный идентификатор, Финляндия</span><span class="sxs-lookup"><span data-stu-id="36494-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="36494-1957">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1957">Format</span></span>

<span data-ttu-id="36494-1958">Шесть цифр, а также символ, обозначающий век, три цифры и контрольная цифра.</span><span class="sxs-lookup"><span data-stu-id="36494-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1959">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1959">Pattern</span></span>

<span data-ttu-id="36494-1960">Шаблон должен включать в себя все указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="36494-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="36494-1961">Шесть цифр в формате ДДММГГ, представляющие собой дату рождения</span><span class="sxs-lookup"><span data-stu-id="36494-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="36494-1962">Маркер века (символы "-" и "+" или буква "a")</span><span class="sxs-lookup"><span data-stu-id="36494-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="36494-1963">Трехзначный личный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="36494-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="36494-1964">Цифра или буква (без учета регистра) — проверочная.</span><span class="sxs-lookup"><span data-stu-id="36494-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1965">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1965">Checksum</span></span>

<span data-ttu-id="36494-1966">Да</span><span class="sxs-lookup"><span data-stu-id="36494-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1967">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1967">Definition</span></span>

<span data-ttu-id="36494-1968">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1969">функция Func_finnish_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1970">находится ключевое слово из Keyword_finnish_national_id;</span><span class="sxs-lookup"><span data-stu-id="36494-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="36494-1971">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1972">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1972">Keywords</span></span>

- <span data-ttu-id="36494-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="36494-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="36494-1974">сосиаалитурватуннус</span><span class="sxs-lookup"><span data-stu-id="36494-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="36494-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="36494-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="36494-1976">персонбетеккнинг</span><span class="sxs-lookup"><span data-stu-id="36494-1976">Personbeteckning</span></span>
- <span data-ttu-id="36494-1977">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="36494-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="36494-1978">Номер паспорта для Финляндии</span><span class="sxs-lookup"><span data-stu-id="36494-1978">Finland Passport Number</span></span>

<span data-ttu-id="36494-1979">Комбинация, состоящая из девяти букв и цифр, комбинация из девяти букв и цифр: две буквы (без учета регистра) семь цифр контрольная сумма нет определения политика защиты от потери данных — 75% уверенности в том, что этот тип конфиденциальной информации определен, если в близость от 300 символов: регулярное выражение Regex_finland_passport_number находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="36494-1980">находится ключевое слово из Keyword_finland_passport_number.</span><span class="sxs-lookup"><span data-stu-id="36494-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="36494-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="36494-1981"></span></span>
<span data-ttu-id="36494-1982">Ключевые слова Keyword_finland_passport_number Passport Пасси</span><span class="sxs-lookup"><span data-stu-id="36494-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="36494-1983">Номер водительского удостоверения для Франции</span><span class="sxs-lookup"><span data-stu-id="36494-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-1984">Format</span><span class="sxs-lookup"><span data-stu-id="36494-1984">Format</span></span>

<span data-ttu-id="36494-1985">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-1986">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-1986">Pattern</span></span>

<span data-ttu-id="36494-1987">12 цифр с проверкой подлинности, чтобы избежать путаницы с похожими шаблонами, например французскими номерами телефонов.</span><span class="sxs-lookup"><span data-stu-id="36494-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-1988">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-1988">Checksum</span></span>

<span data-ttu-id="36494-1989">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-1990">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-1990">Definition</span></span>

<span data-ttu-id="36494-1991">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-1992">Функция Func_french_drivers_license находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-1993">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="36494-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="36494-1994">найдено ключевое слово из Keyword_french_drivers_license;</span><span class="sxs-lookup"><span data-stu-id="36494-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="36494-1995">функция Func_eu_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-1995">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-1996">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="36494-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="36494-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="36494-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="36494-1998">drivers licence</span></span>
- <span data-ttu-id="36494-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="36494-1999">drivers license</span></span>
- <span data-ttu-id="36494-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="36494-2000">driving licence</span></span>
- <span data-ttu-id="36494-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="36494-2001">driving license</span></span>
- <span data-ttu-id="36494-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="36494-2002">permis de conduire</span></span>
- <span data-ttu-id="36494-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="36494-2003">licence number</span></span>
- <span data-ttu-id="36494-2004">license number</span><span class="sxs-lookup"><span data-stu-id="36494-2004">license number</span></span>
- <span data-ttu-id="36494-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="36494-2005">licence numbers</span></span>
- <span data-ttu-id="36494-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="36494-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="36494-2007">Номер внутреннего удостоверения личности для Франции (CNI)</span><span class="sxs-lookup"><span data-stu-id="36494-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="36494-2008">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2008">Format</span></span>

<span data-ttu-id="36494-2009">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2010">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2010">Pattern</span></span>

<span data-ttu-id="36494-2011">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2012">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2012">Checksum</span></span>

<span data-ttu-id="36494-2013">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2014">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2014">Definition</span></span>

<span data-ttu-id="36494-2015">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2016">регулярное выражение Regex_france_cni находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2017">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2017">Keywords</span></span>

<span data-ttu-id="36494-2018">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="36494-2019">Номер паспорта гражданина Франции</span><span class="sxs-lookup"><span data-stu-id="36494-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2020">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2020">Format</span></span>

<span data-ttu-id="36494-2021">Девять цифр и букв.</span><span class="sxs-lookup"><span data-stu-id="36494-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2022">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2022">Pattern</span></span>

<span data-ttu-id="36494-2023">Девять цифр и букв</span><span class="sxs-lookup"><span data-stu-id="36494-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="36494-2024">Две цифры</span><span class="sxs-lookup"><span data-stu-id="36494-2024">Two digits</span></span> 
- <span data-ttu-id="36494-2025">Две буквы (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="36494-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="36494-2026">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="36494-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2027">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2027">Checksum</span></span>

<span data-ttu-id="36494-2028">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2029">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2029">Definition</span></span>

<span data-ttu-id="36494-2030">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2031">функция Func_fr_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2032">находится ключевое слово из Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="36494-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2033">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="36494-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="36494-2034">Keyword_passport</span></span>

- <span data-ttu-id="36494-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="36494-2035">Passport Number</span></span>
- <span data-ttu-id="36494-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="36494-2036">Passport No</span></span>
- <span data-ttu-id="36494-2037">Passport#</span><span class="sxs-lookup"><span data-stu-id="36494-2037">Passport #</span></span>
- <span data-ttu-id="36494-2038">Службу #</span><span class="sxs-lookup"><span data-stu-id="36494-2038">Passport#</span></span>
- <span data-ttu-id="36494-2039">пасспортид</span><span class="sxs-lookup"><span data-stu-id="36494-2039">PassportID</span></span>
- <span data-ttu-id="36494-2040">пасспортно</span><span class="sxs-lookup"><span data-stu-id="36494-2040">Passportno</span></span>
- <span data-ttu-id="36494-2041">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="36494-2041">passportnumber</span></span>
- <span data-ttu-id="36494-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="36494-2042">パスポート</span></span>
- <span data-ttu-id="36494-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="36494-2043">パスポート番号</span></span>
- <span data-ttu-id="36494-2044">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="36494-2044">パスポートのNum</span></span>
- <span data-ttu-id="36494-2045">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="36494-2045">パスポート ＃</span></span> 
- <span data-ttu-id="36494-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="36494-2046">Numéro de passeport</span></span>
- <span data-ttu-id="36494-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="36494-2047">Passeport n °</span></span>
- <span data-ttu-id="36494-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="36494-2048">Passeport Non</span></span>
- <span data-ttu-id="36494-2049">Passeport#</span><span class="sxs-lookup"><span data-stu-id="36494-2049">Passeport #</span></span>
- <span data-ttu-id="36494-2050">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="36494-2050">Passeport#</span></span>
- <span data-ttu-id="36494-2051">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="36494-2051">PasseportNon</span></span>
- <span data-ttu-id="36494-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="36494-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="36494-2053">Страховой номер для Франции (INSEE)</span><span class="sxs-lookup"><span data-stu-id="36494-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="36494-2054">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2054">Format</span></span>

<span data-ttu-id="36494-2055">15 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2056">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2056">Pattern</span></span>

<span data-ttu-id="36494-2057">Должен соответствовать одному из двух шаблонов:</span><span class="sxs-lookup"><span data-stu-id="36494-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="36494-2058">13 цифр, за которыми следует пробел, за которым следуют две цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="36494-2059">или</span><span class="sxs-lookup"><span data-stu-id="36494-2059">or</span></span>
- <span data-ttu-id="36494-2060">15 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2061">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2061">Checksum</span></span>

<span data-ttu-id="36494-2062">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2063">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2063">Definition</span></span>

<span data-ttu-id="36494-2064">Политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2065">Функция Func_french_insee или Func_fr_insee находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2066">находится ключевое слово из Keyword_fr_insee;</span><span class="sxs-lookup"><span data-stu-id="36494-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="36494-2067">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2067">The checksum passes.</span></span>

<span data-ttu-id="36494-2068">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2069">Функция Func_french_insee или Func_fr_insee находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2070">ни одно ключевое слово из Keyword_fr_insee не находится;</span><span class="sxs-lookup"><span data-stu-id="36494-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="36494-2071">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2071">The checksum passes.</span></span>

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2072">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="36494-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="36494-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="36494-2074">INSEE</span><span class="sxs-lookup"><span data-stu-id="36494-2074">insee</span></span>
- <span data-ttu-id="36494-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="36494-2075">securité sociale</span></span>
- <span data-ttu-id="36494-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="36494-2076">securite sociale</span></span>
- <span data-ttu-id="36494-2077">national id</span><span class="sxs-lookup"><span data-stu-id="36494-2077">national id</span></span>
- <span data-ttu-id="36494-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="36494-2078">national identification</span></span>
- <span data-ttu-id="36494-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="36494-2079">numéro d'identité</span></span>
- <span data-ttu-id="36494-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="36494-2080">no d'identité</span></span>
- <span data-ttu-id="36494-2081">Нет.</span><span class="sxs-lookup"><span data-stu-id="36494-2081">no.</span></span> <span data-ttu-id="36494-2082">д'идентитé</span><span class="sxs-lookup"><span data-stu-id="36494-2082">d'identité</span></span>
- <span data-ttu-id="36494-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="36494-2083">numero d'identite</span></span>
- <span data-ttu-id="36494-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="36494-2084">no d'identite</span></span>
- <span data-ttu-id="36494-2085">Нет.</span><span class="sxs-lookup"><span data-stu-id="36494-2085">no.</span></span> <span data-ttu-id="36494-2086">д'идентите</span><span class="sxs-lookup"><span data-stu-id="36494-2086">d'identite</span></span>
- <span data-ttu-id="36494-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="36494-2087">social security number</span></span>
- <span data-ttu-id="36494-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="36494-2088">social security code</span></span>
- <span data-ttu-id="36494-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="36494-2089">social insurance number</span></span>
- <span data-ttu-id="36494-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="36494-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="36494-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="36494-2091">d'identité nationale</span></span>
- <span data-ttu-id="36494-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="36494-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="36494-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="36494-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="36494-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="36494-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="36494-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="36494-2095">numéro de sécu</span></span>
- <span data-ttu-id="36494-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="36494-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="36494-2097">Номер водительского удостоверения для Германии</span><span class="sxs-lookup"><span data-stu-id="36494-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2098">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2098">Format</span></span>

<span data-ttu-id="36494-2099">Сочетание 11 цифр и букв.</span><span class="sxs-lookup"><span data-stu-id="36494-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2100">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2100">Pattern</span></span>

<span data-ttu-id="36494-2101">11 цифр и букв (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="36494-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="36494-2102">Одна цифра или буква</span><span class="sxs-lookup"><span data-stu-id="36494-2102">A digit or letter</span></span> 
- <span data-ttu-id="36494-2103">Две цифры</span><span class="sxs-lookup"><span data-stu-id="36494-2103">Two digits</span></span> 
- <span data-ttu-id="36494-2104">Шесть цифр или букв</span><span class="sxs-lookup"><span data-stu-id="36494-2104">Six digits or letters</span></span> 
- <span data-ttu-id="36494-2105">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="36494-2105">A digit</span></span> 
- <span data-ttu-id="36494-2106">Одна цифра или буква</span><span class="sxs-lookup"><span data-stu-id="36494-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2107">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2107">Checksum</span></span>

<span data-ttu-id="36494-2108">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2109">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2109">Definition</span></span>

<span data-ttu-id="36494-2110">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2111">Функция Func_german_drivers_license находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2112">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="36494-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="36494-2113">найдено ключевое слово из Keyword_german_drivers_license_number;</span><span class="sxs-lookup"><span data-stu-id="36494-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="36494-2114">найдено ключевое слово из Keyword_german_drivers_license_collaborative;</span><span class="sxs-lookup"><span data-stu-id="36494-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="36494-2115">найдено ключевое слово из Keyword_german_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="36494-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="36494-2116">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2116">The checksum passes.</span></span>

```xml
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2117">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="36494-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="36494-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="36494-2119">фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2119">Führerschein</span></span>
- <span data-ttu-id="36494-2120">фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2120">Fuhrerschein</span></span>
- <span data-ttu-id="36494-2121">фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2121">Fuehrerschein</span></span>
- <span data-ttu-id="36494-2122">фüхрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="36494-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="36494-2123">фухрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="36494-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="36494-2124">фуехрерсчеиннуммер</span><span class="sxs-lookup"><span data-stu-id="36494-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="36494-2125">Фüхрерсчеин —</span><span class="sxs-lookup"><span data-stu-id="36494-2125">Führerschein-</span></span> 
- <span data-ttu-id="36494-2126">Фухрерсчеин —</span><span class="sxs-lookup"><span data-stu-id="36494-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="36494-2127">Фуехрерсчеин —</span><span class="sxs-lookup"><span data-stu-id="36494-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="36494-2128">фüхрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="36494-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="36494-2129">фухрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="36494-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="36494-2130">фуехрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="36494-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="36494-2131">фüхрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="36494-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="36494-2132">фухрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="36494-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="36494-2133">фуехрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="36494-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="36494-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="36494-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="36494-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="36494-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="36494-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="36494-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="36494-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="36494-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="36494-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="36494-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="36494-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="36494-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="36494-2140">фüхрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="36494-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="36494-2141">фухрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="36494-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="36494-2142">фуехрерсчеиннуммернр</span><span class="sxs-lookup"><span data-stu-id="36494-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="36494-2143">фüхрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="36494-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="36494-2144">фухрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="36494-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="36494-2145">фуехрерсчеиннуммерклассе</span><span class="sxs-lookup"><span data-stu-id="36494-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="36494-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="36494-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="36494-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="36494-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="36494-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="36494-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="36494-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="36494-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="36494-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="36494-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="36494-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="36494-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="36494-2152">DL</span><span class="sxs-lookup"><span data-stu-id="36494-2152">DL</span></span> 
- <span data-ttu-id="36494-2153">БИБЛИОТЕК</span><span class="sxs-lookup"><span data-stu-id="36494-2153">DLS</span></span>
- <span data-ttu-id="36494-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="36494-2154">Driv Lic</span></span> 
- <span data-ttu-id="36494-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="36494-2155">Driv Licen</span></span> 
- <span data-ttu-id="36494-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="36494-2156">Driv License</span></span>
- <span data-ttu-id="36494-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-2157">Driv Licenses</span></span> 
- <span data-ttu-id="36494-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="36494-2158">Driv Licence</span></span> 
- <span data-ttu-id="36494-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="36494-2159">Driv Licences</span></span> 
- <span data-ttu-id="36494-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="36494-2160">Driv Lic</span></span> 
- <span data-ttu-id="36494-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="36494-2161">Driver Licen</span></span> 
- <span data-ttu-id="36494-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="36494-2162">Driver License</span></span> 
- <span data-ttu-id="36494-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-2163">Driver Licenses</span></span> 
- <span data-ttu-id="36494-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="36494-2164">Driver Licence</span></span> 
- <span data-ttu-id="36494-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="36494-2165">Driver Licences</span></span> 
- <span data-ttu-id="36494-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="36494-2166">Drivers Lic</span></span> 
- <span data-ttu-id="36494-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="36494-2167">Drivers Licen</span></span> 
- <span data-ttu-id="36494-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="36494-2168">Drivers License</span></span> 
- <span data-ttu-id="36494-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="36494-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="36494-2170">Drivers Licence</span></span> 
- <span data-ttu-id="36494-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="36494-2171">Drivers Licences</span></span> 
- <span data-ttu-id="36494-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="36494-2172">Driver's Lic</span></span> 
- <span data-ttu-id="36494-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="36494-2173">Driver's Licen</span></span> 
- <span data-ttu-id="36494-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="36494-2174">Driver's License</span></span> 
- <span data-ttu-id="36494-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="36494-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="36494-2176">Driver's Licence</span></span> 
- <span data-ttu-id="36494-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="36494-2177">Driver's Licences</span></span> 
- <span data-ttu-id="36494-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="36494-2178">Driving Lic</span></span> 
- <span data-ttu-id="36494-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="36494-2179">Driving Licen</span></span> 
- <span data-ttu-id="36494-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="36494-2180">Driving License</span></span> 
- <span data-ttu-id="36494-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-2181">Driving Licenses</span></span> 
- <span data-ttu-id="36494-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="36494-2182">Driving Licence</span></span> 
- <span data-ttu-id="36494-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="36494-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="36494-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="36494-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="36494-2185">НР — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="36494-2186">НР — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="36494-2187">НР — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="36494-2188">Нет — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2188">No-Führerschein</span></span> 
- <span data-ttu-id="36494-2189">Нет — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="36494-2190">Нет — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="36494-2191">N — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2191">N-Führerschein</span></span> 
- <span data-ttu-id="36494-2192">N — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="36494-2193">N — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="36494-2194">НР — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="36494-2195">НР — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="36494-2196">НР — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="36494-2197">Нет — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2197">No-Führerschein</span></span> 
- <span data-ttu-id="36494-2198">Нет — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="36494-2199">Нет — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="36494-2200">N — Фüхрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2200">N-Führerschein</span></span> 
- <span data-ttu-id="36494-2201">N — Фухрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="36494-2202">N — Фуехрерсчеин</span><span class="sxs-lookup"><span data-stu-id="36494-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="36494-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="36494-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="36494-2204">аусстеллунгсдатум</span><span class="sxs-lookup"><span data-stu-id="36494-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="36494-2205">аусстеллунгсорт</span><span class="sxs-lookup"><span data-stu-id="36494-2205">ausstellungsort</span></span>
- <span data-ttu-id="36494-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="36494-2206">ausstellende behöde</span></span>
- <span data-ttu-id="36494-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="36494-2207">ausstellende behorde</span></span>
- <span data-ttu-id="36494-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="36494-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="36494-2209">Номер паспорта гражданина Германии</span><span class="sxs-lookup"><span data-stu-id="36494-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2210">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2210">Format</span></span>

<span data-ttu-id="36494-2211">10 цифр или букв.</span><span class="sxs-lookup"><span data-stu-id="36494-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2212">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2212">Pattern</span></span>

<span data-ttu-id="36494-2213">Шаблон должен включать в себя все указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="36494-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="36494-2214">Первый символ — цифра или буква из следующего набора: C, F, G, H, J, K.</span><span class="sxs-lookup"><span data-stu-id="36494-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="36494-2215">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-2215">Three digits</span></span> 
- <span data-ttu-id="36494-2216">Пять цифр или букв из следующего набора: C, F-H, J-N, P, R, T, V-Z</span><span class="sxs-lookup"><span data-stu-id="36494-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="36494-2217">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="36494-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2218">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2218">Checksum</span></span>

<span data-ttu-id="36494-2219">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2220">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2220">Definition</span></span>

<span data-ttu-id="36494-2221">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2222">функция Func_german_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2223">находится любое ключевое слово из пяти соответствующих списков;</span><span class="sxs-lookup"><span data-stu-id="36494-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="36494-2224">контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2224">The checksum passes.</span></span>

<span data-ttu-id="36494-2225">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2226">функция Func_german_passport_data находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2227">находится любое ключевое слово из пяти соответствующих списков;</span><span class="sxs-lookup"><span data-stu-id="36494-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="36494-2228">контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2228">The checksum passes.</span></span>

```xml
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2229">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="36494-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="36494-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="36494-2231">реисепасс</span><span class="sxs-lookup"><span data-stu-id="36494-2231">reisepass</span></span>
- <span data-ttu-id="36494-2232">реисепассе</span><span class="sxs-lookup"><span data-stu-id="36494-2232">reisepasse</span></span>
- <span data-ttu-id="36494-2233">реисепасснуммер</span><span class="sxs-lookup"><span data-stu-id="36494-2233">reisepassnummer</span></span>
- <span data-ttu-id="36494-2234">службу</span><span class="sxs-lookup"><span data-stu-id="36494-2234">passport</span></span>
- <span data-ttu-id="36494-2235">паспорты</span><span class="sxs-lookup"><span data-stu-id="36494-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="36494-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="36494-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="36494-2237">жебуртсдатум</span><span class="sxs-lookup"><span data-stu-id="36494-2237">geburtsdatum</span></span>
- <span data-ttu-id="36494-2238">аусстеллунгсдатум</span><span class="sxs-lookup"><span data-stu-id="36494-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="36494-2239">аусстеллунгсорт</span><span class="sxs-lookup"><span data-stu-id="36494-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="36494-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="36494-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="36494-2241">No — Реисепасс НР — Реисепасс</span><span class="sxs-lookup"><span data-stu-id="36494-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="36494-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="36494-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="36494-2243">Реисепасс — НР</span><span class="sxs-lookup"><span data-stu-id="36494-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="36494-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="36494-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="36494-2245">бнатионалит. t</span><span class="sxs-lookup"><span data-stu-id="36494-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="36494-2246">Номер идентификационной карты гражданина Германии</span><span class="sxs-lookup"><span data-stu-id="36494-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2247">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2247">Format</span></span>

<span data-ttu-id="36494-2248">С 1 ноября 2010: девять букв и цифр</span><span class="sxs-lookup"><span data-stu-id="36494-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="36494-2249">От 1 апреля 1987 до 31 октября 2010:10 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2250">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2250">Pattern</span></span>

<span data-ttu-id="36494-2251">С 1 ноября 2010 г.:</span><span class="sxs-lookup"><span data-stu-id="36494-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="36494-2252">одна буква (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="36494-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="36494-2253">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2253">Eight digits</span></span>

<span data-ttu-id="36494-2254">От 1 апреля 1987 до 31 октября 2010:</span><span class="sxs-lookup"><span data-stu-id="36494-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="36494-2255">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2256">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2256">Checksum</span></span>

<span data-ttu-id="36494-2257">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2258">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2258">Definition</span></span>

<span data-ttu-id="36494-2259">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2260">регулярное выражение Regex_germany_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2261">находится ключевое слово из Keyword_germany_id_card.</span><span class="sxs-lookup"><span data-stu-id="36494-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2262">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="36494-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="36494-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="36494-2264">Identity Card</span><span class="sxs-lookup"><span data-stu-id="36494-2264">Identity Card</span></span>
- <span data-ttu-id="36494-2265">ID</span><span class="sxs-lookup"><span data-stu-id="36494-2265">ID</span></span>
- <span data-ttu-id="36494-2266">Процедура</span><span class="sxs-lookup"><span data-stu-id="36494-2266">Identification</span></span>
- <span data-ttu-id="36494-2267">персоналаусвеис</span><span class="sxs-lookup"><span data-stu-id="36494-2267">Personalausweis</span></span>
- <span data-ttu-id="36494-2268">идентифизиерунгснуммер</span><span class="sxs-lookup"><span data-stu-id="36494-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="36494-2269">аусвеис</span><span class="sxs-lookup"><span data-stu-id="36494-2269">Ausweis</span></span>
- <span data-ttu-id="36494-2270">идентификатион</span><span class="sxs-lookup"><span data-stu-id="36494-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="36494-2271">Номер внутреннего удостоверения личности для Греции</span><span class="sxs-lookup"><span data-stu-id="36494-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="36494-2272">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2272">Format</span></span>

<span data-ttu-id="36494-2273">Сочетание 7–8 букв и чисел, а также тире.</span><span class="sxs-lookup"><span data-stu-id="36494-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2274">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2274">Pattern</span></span>

<span data-ttu-id="36494-2275">Семь букв и чисел (старый формат):</span><span class="sxs-lookup"><span data-stu-id="36494-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="36494-2276">одна буква (любая буква греческого алфавита);</span><span class="sxs-lookup"><span data-stu-id="36494-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="36494-2277">тире;</span><span class="sxs-lookup"><span data-stu-id="36494-2277">A dash</span></span> 
- <span data-ttu-id="36494-2278">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2278">Six digits</span></span>

<span data-ttu-id="36494-2279">Восемь букв и чисел (новый формат):</span><span class="sxs-lookup"><span data-stu-id="36494-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="36494-2280">две буквы, которые в прописном виде есть как в греческом, так и латинском алфавите (ABEZHIKMNOPTYX);</span><span class="sxs-lookup"><span data-stu-id="36494-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="36494-2281">тире;</span><span class="sxs-lookup"><span data-stu-id="36494-2281">A dash</span></span> 
- <span data-ttu-id="36494-2282">шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2283">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2283">Checksum</span></span>

<span data-ttu-id="36494-2284">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2285">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2285">Definition</span></span>

<span data-ttu-id="36494-2286">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2287">регулярное выражение Regex_greece_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2288">находится ключевое слово из Keyword_greece_id_card.</span><span class="sxs-lookup"><span data-stu-id="36494-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2289">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="36494-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="36494-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="36494-2291">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="36494-2291">Greek identity Card</span></span>
- <span data-ttu-id="36494-2292">таутотита</span><span class="sxs-lookup"><span data-stu-id="36494-2292">Tautotita</span></span>
- <span data-ttu-id="36494-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="36494-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="36494-2294">ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="36494-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="36494-2295">Номер удостоверения личности для Гонконга (HKID)</span><span class="sxs-lookup"><span data-stu-id="36494-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2296">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2296">Format</span></span>

<span data-ttu-id="36494-2297">Сочетание 8–9 букв и чисел, а также необязательные скобки вокруг последнего символа.</span><span class="sxs-lookup"><span data-stu-id="36494-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2298">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2298">Pattern</span></span>

<span data-ttu-id="36494-2299">Сочетание 8–9 букв:</span><span class="sxs-lookup"><span data-stu-id="36494-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="36494-2300">1–2 буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="36494-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="36494-2301">шесть цифр; </span><span class="sxs-lookup"><span data-stu-id="36494-2301">Six digits</span></span> 
- <span data-ttu-id="36494-2302">последний символ (любая цифра или буква "A") является проверочной цифрой и заключен в скобки (необязательно).</span><span class="sxs-lookup"><span data-stu-id="36494-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2303">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2303">Checksum</span></span>

<span data-ttu-id="36494-2304">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2305">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2305">Definition</span></span>

<span data-ttu-id="36494-2306">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2307">функция Func_hong_kong_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2308">находится ключевое слово из Keyword_hong_kong_id_card;</span><span class="sxs-lookup"><span data-stu-id="36494-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="36494-2309">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2309">The checksum passes.</span></span>

<span data-ttu-id="36494-2310">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2311">функция Func_hong_kong_id_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2312">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2312">The checksum passes.</span></span>

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2313">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="36494-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="36494-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="36494-2315">идентификационная карточка Гонконг</span><span class="sxs-lookup"><span data-stu-id="36494-2315">hong kong identity card</span></span>
- <span data-ttu-id="36494-2316">хкидк</span><span class="sxs-lookup"><span data-stu-id="36494-2316">HKIDC</span></span>
- <span data-ttu-id="36494-2317">id card</span><span class="sxs-lookup"><span data-stu-id="36494-2317">id card</span></span>
- <span data-ttu-id="36494-2318">identity card</span><span class="sxs-lookup"><span data-stu-id="36494-2318">identity card</span></span>
- <span data-ttu-id="36494-2319">идентификационная карточка HK</span><span class="sxs-lookup"><span data-stu-id="36494-2319">hk identity card</span></span>
- <span data-ttu-id="36494-2320">Идентификатор Гонконг</span><span class="sxs-lookup"><span data-stu-id="36494-2320">hong kong id</span></span>
- <span data-ttu-id="36494-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="36494-2321">香港身份證</span></span>
- <span data-ttu-id="36494-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="36494-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="36494-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="36494-2323">身份證</span></span>
- <span data-ttu-id="36494-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="36494-2324">身份証</span></span>
- <span data-ttu-id="36494-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="36494-2325">身分證</span></span>
- <span data-ttu-id="36494-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="36494-2326">身分証</span></span>
- <span data-ttu-id="36494-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="36494-2327">香港身份証</span></span>
- <span data-ttu-id="36494-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="36494-2328">香港身分證</span></span>
- <span data-ttu-id="36494-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="36494-2329">香港身分証</span></span>
- <span data-ttu-id="36494-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="36494-2330">香港身份證</span></span>
- <span data-ttu-id="36494-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="36494-2331">香港居民身份證</span></span>
- <span data-ttu-id="36494-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="36494-2332">香港居民身份証</span></span>
- <span data-ttu-id="36494-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="36494-2333">香港居民身分證</span></span>
- <span data-ttu-id="36494-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="36494-2334">香港居民身分証</span></span>
- <span data-ttu-id="36494-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="36494-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="36494-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="36494-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="36494-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="36494-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="36494-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="36494-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="36494-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="36494-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="36494-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="36494-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="36494-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="36494-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="36494-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="36494-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="36494-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="36494-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="36494-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="36494-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="36494-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="36494-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="36494-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="36494-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="36494-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="36494-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="36494-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="36494-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="36494-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="36494-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="36494-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="36494-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="36494-2351">Идентификационный номер налогоплательщика для Индии (PAN)</span><span class="sxs-lookup"><span data-stu-id="36494-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="36494-2352">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2352">Format</span></span>

<span data-ttu-id="36494-2353">10 букв или цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2354">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2354">Pattern</span></span>

<span data-ttu-id="36494-2355">10 букв или цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-2355">10 letters or digits:</span></span>
- <span data-ttu-id="36494-2356">пять букв (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="36494-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="36494-2357">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="36494-2357">Four digits</span></span> 
- <span data-ttu-id="36494-2358">буква, которая является алфавитным проверочным символом.</span><span class="sxs-lookup"><span data-stu-id="36494-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2359">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2359">Checksum</span></span>

<span data-ttu-id="36494-2360">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2361">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2361">Definition</span></span>

<span data-ttu-id="36494-2362">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2363">регулярное выражение Regex_india_permanent_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2364">находится ключевое слово из Keyword_india_permanent_account_number;</span><span class="sxs-lookup"><span data-stu-id="36494-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="36494-2365">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2366">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="36494-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="36494-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="36494-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="36494-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="36494-2369">ПАНОРАМИРОВАНИЕ</span><span class="sxs-lookup"><span data-stu-id="36494-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="36494-2370">Индивидуальный идентификационный номер (Aadhaar) для Индии</span><span class="sxs-lookup"><span data-stu-id="36494-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2371">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2371">Format</span></span>

<span data-ttu-id="36494-2372">12 цифр, содержащих необязательные пробелы или тире.</span><span class="sxs-lookup"><span data-stu-id="36494-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2373">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2373">Pattern</span></span>

<span data-ttu-id="36494-2374">12 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-2374">12 digits:</span></span>
- <span data-ttu-id="36494-2375">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-2375">Four digits</span></span> 
- <span data-ttu-id="36494-2376">необязательный пробел или тире;</span><span class="sxs-lookup"><span data-stu-id="36494-2376">An optional space or dash</span></span> 
- <span data-ttu-id="36494-2377">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-2377">Four digits</span></span> 
- <span data-ttu-id="36494-2378">необязательный пробел или тире;</span><span class="sxs-lookup"><span data-stu-id="36494-2378">An optional space or dash</span></span> 
- <span data-ttu-id="36494-2379">последняя цифра — проверочная.</span><span class="sxs-lookup"><span data-stu-id="36494-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2380">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2380">Checksum</span></span>

<span data-ttu-id="36494-2381">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2382">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2382">Definition</span></span>

<span data-ttu-id="36494-2383">Политика защиты от потери данных — 85% уверенности, что она обнаружила этот тип конфиденциальной информации, если в пределах близости от 300 символов: функция Func_india_aadhaar находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="36494-2384">находится ключевое слово из Keyword_india_aadhar;</span><span class="sxs-lookup"><span data-stu-id="36494-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="36494-2385">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2385">The checksum passes.</span></span>
<span data-ttu-id="36494-2386">Политика защиты от потери данных — 75% уверенности, что она обнаружила этот тип конфиденциальной информации, если в пределах близости от 300 символов: функция Func_india_aadhaar находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="36494-2387">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2387">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="36494-2388">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2388">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="36494-2389">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="36494-2389">Keyword_india_aadhar</span></span>
- <span data-ttu-id="36494-2390">аадхар</span><span class="sxs-lookup"><span data-stu-id="36494-2390">Aadhar</span></span>
- <span data-ttu-id="36494-2391">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="36494-2391">Aadhaar</span></span>
- <span data-ttu-id="36494-2392">UID</span><span class="sxs-lookup"><span data-stu-id="36494-2392">UID</span></span>
- <span data-ttu-id="36494-2393">आधार</span><span class="sxs-lookup"><span data-stu-id="36494-2393">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="36494-2394">Номер удостоверения личности (KTP) для Индонезии</span><span class="sxs-lookup"><span data-stu-id="36494-2394">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2395">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2395">Format</span></span>

<span data-ttu-id="36494-2396">16 цифр, содержащих необязательные точки.</span><span class="sxs-lookup"><span data-stu-id="36494-2396">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2397">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2397">Pattern</span></span>

<span data-ttu-id="36494-2398">16 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-2398">16 digits:</span></span>
- <span data-ttu-id="36494-2399">две цифры (код провинции);</span><span class="sxs-lookup"><span data-stu-id="36494-2399">Two-digit province code</span></span> 
- <span data-ttu-id="36494-2400">точка (необязательно);</span><span class="sxs-lookup"><span data-stu-id="36494-2400">A period (optional)</span></span> 
- <span data-ttu-id="36494-2401">две цифры (код округа или города);</span><span class="sxs-lookup"><span data-stu-id="36494-2401">Two-digit regency or city code</span></span> 
- <span data-ttu-id="36494-2402">две цифры (код района);</span><span class="sxs-lookup"><span data-stu-id="36494-2402">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="36494-2403">точка (необязательно);</span><span class="sxs-lookup"><span data-stu-id="36494-2403">A period (optional)</span></span> 
- <span data-ttu-id="36494-2404">шесть цифр в формате ДДММГГ (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="36494-2404">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="36494-2405">точка (необязательно);</span><span class="sxs-lookup"><span data-stu-id="36494-2405">A period (optional)</span></span> 
- <span data-ttu-id="36494-2406">четыре цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-2406">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2407">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2407">Checksum</span></span>

<span data-ttu-id="36494-2408">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2408">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2409">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2409">Definition</span></span>

<span data-ttu-id="36494-2410">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2410">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2411">регулярное выражение Regex_indonesia_id_card находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-2411">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2412">находится ключевое слово из Keyword_indonesia_id_card.</span><span class="sxs-lookup"><span data-stu-id="36494-2412">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="36494-2413">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2414">регулярное выражение Regex_indonesia_id_card находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-2414">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2415">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2415">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="36494-2416">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="36494-2416">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="36494-2417">KTP</span><span class="sxs-lookup"><span data-stu-id="36494-2417">KTP</span></span>
- <span data-ttu-id="36494-2418">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="36494-2418">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="36494-2419">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="36494-2419">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="36494-2420">Международный номер банковского счета (IBAN)</span><span class="sxs-lookup"><span data-stu-id="36494-2420">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="36494-2421">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2421">Format</span></span>

<span data-ttu-id="36494-2422">Код страны (две буквы), а также проверочные цифры (две) и номер bban (до 30 символов)</span><span class="sxs-lookup"><span data-stu-id="36494-2422">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2423">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2423">Pattern</span></span>

<span data-ttu-id="36494-2424">Шаблон должен включать в себя все указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="36494-2424">Pattern must include all of the following:</span></span>

- <span data-ttu-id="36494-2425">Двухбуквенный код страны</span><span class="sxs-lookup"><span data-stu-id="36494-2425">Two-letter country code</span></span>
- <span data-ttu-id="36494-2426">Две проверочные цифры (после которых может следовать пробел) </span><span class="sxs-lookup"><span data-stu-id="36494-2426">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="36494-2427">1–7 групп из четырех букв или цифр (могут разделяться пробелами)</span><span class="sxs-lookup"><span data-stu-id="36494-2427">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="36494-2428">1–3 буквы или цифры</span><span class="sxs-lookup"><span data-stu-id="36494-2428">1-3 letters or digits</span></span>

<span data-ttu-id="36494-p135">Формат для названия каждой из стран немного отличается. Тип конфиденциальной информации IBAN применяется к следующим 60 странам:</span><span class="sxs-lookup"><span data-stu-id="36494-p135">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="36494-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="36494-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2432">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2432">Checksum</span></span>

<span data-ttu-id="36494-2433">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2433">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2434">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2434">Definition</span></span>

<span data-ttu-id="36494-2435">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2435">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2436">функция Func_iban находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2436">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2437">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2437">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2438">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2438">Keywords</span></span>

<span data-ttu-id="36494-2439">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2439">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="36494-2440">IP-адрес</span><span class="sxs-lookup"><span data-stu-id="36494-2440">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="36494-2441">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2441">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="36494-2442">IPv4</span><span class="sxs-lookup"><span data-stu-id="36494-2442">IPv4:</span></span>
<span data-ttu-id="36494-2443">Сложный шаблон, ответственный за форматированные (с точками) и неформатированные (без точек) версии IPv4-адресов.</span><span class="sxs-lookup"><span data-stu-id="36494-2443">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="36494-2444">Поддерживающ</span><span class="sxs-lookup"><span data-stu-id="36494-2444">IPv6:</span></span>
<span data-ttu-id="36494-2445"> Сложный шаблон, ответственный за форматированные номера IPv6 (вместе с двоеточиями).</span><span class="sxs-lookup"><span data-stu-id="36494-2445">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2446">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2446">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2447">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2447">Checksum</span></span>

<span data-ttu-id="36494-2448">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2448">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2449">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2449">Definition</span></span>

<span data-ttu-id="36494-2450">В случае с протоколом IPv6 политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2450">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2451">регулярное выражение Regex_ipv6_address находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2451">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2452">ни одно ключевое слово из Keyword_ipaddress не находится.</span><span class="sxs-lookup"><span data-stu-id="36494-2452">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="36494-2453">В случае с протоколом IPv4 политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2453">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2454">регулярное выражение Regex_ipv4_address находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2454">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2455">находится ключевое слово из Keyword_ipaddress.</span><span class="sxs-lookup"><span data-stu-id="36494-2455">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="36494-2456">В случае с протоколом IPv6 политика защиты от потери данных с вероятностью в 95 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2456">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2457">регулярное выражение Regex_ipv6_address находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2457">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2458">ни одно ключевое слово из Keyword_ipaddress не находится.</span><span class="sxs-lookup"><span data-stu-id="36494-2458">No keyword from Keyword_ipaddress is found.</span></span>

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2459">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2459">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="36494-2460">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="36494-2460">Keyword_ipaddress</span></span>

- <span data-ttu-id="36494-2461">IP (ключевое слово с учетом регистра)</span><span class="sxs-lookup"><span data-stu-id="36494-2461">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="36494-2462">ip address</span><span class="sxs-lookup"><span data-stu-id="36494-2462">ip address</span></span> 
- <span data-ttu-id="36494-2463">ip addresses</span><span class="sxs-lookup"><span data-stu-id="36494-2463">ip addresses</span></span>
- <span data-ttu-id="36494-2464">internet protocol</span><span class="sxs-lookup"><span data-stu-id="36494-2464">internet protocol</span></span>
- <span data-ttu-id="36494-2465">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="36494-2465">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="36494-2466">Международная классификация Diseases (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="36494-2466">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="36494-2467">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2467">Format</span></span>

<span data-ttu-id="36494-2468">Dictionary</span><span class="sxs-lookup"><span data-stu-id="36494-2468">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2469">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2469">Pattern</span></span>

<span data-ttu-id="36494-2470">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="36494-2470">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2471">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2471">Checksum</span></span>

<span data-ttu-id="36494-2472">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2472">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2473">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2473">Definition</span></span>

<span data-ttu-id="36494-2474">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2474">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2475">Найдено ключевое слово из Dictionary_icd_10_updated.</span><span class="sxs-lookup"><span data-stu-id="36494-2475">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="36494-2476">Найдено ключевое слово из Dictionary_icd_10_codes.</span><span class="sxs-lookup"><span data-stu-id="36494-2476">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="36494-2477">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2477">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2478">Найдено ключевое слово из Dictionary_icd_10_.</span><span class="sxs-lookup"><span data-stu-id="36494-2478">A keyword from Dictionary_icd_10_ updated is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

<span data-ttu-id="36494-2479">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2479">Keywords</span></span>

<span data-ttu-id="36494-2480">Любой термин из словаря ключевых слов Dictionary_icd_10_updated, основанный на [международной классификации Diseases, десятой редакции Клиникал модификации (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="36494-2480">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="36494-2481">Этот тип ищет только термин, а не коды страхования.</span><span class="sxs-lookup"><span data-stu-id="36494-2481">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="36494-2482">Любой термин из словаря ключевых слов Dictionary_icd_10_codes, основанный на [международной классификации Diseases, десятой редакции Клиникал модификации (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604).</span><span class="sxs-lookup"><span data-stu-id="36494-2482">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="36494-2483">Этот тип ищет только страховые коды, а не описание.</span><span class="sxs-lookup"><span data-stu-id="36494-2483">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="36494-2484">Международная классификация Diseases (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="36494-2484">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="36494-2485">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2485">Format</span></span>

<span data-ttu-id="36494-2486">Dictionary</span><span class="sxs-lookup"><span data-stu-id="36494-2486">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2487">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2487">Pattern</span></span>

<span data-ttu-id="36494-2488">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="36494-2488">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2489">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2489">Checksum</span></span>

<span data-ttu-id="36494-2490">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2490">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2491">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2491">Definition</span></span>

<span data-ttu-id="36494-2492">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2492">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2493">Найдено ключевое слово из Dictionary_icd_9_updated.</span><span class="sxs-lookup"><span data-stu-id="36494-2493">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="36494-2494">Найдено ключевое слово из Dictionary_icd_9_codes.</span><span class="sxs-lookup"><span data-stu-id="36494-2494">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="36494-2495">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2495">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2496">Найдено ключевое слово из Dictionary_icd_9_updated.</span><span class="sxs-lookup"><span data-stu-id="36494-2496">A keyword from Dictionary_icd_9_updated is found.</span></span>

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2497">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2497">Keywords</span></span>

<span data-ttu-id="36494-2498">Любой термин из словаря ключевых слов Dictionary_icd_9_updated, основанный на [международной классификации Diseases, девятой редакции, Клиникал модификации (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="36494-2498">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="36494-2499">Этот тип ищет только термин, а не коды страхования.</span><span class="sxs-lookup"><span data-stu-id="36494-2499">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="36494-2500">Любой термин из словаря ключевых слов Dictionary_icd_9_codes, основанный на [международной классификации Diseases, девятой редакции, Клиникал модификации (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605).</span><span class="sxs-lookup"><span data-stu-id="36494-2500">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="36494-2501">Этот тип ищет только страховые коды, а не описание.</span><span class="sxs-lookup"><span data-stu-id="36494-2501">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="36494-2502">Индивидуальный социальный номер (PPS) для Ирландии</span><span class="sxs-lookup"><span data-stu-id="36494-2502">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2503">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2503">Format</span></span>

<span data-ttu-id="36494-2504">Старый формат (до 31 декабря 2012):</span><span class="sxs-lookup"><span data-stu-id="36494-2504">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="36494-2505">семь цифр, за которыми следуют 1–2 буквы. </span><span class="sxs-lookup"><span data-stu-id="36494-2505">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="36494-2506">Новый формат (1 января 2013 и после):</span><span class="sxs-lookup"><span data-stu-id="36494-2506">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="36494-2507">семь цифр, за которыми следуют две буквы.</span><span class="sxs-lookup"><span data-stu-id="36494-2507">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2508">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2508">Pattern</span></span>

<span data-ttu-id="36494-2509">Старый формат (до 31 декабря 2012):</span><span class="sxs-lookup"><span data-stu-id="36494-2509">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="36494-2510">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="36494-2510">Seven digits</span></span> 
- <span data-ttu-id="36494-2511">1–2 буквы (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="36494-2511">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="36494-2512">Новый формат (1 января 2013 и после):</span><span class="sxs-lookup"><span data-stu-id="36494-2512">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="36494-2513">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="36494-2513">Seven digits</span></span> 
- <span data-ttu-id="36494-2514">буква (без учета регистра), которая является алфавитным проверочным символом;</span><span class="sxs-lookup"><span data-stu-id="36494-2514">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="36494-2515">буква "A" или "H" (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="36494-2515">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2516">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2516">Checksum</span></span>

<span data-ttu-id="36494-2517">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2518">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2518">Definition</span></span>

<span data-ttu-id="36494-2519">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2520">Функция Func_ireland_pps находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-2520">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2521">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="36494-2521">One of the following is true:</span></span>
    - <span data-ttu-id="36494-2522">найдено ключевое слово из Keyword_ireland_pps;</span><span class="sxs-lookup"><span data-stu-id="36494-2522">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="36494-2523">функция Func_eu_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-2523">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="36494-2524">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2524">The checksum passes.</span></span>

<span data-ttu-id="36494-2525">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2525">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2526">функция Func_ireland_pps находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2526">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2527">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2527">The checksum passes.</span></span>

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2528">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2528">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="36494-2529">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="36494-2529">Keyword_ireland_pps</span></span>

- <span data-ttu-id="36494-2530">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="36494-2530">Personal Public Service Number</span></span> 
- <span data-ttu-id="36494-2531">PPS Number</span><span class="sxs-lookup"><span data-stu-id="36494-2531">PPS Number</span></span> 
- <span data-ttu-id="36494-2532">PPS Num</span><span class="sxs-lookup"><span data-stu-id="36494-2532">PPS Num</span></span> 
- <span data-ttu-id="36494-2533">PPS No.</span><span class="sxs-lookup"><span data-stu-id="36494-2533">PPS No.</span></span> 
- <span data-ttu-id="36494-2534">PPS #</span><span class="sxs-lookup"><span data-stu-id="36494-2534">PPS #</span></span> 
- <span data-ttu-id="36494-2535">PPS #</span><span class="sxs-lookup"><span data-stu-id="36494-2535">PPS#</span></span> 
- <span data-ttu-id="36494-2536">ппсн</span><span class="sxs-lookup"><span data-stu-id="36494-2536">PPSN</span></span> 
- <span data-ttu-id="36494-2537">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="36494-2537">Public Services Card</span></span> 
- <span data-ttu-id="36494-2538">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="36494-2538">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="36494-2539">Уимх.</span><span class="sxs-lookup"><span data-stu-id="36494-2539">Uimh.</span></span> <span data-ttu-id="36494-2540">НАСТРОЕН</span><span class="sxs-lookup"><span data-stu-id="36494-2540">PSP</span></span> 
- <span data-ttu-id="36494-2541">НАСТРОЕН</span><span class="sxs-lookup"><span data-stu-id="36494-2541">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="36494-2542">Номер банковского счета для Израиля</span><span class="sxs-lookup"><span data-stu-id="36494-2542">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2543">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2543">Format</span></span>

<span data-ttu-id="36494-2544">13 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2544">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2545">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2545">Pattern</span></span>

<span data-ttu-id="36494-2546">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="36494-2546">Formatted:</span></span>
- <span data-ttu-id="36494-2547">Две цифры</span><span class="sxs-lookup"><span data-stu-id="36494-2547">Two digits</span></span> 
- <span data-ttu-id="36494-2548">Тире</span><span class="sxs-lookup"><span data-stu-id="36494-2548">A dash</span></span> 
- <span data-ttu-id="36494-2549">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-2549">Three digits</span></span> 
- <span data-ttu-id="36494-2550">Тире</span><span class="sxs-lookup"><span data-stu-id="36494-2550">A dash</span></span> 
- <span data-ttu-id="36494-2551">Восемь цифр</span><span class="sxs-lookup"><span data-stu-id="36494-2551">Eight digits</span></span>

<span data-ttu-id="36494-2552">Неформатированные</span><span class="sxs-lookup"><span data-stu-id="36494-2552">Unformatted:</span></span>
- <span data-ttu-id="36494-2553">	13 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2553">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2554">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2554">Checksum</span></span>

<span data-ttu-id="36494-2555">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2555">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2556">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2556">Definition</span></span>

<span data-ttu-id="36494-2557">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2558">регулярное выражение Regex_israel_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2558">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2559">находится ключевое слово из Keyword_israel_bank_account_number.</span><span class="sxs-lookup"><span data-stu-id="36494-2559">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2560">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2560">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="36494-2561">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="36494-2561">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="36494-2562">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="36494-2562">Bank Account Number</span></span> 
- <span data-ttu-id="36494-2563">Bank Account</span><span class="sxs-lookup"><span data-stu-id="36494-2563">Bank Account</span></span> 
- <span data-ttu-id="36494-2564">Account Number</span><span class="sxs-lookup"><span data-stu-id="36494-2564">Account Number</span></span> 
- <span data-ttu-id="36494-2565">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="36494-2565">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="36494-2566">Национальный идентификатор для Израиля</span><span class="sxs-lookup"><span data-stu-id="36494-2566">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="36494-2567">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2567">Format</span></span>

<span data-ttu-id="36494-2568">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2568">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2569">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2569">Pattern</span></span>

<span data-ttu-id="36494-2570">Девять последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2570">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2571">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2571">Checksum</span></span>

<span data-ttu-id="36494-2572">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2573">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2573">Definition</span></span>

<span data-ttu-id="36494-2574">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2574">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2575">функция Func_israeli_national_id_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2575">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2576">находится ключевое слово из Keyword_Israel_National_ID;</span><span class="sxs-lookup"><span data-stu-id="36494-2576">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="36494-2577">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2577">The checksum passes.</span></span>

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2578">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2578">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="36494-2579">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="36494-2579">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="36494-2580">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="36494-2580">מספר זהות</span></span> 
- <span data-ttu-id="36494-2581">National ID Number</span><span class="sxs-lookup"><span data-stu-id="36494-2581">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="36494-2582">Номер водительского удостоверения для Италии</span><span class="sxs-lookup"><span data-stu-id="36494-2582">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2583">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2583">Format</span></span>

<span data-ttu-id="36494-2584">Сочетание из 10 букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2584">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2585">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2585">Pattern</span></span>

- <span data-ttu-id="36494-2586">Сочетание 10 букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2586">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="36494-2587">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="36494-2587">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="36494-2588">Буква "A" или "V" (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="36494-2588">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="36494-2589">Семь букв (без учета регистра), цифр или символов подчеркивания</span><span class="sxs-lookup"><span data-stu-id="36494-2589">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="36494-2590">Одна буква (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="36494-2590">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2591">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2591">Checksum</span></span>

<span data-ttu-id="36494-2592">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2592">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2593">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2593">Definition</span></span>

<span data-ttu-id="36494-2594">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2594">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2595">регулярное выражение Regex_italy_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2595">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2596">находится ключевое слово из Keyword_italy_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="36494-2596">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2597">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2597">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="36494-2598">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="36494-2598">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="36494-2599">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="36494-2599">numero di patente di guida</span></span> 
- <span data-ttu-id="36494-2600">patente di guida</span><span class="sxs-lookup"><span data-stu-id="36494-2600">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="36494-2601">Номер банковского счета для Японии</span><span class="sxs-lookup"><span data-stu-id="36494-2601">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2602">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2602">Format</span></span>

<span data-ttu-id="36494-2603">Семь или восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2603">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2604">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2604">Pattern</span></span>

<span data-ttu-id="36494-2605">Номер банковского счета:</span><span class="sxs-lookup"><span data-stu-id="36494-2605">Bank account number:</span></span>
- <span data-ttu-id="36494-2606">семь или восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2606">Seven or eight digits</span></span>
- <span data-ttu-id="36494-2607">Код филиала для банковского счета.</span><span class="sxs-lookup"><span data-stu-id="36494-2607">Bank account branch code:</span></span>
- <span data-ttu-id="36494-2608">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="36494-2608">Four digits</span></span> 
- <span data-ttu-id="36494-2609">Пробел или тире (необязательно)</span><span class="sxs-lookup"><span data-stu-id="36494-2609">A space or dash (optional)</span></span> 
- <span data-ttu-id="36494-2610">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-2610">Three digits</span></span>

<span data-ttu-id="36494-2611">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2611">Checksum</span></span>

<span data-ttu-id="36494-2612">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2612">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2613">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2613">Definition</span></span>

<span data-ttu-id="36494-2614">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2614">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2615">Функция Func_jp_bank_account находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-2615">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2616">Находится ключевое слово из Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="36494-2616">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="36494-2617">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="36494-2617">One of the following is true:</span></span>
- <span data-ttu-id="36494-2618">функция Func_jp_bank_account_branch_code находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2618">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2619">найдено ключевое слово из Keyword_jp_bank_branch_code.</span><span class="sxs-lookup"><span data-stu-id="36494-2619">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="36494-2620">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2621">функция Func_jp_bank_account находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2621">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2622">находится ключевое слово из Keyword_jp_bank_account.</span><span class="sxs-lookup"><span data-stu-id="36494-2622">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2623">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2623">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="36494-2624">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="36494-2624">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="36494-2625">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="36494-2625">Checking Account Number</span></span> 
- <span data-ttu-id="36494-2626">Checking Account</span><span class="sxs-lookup"><span data-stu-id="36494-2626">Checking Account</span></span> 
- <span data-ttu-id="36494-2627">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="36494-2627">Checking Account #</span></span> 
- <span data-ttu-id="36494-2628">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="36494-2628">Checking Acct Number</span></span> 
- <span data-ttu-id="36494-2629">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="36494-2629">Checking Acct #</span></span> 
- <span data-ttu-id="36494-2630">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="36494-2630">Checking Acct No.</span></span> 
- <span data-ttu-id="36494-2631">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="36494-2631">Checking Account No.</span></span> 
- <span data-ttu-id="36494-2632">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="36494-2632">Bank Account Number</span></span> 
- <span data-ttu-id="36494-2633">Bank Account</span><span class="sxs-lookup"><span data-stu-id="36494-2633">Bank Account</span></span> 
- <span data-ttu-id="36494-2634">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="36494-2634">Bank Account #</span></span> 
- <span data-ttu-id="36494-2635">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="36494-2635">Bank Acct Number</span></span> 
- <span data-ttu-id="36494-2636">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="36494-2636">Bank Acct #</span></span> 
- <span data-ttu-id="36494-2637">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="36494-2637">Bank Acct No.</span></span> 
- <span data-ttu-id="36494-2638">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="36494-2638">Bank Account No.</span></span> 
- <span data-ttu-id="36494-2639">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="36494-2639">Savings Account Number</span></span> 
- <span data-ttu-id="36494-2640">Savings Account</span><span class="sxs-lookup"><span data-stu-id="36494-2640">Savings Account</span></span> 
- <span data-ttu-id="36494-2641">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="36494-2641">Savings Account #</span></span> 
- <span data-ttu-id="36494-2642">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="36494-2642">Savings Acct Number</span></span> 
- <span data-ttu-id="36494-2643">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="36494-2643">Savings Acct #</span></span> 
- <span data-ttu-id="36494-2644">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="36494-2644">Savings Acct No.</span></span> 
- <span data-ttu-id="36494-2645">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="36494-2645">Savings Account No.</span></span> 
- <span data-ttu-id="36494-2646">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="36494-2646">Debit Account Number</span></span> 
- <span data-ttu-id="36494-2647">Debit Account</span><span class="sxs-lookup"><span data-stu-id="36494-2647">Debit Account</span></span> 
- <span data-ttu-id="36494-2648">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="36494-2648">Debit Account #</span></span> 
- <span data-ttu-id="36494-2649">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="36494-2649">Debit Acct Number</span></span> 
- <span data-ttu-id="36494-2650">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="36494-2650">Debit Acct #</span></span> 
- <span data-ttu-id="36494-2651">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="36494-2651">Debit Acct No.</span></span> 
- <span data-ttu-id="36494-2652">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="36494-2652">Debit Account No.</span></span> 
- <span data-ttu-id="36494-2653">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="36494-2653">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="36494-2654">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="36494-2654">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="36494-2655">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="36494-2655">＃勘定の確認</span></span> 
- <span data-ttu-id="36494-2656">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="36494-2656">勘定番号の確認</span></span> 
- <span data-ttu-id="36494-2657">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="36494-2657">口座番号の確認</span></span> 
- <span data-ttu-id="36494-2658">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="36494-2658">銀行口座番号</span></span> 
- <span data-ttu-id="36494-2659">銀行口座</span><span class="sxs-lookup"><span data-stu-id="36494-2659">銀行口座</span></span> 
- <span data-ttu-id="36494-2660">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="36494-2660">銀行口座＃</span></span> 
- <span data-ttu-id="36494-2661">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="36494-2661">銀行の勘定番号</span></span> 
- <span data-ttu-id="36494-2662">銀行のаккт #</span><span class="sxs-lookup"><span data-stu-id="36494-2662">銀行のacct＃</span></span> 
- <span data-ttu-id="36494-2663">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="36494-2663">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="36494-2664">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="36494-2664">銀行口座番号</span></span>
- <span data-ttu-id="36494-2665">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="36494-2665">普通預金口座番号</span></span> 
- <span data-ttu-id="36494-2666">預金口座</span><span class="sxs-lookup"><span data-stu-id="36494-2666">預金口座</span></span> 
- <span data-ttu-id="36494-2667">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="36494-2667">貯蓄口座＃</span></span> 
- <span data-ttu-id="36494-2668">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="36494-2668">貯蓄勘定の数</span></span> 
- <span data-ttu-id="36494-2669">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="36494-2669">貯蓄勘定＃</span></span> 
- <span data-ttu-id="36494-2670">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="36494-2670">貯蓄勘定番号</span></span> 
- <span data-ttu-id="36494-2671">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="36494-2671">普通預金口座番号</span></span> 
- <span data-ttu-id="36494-2672">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="36494-2672">引き落とし口座番号</span></span> 
- <span data-ttu-id="36494-2673">口座番号</span><span class="sxs-lookup"><span data-stu-id="36494-2673">口座番号</span></span> 
- <span data-ttu-id="36494-2674">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="36494-2674">口座番号＃</span></span> 
- <span data-ttu-id="36494-2675">デビットのаккт番号</span><span class="sxs-lookup"><span data-stu-id="36494-2675">デビットのacct番号</span></span> 
- <span data-ttu-id="36494-2676">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="36494-2676">デビット勘定＃</span></span> 
- <span data-ttu-id="36494-2677">デビットакктの番号</span><span class="sxs-lookup"><span data-stu-id="36494-2677">デビットACCTの番号</span></span> 
- <span data-ttu-id="36494-2678">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="36494-2678">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="36494-2679">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="36494-2679">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="36494-2680">отемачи</span><span class="sxs-lookup"><span data-stu-id="36494-2680">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="36494-2681">Номер водительского удостоверения для Японии</span><span class="sxs-lookup"><span data-stu-id="36494-2681">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2682">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2682">Format</span></span>

<span data-ttu-id="36494-2683">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2683">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2684">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2684">Pattern</span></span>

<span data-ttu-id="36494-2685">12 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2685">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2686">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2686">Checksum</span></span>

<span data-ttu-id="36494-2687">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2687">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2688">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2688">Definition</span></span>

<span data-ttu-id="36494-2689">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2689">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2690">функция Func_jp_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2690">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2691">находится ключевое слово из Keyword_jp_drivers_license_number.</span><span class="sxs-lookup"><span data-stu-id="36494-2691">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2692">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2692">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="36494-2693">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="36494-2693">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="36494-2694">DL #</span><span class="sxs-lookup"><span data-stu-id="36494-2694">dl#</span></span> 
- <span data-ttu-id="36494-2695">DL</span><span class="sxs-lookup"><span data-stu-id="36494-2695">DL＃</span></span> 
- <span data-ttu-id="36494-2696">библиотек #</span><span class="sxs-lookup"><span data-stu-id="36494-2696">dls#</span></span> 
- <span data-ttu-id="36494-2697">БИБЛИОТЕК</span><span class="sxs-lookup"><span data-stu-id="36494-2697">DLS＃</span></span> 
- <span data-ttu-id="36494-2698">driver license</span><span class="sxs-lookup"><span data-stu-id="36494-2698">driver license</span></span> 
- <span data-ttu-id="36494-2699">driver licenses</span><span class="sxs-lookup"><span data-stu-id="36494-2699">driver licenses</span></span> 
- <span data-ttu-id="36494-2700">drivers license</span><span class="sxs-lookup"><span data-stu-id="36494-2700">drivers license</span></span> 
- <span data-ttu-id="36494-2701">driver's license</span><span class="sxs-lookup"><span data-stu-id="36494-2701">driver's license</span></span> 
- <span data-ttu-id="36494-2702">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="36494-2702">drivers licenses</span></span> 
- <span data-ttu-id="36494-2703">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="36494-2703">driver's licenses</span></span> 
- <span data-ttu-id="36494-2704">driving licence</span><span class="sxs-lookup"><span data-stu-id="36494-2704">driving licence</span></span> 
- <span data-ttu-id="36494-2705">лик #</span><span class="sxs-lookup"><span data-stu-id="36494-2705">lic#</span></span> 
- <span data-ttu-id="36494-2706">Лик #</span><span class="sxs-lookup"><span data-stu-id="36494-2706">LIC＃</span></span> 
- <span data-ttu-id="36494-2707">ликс #</span><span class="sxs-lookup"><span data-stu-id="36494-2707">lics#</span></span> 
- <span data-ttu-id="36494-2708">state id</span><span class="sxs-lookup"><span data-stu-id="36494-2708">state id</span></span> 
- <span data-ttu-id="36494-2709">state identification</span><span class="sxs-lookup"><span data-stu-id="36494-2709">state identification</span></span> 
- <span data-ttu-id="36494-2710">state identification number</span><span class="sxs-lookup"><span data-stu-id="36494-2710">state identification number</span></span> 
- <span data-ttu-id="36494-2711">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="36494-2711">低所得国＃</span></span> 
- <span data-ttu-id="36494-2712">免許証</span><span class="sxs-lookup"><span data-stu-id="36494-2712">免許証</span></span> 
- <span data-ttu-id="36494-2713">状態ид</span><span class="sxs-lookup"><span data-stu-id="36494-2713">状態ID</span></span>
- <span data-ttu-id="36494-2714">状態の識別</span><span class="sxs-lookup"><span data-stu-id="36494-2714">状態の識別</span></span> 
- <span data-ttu-id="36494-2715">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="36494-2715">状態の識別番号</span></span> 
- <span data-ttu-id="36494-2716">運転免許</span><span class="sxs-lookup"><span data-stu-id="36494-2716">運転免許</span></span> 
- <span data-ttu-id="36494-2717">運転免許証</span><span class="sxs-lookup"><span data-stu-id="36494-2717">運転免許証</span></span> 
- <span data-ttu-id="36494-2718">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="36494-2718">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="36494-2719">Номер паспорта гражданина Японии</span><span class="sxs-lookup"><span data-stu-id="36494-2719">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2720">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2720">Format</span></span>

<span data-ttu-id="36494-2721">Две буквы, за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2721">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2722">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2722">Pattern</span></span>

<span data-ttu-id="36494-2723">Две буквы (без учета регистра), за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2723">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2724">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2724">Checksum</span></span>

<span data-ttu-id="36494-2725">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2725">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2726">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2726">Definition</span></span>

<span data-ttu-id="36494-2727">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2728">функция Func_jp_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2728">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2729">находится ключевое слово из Keyword_jp_passport.</span><span class="sxs-lookup"><span data-stu-id="36494-2729">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2730">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2730">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="36494-2731">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="36494-2731">Keyword_jp_passport</span></span>

- <span data-ttu-id="36494-2732">パスポート</span><span class="sxs-lookup"><span data-stu-id="36494-2732">パスポート</span></span> 
- <span data-ttu-id="36494-2733">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="36494-2733">パスポート番号</span></span> 
- <span data-ttu-id="36494-2734">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="36494-2734">パスポートのNum</span></span> 
- <span data-ttu-id="36494-2735">パスポート #</span><span class="sxs-lookup"><span data-stu-id="36494-2735">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="36494-2736">Номер регистрации резидента Японии</span><span class="sxs-lookup"><span data-stu-id="36494-2736">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2737">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2737">Format</span></span>

<span data-ttu-id="36494-2738">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2738">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2739">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2739">Pattern</span></span>

<span data-ttu-id="36494-2740">11 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2740">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2741">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2741">Checksum</span></span>

<span data-ttu-id="36494-2742">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2742">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2743">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2743">Definition</span></span>

<span data-ttu-id="36494-2744">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2744">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2745">функция Func_jp_resident_registration_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2745">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2746">находится ключевое слово из Keyword_jp_resident_registration_number.</span><span class="sxs-lookup"><span data-stu-id="36494-2746">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2747">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2747">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="36494-2748">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="36494-2748">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="36494-2749">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="36494-2749">Resident Registration Number</span></span>
- <span data-ttu-id="36494-2750">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="36494-2750">Resident Register Number</span></span> 
- <span data-ttu-id="36494-2751">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="36494-2751">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="36494-2752">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="36494-2752">Resident Registration No.</span></span> 
- <span data-ttu-id="36494-2753">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="36494-2753">Resident Register No.</span></span> 
- <span data-ttu-id="36494-2754">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="36494-2754">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="36494-2755">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="36494-2755">Basic Resident Register No.</span></span> 
- <span data-ttu-id="36494-2756">住民登録番号 、 登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="36494-2756">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="36494-2757">住民基本登録番号 、 登録番号</span><span class="sxs-lookup"><span data-stu-id="36494-2757">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="36494-2758">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="36494-2758">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="36494-2759">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="36494-2759">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="36494-2760">Номер карты социального страхования для Японии (SIN)</span><span class="sxs-lookup"><span data-stu-id="36494-2760">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="36494-2761">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2761">Format</span></span>

<span data-ttu-id="36494-2762">7–12 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2762">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2763">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2763">Pattern</span></span>

<span data-ttu-id="36494-2764">7–12 цифр</span><span class="sxs-lookup"><span data-stu-id="36494-2764">7-12 digits:</span></span>
- <span data-ttu-id="36494-2765">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="36494-2765">Four digits</span></span> 
- <span data-ttu-id="36494-2766">Дефис (необязательно)</span><span class="sxs-lookup"><span data-stu-id="36494-2766">A hyphen (optional)</span></span> 
- <span data-ttu-id="36494-2767">Шесть цифр или</span><span class="sxs-lookup"><span data-stu-id="36494-2767">Six digits OR</span></span>
- <span data-ttu-id="36494-2768">7–12 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2768">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2769">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2769">Checksum</span></span>

<span data-ttu-id="36494-2770">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2770">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2771">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2771">Definition</span></span>

<span data-ttu-id="36494-2772">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2772">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2773">функция Func_jp_sin находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2773">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2774">находится ключевое слово из Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="36494-2774">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="36494-2775">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2775">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2776">функция Func_jp_sin_pre_1997 находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2776">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2777">находится ключевое слово из Keyword_jp_sin.</span><span class="sxs-lookup"><span data-stu-id="36494-2777">A keyword from Keyword_jp_sin is found.</span></span>

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2778">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2778">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="36494-2779">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="36494-2779">Keyword_jp_sin</span></span>

- <span data-ttu-id="36494-2780">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="36494-2780">Social Insurance No.</span></span> 
- <span data-ttu-id="36494-2781">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="36494-2781">Social Insurance Num</span></span> 
- <span data-ttu-id="36494-2782">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="36494-2782">Social Insurance Number</span></span> 
- <span data-ttu-id="36494-2783">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="36494-2783">社会保険のテンキー</span></span> 
- <span data-ttu-id="36494-2784">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="36494-2784">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="36494-2785">Номер карточки для японского языка</span><span class="sxs-lookup"><span data-stu-id="36494-2785">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2786">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2786">Format</span></span>

<span data-ttu-id="36494-2787">12 букв и цифр</span><span class="sxs-lookup"><span data-stu-id="36494-2787">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2788">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2788">Pattern</span></span>

<span data-ttu-id="36494-2789">12 букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-2789">12 letters and digits:</span></span>
- <span data-ttu-id="36494-2790">две буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="36494-2790">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="36494-2791">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2791">Eight digits</span></span> 
- <span data-ttu-id="36494-2792">две буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="36494-2792">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2793">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2793">Checksum</span></span>

<span data-ttu-id="36494-2794">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2794">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2795">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2795">Definition</span></span>

<span data-ttu-id="36494-2796">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2797">Регулярное выражение Regex_jp_residence_card_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2797">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2798">Найдено ключевое слово из Keyword_jp_residence_card_number.</span><span class="sxs-lookup"><span data-stu-id="36494-2798">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2799">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2799">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="36494-2800">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="36494-2800">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="36494-2801">Номер карточки проживания</span><span class="sxs-lookup"><span data-stu-id="36494-2801">Residence card number</span></span>
- <span data-ttu-id="36494-2802">Номер карточки проживания</span><span class="sxs-lookup"><span data-stu-id="36494-2802">Residence card no</span></span>
- <span data-ttu-id="36494-2803">Карточка проживания #</span><span class="sxs-lookup"><span data-stu-id="36494-2803">Residence card #</span></span>
- <span data-ttu-id="36494-2804">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="36494-2804">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="36494-2805">Номер удостоверения личности для Малайзии</span><span class="sxs-lookup"><span data-stu-id="36494-2805">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2806">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2806">Format</span></span>

<span data-ttu-id="36494-2807">12 цифр, содержащих необязательные дефисы.</span><span class="sxs-lookup"><span data-stu-id="36494-2807">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2808">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2808">Pattern</span></span>

<span data-ttu-id="36494-2809">12 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-2809">12 digits:</span></span>
- <span data-ttu-id="36494-2810">шесть цифр в формате ГГММДД (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="36494-2810">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="36494-2811">дефис (необязательно);</span><span class="sxs-lookup"><span data-stu-id="36494-2811">A dash (optional)</span></span> 
- <span data-ttu-id="36494-2812">код места рождения из двух букв;</span><span class="sxs-lookup"><span data-stu-id="36494-2812">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="36494-2813">дефис (необязательно);</span><span class="sxs-lookup"><span data-stu-id="36494-2813">A dash (optional)</span></span> 
- <span data-ttu-id="36494-2814">три случайные цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-2814">Three random digits</span></span> 
- <span data-ttu-id="36494-2815">код пола из одной цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-2815">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2816">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2816">Checksum</span></span>

<span data-ttu-id="36494-2817">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2817">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2818">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2818">Definition</span></span>

<span data-ttu-id="36494-2819">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2819">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2820">регулярное выражение Regex_malaysia_id_card_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2820">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2821">находится ключевое слово из Keyword_malaysia_id_card_number.</span><span class="sxs-lookup"><span data-stu-id="36494-2821">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2822">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2822">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="36494-2823">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="36494-2823">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="36494-2824">карточка цифрового приложения</span><span class="sxs-lookup"><span data-stu-id="36494-2824">digital application card</span></span>
- <span data-ttu-id="36494-2825">i/c</span><span class="sxs-lookup"><span data-stu-id="36494-2825">i/c</span></span>
- <span data-ttu-id="36494-2826">i/c нет</span><span class="sxs-lookup"><span data-stu-id="36494-2826">i/c no</span></span>
- <span data-ttu-id="36494-2827">внутренних</span><span class="sxs-lookup"><span data-stu-id="36494-2827">ic</span></span>
- <span data-ttu-id="36494-2828">МФ нет</span><span class="sxs-lookup"><span data-stu-id="36494-2828">ic no</span></span>
- <span data-ttu-id="36494-2829">id card</span><span class="sxs-lookup"><span data-stu-id="36494-2829">id card</span></span>
- <span data-ttu-id="36494-2830">идентификационная карточка</span><span class="sxs-lookup"><span data-stu-id="36494-2830">identification Card</span></span>
- <span data-ttu-id="36494-2831">identity card</span><span class="sxs-lookup"><span data-stu-id="36494-2831">identity card</span></span>
- <span data-ttu-id="36494-2832">k/p</span><span class="sxs-lookup"><span data-stu-id="36494-2832">k/p</span></span>
- <span data-ttu-id="36494-2833">k/p</span><span class="sxs-lookup"><span data-stu-id="36494-2833">k/p no</span></span>
- <span data-ttu-id="36494-2834">кад акуан Дири</span><span class="sxs-lookup"><span data-stu-id="36494-2834">kad akuan diri</span></span>
- <span data-ttu-id="36494-2835">кад апликаси Digital</span><span class="sxs-lookup"><span data-stu-id="36494-2835">kad aplikasi digital</span></span>
- <span data-ttu-id="36494-2836">кад пенженалан Малайзии</span><span class="sxs-lookup"><span data-stu-id="36494-2836">kad pengenalan malaysia</span></span>
- <span data-ttu-id="36494-2837">ключев</span><span class="sxs-lookup"><span data-stu-id="36494-2837">kp</span></span>
- <span data-ttu-id="36494-2838">ключевой номер</span><span class="sxs-lookup"><span data-stu-id="36494-2838">kp no</span></span>
- <span data-ttu-id="36494-2839">микад</span><span class="sxs-lookup"><span data-stu-id="36494-2839">mykad</span></span>
- <span data-ttu-id="36494-2840">микас</span><span class="sxs-lookup"><span data-stu-id="36494-2840">mykas</span></span>
- <span data-ttu-id="36494-2841">микид</span><span class="sxs-lookup"><span data-stu-id="36494-2841">mykid</span></span>
- <span data-ttu-id="36494-2842">мипр</span><span class="sxs-lookup"><span data-stu-id="36494-2842">mypr</span></span>
- <span data-ttu-id="36494-2843">митентера</span><span class="sxs-lookup"><span data-stu-id="36494-2843">mytentera</span></span>
- <span data-ttu-id="36494-2844">идентификационная карточка Малайзии</span><span class="sxs-lookup"><span data-stu-id="36494-2844">malaysia identity card</span></span>
- <span data-ttu-id="36494-2845">идентификационная карточка малайсиан</span><span class="sxs-lookup"><span data-stu-id="36494-2845">malaysian identity card</span></span>
- <span data-ttu-id="36494-2846">NRIC</span><span class="sxs-lookup"><span data-stu-id="36494-2846">nric</span></span>
- <span data-ttu-id="36494-2847">Личная идентификационная карточка</span><span class="sxs-lookup"><span data-stu-id="36494-2847">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="36494-2848">Номер гражданской службы для Нидерландов (BSN)</span><span class="sxs-lookup"><span data-stu-id="36494-2848">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2849">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2849">Format</span></span>

<span data-ttu-id="36494-2850">8–9 цифр, содержащих необязательные пробелы.</span><span class="sxs-lookup"><span data-stu-id="36494-2850">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2851">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2851">Pattern</span></span>

<span data-ttu-id="36494-2852">8–9 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-2852">8-9 digits:</span></span>
- <span data-ttu-id="36494-2853">три цифры; </span><span class="sxs-lookup"><span data-stu-id="36494-2853">Three digits</span></span> 
- <span data-ttu-id="36494-2854">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="36494-2854">A space (optional)</span></span> 
- <span data-ttu-id="36494-2855">три цифры; </span><span class="sxs-lookup"><span data-stu-id="36494-2855">Three digits</span></span> 
- <span data-ttu-id="36494-2856">пробел (необязательно); </span><span class="sxs-lookup"><span data-stu-id="36494-2856">A space (optional)</span></span> 
- <span data-ttu-id="36494-2857">2–3 цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-2857">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2858">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2858">Checksum</span></span>

<span data-ttu-id="36494-2859">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2859">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2860">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2860">Definition</span></span>

<span data-ttu-id="36494-2861">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2861">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2862">функция Func_netherlands_bsn находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2862">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2863">находится ключевое слово из Keyword_netherlands_bsn;</span><span class="sxs-lookup"><span data-stu-id="36494-2863">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="36494-2864">функция Func_eu_date2 находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-2864">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="36494-2865">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2865">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2866">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2866">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="36494-2867">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="36494-2867">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="36494-2868">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="36494-2868">Citizen service number</span></span> 
- <span data-ttu-id="36494-2869">BSN</span><span class="sxs-lookup"><span data-stu-id="36494-2869">BSN</span></span> 
- <span data-ttu-id="36494-2870">буржерсервиценуммер</span><span class="sxs-lookup"><span data-stu-id="36494-2870">Burgerservicenummer</span></span> 
- <span data-ttu-id="36494-2871">софинуммер</span><span class="sxs-lookup"><span data-stu-id="36494-2871">Sofinummer</span></span> 
- <span data-ttu-id="36494-2872">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="36494-2872">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="36494-2873">персунснуммер</span><span class="sxs-lookup"><span data-stu-id="36494-2873">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="36494-2874">Номер министерства здравоохранения для Новой Зеландии</span><span class="sxs-lookup"><span data-stu-id="36494-2874">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2875">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2875">Format</span></span>

<span data-ttu-id="36494-2876">Три буквы, пробел (необязательно) и четыре цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-2876">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2877">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2877">Pattern</span></span>

<span data-ttu-id="36494-2878">Три буквы (без учета регистра), пробел (необязательно) из четырех цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2878">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2879">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2879">Checksum</span></span>

<span data-ttu-id="36494-2880">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2880">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2881">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2881">Definition</span></span>

<span data-ttu-id="36494-2882">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2882">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2883">функция Func_new_zealand_ministry_of_health_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2883">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2884">находится ключевое слово из Keyword_nz_terms;</span><span class="sxs-lookup"><span data-stu-id="36494-2884">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="36494-2885">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2885">The checksum passes.</span></span>

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

<span data-ttu-id="36494-2886">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2886">Keywords</span></span>

<span data-ttu-id="36494-2887">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="36494-2887">Keyword_nz_terms</span></span>

- <span data-ttu-id="36494-2888">нхи</span><span class="sxs-lookup"><span data-stu-id="36494-2888">NHI</span></span> 
- <span data-ttu-id="36494-2889">Новая Зеландия</span><span class="sxs-lookup"><span data-stu-id="36494-2889">New Zealand</span></span> 
- <span data-ttu-id="36494-2890">Работоспособность</span><span class="sxs-lookup"><span data-stu-id="36494-2890">Health</span></span> 
- <span data-ttu-id="36494-2891">обращения</span><span class="sxs-lookup"><span data-stu-id="36494-2891">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="36494-2892">Идентификационный номер для Норвегии</span><span class="sxs-lookup"><span data-stu-id="36494-2892">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2893">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2893">Format</span></span>

<span data-ttu-id="36494-2894">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2894">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2895">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2895">Pattern</span></span>

<span data-ttu-id="36494-2896">11 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-2896">11 digits:</span></span>
- <span data-ttu-id="36494-2897">шесть цифр в формате ДДММГГ (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="36494-2897">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="36494-2898">индивидуальный номер из трех цифр;</span><span class="sxs-lookup"><span data-stu-id="36494-2898">Three-digit individual number</span></span> 
- <span data-ttu-id="36494-2899">две проверочные цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-2899">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2900">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2900">Checksum</span></span>

<span data-ttu-id="36494-2901">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2901">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2902">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2902">Definition</span></span>

<span data-ttu-id="36494-2903">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2903">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2904">функция Func_norway_id_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2904">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2905">находится ключевое слово из Keyword_norway_id_number;</span><span class="sxs-lookup"><span data-stu-id="36494-2905">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="36494-2906">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2906">The checksum passes.</span></span>
- <span data-ttu-id="36494-2907">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2907">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2908">функция Func_norway_id_numbe находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2908">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2909">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2909">The checksum passes.</span></span>

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2910">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2910">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="36494-2911">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="36494-2911">Keyword_norway_id_number</span></span>

- <span data-ttu-id="36494-2912">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="36494-2912">Personal identification number</span></span>
- <span data-ttu-id="36494-2913">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="36494-2913">Norwegian ID Number</span></span>
- <span data-ttu-id="36494-2914">ID Number</span><span class="sxs-lookup"><span data-stu-id="36494-2914">ID Number</span></span>
- <span data-ttu-id="36494-2915">Процедура</span><span class="sxs-lookup"><span data-stu-id="36494-2915">Identification</span></span>
- <span data-ttu-id="36494-2916">персоннуммер</span><span class="sxs-lookup"><span data-stu-id="36494-2916">Personnummer</span></span>
- <span data-ttu-id="36494-2917">фøдселснуммер</span><span class="sxs-lookup"><span data-stu-id="36494-2917">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="36494-2918">Единый многофункциональный идентификационный номер для Филиппин</span><span class="sxs-lookup"><span data-stu-id="36494-2918">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2919">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2919">Format</span></span>

<span data-ttu-id="36494-2920">12 цифр, разделенных дефисами.</span><span class="sxs-lookup"><span data-stu-id="36494-2920">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2921">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2921">Pattern</span></span>

<span data-ttu-id="36494-2922">12 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-2922">12 digits:</span></span>
- <span data-ttu-id="36494-2923">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-2923">Four digits</span></span> 
- <span data-ttu-id="36494-2924">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-2924">A hyphen</span></span> 
- <span data-ttu-id="36494-2925">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="36494-2925">Seven digits</span></span> 
- <span data-ttu-id="36494-2926">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-2926">A hyphen</span></span> 
- <span data-ttu-id="36494-2927">одна цифра.</span><span class="sxs-lookup"><span data-stu-id="36494-2927">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2928">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2928">Checksum</span></span>

<span data-ttu-id="36494-2929">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-2929">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2930">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2930">Definition</span></span>

<span data-ttu-id="36494-2931">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2931">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2932">регулярное выражение Regex_philippines_unified_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2932">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2933">находится ключевое слово из Keyword_philippines_id.</span><span class="sxs-lookup"><span data-stu-id="36494-2933">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2934">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2934">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="36494-2935">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="36494-2935">Keyword_philippines_id</span></span>

- <span data-ttu-id="36494-2936">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="36494-2936">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="36494-2937">умид</span><span class="sxs-lookup"><span data-stu-id="36494-2937">UMID</span></span> 
- <span data-ttu-id="36494-2938">Identity Card</span><span class="sxs-lookup"><span data-stu-id="36494-2938">Identity Card</span></span> 
- <span data-ttu-id="36494-2939">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="36494-2939">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="36494-2940">Номер удостоверения личности для Польши</span><span class="sxs-lookup"><span data-stu-id="36494-2940">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="36494-2941">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2941">Format</span></span>

<span data-ttu-id="36494-2942">Три буквы и шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2942">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2943">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2943">Pattern</span></span>

<span data-ttu-id="36494-2944">Три буквы (без учета регистра), за которыми следуют шесть цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2944">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2945">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2945">Checksum</span></span>

<span data-ttu-id="36494-2946">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2946">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2947">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2947">Definition</span></span>

<span data-ttu-id="36494-2948">Политика защиты от потери данных — 75% уверенности, что она обнаружила этот тип конфиденциальной информации, если в пределах близости от 300 символов: функция Func_polish_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2948">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="36494-2949">находится ключевое слово из Keyword_polish_national_id_passport_number;</span><span class="sxs-lookup"><span data-stu-id="36494-2949">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="36494-2950">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2950">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2951">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2951">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="36494-2952">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="36494-2952">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="36494-2953">Довóд особисти</span><span class="sxs-lookup"><span data-stu-id="36494-2953">Dowód osobisty</span></span>
- <span data-ttu-id="36494-2954">Нумер доводу особистего</span><span class="sxs-lookup"><span data-stu-id="36494-2954">Numer dowodu osobistego</span></span>
- <span data-ttu-id="36494-2955">Назва i нумер доводу особистего</span><span class="sxs-lookup"><span data-stu-id="36494-2955">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="36494-2956">Назва i НР доводу особистего</span><span class="sxs-lookup"><span data-stu-id="36494-2956">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="36494-2957">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="36494-2957">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="36494-2958">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="36494-2958">Dowód Tożsamości</span></span>
- <span data-ttu-id="36494-2959">Dow.</span><span class="sxs-lookup"><span data-stu-id="36494-2959">dow.</span></span> <span data-ttu-id="36494-2960">совместим.</span><span class="sxs-lookup"><span data-stu-id="36494-2960">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="36494-2961">Национальный идентификатор (PESEL), Польша</span><span class="sxs-lookup"><span data-stu-id="36494-2961">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="36494-2962">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2962">Format</span></span>

<span data-ttu-id="36494-2963">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2963">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2964">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2964">Pattern</span></span>

<span data-ttu-id="36494-2965">11 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2965">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2966">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2966">Checksum</span></span>

<span data-ttu-id="36494-2967">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2967">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2968">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2968">Definition</span></span>

<span data-ttu-id="36494-2969">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2969">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2970">функция Func_pesel_identification_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2970">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2971">находится ключевое слово из Keyword_pesel_identification_number;</span><span class="sxs-lookup"><span data-stu-id="36494-2971">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="36494-2972">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2972">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-2973">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2973">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="36494-2974">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="36494-2974">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="36494-2975">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="36494-2975">Nr PESEL</span></span>
- <span data-ttu-id="36494-2976">PESEL</span><span class="sxs-lookup"><span data-stu-id="36494-2976">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="36494-2977">Номер паспорта для Польши</span><span class="sxs-lookup"><span data-stu-id="36494-2977">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="36494-2978">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2978">Format</span></span>

<span data-ttu-id="36494-2979">Две буквы и семь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2979">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2980">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2980">Pattern</span></span>

<span data-ttu-id="36494-2981">Две буквы (без учета регистра), за которыми следуют семь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2981">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-2982">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-2982">Checksum</span></span>

<span data-ttu-id="36494-2983">Да</span><span class="sxs-lookup"><span data-stu-id="36494-2983">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-2984">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-2984">Definition</span></span>

<span data-ttu-id="36494-2985">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-2985">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-2986">функция Func_polish_passport_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-2986">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-2987">находится ключевое слово из Keyword_polish_national_id_passport_number;</span><span class="sxs-lookup"><span data-stu-id="36494-2987">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="36494-2988">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-2988">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="36494-2989">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-2989">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="36494-2990">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="36494-2990">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="36494-2991">Нумер пасзпорту</span><span class="sxs-lookup"><span data-stu-id="36494-2991">Numer paszportu</span></span>
- <span data-ttu-id="36494-2992">НР.</span><span class="sxs-lookup"><span data-stu-id="36494-2992">Nr.</span></span> <span data-ttu-id="36494-2993">пасзпорту</span><span class="sxs-lookup"><span data-stu-id="36494-2993">Paszportu</span></span>
- <span data-ttu-id="36494-2994">пасзпорт</span><span class="sxs-lookup"><span data-stu-id="36494-2994">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="36494-2995">Номер карты гражданина Португалии</span><span class="sxs-lookup"><span data-stu-id="36494-2995">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-2996">Format</span><span class="sxs-lookup"><span data-stu-id="36494-2996">Format</span></span>

<span data-ttu-id="36494-2997">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2997">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-2998">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-2998">Pattern</span></span>

<span data-ttu-id="36494-2999">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-2999">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3000">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3000">Checksum</span></span>

<span data-ttu-id="36494-3001">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3001">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3002">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3002">Definition</span></span>

<span data-ttu-id="36494-3003">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3003">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3004">регулярное выражение Regex_portugal_citizen_card находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3004">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3005">находится ключевое слово из Keyword_portugal_citizen_card.</span><span class="sxs-lookup"><span data-stu-id="36494-3005">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3006">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3006">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="36494-3007">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="36494-3007">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="36494-3008">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="36494-3008">Citizen Card</span></span>
- <span data-ttu-id="36494-3009">National ID Card</span><span class="sxs-lookup"><span data-stu-id="36494-3009">National ID Card</span></span>
- <span data-ttu-id="36494-3010">CC</span><span class="sxs-lookup"><span data-stu-id="36494-3010">CC</span></span>
- <span data-ttu-id="36494-3011">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="36494-3011">Cartão de Cidadão</span></span>
- <span data-ttu-id="36494-3012">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="36494-3012">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="36494-3013">Национальный идентификатор для Саудовской Аравии</span><span class="sxs-lookup"><span data-stu-id="36494-3013">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="36494-3014">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3014">Format</span></span>

<span data-ttu-id="36494-3015">10 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3015">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3016">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3016">Pattern</span></span>

<span data-ttu-id="36494-3017">10 последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3017">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3018">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3018">Checksum</span></span>

<span data-ttu-id="36494-3019">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3019">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3020">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3020">Definition</span></span>

<span data-ttu-id="36494-3021">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3021">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3022">регулярное выражение Regex_saudi_arabia_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3022">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3023">находится ключевое слово из Keyword_saudi_arabia_national_id.</span><span class="sxs-lookup"><span data-stu-id="36494-3023">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3024">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3024">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="36494-3025">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="36494-3025">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="36494-3026">Identification Card</span><span class="sxs-lookup"><span data-stu-id="36494-3026">Identification Card</span></span> 
- <span data-ttu-id="36494-3027">I card number</span><span class="sxs-lookup"><span data-stu-id="36494-3027">I card number</span></span> 
- <span data-ttu-id="36494-3028">ID number</span><span class="sxs-lookup"><span data-stu-id="36494-3028">ID number</span></span> 
- <span data-ttu-id="36494-3029">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="36494-3029">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="36494-3030">Номер внутреннего удостоверения личности гражданина Сингапура (NRIC)</span><span class="sxs-lookup"><span data-stu-id="36494-3030">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3031">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3031">Format</span></span>

<span data-ttu-id="36494-3032">Девять букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3032">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3033">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3033">Pattern</span></span>

- <span data-ttu-id="36494-3034">Девять букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-3034">Nine letters and digits:</span></span>
- <span data-ttu-id="36494-3035">буква "F", "G", "S" или "T" (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="36494-3035">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="36494-3036">семь цифр;</span><span class="sxs-lookup"><span data-stu-id="36494-3036">Seven digits</span></span> 
- <span data-ttu-id="36494-3037">алфавитный проверочный символ.</span><span class="sxs-lookup"><span data-stu-id="36494-3037">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3038">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3038">Checksum</span></span>

<span data-ttu-id="36494-3039">Да</span><span class="sxs-lookup"><span data-stu-id="36494-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3040">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3040">Definition</span></span>

<span data-ttu-id="36494-3041">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3042">регулярное выражение Regex_singapore_nric находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3042">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3043">находится ключевое слово из Keyword_singapore_nric;</span><span class="sxs-lookup"><span data-stu-id="36494-3043">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="36494-3044">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-3044">The checksum passes.</span></span>

<span data-ttu-id="36494-3045">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3045">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3046">регулярное выражение Regex_singapore_nric находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3046">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3047">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-3047">The checksum passes.</span></span>

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3048">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3048">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="36494-3049">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="36494-3049">Keyword_singapore_nric</span></span>

- <span data-ttu-id="36494-3050">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="36494-3050">National Registration Identity Card</span></span> 
- <span data-ttu-id="36494-3051">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="36494-3051">Identity Card Number</span></span> 
- <span data-ttu-id="36494-3052">NRIC</span><span class="sxs-lookup"><span data-stu-id="36494-3052">NRIC</span></span> 
- <span data-ttu-id="36494-3053">ВНУТРЕННИХ</span><span class="sxs-lookup"><span data-stu-id="36494-3053">IC</span></span> 
- <span data-ttu-id="36494-3054">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="36494-3054">Foreign Identification Number</span></span> 
- <span data-ttu-id="36494-3055">ПРОЦЕНТ</span><span class="sxs-lookup"><span data-stu-id="36494-3055">FIN</span></span> 
- <span data-ttu-id="36494-3056">身份证</span><span class="sxs-lookup"><span data-stu-id="36494-3056">身份证</span></span> 
- <span data-ttu-id="36494-3057">身份證</span><span class="sxs-lookup"><span data-stu-id="36494-3057">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="36494-3058">Идентификационный номер для Южной Африки</span><span class="sxs-lookup"><span data-stu-id="36494-3058">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3059">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3059">Format</span></span>

<span data-ttu-id="36494-3060">13 цифр, которые могут содержать пробелы.</span><span class="sxs-lookup"><span data-stu-id="36494-3060">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3061">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3061">Pattern</span></span>

<span data-ttu-id="36494-3062">13 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-3062">13 digits:</span></span>
- <span data-ttu-id="36494-3063">шесть цифр в формате ГГММДД (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="36494-3063">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="36494-3064">четыре цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-3064">Four digits</span></span> 
- <span data-ttu-id="36494-3065">индикатор гражданства в виде одной цифры;</span><span class="sxs-lookup"><span data-stu-id="36494-3065">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="36494-3066">цифра "8" или "9";</span><span class="sxs-lookup"><span data-stu-id="36494-3066">The digit "8" or "9"</span></span> 
- <span data-ttu-id="36494-3067">одна цифра (проверочная).</span><span class="sxs-lookup"><span data-stu-id="36494-3067">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3068">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3068">Checksum</span></span>

<span data-ttu-id="36494-3069">Да</span><span class="sxs-lookup"><span data-stu-id="36494-3069">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3070">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3070">Definition</span></span>

<span data-ttu-id="36494-3071">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3071">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3072">функция Func_south_africa_identification_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3072">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3073">находится ключевое слово из Keyword_south_africa_identification_number;</span><span class="sxs-lookup"><span data-stu-id="36494-3073">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="36494-3074">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-3074">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3075">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3075">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="36494-3076">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="36494-3076">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="36494-3077">Identity card</span><span class="sxs-lookup"><span data-stu-id="36494-3077">Identity card</span></span>
- <span data-ttu-id="36494-3078">ID</span><span class="sxs-lookup"><span data-stu-id="36494-3078">ID</span></span>
- <span data-ttu-id="36494-3079">Процедура</span><span class="sxs-lookup"><span data-stu-id="36494-3079">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="36494-3080">Регистрационный номер жителя Южной Кореи</span><span class="sxs-lookup"><span data-stu-id="36494-3080">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3081">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3081">Format</span></span>

<span data-ttu-id="36494-3082">13 цифр, содержащих дефис.</span><span class="sxs-lookup"><span data-stu-id="36494-3082">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3083">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3083">Pattern</span></span>

<span data-ttu-id="36494-3084">13 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-3084">13 digits:</span></span>
- <span data-ttu-id="36494-3085">шесть цифр в формате ГГММДД (дата рождения);</span><span class="sxs-lookup"><span data-stu-id="36494-3085">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="36494-3086">дефис;</span><span class="sxs-lookup"><span data-stu-id="36494-3086">A hyphen</span></span> 
- <span data-ttu-id="36494-3087">одна цифра (определяет век и пол);</span><span class="sxs-lookup"><span data-stu-id="36494-3087">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="36494-3088">код региона рождения из четырех цифр;</span><span class="sxs-lookup"><span data-stu-id="36494-3088">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="36494-3089">одна цифра, используемая для разграничения людей, у которых предшествующие цифры совпадают;</span><span class="sxs-lookup"><span data-stu-id="36494-3089">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="36494-3090">проверочная цифра.</span><span class="sxs-lookup"><span data-stu-id="36494-3090">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3091">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3091">Checksum</span></span>

<span data-ttu-id="36494-3092">Да</span><span class="sxs-lookup"><span data-stu-id="36494-3092">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3093">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3093">Definition</span></span>

<span data-ttu-id="36494-3094">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3094">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3095">функция Func_south_korea_resident_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3095">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3096">находится ключевое слово из Keyword_south_korea_resident_number;</span><span class="sxs-lookup"><span data-stu-id="36494-3096">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="36494-3097">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-3097">The checksum passes.</span></span>

<span data-ttu-id="36494-3098">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3098">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3099">функция Func_south_korea_resident_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3099">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3100">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-3100">The checksum passes.</span></span>

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3101">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3101">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="36494-3102">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="36494-3102">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="36494-3103">National ID card</span><span class="sxs-lookup"><span data-stu-id="36494-3103">National ID card</span></span> 
- <span data-ttu-id="36494-3104">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="36494-3104">Citizen's Registration Number</span></span> 
- <span data-ttu-id="36494-3105">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="36494-3105">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="36494-3106">ррн</span><span class="sxs-lookup"><span data-stu-id="36494-3106">RRN</span></span> 
- <span data-ttu-id="36494-3107">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="36494-3107">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="36494-3108">Страховой номер для Испании (SSN)</span><span class="sxs-lookup"><span data-stu-id="36494-3108">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="36494-3109">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3109">Format</span></span>

<span data-ttu-id="36494-3110">11–12 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3110">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3111">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3111">Pattern</span></span>

<span data-ttu-id="36494-3112">11-12 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-3112">11-12 digits:</span></span>
- <span data-ttu-id="36494-3113">Две цифры</span><span class="sxs-lookup"><span data-stu-id="36494-3113">Two digits</span></span> 
- <span data-ttu-id="36494-3114">Косая черта (необязательно)</span><span class="sxs-lookup"><span data-stu-id="36494-3114">A forward slash (optional)</span></span> 
- <span data-ttu-id="36494-3115">7–8 цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3115">7-8 digits</span></span> 
- <span data-ttu-id="36494-3116">Косая черта (необязательно)</span><span class="sxs-lookup"><span data-stu-id="36494-3116">A forward slash (optional)</span></span> 
- <span data-ttu-id="36494-3117">Две цифры</span><span class="sxs-lookup"><span data-stu-id="36494-3117">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3118">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3118">Checksum</span></span>

<span data-ttu-id="36494-3119">Да</span><span class="sxs-lookup"><span data-stu-id="36494-3119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3120">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3120">Definition</span></span>

<span data-ttu-id="36494-3121">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3122">функция Func_spanish_social_security_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3122">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3123">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-3123">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3124">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3124">Keywords</span></span>

<span data-ttu-id="36494-3125">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3125">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="36494-3126">Строка подключения к SQL Server</span><span class="sxs-lookup"><span data-stu-id="36494-3126">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="36494-3127">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3127">Format</span></span>

<span data-ttu-id="36494-3128">Строка "идентификатор пользователя", "идентификатор пользователя", "UID" или "UserId", за которыми следуют символы и строки, описанные в приведенном ниже шаблоне.</span><span class="sxs-lookup"><span data-stu-id="36494-3128">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3129">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3129">Pattern</span></span>

- <span data-ttu-id="36494-3130">Строка "идентификатор пользователя", "идентификатор пользователя", "UID" или "UserId"</span><span class="sxs-lookup"><span data-stu-id="36494-3130">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="36494-3131">Любая комбинация из 1-200 прописных или строчных букв, цифр, символов, специальных символов и пробелов.</span><span class="sxs-lookup"><span data-stu-id="36494-3131">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="36494-3132">Строка "Password" или "pwd", где "pwd" не предшествует буква нижнего регистра</span><span class="sxs-lookup"><span data-stu-id="36494-3132">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="36494-3133">Знак равенства (=);</span><span class="sxs-lookup"><span data-stu-id="36494-3133">An equal sign (=)</span></span>
- <span data-ttu-id="36494-3134">Любой символ, не являющийся знаком доллара ($), символ процента (%), символ "больше" (>), символ "@", "символ" (@), знак кавычек ("), точка с запятой (;), левая фигурная скобка ([) или левая квадратная скобка ({)</span><span class="sxs-lookup"><span data-stu-id="36494-3134">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="36494-3135">Любая комбинация 7-128 символов, не отделяющая точку с запятой (;), косая черта (/) или кавычки (").</span><span class="sxs-lookup"><span data-stu-id="36494-3135">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="36494-3136">Точка с запятой (;) или кавычки (")</span><span class="sxs-lookup"><span data-stu-id="36494-3136">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3137">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3137">Checksum</span></span>

<span data-ttu-id="36494-3138">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3138">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3139">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3139">Definition</span></span>

<span data-ttu-id="36494-3140">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3141">Регулярное выражение CEP_Regex_SQLServerConnectionString находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3141">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3142">**Не** найдено ключевое слово из CEP_GlobalFilter.</span><span class="sxs-lookup"><span data-stu-id="36494-3142">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="36494-3143">Регулярное выражение CEP_PasswordPlaceHolder не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3143">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3144">Регулярное выражение CEP_CommonExampleKeywords не **находит содержимое** , которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3144">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3145">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3145">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="36494-3146">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="36494-3146">CEP_GlobalFilter</span></span>

- <span data-ttu-id="36494-3147">Некоторые пароли</span><span class="sxs-lookup"><span data-stu-id="36494-3147">some-password</span></span>
- <span data-ttu-id="36494-3148">сомепассворд</span><span class="sxs-lookup"><span data-stu-id="36494-3148">somepassword</span></span>
- <span data-ttu-id="36494-3149">секретпассворд</span><span class="sxs-lookup"><span data-stu-id="36494-3149">secretPassword</span></span>
- <span data-ttu-id="36494-3150">примером</span><span class="sxs-lookup"><span data-stu-id="36494-3150">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="36494-3151">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="36494-3151">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="36494-3152">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="36494-3152">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="36494-3153">Пароль или pwd, за которым следует 0-2 пробелов, знак равенства (=), 0-2 пробелы и звездочка (\*)--или--</span><span class="sxs-lookup"><span data-stu-id="36494-3153">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="36494-3154">Пароль или pwd, а затем:</span><span class="sxs-lookup"><span data-stu-id="36494-3154">Password or pwd followed by:</span></span>
    - <span data-ttu-id="36494-3155">Знак равенства (=)</span><span class="sxs-lookup"><span data-stu-id="36494-3155">Equal sign (=)</span></span>
    - <span data-ttu-id="36494-3156">Символ "меньше" (<)</span><span class="sxs-lookup"><span data-stu-id="36494-3156">Less than symbol (<)</span></span>
    - <span data-ttu-id="36494-3157">Любое сочетание 1-200 символов, которые являются буквами верхнего или нижнего регистра, цифрами, звездочкой (\*), дефисом (-), подчеркиванием (_) или символом пробела</span><span class="sxs-lookup"><span data-stu-id="36494-3157">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="36494-3158">Символ "больше" (>)</span><span class="sxs-lookup"><span data-stu-id="36494-3158">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="36494-3159">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="36494-3159">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="36494-3160">(Технически, обратите внимание, что этот тип конфиденциальной информации определяет эти ключевые слова с помощью регулярного выражения, а не списка ключевых слов.)</span><span class="sxs-lookup"><span data-stu-id="36494-3160">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="36494-3161">компанией</span><span class="sxs-lookup"><span data-stu-id="36494-3161">contoso</span></span>
- <span data-ttu-id="36494-3162">компании</span><span class="sxs-lookup"><span data-stu-id="36494-3162">fabrikam</span></span>
- <span data-ttu-id="36494-3163">базу</span><span class="sxs-lookup"><span data-stu-id="36494-3163">northwind</span></span>
- <span data-ttu-id="36494-3164">песочниц</span><span class="sxs-lookup"><span data-stu-id="36494-3164">sandbox</span></span>
- <span data-ttu-id="36494-3165">онебокс</span><span class="sxs-lookup"><span data-stu-id="36494-3165">onebox</span></span>
- <span data-ttu-id="36494-3166">localhost</span><span class="sxs-lookup"><span data-stu-id="36494-3166">localhost</span></span>
- <span data-ttu-id="36494-3167">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="36494-3167">127.0.0.1</span></span>
- <span data-ttu-id="36494-3168">тестакс.</span><span class="sxs-lookup"><span data-stu-id="36494-3168">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="36494-3169">порта</span><span class="sxs-lookup"><span data-stu-id="36494-3169">com</span></span>
- <span data-ttu-id="36494-3170">s — int.</span><span class="sxs-lookup"><span data-stu-id="36494-3170">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="36494-3171">команде</span><span class="sxs-lookup"><span data-stu-id="36494-3171">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="36494-3172">Национальный идентификатор для Швеции</span><span class="sxs-lookup"><span data-stu-id="36494-3172">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="36494-3173">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3173">Format</span></span>

<span data-ttu-id="36494-3174">10 или 12 цифр и дополнительный разделитель.</span><span class="sxs-lookup"><span data-stu-id="36494-3174">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3175">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3175">Pattern</span></span>

<span data-ttu-id="36494-3176">10 или 12 цифр с необязательным разделителем</span><span class="sxs-lookup"><span data-stu-id="36494-3176">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="36494-3177">2–4 цифры (необязательно)</span><span class="sxs-lookup"><span data-stu-id="36494-3177">2-4 digits (optional)</span></span> 
- <span data-ttu-id="36494-3178">Шесть цифр в формате даты ГГММДД.</span><span class="sxs-lookup"><span data-stu-id="36494-3178">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="36494-3179">Разделитель - или + (необязательно)</span><span class="sxs-lookup"><span data-stu-id="36494-3179">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="36494-3180">четыре цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-3180">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3181">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3181">Checksum</span></span>

<span data-ttu-id="36494-3182">Да</span><span class="sxs-lookup"><span data-stu-id="36494-3182">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3183">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3183">Definition</span></span>

<span data-ttu-id="36494-3184">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3184">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3185">функция Func_swedish_national_identifier находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3185">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3186">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-3186">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3187">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3187">Keywords</span></span>

<span data-ttu-id="36494-3188">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3188">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="36494-3189">Номер паспорта гражданина Швеции</span><span class="sxs-lookup"><span data-stu-id="36494-3189">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3190">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3190">Format</span></span>

<span data-ttu-id="36494-3191">Восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3191">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3192">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3192">Pattern</span></span>

<span data-ttu-id="36494-3193">Восемь последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3193">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3194">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3194">Checksum</span></span>

<span data-ttu-id="36494-3195">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3195">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3196">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3196">Definition</span></span>

<span data-ttu-id="36494-3197">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3198">Регулярное выражение Regex_sweden_passport_number находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3198">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3199">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="36494-3199">One of the following is true:</span></span>
    - <span data-ttu-id="36494-3200">найдено ключевое слово из Keyword_passport;</span><span class="sxs-lookup"><span data-stu-id="36494-3200">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="36494-3201">найдено ключевое слово из Keyword_sweden_passport.</span><span class="sxs-lookup"><span data-stu-id="36494-3201">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3202">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3202">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="36494-3203">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="36494-3203">Keyword_sweden_passport</span></span>

- <span data-ttu-id="36494-3204">visa requirements</span><span class="sxs-lookup"><span data-stu-id="36494-3204">visa requirements</span></span> 
- <span data-ttu-id="36494-3205">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="36494-3205">Alien Registration Card</span></span> 
- <span data-ttu-id="36494-3206">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="36494-3206">Schengen visas</span></span> 
- <span data-ttu-id="36494-3207">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="36494-3207">Schengen visa</span></span> 
- <span data-ttu-id="36494-3208">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="36494-3208">Visa Processing</span></span> 
- <span data-ttu-id="36494-3209">Visa Type</span><span class="sxs-lookup"><span data-stu-id="36494-3209">Visa Type</span></span> 
- <span data-ttu-id="36494-3210">Single Entry</span><span class="sxs-lookup"><span data-stu-id="36494-3210">Single Entry</span></span> 
- <span data-ttu-id="36494-3211">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="36494-3211">Multiple Entry</span></span> 
- <span data-ttu-id="36494-3212">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="36494-3212">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="36494-3213">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="36494-3213">Keyword_passport</span></span>

- <span data-ttu-id="36494-3214">Passport Number</span><span class="sxs-lookup"><span data-stu-id="36494-3214">Passport Number</span></span> 
- <span data-ttu-id="36494-3215">Passport No</span><span class="sxs-lookup"><span data-stu-id="36494-3215">Passport No</span></span> 
- <span data-ttu-id="36494-3216">Passport#</span><span class="sxs-lookup"><span data-stu-id="36494-3216">Passport #</span></span> 
- <span data-ttu-id="36494-3217">Службу #</span><span class="sxs-lookup"><span data-stu-id="36494-3217">Passport#</span></span> 
- <span data-ttu-id="36494-3218">пасспортид</span><span class="sxs-lookup"><span data-stu-id="36494-3218">PassportID</span></span> 
- <span data-ttu-id="36494-3219">пасспортно</span><span class="sxs-lookup"><span data-stu-id="36494-3219">Passportno</span></span> 
- <span data-ttu-id="36494-3220">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="36494-3220">passportnumber</span></span> 
- <span data-ttu-id="36494-3221">パスポート</span><span class="sxs-lookup"><span data-stu-id="36494-3221">パスポート</span></span> 
- <span data-ttu-id="36494-3222">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="36494-3222">パスポート番号</span></span> 
- <span data-ttu-id="36494-3223">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="36494-3223">パスポートのNum</span></span> 
- <span data-ttu-id="36494-3224">パスポート #</span><span class="sxs-lookup"><span data-stu-id="36494-3224">パスポート＃</span></span> 
- <span data-ttu-id="36494-3225">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="36494-3225">Numéro de passeport</span></span> 
- <span data-ttu-id="36494-3226">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="36494-3226">Passeport n °</span></span> 
- <span data-ttu-id="36494-3227">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="36494-3227">Passeport Non</span></span> 
- <span data-ttu-id="36494-3228">Passeport#</span><span class="sxs-lookup"><span data-stu-id="36494-3228">Passeport #</span></span> 
- <span data-ttu-id="36494-3229">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="36494-3229">Passeport#</span></span> 
- <span data-ttu-id="36494-3230">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="36494-3230">PasseportNon</span></span> 
- <span data-ttu-id="36494-3231">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="36494-3231">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="36494-3232">Код SWIFT</span><span class="sxs-lookup"><span data-stu-id="36494-3232">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="36494-3233">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3233">Format</span></span>

<span data-ttu-id="36494-3234">Четыре буквы, за которыми следуют от 5 до 31 буквы или цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-3234">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3235">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3235">Pattern</span></span>

<span data-ttu-id="36494-3236">Четыре буквы, за которыми следуют от 5 до 31 буквы или цифры</span><span class="sxs-lookup"><span data-stu-id="36494-3236">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="36494-3237">Четырехбуквенный код банка (без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="36494-3237">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="36494-3238">Необязательный пробел</span><span class="sxs-lookup"><span data-stu-id="36494-3238">An optional space</span></span> 
- <span data-ttu-id="36494-3239">4–28 букв или цифр (основной номер банковского счета, BBAN)</span><span class="sxs-lookup"><span data-stu-id="36494-3239">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="36494-3240">Необязательный пробел</span><span class="sxs-lookup"><span data-stu-id="36494-3240">An optional space</span></span> 
- <span data-ttu-id="36494-3241">1–3 буквы или цифры (оставшаяся часть BBAN)</span><span class="sxs-lookup"><span data-stu-id="36494-3241">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3242">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3242">Checksum</span></span>

<span data-ttu-id="36494-3243">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3243">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3244">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3244">Definition</span></span>

<span data-ttu-id="36494-3245">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3245">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3246">регулярное выражение Regex_swift находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3246">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3247">находится ключевое слово из Keyword_swift.</span><span class="sxs-lookup"><span data-stu-id="36494-3247">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3248">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3248">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="36494-3249">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="36494-3249">Keyword_swift</span></span>

- <span data-ttu-id="36494-3250">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="36494-3250">international organization for standardization 9362</span></span> 
- <span data-ttu-id="36494-3251">iso 9362</span><span class="sxs-lookup"><span data-stu-id="36494-3251">iso 9362</span></span> 
- <span data-ttu-id="36494-3252">iso9362</span><span class="sxs-lookup"><span data-stu-id="36494-3252">iso9362</span></span> 
- <span data-ttu-id="36494-3253">SWIFT\#</span><span class="sxs-lookup"><span data-stu-id="36494-3253">swift\#</span></span> 
- <span data-ttu-id="36494-3254">свифткоде</span><span class="sxs-lookup"><span data-stu-id="36494-3254">swiftcode</span></span> 
- <span data-ttu-id="36494-3255">свифтнумбер</span><span class="sxs-lookup"><span data-stu-id="36494-3255">swiftnumber</span></span> 
- <span data-ttu-id="36494-3256">свифтраутингнумбер</span><span class="sxs-lookup"><span data-stu-id="36494-3256">swiftroutingnumber</span></span> 
- <span data-ttu-id="36494-3257">swift code</span><span class="sxs-lookup"><span data-stu-id="36494-3257">swift code</span></span> 
- <span data-ttu-id="36494-3258">swift number #</span><span class="sxs-lookup"><span data-stu-id="36494-3258">swift number #</span></span> 
- <span data-ttu-id="36494-3259">swift routing number</span><span class="sxs-lookup"><span data-stu-id="36494-3259">swift routing number</span></span> 
- <span data-ttu-id="36494-3260">bic number</span><span class="sxs-lookup"><span data-stu-id="36494-3260">bic number</span></span> 
- <span data-ttu-id="36494-3261">bic code</span><span class="sxs-lookup"><span data-stu-id="36494-3261">bic code</span></span> 
- <span data-ttu-id="36494-3262">БИК\#</span><span class="sxs-lookup"><span data-stu-id="36494-3262">bic \#</span></span> 
- <span data-ttu-id="36494-3263">БИК\#</span><span class="sxs-lookup"><span data-stu-id="36494-3263">bic\#</span></span> 
- <span data-ttu-id="36494-3264">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="36494-3264">bank identifier code</span></span> 
- <span data-ttu-id="36494-3265">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="36494-3265">標準化9362</span></span> 
- <span data-ttu-id="36494-3266">迅速 #</span><span class="sxs-lookup"><span data-stu-id="36494-3266">迅速＃</span></span> 
- <span data-ttu-id="36494-3267">свифтコード</span><span class="sxs-lookup"><span data-stu-id="36494-3267">SWIFTコード</span></span> 
- <span data-ttu-id="36494-3268">свифт番号</span><span class="sxs-lookup"><span data-stu-id="36494-3268">SWIFT番号</span></span> 
- <span data-ttu-id="36494-3269">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="36494-3269">迅速なルーティング番号</span></span> 
- <span data-ttu-id="36494-3270">бик番号</span><span class="sxs-lookup"><span data-stu-id="36494-3270">BIC番号</span></span> 
- <span data-ttu-id="36494-3271">бикコード</span><span class="sxs-lookup"><span data-stu-id="36494-3271">BICコード</span></span> 
- <span data-ttu-id="36494-3272">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="36494-3272">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="36494-3273">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="36494-3273">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="36494-3274">Быстрая\#</span><span class="sxs-lookup"><span data-stu-id="36494-3274">rapide \#</span></span> 
- <span data-ttu-id="36494-3275">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="36494-3275">code SWIFT</span></span> 
- <span data-ttu-id="36494-3276">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="36494-3276">le numéro de swift</span></span> 
- <span data-ttu-id="36494-3277">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="36494-3277">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="36494-3278">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="36494-3278">le numéro BIC</span></span> 
- <span data-ttu-id="36494-3279">\#БИК</span><span class="sxs-lookup"><span data-stu-id="36494-3279">\# BIC</span></span> 
- <span data-ttu-id="36494-3280">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="36494-3280">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="36494-3281">Национальный идентификатор, Тайвань</span><span class="sxs-lookup"><span data-stu-id="36494-3281">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="36494-3282">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3282">Format</span></span>

<span data-ttu-id="36494-3283">Одна буква (английская), за которой следуют девять цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3283">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3284">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3284">Pattern</span></span>

<span data-ttu-id="36494-3285">Один символ , за которым следуют девять цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3285">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="36494-3286">Один символ (на английском языке, без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="36494-3286">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="36494-3287">Цифра 1 или 2</span><span class="sxs-lookup"><span data-stu-id="36494-3287">The digit "1" or "2"</span></span> 
- <span data-ttu-id="36494-3288">Восемь цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3288">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3289">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3289">Checksum</span></span>

<span data-ttu-id="36494-3290">Да</span><span class="sxs-lookup"><span data-stu-id="36494-3290">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3291">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3291">Definition</span></span>

<span data-ttu-id="36494-3292">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3292">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3293">функция Func_taiwanese_national_id находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3293">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3294">находится ключевое слово из Keyword_taiwanese_national_id;</span><span class="sxs-lookup"><span data-stu-id="36494-3294">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="36494-3295">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-3295">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3296">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3296">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="36494-3297">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="36494-3297">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="36494-3298">身份證字號</span><span class="sxs-lookup"><span data-stu-id="36494-3298">身份證字號</span></span> 
- <span data-ttu-id="36494-3299">身份證</span><span class="sxs-lookup"><span data-stu-id="36494-3299">身份證</span></span> 
- <span data-ttu-id="36494-3300">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="36494-3300">身份證號碼</span></span> 
- <span data-ttu-id="36494-3301">身份證號</span><span class="sxs-lookup"><span data-stu-id="36494-3301">身份證號</span></span> 
- <span data-ttu-id="36494-3302">身分證字號</span><span class="sxs-lookup"><span data-stu-id="36494-3302">身分證字號</span></span> 
- <span data-ttu-id="36494-3303">身分證</span><span class="sxs-lookup"><span data-stu-id="36494-3303">身分證</span></span> 
- <span data-ttu-id="36494-3304">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="36494-3304">身分證號碼</span></span> 
- <span data-ttu-id="36494-3305">身份證號</span><span class="sxs-lookup"><span data-stu-id="36494-3305">身份證號</span></span> 
- <span data-ttu-id="36494-3306">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="36494-3306">身分證統一編號</span></span> 
- <span data-ttu-id="36494-3307">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="36494-3307">國民身分證統一編號</span></span> 
- <span data-ttu-id="36494-3308">簽名</span><span class="sxs-lookup"><span data-stu-id="36494-3308">簽名</span></span> 
- <span data-ttu-id="36494-3309">蓋章</span><span class="sxs-lookup"><span data-stu-id="36494-3309">蓋章</span></span> 
- <span data-ttu-id="36494-3310">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="36494-3310">簽名或蓋章</span></span> 
- <span data-ttu-id="36494-3311">簽章</span><span class="sxs-lookup"><span data-stu-id="36494-3311">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="36494-3312">	Номер паспорта гражданина Тайваня</span><span class="sxs-lookup"><span data-stu-id="36494-3312">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3313">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3313">Format</span></span>

- <span data-ttu-id="36494-3314">Номер биометрического паспорта: девять цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3314">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="36494-3315">Номер биометрической службы Passport: девять цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3315">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3316">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3316">Pattern</span></span>
<span data-ttu-id="36494-3317">Номер биометрического паспорта:</span><span class="sxs-lookup"><span data-stu-id="36494-3317">Biometric passport number:</span></span>
- <span data-ttu-id="36494-3318">цифра "3";</span><span class="sxs-lookup"><span data-stu-id="36494-3318">The digit "3"</span></span> 
- <span data-ttu-id="36494-3319">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3319">Eight digits</span></span>

<span data-ttu-id="36494-3320">Номер биометрической службы Passport:</span><span class="sxs-lookup"><span data-stu-id="36494-3320">Non-biometric passport number:</span></span>
- <span data-ttu-id="36494-3321">девять цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3321">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3322">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3322">Checksum</span></span>

<span data-ttu-id="36494-3323">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3323">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3324">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3324">Definition</span></span>

<span data-ttu-id="36494-3325">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3325">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3326">регулярное выражение Regex_taiwan_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3326">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3327">находится ключевое слово из Keyword_taiwan_passport.</span><span class="sxs-lookup"><span data-stu-id="36494-3327">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3328">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3328">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="36494-3329">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="36494-3329">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="36494-3330">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="36494-3330">ROC passport number</span></span> 
- <span data-ttu-id="36494-3331">Passport number</span><span class="sxs-lookup"><span data-stu-id="36494-3331">Passport number</span></span> 
- <span data-ttu-id="36494-3332">Passport no</span><span class="sxs-lookup"><span data-stu-id="36494-3332">Passport no</span></span> 
- <span data-ttu-id="36494-3333">Passport Num</span><span class="sxs-lookup"><span data-stu-id="36494-3333">Passport Num</span></span> 
- <span data-ttu-id="36494-3334">Passport #</span><span class="sxs-lookup"><span data-stu-id="36494-3334">Passport #</span></span> 
- <span data-ttu-id="36494-3335">护照</span><span class="sxs-lookup"><span data-stu-id="36494-3335">护照</span></span> 
- <span data-ttu-id="36494-3336">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="36494-3336">中華民國護照</span></span> 
- <span data-ttu-id="36494-3337">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="36494-3337">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="36494-3338">Номер удостоверения жителя Тайваня (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="36494-3338">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3339">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3339">Format</span></span>

<span data-ttu-id="36494-3340">10 букв и цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3340">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3341">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3341">Pattern</span></span>

<span data-ttu-id="36494-3342">10 букв и цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-3342">10 letters and digits:</span></span>
- <span data-ttu-id="36494-3343">две буквы (без учета регистра);</span><span class="sxs-lookup"><span data-stu-id="36494-3343">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="36494-3344">восемь цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3344">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3345">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3345">Checksum</span></span>

<span data-ttu-id="36494-3346">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3346">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3347">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3347">Definition</span></span>

<span data-ttu-id="36494-3348">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3349">регулярное выражение Regex_taiwan_resident_certificate находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3349">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3350">находится ключевое слово из Keyword_taiwan_resident_certificate.</span><span class="sxs-lookup"><span data-stu-id="36494-3350">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3351">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3351">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="36494-3352">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="36494-3352">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="36494-3353">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="36494-3353">Resident Certificate</span></span> 
- <span data-ttu-id="36494-3354">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="36494-3354">Resident Cert</span></span> 
- <span data-ttu-id="36494-3355">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="36494-3355">Resident Cert.</span></span> 
- <span data-ttu-id="36494-3356">Identification card</span><span class="sxs-lookup"><span data-stu-id="36494-3356">Identification card</span></span> 
- <span data-ttu-id="36494-3357">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="36494-3357">Alien Resident Certificate</span></span> 
- <span data-ttu-id="36494-3358">ГИПЕРБОЛ</span><span class="sxs-lookup"><span data-stu-id="36494-3358">ARC</span></span> 
- <span data-ttu-id="36494-3359">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="36494-3359">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="36494-3360">TARC</span><span class="sxs-lookup"><span data-stu-id="36494-3360">TARC</span></span> 
- <span data-ttu-id="36494-3361">居留證</span><span class="sxs-lookup"><span data-stu-id="36494-3361">居留證</span></span> 
- <span data-ttu-id="36494-3362">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="36494-3362">外僑居留證</span></span> 
- <span data-ttu-id="36494-3363">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="36494-3363">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="36494-3364">Код идентификации для тайского заполнения</span><span class="sxs-lookup"><span data-stu-id="36494-3364">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="36494-3365">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3365">Format</span></span>

<span data-ttu-id="36494-3366">13 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3366">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3367">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3367">Pattern</span></span>

<span data-ttu-id="36494-3368">13 цифр:</span><span class="sxs-lookup"><span data-stu-id="36494-3368">13 digits:</span></span>
- <span data-ttu-id="36494-3369">Первая цифра не равна 0 или 9</span><span class="sxs-lookup"><span data-stu-id="36494-3369">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="36494-3370">12 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3370">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3371">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3371">Checksum</span></span>

<span data-ttu-id="36494-3372">Да</span><span class="sxs-lookup"><span data-stu-id="36494-3372">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3373">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3373">Definition</span></span>

<span data-ttu-id="36494-3374">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3374">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3375">Функция Func_Thai_Citizen_Id обнаружила содержимое, соответствующее шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3375">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3376">Найдено ключевое слово из Keyword_Thai_Citizen_Id.</span><span class="sxs-lookup"><span data-stu-id="36494-3376">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="36494-3377">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3378">Функция Func_Thai_Citizen_Id обнаружила содержимое, соответствующее шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3378">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3379">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3379">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="36494-3380">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="36494-3380">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="36494-3381">ID Number</span><span class="sxs-lookup"><span data-stu-id="36494-3381">ID Number</span></span>
- <span data-ttu-id="36494-3382">Идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="36494-3382">Identification Number</span></span>
- <span data-ttu-id="36494-3383">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="36494-3383">บัตรประชาชน</span></span>
- <span data-ttu-id="36494-3384">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="36494-3384">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="36494-3385">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="36494-3385">บัตรประชาชน</span></span>
- <span data-ttu-id="36494-3386">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="36494-3386">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="36494-3387">Турецкий национальный идентификационный номер</span><span class="sxs-lookup"><span data-stu-id="36494-3387">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3388">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3388">Format</span></span>

<span data-ttu-id="36494-3389">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3389">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3390">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3390">Pattern</span></span>

<span data-ttu-id="36494-3391">11 цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3391">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3392">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3392">Checksum</span></span>

<span data-ttu-id="36494-3393">Да</span><span class="sxs-lookup"><span data-stu-id="36494-3393">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3394">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3394">Definition</span></span>

<span data-ttu-id="36494-3395">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3395">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3396">Функция Func_Turkish_National_Id обнаружила содержимое, соответствующее шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3396">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3397">Найдено ключевое слово из Keyword_Turkish_National_Id.</span><span class="sxs-lookup"><span data-stu-id="36494-3397">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="36494-3398">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3398">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3399">Функция Func_Turkish_National_Id обнаружила содержимое, соответствующее шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3399">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3400">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3400">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="36494-3401">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="36494-3401">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="36494-3402">TC Кимлик No</span><span class="sxs-lookup"><span data-stu-id="36494-3402">TC Kimlik No</span></span>
- <span data-ttu-id="36494-3403">TC Кимлик нумарасı</span><span class="sxs-lookup"><span data-stu-id="36494-3403">TC Kimlik numarası</span></span>
- <span data-ttu-id="36494-3404">Ватандаşлıк нумарасı</span><span class="sxs-lookup"><span data-stu-id="36494-3404">Vatandaşlık numarası</span></span>
- <span data-ttu-id="36494-3405">Ватандаşлıк нет</span><span class="sxs-lookup"><span data-stu-id="36494-3405">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="36494-p144">Номер водительского удостоверения для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="36494-p144">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3408">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3408">Format</span></span>

<span data-ttu-id="36494-3409">Сочетание 18 букв и цифр в указанном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-3409">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3410">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3410">Pattern</span></span>

<span data-ttu-id="36494-3411">18 букв и цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3411">18 letters and digits:</span></span>
- <span data-ttu-id="36494-3412">Пять букв (без учета регистра) или цифра 9 вместо буквы</span><span class="sxs-lookup"><span data-stu-id="36494-3412">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="36494-3413">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="36494-3413">One digit</span></span> 
- <span data-ttu-id="36494-3414">Пять цифр в формате даты ДДММГ, представляющие собой дату рождения</span><span class="sxs-lookup"><span data-stu-id="36494-3414">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="36494-3415">Две буквы (без учета регистра) или цифра 9 вместо буквы</span><span class="sxs-lookup"><span data-stu-id="36494-3415">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="36494-3416">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3416">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3417">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3417">Checksum</span></span>

<span data-ttu-id="36494-3418">Да</span><span class="sxs-lookup"><span data-stu-id="36494-3418">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3419">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3419">Definition</span></span>

<span data-ttu-id="36494-3420">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3421">функция Func_uk_drivers_license находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3421">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3422">находится ключевое слово из Keyword_uk_drivers_license;</span><span class="sxs-lookup"><span data-stu-id="36494-3422">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="36494-3423">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-3423">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3424">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3424">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="36494-3425">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="36494-3425">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="36494-3426">двла</span><span class="sxs-lookup"><span data-stu-id="36494-3426">DVLA</span></span> 
- <span data-ttu-id="36494-3427">light vans</span><span class="sxs-lookup"><span data-stu-id="36494-3427">light vans</span></span> 
- <span data-ttu-id="36494-3428">куадбикес</span><span class="sxs-lookup"><span data-stu-id="36494-3428">quadbikes</span></span> 
- <span data-ttu-id="36494-3429">motor cars</span><span class="sxs-lookup"><span data-stu-id="36494-3429">motor cars</span></span> 
- <span data-ttu-id="36494-3430">125cc</span><span class="sxs-lookup"><span data-stu-id="36494-3430">125cc</span></span> 
- <span data-ttu-id="36494-3431">сидекар</span><span class="sxs-lookup"><span data-stu-id="36494-3431">sidecar</span></span> 
- <span data-ttu-id="36494-3432">трициклес</span><span class="sxs-lookup"><span data-stu-id="36494-3432">tricycles</span></span> 
- <span data-ttu-id="36494-3433">моторциклес</span><span class="sxs-lookup"><span data-stu-id="36494-3433">motorcycles</span></span> 
- <span data-ttu-id="36494-3434">photocard licence</span><span class="sxs-lookup"><span data-stu-id="36494-3434">photocard licence</span></span> 
- <span data-ttu-id="36494-3435">learner drivers</span><span class="sxs-lookup"><span data-stu-id="36494-3435">learner drivers</span></span> 
- <span data-ttu-id="36494-3436">licence holder</span><span class="sxs-lookup"><span data-stu-id="36494-3436">licence holder</span></span> 
- <span data-ttu-id="36494-3437">licence holders</span><span class="sxs-lookup"><span data-stu-id="36494-3437">licence holders</span></span> 
- <span data-ttu-id="36494-3438">driving licences</span><span class="sxs-lookup"><span data-stu-id="36494-3438">driving licences</span></span> 
- <span data-ttu-id="36494-3439">driving licence</span><span class="sxs-lookup"><span data-stu-id="36494-3439">driving licence</span></span> 
- <span data-ttu-id="36494-3440">dual control car</span><span class="sxs-lookup"><span data-stu-id="36494-3440">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="36494-p145">Регистрационный номер избирателя для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="36494-p145">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3443">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3443">Format</span></span>

<span data-ttu-id="36494-3444">Две буквы, за которыми следуют 1–4 цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-3444">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3445">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3445">Pattern</span></span>

<span data-ttu-id="36494-3446">Две буквы (без учета регистра), за которыми следуют 1–4 цифры.</span><span class="sxs-lookup"><span data-stu-id="36494-3446">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3447">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3447">Checksum</span></span>

<span data-ttu-id="36494-3448">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3448">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3449">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3449">Definition</span></span>

<span data-ttu-id="36494-3450">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3450">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3451">регулярное выражение Regex_uk_electoral находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3451">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3452">находится ключевое слово из Keyword_uk_electoral.</span><span class="sxs-lookup"><span data-stu-id="36494-3452">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3453">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3453">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="36494-3454">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="36494-3454">Keyword_uk_electoral</span></span>

- <span data-ttu-id="36494-3455">council nomination</span><span class="sxs-lookup"><span data-stu-id="36494-3455">council nomination</span></span> 
- <span data-ttu-id="36494-3456">nomination form</span><span class="sxs-lookup"><span data-stu-id="36494-3456">nomination form</span></span> 
- <span data-ttu-id="36494-3457">electoral register</span><span class="sxs-lookup"><span data-stu-id="36494-3457">electoral register</span></span> 
- <span data-ttu-id="36494-3458">electoral roll</span><span class="sxs-lookup"><span data-stu-id="36494-3458">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="36494-p146">Номер национальной службы здравоохранения для Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="36494-p146">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3461">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3461">Format</span></span>

<span data-ttu-id="36494-3462">10–17 цифр, разделенных пробелами.</span><span class="sxs-lookup"><span data-stu-id="36494-3462">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3463">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3463">Pattern</span></span>

<span data-ttu-id="36494-3464">10-17 цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3464">10-17 digits:</span></span>
- <span data-ttu-id="36494-3465">3 или 10 цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3465">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="36494-3466">Пробел</span><span class="sxs-lookup"><span data-stu-id="36494-3466">A space</span></span> 
- <span data-ttu-id="36494-3467">Три цифры</span><span class="sxs-lookup"><span data-stu-id="36494-3467">Three digits</span></span> 
- <span data-ttu-id="36494-3468">Пробел</span><span class="sxs-lookup"><span data-stu-id="36494-3468">A space</span></span> 
- <span data-ttu-id="36494-3469">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="36494-3469">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3470">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3470">Checksum</span></span>

<span data-ttu-id="36494-3471">Да</span><span class="sxs-lookup"><span data-stu-id="36494-3471">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3472">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3472">Definition</span></span>

<span data-ttu-id="36494-3473">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3474">Функция Func_uk_nhs_number находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3474">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3475">Верно одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="36494-3475">One of the following is true:</span></span>
    - <span data-ttu-id="36494-3476">найдено ключевое слово из Keyword_uk_nhs_number;</span><span class="sxs-lookup"><span data-stu-id="36494-3476">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="36494-3477">найдено ключевое слово из Keyword_uk_nhs_number1;</span><span class="sxs-lookup"><span data-stu-id="36494-3477">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="36494-3478">найдено ключевое слово из Keyword_uk_nhs_number_dob.</span><span class="sxs-lookup"><span data-stu-id="36494-3478">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="36494-3479">Контрольная сумма проходит проверку.</span><span class="sxs-lookup"><span data-stu-id="36494-3479">The checksum passes.</span></span>

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3480">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3480">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="36494-3481">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="36494-3481">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="36494-3482">national health service</span><span class="sxs-lookup"><span data-stu-id="36494-3482">national health service</span></span> 
- <span data-ttu-id="36494-3483">NHS</span><span class="sxs-lookup"><span data-stu-id="36494-3483">nhs</span></span> 
- <span data-ttu-id="36494-3484">health services authority</span><span class="sxs-lookup"><span data-stu-id="36494-3484">health services authority</span></span> 
- <span data-ttu-id="36494-3485">health authority</span><span class="sxs-lookup"><span data-stu-id="36494-3485">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="36494-3486">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="36494-3486">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="36494-3487">patient id</span><span class="sxs-lookup"><span data-stu-id="36494-3487">patient id</span></span> 
- <span data-ttu-id="36494-3488">patient identification</span><span class="sxs-lookup"><span data-stu-id="36494-3488">patient identification</span></span> 
- <span data-ttu-id="36494-3489">patient no</span><span class="sxs-lookup"><span data-stu-id="36494-3489">patient no</span></span> 
- <span data-ttu-id="36494-3490">patient number</span><span class="sxs-lookup"><span data-stu-id="36494-3490">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="36494-3491">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="36494-3491">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="36494-3492">ГРУПП</span><span class="sxs-lookup"><span data-stu-id="36494-3492">GP</span></span> 
- <span data-ttu-id="36494-3493">доб</span><span class="sxs-lookup"><span data-stu-id="36494-3493">DOB</span></span> 
- <span data-ttu-id="36494-3494">D. O. B</span><span class="sxs-lookup"><span data-stu-id="36494-3494">D.O.B</span></span> 
- <span data-ttu-id="36494-3495">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="36494-3495">Date of Birth</span></span> 
- <span data-ttu-id="36494-3496">Birth Date</span><span class="sxs-lookup"><span data-stu-id="36494-3496">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="36494-p147">Номер карты национального страхования для Соединенного Королевства (NINO)</span><span class="sxs-lookup"><span data-stu-id="36494-p147">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="36494-3499">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3499">Format</span></span>

<span data-ttu-id="36494-3500">7 символов или 9 символов, разделенных пробелами или тире</span><span class="sxs-lookup"><span data-stu-id="36494-3500">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3501">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3501">Pattern</span></span>

<span data-ttu-id="36494-3502">Два возможных шаблона:</span><span class="sxs-lookup"><span data-stu-id="36494-3502">Two possible patterns:</span></span>

- <span data-ttu-id="36494-3503">Две буквы (допустимые Нинос используют только определенные символы в этом префиксе, которые пропускаются при проверке этого шаблона; без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="36494-3503">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="36494-3504">Шесть цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3504">Six digits</span></span>
- <span data-ttu-id="36494-3505">"A", "B", "C", или "'D" (например, префикс, в суффиксе допускаются только определенные символы; без учета регистра)</span><span class="sxs-lookup"><span data-stu-id="36494-3505">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="36494-3506">OR</span><span class="sxs-lookup"><span data-stu-id="36494-3506">OR</span></span>

- <span data-ttu-id="36494-3507">Две буквы</span><span class="sxs-lookup"><span data-stu-id="36494-3507">Two letters</span></span>
- <span data-ttu-id="36494-3508">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="36494-3508">A space or dash</span></span>
- <span data-ttu-id="36494-3509">Две цифры</span><span class="sxs-lookup"><span data-stu-id="36494-3509">Two digits</span></span>
- <span data-ttu-id="36494-3510">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="36494-3510">A space or dash</span></span>
- <span data-ttu-id="36494-3511">Две цифры</span><span class="sxs-lookup"><span data-stu-id="36494-3511">Two digits</span></span>
- <span data-ttu-id="36494-3512">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="36494-3512">A space or dash</span></span>
- <span data-ttu-id="36494-3513">Две цифры</span><span class="sxs-lookup"><span data-stu-id="36494-3513">Two digits</span></span>
- <span data-ttu-id="36494-3514">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="36494-3514">A space or dash</span></span>
- <span data-ttu-id="36494-3515">Значение "A", "B", "C" или "'D"</span><span class="sxs-lookup"><span data-stu-id="36494-3515">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3516">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3516">Checksum</span></span>

<span data-ttu-id="36494-3517">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3517">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3518">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3518">Definition</span></span>

<span data-ttu-id="36494-3519">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3520">функция Func_uk_nino находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3520">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3521">находится ключевое слово из Keyword_uk_nino.</span><span class="sxs-lookup"><span data-stu-id="36494-3521">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="36494-3522">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3523">функция Func_uk_nino находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3523">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3524">ни одно ключевое слово из Keyword_uk_nino не находится.</span><span class="sxs-lookup"><span data-stu-id="36494-3524">No keyword from Keyword_uk_nino is found.</span></span>

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3525">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3525">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="36494-3526">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="36494-3526">Keyword_uk_nino</span></span>

- <span data-ttu-id="36494-3527">national insurance number</span><span class="sxs-lookup"><span data-stu-id="36494-3527">national insurance number</span></span> 
- <span data-ttu-id="36494-3528">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="36494-3528">national insurance contributions</span></span> 
- <span data-ttu-id="36494-3529">protection act</span><span class="sxs-lookup"><span data-stu-id="36494-3529">protection act</span></span> 
- <span data-ttu-id="36494-3530">страхования</span><span class="sxs-lookup"><span data-stu-id="36494-3530">insurance</span></span> 
- <span data-ttu-id="36494-3531">social security number</span><span class="sxs-lookup"><span data-stu-id="36494-3531">social security number</span></span> 
- <span data-ttu-id="36494-3532">insurance application</span><span class="sxs-lookup"><span data-stu-id="36494-3532">insurance application</span></span> 
- <span data-ttu-id="36494-3533">medical application</span><span class="sxs-lookup"><span data-stu-id="36494-3533">medical application</span></span> 
- <span data-ttu-id="36494-3534">social insurance</span><span class="sxs-lookup"><span data-stu-id="36494-3534">social insurance</span></span> 
- <span data-ttu-id="36494-3535">medical attention</span><span class="sxs-lookup"><span data-stu-id="36494-3535">medical attention</span></span> 
- <span data-ttu-id="36494-3536">social security</span><span class="sxs-lookup"><span data-stu-id="36494-3536">social security</span></span> 
- <span data-ttu-id="36494-3537">great britain</span><span class="sxs-lookup"><span data-stu-id="36494-3537">great britain</span></span> 
- <span data-ttu-id="36494-3538">страхования</span><span class="sxs-lookup"><span data-stu-id="36494-3538">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="36494-p148">Номер паспорта гражданина США и/или Соединенного Королевства</span><span class="sxs-lookup"><span data-stu-id="36494-p148">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3541">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3541">Format</span></span>

<span data-ttu-id="36494-3542">Девять цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3542">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3543">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3543">Pattern</span></span>

<span data-ttu-id="36494-3544">Девять последовательных цифр.</span><span class="sxs-lookup"><span data-stu-id="36494-3544">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3545">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3545">Checksum</span></span>

<span data-ttu-id="36494-3546">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3546">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3547">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3547">Definition</span></span>

<span data-ttu-id="36494-3548">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3549">функция Func_usa_uk_passport находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3549">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3550">находится ключевое слово из Keyword_passport.</span><span class="sxs-lookup"><span data-stu-id="36494-3550">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3551">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3551">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="36494-3552">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="36494-3552">Keyword_passport</span></span>

- <span data-ttu-id="36494-3553">Passport Number</span><span class="sxs-lookup"><span data-stu-id="36494-3553">Passport Number</span></span> 
- <span data-ttu-id="36494-3554">Passport No</span><span class="sxs-lookup"><span data-stu-id="36494-3554">Passport No</span></span> 
- <span data-ttu-id="36494-3555">Passport#</span><span class="sxs-lookup"><span data-stu-id="36494-3555">Passport #</span></span> 
- <span data-ttu-id="36494-3556">Службу #</span><span class="sxs-lookup"><span data-stu-id="36494-3556">Passport#</span></span> 
- <span data-ttu-id="36494-3557">пасспортид</span><span class="sxs-lookup"><span data-stu-id="36494-3557">PassportID</span></span> 
- <span data-ttu-id="36494-3558">пасспортно</span><span class="sxs-lookup"><span data-stu-id="36494-3558">Passportno</span></span> 
- <span data-ttu-id="36494-3559">пасспортнумбер</span><span class="sxs-lookup"><span data-stu-id="36494-3559">passportnumber</span></span> 
- <span data-ttu-id="36494-3560">パスポート</span><span class="sxs-lookup"><span data-stu-id="36494-3560">パスポート</span></span> 
- <span data-ttu-id="36494-3561">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="36494-3561">パスポート番号</span></span> 
- <span data-ttu-id="36494-3562">パスポートのнум</span><span class="sxs-lookup"><span data-stu-id="36494-3562">パスポートのNum</span></span> 
- <span data-ttu-id="36494-3563">パスポート #</span><span class="sxs-lookup"><span data-stu-id="36494-3563">パスポート＃</span></span> 
- <span data-ttu-id="36494-3564">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="36494-3564">Numéro de passeport</span></span> 
- <span data-ttu-id="36494-3565">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="36494-3565">Passeport n °</span></span> 
- <span data-ttu-id="36494-3566">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="36494-3566">Passeport Non</span></span> 
- <span data-ttu-id="36494-3567">Passeport#</span><span class="sxs-lookup"><span data-stu-id="36494-3567">Passeport #</span></span> 
- <span data-ttu-id="36494-3568">пассепорт #</span><span class="sxs-lookup"><span data-stu-id="36494-3568">Passeport#</span></span> 
- <span data-ttu-id="36494-3569">пассепортнон</span><span class="sxs-lookup"><span data-stu-id="36494-3569">PasseportNon</span></span> 
- <span data-ttu-id="36494-3570">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="36494-3570">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="36494-3571">Номер банковского счета для США</span><span class="sxs-lookup"><span data-stu-id="36494-3571">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3572">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3572">Format</span></span>

<span data-ttu-id="36494-3573">8-17 цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3573">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3574">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3574">Pattern</span></span>

<span data-ttu-id="36494-3575">8–17 последовательных цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3575">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3576">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3576">Checksum</span></span>

<span data-ttu-id="36494-3577">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3577">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3578">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3578">Definition</span></span>

<span data-ttu-id="36494-3579">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3579">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3580">регулярное выражение Regex_usa_bank_account_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3580">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3581">находится ключевое слово из Keyword_usa_Bank_Account.</span><span class="sxs-lookup"><span data-stu-id="36494-3581">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3582">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3582">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="36494-3583">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="36494-3583">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="36494-3584">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="36494-3584">Checking Account Number</span></span> 
- <span data-ttu-id="36494-3585">Checking Account</span><span class="sxs-lookup"><span data-stu-id="36494-3585">Checking Account</span></span> 
- <span data-ttu-id="36494-3586">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="36494-3586">Checking Account #</span></span> 
- <span data-ttu-id="36494-3587">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="36494-3587">Checking Acct Number</span></span> 
- <span data-ttu-id="36494-3588">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="36494-3588">Checking Acct #</span></span> 
- <span data-ttu-id="36494-3589">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="36494-3589">Checking Acct No.</span></span> 
- <span data-ttu-id="36494-3590">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="36494-3590">Checking Account No.</span></span> 
- <span data-ttu-id="36494-3591">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="36494-3591">Bank Account Number</span></span> 
- <span data-ttu-id="36494-3592">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="36494-3592">Bank Account #</span></span> 
- <span data-ttu-id="36494-3593">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="36494-3593">Bank Acct Number</span></span> 
- <span data-ttu-id="36494-3594">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="36494-3594">Bank Acct #</span></span> 
- <span data-ttu-id="36494-3595">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="36494-3595">Bank Acct No.</span></span> 
- <span data-ttu-id="36494-3596">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="36494-3596">Bank Account No.</span></span> 
- <span data-ttu-id="36494-3597">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="36494-3597">Savings Account Number</span></span> 
- <span data-ttu-id="36494-3598">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="36494-3598">Savings Account.</span></span> 
- <span data-ttu-id="36494-3599">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="36494-3599">Savings Account #</span></span> 
- <span data-ttu-id="36494-3600">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="36494-3600">Savings Acct Number</span></span> 
- <span data-ttu-id="36494-3601">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="36494-3601">Savings Acct #</span></span> 
- <span data-ttu-id="36494-3602">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="36494-3602">Savings Acct No.</span></span> 
- <span data-ttu-id="36494-3603">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="36494-3603">Savings Account No.</span></span> 
- <span data-ttu-id="36494-3604">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="36494-3604">Debit Account Number</span></span> 
- <span data-ttu-id="36494-3605">Debit Account</span><span class="sxs-lookup"><span data-stu-id="36494-3605">Debit Account</span></span> 
- <span data-ttu-id="36494-3606">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="36494-3606">Debit Account #</span></span> 
- <span data-ttu-id="36494-3607">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="36494-3607">Debit Acct Number</span></span> 
- <span data-ttu-id="36494-3608">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="36494-3608">Debit Acct #</span></span> 
- <span data-ttu-id="36494-3609">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="36494-3609">Debit Acct No.</span></span> 
- <span data-ttu-id="36494-3610">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="36494-3610">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="36494-3611">Номер водительского удостоверения для США</span><span class="sxs-lookup"><span data-stu-id="36494-3611">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="36494-3612">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3612">Format</span></span>

<span data-ttu-id="36494-3613">Зависит от штата.</span><span class="sxs-lookup"><span data-stu-id="36494-3613">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3614">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3614">Pattern</span></span>

<span data-ttu-id="36494-3615">В зависимости от штата. Например, для Нью-Йорка:</span><span class="sxs-lookup"><span data-stu-id="36494-3615">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="36494-3616">Девять цифр, отформатированных как DDD DDD DDD, будут совпадают.</span><span class="sxs-lookup"><span data-stu-id="36494-3616">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="36494-3617">Не подойдут девять цифр в формате ццццццццц.</span><span class="sxs-lookup"><span data-stu-id="36494-3617">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3618">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3618">Checksum</span></span>

<span data-ttu-id="36494-3619">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3619">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3620">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3620">Definition</span></span>

<span data-ttu-id="36494-3621">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3621">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3622">функция Func_new_york_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3622">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3623">находится ключевое слово из Keyword_[state_name]_drivers_license_name;</span><span class="sxs-lookup"><span data-stu-id="36494-3623">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="36494-3624">обнаружено ключевое слово из списка Keyword_us_drivers_license.</span><span class="sxs-lookup"><span data-stu-id="36494-3624">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="36494-3625">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3626">функция Func_new_york_drivers_license_number находит содержимое, которое соответствует шаблону;</span><span class="sxs-lookup"><span data-stu-id="36494-3626">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3627">находится ключевое слово из Keyword_[state_name]_drivers_license_name;</span><span class="sxs-lookup"><span data-stu-id="36494-3627">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="36494-3628">находится ключевое слово из Keyword_us_drivers_license_abbreviations.</span><span class="sxs-lookup"><span data-stu-id="36494-3628">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="36494-3629">ни одно ключевое слово из Keyword_us_drivers_license не находится.</span><span class="sxs-lookup"><span data-stu-id="36494-3629">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
```

### <a name="keywords"></a><span data-ttu-id="36494-3630">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3630">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="36494-3631">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="36494-3631">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="36494-3632">DL</span><span class="sxs-lookup"><span data-stu-id="36494-3632">DL</span></span> 
- <span data-ttu-id="36494-3633">БИБЛИОТЕК</span><span class="sxs-lookup"><span data-stu-id="36494-3633">DLS</span></span> 
- <span data-ttu-id="36494-3634">кдл</span><span class="sxs-lookup"><span data-stu-id="36494-3634">CDL</span></span> 
- <span data-ttu-id="36494-3635">кдлс</span><span class="sxs-lookup"><span data-stu-id="36494-3635">CDLS</span></span> 
- <span data-ttu-id="36494-3636">ID</span><span class="sxs-lookup"><span data-stu-id="36494-3636">ID</span></span> 
- <span data-ttu-id="36494-3637">Идентификаторы</span><span class="sxs-lookup"><span data-stu-id="36494-3637">IDs</span></span> 
- <span data-ttu-id="36494-3638">DL #</span><span class="sxs-lookup"><span data-stu-id="36494-3638">DL#</span></span> 
- <span data-ttu-id="36494-3639">БИБЛИОТЕК #</span><span class="sxs-lookup"><span data-stu-id="36494-3639">DLS#</span></span> 
- <span data-ttu-id="36494-3640">кдл #</span><span class="sxs-lookup"><span data-stu-id="36494-3640">CDL#</span></span> 
- <span data-ttu-id="36494-3641">кдлс #</span><span class="sxs-lookup"><span data-stu-id="36494-3641">CDLS#</span></span> 
- <span data-ttu-id="36494-3642">КОДОВ #</span><span class="sxs-lookup"><span data-stu-id="36494-3642">ID#</span></span>
- <span data-ttu-id="36494-3643">Идентификаторы #</span><span class="sxs-lookup"><span data-stu-id="36494-3643">IDs#</span></span> 
- <span data-ttu-id="36494-3644">ID number</span><span class="sxs-lookup"><span data-stu-id="36494-3644">ID number</span></span> 
- <span data-ttu-id="36494-3645">ID numbers</span><span class="sxs-lookup"><span data-stu-id="36494-3645">ID numbers</span></span> 
- <span data-ttu-id="36494-3646">лик</span><span class="sxs-lookup"><span data-stu-id="36494-3646">LIC</span></span> 
- <span data-ttu-id="36494-3647">лик #</span><span class="sxs-lookup"><span data-stu-id="36494-3647">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="36494-3648">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="36494-3648">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="36494-3649">дриверлик</span><span class="sxs-lookup"><span data-stu-id="36494-3649">DriverLic</span></span> 
- <span data-ttu-id="36494-3650">дриверликс</span><span class="sxs-lookup"><span data-stu-id="36494-3650">DriverLics</span></span> 
- <span data-ttu-id="36494-3651">дриверлиценсе</span><span class="sxs-lookup"><span data-stu-id="36494-3651">DriverLicense</span></span> 
- <span data-ttu-id="36494-3652">дриверлиценсес</span><span class="sxs-lookup"><span data-stu-id="36494-3652">DriverLicenses</span></span> 
- <span data-ttu-id="36494-3653">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="36494-3653">Driver Lic</span></span> 
- <span data-ttu-id="36494-3654">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="36494-3654">Driver Lics</span></span> 
- <span data-ttu-id="36494-3655">Driver License</span><span class="sxs-lookup"><span data-stu-id="36494-3655">Driver License</span></span> 
- <span data-ttu-id="36494-3656">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-3656">Driver Licenses</span></span> 
- <span data-ttu-id="36494-3657">дриверслик</span><span class="sxs-lookup"><span data-stu-id="36494-3657">DriversLic</span></span> 
- <span data-ttu-id="36494-3658">дриверсликс</span><span class="sxs-lookup"><span data-stu-id="36494-3658">DriversLics</span></span> 
- <span data-ttu-id="36494-3659">дриверслиценсе</span><span class="sxs-lookup"><span data-stu-id="36494-3659">DriversLicense</span></span> 
- <span data-ttu-id="36494-3660">дриверслиценсес</span><span class="sxs-lookup"><span data-stu-id="36494-3660">DriversLicenses</span></span> 
- <span data-ttu-id="36494-3661">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="36494-3661">Drivers Lic</span></span> 
- <span data-ttu-id="36494-3662">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="36494-3662">Drivers Lics</span></span> 
- <span data-ttu-id="36494-3663">Drivers License</span><span class="sxs-lookup"><span data-stu-id="36494-3663">Drivers License</span></span> 
- <span data-ttu-id="36494-3664">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-3664">Drivers Licenses</span></span> 
- <span data-ttu-id="36494-3665">Driver ' LIC</span><span class="sxs-lookup"><span data-stu-id="36494-3665">Driver'Lic</span></span> 
- <span data-ttu-id="36494-3666">Driver ' LICS</span><span class="sxs-lookup"><span data-stu-id="36494-3666">Driver'Lics</span></span> 
- <span data-ttu-id="36494-3667">Driver ' License</span><span class="sxs-lookup"><span data-stu-id="36494-3667">Driver'License</span></span> 
- <span data-ttu-id="36494-3668">Driver ' Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-3668">Driver'Licenses</span></span> 
- <span data-ttu-id="36494-3669">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="36494-3669">Driver' Lic</span></span> 
- <span data-ttu-id="36494-3670">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="36494-3670">Driver' Lics</span></span> 
- <span data-ttu-id="36494-3671">Driver' License</span><span class="sxs-lookup"><span data-stu-id="36494-3671">Driver' License</span></span> 
- <span data-ttu-id="36494-3672">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-3672">Driver' Licenses</span></span>
- <span data-ttu-id="36494-3673">дривер'слик</span><span class="sxs-lookup"><span data-stu-id="36494-3673">Driver'sLic</span></span> 
- <span data-ttu-id="36494-3674">дривер'сликс</span><span class="sxs-lookup"><span data-stu-id="36494-3674">Driver'sLics</span></span> 
- <span data-ttu-id="36494-3675">дривер'слиценсе</span><span class="sxs-lookup"><span data-stu-id="36494-3675">Driver'sLicense</span></span> 
- <span data-ttu-id="36494-3676">дривер'слиценсес</span><span class="sxs-lookup"><span data-stu-id="36494-3676">Driver'sLicenses</span></span> 
- <span data-ttu-id="36494-3677">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="36494-3677">Driver's Lic</span></span> 
- <span data-ttu-id="36494-3678">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="36494-3678">Driver's Lics</span></span> 
- <span data-ttu-id="36494-3679">Driver's License</span><span class="sxs-lookup"><span data-stu-id="36494-3679">Driver's License</span></span> 
- <span data-ttu-id="36494-3680">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="36494-3680">Driver's Licenses</span></span> 
- <span data-ttu-id="36494-3681">identification number</span><span class="sxs-lookup"><span data-stu-id="36494-3681">identification number</span></span> 
- <span data-ttu-id="36494-3682">identification numbers</span><span class="sxs-lookup"><span data-stu-id="36494-3682">identification numbers</span></span> 
- <span data-ttu-id="36494-3683">identification #</span><span class="sxs-lookup"><span data-stu-id="36494-3683">identification #</span></span> 
- <span data-ttu-id="36494-3684">id card</span><span class="sxs-lookup"><span data-stu-id="36494-3684">id card</span></span> 
- <span data-ttu-id="36494-3685">id cards</span><span class="sxs-lookup"><span data-stu-id="36494-3685">id cards</span></span> 
- <span data-ttu-id="36494-3686">identification card</span><span class="sxs-lookup"><span data-stu-id="36494-3686">identification card</span></span> 
- <span data-ttu-id="36494-3687">identification cards</span><span class="sxs-lookup"><span data-stu-id="36494-3687">identification cards</span></span> 
- <span data-ttu-id="36494-3688">дриверлик #</span><span class="sxs-lookup"><span data-stu-id="36494-3688">DriverLic#</span></span> 
- <span data-ttu-id="36494-3689">дриверликс #</span><span class="sxs-lookup"><span data-stu-id="36494-3689">DriverLics#</span></span> 
- <span data-ttu-id="36494-3690">дриверлиценсе #</span><span class="sxs-lookup"><span data-stu-id="36494-3690">DriverLicense#</span></span> 
- <span data-ttu-id="36494-3691">дриверлиценсес #</span><span class="sxs-lookup"><span data-stu-id="36494-3691">DriverLicenses#</span></span> 
- <span data-ttu-id="36494-3692">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="36494-3692">Driver Lic#</span></span> 
- <span data-ttu-id="36494-3693">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="36494-3693">Driver Lics#</span></span> 
- <span data-ttu-id="36494-3694">Driver License#</span><span class="sxs-lookup"><span data-stu-id="36494-3694">Driver License#</span></span> 
- <span data-ttu-id="36494-3695">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="36494-3695">Driver Licenses#</span></span> 
- <span data-ttu-id="36494-3696">дриверслик #</span><span class="sxs-lookup"><span data-stu-id="36494-3696">DriversLic#</span></span> 
- <span data-ttu-id="36494-3697">дриверсликс #</span><span class="sxs-lookup"><span data-stu-id="36494-3697">DriversLics#</span></span> 
- <span data-ttu-id="36494-3698">дриверслиценсе #</span><span class="sxs-lookup"><span data-stu-id="36494-3698">DriversLicense#</span></span> 
- <span data-ttu-id="36494-3699">дриверслиценсес #</span><span class="sxs-lookup"><span data-stu-id="36494-3699">DriversLicenses#</span></span> 
- <span data-ttu-id="36494-3700">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="36494-3700">Drivers Lic#</span></span> 
- <span data-ttu-id="36494-3701">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="36494-3701">Drivers Lics#</span></span> 
- <span data-ttu-id="36494-3702">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="36494-3702">Drivers License#</span></span> 
- <span data-ttu-id="36494-3703">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="36494-3703">Drivers Licenses#</span></span> 
- <span data-ttu-id="36494-3704">Driver ' LIC #</span><span class="sxs-lookup"><span data-stu-id="36494-3704">Driver'Lic#</span></span> 
- <span data-ttu-id="36494-3705">Driver ' LICS #</span><span class="sxs-lookup"><span data-stu-id="36494-3705">Driver'Lics#</span></span> 
- <span data-ttu-id="36494-3706">Driver ' License #</span><span class="sxs-lookup"><span data-stu-id="36494-3706">Driver'License#</span></span> 
- <span data-ttu-id="36494-3707">Driver ' Licenses #</span><span class="sxs-lookup"><span data-stu-id="36494-3707">Driver'Licenses#</span></span> 
- <span data-ttu-id="36494-3708">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="36494-3708">Driver' Lic#</span></span> 
- <span data-ttu-id="36494-3709">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="36494-3709">Driver' Lics#</span></span> 
- <span data-ttu-id="36494-3710">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="36494-3710">Driver' License#</span></span> 
- <span data-ttu-id="36494-3711">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="36494-3711">Driver' Licenses#</span></span> 
- <span data-ttu-id="36494-3712">дривер'слик #</span><span class="sxs-lookup"><span data-stu-id="36494-3712">Driver'sLic#</span></span> 
- <span data-ttu-id="36494-3713">дривер'сликс #</span><span class="sxs-lookup"><span data-stu-id="36494-3713">Driver'sLics#</span></span> 
- <span data-ttu-id="36494-3714">дривер'слиценсе #</span><span class="sxs-lookup"><span data-stu-id="36494-3714">Driver'sLicense#</span></span> 
- <span data-ttu-id="36494-3715">дривер'слиценсес #</span><span class="sxs-lookup"><span data-stu-id="36494-3715">Driver'sLicenses#</span></span> 
- <span data-ttu-id="36494-3716">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="36494-3716">Driver's Lic#</span></span> 
- <span data-ttu-id="36494-3717">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="36494-3717">Driver's Lics#</span></span> 
- <span data-ttu-id="36494-3718">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="36494-3718">Driver's License#</span></span> 
- <span data-ttu-id="36494-3719">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="36494-3719">Driver's Licenses#</span></span> 
- <span data-ttu-id="36494-3720">id card#</span><span class="sxs-lookup"><span data-stu-id="36494-3720">id card#</span></span> 
- <span data-ttu-id="36494-3721">id cards#</span><span class="sxs-lookup"><span data-stu-id="36494-3721">id cards#</span></span> 
- <span data-ttu-id="36494-3722">identification card#</span><span class="sxs-lookup"><span data-stu-id="36494-3722">identification card#</span></span> 
- <span data-ttu-id="36494-3723">identification cards#</span><span class="sxs-lookup"><span data-stu-id="36494-3723">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="36494-3724">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="36494-3724">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="36494-3725">Аббревиатура штата (например, NY)</span><span class="sxs-lookup"><span data-stu-id="36494-3725">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="36494-3726">Название штата (например, New York)</span><span class="sxs-lookup"><span data-stu-id="36494-3726">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="36494-3727">Идентификационный номер налогоплательщика для США (ITIN)</span><span class="sxs-lookup"><span data-stu-id="36494-3727">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="36494-3728">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3728">Format</span></span>

<span data-ttu-id="36494-3729">Девять цифр, которые начинаются с "9" и содержат "7" или "8" в качестве четвертой цифры, отформатированных с помощью пробелов или тире (необязательно).</span><span class="sxs-lookup"><span data-stu-id="36494-3729">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3730">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3730">Pattern</span></span>

<span data-ttu-id="36494-3731">Форматируемые</span><span class="sxs-lookup"><span data-stu-id="36494-3731">Formatted:</span></span>
- <span data-ttu-id="36494-3732">Цифра 9</span><span class="sxs-lookup"><span data-stu-id="36494-3732">The digit "9"</span></span> 
- <span data-ttu-id="36494-3733">Две цифры</span><span class="sxs-lookup"><span data-stu-id="36494-3733">Two digits</span></span> 
- <span data-ttu-id="36494-3734">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="36494-3734">A space or dash</span></span> 
- <span data-ttu-id="36494-3735">Цифра 7 или 8</span><span class="sxs-lookup"><span data-stu-id="36494-3735">A "7" or "8"</span></span> 
- <span data-ttu-id="36494-3736">Одна цифра</span><span class="sxs-lookup"><span data-stu-id="36494-3736">A digit</span></span> 
- <span data-ttu-id="36494-3737">Пробел или тире</span><span class="sxs-lookup"><span data-stu-id="36494-3737">A space, or dash</span></span> 
- <span data-ttu-id="36494-3738">Четыре цифры</span><span class="sxs-lookup"><span data-stu-id="36494-3738">Four digits</span></span>

<span data-ttu-id="36494-3739">Неформатированные</span><span class="sxs-lookup"><span data-stu-id="36494-3739">Unformatted:</span></span>
- <span data-ttu-id="36494-3740">Цифра 9</span><span class="sxs-lookup"><span data-stu-id="36494-3740">The digit "9"</span></span> 
- <span data-ttu-id="36494-3741">Две цифры</span><span class="sxs-lookup"><span data-stu-id="36494-3741">Two digits</span></span> 
- <span data-ttu-id="36494-3742">Цифра 7 или 8</span><span class="sxs-lookup"><span data-stu-id="36494-3742">A "7" or "8"</span></span> 
- <span data-ttu-id="36494-3743">Пять цифр</span><span class="sxs-lookup"><span data-stu-id="36494-3743">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3744">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3744">Checksum</span></span>

<span data-ttu-id="36494-3745">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3745">No</span></span>

### <a name="definition"></a><span data-ttu-id="36494-3746">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3746">Definition</span></span>

<span data-ttu-id="36494-3747">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3747">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3748">Функция Func_formatted_itin находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3748">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3749">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="36494-3749">At least one of the following is true:</span></span>
    - <span data-ttu-id="36494-3750">найдено ключевое слово из Keyword_itin;</span><span class="sxs-lookup"><span data-stu-id="36494-3750">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="36494-3751">функция Func_us_address находит адрес в правильном формате;</span><span class="sxs-lookup"><span data-stu-id="36494-3751">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="36494-3752">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-3752">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="36494-3753">найдено ключевое слово из Keyword_itin_collaborative.</span><span class="sxs-lookup"><span data-stu-id="36494-3753">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="36494-3754">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3755">Функция Func_unformatted_itin находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3755">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3756">Верно по меньшей мере одно из условий ниже:</span><span class="sxs-lookup"><span data-stu-id="36494-3756">At least one of the following is true:</span></span>
    - <span data-ttu-id="36494-3757">найдено ключевое слово из Keyword_itin_collaborative;</span><span class="sxs-lookup"><span data-stu-id="36494-3757">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="36494-3758">функция Func_us_address находит адрес в правильном формате;</span><span class="sxs-lookup"><span data-stu-id="36494-3758">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="36494-3759">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-3759">The function Func_us_date finds a date in the right date format.</span></span>

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3760">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3760">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="36494-3761">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="36494-3761">Keyword_itin</span></span>

- <span data-ttu-id="36494-3762">дубликат</span><span class="sxs-lookup"><span data-stu-id="36494-3762">taxpayer</span></span> 
- <span data-ttu-id="36494-3763">tax id</span><span class="sxs-lookup"><span data-stu-id="36494-3763">tax id</span></span> 
- <span data-ttu-id="36494-3764">tax identification</span><span class="sxs-lookup"><span data-stu-id="36494-3764">tax identification</span></span> 
- <span data-ttu-id="36494-3765">SharePointв</span><span class="sxs-lookup"><span data-stu-id="36494-3765">itin</span></span> 
- <span data-ttu-id="36494-3766">SSN</span><span class="sxs-lookup"><span data-stu-id="36494-3766">ssn</span></span> 
- <span data-ttu-id="36494-3767">ИНН</span><span class="sxs-lookup"><span data-stu-id="36494-3767">tin</span></span> 
- <span data-ttu-id="36494-3768">social security</span><span class="sxs-lookup"><span data-stu-id="36494-3768">social security</span></span> 
- <span data-ttu-id="36494-3769">tax payer</span><span class="sxs-lookup"><span data-stu-id="36494-3769">tax payer</span></span> 
- <span data-ttu-id="36494-3770">итинс</span><span class="sxs-lookup"><span data-stu-id="36494-3770">itins</span></span> 
- <span data-ttu-id="36494-3771">такси</span><span class="sxs-lookup"><span data-stu-id="36494-3771">taxid</span></span> 
- <span data-ttu-id="36494-3772">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="36494-3772">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="36494-3773">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="36494-3773">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="36494-3774">Лицензия</span><span class="sxs-lookup"><span data-stu-id="36494-3774">License</span></span> 
- <span data-ttu-id="36494-3775">DL</span><span class="sxs-lookup"><span data-stu-id="36494-3775">DL</span></span> 
- <span data-ttu-id="36494-3776">доб</span><span class="sxs-lookup"><span data-stu-id="36494-3776">DOB</span></span> 
- <span data-ttu-id="36494-3777">Birthdate</span><span class="sxs-lookup"><span data-stu-id="36494-3777">Birthdate</span></span> 
- <span data-ttu-id="36494-3778">День рождения </span><span class="sxs-lookup"><span data-stu-id="36494-3778">Birthday</span></span> 
- <span data-ttu-id="36494-3779">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="36494-3779">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="36494-3780">Страховой номер для США (SSN)</span><span class="sxs-lookup"><span data-stu-id="36494-3780">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="36494-3781">Format</span><span class="sxs-lookup"><span data-stu-id="36494-3781">Format</span></span>

<span data-ttu-id="36494-3782">9 цифр в виде форматированного или неформатированного шаблона.</span><span class="sxs-lookup"><span data-stu-id="36494-3782">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="36494-3783">Есть SSN выдан до середины 2011 г., он отличается строгим форматированием, при котором определенные части номера должны входить в указанные диапазоны (при этом нет контрольной суммы).</span><span class="sxs-lookup"><span data-stu-id="36494-3783">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="36494-3784">Шаблон</span><span class="sxs-lookup"><span data-stu-id="36494-3784">Pattern</span></span>

<span data-ttu-id="36494-3785">Четыре функции выполняют поиск SSN с использованием четырех разных шаблонов:</span><span class="sxs-lookup"><span data-stu-id="36494-3785">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="36494-3786">Func_ssn находит SSN со строгим форматированием с тире или пробелами, выданные до 2011 г. (ццц-цц-цццц ИЛИ ццц цц цццц);</span><span class="sxs-lookup"><span data-stu-id="36494-3786">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="36494-3787">Func_unformatted_ssn находит SSN со строгим форматированием, выданные до 2011 г. (без форматирования в виде девяти последовательных цифр — ццццццццц);</span><span class="sxs-lookup"><span data-stu-id="36494-3787">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="36494-3788">Func_randomized_formatted_ssn находит SSN с тире или пробелами, выданные после 2011 г. (ццц-цц-цццц ИЛИ ццц цц цццц);</span><span class="sxs-lookup"><span data-stu-id="36494-3788">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="36494-3789">Func_randomized_unformatted_ssn находит SSN без форматирования в виде девяти последовательных цифр, выданные после 2011 г. (ццццццццц).</span><span class="sxs-lookup"><span data-stu-id="36494-3789">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="36494-3790">Контрольная сумма</span><span class="sxs-lookup"><span data-stu-id="36494-3790">Checksum</span></span>

<span data-ttu-id="36494-3791">Нет</span><span class="sxs-lookup"><span data-stu-id="36494-3791">No</span></span>


### <a name="definition"></a><span data-ttu-id="36494-3792">Определение</span><span class="sxs-lookup"><span data-stu-id="36494-3792">Definition</span></span>

<span data-ttu-id="36494-3793">Политика защиты от потери данных с вероятностью в 85 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3794">Функция Func_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3794">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3795">Находится ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="36494-3795">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="36494-3796">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-3796">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="36494-3797">Функция Func_us_address находит адрес в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-3797">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="36494-3798">Политика защиты от потери данных с вероятностью в 75 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, не отдаленном более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3798">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3799">Функция Func_unformatted_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3799">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3800">Находится ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="36494-3800">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="36494-3801">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-3801">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="36494-3802">Функция Func_us_address находит адрес в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-3802">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="36494-3803">Политика защиты от потери данных с вероятностью в 65 % верно обнаруживает этот тип конфиденциальной информации, если в расположении, отдаленном не более чем на 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3803">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3804">Функция Func_randomized_formatted_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3804">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3805">Находится ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="36494-3805">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="36494-3806">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-3806">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="36494-3807">Функция Func_us_address находит адрес в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-3807">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="36494-3808">Политика защиты от потери данных с вероятностью в 55 % верно обнаружила этот тип конфиденциальной информации, если в пределах ближайших 300 знаков:</span><span class="sxs-lookup"><span data-stu-id="36494-3808">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3809">Функция Func_randomized_unformatted_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3809">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3810">Находится ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="36494-3810">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="36494-3811">функция Func_us_date находит дату в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-3811">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="36494-3812">Функция Func_us_address находит адрес в правильном формате.</span><span class="sxs-lookup"><span data-stu-id="36494-3812">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="36494-3813">Политика защиты от потери данных — 40% уверенности в том, что этот тип конфиденциальной информации обнаружен, если в пределах расстояния от 300 символов:</span><span class="sxs-lookup"><span data-stu-id="36494-3813">A DLP policy is 40% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="36494-3814">Функция Func_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3814">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3815">Функция Func_unformatted_ssn не находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3815">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3816">Функция Func_randomized_unformatted_ssn не находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3816">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3817">Не найдено ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="36494-3817">A keyword from Keyword_ssn is not found.</span></span>
 
<span data-ttu-id="36494-3818">или</span><span class="sxs-lookup"><span data-stu-id="36494-3818">Or</span></span>

- <span data-ttu-id="36494-3819">Функция Func_randomized_formatted_ssn находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3819">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3820">Функция Func_unformatted_ssn не находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3820">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3821">Функция Func_randomized_unformatted_ssn не находит содержимое, которое соответствует шаблону.</span><span class="sxs-lookup"><span data-stu-id="36494-3821">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="36494-3822">Не найдено ключевое слово из Keyword_ssn.</span><span class="sxs-lookup"><span data-stu-id="36494-3822">A keyword from Keyword_ssn is not found.</span></span>

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="36494-3823">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36494-3823">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="36494-3824">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="36494-3824">Keyword_ssn</span></span>

- <span data-ttu-id="36494-3825">Social Security</span><span class="sxs-lookup"><span data-stu-id="36494-3825">Social Security</span></span> 
- <span data-ttu-id="36494-3826">Social Security#</span><span class="sxs-lookup"><span data-stu-id="36494-3826">Social Security#</span></span> 
- <span data-ttu-id="36494-3827">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="36494-3827">Soc Sec</span></span> 
- <span data-ttu-id="36494-3828">SSN</span><span class="sxs-lookup"><span data-stu-id="36494-3828">SSN</span></span> 
- <span data-ttu-id="36494-3829">SSNS</span><span class="sxs-lookup"><span data-stu-id="36494-3829">SSNS</span></span> 
- <span data-ttu-id="36494-3830">SSN #</span><span class="sxs-lookup"><span data-stu-id="36494-3830">SSN#</span></span> 
- <span data-ttu-id="36494-3831">НН #</span><span class="sxs-lookup"><span data-stu-id="36494-3831">SS#</span></span> 
- <span data-ttu-id="36494-3832">SSID</span><span class="sxs-lookup"><span data-stu-id="36494-3832">SSID</span></span> 
   

